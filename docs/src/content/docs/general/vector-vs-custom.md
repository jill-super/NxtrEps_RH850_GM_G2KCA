---
title: "Third-party versus in-house code"
description: "How to tell vendor code from project code."
---
## Policy

- **Vector-provided** modules are third-party communication-stack deliveries (driver sources, interaction layer, transport protocol, network management, diagnostic addon, memory stack parts, operating system, state managers, calibration protocol, DaVinci and GENy tooling). Treat them as read-only; changes belong in configuration, not in delivered sources.
- **Renesas-provided** modules are microcontroller vendor drivers for the RH850 family.
- **Custom (in-house)** modules are project-developed control and integration logic. Many of them contain a small amount of Vector-generated Runtime Environment scaffolding (component templates, contracts, memory-mapping headers produced by the MICROSAR generator). Each affected page says so explicitly: the algorithm is in-house, the scaffolding is generated.

## How origin was determined

Origin follows the copyright and generator banners in the sources: Vector Informatik banners mark vendor deliveries, Renesas Electronics banners mark vendor drivers, and Nexteer banners (plus the absence of vendor banners in the hand-written files) mark in-house code. Generator banners naming the MICROSAR Runtime Environment Generator, DaVinci, or GENy mark generated scaffolding even inside in-house folders.

## Practical rules

1. Never hand-edit files whose header names a vendor generator; regenerate instead.
2. Keep calibration and network databases in their tool projects (DaVinci, GENy) rather than copying values into code.
3. When a custom component wraps a vendor driver, the wrapper page names the wrapped peripheral and the vendor module it configures.
