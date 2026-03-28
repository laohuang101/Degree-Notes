# System Development Methods - Comprehensive Study Notes

## Table of Contents

1. [Information Systems Development Methods](#1-information-systems-development-methods)
2. [Structured Methodologies](#2-structured-methodologies)
3. [Agile Methodologies](#3-agile-methodologies)
4. [Process Oriented Methodologies](#4-process-oriented-methodologies)
5. [Socio-Technical Methodologies](#5-socio-technical-methodologies)
6. [System Planning](#6-system-planning)
7. [System Analysis](#7-system-analysis)
8. [System Design](#8-system-design)
9. [System Implementation](#9-system-implementation)
10. [System Deployment](#10-system-deployment)

---

## 1. Information Systems Development Methods

### Overview Table

| Concept | Description |
|---------|-------------|
| **Information System (IS)** | Collection of interrelated components that collect, process, store, and provide information to complete tasks |
| **SDLC** | System Development Lifecycle - entire process of building, launching, and maintaining an information system |
| **IS Methodology** | A specific framework/recipe to 'cook-up' a specific type of Information System |

### Information System Components

| Component | Description | Examples |
|-----------|-------------|----------|
| **Hardware** | All physical components of the information system | Servers, workstations, networks, mobile devices, scanners |
| **Software** | Programs that control hardware and produce desired results | System software (OS, security), Application software (order processing, payroll) |
| **People** | Those who interact and use the system | Stakeholders, users, IT staff (analysts, programmers, network admins) |
| **Data** | Raw material transformed into useful information | Stored in tables, linked to extract specific information |
| **Processes** | Tasks and business functions that users, managers, and IT staff perform | Day-to-day business operations |

### SDLC Phases

| Phase | Description | Key Activities | Output |
|-------|-------------|----------------|--------|
| **Planning** | Define business problem and scope, feasibility studies, project staffing | Feasibility study, resource management, project proposal | Feasibility Study Report, Initial Study Report, Project Proposal |
| **Analysis** | Define system requirements, prioritize requirements, evaluate alternatives | Data visualization, statistical analysis, data mining | System Requirement Specification (SRS) |
| **Design** | Design application architecture, user interfaces, system interfaces, database | Conceptual design, logical design, physical design | Design Specification |
| **Implementation** | Build, test, and integrate system components | Unit testing, integration testing, user acceptance testing | Fully functional system |
| **Maintenance** | Support users, enhance system, maintain system | Help desk, upgrades, patches, repairs | Ongoing support and improvements |

### People Involved in IS Development

| Role | Responsibility |
|------|---------------|
| **System Owners** | People who pay and own the system |
| **Users** | People who directly/indirectly use the new system |
| **Project Manager** | Responsible for knowing "who, what, where, when and why" of the project |
| **System Analysts** | Understand business processes and document them carefully |
| **Developers** | Use technical requirements to build deliverables and communicate status |
| **System Testers** | Ensure software meets business requirements and is free of bugs |
| **System Administrators** | Take care of the system after completion |

---

## 2. Structured Methodologies

### Overview

Structured methodologies are traditional methodologies developed in the 1970s that:
- Organize system development into phases with deliverables and milestones
- Have very detailed steps
- Require clear and fixed requirements
- Focus on error-free product
- Emphasize full documentation

### Key Methodologies

| Methodology | Description | Characteristics |
|-------------|-------------|-----------------|
| **Waterfall Model** | Sequential development process introduced in 1970s | Highly structured and rigid, promotes quality control, emphasis on documentation |
| **SSADM** | Structured Systems Analysis and Design Methodology | Rigid and document-led, good for projects with complex database design, ends at design stage |
| **V-Model** | Derived from Waterfall Model | Associates each development phase with its testing phase |

### Waterfall Model Phases

| Phase | Description |
|-------|-------------|
| **Requirements Gathering and Analysis** | Capture all requirements into System Requirement Specification (SRS) |
| **System Design** | Specify hardware and system requirements, define overall system architecture |
| **Implementation** | Develop system in small programs called units, unit testing |
| **Integration and Testing** | Test integrated system for faults and failures |
| **Deployment** | Deploy product in customer environment or release to market |
| **Maintenance** | Fix issues in client environment, enhance product with better versions |

### SSADM Phases

| Phase | Description |
|-------|-------------|
| **Feasibility Study** | Decide how viable the project really is |
| **Investigation of Current Environment** | Investigate current system and provide users with options |
| **Business System Options** | Describe scope and functionality of alternative solutions |
| **Definition of Requirements** | Refine requirements based on selected business system option |
| **Technical System Options** | Evaluate best technical products and provide detailed specification |
| **Logical Design** | Provide detailed specification of processing structures, data, and interfaces |
| **Physical Design** | Specify physical data, processes, inputs, and outputs |

### V-Model Phases

| Phase | Description |
|-------|-------------|
| **Concept of Operations** | Identify goals and objectives of proposed system |
| **Requirements Analysis and Architecture** | Collect user requirements, study SRS, figure out implementation possibilities |
| **Architecture Design/Physical Design** | Includes software architecture, database tables, interface relationships |
| **Detailed/Module Design** | Break proposed system into smaller manageable units/modules |
| **Implementation** | Build the system components |
| **Verification and Validation** | Unit testing, integration testing, system testing, user acceptance testing |
| **Operation and Maintenance** | Identify best practices for system operations and support |

### Strengths of Structured Methodologies

- Tends to generate well-organized systems
- Step-by-step approach parallel to SDLC
- Tools and techniques can support other methodologies
- Simplifies project, risk, and resource management

### Weaknesses of Structured Methodologies

- Rigid phases, discourage skipping steps
- Requirements must be defined at beginning, not encouraged to change
- Cost and time unpredictable for large projects
- Emphasize process and product quality rather than customer satisfaction
- Too much "red-tape", wasting time and resources

---

## 3. Agile Methodologies

### Overview

Agile methodologies are modern IS methodologies developed in the mid 80's to 90's that:
- Focus on fast delivery of software and customer satisfaction
- Have flexible stages
- Share Agile Principles defined in 'The Agile Manifesto' (2001)

### The Agile Manifesto - Four Values

| Value | Description |
|-------|-------------|
| **Individuals and Interactions** | Over processes and tools |
| **Working Software** | Over comprehensive documentation |
| **Customer Collaboration** | Over contract negotiation |
| **Responding to Change** | Over following a plan |

### Twelve Agile Principles

| # | Principle | Description |
|---|-----------|-------------|
| 1 | Customer Satisfaction | Early and continuous delivery of valuable software |
| 2 | Welcome Changing Requirements | Even in late development |
| 3 | Working Software Delivered Frequently | Weeks rather than months |
| 4 | Close Daily Cooperation | Between business-people and developers |
| 5 | Motivated Individuals | Projects built around trusted, motivated individuals |
| 6 | Face-to-Face Conversation | Best form of communication (co-location) |
| 7 | Working Software | Principal measure of progress |
| 8 | Sustainable Development | Able to maintain constant pace |
| 9 | Technical Excellence | Continuous attention to good design |
| 10 | Simplicity | Art of maximizing work not done |
| 11 | Self-Organizing Teams | Best architectures, requirements, designs emerge |
| 12 | Regular Reflection | Team reflects on effectiveness and adjusts |

### Popular Agile Methodologies

| Methodology | Description | Best For |
|-------------|-------------|----------|
| **Scrum** | Team-work based methodology with sprints, product backlog, daily standups | Most agile projects |
| **Extreme Programming (XP)** | Heavy coding approach with pair programming, test-driven development | Advance/heavy coding projects |
| **Rapid Application Development (RAD)** | Small and fast projects with prototyping | Small and fast projects |
| **DSDM** | Improvement on RAD, focus on rapid prototyping based on users' feedback | Projects requiring rapid development |
| **Feature Driven Development (FDD)** | Long-term projects that frequently change and add features | Long-term iterative projects |
| **Lean** | Focuses on identifying and eliminating waste, improving quality | Continuous improvement projects |
| **Kanban** | Visualizing workload and development progress | Teams needing visual workflow |

### Advantages of Agile Methodologies

- Customer satisfaction with frequent delivery of working product
- Gives customers/users 'power' to change minds anytime and send new requirements
- Gives more 'control' to core developers to make decisions
- Emphasize use of latest design and technologies
- Encourage close communication and teamwork

### Disadvantages of Agile Methodologies

- Users/customers not available at all times
- Developer difficult to determine final cost and development time as requirements keep changing
- Developer difficult to plan and deliver workable products frequently
- Expert developers and CASE Tools are expensive
- Often lack comprehensive documentation

---

## 4. Process Oriented Methodologies

### Overview

Process-oriented methodologies can be applied to complex and distributed business processes where:
- Business process is converted into functions in a system
- Processes and tasks are broken down into smallest workable components
- Each sub-process can be assigned time, cost, and resources

### Key Methodologies

| Methodology | Description | Characteristics |
|-------------|-------------|-----------------|
| **RAD** | Rapid Application Development | 'Fast' methodology for fast/urgent projects, completed within days/weeks |
| **RUP** | Rational Unified Process | "Plan a little, design a little, and code a little", extensive use of UML |
| **Scrum** | Team-work based methodology | Time-controlled mini-projects (sprints), daily standup meetings |
| **XP** | Extreme Programming | Very flexible methodology for heavy coding projects |
| **Spiral** | Risk-driven process model | For high-risk projects with unclear/unfixed requirements |

### RAD (Rapid Application Development)

#### Phases
| Phase | Description |
|-------|-------------|
| **Analysis & Quick Design** | Users, managers, and IT staff discuss business needs, project scope, constraints, and system requirements |
| **Prototype Cycles** | Develop, demonstrate, and refine prototypes based on user feedback |
| **Testing** | Test software product and ensure all parts work together |
| **Deployment** | Data conversion, user acceptance testing, changeover, user training |

#### Techniques
- Expert developers used
- Uses CASE tools for faster development and testing
- Uses minimal planning, analysis, and documentation
- Uses prototype for user feedback and review
- Users involved in development
- Iterative and incremental design approach with prototyping

#### Advantages
- Systems can be developed more quickly with significant cost savings
- Cut development time and expense by involving users in every phase
- Continuous process allows development team to make modifications quickly

#### Disadvantages
- Stresses mechanics of system, does not emphasize company's strategic business needs
- System might work well short-term but long-term objectives might not be met
- Accelerated time cycle might allow less time for quality, consistency, and design standards

### RUP (Rational Unified Process)

#### Life Cycle Phases
| Phase | Description |
|-------|-------------|
| **Inception** | Basic idea and structure of project determined |
| **Elaboration** | Analyze requirements and necessary architecture |
| **Construction** | Coding and implementation |
| **Transition** | Final release, delivery to customers, post-release support |

#### Disciplines
- Business modelling
- Requirements
- Design
- Implementation
- Testing
- Deployment
- Configuration and change management
- Project management
- Environment

#### Practices
- Focuses early and often on users
- Use case driven
- Model driven – uses UML exclusively
- Iterative, but provides management structure by defining phases
- Focuses on defining an architecture
- Adaptable to needs of specific project

### Scrum

#### Organization Roles
| Role | Responsibility |
|------|---------------|
| **Product Owner** | Client stakeholder responsible for business requirements, project backlog, and priorities |
| **Scrum Master** | Person in charge of Scrum project, similar to project manager |
| **Scrum Team** | Team of 5-9 people from mixed skills, sets own goals, organizes self, makes decisions |

#### Practices
- **Sprint**: Time-controlled mini-project (30-day time box) with specific goal or deliverable
- **Daily Scrum**: Daily meeting (15 minutes max) to report progress
- **Sprint Review**: Scheduled to review and identify changes needed for following sprints

#### Ceremonies
| Ceremony | Description |
|----------|-------------|
| **Sprint Planning** | Team meets and decides what to complete in coming sprint |
| **Daily Scrum** | Standup meeting to ensure transparency across team |
| **Sprint Review** | Team demos what they shipped in sprint |
| **Sprint Retrospective** | Team reviews work, identifying what went well and what didn't |

### XP (Extreme Programming)

#### Core Values
| Value | Description |
|-------|-------------|
| **Communication** | Lack of open communication is major cause of project failure |
| **Simplicity** | Keep things simple to make it standard way of developing systems |
| **Feedback** | Frequent, meaningful feedback is recognized as best practice |
| **Courage** | Developers need courage to face harsh choices |

#### Practices
- **Planning**: Make rough plan quickly and refine as things become clearer
- **Testing**: Tests for each use case written first before solution programmed
- **Pair Programming**: Two programmers work together on designing, coding, and testing
- **Simple Designs**: Accomplish desired result with few classes and methods
- **Refactoring**: Improve code without changing what it does
- **Collective Ownership**: Everyone is responsible for code, anyone can modify any piece
- **Continuous Integration**: Small pieces integrated into system daily or more often
- **On-Site Customer**: Continual involvement of users who make business decisions
- **System Metaphor**: Easily understood and well known to development team
- **Small Releases**: Frequent releases to keep users involved
- **Forty-Hour Week**: Project shouldn't be death march that burns out team
- **Coding Standards**: Follow standards for coding and documentation

### Spiral Methods

#### Characteristics
- "Risk-driven" process model
- Next steps determined based on 'Risk' pattern
- For projects with high risk: unclear/unfixed requirements, too many independent components, too many stakeholders

#### Phases
| Phase | Description |
|-------|-------------|
| **Planning Phase** | Define objectives, constraints, and deliverables |
| **Risk Analysis** | Identify risks and develop acceptably resolutions |
| **Engineering Phase** | Develop prototype with all deliverables and perform integration |
| **Evaluation Phase** | Various functional testing, deploy system at user's site and perform assessment |

### Strengths of Process Oriented Methodologies

- Attempt to develop system incrementally by building series of prototypes
- Each iteration has deliverable
- Users get involved in testing system's ability to meet business needs
- Testing and quality control spread across entire project
- Provides better-tested and more robust system
- Speeds up system development and delivers precisely what customer wants
- Fosters teamwork and empowers employees

### Weaknesses of Process Oriented Methodologies

- Project scope isn't well understood
- Many changes, updates, and refinements to requirements as project progresses
- Without detailed system requirements, certain features might not be consistent with company's larger game plan
- Include weak documentation, blurred lines of accountability
- Too little emphasis on larger business picture
- Long series of iterations might add to project cost and development time
- May not work as well for larger projects due to complexity

---

## 5. Socio-Technical Methodologies

### Overview

Socio-technical methodologies are used when:
- Requirements are not fixed/cannot be fully determined earlier
- Requirements and scenarios are constantly changing
- Structured methodologies might not be suitable
- System involves gaming, robotics, virtual reality, augmented reality, medicine, animal behaviors, etc.

### Methodologies vs Frameworks

| Type | Description | Examples |
|------|-------------|----------|
| **Methodologies** | Comprehensive, prescriptive set of principles, processes, roles, and deliverables that guide entire SDLC. Defines techniques and tools | Waterfall, Scrum, DSDM |
| **Frameworks** | Set of guiding practices, philosophies, or tools that influence how to approach specific aspects of system design | Human-Centred Design (HCD), Design Thinking, Participatory Design |

### Soft Systems Methodology (SSM)

An organized way of tackling messy situations in the real world, particularly useful in:
- Business process modeling
- Organizational change management
- Human-centric systems

#### Development Path
1. Problem situation considered problematic
2. Problem situation expressed
3. Root definition of relevant purposeful activity systems
4. Conceptual models of the systems named in root definitions
5. Comparison of models and real world
6. Changes: systemically desirable, culturally feasible
7. Action to improve the problem situation

#### CATWOE Concept
| Element | Description |
|---------|-------------|
| **C**ustomers | Those who are direct victims or beneficiaries of the system |
| **A**ctors | Key people involved in implementation of changes |
| **T**ransformation | Fundamental concept of converting input into output |
| **W**orld-View | Big picture of situation, highlights problems |
| **O**wner | Person, system, or agency with power to direct and abolish system |
| **E**nvironment | Restrictions that may halt operating the system |

### Socio-Technical Development Areas

| Area | Example | Considerations |
|------|---------|----------------|
| **Healthcare & Digital Health** | EPIC EHR systems | Balance usability, privacy, safety, workflow |
| **Smart Cities & Urban Infrastructure** | Singapore's Smart Nation program | Sustainability, inclusivity, trust |
| **Cybersecurity & Privacy Systems** | Bank phishing defense | Tech + training + culture |
| **Education Technology (EdTech)** | Moodle/Canvas LMS | Align with pedagogy, motivation, accessibility |
| **Workplace & Collaboration Systems** | SAP ERP implementation | Workflows, teamwork, resistance to change |
| **E-Governance & Digital Public Services** | Estonia e-Government | Security, accessibility, trust |
| **Transportation & Autonomous Systems** | Tesla Autopilot | Accountability & safety |
| **Sustainability & Environmental Systems** | Smart meters | Behavior + tech + policy integration |
| **Financial & FinTech Systems** | M-Pesa/GrabPay | Trust, transparency, compliance |
| **Defense & Safety-Critical Systems** | Air traffic control | Human + machine integration |

### General Strategies

1. Developers study user behaviors of a system in real-world
2. Capture user's behavior into 'tasks' in virtual world
3. Connect/link several tasks to become complete process
4. Build IS to satisfy process in real-world
5. Continually update IS system with new and improved tasks (continuous development)

---

## 6. System Planning

### Overview

System Planning Strategies is the process of:
- Identifying long-term organizational goals, strategies, and resources
- First phase of SDLC
- Examining purpose, vision, values and developing mission statement
- Reviewing business case (basis/reason for proposed system)

### Feasibility Study

Conducted by potential developer to assess if project can be done according to owner's requirements.

| Type | Description | Key Questions |
|------|-------------|---------------|
| **Operational Feasibility** | System will be used effectively after development | Does management support project? Do users support project? Will new system result in workforce reduction? Will new system require training? |
| **Technical Feasibility** | Technical resources needed to develop, purchase, install, or operate system | Does company have necessary hardware, software, network resources? Does company have needed technical expertise? Will proposed platform have sufficient capacity? |
| **Economic Feasibility** | Projected benefits outweigh estimated costs (Total Cost of Ownership - TCO) | Tangible benefits (measurable in dollars), Intangible benefits (important but hard to measure) |
| **Schedule Feasibility** | Project can be implemented in acceptable time frame | Can company control factors affecting schedule feasibility? Has management established firm timetable? Will accelerated schedule pose risks? |
| **Legal Feasibility** | No conflicts with legal requirements | Zoning laws, data protection, privacy issues |
| **Cultural Feasibility** | Organizational structure, management competency, professional skills | Cultural fit with organization |

### Resource Planning Tools

| Tool | Description | Purpose |
|------|-------------|---------|
| **Gantt Chart** | Horizontal bar chart representing tasks with time on horizontal axis | Simplify complex project by combining several activities into task group |
| **PERT Chart** | Program Evaluation Review Technique - analyzes complex project as series of individual tasks | Analyze large, complex projects, estimate task duration |
| **Work Breakdown Structure (WBS)** | Breaking project down into series of smaller tasks | For project activities and human resources planning |
| **Hierarchy Task Analysis** | For task restructuring | Task restructuring |

### Outsourcing Options

| Type | Description | Example |
|------|-------------|---------|
| **Application Service Provider (ASP)** | Firm that delivers software application by charging usage or subscription fee | Databases, accounting packages |
| **Internet Business Services (IBS)** | Powerful Web-based support for transactions | Order processing, billing, customer relationship management |

#### Reasons for Outsourcing
- Companies don't have expertise to handle task
- Companies want to concentrate on main business
- Transfer risk – vendors absorb risks and provide warranty
- Cost Saving – off-shore outsourcing often cheaper

#### Problems with Outsourcing
- Outsourcing to experts could be expensive
- Security risk – outsourcing critical systems
- Loss of control – Owner doesn't own system entirely

### Requirement Engineering (RE)

Requirement Engineering is process of gathering, analyzing, and finalizing requirements for project.

#### Main Activities
| Activity | Description |
|----------|-------------|
| **Requirement Elicitation** | Collect data about old system and new system to be built |
| **Requirement Compilation** | Gathering/merging collected data into one location |
| **Requirement Validation and Analysis** | Narrowing/filtering, keeping only important and achievable requirements |

#### Techniques
| Technique | Description |
|-----------|-------------|
| **Interviews** | Planned meeting to obtain information from another person |
| **Questionnaires/Survey** | Document containing standard questions sent to many individuals |
| **Research** | Internet, IT magazines, books, professional meetings, site visits |
| **Observation** | Gives additional perspective and better understanding of system procedures |
| **Document Review** | Understand how current system is supposed to work |
| **Sampling** | Selecting subset of data for analysis (systematic, stratified, random) |

#### Question Types
| Type | Description | Example |
|------|-------------|---------|
| **Open-ended** | Encourage spontaneous and unstructured responses | "What are users saying about the new system?" |
| **Closed-ended** | Limit or restrict response | "How many personal computers do you have?" |
| **Range-of-response** | Evaluate something on numeric scale | "Rate effectiveness from 1 to 10" |

### Project Risk Management

#### Steps
1. Identify the risks
2. Develop a risk management plan
3. Analyze the risks (qualitative and quantitative)
4. Create a risk response plan
5. Monitor risks

#### Risk Management Strategies
| Strategy | Description |
|----------|-------------|
| **Risk Transfers** | Transferring risk to vendor or customer |
| **Risk Avoidance** | Take alternative path to avoid risk from happening |
| **Risk Reduction** | Take additional steps to reduce risk from occurring |
| **Risk Acceptance** | Implement total solution as risk will happen |

---

## 7. System Analysis

### Overview

System analysis is a problem-solving technique that:
- Decomposes system into component pieces
- Involves data gathering, data analysis, creating specification
- Inspects, cleans, transforms, and models data to discover useful information

### Data Analysis Process

| Step | Description |
|------|-------------|
| 1. Collect and Store Data | Collect and merge data from different sources |
| 2. Clean Data | Remove errors, invalid data, redundancy, empty/incomplete data |
| 3. Analyze Data | Look for relations and patterns within/between data |
| 4. Create Output Information | Present data in tabular, graphical, chart format |
| 5. Conclusion | Result of analysis, helps create SRS |

### Systems Analysis Activities

| Activity | Description |
|----------|-------------|
| **Gather Detailed Information** | Interviews, questionnaires, documents, observing business processes, researching vendors |
| **Define Requirements** | Model functional requirements, non-functional requirements |
| **Prioritize Requirements** | Essential, important, vs. nice to have |
| **Develop User-Interface Dialogs** | Flow of interaction between user and system |
| **Evaluate Requirements with Users** | User involvement, feedback, adapt to changes |

### System Requirements

| Requirement Type | Description | Examples |
|------------------|-------------|----------|
| **Functional Requirements** | Activities system must perform (use cases) | Send email when order placed, apply discount for orders above RM100 |
| **Non-Functional Requirements** | Technical environment or performance objectives | Usability, reliability, security, performance |
| **Technical Requirements** | Hardware/software/environment requirements | Windows Server 2010, minimum 4GB RAM |
| **Performance Requirements** | Operational characteristics related to workload | 0.5 second response time, support 100 simultaneous sessions |
| **Usability Requirements** | Operational characteristics related to users | Behave similarly to other apps, multilanguage support |
| **Reliability Requirements** | Dependability of system - service outages and recovery | Failure rate, recovery methods |
| **Security Requirements** | Access control and data protection | Password protected, encrypt data with 1024-bit keys |
| **Interface Requirements** | Interactions among systems | Generate data in specific XML format for SEC |
| **User Requirements** | Special requirements from users for personal benefits | Print profiles, customize background |
| **Business Requirements** | Requirements for benefit of company's business | Support business growth for next five years |

### FURPS+ Model

| Category | Description | Example |
|----------|-------------|---------|
| **F**unctional | Functions, business rules and processes | System calculates totals |
| **U**sability | User interface, ease of use | User-friendly forms |
| **R**eliability | Failure rate, recovery methods | 99.9% uptime |
| **P**erformance | Response time, throughput | <2 second response |
| **S**ecurity | Access controls, encryption | Password protection |
| **+ Design Constraints** | Hardware & support software | Must use specific database |
| **+ Implementation** | Development tools, protocols | Use Java, Spring Boot |
| **+ Interface** | Data interchange formats | JSON, XML |
| **+ Physical** | Size, weight, power consumption | Fit in specific server rack |
| **+ Support** | Installation & updates | Easy upgrade process |

### Stakeholders

| Stakeholder Type | Description | Examples |
|------------------|-------------|----------|
| **Internal Stakeholders** | Within organization who interact with system | Employees, volunteers, students |
| **External Stakeholders** | Outside organization's control | Customers, suppliers, regulators |
| **Operational Stakeholders** | Regularly interact with system | Accountants, factory supervisors, customers |
| **Executive Stakeholders** | Don't interact directly but use information | Senior managers, board of directors |
| **Client** | Provides funding for project | Senior management, board of directors |
| **Technical and Support Staff** | Establish and maintain computing environment | IT staff, support staff |

### System Analysis Techniques

| Technique | Description | Tools |
|-----------|-------------|-------|
| **Financial Analysis** | Payback analysis, ROI, NPV | Financial calculators, spreadsheets |
| **Risk Analysis** | Identify risks and develop resolutions | Risk registers, probability matrices |
| **Business Intelligence Analysis** | Find benefits of data to business | SWOT, Fishbone, PEST analysis |
| **Data Mining** | Digging through large data to find relevant information | Statistical software, machine learning tools |
| **Statistical Analysis** | Use numeric data to find/predict data relationships | Statistical software (R, SPSS, Python) |

#### Data Mining Techniques
| Technique | Description | Example |
|-----------|-------------|---------|
| **Aggregation** | Get information about specific groups based on variables | Car class containing engine, seat, wheels classes |
| **Regression** | Identify likelihood of variable given presence of others | Project price based on availability, demand |
| **Association** | Track patterns, specific events highly correlated | Customers buying item also buy related item |
| **Clustering** | Group chunks of data based on similarities | Cluster demographics by income, shopping frequency |
| **Prediction** | Recognize historical trends to predict future | Credit risk prediction from purchase history |

### System Analysis Benefits

- Knowledge discovery
- Verify assumptions with real facts
- Problem's source/cause discovery
- Obtain proof to support theory
- Filter and keep only important/relevant data
- See relationship between facts and figures
- View data in different way to obtain ideas

### System Analysis Setbacks

- Insufficient data collected
- Difficult to use analysis tools
- Unreliable and invalid data
- Incorrect analysis methods used
- Lack of scope/objective of output
- Biased inference
- Analyst (architect) lack analysis skills
- External issues/hindrance

---

## 8. System Design

### Overview

System Design is process of defining architecture, components, modules, interfaces, and data for system to satisfy specified requirements.

**Input**: System Specification (including SRS)
**Output**: System Design Specification

### Design Areas

| Area | Description |
|------|-------------|
| **Hi-level Design** | System Architecture - Hardware, Software, Network |
| **Software Design** | Software Architecture - Conceptual, Logical, Physical Design |

### System Design Objectives

- Creating solution to problem in hand
- Breakdown and understand complex concepts and process
- Create product safe and secure for use (HCI)
- Add vital details to product
- Come-up with efficient and effective product/solution
- Ensure product comply with set specifications and standards
- Implement modern technology into product
- Test product early and avoid costly rework

### System Architecture

High-level view of system where developer needs to determine:
- Types of users
- Environment (Different 'views' of system)
- Behavior of system
- Availability of technology
- Platform
- Laws and Legislations
- Industry Standards and Protocols
- Security
- Network and connectivity
- Maintenance

### Design Levels

| Level | Description | Examples |
|-------|-------------|----------|
| **Conceptual Design** | Understanding and presenting concept to non-IT people | Context Diagram, Use Case Diagram, Sequence Diagram, Flow Chart, Story Board, Rich Picture |
| **Logical Design** | Abstract of system, usually in diagrams (models) | Data Flow Diagram, Activity Diagram, Entity Relations Diagram, UML Class Diagrams |
| **Physical Design** | Enhanced presentation, usually graphical | Prototype, Simulation, Animation, Video |

### Good Design Practices

- Design process should not suffer from "tunnel vision"
- Good designer should consider alternative approaches
- Design should be traceable to analysis model
- Design should not reinvent the wheel
- Design should be structured to accommodate change
- Design should be assessed for quality

### Design Influence

| Type | Description | Example |
|------|-------------|---------|
| **Process Centered Design** | Designing based on automation of process | Ticketing Machine, Manufacturing process, Hotel booking |
| **Data Centered Design** | Designing based on processing large data | Big Data, Shopping, Immigration system |
| **User Centered Design** | Designing based on human behavior | AI, games, social sites, navigation applications |

### UML (Unified Modeling Language)

Modeling techniques to visualize design of system, supports Object Oriented development.

| View | Description | Diagrams |
|------|-------------|---------|
| **Static/Structural View** | Emphasizes static structure using objects, attributes, operations | Class and composite structure diagrams |
| **Dynamic/Behavioral View** | Emphasizes dynamic behavior showing collaborations | Sequence diagrams, activity diagrams, state machine diagrams |

### Prototyping

Process of creating model (prototype) of system.

| Dimension | Description | Purpose |
|-----------|-------------|---------|
| **Horizontal Prototype** | Broad view of entire system, focusing on user interaction | Demonstration to users, estimating project |
| **Vertical Prototype** | Elaborates single subsystem or function | Study and testing, refine database design |

| Type | Description | Usage |
|------|-------------|-------|
| **Throw-away Prototype** | Basic form for demonstration purpose, 'dummy' representation | Quick demonstration |
| **Evolutionary Prototype** | Product built in stages, becomes final product | Development with changing requirements |
| **Incremental Prototype** | Several prototypes merged and refined to become final product | Complex systems |
| **Extreme Prototype** | Web development, delivered in fully functional scale by stages | Web development |

### HCI (Human Computer Interaction)

Concepts of creating software which are safe and pleasant to use, concerns mostly on interface design.

**Things to consider:**
- Users abilities/disabilities
- User's age group (interest, legal contents)
- User's computer literacy (Novice, Intermediate, Expert)
- User's Socio-culture (perception of color, language, religious sensitivity)
- Purpose of Software (Command line, GUI, Interactive, 3D)

---

## 9. System Implementation

### Overview

System Implementation (Construction and Testing) is process of building system through programming language.

**When**: Design of system is approved, Design Specification is available
**Deliverable**: Fully working software/system

### Coding Strategies - Things to Consider

| Factor | Description |
|--------|-------------|
| **Software Architecture/Platform** | Types of platform to build/supported by application |
| **Choice Programming Language(s)** | Most flexible/compatible language based on requirements |
| **Programming/Coding Standards** | Check compliance with standards (IEEE, Open Source) |
| **Types of Testing** | Type of testing necessary for pre and post product deployment |
| **User Involvement** | Degree of user involvement, availability, expertise |
| **Code Repository** | Where to store codes, secure and sharable to other developers |
| **Version Control** | Control of modifications made on codes, backup and restore |
| **Security and Copyright** | Level of security, artifacts to be patented/copyrighted |

### Good Programming Practice

| Practice | Description |
|----------|-------------|
| **Efficiency** | Keep it Short and Simple (KISS) |
| **Portability** | Use good variables and no hard codes |
| **Security** | Source Codes, Encapsulation |
| **Readable Codes** | Meaningful and informative names, comments, formats |
| **Refactoring** | Improve code without changing what it does |

### Software Testing

Process of executing program with intent of finding software bugs. Validates and verifies that software meets business and technical requirements.

#### Testing Objectives
- Finding defects/bugs
- Prevent defects (avoid expensive recovery)
- Improving level of quality (code and product)
- Make sure end result meets business and user requirements

#### Testing Approach

| Approach | Description | When |
|----------|-------------|------|
| **Static Testing** | Test and find defects without executing code, verify requirements | During verification process |
| **Dynamic Testing** | Software code executed, satisfy customers | During validation process |

#### Common Testing Terms

| Term | Description | Who Performs |
|------|-------------|--------------|
| **White Box Testing** | All INPUT, PROCESS (code functions) and OUTPUT is seen | Programmer |
| **Black Box Testing** | Only INPUT and OUTPUT is seen, PROCESS hidden | User/Customer |
| **Stub Testing** | Testing just one line of execution to check presence of data | Programmer |

#### Testing Levels

| Level | Description | Type |
|-------|-------------|------|
| **Unit Testing** | Tests functionality of specific section of code at function level | White-box |
| **Integration Testing** | Verify interfaces between components against software design | Black-box |
| **Component Interface Testing** | Check handling of data passed between various units | Black-box |
| **System Testing** | Tests completely integrated system to verify it meets requirements | Black-box |

#### Popular Testing Types

| Type | Description |
|------|-------------|
| **Installation Testing** | Assures system is installed correctly |
| **Compatibility Testing** | Compatibility with other application software, operating systems |
| **Smoke And Sanity Testing** | Determines whether reasonable to proceed with further testing |
| **Regression Testing** | Focuses on finding defects after major code change |
| **Acceptance Testing** | Performed by customer for approval and feedback |
| **Alpha Testing** | Simulated or actual operational testing by potential selected/internal users |
| **Beta Testing** | After alpha testing, external user acceptance testing |
| **Destructive/Robust Testing** | Test software durability and tolerance |
| **Security Testing** | For software processing confidential data to prevent intrusion |

#### Types of Testing Tools

| Tool Type | Description | Examples |
|-----------|-------------|----------|
| **Program Monitors** | Permitting full or partial monitoring of program code | Instruction set simulator, Hypervisor, Program animation |
| **Formatted Dump/Symbolic Debugging** | Tools allowing inspection of program variables on error | Debuggers |
| **Automated Functional GUI** | Testing tools used to repeat system-level tests through GUI | Selenium, Cypress |
| **Benchmarks Tools** | Allowing run-time performance comparisons | Performance testing tools |
| **Performance Analysis/Profiling Tools** | Highlight hot spots and resource usage | Profiling tools |

---

## 10. System Deployment

### Overview

System Deployment makes software system available for use when system is ready to be delivered to owner/customer.

**Status**: System fully tested and fully functional

### System Deployment Plan

| Activity | Description |
|----------|-------------|
| **Determining Deployment Options** | Where will system/software be delivered? |
| **Packaging Software/Systems** | What and how components will be delivered to users? |
| **Deployment Scheduling** | Inform stakeholders of deployment event, who and when? |
| **System Change-over Strategies** | How will old system be replaced with new? |
| **Integrating System Components** | Installing equipment, connecting servers |
| **Post-Deployment (On-Site) Testing** | Running tests to spot new problems after deployment |
| **Provide Training to Users** | Training administrators, end-users, technical support |

### Determining Deployment Options

| Option | Description | Example |
|--------|-------------|---------|
| **Upload to Web Server/Web Host** | Website/web applications, software patches/plug-ins | Website hosting |
| **Upload to Web Store** | Mobile applications, games | App Store, Google Play |
| **Create Digital Medium - DVD** | Off-shelf applications, console games | Software distribution |
| **Install in Customer's Local Servers** | Customized Business Systems/applications, security systems, database | Enterprise software |

### Packaging Software/Systems

Operations to prepare system for assembly and transfer to customer site:
- Converting/securing source codes
- Preparing SETUP or INSTALL files
- Compress files
- Burn to installation disks OR prepare to upload to server
- Prepare User Manual
- Prepare Technical Manual

### System Change-over Strategies

| Strategy | Description |
|----------|-------------|
| **Direct Changeover** | Old system stopped, new system started immediately |
| **Parallel Changeover** | Old and new systems run simultaneously for period |
| **Pilot Changeover** | New system implemented in one location/department first |
| **Phased Changeover** | New system implemented in phases/stages |

### Integrating System Components

- Connecting sub systems to main systems
- Connecting database
- Connecting new system to other local system (legacy systems)
- Installing security components (Firewall, User profiles)

### Post-Deployment (On-Site) Testing

Running test to spot new problems after deployment:
- **Develop Test**: Technical Tests, Connections Tests, Security Tests
- **User Test**: User Acceptance Test

### User Training

Applicable for large/complicated systems:
- **Training Administrators**: Content Management, Maintenance of system
- **Training End-Users**: Common User functions
- **Training Technical Support**: Fixing common problems

### Other Activities

- **License Activation**: EULA (End User License Agreement), Corporate License
- **Connecting to Backup Machines**: Disaster Recovery Centre (DR)

---

## Summary of Key Concepts

### System Development Lifecycle (SDLC)

```
Planning → Analysis → Design → Implementation → Maintenance
```

### Methodology Comparison

| Aspect | Structured | Agile | Process-Oriented | Socio-Technical |
|--------|-----------|-------|-----------------|-----------------|
| **Focus** | Documentation, quality | Customer satisfaction, speed | Process, team collaboration | People, values, context |
| **Flexibility** | Low | High | Medium-High | Very High |
| **Requirements** | Fixed at start | Can change anytime | Can change in iterations | Evolving, uncertain |
| **Best For** | Clear requirements, critical systems | Fast-changing environments | Team-based projects | Complex human systems |
| **Examples** | Waterfall, SSADM, V-Model | Scrum, XP, Kanban | RAD, RUP, Spiral | SSM, HCD, Design Thinking |

### Testing Pyramid

```
           /\
          /  \
         / UI \         - User Acceptance Testing
        /------\
       /Integration\   - Integration Testing
      /------------\
     /   Unit      \  - Unit Testing
    /______________\
```

### Key Takeaways

1. **Information Systems** have five key components: Hardware, Software, People, Data, Processes
2. **SDLC** provides framework for all IS development methodologies
3. **Structured Methodologies** are rigid, document-heavy, suitable for well-defined projects
4. **Agile Methodologies** prioritize flexibility, customer satisfaction, and working software
5. **Process-Oriented Methodologies** focus on team collaboration and iterative development
6. **Socio-Technical Methodologies** emphasize human factors and values in system design
7. **System Planning** involves feasibility studies, resource planning, and requirement engineering
8. **System Analysis** focuses on understanding and documenting system requirements
9. **System Design** creates architecture, components, and interfaces for the system
10. **System Implementation** involves coding, testing, and quality assurance
11. **System Deployment** makes system available to users with appropriate changeover strategies

---

## References

- Satzinger, J. W., Jackson, R. B., & Burd, S. D. (2015). Systems Analysis and Design in A Changing World. Cengage learning.
- Shelly, G. B., & Rosenblatt, H. J. (2012). Systems Analysis and Design. Boston, MA: Course Technology.
- Whitten, J. L., Bentley, L. D., & Dittman, K. C. (2005). Systems Analysis and Design Methods (7th Ed.). McGraw-Hill/Irwin.
- Martin, R. C., Newkirk, J., & Koss, R. S. (2003). Agile Software Development: Principles, Patterns, and Practices (Vol. 2). Upper Saddle River, NJ: Prentice Hall.
- Milton, N. R. (2007). Knowledge acquisition in practice: a step-by-step guide. Springer Science and Business Media.
- Davies, L., & Ledington, P. (1991). Information in action: Soft systems methodology. Macmillan International Higher Education.

---

*End of Comprehensive Notes*