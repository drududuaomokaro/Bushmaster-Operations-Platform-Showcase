# Phase 2 controlled-acceptance status

**Status date:** 25 August 2026

This document separates implemented product capability from production
activation. A feature can be deployed and testable while its real-world effect
remains intentionally disabled until the related acceptance evidence is
complete.

## Operational and under acceptance

- Staff operations console with role-aware access and audit history
- Customer, plan, Internet-service and PPPoE provisioning records
- MikroTik, FreeRADIUS and UISP visibility for authorized staff
- Automated billing, invoice generation and payment allocation
- Isolated customer portal and Paystack checkout
- UISP/Mapbox network map and subscriber traffic correlation
- Consent-aware billing-reminder scheduler and notification evidence ledger
- BulkSMSNigeria sandbox delivery path

## Deployed but fail-closed

### Live customer communications

- **SMS:** the provider adapter is deployed; live transmission awaits
  BUSHMASTER sender-ID approval and a controlled pilot.
- **WhatsApp:** the Meta Cloud API adapter is deployed; transmission awaits a
  production token, registered phone-number ID, approved utility template and
  a controlled pilot.
- **Email:** the Brevo adapter is deployed; transmission awaits a verified
  sender, production credential and a controlled pilot.

Every channel requires explicit customer consent. Existing preference records
do not gain email consent automatically. Channel switches and a global reminder
switch must all be enabled before a provider request can be transmitted.

### Subscriber enforcement

Billing reminders do not suspend subscribers and do not modify MikroTik or
FreeRADIUS. D-3 through D+3 messages are communication milestones; an unpaid
account becomes an operator-visible candidate after the grace period.

Live subscriber disconnection remains a separately governed capability. It must
stay disabled until paying subscribers have verified PPPoE topology bindings,
the pilot proves suspend/disconnect/restore/rollback behaviour, and production
approval is recorded.

## Phase 2 exit gates

- Complete and verify every paying-subscriber access binding
- Finish provider pilots and opt-out acceptance for all communication channels
- Rehearse backup, deployment and rollback procedures
- Confirm security and operational runbooks are current
- Resolve Critical and High security findings
- Record explicit production approval for subscriber-impacting automation

The v1.0.0 release will be created only after these gates are complete.
