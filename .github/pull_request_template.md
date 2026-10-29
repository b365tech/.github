<!--
  Banc365tech template
  Required for every PR targeting `dev` or `main`.
  Fill in every section. Do not delete or rename the headings or the labels ending in ":" —
  they are checked automatically by the "PR template check" workflow.
  Text inside these comment markers are not shown in the rendered PR.
-->

## Summary
<!-- One paragraph: what this change does and why it is needed. -->


## Ticket
<!--
  Link the originating ticket:
  - infrastructure, NSC or emergency change → Jira "Change & Access Requests" ticket
    (issue type Infrastructure Change)
  - project work → Jira issue (if it needs an infrastructure or NSC change, also link the
    Change & Access Requests ticket)
  More than one link is fine.
-->


## Security Impact
<!--
  Tick exactly one box.
  - If YES: describe the impact (e.g. authentication, crypto/HSM, network or Security Group
    rules, IAM, secrets, logging, flow of cardholder data) and the mitigation.
  - If NO: replace [reason] with why there is no security impact.
-->
- [ ] **Yes** — this change has a security impact.
  - Impact:
  - Mitigation:
- [ ] **No security impact** — [reason]


## NSC Change (PCI DSS 1.2.2)
<!--
  Tick exactly one of Yes / No.
  NSCs and network connections are those recorded in VNE-SEC-NET-001: security groups, route
  tables, VPC endpoints, payment brand connections, load balancer listeners, AWS WAF rules,
  Istio and OPA-Istio policies.
  If YES: tick every item. The reviewer confirms each one before approving.
-->
- [ ] **No** — this change does not modify an NSC or network connection.
- [ ] **Yes** — this change modifies an NSC or network connection.
 - Affected resources:
  - [ ] No inbound rule allows 0.0.0.0/0 or ::/0, except on the public entry points in VNE-SEC-POL-041 section 7.2
  - [ ] The source is the minimum required (a security group ID rather than a CIDR when the source is inside AWS)
  - [ ] Each allowed service, protocol and port has a business justification recorded in VNE-SEC-NET-001


## Significant Change (PCI DSS 6.5.2)
<!--
  A significant change is any of the following:
  - new hardware, software or network equipment added to the CDE
  - replacement or major upgrade of hardware or software in the CDE
  - any change to the flow or storage of account data
  - any change to the CDE boundary or to PCI DSS scope
  - any change to infrastructure supporting the CDE (e.g. directory services,
    time synchronisation, logging, monitoring)
  - any change to a third-party service provider supporting the CDE

  Tick exactly one of Yes / No.
  If YES: link the Jira ticket where the DevSecOps Lead records the post-change confirmation and tick every item below to confirm
  it is covered by that ticket. Where an item does not apply, record "N/A" and the reason
  in the ticket, then tick it here.
-->
- [ ] **No** — this is not a significant change.
- [ ] **Yes** — this is a significant change.
  - Post-change confirmation ticket:
  - [ ] Applicable PCI DSS requirements confirmed in place on all new or changed systems and networks (6.5.2)
  - [ ] Documentation updated: network diagram (1.2.3), data-flow diagram (1.2.4), system component inventory VNE-SEC-INV-001 (12.5.1), VNE-SEC-NET-001 if NSCs changed, VNE-SEC-CRY-001 if keys or cryptography changed, hardening standard (2.2)
  - [ ] Internal and external vulnerability scans after the change (11.3.1.3, 11.3.2.1)
  - [ ] Penetration test after a significant infrastructure or application upgrade or change (11.4.2, 11.4.3)
  - [ ] Segmentation testing if segmentation controls changed (11.4.5)
  - [ ] PCI DSS scope confirmation (12.5.2)


## Testing performed
<!--
  Describe the tests run in dev beyond the automated PR checks
  e.g. manual or integration testing, environments used, results.
  Include ZeroPath results and, for CDK changes, the CDK snapshot diff.
-->


## Rollback Plan
<!--
  How to revert this change if it causes problems in production.
  Name the method (e.g. revert PR and re-tag, k8s image revert to the previous tag,
  CDK revert, DB down-migration, RDS point-in-time recovery) and any data or ordering concerns.
-->


## Test Data Confirmation (CDE repos only)
<!-- CDE repositories: tick the box. Non-CDE repositories: leave unticked and write "N/A — non-CDE repository". -->
- [ ] I confirm no real account data, test credentials or test accounts exist in this change.
