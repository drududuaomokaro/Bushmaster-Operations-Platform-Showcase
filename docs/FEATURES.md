# Complete BOP feature catalogue

**Status date:** 27 October 2026
**Scope:** public product description; no credentials, customer data or private
infrastructure details are included.

Bushmaster Operations Platform (BOP) is a governed OSS/BSS for wireless Internet
service providers and managed network environments. Capabilities are grouped as
**production**, **controlled** or **optional integration** so implementation is
not confused with unrestricted automation.

## Subscriber and customer operations

- Customer records, service history, installation and billing addresses
- Standard, complimentary and unlimited service-plan governance
- Internet-service records with station, access VLAN and PPPoE identities
- Customer-specific lifecycle states and activation readiness
- Searchable customer and service consoles
- Secure customer portal activation, login and invoice access
- Communication preferences and explicit per-channel consent
- Role-aware staff access, profile administration and password controls

## Guided subscriber provisioning

- New-customer and existing-customer provisioning workflows
- Step-by-step progress page for field and operations staff
- Device naming and station assignment
- Available VLAN allocation and subscriber access binding
- PPPoE username and generated credential handling
- MikroTik subscriber-edge preparation
- FreeRADIUS and MikroTik cross-system execution
- Credential-installation and Layer-2 bypass-prevention evidence
- Activation gate that blocks incomplete or unsafe cutovers
- Provision, activate, suspend, restore and terminate jobs
- Verification, retry, rollback evidence and detailed job outcomes
- Installation guide with router and station configuration details

## Authentication and subscriber enforcement

- FreeRADIUS authentication, authorization and accounting
- MikroTik PPPoE server and active-session integration
- Per-plan RADIUS groups and MikroTik profiles
- Subscriber VLAN isolation and PPPoE-only access controls
- Calling-Station-Id and managed-router binding
- Governed active-session disconnect, suspension and restoration
- Independent production safety interlocks and access-readiness checks

## Billing, payments and communications

- Automated monthly billing cycles and customer-specific renewal days
- Invoice creation, issue, cancellation, overdue and payment states
- Installation and recurring-subscription line items
- Manual payment recording, confirmation, allocation and reversal
- Flutterwave v3 Standard customer checkout
- Independently verified callback and signed webhook handling
- Transaction-reference and provider-transaction idempotency
- Customer invoice and payment history in the self-service portal
- SMS, WhatsApp and email provider adapters
- Consent-aware D-3, due-date and D+1 through D+3 reminders
- Three-day grace handling and final-notice evidence
- Governed automatic suspension after grace and automatic restoration after payment
- Per-customer holds, due-day overrides and auditable exceptions

## Network operations and visibility

- Operations dashboard for MikroTik, FreeRADIUS and UISP health
- Ubiquiti device inventory, topology, association and telemetry views
- Device detail pages with Ethernet, RF, capacity and firmware evidence
- Correct interpretation of access points with no associated stations
- Stale-telemetry detection instead of false healthy/offline reporting
- Subscriber-session, traffic and accounting correlation
- Customer/service reconciliation and mapping approval
- UISP/Mapbox network map with device locations and ground imagery
- Governed UISP monitoring recovery tools
- Domain-retirement and certificate-renewal safeguards

## Deep health and self-healing

- Scheduled thirty-minute infrastructure health assessments
- Deep device and system health findings beyond simple online/offline state
- Ethernet negotiation, wireless capacity, signal and firmware diagnostics
- Corrective recommendations, including cable, PoE, alignment and replacement advice
- Guarded automatic repair for approved, reversible failure classes
- Before/after evidence and explicit success or failure results
- Superuser email reporting for detected incidents and repair outcomes
- Suppression of misleading RF findings when an access point has no client station

## Controlled Ubiquiti firmware operations

- Firmware inventory and compatible-update visibility
- Explicit device selection before an update run
- Offline-device exclusion and preflight checks
- Serial, supervised updates rather than an uncontrolled fleet-wide blast
- Backup, reconnect and post-update verification gates
- Conflict detection for UISP native updater and beta-firmware policies
- Audited pause, resume and operator-visible outcomes

## Sentinel AI operations assistant

- Typed and voice conversations inside the BOP console
- Wake-word and push-to-talk interaction modes
- BOP-aware operational context and governed tool access
- Role and trusted-device checks before privileged assistance
- Fast-response voice-session lifecycle and reconnect handling
- Approved learning, memory and operator lessons
- Budget-aware reasoning and bounded external-AI use
- Provisioning guidance and confirmation-oriented workflow assistance
- Clear separation between advice, preview and production execution

## Pegasus Sentinel Android companion

- Lightweight Android companion for vehicle and field consoles
- Offline common commands and cached spoken prompts
- USB-first workspace for large assets on storage-constrained devices
- Local media and volume controls
- Secure pairing with BOP Sentinel for extended online functions
- Trusted-device enrollment and scoped public endpoints
- Signed application/update metadata and compact incremental-update support

## Surveillance operations

- Governed surveillance probe registration
- Rotatable probe tokens and scoped configuration delivery
- Camera/device identity, reachability and health reporting
- Editable governed inventory without exposing footage or credentials
- Operational recommendations for unhealthy or missing devices

## Jerou managed-access plane

- Staff self-service Wi-Fi enrollment
- FreeRADIUS-backed staff credentials
- Departments, access policies, speed profiles and data quotas
- Captive access for unknown devices
- Registered-device DHCP reservations and captive exemptions
- Governed IoT, camera, computer and access-point inventory
- Device presence, session and daily-usage monitoring
- Session revoke, suspend, restore and approval workflows
- Attendance terminals, shifts, rosters and manual attendance events
- Scoped gateway-policy publication and reconciliation
- Signed desired state and least-privilege gateway synchronization

## Governance, security and resilience

- Role-based access and write permissions
- CSRF, trusted-host and domain-policy enforcement
- Immutable operational audit evidence
- Fail-closed provider and infrastructure switches
- Idempotent jobs, reminders, payments and callbacks
- Scoped credentials and separation of infrastructure authority
- Health, deployment, backup and rollback checks
- Legacy-domain retirement guards and automated certificate renewal

## Capability status

| Status | Meaning |
| --- | --- |
| Production | Used in the controlled live BOP environment with audit and safety gates. |
| Controlled | Implemented but requires explicit operator selection, confirmation or acceptance evidence. |
| Optional integration | Requires an independently configured provider account, credential or approval. |

Production source remains private. This showcase documents the product without
publishing customer information, credentials, private addresses or proprietary
implementation details.
