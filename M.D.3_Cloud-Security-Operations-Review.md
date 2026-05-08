# M.D.3 — Cloud Security Operations Review
## AWS IAM Administration, CloudWatch Monitoring, and Account Security Controls

**Technical Context:** AWS Identity and Access Management, CloudWatch Monitoring, EC2 Recovery Actions, and Billing Alerts

---

## Overview

This project focused on practical AWS cloud-security administration through Identity and Access Management (IAM), policy review, resource tagging, CloudWatch alarm configuration, EC2 monitoring, and billing-alert awareness.

The goal was to demonstrate how cloud environments rely on two connected security functions: controlled access and continuous monitoring. IAM was used to create and review access boundaries, while CloudWatch was used to monitor infrastructure metrics and trigger operational responses.

---

## Evidence Screenshots

### IAM User Permission Configuration

![AWS IAM user permissions and group attachment](images/M.D.3%20Cloud%20Security%20Operations%20Part%201.png)

The IAM user view shows `User1` configured with console access and attached permission policies. The screenshot also shows group-based access and AWS-managed policy attachment, demonstrating hands-on IAM permission review.

### AdministratorAccess Policy Review

![AWS AdministratorAccess managed policy review](images/M.D.3%20Cloud%20Security%20Operations%20Part%202.png)

The `AdministratorAccess` managed policy was reviewed to understand the scope of elevated AWS permissions. The policy summary shows broad access across AWS services and resources, reinforcing why administrative permissions should be assigned carefully and monitored.

### CloudWatch Alarm Dashboard

![AWS CloudWatch alarms configured for EC2 monitoring](images/M.D.3%20Cloud%20Security%20Operations%20Part%203.png)

CloudWatch was configured with multiple alarms for EC2-related monitoring. The dashboard demonstrates infrastructure monitoring, threshold-based alerting, and automated response actions.

---

## Objectives

- Configure IAM users and administrative groups
- Review policy inheritance through IAM groups
- Understand root-user vs standard IAM-user security boundaries
- Apply AWS resource tags and account alias concepts
- Configure CloudWatch alarms for EC2 metrics and status checks
- Create billing alerting for cost-awareness
- Understand how AWS CLI commands support monitoring workflows

---

## IAM Access Management Workflow

The IAM portion of the project focused on creating and reviewing a controlled access structure instead of relying on the AWS root account for routine administrative activity.

The IAM user was associated with a group and assigned managed-policy permissions. This demonstrated how AWS permissions can be centralized through groups, allowing users to inherit permissions without manually attaching every policy individually.

Security relevance: IAM supports least-privilege access, user separation, auditability, and safer administration. Even when elevated permissions are used for lab purposes, the exercise showed why administrative access must be intentionally assigned and reviewed.

---

## Root User vs IAM User Model

The project reviewed the difference between the root user and a standard IAM user.

The root user represents the account owner and has unrestricted access to account-level controls. In contrast, an IAM user starts with limited access and must be granted permissions through groups, policies, or roles.

This distinction is important because routine use of the root account increases risk. Delegating access through IAM allows access to be scoped, reviewed, and adjusted without exposing full account ownership privileges.

---

## Policy Review and Permission Inheritance

The `AdministratorAccess` policy was reviewed to understand the impact of AWS-managed administrative permissions. This policy provides broad access across services and resources, making it useful for understanding high-privilege access but risky if assigned without governance.

The project demonstrated:

- IAM user creation
- Group-based permission inheritance
- Managed-policy review
- Administrative-access visibility
- Permission assignment through IAM structures

Security relevance: policy review is central to cloud security because over-permissive identities are a common source of cloud exposure.

---

## Resource Tagging and Account Organization

AWS tags were reviewed as metadata key-value pairs that help organize, track, and manage cloud resources. Tags can support cost allocation, asset ownership, environment labeling, and administrative clarity.

An example tag value was created during the IAM work. This reinforced how tagging supports cloud governance and makes resources easier to identify during operations.

---

## Credential Handling Awareness

During IAM user creation, credential material such as sign-in information and access-related data may be exported through a CSV file. This part of the project reinforced that credential files must be stored securely and never committed to public repositories.

Security relevance: access keys, passwords, and sign-in URLs can expose cloud environments if mishandled. Strong credential hygiene is a major part of cloud-security administration.

---

## CloudWatch Monitoring and Alarm Configuration

AWS CloudWatch was used to configure alarms for EC2 monitoring and operational response.

The project included the following alarm configurations:

| Alarm | Monitored Condition | Threshold / Trigger | Action |
|---|---|---|---|
| Alarm #1 | EC2 CPU utilization | 80% CPU utilization | Email notification |
| Alarm #2 | EC2 system-status failure | Status check failed: system | Recover instance |
| Alarm #3 | High CPU utilization | 95% CPU utilization | Reboot instance |
| Alarm #4 | AWS billing threshold | $20 estimated charge | Billing notification |

These alarms demonstrated how AWS monitoring can support availability, incident response, and cost control.

Security relevance: monitoring is a defensive control. Alerts help administrators detect resource stress, system failure, and unexpected spending before they create larger operational issues.

---

## AWS CLI Monitoring Concepts

The AWS Command Line Interface was reviewed as an operational method for inspecting metrics and managing alarms from a terminal.

Example command capabilities included:

```bash
aws cloudwatch describe-alarms
aws cloudwatch get-metric-statistics
aws cloudwatch put-metric-alarm
aws cloudwatch set-alarm-state
```

These commands demonstrate how cloud operations can be automated or managed outside the web console.

Security relevance: CLI usage is important for scalable cloud administration, repeatable configuration, and incident-response workflows.

---

## Technical Skills Demonstrated

- AWS IAM user and group administration
- IAM managed-policy review
- Understanding of root-user vs IAM-user security boundaries
- AWS resource tagging concepts
- Credential-handling awareness
- CloudWatch alarm configuration
- EC2 monitoring and automated recovery/reboot actions
- Billing alert configuration
- AWS CLI monitoring awareness
- Cloud-security documentation

---

## Conclusion

This project demonstrated how AWS identity management and infrastructure monitoring work together to support secure cloud operations. IAM provided controlled access structures, while CloudWatch alarms provided visibility into system health, performance thresholds, automated recovery actions, and cost monitoring.

The project reinforced the importance of combining access control, monitoring, alerting, and credential hygiene when operating cloud environments.

---

## References

- Amazon Web Services. *AWS Identity and Access Management Documentation*. https://docs.aws.amazon.com/iam/
- Amazon Web Services. *Amazon CloudWatch Documentation*. https://docs.aws.amazon.com/cloudwatch/
- Amazon Web Services. *AWS Command Line Interface Documentation*. https://docs.aws.amazon.com/cli/
- Gregg, M., & Santos, O. (2022). *CEH Certified Ethical Hacker Cert Guide*. Pearson Education.

**M. Dominguez**
