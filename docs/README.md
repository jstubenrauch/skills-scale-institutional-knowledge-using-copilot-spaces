# OctoAcme Project Management Processes

This README provides a comprehensive overview of the project management processes used by OctoAcme. It summarizes our key workflows, roles, communication strategies, and quality assurance practices.

*Related to: [Issue #2](https://github.com/jstubenrauch/skills-scale-institutional-knowledge-using-copilot-spaces/issues/2)*

## Overview

OctoAcme centralizes project knowledge and uses consistent, repeatable workflows to deliver customer value iteratively. Our approach emphasizes:

- **Customer-first mindset**: Prioritizing customer value and usability in all decisions
- **Clear ownership**: Each project has named Project Manager (PM) and Product Lead
- **Data-informed decisions**: Measuring impact and iterating based on evidence
- **Psychological safety**: Encouraging feedback and continuous learning
- **Iterative delivery**: Delivering small, testable increments

## Workflows

OctoAcme follows a standardized five-phase project lifecycle that ensures consistency and repeatability across all projects:

### 1. Initiation
- **Purpose**: Validate business need and authorize work
- **Key activities**: 
  - Define problem statement and measurable outcomes
  - Identify stakeholders and champions
  - Create Project One-pager with success criteria
  - Establish high-level timeline and resource needs
  - Document initial risks
- **Deliverables**: Project One-pager, stakeholder list, communication plan, initial risk list
- **Decision gate**: Move to planning when success metrics are clear, stakeholders agree on priority, and team availability is confirmed

### 2. Planning
- **Purpose**: Convert approved initiative into actionable plan and backlog
- **Key activities**:
  - Hold project kickoff meeting
  - Break work into shippable increments with acceptance criteria
  - Estimate scope (T-shirt sizing or story points)
  - Define Definition of Done (DoD)
  - Identify dependencies and integration points
  - Create release plan and milestone map
- **Deliverables**: Prioritized backlog, release timeline, Definition of Done, test plan
- **Sprint planning**: Timeboxed to agreed sprint length, respecting team capacity

### 3. Execution & Tracking
- **Purpose**: Manage day-to-day work and track progress toward milestones
- **Key activities**:
  - Follow project board workflow: Backlog → Ready → In Progress → In Review → QA → Done
  - Implement features with proper testing and code reviews
  - Track velocity and burndown metrics
  - Monitor success metrics from Project One-pager
  - Update risk register weekly
- **Quality practices**: Unit tests, integration tests, end-to-end smoke tests, security scanning in CI, manual QA for acceptance
- **Pull Request workflow**: Small PRs (≤400 lines), include issue link and acceptance criteria, automated tests in CI, require approval before merging

### 4. Release & Deployment
- **Purpose**: Standardize production releases to reduce risk and improve observability
- **Release types**: Patch (hotfixes), Minor (incremental features), Major (significant changes)
- **Pre-release requirements**:
  - All acceptance criteria met and PRs merged
  - Passing CI and security scans
  - Release notes drafted
  - Rollback/mitigation plan documented
  - Smoke tests prepared
- **Deployment process**: Schedule window → backup → deploy to staging → test → deploy to production → verify → announce
- **Incident response**: Trigger on-call, rollback if necessary, triage root cause, capture action items

### 5. Retrospective & Continuous Improvement
- **Purpose**: Capture learnings and convert them into actionable improvements
- **When**: After each sprint, release, important milestone, or incident
- **Format**: What went well, what could be improved, action items (with owners and due dates), follow-up on previous actions
- **Best practices**: Timebox 45-75 minutes, prioritize 2-3 top action items, track in backlog with clear owners
- **Culture**: Measure impact of improvements, celebrate progress, make iterative changes

## Roles and Personas

OctoAcme defines clear responsibilities and communication pathways for each role:

### Project Managers (PM)
- **Responsibilities**: Create and maintain project plans/timelines, manage risks and dependencies, facilitate meetings (kickoff, planning, retrospectives), ensure documentation and status reporting, coordinate cross-team communication
- **Goals**: Deliver projects on time and within scope, minimize unplanned work, maintain transparency
- **Communication**: Weekly status updates, risk registers, decision logs, project board coordination

### Product Managers (PdM)
- **Responsibilities**: Define problem statements and success metrics, prioritize roadmap and backlog, collaborate on trade-offs, validate solutions through research and metrics
- **Goals**: Maximize customer value and impact, make data-driven prioritization decisions, ensure product-market fit
- **Communication**: Weekly alignment with PM and engineering leads, roadmap updates, acceptance criteria and feature specs

### Developers
- **Responsibilities**: Implement features meeting acceptance criteria, write and maintain tests/documentation, participate in design and code reviews, assist in estimation and planning, identify technical risks
- **Goals**: Deliver reliable, maintainable code, reduce cycle time, maintain high test coverage and observability
- **Communication**: Daily standups, sprint planning, PR descriptions, code review comments, technical design docs

### QA/Testing
- **Responsibilities**: Validate quality and acceptance criteria, perform manual and automated testing, ensure test coverage across unit, integration, and end-to-end levels
- **Goals**: Catch issues early, ensure features meet specifications, maintain quality standards
- **Communication**: Test results, bug reports, acceptance validation

### Stakeholders
- **Responsibilities**: Provide inputs and approvals, validate business requirements, support go-to-market activities
- **Goals**: Ensure projects align with business objectives and customer needs
- **Communication**: Milestone updates, decision requests, release announcements

## Communication Strategies

OctoAcme maintains structured communication cadences to ensure alignment and transparency:

### Daily Communication
- **Daily standups** (15 minutes): Focus on progress, blockers, and dependencies
- **Team rhythm**: Delivery team synchronization

### Weekly Communication
- **Weekly sync**: PM + Product Manager alignment
- **Weekly delivery sync**: Show progress, updates, flagged risks
- **Risk register review**: Update status and mitigation plans

### Monthly Communication
- **Monthly stakeholder updates**: Progress against milestones and metrics
- **Roadmap reviews**: Alignment on priorities and timeline adjustments

### Ad-hoc Communication
- **Incident communication**:
  - Triage summary
  - Actions being taken
  - Expected timeline
  - Post-incident blameless retrospective scheduled
- **Escalation paths**:
  - Level 1: Team-level triage in daily standup
  - Level 2: PM escalates to Product Lead and dependent teams
  - Level 3: Sponsor-level escalation for business-impacting issues
  - Security incidents: Follow security incident runbook, notify Security on-call

### Communication Templates
OctoAcme provides standardized templates for consistency:
- **Weekly Status Template**: Progress this week, next steps, risks & blockers, asks/decisions needed
- **Incident Communication Template**: Triage summary, actions, timeline, retrospective plan
- **Release Notes Template**: Release name/number, date, summary, notable changes, migration steps, known issues

## Quality Assurance Practices

OctoAcme maintains high quality standards through comprehensive testing and continuous improvement:

### Automated Testing
- **Unit tests**: For all new logic and code changes
- **Integration tests**: Validate component interactions where applicable
- **End-to-end smoke tests**: Test critical flows before release
- **CI-based checks**: Automated tests and linting run in CI before PR approval
- **Security scanning**: Automated security scans in CI pipeline

### Manual Testing
- **Feature acceptance testing**: Manual QA for feature validation when needed
- **Exploratory testing**: Test edge cases and user scenarios
- **Pre-release validation**: Smoke tests in staging environment

### Acceptance Criteria
- **Definition of Done (DoD)**: Documented for each project and consistently applied
- **Clear acceptance criteria**: Defined for each backlog item before work begins
- **PR requirements**: Include issue link and acceptance criteria in PR description
- **Review process**: At least one approval required before merging (or team-defined policy)

### Continuous Improvement
- **Retrospectives**: Held after each sprint, release, milestone, or incident
- **Action items**: Tracked with clear owners, due dates, and success criteria
- **Weekly review**: Outstanding action items reviewed in PM sync
- **Metrics tracking**: Velocity, burndown, success metrics from Project One-pager
- **Dashboards**: Monitor key signals (errors, latency, usage)
- **Blameless culture**: Focus on learning and improvement, not blame

### Risk Management
- **Risk Register**: Simple table tracking ID, description, impact, likelihood, owner, mitigation plan, status
- **Risk lifecycle**: Identify → assess → mitigate → monitor
- **Proactive identification**: During planning and ongoing execution
- **Regular review**: Weekly syncs to update risk status
- **Escalation**: Clear paths for business-impacting issues

## Key Artifacts and Templates

OctoAcme leverages consistent checklists and templates extensively:

### Planning Artifacts
- **Project Charter/One-pager**: Problem, goal, success metrics, stakeholders, timeline, risks, team roles
- **Roadmap and Release Plan**: Milestones, dependencies, release schedule
- **Sprint/Iteration Backlog**: Prioritized items with acceptance criteria and estimates
- **Definition of Done**: Quality standards for completed work
- **Risk Register**: Risk tracking with mitigation plans

### Execution Artifacts
- **Project Board**: Visual workflow management (Backlog → Ready → In Progress → In Review → QA → Done)
- **Status Reports**: Weekly progress, risks, blockers, decisions needed
- **Pull Requests**: Code changes with context and acceptance criteria
- **Test Plans**: Testing approach and coverage

### Release Artifacts
- **Release Notes**: Summary of changes, migration steps, known issues
- **Deployment Checklist**: Pre-deployment, deployment, and post-deployment verification steps
- **Rollback Plan**: Mitigation strategy for deployment issues

### Retrospective Artifacts
- **Retrospective Notes**: What went well, improvements, action items
- **Action Item Tracking**: Owners, due dates, success criteria
- **Decision Logs**: Key decisions and rationale

## Documentation Structure

All project documentation is centralized in the repository for easy access:

- Keep Project Charter updated in the project repo
- Add process-specific docs to `.copilot/` for Copilot Spaces context
- Use single source of truth for status (project README or release doc)
- Maintain documentation in sync with actual practices

## Additional Resources

For more detailed information on specific topics, refer to:

- [Project Management Overview](./octoacme-project-management-overview.md) - Principles, roles, and lifecycle
- [Roles and Personas](./octoacme-roles-and-personas.md) - Detailed role definitions
- [Project Initiation](./octoacme-project-initiation.md) - Starting new projects
- [Project Planning](./octoacme-project-planning.md) - Creating actionable plans
- [Execution and Tracking](./octoacme-execution-and-tracking.md) - Day-to-day management
- [Release and Deployment](./octoacme-release-and-deployment.md) - Production releases
- [Retrospective and Continuous Improvement](./octoacme-retrospective-and-continuous-improvement.md) - Learning and improving
- [Risk Management & Communication](./octoacme-risks-and-communication.md) - Managing risks and stakeholder communication

---

*This documentation is maintained by the OctoAcme team. For questions or suggestions, please open an issue or contact the Project Management Office.*
