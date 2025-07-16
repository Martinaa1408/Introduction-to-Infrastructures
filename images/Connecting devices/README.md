# Connecting Devices – README
This section of the repository illustrates the key concepts and roles of IoT (Internet of Things), Edge Computing, and Cloud Computing, highlighting their interactions and layered structure in modern infrastructures. The images in this folder explain how connected devices communicate, process, and transfer data at different levels of the digital ecosystem.

## Included Images and Descriptions

`cloud-edge-IoT.png`

Description:
This layered diagram introduces the vertical integration of:

IoT at the bottom: Smart devices that collect and transmit data (e.g., wearables, cars).

Edge computing in the middle: Performs local, real-time data processing (e.g., routers, gateways).

Cloud computing at the top: Centralized processing and storage (big data analytics, warehousing).

Comparison:

Highlights the flow of data upward from device to cloud.

Edge is a bridge between latency-sensitive tasks and deep cloud analytics.

`IoT.png`

Description:
A holistic representation of IoT domains, including:

Applications: Smart cities, healthcare, agriculture, security, energy, etc.

Communication modes: M2M, sensor networks, embedded systems.

Environments: Smart homes, wearable tech, urban monitoring.

Comparison:

Broader scope compared to cloud-edge-IoT.png, emphasizing use cases.

More domain-centric and visually comprehensive.

`IoT-edge-cloud-descriptive.png`

Description:
This workflow explains data pipeline from IoT to Cloud:

IoT collects raw data from diverse sources.

Edge devices perform low-latency analytics for fast decisions.

Cloud handles long-term storage, deep analytics, and automation.

Output leads to insights for action: descriptive, predictive, prescriptive.

Comparison:

More functional and analytical than the other diagrams.

Integrates analytics concepts (Lambda architecture, IaaS/PaaS/SaaS).

Shows real value of connecting edge and cloud.

## Conceptual Connections
Layer	Function	Technologies
IoT	Sensing & collecting data	Smart devices, M2M
Edge	Real-time & local analytics	Gateways, routers
Cloud	Deep storage & AI-based data processing	Data lakes, ML platforms

Edge computing reduces latency and bandwidth needs before data reaches the cloud.

IoT enables digital twins, predictive maintenance, smart automation.

Cloud centralizes intelligence and feeds insights back to edge/IoT.

###### Tip: These layers are not mutually exclusive. For example, a smart vehicle may locally detect danger (edge) but upload logs to cloud for fleet-wide AI model retraining.
