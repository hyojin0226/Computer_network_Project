# Impact of Vehicle Speed on Handover and Packet Loss

This repository contains a Computer Networks final project that analyzes how vehicle speed affects V2I communication stability.

The project uses a simplified SUMO and Python-based simulation to observe the relationship between vehicle speed, handover-like events, and packet loss in a high-speed road environment.

This project does not aim to reproduce an actual LTE or 5G handover system. Instead, it focuses on trend analysis by using simplified rules based on vehicle movement, RSU distance, and vehicle speed.

---

## Project Overview

Vehicle-to-Infrastructure, or V2I, is a communication system where vehicles exchange data with roadside infrastructure such as RSUs or base stations.

In high-speed mobility environments, vehicles move through infrastructure coverage areas quickly. This can reduce the time available for stable communication and may increase connection changes and packet loss.

This project investigates how different vehicle speeds affect V2I communication stability.

The simulation compares three vehicle speed conditions:

| Speed Condition | Vehicle Speed |
| --------------- | ------------: |
| Low Speed       |       40 km/h |
| Medium Speed    |       80 km/h |
| High Speed      |      120 km/h |

---

## Problem Statement

The main research question of this project is:

> How does vehicle speed affect V2I communication stability in a high-speed mobility environment?

In V2I communication, a vehicle may need to change its connected RSU as it moves along the road. When the vehicle speed increases, the vehicle passes through each RSU coverage area more quickly.

As a result, higher speed can lead to:

* More frequent RSU changes
* Shorter stable connection time
* Increased packet loss
* Lower overall communication stability

This project measures these effects using simplified simulation rules.

---

## Key Concepts

### V2X

V2X refers to a vehicle communication environment where vehicles exchange information with surrounding entities such as vehicles, infrastructure, pedestrians, and networks.

### V2I

V2I, or Vehicle-to-Infrastructure, is a communication method where vehicles exchange data with roadside infrastructure such as RSUs or base stations.

### Handover

Handover is the process where a moving vehicle changes its connection from one RSU or base station to another.

### Handover-like Event

In this project, a handover-like event is recorded whenever the nearest connected RSU changes.

This is not a full LTE or 5G handover procedure. It is a simplified event used to observe connection changes in the simulation.

### Packet Loss

Packet loss occurs when transmitted data packets fail to reach the destination.

In this project, packet loss is calculated using a simplified probability model based on distance and speed.

---

## Simulation Environment

| Item                     | Description                                            |
| ------------------------ | ------------------------------------------------------ |
| Tools                    | SUMO, Python                                           |
| Road Type                | Highway-like road environment                          |
| Number of RSUs           | 3                                                      |
| Number of Vehicles       | 3                                                      |
| Speed Conditions         | 40 km/h, 80 km/h, 120 km/h                             |
| Connection Rule          | Each vehicle connects to the nearest RSU               |
| Handover-like Event Rule | Recorded when the connected RSU changes                |
| Packet Sending Rule      | Vehicles send packets every 1 second                   |
| Packet Loss Model        | Simplified distance- and speed-based probability model |

---

## Methodology

The simulation and analysis were conducted through the following process:

1. A highway-like road environment was created using SUMO.
2. Vehicles were simulated under three speed conditions: 40 km/h, 80 km/h, and 120 km/h.
3. Python was used to collect vehicle position and speed data.
4. The distance between each vehicle and each RSU was calculated.
5. Each vehicle was connected to the nearest RSU.
6. A handover-like event was recorded whenever the connected RSU changed.
7. Packet loss was calculated using a simplified probability model based on distance and speed.
8. The cumulative number of handover-like events and packet losses was compared by speed condition.

This methodology allows the project to isolate the effect of vehicle speed in a simplified V2I scenario.

---

## Results

### Handover-like Events
<img width="1169" height="582" alt="image" src="https://github.com/user-attachments/assets/b3b98604-8550-421a-a0a5-9494db474f60" />

As vehicle speed increased, vehicles passed through each RSU coverage area more quickly.

Because of this, the connected RSU changed more frequently at higher speeds. The high-speed vehicle showed the largest cumulative number of handover-like events, while the low-speed vehicle showed the smallest number.

Approximate final handover-like events:

| Speed Condition | Vehicle Speed | Approximate Final Events |
| --------------- | ------------: | -----------------------: |
| Low Speed       |       40 km/h |                  About 4 |
| Medium Speed    |       80 km/h |                  About 7 |
| High Speed      |      120 km/h |                 About 10 |

### Packet Loss
<img width="1171" height="572" alt="image" src="https://github.com/user-attachments/assets/6a0a726e-8b01-4986-84d9-47b230f59e14" />

Packet loss also increased as vehicle speed increased.

Faster vehicles had shorter stable connection time with RSUs. Rapid changes in distance between the vehicle and RSUs made the connection less stable in the simplified model, which increased cumulative packet loss.

Final cumulative packet loss:

| Speed Condition | Cumulative Packet Loss |
| --------------- | ---------------------: |
| Low Speed       |               About 75 |
| Medium Speed    |               About 99 |
| High Speed      |              About 123 |

---

## Trade-off Analysis

Higher vehicle speed improves mobility efficiency, but it can reduce V2I communication stability.

In this simulation, faster vehicles showed:

* Shorter RSU dwell time
* More frequent handover-like events
* Higher packet loss
* Lower communication stability

This shows a trade-off between mobility efficiency and communication reliability.

In high-speed V2I environments, communication systems must support fast-moving vehicles while maintaining stable data transmission.

---

## Limitations

This project has several limitations.

First, the simulation does not implement an actual LTE or 5G handover protocol. Real cellular handover involves more complex factors such as:

* RSRP
* SINR
* Handover trigger conditions
* Time-to-trigger
* X2 or NG interface signaling
* Base station coordination

Second, the packet loss model is simplified. In real wireless communication environments, packet loss can also be affected by:

* Radio interference
* Obstacles
* Terrain
* Wireless channel conditions
* Weather
* Traffic density
* Network congestion

Therefore, the results should be interpreted as trend analysis rather than exact LTE or 5G performance prediction.

---

## Paper Comparison and Validation

The simulation results were compared with related research trends.

| Reference          | Research Focus                                  | Connection to This Project                                              |
| ------------------ | ----------------------------------------------- | ----------------------------------------------------------------------- |
| C-V2X Mode 4, 2022 | PDR analysis at 40, 80, and 120 km/h            | Supports the use of the selected speed conditions                       |
| LTE Handover, 2018 | Handover analysis at various vehicle speeds     | Supports the trend that higher speed can increase handover frequency    |
| VANET AODV, 2022   | PDR, delay, and overhead at 60 and 80 km/h      | Supports the relationship between speed and packet delivery performance |
| IEEE 802.11p, 2012 | Effect of mobility on communication performance | Supports the idea that mobility can degrade communication quality       |
| Sensors, 2022      | Real-road test using LTE and 5G devices         | Shows that distance and speed affect real communication performance     |

These references were used to compare the direction of the observed trends.

The simulation in this project remains simplified and should not be considered a full replication of previous studies.

---

## Conclusion

This project analyzed the impact of vehicle speed on V2I communication stability using a simplified SUMO and Python simulation.

The results showed that higher vehicle speed caused:

* More handover-like events
* More packet loss
* Lower communication stability

At higher speeds, vehicles pass through RSU coverage areas more quickly. This reduces stable connection time and increases the possibility of communication instability.

However, since actual LTE and 5G handover protocols were not fully implemented, the results should be understood as a simplified trend analysis rather than an exact real-world performance prediction.

---

## References

1. C-V2X Mode 4, 2022.
2. LTE Handover, 2018.
3. VANET AODV, 2022.
4. IEEE 802.11p, 2012.
5. Sensors, 2022.

---

## Presentation Materials

* CN_Group11_V2I_Speed_handover.pdf

---

## About

Computer Networks final project on V2I communication stability, vehicle speed, handover-like events, and packet loss.
