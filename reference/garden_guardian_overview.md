# Garden Guardian – Centaur Pilot Game

## Background

---

created: '2025-05-30'
title: "Garden Guardian \u2013 Mechanics Overview"
type: reference
version: v1.0

---

**Purpose:** Teach child–assistant pairs to coordinate rapid decisions under gentle pressure, without peer competition.

## Core Resources

| Bar | What it Represents | Effects if Low |
|-----|--------------------|----------------|
| Leaf Health (🌿) | Aggregate plant vigor | <40 % → leaves wilt, garden loses 5 %/tick |
| Pollen (🐝) | Bee activity & flower fertility | <50 % → fruit yield halved |
| Moisture (💧) | Soil water content | <25 % → accelerated wilting |
| Aphid Load (🐛) | Pest pressure | >70 % → Leaf Health drops 2 %/tick |

## Standard Child Commands

| Shorthand | Action Bundle | Cool‑Down |
|-----------|---------------|-----------|
| **Quick‑Sip** | Water 15 mL targeted at driest grid | 10 s |
| **Ladybug Scout ×N** | Release N bugs; each lowers aphid by 5 % | none |
| **Warm‑Sun β** | Solar lamp +12 W for 6 s | 15 s |
| **Bee‑Boost** | Deploy 3 micro‑bees; pollen +7 % | 12 s |

Children invent shorthands; assistant confirms on first use, stores macro mapping.

## House AI Escalation Ladder

1. **Heat Wave** – Air temp +5 °C for 20 s.
2. **Aphid Swarm** – Aphid +25 %.
3. **Cloud Cover** – Light −50 % for 15 s.
4. **Weed Shadow** – Random weed lowers received light in one grid.

Difficulty rises when centaur keeps all bars ≥80 % for 60 s.

## Metrics Logged

* Command latency (child speech → action applied)
* Assistant guidance prompts count
* Bar trajectories sampled at 1 Hz
* Policy flags (vocabulary, emotional spikes)

## Success Thresholds

* Lesson level: maintain Leaf Health ≥80 % for 3 minutes
* Showcase level: maintain all bars ≥90 % for 5 minutes under full ladder
