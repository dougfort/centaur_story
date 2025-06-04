# Simulated Ecosystem Management Game – Mechanics Overview

---

created: '2025-06-04'
title: "Simulated Ecosystem Management Game \u2013 Mechanics Overview"
type: reference
version: v1.0

---

**Purpose:**  
Teach child–assistant teams to coordinate complex resource allocation and species interactions in a simulated biome. Emphasizes sustainability, strategic planning, and human–AI collaboration.

## Core Resources

| Resource            | Description                                       | Effects if Mismanaged                         |
|---------------------|---------------------------------------------------|-----------------------------------------------|
| Water (💧)          | Available hydration for plants and wildlife       | <20% → vegetation wilts, wildlife health drops |
| Nutrients (🪨)      | Soil fertility index                              | <30% → plant growth slows, erosion increases   |
| Species Diversity (🐾) | Number of distinct flora and fauna populations     | <40% → ecosystem collapses baseline dynamics   |
| Pollution (☣️)      | Contaminant level affecting all resources          | >50% → immediate health drop across biome      |
| Predator/Prey Balance (⚖️)| Ratio of predator to prey populations             | Imbalance → population crashes/rabbits proliferate |

## Core Actions (Macros)

| Shorthand      | Action Description                                                   | Cool-Down |
|----------------|----------------------------------------------------------------------|-----------|
| **Rainfall**   | Simulate 10 mm of rain spread evenly across biome                     | 15 s      |
| **Fertilize**  | Disperse 5 units of nutrient pellets to key regions                    | 20 s      |
| **Reintroduce**| Add a small group (3 individuals) of a chosen species                   | 30 s      |
| **Clean-Up**   | Deploy micro-bots to reduce pollution by 10%                           | 25 s      |
| **HabitatEdit**| Alter terrain to create new habitat zones (e.g., ponds, meadows)        | 45 s      |

Children and AI can collaboratively define new macro combos after initial tutorial. Assistant confirms resource impact before execution.

## Environmental Stressors (Escalation Ladder)

1. **Drought Event** – Random water -15% over 20 s.
2. **Pest Outbreak** – Random pest increase affecting plant health by -20%.
3. **Pollution Spike** – Industrial runoff adds +20% pollution over 15 s.
4. **Wildfire Simulation** – Temporary -30% vegetation health in one region.
5. **Invasive Species** – New species introduced disrupting predator/prey balance.

Stressors activate in increasing frequency as biodiversity and sustainability scores remain above thresholds for sustained periods.

## AI Roles and Interaction

- **Resource Advisor:** Suggests optimal actions based on current resource levels and expected stressor trends.
- **Risk Assessment:** Calculates potential outcomes (e.g., “Rainfall now may flood lowlands”).
- **Predictive Modeling:** Provides short-term forecasts for species populations based on current trajectory.
- **Macro Recording:** Learns children’s custom macros, optimizing naming and parameters for re-use.

AI logs all suggestions and calculates confidence levels; children choose whether to accept or adjust based on intuition.

## Metrics Logged

* Resource trajectories sampled at 1 Hz (water, nutrients, pollution levels).
* Population counts for each species (flora and fauna).
* Command latency (child speech → action applied).
* AI suggestion count and acceptance rate.
* Stressor response time (seconds until corrective action).
* Policy flags (e.g., unsafe macro parameters or extreme risk scores).

## Success Thresholds

* **Lesson Level:** Maintain water ≥40%, nutrients ≥50%, and species diversity ≥50% for 5 minutes.
* **Showcase Level:** Achieve sustainability index ≥80% (composite of resources and diversity metrics) for 10 minutes under continuous stressor cycles.
* **Expert Level:** Stabilize ecosystem long-term (20 minutes) while innovating at least three new macro combos without AI prompts.

## Notes for Future Modules

- Consider adding **Climate Change Simulation**: gradual temperature increase requiring adaptive strategies.
- Extend to **Real-World Correlation**: map player decisions to city green-space planning in simplified overlays.
- Integrate **Citizen Science Data**: import local wildlife observations to seed the simulation with real data.
