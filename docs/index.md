---
title: Zammad Helpdesk — Overview
audience: technical
last_reviewed: 2026-07-26
---

# Zammad Helpdesk

This repository is AGM's fork of the upstream [zammad/zammad](https://github.com/zammad/zammad)
open-source helpdesk and customer support platform. It is kept as a **vanilla
mirror** — dependency updates are applied automatically via `updatecli`, and
AGM carries no local code patches on top of upstream `develop`. The purpose
of the fork is provenance and CI/build control, not customization.

The AGM-specific behavior (integrations, configuration, deployment) lives
outside this codebase, documented here.

## What this covers

- [Deployment](deployment.md) — where and how AGM runs Zammad, and the
  configuration this deployment overrides relative to upstream defaults.
- [3CX Integration](3cx-integration.md) — how call events from 3CX phone
  system reach Zammad as CTI tickets, via the companion
  [3cx-zammad-bridge](https://github.com/AGM-One-Vision/3cx-zammad-bridge)
  service.

## Where to look for everything else

Zammad's general user/admin documentation (agent workflows, triggers, SLAs,
channel setup, REST API reference) is upstream, not duplicated here:

- [docs.zammad.org](https://docs.zammad.org) — installation & admin manual
- [REST API reference](https://docs.zammad.org/en/latest/api/intro.html)
- [Developer manual](https://github.com/zammad/zammad/blob/develop/doc/developer_manual/index.md)

## System

Registered in DevHub under the [`zammad` System](https://devhub.agmegypt.com/catalog/default/system/zammad),
owned by the DTO group, alongside the `3cx-zammad-bridge` component.
