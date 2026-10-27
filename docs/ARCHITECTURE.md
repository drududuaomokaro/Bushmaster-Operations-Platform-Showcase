# BOP high-level architecture

Bushmaster Operations Platform (BOP) is a governed ISP Operations Support System /
Business Support System (OSS/BSS).

## System boundary

```text
Staff Operations Console                 Customer Self-Service Portal
          |                                          |
          +------------------+-----------------------+
                             |
                  Identity and Permission Layer
                             |
             Workflow, Billing and Notification Engine
                             |
       +---------------------+---------------------+
       |                     |                     |
   MikroTik              FreeRADIUS              UISP
gateway/PPPoE       authentication/accounting   device plane
       |                     |                     |
       +---------------- Subscriber Network -------+

External business services:
  Flutterwave | BulkSMSNigeria | Meta WhatsApp Cloud API | Brevo | Mapbox
```

## Jerou Hospital access plane

```text
Jerou staff and devices
          |
   Ruijie / bridged APs
          |
 EdgeRouter switch0 (LAN10)
    |                 |
registered MACs    unknown/staff devices
DHCP exemption     captive redirect
    |                 |
 Internet        BOP portal + FreeRADIUS
```

BOP publishes signed desired state to a scoped gateway synchronizer. The
synchronizer manages only BOP-owned DHCP reservations and firewall chains;
camera, subscriber and unrelated router rules remain outside its authority.

## Authority model

- BOP is the customer, billing, provisioning and automation authority.
- MikroTik is the gateway, PPPoE server and subscriber-enforcement plane.
- FreeRADIUS is the authentication, authorization and accounting authority.
- UISP is the Ubiquiti hardware-monitoring plane and an import source; it is not
  the billing-enforcement plane.
- Flutterwave confirms customer payments through independently verified callbacks,
  signed webhooks and transaction-API verification.
- Notification channels are independent adapters behind consent checks, an
  idempotent evidence ledger and fail-closed transmission switches.

## Health and firmware control plane

```text
UISP and system telemetry
          |
  Thirty-minute deep-health engine
          |
 findings + recommendations + guarded repairs
          |
  operator email and immutable audit evidence

UISP firmware inventory
          |
 device selection + preflight + policy-conflict check
          |
 serial update + reconnect verification
```

Health automation acts only on approved, reversible failure classes. Firmware
updates remain supervised and exclude devices that are offline or fail preflight.

## Sentinel and Pegasus assistance plane

Sentinel combines typed and voice interaction with BOP-aware context, role checks,
trusted-device checks and confirmation gates. Pegasus is a lightweight Android
companion that keeps common commands and prompts offline, stores large assets on
USB where available, and securely pairs to BOP for extended functions.

## Architectural principles

- Governed subscriber lifecycle operations
- Verification before completing infrastructure state transitions
- Rollback after failed infrastructure changes
- Separation of business rules from infrastructure and delivery providers
- Least-privilege infrastructure access
- Explicit per-channel customer consent
- Idempotent billing, payments and communications
- Independent safety interlocks for outbound messaging and network enforcement
- Auditability and traceability
- Dedicated pilot validation before production-impacting rollout
- Per-device identity visibility through access-point/bridge network topology
- Role-governed AI assistance through Sentinel

## Subscriber lifecycle

```text
PENDING -> PROVISIONED -> ACTIVE
ACTIVE  -> SUSPENDED   -> ACTIVE
ACTIVE  -> TERMINATED
```

Payment and reminder processing never silently changes this lifecycle. A due
account becomes operator-visible first; network enforcement is a separate,
governed workflow with its own production interlock.

## Source code

The production implementation is maintained in a private repository. This
public repository documents the platform architecture, development progress,
product capabilities, screenshots and roadmap without publishing proprietary
source code or operational secrets.
