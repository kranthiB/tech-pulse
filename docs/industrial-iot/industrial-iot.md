---
id: industrial-iot/industrial-iot
title: Industrial IoT
sidebar_label: Industrial IoT
next_page: industrial-iot/industry-5.0
---

Table of contents
=================

<!--ts-->
   * [Industrial Revolution](#industrial-revolution)
   * [Smart Manufacturing](#smart-manufacturing)
      * [Manufacturing Paradigms](#manufacturing-paradigms)
      * [Evolution of Digital Manufacturing](#evolution-of-digital-manufacturing)
      * [Discrete vs Process Manufacturing](#discrete-vs-process-manufacturing)
      * [Key Capabilities](#key-capabilities)
      * [Design Principles & Smart System Elements](#design-principles--smart-system-elements)
      * [Ecosystem](#ecosystem)
      * [Landscape](#landscape)
      * [Standard Opportunities](#standard-opportunities)
   * [Nine Pillars](#nine-pillars)
      * [Additive Manufacturing](#additive-manufacturing)
      * [AR / VR / MR / Haptics](#ar--vr--mr--haptics)
      * [Autonomous Robots](#autonomous-robots)
      * [The Cloud](#the-cloud)
      * [Big Data & Analytics](#big-data--analytics)
      * [Cybersecurity](#cybersecurity)
      * [IIOT](#iiot)
      * [Simulation](#simulation)
      * [Horizontal and Vertical Integration](#horizontal-and-vertical-integration)
   * [Reference Architectures](#reference-architectures)
      * [RAMI 4.0](#rami-40)
      * [AWS Industrial](#aws-industrial)
      * [Azure Industrial](#azure-industrial)
      * [Edge Compute](#edge-compute)
      * [Predictive Maintenance](#predictive-maintenance)
      * [Overall Equipment Effectiveness](#overall-equipment-effectiveness)
      * [Plant Architecture](#plant-architecture)
         * [Industrial Control System Components](#industrial-control-system-components)
   * [Workloads](#workloads)
      * [Key Enablers](#key-enablers)
      * [Digitalization Journey](#digitalization-journey)
      * [Use cases](#use-cases)
      * [Demos](#demos)
         * [OPC-UA Pipeline (On-Premise)](#opc-ua-pipeline-on-premise)
         * [Computer Vision at the Edge](#computer-vision-at-the-edge)
            * [Virtual Andon](#virtual-andon)
   * [IT Vs OT Security](#it-vs-ot-security)
      * [Network Topologies in OT Environment](#network-topologies-in-ot-environment)
      * [IT and OT Networking Background](#it-and-ot-networking-background)
      * [Challenges](#challenges)
         * [Business Risk](#business-risk)
         * [TRITON Attack](#triton-attack)
      * [How Gartner Defines?](#how-gartner-defines)
      * [IT Security vs OT Security](#it-security-vs-ot-security)
         * [SCADA](#scada)
      * [Aligning IT & OT](#aligning-it--ot)
      * [Events that Affect IoT / OT Networks](#events-that-affect-iot--ot-networks)
      * [Microsoft Defender for IoT](#microsoft-defender-for-iot)
         * [Features](#features)
         * [Reference Architecture](#reference-architecture)
         * [Unified, E2E Protection](#unified-e2e-protection)
         * [Deployment Options](#deployment-options)
            * [Recommended Deployment Process](#recommended-deployment-process)
            * [9 Steps Deployment Process](#9-steps-deployment-process)
   * [Readniess](#readniess)
      * [Model Dimensions](#model-dimensions)
      * [Maturity Models](#maturity-models)
<!--te-->

## Industrial Revolution
![IR](https://raw.githubusercontent.com/kranthiB/tech-pulse/main/images/industrial-iot/industrial-iot/0001-IR.png)
The Industrial Revolution was a pivotal period in human history, marking a significant shift from manual labor to machine-based manufacturing. This transformation had far-reaching consequences, impacting various aspects of society and shaping the modern world as we know it today.
   
 * `First Industrial Revolution (18th Century)`
   * *Automation of Physical Labor*
     * Water/Stream Power
       * The introduction of water-powered machinery marked a significant milestone in automation. 
     * First Mechanical Loom
       * The invention of the mechanical loom revolutionized textile production, increasing efficiency and output 
     * Power - Coal
       * Coal became a primary source of energy for industrial processes, driving growth and development. 
     * Mobility - Rail/Ship Networks, Steam Engine
       * Advances in transportation enabled rapid movement of goods and people, further facilitating economic expansion.
          
 * `Second Industrial Revolution (19th Century)`
   * *Automation/Rationalization of Physical Labor*
     * Electricity-Powered Mass Production
       * The widespread adoption of electricity transformed manufacturing processes, allowing for faster and more efficient production 
     * First Production Lines
       * Assembly lines became a standard feature in factories, streamlining production and increasing productivity 
     * Power - Oil/Gas
       * Fossil fuels emerged as a primary source of energy, fueling further industrialization. 
     * Mobility - Planes, Oil-Powered Ships, Automobiles
       * Advances in transportation led to the development of new modes of travel, transforming global connectivity.

 * `Third Industrial Revolution (20th Century)`
   * *Automation of Individual Entities in an Organization*
     * Computers/Sensors
       * The rise of computers and sensors enabled automation within individual entities, enhancing efficiency and accuracy. 
     * First Programmable Logic Controller (PLC)
       * The introduction of PLCs revolutionized industrial control systems, allowing for greater flexibility and adaptability. 
     * Power - Renewables
       * Renewable energy sources began to gain prominence, reducing reliance on fossil fuels and promoting sustainability. 
     * Mobility - Satellite-Based Navigational Aids
       * Advances in satellite technology enabled precise navigation and communication, transforming industries such as aviation and maritime

 * `Fourth Industrial Revolution`
   * *Automation Across Entire Organizations*
     * Autonomy Across Entire Organizations
       * The integration of artificial intelligence and robotics has led to increased autonomy across entire organizations. 
     * Based on Physical Systems
       * Automation is now based on physical systems, leveraging the capabilities of sensors, actuators, and other devices. 
     * Powered by Distributed Storage
       * Distributed storage solutions have enabled efficient management of data and resources, supporting widespread automation. 
     * Mobility - Autonomous Vehicles and Networks
       * The development of autonomous vehicles and networks has transformed transportation systems, enhancing safety and efficiency.

-----

## Smart Manufacturing

### Manufacturing Paradigms
![IR](https://raw.githubusercontent.com/kranthiB/tech-pulse/main/images/industrial-iot/industrial-iot/0002-MP.png)
Smart manufacturing is an emerging trend that combines advanced technologies such as artificial intelligence, robotics, IoT, and big data analytics to transform traditional manufacturing processes into more efficient, agile, and sustainable systems
 * `Characteristics of Smart Manufacturing:`
   * *Digitization:* The integration of digital technologies to create a virtual representation of the physical world.
   * *Connected Devices and Distributed Intelligence for Real-Time Control:* The use of sensors, actuators, and control systems to monitor and control production processes in real-time.
   * *Collaborative Supply Chain Management:* The integration of supply chain management with manufacturing to optimize inventory levels, reduce lead times, and improve customer satisfaction.
   * *Energy and Resource Efficiency through Optimal Decision-Making:* The use of data analytics and machine learning algorithms to make informed decisions about energy consumption, resource allocation, and production planning.
   * *Advanced Sensors and Big Data Analytics Integrated into Product Lifecycle:* The integration of sensors and big data analytics to monitor product performance, predict maintenance needs, and optimize product design. 
 * `Manufacturing Paradigms:`
   * *Lean Manufacturing:* A paradigm that focuses on minimizing waste and maximizing value-added activities through continuous improvement and elimination of non-value-added tasks.
   * *Cloud Manufacturing:* A paradigm that leverages cloud computing to enable flexible, scalable, and collaborative manufacturing processes.
   * *Intelligent Manufacturing:* A paradigm that incorporates artificial intelligence, machine learning, and data analytics to optimize production planning, quality control, and maintenance.
   * *Holonic Manufacturing:* A paradigm that uses multi-agent systems, decentralized decision-making, and model-based reasoning to create self-organizing production systems.
   * *Agile Manufacturing:* A paradigm that focuses on rapid response to changing market demands through flexible and adaptable manufacturing processes.
   * *Digital Manufacturing:* A paradigm that leverages digital technologies such as 3D printing, simulation, and virtual reality to design, test, and manufacture products virtually.
   * *Sustainable Manufacturing:* A paradigm that prioritizes environmental sustainability by reducing waste, conserving resources, and promoting eco-friendly practices throughout the product lifecycle.
   * *Flexible Manufacturing:* A paradigm that enables rapid changeover between different production runs through modularized designs, interoperability, and real-time visualization.
   * *Intelligent Manufacturing:* A paradigm that incorporates artificial intelligence, advanced sensing, control systems, optimization techniques, and knowledge management to optimize production processes. 
 * `Benefits of Smart Manufacturing:`
   * *Increased Efficiency:* Smart manufacturing enables automation, streamlines processes, and reduces labor costs.
   * *Improved Product Quality:* Advanced sensors and analytics ensure consistent product quality, reducing defects and rework.
   * *Enhanced Customer Experience:* Smart manufacturing allows for real-time monitoring, predictive maintenance, and personalized products tailored to customer needs.
   * *Reduced Costs:* Smart manufacturing optimizes resource allocation, reduces energy consumption, and minimizes waste.
   * *Increased Competitiveness:* Smart manufacturing enables businesses to stay competitive in the global market by offering innovative products, services, and experiences. 
 * `Challenges and Limitations:`
   * *High Initial Investment:* Implementing smart manufacturing technologies requires significant upfront investments in hardware, software, and training.
   * *Integration Challenges:* Integrating different systems, devices, and data sources can be complex and time-consuming.
   * *Cybersecurity Risks:* Smart manufacturing introduces new cybersecurity risks due to the increased connectivity and data exchange between devices and systems.
   * *Skills Gap:* The adoption of smart manufacturing requires a significant shift in workforce skills, which can be challenging for companies to implement. 
 * `Future Directions:`
   * *Artificial Intelligence and Machine Learning:* AI and ML will play an increasingly important role in optimizing production processes, predicting maintenance needs, and improving product quality.
   * *Internet of Things (IoT):* IoT will continue to expand its presence in manufacturing, enabling real-time monitoring, remote access, and predictive maintenance.
   * *5G Networks:* 5G networks will provide faster data transfer rates, lower latency, and increased connectivity, enabling more widespread adoption of smart manufacturing technologies.
   * *Sustainability and Environmental Impact:* Smart manufacturing will prioritize environmental sustainability by reducing waste, conserving resources, and promoting eco-friendly practices throughout the product lifecycle. 

-----

### Evolution of Digital Manufacturing
![EDM](https://raw.githubusercontent.com/kranthiB/tech-pulse/main/images/industrial-iot/industrial-iot/0003-EDM.png)
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`

-----

### Discrete vs Process Manufacturing
![DMPM](https://raw.githubusercontent.com/kranthiB/tech-pulse/main/images/industrial-iot/industrial-iot/0004-DMPM.png)
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`

-----

### Key Capabilities
![KP](https://raw.githubusercontent.com/kranthiB/tech-pulse/main/images/industrial-iot/industrial-iot/0005-KP.png)
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`

-----

### Design Principles & Smart System Elements
![DPSSE](https://raw.githubusercontent.com/kranthiB/tech-pulse/main/images/industrial-iot/industrial-iot/0006-DPSSE.png)
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`

-----

### Ecosystem
![ES](https://raw.githubusercontent.com/kranthiB/tech-pulse/main/images/industrial-iot/industrial-iot/0007-ES.png)
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`

-----

### Landscape
![LS](https://raw.githubusercontent.com/kranthiB/tech-pulse/main/images/industrial-iot/industrial-iot/0008-LS.png)
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`

-----

### Standard Opportunities
![SP](https://raw.githubusercontent.com/kranthiB/tech-pulse/main/images/industrial-iot/industrial-iot/0009-SP.png)
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`

-----

## Nine Pillars
![SP](https://raw.githubusercontent.com/kranthiB/tech-pulse/main/images/industrial-iot/industrial-iot/0010-NP.png)
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`

-----

### Additive Manufacturing
![AM](https://raw.githubusercontent.com/kranthiB/tech-pulse/main/images/industrial-iot/industrial-iot/0011-AM.png)
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`

-----

### AR / VR / MR / Haptics
![AM](https://raw.githubusercontent.com/kranthiB/tech-pulse/main/images/industrial-iot/industrial-iot/0012-IE.png)
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`

-----

### Autonomous Robots
![AR](https://raw.githubusercontent.com/kranthiB/tech-pulse/main/images/industrial-iot/industrial-iot/0013-AR.png)
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`

-----

### The Cloud
![CL](https://raw.githubusercontent.com/kranthiB/tech-pulse/main/images/industrial-iot/industrial-iot/0014-CL.png)
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`

-----

### Big Data & Analytics
![BD](https://raw.githubusercontent.com/kranthiB/tech-pulse/main/images/industrial-iot/industrial-iot/0015-BD.png)
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`

-----

### Cybersecurity
![CS](https://raw.githubusercontent.com/kranthiB/tech-pulse/main/images/industrial-iot/industrial-iot/0016-CS.png)
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`

-----

### IIOT
![IIOT](https://raw.githubusercontent.com/kranthiB/tech-pulse/main/images/industrial-iot/industrial-iot/0017-IIOT.png)
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`

-----

### Simulation
![SM](https://raw.githubusercontent.com/kranthiB/tech-pulse/main/images/industrial-iot/industrial-iot/0018-SM.png)
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`

-----

### Horizontal and Vertical Integration
![HIVI](https://raw.githubusercontent.com/kranthiB/tech-pulse/main/images/industrial-iot/industrial-iot/0019-HIVI.png)
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`

-----

## Reference Architectures

### RAMI 4.0
![RAMI](https://raw.githubusercontent.com/kranthiB/tech-pulse/main/images/industrial-iot/industrial-iot/0020-RAMI.png)
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`

-----

### AWS Industrial
![AWS](https://raw.githubusercontent.com/kranthiB/tech-pulse/main/images/industrial-iot/industrial-iot/0021-AWS.png)
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`

-----

### Azure Industrial
![AZURE](https://raw.githubusercontent.com/kranthiB/tech-pulse/main/images/industrial-iot/industrial-iot/0022-AZURE.png)
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`

-----

### Edge Compute
![EC](https://raw.githubusercontent.com/kranthiB/tech-pulse/main/images/industrial-iot/industrial-iot/0023-EC.png)
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`

-----

### Predictive Maintenance
![PM](https://raw.githubusercontent.com/kranthiB/tech-pulse/main/images/industrial-iot/industrial-iot/0024-PM.png)
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`

-----

### Overall Equipment Effectiveness
![OEE](https://raw.githubusercontent.com/kranthiB/tech-pulse/main/images/industrial-iot/industrial-iot/0025-OEE.png)
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`

-----

### Plant Architecture
![PA](https://raw.githubusercontent.com/kranthiB/tech-pulse/main/images/industrial-iot/industrial-iot/0026-PA.png)
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`

-----

#### Industrial Control System Components
![ICS](https://raw.githubusercontent.com/kranthiB/tech-pulse/main/images/industrial-iot/industrial-iot/0027-ICS.png)
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`


-----

## Workloads

### Key Enablers
![KE](https://raw.githubusercontent.com/kranthiB/tech-pulse/main/images/industrial-iot/industrial-iot/0028-KE.png)
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`

-----

### Digitalization Journey
![DJ](https://raw.githubusercontent.com/kranthiB/tech-pulse/main/images/industrial-iot/industrial-iot/0029-DJ.png)
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`

-----

### Use cases
![IW1](https://raw.githubusercontent.com/kranthiB/tech-pulse/main/images/industrial-iot/industrial-iot/0030-IW1.png)
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`

-----

![IW2](https://raw.githubusercontent.com/kranthiB/tech-pulse/main/images/industrial-iot/industrial-iot/0031-IW2.png)
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`

-----

### Capabilities
![CP](https://raw.githubusercontent.com/kranthiB/tech-pulse/main/images/industrial-iot/industrial-iot/0032-CP.png)
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
### Demos

#### OPC-UA Pipeline (On-Premise)
![OPCA](https://raw.githubusercontent.com/kranthiB/tech-pulse/main/images/industrial-iot/industrial-iot/0033-OPCA.png)
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`

-----

![OPCB](https://raw.githubusercontent.com/kranthiB/tech-pulse/main/images/industrial-iot/industrial-iot/0034-OPCB.png)
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
#### Computer Vision at the Edge

##### Virtual Andon
![VA](https://raw.githubusercontent.com/kranthiB/tech-pulse/main/images/industrial-iot/industrial-iot/0035-CV.png)
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`

-----

[![Virtual Andon](https://img.youtube.com/vi/_2Wfz4T_yP0/maxresdefault.jpg)](https://www.youtube.com/watch?v=_2Wfz4T_yP0)
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`

-----

https://www.youtube.com/watch?v=_2Wfz4T_yP0

-----

## IT vs OT Security

### Network Topologies in OT Environment
![NT](https://raw.githubusercontent.com/kranthiB/tech-pulse/main/images/industrial-iot/industrial-iot/0036-NT.png)
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`

-----

### IT and OT Networking Background
![NB](https://raw.githubusercontent.com/kranthiB/tech-pulse/main/images/industrial-iot/industrial-iot/0037-NB.png)
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`

-----

### Challenges
![CL](https://raw.githubusercontent.com/kranthiB/tech-pulse/main/images/industrial-iot/industrial-iot/0038-CL.png)
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`

#### Business Risk
![BR](https://raw.githubusercontent.com/kranthiB/tech-pulse/main/images/industrial-iot/industrial-iot/0039-BR.png)
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`

-----

#### TRITON Attack
![TA](https://raw.githubusercontent.com/kranthiB/tech-pulse/main/images/industrial-iot/industrial-iot/0040-BR1.png)
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`

-----

### How Gartner Defines?
![GT](https://raw.githubusercontent.com/kranthiB/tech-pulse/main/images/industrial-iot/industrial-iot/0041-GT.png)
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`

-----

### IT Security vs OT Security
![ITOT](https://raw.githubusercontent.com/kranthiB/tech-pulse/main/images/industrial-iot/industrial-iot/0042-ITOT.png)
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`

-----

#### SCADA
![SCADA](https://raw.githubusercontent.com/kranthiB/tech-pulse/main/images/industrial-iot/industrial-iot/0043-SC.png)
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`

-----

### Aligning IT & OT
![OT](https://raw.githubusercontent.com/kranthiB/tech-pulse/main/images/industrial-iot/industrial-iot/0044-OT.png)
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`

-----

### Events that Affect IoT / OT Networks
![OT](https://raw.githubusercontent.com/kranthiB/tech-pulse/main/images/industrial-iot/industrial-iot/0045-ET.png)
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`

-----

### Microsoft Defender for IoT

#### Features
![FR](https://raw.githubusercontent.com/kranthiB/tech-pulse/main/images/industrial-iot/industrial-iot/0046-FR.png)
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`

-----

#### Reference Architecture
![AR](https://raw.githubusercontent.com/kranthiB/tech-pulse/main/images/industrial-iot/industrial-iot/0047-AR.png)
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`

-----

#### Unified, E2E Protection
![UE](https://raw.githubusercontent.com/kranthiB/tech-pulse/main/images/industrial-iot/industrial-iot/0048-UE.png)
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`

-----

#### Deployment Options
![DP](https://raw.githubusercontent.com/kranthiB/tech-pulse/main/images/industrial-iot/industrial-iot/0049-DP.png)
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`

-----

##### Recommended Deployment Process
![DPA](https://raw.githubusercontent.com/kranthiB/tech-pulse/main/images/industrial-iot/industrial-iot/0050-DPA.png)
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`

-----

##### 9 Steps Deployment Process
![DPB](https://raw.githubusercontent.com/kranthiB/tech-pulse/main/images/industrial-iot/industrial-iot/0050-DPB.png)
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`

-----

## Readniess

### Model Dimensions
![MR](https://raw.githubusercontent.com/kranthiB/tech-pulse/main/images/industrial-iot/industrial-iot/0051-MR.png)
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`

-----

### Maturity Models
![MM](https://raw.githubusercontent.com/kranthiB/tech-pulse/main/images/industrial-iot/industrial-iot/0052-MM.png)
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`
 * `<<PLACEHOLDEER>> - <<PLACEHOLDEER>> - <<PLACEHOLDEER>>`

-----
