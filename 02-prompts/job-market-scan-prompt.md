# Internship Job Market Research Prompt

Use this prompt with an AI assistant that has web/search access (e.g., ChatGPT with browsing, Perplexity, Google Gemini, or Claude with web search enabled). AI tools without live web access will return stale or fabricated results.

---

```
You are a career research analyst specializing in robotics and
autonomous systems internship hiring. Conduct a comprehensive scan
of current internship job postings and produce a structured report
I can use to fine-tune my resume.

===================================================================
CANDIDATE PROFILE (for matching purposes)
===================================================================

- BS Computer Engineering, UMass Amherst (May 2027)
- Core skills: ROS1, C++, Python, SLAM (RTAB-Map, GraphSLAM,
  FastSLAM), AMCL, LiDAR, RGB-D perception, sensor fusion,
  Gazebo simulation, motion planning (A*, DWA), PID control,
  embedded systems, PCB design, microcontrollers, CMake, Catkin,
  Linux, Git, MATLAB
- Project experience: autonomous navigation, localization,
  3D point cloud mapping, real-time object tracking, custom
  Gazebo environments, full-stack web development
- Completed Udacity Robotics Software Engineer Nanodegree

===================================================================
SEARCH SCOPE
===================================================================

Search the following platforms for internship postings (Summer 2026,
Fall 2026, or any currently open robotics intern roles):

PLATFORMS TO SEARCH:
  1. LinkedIn Jobs (linkedin.com/jobs)
  2. Indeed (indeed.com)
  3. Glassdoor (glassdoor.com)
  4. Handshake (joinhandshake.com)
  5. Google Jobs (google.com/jobs)
  6. Company career pages (see target companies below)
  7. RoboticsCareer.org / Robotics job boards
  8. GitHub Jobs alternatives (Wellfound/AngelList, Y Combinator
     Work at a Startup — workatastartup.com)

TARGET COMPANIES (check career pages directly):
  - Boston Dynamics
  - Waymo
  - Tesla (Optimus / Robotics division)
  - NVIDIA (Isaac Robotics)
  - Amazon Robotics
  - Agility Robotics
  - Intrinsic (Alphabet)
  - Zoox
  - Motional
  - Aurora Innovation
  - Nuro
  - iRobot
  - Sarcos Robotics
  - Locus Robotics
  - Fetch Robotics / Zebra Technologies
  - Diligent Robotics
  - Covariant
  - Skydio
  - Shield AI
  - Anduril Industries
  - Reliable Robotics
  - Apptronik
  - Figure AI
  - 1X Technologies
  - Symbotic
  - Plus One Robotics
  - RightHand Robotics
  - Berkshire Grey
  - Kodiak Robotics
  - Gatik
  - Cruise (if still hiring)

SEARCH QUERIES TO USE (adapt per platform):
  - "robotics software engineer intern"
  - "robotics intern ROS"
  - "autonomous systems intern"
  - "SLAM intern"
  - "robot perception intern"
  - "motion planning intern"
  - "controls engineering intern"
  - "simulation engineer intern robotics"
  - "embedded robotics intern"
  - "computer vision intern robotics"
  - "ROS2 developer intern"
  - "robot software intern summer 2026"

===================================================================
OUTPUT FORMAT
===================================================================

Produce the report in FOUR parts:

-----------------------------------------------------------------
PART 1: JOB POSTINGS TABLE
-----------------------------------------------------------------

A table with these columns, sorted by match strength (best fit first):

| # | Company | Role Title | Location | Posted Date | Application Deadline | Link | Match Score (1-10) |

- Match Score: Rate 1–10 how well the candidate profile above
  fits the listed requirements (10 = near-perfect match).
- Include at least 30 postings if available. More is better.
- Include remote/hybrid roles and note location flexibility.
- If a role has closed, mark it as "[Closed]" but still include
  it — the requirements are useful for resume tuning.

-----------------------------------------------------------------
PART 2: APPLICATION GUIDE (Ready-to-Apply Details)
-----------------------------------------------------------------

For every posting in Part 1 that is currently OPEN and has a Match
Score of 6 or higher, provide a detailed application card:

Format each entry as:

### [Company] — [Role Title]

  APPLICATION LINK:    [Direct URL to apply — not the search result
                        page, but the actual application portal or
                        "Apply Now" page. If the posting is on
                        LinkedIn/Indeed, provide BOTH the aggregator
                        link and the company career page link.]

  STATUS:              Open / Closing Soon / Rolling
  DEADLINE:            [Exact date if listed, or "Rolling" / "ASAP"]
  LOCATION:            [City, State | Remote | Hybrid]
  COMPENSATION:        [Hourly rate or stipend if listed, else "Not listed"]
  DURATION:            [e.g., 12 weeks, May–Aug 2026, flexible]
  VISA/SPONSORSHIP:    [Yes / No / Not specified]
  REQUIRES COVER LETTER: [Yes / No / Optional]

  KEY REQUIREMENTS (verbatim from posting):
    - [Requirement 1]
    - [Requirement 2]
    - [Requirement 3]
    - [...up to 8 most important requirements]

  PREFERRED/BONUS QUALIFICATIONS:
    - [Preferred 1]
    - [Preferred 2]
    - [...]

  CANDIDATE FIT NOTES:
    - Strengths: [Which of the candidate's skills/projects directly
      match the requirements — name specific resume items]
    - Gaps: [Any listed requirements the candidate does not have —
      note if they are "required" vs "preferred"]
    - Tailoring tip: [One specific suggestion for customizing the
      resume or cover letter for THIS role, e.g., "Lead with the
      SLAM project and emphasize the 3x pose error reduction —
      this posting explicitly asks for localization experience"]

  HOW TO APPLY:
    - [Step-by-step if the process is non-standard, e.g.,
      "Apply on Workday portal → Upload resume → Complete
      HackerRank assessment within 7 days"]
    - [If referral-friendly, note: "Company is known to
      prioritize employee referrals — check LinkedIn for
      UMass alumni at this company"]

  RECRUITER/CONTACT (if findable):
    - [Recruiter name + LinkedIn profile if listed on the posting
      or identifiable from the company's recruiting team page]
    - [If not findable: "Not listed — consider reaching out to
      the hiring manager or team lead on LinkedIn"]

Sort the application cards in the same order as Part 1 (best
match first). For postings with Match Score below 6 or that are
closed, do NOT create a full card — they are already covered by
the Part 1 table.

-----------------------------------------------------------------
PART 3: SKILLS GAP ANALYSIS
-----------------------------------------------------------------

Analyze ALL the job postings found and produce:

a) MOST REQUESTED SKILLS — A ranked list of the top 20 skills/
   technologies mentioned across postings, with frequency count:

   | Rank | Skill/Technology | Times Mentioned | Candidate Has? (Y/N) |

b) SKILLS THE CANDIDATE IS MISSING — List every skill that appears
   in 3+ postings but is NOT in the candidate profile above.
   For each missing skill, note:
   - How many postings require it
   - How hard it is to acquire (Easy / Medium / Hard)
   - Suggested resource to learn it (course, tutorial, project)

   Format:
   | Missing Skill | Frequency | Difficulty | Suggested Resource |

c) CANDIDATE'S UNDERUTILIZED STRENGTHS — Skills the candidate has
   that appear frequently in postings but may not be prominent
   enough on the resume. These should be elevated in resume
   bullet points.

-----------------------------------------------------------------
PART 4: RESUME FINE-TUNING RECOMMENDATIONS
-----------------------------------------------------------------

Based on the job postings analysis, provide:

a) KEYWORDS TO ADD to the resume (not currently present but
   frequently required):
   - List each keyword and suggest which resume section/bullet
     it should be inserted into.

b) KEYWORDS TO EMPHASIZE (already on resume but should be more
   prominent — move to summary, project titles, or skill
   subcategories):

c) BULLET POINT REWRITES — For the 3–5 resume bullets that would
   benefit most from alignment with posting language, provide
   a before/after rewrite showing how to mirror the terminology
   recruiters and ATS systems are scanning for.

d) PROJECT TITLE SUGGESTIONS — If any of the candidate's project
   names should be reworded to better match job posting language,
   suggest alternatives. Example:
     Before: "Autonomous Ball-Chasing Robot"
     After:  "Real-Time Visual Tracking & Pursuit Robot"

e) MISSING PROJECT SUGGESTIONS — If there is a common project
   type that appears in 5+ postings as a desired qualification
   and the candidate does not have it, suggest 1–2 small projects
   the candidate could build to fill that gap. For each:
   - Project idea (1 sentence)
   - Technologies involved
   - Estimated scope (weekend project vs. multi-week)
   - Which postings it would strengthen the application for

===================================================================
IMPORTANT NOTES
===================================================================

- Only include REAL postings with verifiable links. Do not fabricate
  job listings or URLs.
- If a platform is inaccessible, note that and move on.
- Prefer postings from the last 60 days. Older postings can be
  included if the role is recurring (companies that hire robotics
  interns every cycle).
- If a company has no current intern posting but is known to hire
  robotics interns seasonally, note it in a separate "Watch List"
  table with expected posting windows.
- For the skills gap analysis, only count skills that are explicitly
  listed in job requirements — do not infer.
```
