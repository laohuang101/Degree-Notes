# SDM Exam Tips

## Data Analysis Process

### Process Steps
1. **Collect Data** - Gather relevant information from various sources
2. **Setup Data Repository** - Organize data in tables to ensure uniform format
3. **Clean Data** (5 steps):
   - Remove invalid data
   - Remove duplicate data
   - Remove erroneous data
   - Remove incomplete data
   - Remove unverifiable data
   - Correct data format inconsistencies
4. **Analyze Data** - Review data to determine what to keep/remove (sort by priority, cost, etc.)
5. **Create Output and Conclusion** - Generate final reports and findings

### Example
**Scenario:** A retail company wants to analyze customer purchase behavior.

| Step | Action |
|------|--------|
| Collect | Gather sales data from POS systems, online platforms, and customer surveys |
| Setup | Import all data into a unified database with standardized columns |
| Clean | Remove duplicate entries, fix date format errors, delete incomplete transactions |
| Analyze | Sort customers by purchase frequency, average order value, and product categories |
| Output | Generate reports showing top customer segments, popular products, and seasonal trends |

---

## System Requirements Specification (SRS)

### Types of Requirements

| Requirement Type | Description | Examples |
|------------------|-------------|----------|
| **Functional** | What the system must do | User authentication, data processing, report generation |
| **Non-Functional** | How the system performs | Response time, security, scalability, reliability |

### Key Points
- **Outsourcing** is a common exam topic
- SRS documents stakeholder contributions and requirements
- Critical for project success and vendor agreements

---

## Outsourcing

### Definition
The use of external service providers to effectively deliver IT-enabled business processes.

### Reasons to Outsource

| Reason | Explanation |
|--------|-------------|
| **No Time** | Internal team lacks time to complete the project |
| **No Knowledge/Skills** | Team lacks required technical expertise |
| **Cost Efficiency** | Cheaper than purchasing all necessary software and hardware |
| **Non-Core Business** | Task is not part of the company's core business |
| **Focus on Core Business** | Internal team can focus on strategic planning, system design, stakeholder communication, and quality control |
| **Resource Limitations** | Helps balance workload when internal teams are overburdened |

### Disadvantages of Outsourcing

| Disadvantage | Impact |
|--------------|--------|
| **Expensive** | Costs can increase due to change requests, contract revisions, rework, or additional coordination efforts |
| **Communication Barriers** | Language, cultural, and time zone differences can cause misunderstandings |
| **Security Risks** | Sharing system data, source code, or user information increases risk of data breaches or IP leakage |

---

## Risk Management

### Risk Management Process

#### 1. Risk Identification
- Identify potential risks
- Discuss with development team what could go wrong
- List each risk with a brief description

#### 2. Risk Analysis
- Analyze risks based on priority
- Classify as: High Risk, Medium Risk, Low Risk

#### 3. Risk Response Plan
- **Proactive effort** to anticipate risk
- Create an action plan to address risks
- **Mitigation Plan:** How to avoid the risk from happening
- **Contingency Plan:** How to overcome the risk if it occurs

### Risk Management Strategies

| Strategy | Description | Example |
|----------|-------------|---------|
| **Risk Transfer** | Transfer responsibility to customer or vendor | Include liability clauses in contracts |
| **Risk Avoidance** | Accept that risk may happen and take steps to avoid | Choose proven technologies over experimental ones |
| **Risk Reduction** | Accept risk will happen and take steps to reduce impact | Implement redundancy systems |
| **Risk Acceptance** | Acknowledge risks and prepare to handle them | Maintain budget reserves for unexpected issues |

---

## System Change Over Strategies

### Overview Comparison

| Strategy | Best For | System Size | Complexity | Downtime |
|----------|----------|-------------|------------|----------|
| **Direct Change Over** | Non-critical, small systems | Small | Low | High (brief) |
| **Parallel Operation** | Large, critical, complex systems | Large | High | None |
| **Pilot Operation** | New systems, manual to automated migration | Medium | Medium | Minimal |
| **Phased Operation** | Extremely large systems with independent units | Very Large | Very High | Minimal per phase |

### 1. Direct Change Over (Cut Over)

**When to use:**
- System is small (like mobile app)
- System is not critical

**Process:**
- Switch from old to new system in one operation
- Old system is immediately replaced

**Advantages:**
- Simple and cost-effective
- Clear transition point

**Disadvantages:**
- High risk if problems occur
- No fallback option

---

### 2. Parallel Operation

**When to use:**
- System is large, critical, and complex
- Installation takes several hours
- Many things could go wrong

**Process:**
- Announce a date range where both old and new systems are available
- Users can use both systems during transition period
- Collect user feedback
- Shut down old system only after confirming no problems

**Advantages:**
- Zero downtime
- Safe fallback to old system
- Real-world testing opportunity
- User feedback integration

**Disadvantages:**
- Higher cost (running two systems)
- More complex data synchronization
- Longer transition period

**Comparison with Agile:** Similar to rolling updates where both versions coexist briefly.

---

### 3. Pilot Operation

**When to use:**
- New systems that are completely different from old system
- Typically manual to automated transitions

**Process:**
- Install system branch by branch (department by department)
- Small group uses new system first
- Gradually expand to other branches
- Based on success, full deployment

**Advantages:**
- Controlled testing environment
- Learnings from pilot improve full rollout
- Lower risk than full deployment

**Disadvantages:**
- Longer overall transition
- Integration challenges between pilot and rest of system

**Comparison with Agile:** Similar to phased migration where deployment happens incrementally.

---

### 4. Phased Operation

**When to use:**
- Extremely large systems
- Can be divided into multiple functional units (sub-systems)
- Each unit can be independently installed

**Process:**
- Divide system into independent functional modules
- Install module by module, function by function
- Each phase tested before proceeding
- Too large to install all at once

**Advantages:**
- Manageable implementation
- Problems isolated to specific modules
- Resource-efficient (focus on one area at a time)

**Disadvantages:**
- Longest transition period
- Complex inter-module dependencies
- Users may work across old and new modules simultaneously

---

### Parallel vs. Phased Operation (10 Marks)

| Aspect | Parallel Operation | Phased Operation |
|--------|-------------------|------------------|
| **Approach** | Both old and new systems run simultaneously | System divided into modules, implemented one at a time |
| **Best For** | Large, critical systems where safety is paramount | Extremely large systems with independent sub-systems |
| **Downtime** | None during transition | Minimal per phase, but extended overall |
| **Risk Level** | Very Low (old system always available) | Low (issues isolated to specific modules) |
| **Cost** | High (running two systems) | Medium to High (longer implementation) |
| **Complexity** | High (data synchronization between systems) | Very High (module integration planning) |
| **User Experience** | Users can choose between systems during transition | Users gradually migrate to new system |
| **Fallback** | Immediate (switch back to old system) | Limited (rollback specific modules) |
| **Testing** | Real-world production testing on both systems | Each module tested before next phase |
| **Duration** | Short transition period (few weeks/months) | Long transition period (months/years) |

---

## Mirror Swapping for No Downtime Maintenance

### Blue-Green Deployments

**Concept:**
- Create a total duplicate of the main server (mirror)
- Mirror is not connected to production
- All updates/changes happen on the mirror server
- Once verified, swap traffic from main to mirror
- Results in zero downtime for users

**Advantages:**
- No production downtime during updates
- Immediate rollback capability (swap back)
- Safe testing environment
- Production-like testing before release

---

## Testing

### User Acceptance Testing (UAT)

**Purpose:**
- Verify system meets user requirements
- Final approval before project completion

**Critical Point:**
- If users are not happy, you won't get paid
- User satisfaction is the ultimate measure of success

---

## User Training

**Purpose:**
- Test everything users need to know
- Ensure users can effectively use the system

**Important Note:**
- Usually paid extra as a separate service
- Critical for system adoption and success

---

## Agile Development

### Sprint-Based Migration

**Concept:**
- Every sprint can be a small migration
- Similar to phase migration
- Incremental delivery of system changes

**Advantages:**
- Continuous improvement
- Regular user feedback
- Reduced risk with small changes
- Faster time to value

---

## Exam Tips Summary

1. **Outsourcing** is a high-probability topic - understand advantages and disadvantages
2. **Risk Management** - Know the process: Identify → Analyze → Response Plan
3. **System Change Over** - Memorize all 4 strategies and when to use each
4. **Parallel vs. Phased** - Common 10-mark comparison question
5. **Data Analysis** - Understand the 5 steps in data cleaning
6. **SRS** - Know difference between functional and non-functional requirements
7. **UAT** - Remember: unhappy users = no payment
8. **Blue-Green Deployment** - Zero downtime strategy with mirror servers
