# Subtask 1 – Field Inventory Review

**Objective:**  
List and confirm all provided fields from the uploaded spreadsheet (Grafana-Feilds-tonormalise.xlsx) before schema design.

**Details:**  
| Field Name | Data Type | Example | Notes | Source |
|-------------|------------|----------|--------|--------|
| platform_name | varchar(250) | Payments platform, Franchise Data | (check Jira) | JMeter |
| Agile_release_train | varchar(250) | ISO 2022, Project Rubics |  | JMeter |
| project_name | varchar(250) | D&A Specific, Euro Domestic, Batch |  | JMeter |
| release_name | varchar(250) | Migration Events - 4, 2024.2 | Release name will be consistent with Jira | JMeter |
| Source_system | varchar(250) | K4, K5, Athena, Mongo collections |  | JMeter |
| Target_system | varchar(250) | K4, K5, Athena, Mongo collections |  | JMeter |
| test_cycle | varchar(250) |  | Fetch from Jira | Jira |
| test_run_name | varchar(250) | BVT, SIT, NFT, Regression | TBC | GitLab |
| test_run_id | int | unique | System generated | GitLab |
| test_id | varchar(250) |  | From Jira or GitLab | Jira |

**Deliverable:**  
Verified list of fields and metadata for schema mapping.
