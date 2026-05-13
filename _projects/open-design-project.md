---
layout: project
title: Open Design Project
description: Spotted Lantern Fly Solution
technologies: N/A
image: /assets/images/slf.jpg
---

# SLF Mechanical Repellant from Grape Harvester

**Team:** Lanternfly Killers  
**Client(s):** Cornell CALS Extension / E&J Gallo Winery / National Grape  

---

## Table of Contents

- [Client Pitch](#client-pitch)
- [Functional Prototype](#functional-prototype)

---

## Client Pitch {#client-pitch}

### Problem Statement

Just 1–2 adult spotted lanternflies (SLF) can taint a kilogram of grape slurry. With how prevalent they are in vineyards, this contamination adds up rapidly. Farmers are searching for ways to manage the SLF population without diminishing crop yield. One key entry point is the harvester itself — SLFs present on the vines can enter the machine during harvest. Finding a way to remove flies from the vines as the harvester intakes grapes is critical to preventing crop contamination.

### Impact

Reducing the number of SLF present in the crop yield would benefit the entire supply chain. Farmers would benefit financially as less crop would be discarded due to contamination. Consumers and businesses would benefit from the resulting reduction in scarcity and cost of grape products.

### Proposed Directions

#### Concept A: Blower

A system of devices attached to the front of the harvester that blows SLF off the vines before they can enter the machine — similar in principle to the drying stage of a car wash, but calibrated to dislodge insects without damaging fruit.

**How it would be used:**
- Mounted in front of the harvester, pointing outward toward the grape vines
- A fan produces a steady airstream toward the vines, causing SLF to fly outward
- The continuous airflow also prevents SLF from flying back into the harvester after leaving the vine

**Why it's better than the status quo:**
- Avoids chemical deterrents that risk contaminating the crop
- Physically displaces insects rather than simply deterring them

#### Concept B: Vibration Attraction Device

A set of vibrating towers placed around the field to attract SLF toward liquid chemical traps.

**How it would be used:**
- Towers with mechanical vibration devices operating at 60 Hz to attract SLF
- An electrified outer cage shocks SLF on contact
- A container below catches insects for easy removal

**Why it's better than the status quo:**
- Eliminates SLF year-round without continuous spraying
- Requires no modifications to the harvester; one-time purchase rather than a recurring cost

### Key Risks and Unknowns

- **Damage to grapes/vines** — Test by measuring how much wind force store-bought grapes can sustain before detaching from the vine.
- **Lanternflies getting stuck in the blower** — Test different blower geometries to ensure clear passage.
- **Insufficient blower force** — Weigh lanternfly samples and measure grip force to calculate the wind force required for removal.

### Questions for the Client

1. **Do SLF tend to stay on the vine when grapes are being removed?**  
   *Decision affected:* This would influence blower design — we would need to prototype carefully to ensure the airflow removes SLF without also dislodging grapes.

2. **If SLF contamination occurs, do processing facility machines need to be shut down and cleaned?**  
   *Decision affected:* This would help clarify the full downstream cost of contamination and strengthen the case for intervention.

3. **Is there space in the field to install a freestanding structure such as a tower?**  
   *Decision affected:* If field placement is not feasible, the vibration tower concept would need to be redesigned or reconsidered.

### Sources

- [60 Hz vibration study — USDA ARS](https://www.ars.usda.gov/research/publications/publication/?seqNo115=392118)
- SLF contamination threshold (1–2 adult SLF per kg slurry) — Professor Steve Heim, February 9th PM lab section

---

## Functional Prototype {#functional-prototype}

### Purpose of the Prototype

The goal of this prototype was to validate Concept A — a blower-based system that produces a directed burst of air to dislodge spotted lanternflies from grapevines before they enter the harvester. The prototype consisted of a 3D-printed PLA funnel and motor housing powered by an Arduino Uno Minima Rev4, designed to test whether a compact fan system could generate sufficient airflow to remove SLF-sized insects.

### What Was Tested

| Test | Method |
|------|--------|
| Wind speed / motor output | Marked fan blades; captured slow-motion video and counted RPM (~3,500 RPM at 5V via Arduino) |
| Wind pressure | Calculated from wind velocity and cross-sectional surface area |
| Funnel shape | Simulated in Autodesk Fusion 360; circular cross-section evaluated for pressure distribution |
| Material durability | Manual flex test on PLA funnel |
| Required force / air pattern | Real-life simulation using a cardboard lanternfly taped to a string-and-tape "vine" with grapes |

### Outcomes

- **Wind speed:** At 5V, the motor produced approximately 3,500 RPM. A dedicated anemometer was unavailable, so RPM was measured via slow-motion video.
- **Funnel geometry:** The circular funnel produced an even pressure distribution across the outlet, which is desirable for consistent insect removal.
- **Material:** The PLA funnel showed slight flex under hand pressure — acceptable for a proof-of-concept prototype, but not suitable for field conditions without a material change.
- **Air pattern:** A sudden burst of air proved significantly more effective than a constant stream at dislodging the simulated SLF, consistent with the insects' "flighty" escape behavior. This informs the control strategy: a pulsed output is preferred over continuous flow.

### Success Criteria

- The system must generate sufficient airflow to dislodge adult SLF (mean weight: 0.331 g, per [Stop SLF proceedings](https://www.stopslf.org/stopslf/assets/File/Spotted-Lanternfly-RTD-Proceedings-Oct-2024.pdf))
- The blower must not deviate more than 10 degrees from its mounted position during operation
- The system will be simplified to a single unit for harvester attachment
- The blower must be capable of producing a burst of air in under 1 second

### Design Improvements Identified

- **Increase airflow:** Add a planetary gearbox to step up fan speed beyond what the motor alone provides
- **Improve intake:** Add holes to the bottom of the motor housing so the fan can draw air from outside rather than recirculating
- **Motor housing height:** Extend side walls to fully enclose the fan blades
- **Tolerances:** Widen shaft, tubing, and wire feedthrough holes — initial tolerances were too tight for proper assembly
- **Sealing:** Add tube fittings at nozzle connections to eliminate air leaks
- **Fan blade redesign:** The current symmetric impeller draws air from the high-pressure side, which is opposite to the intended direction. Either add intake holes on the back face or redesign the funnel system to correct the airflow direction

---

## Client Report {#client-report}

### Final Solution

Our final proposed solution was a blower-based attachment mounted onto a grape harvester to remove spotted lanternflies (SLF) before they enter the harvesting system. The device uses short bursts of airflow to agitate and physically displace SLF from the vines while minimizing disturbance to the grapes themselves.

The final prototype consisted of:
- A 3D-printed PLA motor housing and funnel
- A directional fan blade system
- A 12V DC brushed motor
- Arduino-controlled operation
- A nozzle designed to concentrate airflow toward the vines

The system was designed to be low-cost, easy to mount, and minimally disruptive to existing harvester operation.

### How the System Works

The blower mounts near the intake region of the grape harvester and directs air toward the vines immediately before harvesting occurs.

The system works in three stages:

1. The motor spins the directional fan blades inside the enclosed housing.
2. Air is funneled through the nozzle, increasing outlet velocity.
3. Pulsed bursts of air dislodge SLF from the vine before grapes enter the harvester.

Testing showed that short bursts of air were more effective than continuous airflow because they triggered the lanternflies’ instinct to release and fly away.

### Prototype Testing and Results

We tested the prototype against three primary success criteria:

| Test | Result |
|------|--------|
| Wind speed | Maximum measured air velocity of 10.28 m/s |
| Material strength | Housing remained elastically deformed under 177 N force |
| SLF removal effectiveness | Mock lanternflies removed from vine setup within 1–2 seconds |

Additional airflow simulations were performed using SimScale to estimate pressure and airflow behavior through the funnel geometry.

Key measured values:
- Inlet velocity: 3.1 m/s
- Maximum pressure: 191.18 Pa
- Dynamic pressure: 183.75 Pa
- Air displacement exceeded target requirement of 1,000 cm³/s

### Development Process

#### Initial Prototype

The first design did not generate enough thrust to effectively remove lanternflies. To improve performance, we:
- Increased supplied motor voltage
- Redesigned the housing for better airflow intake
- Switched to a larger fan blade

These changes demonstrated that airflow-based removal was feasible.

#### Design Iteration

Later iterations focused on:
- Directional fan blade geometry
- Improved airflow routing
- Fully enclosed motor housing
- System modeling in Fusion 360
- Power system integration with Arduino controls

Gearbox concepts were considered but ultimately determined unnecessary for the required fan speed.

#### Final Prototype

The final assembly integrated:
- Directional fan blades
- Redesigned nozzle and funnel
- Reinforced motor housing
- Arduino motor control

The completed system was tested for airflow, durability, and SLF removal performance.

### Conclusion

Our testing demonstrated that the blower concept is a viable approach for reducing SLF contamination during grape harvesting. The prototype successfully generated sufficient airflow to remove simulated lanternflies while maintaining a compact and mountable design.

The project validated the feasibility of:
- Mechanical insect removal
- Harvester-mounted airflow systems
- Low-cost non-chemical SLF mitigation

### Recommended Next Steps

Future work should focus on:
- Testing with live spotted lanternflies
- Field testing on an active grape harvester
- Scaling the system to multiple blower units
- Investigating compressed-air implementations for higher airflow output
- Improving long-term durability with stronger materials than PLA

Although the current prototype demonstrates feasibility, additional real-world validation is needed before deployment in commercial vineyard operations.