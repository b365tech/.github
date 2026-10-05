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
  - project work → ClickUp task, e.g. https://app.clickup.com/t/86xxxxxxx
  - operational change → help desk ticket, e.g. a Freshservice or Jira Service Management ticket URL
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
  If YES: link the post-change confirmation ticket (ClickUp or help desk) and tick every item below to confirm
  it is covered by that ticket. Where an item does not apply, record "N/A" and the reason
  in the ticket, then tick it here.
-->
- [ ] **No** — this is not a significant change.
- [ ] **Yes** — this is a significant change.
  - Post-change confirmation ticket:
  - [ ] Applicable PCI DSS requirements confirmed in place on all new or changed systems and networks (6.5.2)
  - [ ] Documentation updated: network diagram (1.2.3), data-flow diagram (1.2.4), system component inventory (12.5.1), hardening standard and primary functions (2.2)
  - [ ] Internal and external vulnerability scans after the change (11.3.1.3, 11.3.2.1)
  - [ ] Penetration test after a significant infrastructure or application upgrade or change (11.4.2, 11.4.3)
  - [ ] Segmentation testing if segmentation controls changed (11.4.5)
  - [ ] PCI DSS scope confirmation (12.5.2)


## Testing performed
<!--
  Describe the tests run in dev beyond the automated PR checks
  e.g. manual or integration testing, environments used, results.
-->


## Rollback Plan
<!--
  How to revert this change if it causes problems in production.
  Name the method (e.g. revert PR and re-tag, k8s image revert to the previous tag,
  CDK revert, DB down-migration, RDS point-in-time recovery) and any data or ordering concerns.
-->


## Test Data Confirmation (CDE repos only)
<!-- CDE repositories: tick the box. Non-CDE repositories: leave unticked and write "N/A — non-CDE repository". -->
- [ ] I confirm no real CHD or test credentials exist in this change.
