Impact of Vehicle Speed on Handover and Packet Loss
This repository contains a Computer Networks final project about V2I communication stability in a high-speed mobility environment. The project uses a simplified SUMO and Python simulation to analyze how vehicle speed affects handover-like events and packet loss.

The work focuses on trend analysis rather than exact LTE/5G performance prediction. The simulation does not implement a full cellular handover protocol; instead, it observes RSU changes and packet loss behavior using simplified rules based on vehicle movement, distance, and speed.

Project Overview
Vehicle-to-Infrastructure (V2I) communication allows vehicles to exchange data with roadside RSUs or base stations. In a high-speed road environment, vehicles pass through infrastructure coverage areas quickly, which can reduce the time available for stable communication.

This project analyzes how vehicle speed affects V2I communication stability. A simplified high-speed V2I simulation was implemented using SUMO and Python. The main focus is to observe handover-like events and packet loss under three vehicle speed conditions:

Low speed: 40 km/h
Medium speed: 80 km/h
High speed: 120 km/h
Problem Statement
How stable is V2I communication in a high-speed mobility environment?

In V2I communication, vehicles exchange data with roadside RSUs or base stations. When vehicles move faster, they pass through RSU coverage areas more quickly. This can cause more frequent RSU changes and lower communication stability.

The project studies this problem by measuring:

Handover-like events, recorded when the nearest connected RSU changes.
Packet loss, calculated using a simplified distance- and speed-based probability model.
Key Concepts
V2X: A vehicle communication environment where vehicles exchange data with surrounding entities.

V2I: A communication method where vehicles exchange data with roadside RSUs or base stations.

Handover: A process where a moving vehicle changes its connection from one RSU to another.

Handover-like event: In this project, this was recorded whenever the nearest connected RSU changed.

Packet loss: A situation where some transmitted data packets fail to reach the destination.

Simulation Environment
Item	Description
Tools	SUMO and Python
Road type	Highway-like road environment
Number of RSUs	3
Number of vehicles	3
Speed conditions	40 km/h, 80 km/h, 120 km/h
Connection rule	Each vehicle connects to the nearest RSU
Recording rule	A handover-like event is recorded when the connected RSU changes
Packet sending rule	Vehicles send packets every 1 second
Packet loss model	Simplified distance- and speed-based probability model
Methodology
The simulation and analysis followed these steps:

Constructed a highway-like road environment in SUMO.
Simulated vehicles moving at 40, 80, and 120 km/h.
Used Python to check vehicle position and speed data.
Calculated the distance between each vehicle and RSU.
Determined the connected RSU based on the nearest RSU.
Recorded handover-like events when the connected RSU changed.
Calculated packet loss using a simplified probability model based on distance and speed.
This methodology isolates the effect of speed in a simplified V2I setting. It does not model full LTE/5G handover procedures or a real wireless channel.

Results
Handover-like Events
Handover-like events by vehicle speed

As vehicle speed increases, the vehicle passes through each RSU coverage area in a shorter time. Therefore, the connected RSU changes more frequently. High-speed vehicles show a larger cumulative number of handover-like events than low-speed vehicles.

Approximate final handover-like events:

Speed condition	Vehicle speed	Approximate final events
Low speed	40 km/h	about 4
Medium speed	80 km/h	about 7
High speed	120 km/h	about 10
Packet Loss
Cumulative packet loss by vehicle speed

Faster vehicles have shorter stable connection time with RSUs. Rapid distance changes from RSUs make the connection less stable, which increases cumulative packet loss in the simplified probability model.

Final cumulative packet loss:

Speed condition	Cumulative packet loss
Low speed	about 75
Medium speed	about 99
High speed	about 123
Analysis
The simulation results show that vehicle speed has a clear effect on V2I communication stability.

For handover-like events, higher-speed vehicles pass through each RSU coverage area in a shorter amount of time. Because the vehicle stays connected to each RSU for less time, the nearest RSU changes more frequently. This explains why the cumulative number of handover-like events increases from about 4 at 40 km/h to about 10 at 120 km/h.

For packet loss, faster vehicles experience more rapid distance changes from RSUs. Since the packet loss model is based on distance and speed, higher speed increases the probability of packet loss. This explains why cumulative packet loss increases from about 75 at low speed to about 123 at high speed.

Overall, the results suggest that higher vehicle speed reduces V2I communication stability by shortening RSU dwell time, increasing connection switching, and increasing packet loss.

Trade-offs
Higher vehicle speed improves movement efficiency, but it reduces V2I communication stability. Faster vehicles have shorter RSU dwell time, more frequent connection switching, and more packet loss.

This creates a trade-off between mobility efficiency and communication stability. In a high-speed V2I environment, the network must support vehicles that move quickly through infrastructure coverage areas while still maintaining reliable data delivery.

Limitations
This project does not implement an actual LTE/5G protocol. It is a simplified simulation based on vehicle movement data.

Actual LTE/5G handover involves more complex factors such as RSRP, SINR, handover trigger conditions, time-to-trigger, and base station interfaces such as X2 or NG.

Packet loss was also calculated using a simplified distance- and speed-based probability model, not an actual wireless channel model. Real packet loss can also be affected by radio interference, obstacles, terrain, wireless channel conditions, weather, and traffic density.

Because of these limitations, the results should be interpreted as trend analysis rather than exact performance prediction.

Paper Comparison and Validation
The project compares its trends with the following references only:

Reference	Research focus	Connection to this project
C-V2X Mode 4, 2022	PDR analysis at 40 / 80 / 120 km/h	Supports the reliability of the speed conditions used in the simulation
LTE Handover, 2018	Handover analysis at 3-170 km/h	Supports that higher speed leads to more handovers
VANET AODV, 2022	PDR, delay, and overhead at 60 / 80 km/h	Confirms PDR decrease and packet loss increase
IEEE 802.11p, 2012	Impact of mobility on communication performance	Supports that mobility can degrade communication quality
Sensors, 2022	Real-road test with LTE-5G devices	Shows that distance and speed affect real communication performance
These papers are used as comparison points for the direction of the observed trends. The simulation in this repository remains simplified and should not be treated as a full replication of those studies.

Conclusion
Higher vehicle speed reduces V2I communication stability. In the simplified SUMO and Python simulation, higher speed caused more handover-like events and more packet loss.

Since vehicles pass through RSU coverage areas quickly at high speeds, designing stable V2I communication is important. However, because actual LTE/5G protocols were not fully implemented, the results should be interpreted as trend analysis rather than exact performance prediction.

References
C-V2X Mode 4, 2022.
LTE Handover, 2018.
VANET AODV, 2022.
IEEE 802.11p, 2012.
Sensors, 2022.
Presentation Materials
Presentation PDF
Google Drive Folder
