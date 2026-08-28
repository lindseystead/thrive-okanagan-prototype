# Thrive Okanagan — Community Well-Being Intelligence Platform

## Interactive Prototypes

Prepared by **Lifesaver Technology Services Inc.** for **Thrive Okanagan / KGH Foundation**,
in support of the AWS Imagine Grant Canada 2026–2027, Round Two ("Go Further, Faster") technical
submission.

**Live site:** https://lindseystead.github.io/thrive-okanagan-prototype/

## What this repository contains

Two standalone, illustrative HTML/CSS/JS prototypes demonstrating the intake-to-insight mechanism
described in the Round Two Technical Design (Q4) and Implementation (Q5) answers:

| Prototype | Path | Description |
|---|---|---|
| **1. Scripted Demo** | [`docs/demo/index.html`](docs/demo/index.html) | A guided, click-through walkthrough of all four dashboard tiers: conversational AI intake, an organization's private dashboard, the de-identified regional gap view, and Thrive's full administrator view. |
| **2. Live, Freeform Prototype** | [`docs/live/index.html`](docs/live/index.html) | Accepts real free-text input, classifies it against the actual 16-goal Goals for Well-being Framework, and persists confirmed submissions to this browser's local storage so the regional view grows as you test it. |

Both are self-contained, dependency-free HTML files — no build step, no server, no framework.
Each file's own header comment documents its purpose, its known limitations, and which section of
the real architecture it stands in for.

## What these prototypes are, and are not

**They are:** a working demonstration of the confirmation-gate control loop (AI proposes, a human
confirms, only then is anything saved) and the four-tier dashboard visibility model (organization,
organization-vs-region, regional public view, Thrive administrator) described in the Technical
Design.

**They are not:** a connection to the real production system. Neither file calls Amazon Bedrock,
Amazon Cognito, or Amazon Aurora — that isn't possible from a static, client-side page. Where the
real system would call AWS services, these prototypes use a transparent, client-side stand-in
(a keyword classifier for Bedrock's role, browser local storage for Aurora's role), documented as
such directly in the code.

All organization names and program data appearing on load are **sample data**, not real pilot
submissions. Any data you enter while testing this prototype stays in your own browser's local
storage and is never transmitted anywhere.

## Code organization

Each HTML file is organized into clearly labeled sections, marked with banner comments:

```
1. Design Tokens         — color, type, light/dark theme variables
2. Masthead              — page identity and demo-data disclosure
3. Step Navigation       — switches between the four dashboard tiers
4–7. Tier 1–4            — one section per dashboard tier's markup and styles
Script Section A–H       — one section per JavaScript concern (navigation,
                            classification, persistence, and one renderer
                            per dashboard tier)
```

## Real sources this prototype is grounded in

- Thrive Okanagan Goals for Well-being Framework, Summary Report (4 environments, 16 goals,
  indicator category definitions — used verbatim in the classifier's keyword sets)
- Thrive Okanagan Goals for Well-being Framework, Pilot Partner 3.0 Mapping Form (real field names
  and structured option lists: age bands, priority populations, cost structure, access method)
- Real June 2026 pilot data pattern (Health and Social Care as the highest-concentration
  environment, Economic and Work at zero programs) — used to calibrate the demo's illustrative
  baseline counts, not presented as live reported figures

## License and ownership

Delivered to Kelowna General Hospital Foundation (on behalf of Thrive Okanagan) under Statement of
Work LS-SOW-2026-01. Ownership of these files transfers to KGH Foundation upon full payment, per
Section 8 of that agreement.
