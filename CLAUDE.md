# Business Ambitions — chraibi.de

Source: org-roam note `20260510212411-business_frei.org` ("Business Frei", stage: Ausgruenden).

## Goal

Build an independent **freiberufliche wissenschaftlich-technische Beratung** alongside employment — without using the employer's resources, time, or name. Treat `chraibi.de` as the public expert brand; add a `/consulting` (or `/beratung`) page rather than a separate site.

## Positioning

> Scientific and technical consulting for pedestrian dynamics, crowd simulation, evacuation analysis, and JuPedSim-based workflows.

Not "freelance developer." The commercial core is **scientific expertise**, not generic software work.

## Brand Identity

- Name: **Mohcine Chraibi — Scientific Simulation Consulting**
- Email: `consulting@chraibi.de` (active). Never the FZJ address.
- Disclaimer required on consulting pages: *"Independent consulting by Mohcine Chraibi. No institutional endorsement implied."*
- Tone: expert/personal, not corporate. Keep the research credibility (JuPedSim author, 15+ years, publications) front and center.

## Services (four core offerings)

1. **Pedestrian Simulation Audit** — independent review of models, assumptions, calibration, reproducibility, interpretation.
2. **JuPedSim Consulting** — workflows, Python scripting, scenario setup, analysis, integration.
3. **Training & Workshops** — JuPedSim, pedestrian dynamics, evacuation, reproducible workflows.
4. **Simulation Tool Prototyping** — web-based prototypes, dashboards, custom analysis tools.

## Target Customers

Research institutes, universities, planning/engineering offices, mobility companies, event and infrastructure operators, software teams in the simulation space.

## Pricing (net)

| Package             | Price                |
|---------------------|----------------------|
| Expert Call         | 350 €                |
| Mini Audit          | 1.500–2.500 €        |
| Simulation Audit    | 2.900–4.900 €        |
| JuPedSim Workshop   | 3.000–6.000 €        |
| Technical Discovery | 2.000–4.000 €        |
| Prototype Sprint    | 6.000–15.000 €       |
| Retainer            | 2.000–6.000 €/month  |

Hourly: 140–250 €/h depending on type; workshop day 1.500–2.500 €/day. Prefer fixed packages over pure hourly.

## Tax & Legal Setup

- German *Freiberufler* (wissenschaftlich-technisch), EÜR — no double-entry bookkeeping.
- **Regelbesteuerung** (not Kleinunternehmer) — B2B clients, Vorsteuerabzug, scalable.
- Three-layer liability protection: (1) tight contracts with scope/assumption/liability caps, (2) Berufshaftpflicht/Vermögensschadenhaftpflicht covering IT, technical consulting, simulation, (3) explicit scope control per project — simulations are decision support, not safety guarantees.

## Website Implications (this repo)

Structure to aim for:

```
chraibi.de
├── Home / About
├── Research
├── Projects
├── Publications / Talks
├── Consulting
│   ├── Pedestrian Simulation Audit
│   ├── JuPedSim Training
│   ├── Simulation Tool Prototyping
│   └── Technical Advisory
└── Contact
```

Current branch `consulting-page` is drafting `consulting.md`. The page must:

- Use English (international audience).
- Show concrete services + who they are for + example engagements.
- Carry the employer-separation disclaimer.
- Use the `consulting@chraibi.de` address — never the FZJ address.
- Stay an *expert profile* page; do not turn `chraibi.de` into an aggressive sales site.

## Competitor Reference: beyondsimulations.com

Hamburg-based boutique consultancy (single founder, network via Hamburg Analytics). Useful comparison point.

- **Breadth play, not depth**: OR + simulation + ML + dashboards. Tagline pattern: "when off-the-shelf software gives up." Our counter-position is **depth in pedestrian dynamics + JuPedSim authorship**.
- **Project-as-storefront**: lists named engagements (Crowd Management Platform for 1M+ pilgrimage with desior GmbH, FIFA 2022 Doha crowd movement, warehouse optimization with Planningio GmbH, library routing) as credibility anchors. No prices, no service packages — clients contact to scope.
- **Crowd Management Platform** is the closest overlap with `app.jupedsim.org`, but presented as a *case study delivered with a partner GmbH*, not as a product. He carries no platform/liability load alone.
- **Interactive demos** on his site work well; for our case a YouTube embed of the JuPedSim App is sufficient (we already have recorded material).
- **Partnership pattern worth noting**: for platform-style offerings, delivering *through* a GmbH partner keeps the Freiberufler scope clean and offloads operational/liability concerns.

## Roadmap (in order)

1. Clarify Nebentätigkeit with employer.
2. Finalize Tätigkeitsbeschreibung.
3. ELSTER-Fragebogen.
4. Decide Regelbesteuerung vs. Kleinunternehmer (→ Regelbesteuerung).
5. Separate bank account.
6. Berufshaftpflicht.
7. Invoice + offer/contract templates.
8. Extend landing page (this repo, `/consulting`).
9. Define first concrete offer package.
10. Identify 10–20 potential contacts.
11. Land first paid audit or workshop.
