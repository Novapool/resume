# Personality Profile - Laith Assaf

This file contains personal background, interests, technical experience, and motivations to inform authentic, personalized cover letters.

*Last updated: August 2026*

---

## Academic Background

**Current Status**: Senior computer science student at Michigan State University, completing a fifth year

**Major**: Computer Science (AI/ML)
**Minor**: Economics
**Expected Graduation**: May 2027
**Recruiting for**: Summer 2027 internships
**Honors**: Dean's List x3

**Relevant Coursework**:
- CSE 331: Data Structures and Algorithms
- CSE 320: Computer Organization and ARM Assembly
- CSE 325: Computer Systems
- CSE 335: Object-Oriented Programming / Software Design
- CSE 380: Cloud Computing and Database Systems
- EC 440: International Trade Economics

---

## Leadership & Community

**MSU AI Club - Workshop Coordinator** (January 2025 - Present)
- Delivered 8+ technical workshops to 500+ attendees across 15 sessions, with 90% retention and a 4.8/5 satisfaction score
- Topics: local LLM deployment (Ollama, LM Studio), agent orchestration, AI ethics, PyTorch fundamentals
- Built a multi-agent orchestrator demo used as live workshop material, coordinating Scope, Architecture, Builder, and Reviewer agents to plan and generate a web app from a one-line idea
- Bridge the gap between theoretical knowledge and real-world implementation
- Passionate about making AI accessible to students

**MSU AI Club - Project Lead** (January 2025 - May 2025)
- Led a 4-student team building an Academic Performance Predictor on the GPT-4 API with prompt engineering, shipping course-level predictions across 50+ courses on agile sprints

---

## Technical Interests & Expertise

### Primary Interests
- **Backend Services & Infrastructure**: Passionate about server architecture, distributed systems, and scalable backend services
- **Systems Programming**: Deep interest in low-level systems, performance optimization
- **Agentic AI & AI-Native Development**: Building multi-agent systems and the tooling around them, not just using AI assistants. Interested in orchestration, context management, and how you actually evaluate whether an agent is working
- **Applied Reinforcement Learning**: Training agents against real opponents and measuring them honestly
- **AI/ML Applications**: Practical applications of AI, especially in automation and real-time processing
- **Database Architecture**: Microservices, distributed databases, query optimization

### Technical Stack
- **Languages**: Python, C++, C#, TypeScript, SQL, ARM Assembly
- **AI/ML**: PyTorch, scikit-learn, pandas, NumPy; PPO / reinforcement learning, MCTS, behavior cloning, CNNs
- **AI Engineering**: LLM APIs (Anthropic, OpenAI), agent orchestration, MCP, local inference (Ollama, LM Studio), model evaluation
- **Backend**: FastAPI, Flask, Express, Node.js, Socket.io, REST APIs, WebSockets
- **Web**: React, Next.js, Tailwind, Streamlit
- **Data**: PostgreSQL, Firebase, ETL and preprocessing pipelines
- **Infrastructure**: Docker, Linux server administration, networking, VPN setup, Railway, Vercel, Git
- **Enterprise IT**: Active Directory, Intune, Ivanti MDM, Power Automate, endpoint imaging

### Personal Infrastructure
- Operates home lab with rack server (128GB+ RAM)
- Runs multiple services: Plex media server, Minecraft servers, VPN infrastructure
- Hands-on experience with Docker containerization and service orchestration
- Self-taught in server administration and networking

### Working Method
- Built a personal agentic development system: 10 subagents with defined handoffs (planner to parallel builders to reviewer, tester, simplifier, docs auditor), 11 lifecycle hooks, and 5 reusable skills, applied across 44 repositories
- Designed a tiered documentation protocol where every milestone declares a pre-registered, testable success gate *before* implementation starts. "Faster" has to become "LCP under 2.5s measured by X" before any code gets written
- The same discipline shows up in the ML work: when a code review turned up four confounds inflating results, restated every affected number and reopened two milestones rather than quoting the better figure

---

## Notable Projects

### Pokemon Battle Agent - Reinforcement Learning (May 2026 - Present)
- Behavior cloning on human replay data, anchored PPO fine-tuning of an MLP policy/value network over structured per-Pokemon token observations, determinized MCTS at decision time
- 93% win rate against scripted baselines; 747 rated ladder games across 11 milestones
- Tested and retired a transformer policy against the MLP baseline; six hypotheses returned null or weak
- Ran a self-review that found four confounds invalidating prior results, then restated every affected number
- The project I care most about. It is genuinely hard and the honest answer is that the ladder gap is still open
- **Approved cover-letter framing for this project lives in `CLAUDE.md` under "Reference Paragraph".** Use it once per letter, in the project paragraph only

### Agentic Development System (January 2026 - Present)
- 10-agent orchestration pipeline with a single transient plan file as the handoff contract, applied across 44 repositories
- 11 lifecycle hook events enforcing project conventions automatically instead of relying on prompt discipline
- Tiered documentation protocol with pre-registered success gates, plus 5 reusable skills

### Bonfire Platform & Ember Framework (December 2025 - April 2026)
- Published **Ember**, an open-source TypeScript framework for multiplayer party games (3 npm packages under @bonfire-ember)
- Phase state machine, WebSocket room orchestration, and player lifecycle collapsed into a 5-hook API, giving 80%+ code reuse on every new game build
- Multi-room orchestration on Express + Socket.io namespaces with Firebase Realtime DB state sync, 4 concurrent games on a single Railway server
- Successor to the earlier Intimacy Ladder party-game webapp; the framework came out of building the game twice

### SoundSense - Real-Time Audio Classification (October 2025)
- **2nd Place at MHacks 2025** (300+ participants, 24-hour hackathon)
- YAMNet CNN on MemryX MXA2301 edge accelerators, 95% accuracy at under 50ms latency across 521 AudioSet classes
- Flask + WebSocket pipeline delivering hazard alerts to a live web interface for hearing-impaired users, all inference on-device

### AI-Assisted Comparative Market Analysis (June 2026 - Present)
- Sold-price prediction over metro Detroit MLS history: 13.3% MAPE, 52% of estimates within 10%
- Surfaces the comparable sales behind every estimate so an agent can defend the number to a client
- Diagnosed the accuracy ceiling as a data problem, not a model problem (square footage on only 17% of sold records; lot size, parking, condition missing entirely) and gated the roadmap on closing that gap rather than shipping something an agent could not trust

### Nexus - AI-Powered SSH Terminal Management
- Multi-server SSH platform pairing live terminal access with a locally hosted LLM (Ollama, gpt-oss:20b)
- Natural-language requests translated into suggested shell commands behind a safety validation layer, so nothing executes unreviewed
- FastAPI backend, Svelte frontend, real-time terminal I/O over WebSockets, Dockerized

### Toyota GR Cup Telemetry Analysis
- Hackathon project modeling tire degradation across 3,257 laps from 7 racetracks
- R² = 0.631 on high-frequency telemetry loaded into PostgreSQL with ML-ready preprocessing pipelines

---

## Career Motivations & Goals

### Dream Companies
- **Valve Corporation**: Specifically interested in backend services, not game development
- Companies with strong infrastructure challenges and technical depth
- AI-native companies building agent systems rather than bolting AI onto an existing product
- Organizations that value individual technical excellence and innovation

### What I'm Looking For
- **Summer 2027 Internship** in software engineering or applied AI
- Backend engineering roles with infrastructure focus
- Opportunities to work on scalable, distributed systems
- Teams that tackle interesting technical challenges
- Companies that value learning and technical growth

### In Progress
- **AWS Certified Solutions Architect - Associate (SAA-C03)**: studying toward it, both for the cloud fundamentals and because it is the clearest credential for architecture-leaning roles

### What Drives Me
- Building systems that solve real problems at scale
- The intersection of theoretical CS and practical engineering
- Automation and efficiency optimization
- Learning new technologies and pushing technical boundaries
- Hands-on problem solving with infrastructure and systems
- Making free software anyone can use, big open source fan

---

## Personal Interests

### Beyond Code
- **Cooking**: Particularly steak preparation and recipe development
- **Language Learning**: Currently learning Chinese (Mandarin)
- **Gaming**: Appreciation for well-engineered game infrastructure
- **Economics**: Interest in market dynamics and international trade

### Learning Philosophy
- Self-directed learner (evidenced by home lab infrastructure)
- Prefer hands-on experimentation over pure theory
- Enjoy deep dives into complex technical topics
- Value understanding the "why" behind systems design

---

## Communication Style & Personality

### Professional Traits
- Direct and technical when discussing engineering topics
- Analytical problem-solver who enjoys optimization challenges
- Collaborative leader (AI Club workshops show teaching ability)
- Self-motivated and capable of independent project execution
- Skeptical of my own numbers, which has cost me results I would rather have kept

### Authenticity Markers
- Genuine enthusiasm for infrastructure and backend systems
- Real experience running production-like environments (home lab)
- Track record of completing ambitious projects (MHacks, Ember, the RL agent)
- Balance of academic rigor and practical application
- Comfortable saying a project is not ready, and saying why

---

## Why I'm Applying

### Technical Growth
- Eager to work on production systems at scale
- Want to learn from experienced engineers in backend infrastructure
- Interested in seeing how large companies solve distributed systems challenges

### Practical Application
- Want to apply database and systems knowledge from coursework to real-world problems
- Interested in understanding production deployment pipelines and DevOps practices
- Excited to contribute to systems that serve millions of users

### Career Development
- Building toward a career in backend engineering and infrastructure
- Seeking mentorship from teams that value technical excellence
- Looking for exposure to modern cloud architecture and distributed systems

---

## Additional Context

### Current Focus Areas
- Reinforcement learning and evaluation methodology
- Agent orchestration and multi-agent system design
- Database system design and optimization
- Cloud architecture (working toward AWS SAA)

### Technical Competencies
- Strong foundation in CS fundamentals (data structures, algorithms, systems)
- Practical experience with modern development tools and workflows
- Self-sufficient in Linux/Unix environments
- Comfortable with both high-level application development and low-level systems programming

### Unique Value Proposition
- Combination of theoretical knowledge (coursework) and practical experience (home lab)
- Leadership experience through AI Club workshops
- Proven ability to deliver projects from concept to deployment
- Builds the tooling around AI systems, not just applications that call an API
- Economics minor provides business context for technical decisions
