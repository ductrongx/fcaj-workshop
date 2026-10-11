---
title: "Week 2 Worklog"
menuTitle: "Week2"
date: 2026-10-05
weight: 2
chapter: false
pre: " <b> 1.2 </b> "
---

## IAM, policies and temporary application permissions

**Week 2 period:** 05/10/2026–11/10/2026. **Report updated:** 11/10/2026.

**Learning scope:** Section 1 — Explore AWS Services; Region/AZ review, user/group/role sections of `000002`, and application role concepts/configuration related to `000048`.

This week focused on distinguishing identities from permissions, practicing IAM in the Happy Path account, and simulating narrowly scoped policies. IAM objects were created, an AdminRole session was used, and cleanup was reported. The EC2 application role remains configured but has not been verified through a real S3 application request.

### Week 2 objectives

| Objective | Completion criteria |
| --- | --- |
| Distinguish Region/AZ and AWS identities. | Explain Region/AZ, AWS account, Builder ID, root, IAM user and role sessions; identify unverified security settings. |
| Practice users/groups and Switch Role. | Create IAM objects, sign in and confirm an active AdminRole session; record cleanup status. |
| Read policies and apply least privilege. | Explain Effect/Action/Resource/Condition; simulate Allow, implicit deny and explicit deny. |
| Understand application roles. | Distinguish trust/permissions policies, explain temporary credentials and configure a narrowly scoped EC2 S3 read role. |
| Continue CLI and live permission testing. | Identify caller/Region and compare results before/after a small permission change; no results are recorded in the three notes summarized here. |

### Tasks for the week

The table is a **content allocation based on Monday–Wednesday notes**, not confirmation that tasks took place on the scheduled dates. Actual dates have not been recorded; the update date is not substituted for practice dates.

| Day / scheduled date | Task | Start date | Completion date | Status | Reference |
| --- | --- | --- | --- | --- | --- |
| Monday — 05/10 | Review Region/AZ; create AdminGroup, AdminUser, AdminRole, OperatorUser; Switch Role and IAM cleanup. | Not recorded | Not recorded | Completed creation/role switching scope; cleanup reported in practice notes. | [000002 — IAM](https://000002.awsstudygroup.com/vi/) |
| Tuesday — 06/10 | Read policies and least privilege; simulate S3 permissions and SecureTransport. | Not recorded | Not recorded | Completed simulation scope according to learner confirmation. | [IAM Policy Simulator](https://docs.aws.amazon.com/IAM/latest/UserGuide/access_policies_testing-policies.html) |
| Wednesday — 07/10 | Study application roles; configure EC2 trust and S3 photos read permissions. | Not recorded | — | Configured — pending application verification. | [000048 — Application roles](https://000048.awsstudygroup.com/) |

> **To be added — Actual dates:** Dates of studying, creating objects, running simulations and cleanup corresponding to the three notes.

### Week 2 achievements

| Lab or objective | Result within report scope | Status | Evidence |
| --- | --- | --- | --- |
| Region/AZ and identities | Distinguished Region, AZ, Data Center, Edge Location, account, Builder ID, root and IAM user. | Completed theory scope; root security unverified. | MC-01; learning notes. |
| `000002` — Users/groups and Switch Role | Created AdminGroup, AdminUser, AdminRole, OperatorUser; read the users list in an AdminRole session. | Completed stated scope. | MC-03–MC-06; practice notes. |
| `000002` — Cleanup | Learner reported deleting both users, AdminGroup and AdminRole. | Performed; no post-deletion screenshots/logs checked. | Practice notes. |
| Policies and least privilege | Simulated action/resource permissions, explicit deny and Condition. | Completed simulation scope. | Learner confirmation; screenshots/output pending. |
| `000048` — Application role | Configured an EC2 role and S3 read policy using the example. | Configured — pending verification. | Learner confirmation; policy screenshots pending. |
| CLI / API tests before–after | No results in Monday–Wednesday notes. | Practice not recorded. | None available. |

These results do not establish completion of the full `000048` lab, a multi-AZ deployment or live CLI permission tests.

### Learning and lab details

#### Region/AZ and the lab account

A Region is a geographic area with multiple AZs; each AZ contains one or more Data Centers. Separate infrastructure supports fault isolation. Applications must be designed and deployed appropriately to benefit from multiple AZs; selecting a Region does not deploy across every AZ.

The lab account is **Happy Path**. The Builder ID configuration session uses `AccountFullAccessRole`; IAM users and root are separate identities. Following Advanced features activation, the account is managed through AWS Organizations and the Console displays multiple Regions. The IAM Identity Center team name differs from AdminGroup. Learned that activation cannot be reversed and removes existing spend limits; budget alerts are not automatic spending caps. [AWS documentation](https://docs.aws.amazon.com/accounts/latest/reference/activate-advanced-features.html)

MC-06 indicates MFA/passkey for AdminUser, while OperatorUser shows `—` at capture time. Builder ID/root MFA, a separate strong root password and root access keys remain unverified; IAM user MFA does not establish root security.

> **To be added — Account security:** Builder ID/root MFA for Happy Path, root credential and access key status, and inspection dates. Region/resource/AZ observations in the notes are insufficient to complete the inventory.

#### `000002` — IAM users/groups and Switch Role

**References:** [Create group/user](https://000002.awsstudygroup.com/vi/2-create-admin-user-and-group/), [Create role/user](https://000002.awsstudygroup.com/vi/3-aws-role/), [Switch Role](https://000002.awsstudygroup.com/vi/4-switch-roles/), [Cleanup](https://000002.awsstudygroup.com/vi/5-cleanup/).

- Created AdminGroup and AdminUser; reported using AdministratorAccess and adding the user to the group. MC-03 shows the group before any members; MC-04 shows one group membership without its name or policy details.
- Created AdminRole and OperatorUser, signed in as OperatorUser and switched roles. MC-05 confirms role creation; MC-06 confirms the AdminRole session can read the users list.
- Learned that roles are not attached to users/groups as permissions policies. A switched session uses role permissions instead of the original user permissions; switching back does not undo changes. No separate test after switching back is available.
- Reported deleting AdminUser, OperatorUser, AdminGroup and AdminRole; this does not imply cleanup of all account resources or system roles.

> **To be added — Cleanup evidence:** Post-cleanup Users, User groups and Roles screenshots/logs confirming the four lab objects are absent, with inspection dates.

#### Policies and least privilege — supplementary simulations for `000002`

Studied Effect (Allow/Deny), Action (API), Resource (ARN scope), Condition, and granting only necessary permissions. The example policy allows only `s3:GetObject` on `arn:aws:s3:::fcaj-example-bucket/photos/*`.

The following results are recorded from the learner's confirmation of completing Tuesday's guided practice; individual simulation screenshots/output have not been checked:

| Simulator test | Reported result |
| --- | --- |
| GetObject on `photos/cat.jpg` | Allowed. |
| GetObject on `private/report.pdf` | Implicit deny — outside the allowed resource scope. |
| DeleteObject on `photos/cat.jpg` | Implicit deny — delete action not allowed. |
| Add GetObject Deny on `photos/private/*`; test `photos/private/secret.jpg` | Explicit deny despite matching Allow on `photos/*`. |
| Allow with Condition `aws:SecureTransport = true`; context true / false | Allowed / implicit deny within the tested policy. |

Objects refer to the example bucket; its existence is not claimed. The Simulator does not make live S3 API calls. An unmet condition prevents that Allow from applying; it is not an explicit HTTP deny across the bucket. [Simulator documentation](https://docs.aws.amazon.com/IAM/latest/UserGuide/access_policies_testing-policies.html)

> **To be added — Policy evidence:** Allow, implicit deny, explicit deny and SecureTransport screenshots/output, tested policies/context and inspection dates.

#### `000048` — Application role: theory and configuration

Distinguished **trust policies** (who can assume the role) from **permissions policies** (what the role can do). Studied the flow: EC2 associated with an instance profile containing the role → application obtains temporary credentials through instance metadata → SDK signs requests → S3 evaluates permissions. Applications do not use Console passwords; avoid embedding long-term access keys in code. [AWS guide](https://docs.aws.amazon.com/IAM/latest/UserGuide/id_roles_use_switch-role-ec2.html)

According to Wednesday's note and learner confirmation, configured `fcaj-ec2-photo-reader`, trusting `ec2.amazonaws.com` with `sts:AssumeRole`, and inline policy `ReadPhotosOnly` allowing `s3:GetObject` under `photos/*` in the example bucket. No screenshots are available to check actual names/configuration.

**Remaining scope:** EC2/a real bucket and application S3 access have not been implemented and verified within this guided exercise. The separately discussed EC2 Terminated screenshot does not establish that the instance used this role or successfully read S3. Retention/deletion of the role and instance profile has not been recorded.

> **To be added — Application role:** Permissions/Trust relationships screenshots, actual names if different, inspection dates and role/instance profile retention or deletion status.

### Practice evidence

Screenshots show capture-time state; capture dates have not been verified and they do not show post-cleanup state.

**MC-01 — Studying AZ concepts in Module 01-01 — Introduction to AWS.**

![AWS introductory video explaining Availability Zones](/images/1-worklog/1.2-week2/watching_video_youtube_introduction_to_aws_t2.png)

Shows learning material, not a multi-AZ deployment.

**MC-02 — Advanced features activation review and team name screen.**

![AWS Settings describing Advanced features changes](/images/1-worklog/1.2-week2/open_advanced_team_mode.png)

Shows review before confirmation, not completed activation by itself; activation is reported by the learner and followed by IAM actions.

**MC-03 — AdminGroup exists with 0 members at capture time.**

![IAM groups list containing AdminGroup](/images/1-worklog/1.2-week2/created_IAM_group.png)

**MC-04 — AdminUser created successfully; Groups column shows 1.**

![AdminUser creation success message](/images/1-worklog/1.2-week2/created_user_admin.png)

**MC-05 — Console confirms successful AdminRole creation.**

![Role AdminRole created message](/images/1-worklog/1.2-week2/created_role.png)

**MC-06 — AdminRole session reads the AdminUser and OperatorUser list.**

![AdminRole session displaying two IAM users](/images/1-worklog/1.2-week2/switch_role.png)

### Issues and follow-up actions

| Observation | Verified cause / supported conclusion | Action / next step | Status |
| --- | --- | --- | --- |
| IAM groups shows Feature unavailable. | UI requires Advanced features. | Activation reported, followed by group creation. | Resolved within lab scope. |
| OperatorUser denied GetUser/GetLoginProfile. | Error states no identity-based policy allows these actions in the user session. | Switch Role; MC-06 confirms reading the users list in the role session. No separate retest of the two failed APIs is established. | Role session used; detailed retest unavailable. |
| Builder ID sign-in works but root Authentication failed. | Invalid credentials versus disabled root sign-in remains undetermined. | Continue using authorized identities; inspect root credentials for the correct account. | Root unverified. |

### Lessons learned and next steps

- Successful sign-in does not authorize every API; identify the current user/role.
- Scope permissions to necessary actions/resources; distinguish simulations from live requests and role configuration from a working application.
- Save dates, policy/context and output when testing so results can be checked.

| Priority | Next task | Completion criteria |
| --- | --- | --- |
| High | AWS CLI: sign-in, profiles, caller and Region. | Run identity/resource read commands, record output and distinguish authentication/permission/scope errors. |
| High | Test before/after adding one narrow permission. | Same identity, action and Region; record API results before/after. |
| Medium | EC2/S3 in `000048`, scheduled for week 3. | Confirm credential source, read allowed objects, test outside scope and clean up. |
| Medium | Complete evidence and week 1 carry-over checks. | Add dates, policy/cleanup and account security evidence; review Budgets, Support, Cost Explorer and inventory against the checklist. |
