---
layout: post
title: "Walking through smoke"
lead: "Talk at the Visibility Seminar 2026 in Wuppertal."
description: "Slides and a short clip from my talk on a modular workflow for visibility-aware evacuation modelling with pyFDS-Evac, given at the Visibility Seminar 2026, University of Wuppertal."
thumb: /images/notes/2026-09-visibility-seminar/smoke-exit-choice.gif
---

Today I gave a talk at the Visibility Seminar 2026 at the University of Wuppertal: *A Modular Workflow for Visibility-Aware Evacuation Modelling*.

The workflow is pyFDS-Evac. It couples FDS, fdsreader, fdsvismap and JuPedSim, so that smoke from a fire simulation affects how agents walk and which exits they choose.

<figure>
  <img src="/images/notes/2026-09-visibility-seminar/smoke-exit-choice.gif" alt="Agents leaving a generated world with four exits while smoke spreads; agents are coloured by their speed factor" loading="lazy">
  <figcaption>A coupled FDS run on a generated world with four exits. Background: smoke extinction coefficient at 2 m. Dots: agents, coloured by the speed factor they experience in the smoke.</figcaption>
</figure>

The slides are online: [Visibility Seminar 2026](https://pedestriandynamics.org/pyFDS-Evac/talks/visibility-seminar-2026).
