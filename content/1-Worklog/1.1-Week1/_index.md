---
title: "Week 1 Worklog"
date: 2026-09-28
weight: 1
chapter: false
pre: " <b> 1.1. </b> "
---

## AWS Free Tier and Cost Management

**Week 1:** 28 September–4 October 2026.

**Results updated:** 9 October 2026.

The first week focused on creating an AWS account, using the Console, completing the five credit activities, and setting up cost management before deploying workloads. This report combines the practice notes with the latest confirmation of completion.

### Program lessons and labs studied

Week 1 covered two lessons in **Section 1 — Explore AWS Services** of the [First Cloud Journey roadmap](https://cloudjourney.awsstudygroup.com/1-explore/). Each program section contains multiple lessons and labs and may span several weeks.

| Lesson/lab ID | Content studied | Practice results |
| --- | --- | --- |
| [000001 — Create an AWS Account / AWS Free Tier 2025](https://000001.awsstudygroup.com/) | Account creation, Free Plan and Paid Plan, AWS Credits, basic services introduced through five activities, Monitoring & Cost Optimization, and FAQ. | Created an account, completed five credit activities, received $200 credits, and upgraded to Paid Plan. Individual monitoring outcomes are documented below. |
| [000007 — Manage AWS costs with AWS Budgets](https://000007.awsstudygroup.com/vi/) | AWS Budgets concepts and the distinction between cost and usage budgets. | Configured Cost Budget and Usage Budget. |

**Scope of completion:** The five credit activities belong to lesson **000001**. Basic EC2, Bedrock, Lambda, and RDS practice in this lesson does not establish completion of their separate in-depth labs or all of Section 1. RI Budget and Savings Plans Budget have not been recorded as implemented.

### Week 1 objectives

- Understand Free Plan, Paid Plan, and AWS Credits tracking.
- Complete five activities and understand the basic roles of EC2, Amazon Bedrock, AWS Budgets, AWS Lambda, and Amazon RDS.
- Set up Cost Budget, Usage Budget, and Project Spend Limit.
- Explore Cost Explorer, resource checks, and measures to limit unexpected charges.

### Weekly content allocation

The table organizes learning content across working days from the internship start date of 28 September 2026. It is a content allocation, not a verified daily record of when each action took place. The report update on 9 October falls in Week 2.

| Day | Date | Learning and practice | Reference |
| --- | --- | --- | --- |
| Monday | 28/09/2026 | Learn about AWS Free Tier; create an account; explore the Console, Free Plan, and Paid Plan. | [AWS Free Tier 2025](https://000001.awsstudygroup.com/) |
| Tuesday | 29/09/2026 | Complete the EC2 and Amazon Bedrock activities; learn about virtual servers and AI foundation models. | [Five credit activities](https://000001.awsstudygroup.com/4-hướng-dẫn-chi-tiết-5-nhiệm-vụ-kiếm-tiền/) |
| Wednesday | 30/09/2026 | Complete the AWS Budgets activity; create Cost Budget and Usage Budget; explore alert thresholds. | [AWS Budget workshop](https://000007.awsstudygroup.com/vi/) |
| Thursday | 01/10/2026 | Complete the Lambda and RDS activities; learn about serverless computing and managed relational databases. | [Five credit activities](https://000001.awsstudygroup.com/4-hướng-dẫn-chi-tiết-5-nhiệm-vụ-kiếm-tiền/) |
| Friday | 02/10/2026 | Review all five activities; check credits, Paid Plan, and spend limit; set up Cost Explorer and study Monitoring & Cost Optimization and FAQ. | [AWS Free Tier 2025](https://000001.awsstudygroup.com/) |

Dates in tables use **DD/MM/YYYY**.

### Overall results

Figures recorded at the check documented in the report updated on 9 October 2026:

| Item | Result |
| --- | --- |
| AWS Account | Created; Console in use |
| Credit activities | 5/5 completed, as confirmed in the latest practice update |
| Available AWS Credits | $200.00 |
| Account plan | Upgraded to Paid Plan |
| Recorded charges / amount due | $0.00 / $0.00 |
| Project | Happy Path — Within limit |
| Project Spend Limit | $20/month |
| Cost Budget | Configured |
| Usage Budget | Configured |
| Cost Explorer | Initial setup complete; awaiting data |

### Five activities and learning outcomes

The activity list follows the [AWS Study Group guide](https://000001.awsstudygroup.com/4-hướng-dẫn-chi-tiết-5-nhiệm-vụ-kiếm-tiền/). Completion reflects my latest practice confirmation.

| Activity | Status | Basic knowledge gained |
| --- | --- | --- |
| Launch an EC2 instance | Completed | Virtual servers; roles of AMIs, instance types, and security groups. |
| Use Amazon Bedrock Playground | Completed | AI foundation models; submitting prompts and viewing responses. |
| Set up AWS Budgets | Completed | Budget monitoring and cost alerts. |
| Create a web app with AWS Lambda | Completed | Running functions with serverless computing. |
| Create an Amazon RDS database | Completed | AWS-managed relational databases. |

The earlier unresponsive Aurora/RDS create button was an obstacle during a previous attempt. The RDS activity is now recorded as **completed** based on the latest confirmation; the cause of the earlier issue remains undetermined.

### AWS Budgets and Cost Explorer

Configured **Cost Budget** to monitor spending and **Usage Budget** to monitor service consumption. Their tracking goals and units differ, as explained in the [AWS Budget workshop](https://000007.awsstudygroup.com/vi/).

The Budgets screenshot shows `daily-budget-10` ($10), `monthly-budget-25` ($25), and `monthly-budget-50` ($50), all with OK status and $0.00 used. It illustrates the budget list; it does not show the detailed Usage Budget configuration or successful delivery of alert emails.

Happy Path has a separate **$20/month Project Spend Limit**. The Budgets interface states that budgets do not set hard spend limits; creating a budget does not imply that every resource will stop automatically.

Accessed Cost Explorer and completed initial setup. Explored Unblended Cost, daily tracking, service grouping, and identifying Top 5 Cost Drivers. At the check, AWS was preparing data and requested another check after 24 hours; there was no data available to identify the highest-cost services.

### Resource monitoring and outstanding items

| Item | Practice result |
| --- | --- |
| Emergency Cost Control | Checked Billing Dashboard and EC2 in the inspected Region. No EC2 instances were found; recorded charges were $0 with $200 credits remaining. No emergency shutdown was needed. |
| CloudWatch Billing Alerts | Not implemented: no `AWS/Billing` metrics were visible, and Billing Preferences displayed an Enterprise AWS requirement at the check. Recorded as an observed limitation; the final cause has not been verified. |
| Resource tagging through Tag Editor | Not implemented: `AccessDeniedException` with an explicit deny in an AWS Organizations SCP. |
| AWS CloudShell | Unavailable at the check due to an account verification in progress message. |
| Custom CloudWatch Metrics | Studied; the Lambda function for publishing cost metrics has not been implemented. This is separate from the Lambda credit activity. |

Studied resource auditing and stopping non-critical EC2 instances when needed. Checking one Region does not establish resource status across all Regions.

### Practice screenshots

**Figure 1 — Console shows $200 credits and $0.00 monthly charges before the plan upgrade.** The screenshot does not display the five activity statuses; the 5/5 result is based on the practice confirmation.

![Console showing $200 AWS Credits and $0.00 monthly charges](</images/1-worklog/1.1-week1/full_5_task_earn%20_credit.png>)

**Figure 2 — Created budgets and the $20 Happy Path Project Spend Limit.**

![Created budgets and the $20 project spend limit](/images/1-worklog/1.1-week1/list_budget_created.png)

**Figure 3 — Billing shows $200 available credits, $0 amount due, and Happy Path within its $20 limit.** The Paid Plan upgrade is recorded from the practice confirmation; this Billing screenshot does not display the account plan name.

![Billing showing credits, amount due, and project status](/images/1-worklog/1.1-week1/total_200_and_paid_plan.png)

### Lessons learned

- Understand the five services better through practice and monitor costs before deploying further workloads.
- Studied credit eligibility, charges that may not be covered, and the one-time reward for each activity through the [FAQ](https://000001.awsstudygroup.com/8-faq---giải-đáp-mọi-thắc-mắc/).
- Distinguish configuration errors from IAM/SCP restrictions, account verification, and data preparation delays.
- Record completed activities, setup awaiting data, and unimplemented features separately. A $0 balance at one check does not guarantee that future charges will remain zero.

**Summary:** Completed the Week 1 foundations: created an AWS account, completed five activities, received $200 credits, upgraded to Paid Plan, and configured Cost Budget, Usage Budget, and Project Spend Limit. Outstanding advanced monitoring items are documented separately for follow-up.
