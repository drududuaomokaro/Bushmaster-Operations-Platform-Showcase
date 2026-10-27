# Version 1 controlled-production status

**Status date:** 27 October 2026

**Milestone lineage:** `v1.0.0-beta.1`

This document separates implemented product capability from unrestricted
automation. BOP is used in a controlled production environment, while actions
that affect subscribers, firmware or external communications retain independent
gates, verification and audit evidence.

## Operational in the controlled production environment

- Staff operations console with role-aware access and audit history
- Customer, plan, Internet-service and PPPoE provisioning records
- MikroTik, FreeRADIUS and UISP visibility for authorized staff
- Automated billing, invoice generation and payment allocation
- Isolated customer portal and verified Flutterwave v3 checkout
- UISP/Mapbox network map and subscriber traffic correlation
- Consent-aware billing-reminder scheduler and notification evidence ledger
- Production SMS and email delivery with consent and evidence controls
- Jerou Hospital staff identity enrollment and editable access policies
- FreeRADIUS-backed staff captive-portal authentication
- Governed hospital-device and camera registration
- Verified EdgeRouter LAN10 DHCP reservations
- Captive access for unknown hospital-network devices, with approved-device exemptions
- Role-governed Sentinel AI operations assistance
- Guided subscriber provisioning, access-binding and activation gates
- Deep-health reporting and guarded thirty-minute self-healing
- Supervised UISP firmware updates with explicit device selection
- Lightweight Pegasus Sentinel Android companion

## Controlled and fail-closed boundaries

### Customer communications

- **SMS and email:** available through independently configured production adapters.
  Delivery requires explicit consent, enabled channel switches and an idempotent evidence record.
- **WhatsApp:** implemented as an optional adapter requiring Meta production
  credentials, a registered number and an approved utility template.

Every channel requires explicit customer consent. Existing preference records
do not gain email consent automatically. Channel switches and a global reminder
switch must all be enabled before a provider request can be transmitted.

### Subscriber enforcement

Subscriber disconnection remains separate from reminder delivery. An unpaid
invoice cannot suspend service until the configured grace period has expired,
the final notice is recorded, the PPPoE access binding is enforceable and the
independent production switches permit the action. Payment restoration follows
the same verified, audited workflow.

### Self-healing and firmware operations

Deep-health automation may repair only approved, reversible failure classes.
Other findings become operator recommendations. Firmware work requires explicit
device selection, online/preflight evidence, serial execution and reconnect
verification. Conflicting UISP native or beta policies pause BOP's firmware worker.

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
