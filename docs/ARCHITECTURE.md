# BOP High-Level Architecture

Bushmaster Operations Platform (BOP) is designed as a governed ISP Operations Support System / Business Support System (OSS/BSS).

## Core Architecture

Operations Console
        |
        v
Provision Jobs
        |
        v
Workflow Engine
        |
        +-- MikroTik
        |
        +-- FreeRADIUS
        |
        +-- UISP
        |
        v
Subscriber Network

## Architectural Principles

- Governed subscriber lifecycle operations
- Verification before state transition completion
- Rollback after failed infrastructure changes
- Separation of business logic from infrastructure providers
- Least-privilege infrastructure access
- Auditability and traceability
- Dedicated test-subscriber validation before production rollout

## Subscriber Lifecycle

PENDING -> PROVISIONED -> ACTIVE

ACTIVE -> SUSPENDED -> ACTIVE

ACTIVE -> TERMINATED

## Source Code

The production implementation of Bushmaster Operations Platform is maintained in a private repository.

This public repository documents the platform architecture, development progress, product capabilities, screenshots, and roadmap without publishing proprietary source code.

