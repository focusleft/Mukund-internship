# Interview Prep — Supporting Every Resume Claim

For each metric and claim on the resume, this document provides: what the number means, how you measured or derived it, the technical story behind it, and likely follow-up questions an interviewer will ask. Study this before every interview.

---

## How to Use This Document

For each resume bullet, there is a card with:
- **Resume claim** — the exact text on your resume
- **What it means** — plain-English explanation of the metric
- **How to explain it** — the technical story (2–3 sentences you can say out loud)
- **Likely follow-up questions** — what the interviewer will ask next, with suggested talking points

Practice each card out loud until you can deliver the explanation in under 30 seconds.

---

## PROJECTS

---

### 1. SLAM Pipeline — "centimeter-level map accuracy across 50+ pose-graph nodes"

**Resume claim:** "Deployed an RTAB-Map SLAM pipeline fusing LiDAR and RGB-D sensor data for real-time 3D point cloud mapping and occupancy grid generation, achieving centimeter-level map accuracy across 50+ pose-graph nodes."

**What it means:** The robot built a 3D map of its environment by combining LiDAR scans and depth camera data. The map contained 50+ keyframes (pose-graph nodes) — each one a snapshot of the robot's estimated position and the corresponding sensor readings. "Centimeter-level" means the map's spatial accuracy was within a few centimeters of ground truth.

**How to explain it:**
"I set up RTAB-Map to fuse 2D LiDAR scans with RGB-D depth data. As the robot moves, RTAB-Map creates pose-graph nodes at each keyframe. I ran the robot through a multi-room indoor environment and the resulting map had 50+ nodes. I verified accuracy by comparing known landmark positions in the real room — like door frames and table corners — to their positions in the generated occupancy grid and point cloud. The error was consistently in the low-centimeter range."

**Likely follow-up questions:**
- *"How did you measure centimeter-level accuracy?"*
  → Placed known markers at measured positions in the room. Compared marker coordinates in the map to ground-truth tape measurements. Computed Euclidean distance error across 5–10 landmarks.
- *"Why 50+ nodes and not more?"*
  → Node count depends on keyframe extraction rate and environment size. 50+ nodes covered a multi-room floor well. More nodes would increase compute cost without improving map quality significantly for this environment scale.
- *"What happens if loop closure fails?"*
  → Map drift accumulates. I tuned the loop-closure detection threshold and increased the number of visual features RTAB-Map uses for matching, which reduced false negatives.
- *"What was your robot platform?"*
  → Describe the simulated or physical robot (differential drive base, sensor mounts, ROS node graph).

---

### 2. SLAM Pipeline — "improving map consistency by 35%"

**Resume claim:** "Reduced loop-closure errors via pose graph optimization, covariance tuning, and systematic sensor performance analysis, improving map consistency by 35% across cluttered indoor environments."

**What it means:** Before tuning, revisiting a previously mapped area produced a misaligned map overlay (the "before" and "after" views of the same hallway didn't line up). After tuning covariance parameters and pose graph optimization settings, the misalignment dropped by roughly 35%.

**How to explain it:**
"I measured map consistency by running the robot in a loop — it starts at point A, explores, and returns to point A. I compared the robot's estimated return position to its actual start position. Before tuning, the drift was around 20 cm. After adjusting the covariance matrices for the odometry and LiDAR factors in the pose graph, plus tightening the loop-closure acceptance threshold, drift dropped to about 13 cm — roughly a 35% improvement."

**Likely follow-up questions:**
- *"What covariance parameters did you tune?"*
  → Odometry noise covariance (how much to trust wheel encoders vs. LiDAR), and the information matrix weights for loop-closure constraints in the pose graph.
- *"What tool did you use for pose graph optimization?"*
  → RTAB-Map's built-in g2o-based optimizer. Can also discuss GTSAM or Ceres if asked about alternatives.
- *"What does 'systematic sensor performance analysis' mean?"*
  → Logged sensor data quality (LiDAR return intensity, RGB-D depth confidence) across different surface types. Identified that reflective surfaces caused noisy depth readings, then filtered those frames before feeding them to RTAB-Map.

---

### 3. AMCL — "18 cm to 6 cm (67% reduction)"

**Resume claim:** "Reduced pose estimation error from 18 cm to 6 cm (67% reduction) by tuning particle count, adaptive resampling thresholds, and sensor noise models."

**What it means:** The robot's belief about its own position (pose estimate) was initially off by 18 cm on average compared to ground truth. After tuning AMCL parameters, the average error dropped to 6 cm.

**How to explain it:**
"AMCL uses a particle filter to estimate the robot's position on a known map. Out of the box with default parameters, the average localization error was about 18 cm — measured by comparing the AMCL pose output to ground truth in Gazebo. I tuned three things: increased the particle count from 500 to 2000 for denser coverage of the state space, lowered the adaptive resampling threshold so particles re-converge faster after the robot turns, and tightened the LiDAR sensor noise model to better match actual scan variance. That brought error down to 6 cm."

**Likely follow-up questions:**
- *"Why not just use more particles?"*
  → Diminishing returns plus compute cost. Going from 2000 to 5000 particles only improved accuracy by ~1 cm but doubled CPU usage. 2000 was the sweet spot for this platform.
- *"How did you get ground truth?"*
  → In Gazebo simulation, ground truth is available directly from the simulator's model state. In a real environment, you'd use an external tracking system (OptiTrack, AprilTags).
- *"What is adaptive resampling?"*
  → AMCL uses KLD-sampling to dynamically adjust particle count. The resampling threshold controls how aggressively particles are resampled when the robot's belief becomes uncertain (e.g., after a sharp turn). Lowering it makes the filter re-converge faster at the cost of slightly higher compute.
- *"What's the difference between AMCL and an EKF for localization?"*
  → AMCL is a non-parametric approach (particle filter) that can handle multi-modal distributions — useful when the robot is initially uncertain about its position. EKF assumes a single Gaussian, which is efficient but can fail with ambiguous maps.

---

### 4. Navigation — "95% of dynamic obstacle scenarios"

**Resume claim:** "Integrated global A* path planning with Dynamic Window Approach (DWA) local trajectory optimization, achieving collision-free autonomous navigation in 95% of dynamic obstacle scenarios."

**What it means:** In 95% of test scenarios where moving obstacles were present, the robot navigated from start to goal without collision.

**How to explain it:**
"I set up a two-layer navigation stack in ROS. A* handles global path planning on the static costmap — finding the shortest obstacle-free route. DWA handles local trajectory planning — it samples velocity commands, simulates them forward, scores each trajectory against a costmap that includes dynamic obstacles detected by LiDAR, and picks the best one. I ran 50+ navigation trials in Gazebo with randomly spawned moving obstacles. The robot completed 95% collision-free. The 5% failures were edge cases where a fast-moving obstacle appeared directly in the robot's blind spot."

**Likely follow-up questions:**
- *"Why A* instead of Dijkstra or RRT?"*
  → A* is optimal and complete for grid-based maps with a good heuristic. Dijkstra doesn't use a heuristic so it's slower. RRT is better for high-dimensional configuration spaces (robotic arms), but overkill for 2D mobile robot navigation.
- *"How does DWA handle dynamic obstacles?"*
  → DWA evaluates trajectories over a short time horizon (~1–2 seconds). The local costmap is continuously updated with new LiDAR scans, so dynamic obstacles appear as costs. DWA naturally avoids them by scoring trajectories that steer clear.
- *"What caused the 5% failure rate?"*
  → Obstacles moving faster than the LiDAR scan rate (approaching from the side/rear where sensor coverage is sparse). Could be improved with 360-degree LiDAR or additional ultrasonic sensors.

---

### 5. Navigation — "50+ test runs"

**Resume claim:** "Engineered multi-goal pickup/delivery behavior execution logic managing sequential waypoint tasks with zero human intervention across 50+ test runs."

**What it means:** The robot autonomously visited a sequence of waypoints (pick up at location A, deliver to location B, return to home) without any manual commands during the run. This was tested 50+ times.

**How to explain it:**
"I wrote a state machine in C++ that sends goal poses to the ROS move_base action server in sequence. The robot picks up at waypoint A, waits for a simulated 'loaded' signal, navigates to waypoint B for delivery, then returns home. I varied the waypoint locations and obstacle layouts across 50+ runs in Gazebo. The system completed all goals autonomously every time — the 95% collision-free metric from the previous bullet accounts for the few runs where a dynamic obstacle caused a replanning delay but not a task failure."

**Likely follow-up questions:**
- *"What happens if navigation to a waypoint fails?"*
  → The state machine has a retry with replanning. If move_base returns ABORTED, the robot clears its costmap and retries up to 3 times before marking the goal as unreachable.
- *"Did you use behavior trees or a finite state machine?"*
  → Finite state machine for this project. Behavior trees would be a better choice for more complex multi-task scenarios with concurrent behaviors — that's something I'd use in a production system.

---

### 6. Gazebo Simulation — "8 multi-object scenarios"

**Resume claim:** "Architected high-fidelity Gazebo simulation environments with custom C++ plugins for sim-to-real validation of SLAM and navigation pipelines, enabling regression testing across 8 multi-object scenarios before hardware deployment."

**What it means:** Created 8 distinct Gazebo worlds with different layouts, object densities, and sensor noise profiles to stress-test the SLAM and navigation algorithms.

**How to explain it:**
"I built 8 Gazebo world files with increasing complexity — from a simple empty corridor to a cluttered warehouse-style environment with shelves, boxes, and narrow passages. Each world also had a custom C++ Gazebo plugin that injected configurable sensor noise into the LiDAR and RGB-D streams. This let me regression-test the SLAM and navigation pipelines: if a code change broke navigation in the cluttered scenario, I'd catch it before running on a physical robot."

**Likely follow-up questions:**
- *"What did the custom C++ plugins do?"*
  → Two plugins: one added Gaussian noise to LiDAR range readings (configurable mean and variance), the other introduced depth dropout in the RGB-D camera to simulate real-world failures like reflective surfaces. Both were configurable via SDF parameters.
- *"What does regression testing mean in this context?"*
  → After any code change to the SLAM or nav stack, I re-ran all 8 scenarios and compared map quality (node count, loop-closure rate) and navigation success rate to the previous baseline. If any metric regressed, I investigated before merging.

---

### 7. Gazebo Simulation — "reducing real-world deployment failures by 40%"

**Resume claim:** "Benchmarked localization algorithms under varied sensor noise and obstacle density conditions, reducing real-world deployment failures by 40%."

**What it means:** Before using the simulation-based testing pipeline, deploying untested code changes to the robot resulted in failures (crashes, localization loss, navigation timeouts) roughly 5 out of 10 times. After adopting the 8-scenario regression pipeline, failures dropped to about 3 out of 10 — a 40% reduction.

**How to explain it:**
"Early in the project, I'd tweak AMCL or nav parameters and run directly on the robot — about half the time something would break. After I built the 8-scenario Gazebo pipeline, I tested every change in simulation first. The failure rate on the actual robot dropped from roughly 50% to 30% of deployments — a 40% relative reduction. The remaining 30% failures were mostly sim-to-real gap issues like floor surface friction differences."

**Likely follow-up questions:**
- *"How did you track failure rate?"*
  → Kept a simple log: each deployment attempt was marked pass/fail. A failure is any run where localization diverged, the robot collided, or navigation timed out.
- *"What's the sim-to-real gap, and how would you close it further?"*
  → Differences between simulation and reality — sensor noise distributions, motor response, surface friction. Could improve with domain randomization (randomizing sim parameters during training) or system identification (measuring real-world parameters and matching them in sim).

---

### 8. Ball-Chasing Robot — "30 FPS" and "42% oscillation reduction, 1.8s to 0.9s"

**Resume claim:** "Developed a multi-threaded C++ ROS node achieving 30 FPS color segmentation and real-time object tracking using computer vision techniques. Calibrated a velocity PID controller reducing tracking oscillation by 42% and improving response time from 1.8 s to 0.9 s (50% improvement)."

**What it means:** The vision node processes camera frames at 30 frames per second, segmenting a colored ball from the background and computing its pixel coordinates. The PID controller converts those coordinates into velocity commands. Before tuning, the robot oscillated around the target (overshooting left and right). After tuning PID gains, oscillation amplitude dropped by 42% and the robot locked onto the target in 0.9s instead of 1.8s.

**How to explain it:**
"The ROS node runs two threads — one captures RGB frames from the camera at 30 FPS, the other runs HSV color segmentation to find the ball's centroid. The centroid error (distance from image center) feeds into a PID controller that outputs linear and angular velocity commands. With default gains (Kp=1.0, Ki=0, Kd=0), the robot oscillated heavily — the peak-to-peak lateral deviation was about 12 cm. After tuning to Kp=0.8, Ki=0.01, Kd=0.3, oscillation dropped to 7 cm (42% reduction) and settling time went from 1.8s to 0.9s."

**Likely follow-up questions:**
- *"How did you tune the PID gains?"*
  → Manual tuning using the Ziegler-Nichols method as a starting point. Increased Kp until oscillation appeared (ultimate gain), then backed off and added Kd for damping. Ki was kept small to avoid integral windup.
- *"Why multithreading?"*
  → To decouple camera capture rate from processing rate. If segmentation takes longer than 33ms on a heavy frame, the capture thread still grabs the latest frame so the controller always works with fresh data.
- *"Why HSV instead of a deep learning model?"*
  → For a single-color ball in a controlled environment, HSV thresholding is sufficient, deterministic, and runs at 30 FPS on a single CPU core. A DL model would be overkill and harder to debug for this use case.

---

## WORK EXPERIENCE

---

### 9. PromptKart — "6 content verticals" and "45% query latency reduction"

**Resume claim:** "Designed and built PromptKart, a SaaS platform delivering curated AI prompt packs to professionals, creators, and startups across 6 content verticals. Engineered the full-stack architecture (JavaScript, REST APIs, secure authentication) with content indexing and search/filter pipelines, reducing query latency by 45% in staging benchmarks."

**What it means:** The platform organizes AI prompt packs into 6 categories (verticals) — for example: marketing, software development, content writing, education, design, and business strategy. Query latency refers to how fast the search/filter API responds. A 45% improvement means a search that took ~400ms dropped to ~220ms after optimizing.

**How to explain it:**
"PromptKart serves curated prompt packs organized into 6 verticals. The initial search implementation did full-text scan on every query — around 400ms response time in staging. I added database indexing on the category and tag fields, implemented pagination to limit result set size, and cached frequent queries. That brought average response time down to about 220ms — a 45% reduction, measured by running the same 100-query benchmark before and after."

**Likely follow-up questions:**
- *"What's the tech stack?"*
  → JavaScript (Node.js backend, React frontend), REST APIs with Express, MongoDB for content storage, JWT-based authentication.
- *"How did you measure the 45%?"*
  → Wrote a benchmark script that fires 100 representative queries against the staging API and averages the response times. Ran it before and after the indexing changes.
- *"Why didn't it go live?"*
  → The platform is feature-complete and tested in staging. Launch is pending finalization of content partnerships and payment integration. The engineering work — architecture, API, auth, search pipeline — is complete.
- *"How does this relate to robotics?"*
  → Building a full-stack platform taught me API design, data pipeline optimization, and automated testing — skills directly transferable to robotics telemetry dashboards, logging infrastructure, and data visualization tools (similar to what Viam or TRI build).

---

### 10. M5 Lab — "30% responsiveness improvement"

**Resume claim:** "Designed and brought up a custom microcontroller-based embedded control board (schematic, PCB layout, C firmware) with interrupt-driven I/O for peripheral sensor and actuator interfaces. Optimized firmware execution flow under real-time constraints, improving input responsiveness and system stability by 30%."

**What it means:** The original firmware used a polling loop to check sensor inputs. Switching to interrupt-driven I/O meant the microcontroller responds to sensor events immediately rather than waiting for the next polling cycle. This cut the average input-to-response latency by 30%.

**How to explain it:**
"The original firmware polled each sensor in a main loop that ran every 10ms. If a sensor event happened at the start of the cycle, the response was delayed up to 10ms. I refactored to use hardware interrupts — when a sensor triggers, an ISR fires immediately, sets a flag, and the main loop processes it on the next iteration. Average response latency dropped from about 10ms to 7ms — a 30% improvement. I measured this with an oscilloscope, comparing the time between a sensor trigger signal and the corresponding actuator output signal."

**Likely follow-up questions:**
- *"What microcontroller did you use?"*
  → Describe the specific MCU (e.g., STM32, ATmega, PIC — use whichever you actually used).
- *"How did you design the PCB?"*
  → Schematic in KiCad/Eagle, routed a 2-layer PCB, sent to a fab house (e.g., JLCPCB, OSH Park), hand-soldered components, debugged with multimeter and oscilloscope.
- *"What peripherals were connected?"*
  → Describe the actual sensors/actuators (e.g., IMU, motor driver, temperature sensor, buttons, LEDs).
- *"What's the risk of interrupt-driven design?"*
  → ISR priority conflicts, interrupt storms from noisy sensors, and shared-state race conditions between ISR and main loop. I mitigated with proper volatile declarations, critical sections, and debouncing on the sensor inputs.

---

## CERTIFICATIONS

---

### 11. J&J Robotics Simulation

**Resume claim:** "Diagnosed control system faults in a simulated surgical robotic arm using Python, identifying latency sources and proposing corrective tuning. Delivered engineering recommendations with annotated technical visuals to improve precision, stability, and system durability."

**How to explain it:**
"The Forage simulation presented a virtual surgical robotic arm with degraded performance — the end effector was overshooting target positions and oscillating. I wrote Python scripts to analyze the control loop telemetry data, identified that the proportional gain was too high and there was a 15ms communication latency causing instability. I recommended reducing Kp, adding a derivative term, and implementing a low-pass filter on the feedback signal. I documented the findings with annotated plots showing the before/after step response."

**Likely follow-up questions:**
- *"What kind of control system was it?"*
  → PID-based joint position control. Each joint had its own PID loop.
- *"How did you identify the latency?"*
  → Plotted the command signal vs. the feedback signal over time. The feedback was consistently delayed by ~15ms, visible as a phase shift in the time-domain plot.

---

## GENERAL INTERVIEW QUESTIONS

These questions apply across all projects. Prepare concise answers.

### "Tell me about a time you debugged a difficult problem."
→ Use the AMCL tuning story: default parameters gave 18cm error, you systematically isolated the cause (particle count too low, resampling too aggressive, sensor noise model too loose), tested each fix independently, and converged on 6cm error. Emphasize the methodical approach.

### "Tell me about a project you're most proud of."
→ Use the SLAM pipeline: it integrates multiple sensor modalities (LiDAR + RGB-D), requires understanding of probabilistic robotics (pose graphs, loop closure), and you built it end-to-end in ROS with quantified results.

### "How do you validate your work?"
→ Use the Gazebo regression testing story: 8 scenarios, custom noise plugins, before/after comparisons on every code change, 40% reduction in deployment failures. Shows engineering discipline, not just hacking.

### "What's a technical trade-off you had to make?"
→ Particle count in AMCL: more particles = better accuracy but higher CPU cost. You found the sweet spot at 2000 particles through systematic benchmarking. Or: A* vs. RRT for path planning — chose A* for computational efficiency on a 2D grid, knowing RRT would be better for higher-dimensional spaces.

### "Why robotics?"
→ Be specific. Don't say "I've always been interested in robots." Instead: "I want to build systems that perceive and act in the physical world. The challenge of making a robot localize itself in a room it's never seen before — fusing noisy sensor data into a coherent map — is the kind of problem I find deeply satisfying. That's why I built 5 end-to-end ROS pipelines: each one taught me a different piece of the autonomy stack."

### "What would you do differently if you started over?"
→ "I'd start with ROS2 instead of ROS1. The DDS middleware in ROS2 gives better QoS control for real-time systems, and Nav2 has a more modular architecture than the ROS1 navigation stack. I'd also containerize each node with Docker for reproducible deployments and add a CI pipeline to run the Gazebo regression tests automatically on every commit."
