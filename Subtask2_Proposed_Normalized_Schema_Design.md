# Subtask 2 – Proposed Normalized Schema Design & Clarification Questions

**Objective:**  
Design a draft normalized schema and identify clarification points to confirm before DDL creation.

**Proposed Entities & Relationships:**  
| Entity | Key Fields | Relationships | Source |
|--------|-------------|----------------|---------|
| Platform | platform_id, platform_name | 1:N → AgileReleaseTrain | JMeter |
| AgileReleaseTrain | art_id, art_name, platform_id | 1:N → Project | JMeter |
| Project | project_id, project_name, art_id | 1:N → Release | JMeter |
| Release | release_id, release_name, project_id | 1:N → TestCycle; N:M → System | Jira |
| System | system_id, system_name | M:N → Release | JMeter |
| Release_System_Map | release_id, system_id, system_role | Join table for Source/Target | Derived |
| TestCycle | cycle_id, cycle_name, release_id | 1:N → TestRun | Jira |
| TestRun | test_run_id, test_run_name, cycle_id | 1:N → Test | GitLab |
| Test | test_id, test_run_id | Leaf entity | Jira/GitLab |

**Relationships Summary:**  
- Platform → ART → Project → Release  
- Release ↔ Systems (via mapping)  
- Release → Test Cycles → Test Runs → Tests

**Clarification Questions:**  
1. Is the hierarchy Platform → ART → Project → Release always consistent, or can projects span multiple ARTs?  
2. Should Source and Target systems be stored in one mapping table or separately?  
3. Can a Release have multiple source and multiple target systems?  
4. Are test_run_id and test_id globally unique (GitLab + Jira)?  
5. What’s the preferred ingestion path — direct API, JSON intermediate, or CSV extract?  
6. Should all IDs be system-generated or align with IDs from Jira/GitLab?  
7. Are lowercase snake_case names confirmed for Postgres?  
8. Do we need to store historical versions or just current snapshots?

**Deliverable:**  
Proposed normalized schema and list of open questions to validate before generating Postgres DDL.
