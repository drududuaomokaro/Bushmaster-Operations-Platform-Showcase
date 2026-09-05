# Version 1 beta-testing status

**Status date:** 5 September 2026

**Milestone:** `v1.0.0-beta.1`

This document separates implemented product capability from production
activation. A feature can be deployed and testable while its real-world effect
remains intentionally disabled until the related acceptance evidence is
complete.

## Operational and under beta acceptance

- Staff operations console with role-aware access and audit history
- Customer, plan, Internet-service and PPPoE provisioning records
- MikroTik, FreeRADIUS and UISP visibility for authorized staff
- Automated billing, invoice generation and payment allocation
- Isolated customer portal and Paystack checkout
- UISP/Mapbox network map and subscriber traffic correlation
- Consent-aware billing-reminder scheduler and notification evidence ledger
- BulkSMSNigeria sandbox delivery path
- Jerou Hospital staff identity enrollment and editable access policies
- FreeRADIUS-backed staff captive-portal authentication
- Governed hospital-device and camera registration
- Verified EdgeRouter LAN10 DHCP reservations
- Captive access for unknown hospital-network devices, with approved-device exemptions
- Role-governed Sentinel AI operations assistance

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

### Jerou Hospital network pilot

Jerou captive access is enabled for unknown devices entering through the governed
EdgeRouter LAN. Registered cameras, access points, computers and other approved
equipment receive governed DHCP reservations and bypass staff authentication.
Staff devices must be enrolled and authenticate through FreeRADIUS.

The beta requires downstream wireless routers to operate in access-point/bridge
mode. NAT/router mode hides individual client identities and is therefore not an
accepted production topology.

## Final v1.0.0 exit gates

- Complete and verify every paying-subscriber access binding
- Finish provider pilots and opt-out acceptance for all communication channels
- Rehearse backup, deployment and rollback procedures
- Confirm security and operational runbooks are current
- Resolve Critical and High security findings
- Record explicit production approval for subscriber-impacting automation
- Complete the Jerou staff enrollment and reconnect/suspension acceptance exercises
- Confirm all downstream hospital wireless equipment uses bridge/AP mode

The stable `v1.0.0` release will be created only after these beta gates are complete.
