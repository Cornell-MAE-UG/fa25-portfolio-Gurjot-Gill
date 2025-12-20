---
layout: project
title: Heat Exchanger Analysis
description: Heat Exchanger Lab Experiment
technologies: N/A
image: /assets/images/heat-exchanger.webp
---
For a class, we were asked to analyze the performance of a heat exchanger when performing in parallel flow, counter flow, and low vs. high flow rate. The system analyzed is a liquid-to-liquid heat exchanger used to transfer thermal energy from a hot fluid stream to a cold fluid stream without direct mixing. The exchanger can be configured in either parallel-flow or counterflow operation and operated at different flow rates. Temperature measurements were taken before and after flow occurred to characterize heat transfer behavior under varying operating conditions.

![setup 1]({{ "/assets/images/setup.jpg" | relative_url }}){: style="display: block; margin: 0 auto; width: 200px;"}

---

### Qualitative Description of Operation

In a heat exchanger, thermal energy is transferred from the hot fluid to the cold fluid due to a temperature gradient across a separating wall. In a parallel-flow configuration, both fluids enter the exchanger at the same end and flow in the same direction, resulting in a large temperature difference at the inlet that rapidly decreases along the exchanger length. In a counterflow configuration, fluids enter from opposite ends, maintaining a more uniform temperature difference and enabling greater overall heat transfer.

Flow rate also plays a critical role in performance. At low flow rates, fluids remain in the exchanger longer, allowing more time for heat transfer. At high flow rates, residence time decreases, reducing the temperature change experienced by each fluid.

![cross section 2]({{ "/assets/images/cross2.jpg" | relative_url }}){: style="display: block; margin: 0 auto; width: 400px;"}

![cross section 1]({{ "/assets/images/cross1.jpg" | relative_url }}){: style="display: block; margin: 0 auto; width: 400px;"}

---

### System Diagram and Control Volume Description

The heat exchanger is modeled as a steady-flow control volume with two fluid inlets and two fluid outlets. No shaft work is performed, and kinetic and potential energy effects are neglected. Heat transfer occurs internally between the two fluid streams through the exchanger wall, with minimal heat loss to the surroundings. The energy balance, mass balance, and entropy balance are as given below.

![diagram]({{ "/assets/images/HE.png" | relative_url }}){: style="display: block; margin: 0 auto; height: 150px;"}
<p align="center">
  Parallel Flow Heat Exchanger, Control Volume 
</p>
<p align="center">
  ṁ<sub>in</sub> = ṁ<sub>out</sub> 
</p>
<p align="center">
  Q̇ =  ṁ<sub>c</sub>c<sub>p</sub>(T<sub>h,i</sub>-T<sub>c,o</sub>) = ṁ<sub>h</sub>c<sub>p</sub>(T<sub>h,i</sub>-T<sub>h,o</sub>)
</p>
<p align="center">
  Ṡ<sub>gen</sub> = ṁ<sub>h</sub> (s<sub>h,out</sub> − s<sub>h,in</sub>) + ṁ<sub>c</sub> (s<sub>c,out</sub> − s<sub>c,in</sub>) ≥ 0
</p>

---

## Experimental Performance Results

Temperature data showed that counterflow operation consistently produced larger cold-side temperature increases than parallel flow, particularly at low flow rates. Under low-flow counterflow operation, the cold reservoir temperature increased by approximately 20.9 °F, compared to approximately 18.5 °F for parallel flow. Counterflow operation also approached thermal equilibrium more closely, indicating higher effectiveness.

Increasing the flow rate reduced the magnitude of temperature changes in both the hot and cold streams. This behavior is attributed to reduced residence time within the heat exchanger, which limits the total heat transferred.

---

## Additional Calculations and Quantitative Comparisons

To further quantify performance differences, several temperature-based metrics were calculated directly from experimental data.

The average reservoir temperature change magnitude was used as a simple performance indicator. For low-flow counterflow operation, the average change was approximately 20.25 °F, compared to approximately 15.15 °F for low-flow parallel operation. This indicates that counterflow configuration achieved greater overall thermal exchange.

An effective temperature driving force was estimated using final reservoir temperatures. For low-flow counterflow operation, the temperature difference between hot and cold reservoirs after flow was approximately −6.1 °F, indicating that the cold stream approached or exceeded the hot-side temperature. In contrast, low-flow parallel operation maintained a positive temperature difference of approximately 3.8 °F, demonstrating reduced approach to thermal equilibrium.

A cold-side temperature gain ratio was also calculated by comparing cold-side temperature increase to hot-side reservoir temperature decrease. For low-flow counterflow operation, this ratio was approximately 1.07, while parallel flow yielded a ratio of approximately 1.57. These ratios provide insight into how effectively hot-side cooling translated into cold-side heating across configurations.

--- 

## Effect of Design and Operating Changes

*Change in Flow Configuration*
Switching from parallel flow to counterflow increases the average temperature difference between the hot and cold streams along the exchanger length. This reduces entropy generation and increases overall heat transfer effectiveness, as supported by the larger cold-side temperature increases and closer approach to thermal equilibrium observed experimentally.

*Change in Flow Rate*
Increasing the flow rate decreases resistance time, reducing the temperature change experienced by each fluid. While higher flow rates may increase the convective heat transfer coefficient, the reduced contact time dominated system behavior, resulting in lower overall temperature changes.

---

## Conclusion

This analysis demonstrates how heat exchanger performance is strongly influenced by both flow configuration and operating conditions. Counterflow operation provides superior thermal performance due to a more uniform temperature gradient and reduced entropy generation, while lower flow rates enhance heat transfer by increasing residence time. The inclusion of temperature-based performance metrics reinforces these conclusions and illustrates the practical thermodynamic trade-offs involved in heat exchanger design.