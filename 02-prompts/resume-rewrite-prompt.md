```
You are an expert resume writer and ATS (Applicant Tracking System) optimization specialist with deep knowledge of the software robotics industry and technical recruiting pipelines.

Below is my current resume. Your task is to rewrite and restructure it according to ALL of the following requirements. Do not skip any requirement.

Out put The new resume to resume-new.md and the supplimental info to resume-suppliment.md
===================================================================
GOAL & TARGET ROLE
===================================================================

- Target: Summer 2026 internship in Software Robotics and closely
  related fields (autonomous systems, robot software engineering,
  motion planning, robot perception, ROS/ROS2 development, embedded
  robotics software, simulation engineering, controls engineering,
  SLAM, computer vision for robotics).
- Target companies include: DEKA Research, Apptronik, Figure AI,
  Yondu, NVIDIA (Isaac), Kodiak Robotics, Tesla (Optimus/AI
  Platforms), Amazon Robotics, Viam Robotics, Imperative Care,
  Skydio, Toyota Research Institute, Zoox, Boston Dynamics, and
  robotics-focused YC startups.

===================================================================
JOB MARKET INTELLIGENCE (from live research — March 2026)
===================================================================

The following data was gathered from scanning 30+ current robotics
internship postings. Use it to align every word of the resume with
what recruiters and ATS systems are actually screening for.

TOP 10 MOST REQUESTED SKILLS (by frequency across postings):
  1. C++                    (~20 roles — nearly universal)
  2. Python                 (~18 roles)
  3. Linux/Ubuntu           (~12 roles)
  4. ROS / ROS2             (~10 roles — ROS2 explicitly required
                             by DEKA, Apptronik, Figure, Yondu,
                             NVIDIA; candidate has ROS1 only)
  5. SLAM / localization    (~8 roles)
  6. Motion planning /
     trajectory optimization (~8 roles)
  7. Simulation (Gazebo,
     Isaac Sim, MuJoCo)     (~7 roles)
  8. Git / version control   (~7 roles)
  9. Computer vision /
     perception              (~7 roles)
  10. ML / DL frameworks
      (PyTorch, TensorFlow)  (~7 roles)

SKILLS THE CANDIDATE IS MISSING (appear in 3+ postings):
  - ROS2 / Nav2 / DDS middleware     (~10 roles)
  - Deep learning (PyTorch/TF)       (~7 roles)
  - CUDA / GPU programming           (~4 roles)
  - Isaac Sim                        (~4 roles)
  - Docker / containerization        (~3 roles)
  - Cloud / distributed robotics     (~4 roles)
  - Behavior trees / state machines  (~3 roles)

CANDIDATE'S UNDER-UTILIZED STRENGTHS (present on resume but buried):
  - SLAM & localization (LiDAR + RGB-D + AMCL/GraphSLAM) — called
    out by NVIDIA, Boston Dynamics, Yondu, DEKA, and AV companies.
    Must be a PRIMARY THEME in summary and project titles.
  - Motion planning & navigation (A*, DWA, Nav stack) — nearly all
    autonomy roles mention this. Deserves its own prominence.
  - Gazebo simulation & custom environments — many postings
    emphasize "high-fidelity simulation for validation." Elevate
    as "simulation-driven development and testing."
  - Embedded systems / PCB / microcontrollers — differentiator vs
    pure CS candidates. Maps to Tesla AI Platforms, Amazon Robotics
    deployment, and humanoid integration roles.

===================================================================
REQUIREMENT 1 — SECTION ORDER (Descending Importance)
===================================================================

For an internship candidate with <3 years of experience, hands-on
robotics projects are the strongest differentiator — more than
education alone. Arrange sections in this exact order:

1. NAME & CONTACT INFO
   Name, Phone, Email, LinkedIn URL, GitHub URL, Portfolio (if any).
   - Add a GitHub link. If one does not exist in the original resume,
     insert a placeholder: github.com/[your-github-username]

2. PROFESSIONAL SUMMARY
   (See Requirement 2 below for detailed sentence-by-sentence spec.)

3. TECHNICAL SKILLS
   Group into exactly FIVE subcategories:
     a) Languages: (C++, Python, C, MATLAB)
     b) Robotics Frameworks & Tools: (ROS1, Gazebo, RViz, RTAB-Map,
        CMake, Catkin — and note "ROS2/Nav2: in progress" if the
        candidate is currently upskilling)
     c) Algorithms & Methods: (AMCL, SLAM, Particle Filters, EKF,
        A*, DWA, PID Control, Sensor Fusion, Occupancy Grid Mapping,
        Differential Drive Kinematics, Pose Graph Optimization,
        Loop Closure Detection, Trajectory Optimization)
     d) Simulation & Testing: (Gazebo, Custom Environment Design,
        Sim-to-Real Validation, Regression Testing, High-Fidelity
        Sensor Simulation)
     e) Hardware & Embedded: (PCB Design, Microcontrollers,
        Interrupt-Driven Firmware, Circuit Prototyping, LiDAR,
        RGB-D Cameras, Sensor Integration)
   Place Technical Skills high because ATS bots scan the top third
   of the resume first. This section acts as a keyword anchor.

4. PROJECTS
   This is the most important content section for this candidate.
   Rename the current "Experience and Leadership" entries that are
   project-based (AMCL, SLAM Mapping, Autonomous Navigation,
   Gazebo Environment, Ball-Chasing Robot) into a dedicated
   "Projects" section.

   CRITICAL — RENAME PROJECT TITLES to match posting language:

     Current title                  → Rewrite to
     ─────────────────────────────────────────────────────────
     "Monte Carlo Localization       → "Probabilistic Robot Localization
      (AMCL)"                          using AMCL with LiDAR & Odometry
                                       Fusion"

     "SLAM Mapping System"           → "LiDAR–RGB-D SLAM Pipeline for
                                       3D Point Cloud Mapping &
                                       Loop-Closure Optimization"

     "Autonomous Navigation Robot"   → "Autonomous Multi-Goal Navigation
                                       with A*/DWA Motion Planning"

     "Gazebo Environment Design"     → "High-Fidelity Gazebo Simulation
                                       for Localization & Navigation
                                       Regression Testing"

     "Autonomous Ball-Chasing Robot" → "Real-Time Visual Tracking &
                                       Pursuit Robot with PID Control"

   For each project:
     - Use the renamed descriptive title
     - Include technologies used in parentheses after the title
     - Include date range
     - Write 2–3 impact-driven bullets (action verb + what + metric)

   Order projects by relevance to software robotics, not just
   chronology. Place the strongest robotics projects first:
     a) SLAM and localization projects first (most aligned —
        matches DEKA, NVIDIA, Boston Dynamics, Yondu)
     b) Autonomous navigation second (matches Kodiak, Zoox,
        Apptronik, Amazon Robotics)
     c) Simulation/Gazebo work third (matches Figure, NVIDIA,
        Apptronik — "validate in sim before hardware deployment")
     d) Ball-chasing / perception last (matches Skydio, TRI)

5. WORK EXPERIENCE
   Only entries that are actual employment (paid roles, co-ops,
   co-founder positions). From the current resume, this includes:
     - Prompt Kart INC. (Co-Founder)
     - UMass M5 Engineering Lab (Lead Student Engineer)

   REWRITE GUIDELINES (from job market research):

   For Prompt Kart — reframe for robotics platform/tooling roles
   (Viam, TRI Application & Deployment):
     Before: "Built & deployed Prompt Kart, a scalable full-stack
              platform using JavaScript, REST APIs..."
     After:  "Architected a full-stack monitoring and data platform
              (JavaScript, REST APIs) with real-time search and
              filtering pipelines, reducing query response time by
              [X%] — transferable to robotics telemetry dashboards
              and log visualization tools."

   For M5 Lab — reframe for embedded/hardware-close roles
   (Tesla AI Platforms, Amazon Robotics deployment, Figure):
     Before: "Designed a custom PCB integrating a microcontroller-
              based embedded system..."
     After:  "Designed and brought up a custom microcontroller-based
              control board (schematic, PCB layout, C firmware) with
              interrupt-driven I/O and peripheral communication,
              improving input responsiveness by [X%] — directly
              applicable to embedded robotics sensor interfaces."

6. EDUCATION
   - University of Massachusetts Amherst — BS Computer Engineering,
     May 2027
   - GPA: Omit (3.3 is below the 3.5 threshold for inclusion)
   - Udacity Robotics Software Engineer Nanodegree — list as a
     sub-entry under Education with 1 bullet summarizing scope:
     "Completed advanced training in ROS-based autonomous systems,
      probabilistic localization (AMCL), SLAM, and autonomous
      navigation; built modular C++/Python ROS pipelines."
   - Add a "Relevant Coursework" line listing 4–6 courses most
     aligned with robotics (e.g., Embedded Systems, Control Systems,
     Data Structures, Linear Algebra, Probability & Statistics,
     Signals & Systems). Only include courses actually taken.

7. CERTIFICATIONS
   - Johnson & Johnson Robotics and Controls Job Simulation
   - Rewrite to emphasize robotics-specific skills:
     "Diagnosed control system faults in a simulated surgical
      robotic arm using Python; delivered engineering
      recommendations to improve precision and stability."

===================================================================
WHY THIS ORDER (rationale — do not include in output)
===================================================================

For an internship applicant targeting software robotics:
- TECHNICAL SKILLS up front gives ATS bots immediate keyword matches
  in the top third of the document (where most parsers weight
  highest).
- PROJECTS before Work Experience because this candidate's robotics
  work IS the projects — they demonstrate exactly the skills hiring
  managers need (SLAM, ROS, localization, navigation, simulation).
  The work experience (startup, lab) is relevant but less directly
  aligned than the robotics projects.
- EDUCATION lower because it is a qualifying credential, not a
  differentiator — every intern applicant has a degree in progress.
- CERTIFICATIONS last because simulations carry less weight than
  hands-on project work.

===================================================================
REQUIREMENT 2 — PROFESSIONAL SUMMARY
===================================================================

Write a 3–4 sentence Professional Summary (not "Objective") placed
immediately below contact info. It must:

- Sentence 1 (IDENTITY): State degree program (BS Computer
  Engineering), university (UMass Amherst), expected graduation
  (May 2027), and core technical identity in software robotics.
  Use the phrase "robotics software engineer" — this exact phrase
  appears in 20+ job titles across DEKA, NVIDIA, Intrinsic,
  Anduril, and startup postings.

- Sentence 2 (PASSION): Convey genuine drive for building autonomous
  systems that operate in the physical world. Be specific — reference
  the kind of problems that excite this candidate (e.g., making
  robots perceive, localize, and navigate real environments). Avoid
  generic filler like "passionate about technology."

- Sentence 3 (GRIT): Demonstrate persistence by referencing a
  concrete pattern from the resume — e.g., independently completing
  the Udacity Robotics Nanodegree, iterating on AMCL tuning to cut
  pose error by 3x, or building 5+ end-to-end ROS pipelines from
  scratch.

- Sentence 4 (ANCHOR): Name 2–3 strongest proof points using
  language mirrored from actual postings:
  "Built SLAM mapping pipelines with LiDAR–RGB-D fusion,
  autonomous navigation systems with A*/DWA motion planning,
  and real-time perception nodes — validated in high-fidelity
  Gazebo simulation before hardware deployment."

Constraints:
- Maximum 60 words total.
- No personal pronouns (I, my, me).
- Must read naturally — not a keyword dump.

===================================================================
REQUIREMENT 3 — SECTION TITLES (Unambiguous)
===================================================================

Use ONLY these exact section headings:

  Professional Summary    (not: Summary, About Me, Profile)
  Technical Skills        (not: Skills, Tools, Technologies)
  Projects                (not: Academic Projects, Project Work)
  Work Experience         (not: Experience, Experience and Leadership)
  Education               (not: Academic Background)
  Certifications          (not: Credentials, Training)

Remove any section that has no content. Do not include "References."

===================================================================
REQUIREMENT 4 — ATS & AI RANKING OPTIMIZATION
===================================================================

Rewrite every bullet point to maximize ATS ranking:

1. KEYWORD DENSITY: Naturally embed these high-value keywords where
   truthful (never fabricate experience). This list is ordered by
   frequency across 30+ real postings scanned in March 2026:

   TIER 1 — appear in 8+ postings (MUST appear on resume):
   C++, Python, Linux, ROS, SLAM, LiDAR, motion planning,
   path planning, Gazebo, Git, sensor fusion, computer vision,
   autonomous navigation, localization, pose estimation

   TIER 2 — appear in 4–7 postings (include where truthful):
   ROS2, Nav2, control systems, PID, embedded systems,
   real-time systems, CMake, Catkin, RTAB-Map, RGB-D,
   odometry, point cloud, occupancy grid, particle filter,
   EKF, A*, DWA, loop closure, graph optimization,
   hardware-software integration, microcontrollers, MATLAB,
   simulation, kinematics, trajectory optimization,
   behavior execution, sim-to-real

   TIER 3 — appear in 3+ postings (add if candidate has exposure):
   Docker, CI/CD, URDF, MoveIt, OpenCV, PCL, CUDA, Isaac Sim,
   PyTorch, TensorFlow, reinforcement learning, behavior trees,
   state machines, unit testing, integration testing, agile,
   DDS, cloud robotics, inverse kinematics, forward kinematics

2. ACTION-VERB LED BULLETS: Start every bullet with a strong, unique
   action verb. Never repeat the same verb within a section. Use
   verbs like: Engineered, Architected, Implemented, Optimized,
   Deployed, Integrated, Automated, Designed, Developed, Validated,
   Accelerated, Reduced, Calibrated, Programmed, Prototyped,
   Debugged, Benchmarked, Fused, Tuned.

3. QUANTIFIED IMPACT: Every bullet must include at least one metric
   (percentage improvement, time saved, accuracy achieved, error
   reduction, count of components, etc.). Preserve all existing
   metrics from the original resume:
     - Pose estimation error: 18cm → 6cm (67% reduction)
     - Tracking oscillation: reduced by 42%
     - Response time: 1.8s → 0.9s (50% improvement)
     - Color segmentation: 30 FPS
     - Collision-free navigation: 95% of dynamic obstacles
     - Loop-closure: 50+ nodes
   For bullets without metrics, insert realistic placeholders
   formatted as [X%] or [Xms] for the candidate to fill in.

4. ATS-SAFE FORMATTING:
   - Single-column layout. No tables, graphics, icons, or columns.
   - No headers/footers (ATS parsers often skip them).
   - Standard fonts only (in the formatting note, not in output).
   - Section titles in ALL CAPS or bold — both are ATS-safe.

===================================================================
REQUIREMENT 5 — BULLET POINT REWRITES (before/after examples)
===================================================================

Use these as models for tone, keyword density, and structure.
Apply the same pattern to ALL bullets in the resume.

1. SLAM / Localization bullet:
   Before: "Deployed an RTAB-Map SLAM pipeline integrating LiDAR
            and RGB-D data for 3D point cloud generation."
   After:  "Deployed an RTAB-Map SLAM pipeline fusing LiDAR and
            RGB-D sensor data for real-time 3D point cloud mapping
            and occupancy grid generation, achieving centimeter-
            level map accuracy across 50+ pose-graph nodes."

2. Navigation bullet:
   Before: "Integrated global A* planner with DWA local planner
            achieving collision-free navigation in 95% of dynamic
            obstacles."
   After:  "Integrated global A* path planning with Dynamic Window
            Approach (DWA) local trajectory optimization, achieving
            collision-free autonomous navigation in 95% of dynamic
            obstacle scenarios with zero human intervention."

3. Embedded / Hardware bullet:
   Before: "Designed a custom PCB integrating a microcontroller-
            based embedded system with peripheral device
            communication."
   After:  "Designed and brought up a custom microcontroller-based
            embedded control board (schematic + PCB + C firmware)
            with interrupt-driven I/O for motor and sensor
            interfaces, improving input responsiveness by [X%]
            under real-time constraints."

4. Simulation / Testing bullet:
   Before: "Architected a high-fidelity Gazebo simulation with
            custom C++ plugins to validate robot-world interactions."
   After:  "Architected high-fidelity Gazebo simulation environments
            with custom C++ plugins for sim-to-real validation of
            SLAM and navigation pipelines, enabling regression
            testing across [X] multi-object scenarios before
            hardware deployment."

5. Full-stack / Tooling bullet (for Viam/TRI-style roles):
   Before: "Built & deployed Prompt Kart, a scalable full-stack
            platform using JavaScript, REST APIs..."
   After:  "Architected a full-stack data platform (JavaScript,
            REST APIs, secure auth) with real-time search/filter
            pipelines, reducing query latency by [X%] — directly
            transferable to robotics telemetry dashboards and
            log visualization tools."

===================================================================
REQUIREMENT 6 — ADDITIONAL RULES
===================================================================

- Remove all personal pronouns (I, my, me).
- Limit to 1 page (this candidate has <3 years of experience).
- Use reverse chronological order within each section, EXCEPT for
  Projects — order those by relevance to target role (see Req 1.4).
- Spell out acronyms on first use: e.g., "Simultaneous Localization
  and Mapping (SLAM)", "Robot Operating System (ROS)".
- For each project: descriptive title, (technologies), date range,
  2–3 bullets.
- For work experience: company, title, location, date range,
  2–3 bullets.
- Separate the "Languages" line (English, Telugu, Hindi) from
  Technical Skills — place it at the very bottom as a single line:
  "Languages: English, Telugu, Hindi" (outside any section, or as
  the last line of the resume).

===================================================================
OUTPUT FORMAT
===================================================================

Return the rewritten resume as clean markdown text that I can copy
into a Word/Google Docs template. Use this structure:

  # Mukund Jeedigunta
  (contact line)

  ## PROFESSIONAL SUMMARY
  (paragraph)

  ## TECHNICAL SKILLS
  (subcategorized list)

  ## PROJECTS
  (entries — renamed titles, ordered by relevance)

  ## WORK EXPERIENCE
  (entries — reframed for robotics transferability)

  ## EDUCATION
  (entries — with relevant coursework line)

  ## CERTIFICATIONS
  (entries)

  Languages: English, Telugu, Hindi

After the resume, provide these four supplementary outputs:

1. **ATS Keywords Checklist** — A table with columns:
   [Keyword | Tier (1/2/3) | Present? (Y/N) | Where it appears]
   covering every keyword from Requirement 4.1, organized by tier.

2. **Suggested LinkedIn Headline** — A single line optimized for
   recruiter search (under 120 characters), e.g.:
   "Robotics Software Engineer | ROS · SLAM · C++ · Motion Planning
    | UMass Amherst '27"

3. **Suggested LinkedIn About Section** — A 3–4 sentence first-person
   paragraph echoing the Professional Summary, suitable for pasting
   into LinkedIn.

4. **Top 5 Roles to Apply (from research)** — Based on resume fit,
   list the 5 best-match open internships with company name, role
   title, and one sentence explaining why this resume is a strong
   fit for each:
     - DEKA Research — Robotics SW Engineer Intern (near-perfect
       ROS/SLAM/nav/Gazebo match)
     - Apptronik — Autonomy SW Intern (ROS + Gazebo + controls +
       embedded aligns with humanoid autonomy stack)
     - Figure AI — Robotics Integration Intern (controls, kinematics,
       hardware-software debugging, sim validation)
     - Yondu — Autonomous Navigation Intern (SLAM + A*/DWA + LiDAR
       sensor integration for warehouse AMRs)
     - Kodiak Robotics — Motion Planning Intern (A*, DWA, trajectory
       planning, SLAM, strong C++/Python)

===================================================================
MY CURRENT RESUME (to be rewritten)
===================================================================

@resume.md
```
