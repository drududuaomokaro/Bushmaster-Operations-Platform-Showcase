# BOP v1.0.0 Beta 1

**Release date:** 5 September 2026  
**Release stage:** Controlled beta testing  
**Production source milestone:** `e45dc89`

This is the first official Version 1 beta milestone for Bushmaster Operations
Platform. It is intended for controlled operational testing and is not the final
general-availability release.

## Highlights

- Governed ISP customer, billing, payment and subscriber-lifecycle operations
- MikroTik, FreeRADIUS and UISP integration with reconciliation evidence
- Customer self-service and Paystack invoice checkout
- Role-aware staff console with immutable operational audit history
- Sentinel AI operations assistant with role-governed authority
- Jerou Hospital staff self-service enrollment and editable network policies
- FreeRADIUS-backed captive-portal access
- Registered hospital-device, camera and access-point inventory
- Scoped EdgeRouter DHCP reservation and captive-enforcement synchronization
- Daily hospital-device usage, speed and data-cap controls

## Beta validation evidence

- 106 infrastructure tests passed for the release source
- Production application and gateway-sync services verified active
- 25 Jerou hospital-device reservations applied with no gateway errors
- Approved device traffic and unknown-device captive enforcement observed through
  live scoped-rule counters
- Deployment and captive activation protected by automatic rollback checks

## Beta boundaries

- The milestone remains subject to controlled user and network acceptance testing.
- Downstream Wi-Fi equipment must operate in access-point/bridge mode.
- Subscriber-impacting automation and outbound communications retain independent
  production interlocks.
- Camera inventory records identity and network state; it does not publish footage
  or private operational credentials.

## Path to stable v1.0.0

Stable release requires completion of the acceptance, security, recovery and
operator-runbook gates documented in [Beta status](PHASE_2_STATUS.md) and the
[roadmap](ROADMAP.md).
