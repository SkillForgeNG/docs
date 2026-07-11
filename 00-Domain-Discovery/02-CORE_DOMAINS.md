# SkillForge Core Domains

## Domain Overview

SkillForge is organized into seven primary business domains. Each domain has specific responsibilities, owns critical business concepts, and manages clear boundaries.

Using Domain-Driven Design principles, these domains should eventually become separate microservices with independent databases and clear APIs.

```
                        ┌─────────────────────┐
                        │   Administration    │
                        │   (System Control)  │
                        └─────────────────────┘
                                  │
        ┌─────────────┬───────────┼───────────┬─────────────┐
        ▼             ▼           ▼           ▼             ▼
    ┌────────┐   ┌────────┐  ┌────────┐  ┌────────┐   ┌────────┐
    │Learning│   │Skill & │  │Career  │  │Community│   │Analytics│
    │Domain  │   │Comp.   │  │Domain  │  │Domain  │   │Domain  │
    └────────┘   └────────┘  └────────┘  └────────┘   └────────┘
        │             │          │          │            │
        └─────────────┴──────────┴──────────┴────────────┘
                        ▼
            ┌─────────────────────────┐
            │    Identity & Access    │
            │   (Cross-cutting)       │
            └─────────────────────────┘
                        │
            ┌───────────┴───────────┐
            ▼                       ▼
        ┌────────────┐         ┌──────────┐
        │AI & Guidance   │    │Notification│
        │(Cross-cutting) │    │(Cross-cut.)│
        └────────────┘         └──────────┘
```

---

## 1. Learning Domain

### Purpose
Organize, curate, and deliver learning content in coherent paths leading to competency achievement.

### Responsibilities
- Define learning paths and their structure
- Organize courses, lessons, and resources
- Track learner progress through paths
- Manage prerequisites and dependencies
- Create and manage modules
- Organize resources (videos, articles, tutorials)
- Recommend next steps based on progress
- Provide learning recommendations

### Key Concepts
- **Learning Path** - Curated sequence toward competency
- **Course** - Collection of related learning modules
- **Module** - Unit of learning (~2-4 hours)
- **Lesson** - Sub-unit (~15-30 minutes)
- **Resource** - Individual learning material (external)
- **Curriculum** - Structured content within a path
- **Progress Tracking** - Learner advancement monitoring
- **Enrollment** - Learner joining a path

### Boundaries
- Owns learning path structure and content organization
- Does NOT own competency definitions (Skill Domain owns this)
- Does NOT own assessment/project evaluation (Career Domain)
- Does NOT own AI recommendations (separate cross-cutting concern)
- Does NOT manage user authentication (Identity Domain)

### Key Metrics
- Learning path completion rate
- Time to completion
- Resource quality ratings
- Enrollment numbers
- Learner satisfaction

### Related Domains
- **Skill Domain:** Uses competency definitions to organize paths
- **Career Domain:** Paths lead to competency achievement
- **Analytics Domain:** Measures learning effectiveness
- **Community Domain:** Peer learning within paths

---

## 2. Skill & Competency Domain

### Purpose
Define, organize, and govern the skills and competencies that SkillForge teaches and validates.

### Responsibilities
- Define individual skills and their components
- Create competency frameworks (role-based)
- Define mastery levels and progression
- Establish learning objectives for competencies
- Define required projects and assessments
- Set standards for skill validation
- Manage skill prerequisites and dependencies
- Track industry relevance and currency
- Create skill graph and knowledge trees

### Key Concepts
- **Skill** - Discrete, teachable ability (HTML, Git, Communication)
- **Competency** - Cluster of related skills (Frontend Developer)
- **Skill Level** - Progression (Beginner, Intermediate, Advanced, Expert)
- **Mastery** - Demonstrated ability to apply skill
- **Skill Graph** - Network of related skills and prerequisites
- **Competency Framework** - Definition of a role's competencies
- **Evidence of Mastery** - Requirements to prove skill (project, assessment)

### Boundaries
- Owns skill and competency definitions
- Owns skill graph and relationship mapping
- Does NOT own learning content (Learning Domain)
- Does NOT own project creation (Career Domain)
- Does NOT own assessment/grading (Career Domain)
- Does NOT own user profiles (Career Domain)

### Key Metrics
- Number of skills in system
- Skill graph completeness
- Industry alignment
- Competency framework adoption
- Skill mastery rates

### Related Domains
- **Learning Domain:** Organized by skills and competencies
- **Career Domain:** Competencies map to jobs
- **Analytics Domain:** Measures skill acquisition

---

## 3. Career Domain

### Purpose
Connect learning to career outcomes; help learners prove competency and find opportunity.

### Responsibilities
- Define career paths and job roles
- Create project requirements for skill proof
- Define and manage assessments
- Evaluate learner work against competencies
- Issue certificates and badges
- Track career outcomes and employment data
- Manage employer partnerships
- Connect learners with opportunities
- Create skill passports (professional profiles)
- Provide career guidance and planning

### Key Concepts
- **Career Path** - Sequence of related roles or competencies
- **Job Role** - Specific employment position
- **Project** - Hands-on work demonstrating competency
- **Assessment** - Evaluation of learner mastery
- **Certificate** - Recognition of competency achievement
- **Badge** - Micro-credential for specific skill
- **Portfolio** - Collection of learner's best work
- **Skill Passport** - Lifelong learner professional profile
- **Career Goal** - Desired role or opportunity
- **Employer Partnership** - Connection to job opportunities

### Boundaries
- Owns projects and assessments
- Owns certification and validation
- Owns career goal tracking and planning
- Does NOT own learning content (Learning Domain)
- Does NOT own skill definitions (Skill Domain)
- Does NOT own learner identity/authentication (Identity Domain)
- Does NOT own recommendation algorithms (AI Domain)

### Key Metrics
- Learners with portfolios
- Certificate issuance rate
- Project completion rate
- Assessment pass rate
- Employment outcomes
- Employer engagement
- Portfolio quality

### Related Domains
- **Skill Domain:** Competency proof requirements
- **Learning Domain:** Paths lead to career competency
- **Community Domain:** Peer feedback on projects
- **Analytics Domain:** Career outcome measurement

---

## 4. Community Domain

### Purpose
Enable peer learning, mentorship, and collaboration among learners, instructors, and industry professionals.

### Responsibilities
- Manage learner communities and study groups
- Enable peer-to-peer learning and support
- Facilitate peer review and feedback
- Manage instructor community and contributions
- Create discussion forums and collaboration spaces
- Recognize and reward community contributions
- Facilitate mentorship matching
- Foster inclusive, safe community culture
- Manage reputation and trust systems
- Enable knowledge sharing

### Key Concepts
- **Community** - Group organized around interest/goal
- **Study Group** - Small group learning together
- **Discussion Forum** - Topic-based conversation
- **Peer Review** - Learners evaluating peer work
- **Mentor Relationship** - Experienced advising learner
- **Contribution** - Community member adding value
- **Reputation** - Recognition of community standing
- **Code of Conduct** - Community norms and expectations
- **Collaboration** - Joint learning or project work

### Boundaries
- Owns community structure and management
- Owns peer interaction and feedback
- Owns contributor recognition
- Does NOT own identity/authentication (Identity Domain)
- Does NOT own project grading (Career Domain)
- Does NOT own content curation (Learning Domain)
- Does NOT own notifications (Notification Domain)

### Key Metrics
- Community member count
- Active discussion participation
- Peer review completion rate
- Mentor-mentee pairs
- Contribution quality and volume
- Community satisfaction
- Retention through community

### Related Domains
- **Career Domain:** Project feedback and peer review
- **Learning Domain:** Study groups, collaboration
- **Administration Domain:** Community moderation
- **Analytics Domain:** Community engagement metrics

---

## 5. Analytics Domain

### Purpose
Measure, analyze, and report on learner progress, platform health, and impact.

### Responsibilities
- Track learner progress and engagement
- Measure learning outcomes
- Analyze competency acquisition rates
- Report career outcomes and employment data
- Monitor platform health and performance
- Create dashboards and reports
- Identify at-risk learners
- Measure content effectiveness
- Track community metrics
- Provide data for decision-making

### Key Concepts
- **Progress Tracking** - Learner advancement through paths
- **Engagement Metrics** - Activity and participation levels
- **Learning Analytics** - Data on skill acquisition
- **Career Outcomes** - Employment and advancement data
- **Platform Metrics** - System health and performance
- **Effectiveness Analysis** - What content/methods work best
- **Cohort Analysis** - Patterns across learner groups
- **Dashboard** - Visual data presentation

### Boundaries
- Owns data aggregation and analysis
- Owns reporting and visualization
- Does NOT own personal data storage (Identity Domain)
- Does NOT own individual learner profiles (Career Domain)
- Does NOT own data collection (owned by each domain)
- Does NOT own algorithm development (AI Domain)
- Respects privacy and data protection rules

### Key Metrics
- Data accuracy and completeness
- Dashboard usage
- Report relevance
- Decision-making impact
- Analytics timeliness

### Related Domains
- All domains: Reports on domain-specific metrics
- **Administration Domain:** System-wide monitoring
- **AI Domain:** Provides data for algorithms

---

## 6. Administration Domain

### Purpose
Manage system configuration, platform governance, and organizational operations.

### Responsibilities
- Manage platform settings and configuration
- Manage organizational structure
- Set policies and governance rules
- Manage content moderation and quality
- Handle dispute resolution
- Manage platform security and compliance
- Oversee system operations
- Create and manage platform features
- Manage languages and localization
- Coordinate cross-domain policies

### Key Concepts
- **Platform Settings** - System configuration
- **Organization** - SkillForge entity and structure
- **Policy** - Rules governing platform behavior
- **Role** - User permissions and responsibilities
- **Moderation** - Content and community oversight
- **Compliance** - Legal and regulatory adherence
- **Localization** - Language and regional support
- **Feature Flag** - Controlled feature rollout

### Boundaries
- Owns platform governance and policy
- Owns role and permission management
- Owns content moderation and quality standards
- Does NOT own user authentication (Identity Domain)
- Does NOT own individual user data (Identity Domain)
- Does NOT own data analysis (Analytics Domain)
- Does NOT own specific domain operations (each domain)

### Key Metrics
- Policy compliance rate
- Content quality rating
- Moderation response time
- System uptime
- Regulatory compliance

### Related Domains
- All domains: Sets policies affecting all
- **Identity Domain:** Manages admin roles

---

## 7. Identity & Access (Cross-Cutting)

### Purpose
Manage user identity, authentication, authorization, and privacy.

### Responsibilities
- User registration and account management
- Authentication (login, security)
- Authorization (permissions and roles)
- User profile data management
- Privacy and data protection
- Account security and recovery
- Credential management
- Session management
- Data export and deletion
- Compliance with privacy regulations

### Key Concepts
- **User Account** - Individual SkillForge user
- **User Role** - Type of user (Learner, Instructor, Admin)
- **Authentication** - Verifying user identity
- **Authorization** - Determining user permissions
- **User Profile** - Basic user data
- **Privacy** - Data protection and user consent
- **Credential** - Username/password, OAuth token
- **Session** - Active user login

### Boundaries
- Owns authentication and authorization
- Owns user account management
- Owns privacy and data protection
- Works with all domains for authorization
- Does NOT own domain-specific user data
- Does NOT own role-specific permissions (Administration)
- Privacy-first: Minimal data collection

### Key Metrics
- Authentication success rate
- Account security incidents
- Privacy policy compliance
- User consent rate
- Data deletion/export requests processed

### Related Domains
- All domains: Depends on for authentication
- **Administration Domain:** Role and permission policies
- **Analytics Domain:** Aggregate data only, no PII

---

## Cross-Cutting Concerns

### AI & Guidance (Cross-Cutting)
**Responsibilities:**
- Personalized learning path recommendations
- Adaptive content suggestions
- Intelligent tutoring and support
- Progress prediction and intervention
- Career path recommendations
- Content curation assistance

**Dependencies:** Uses data from all domains

### Notifications (Cross-Cutting)
**Responsibilities:**
- Learner progress notifications
- Peer interaction alerts
- Career opportunity alerts
- Community messages
- System notifications

**Dependencies:** Triggers from Learning, Career, Community domains

---

## Domain Interactions

### Data Flow Example: Learner Starting a Path

```
1. Identity Domain
   → Authenticates user
   → Checks authorization

2. Learning Domain
   → User enrolls in learning path
   → Path selected from Skill Domain definitions

3. Skill Domain
   → Provides competency framework
   → Provides learning objectives
   → Provides assessment requirements

4. Career Domain
   → Defines projects required for competency
   → Provides assessment rubrics

5. Analytics Domain
   → Tracks enrollment
   → Measures progress

6. AI Domain
   → Recommends content based on pace
   → Suggests peer study groups
   → Predicts completion likelihood

7. Community Domain
   → Connects to study group
   → Enables peer support
```

---

**Status:** Approved  
**Last Updated:** 2026-07-11  
**Reviewed By:** Architecture & DDD Team
