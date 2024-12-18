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
   
`First Industrial Revolution (18th Century)`
   * *Automation of Physical Labor*
     * Water/Stream Power
       * The introduction of water-powered machinery marked a significant milestone in automation. 
     * First Mechanical Loom
       * The invention of the mechanical loom revolutionized textile production, increasing efficiency and output 
     * Power - Coal
       * Coal became a primary source of energy for industrial processes, driving growth and development. 
     * Mobility - Rail/Ship Networks, Steam Engine
       * Advances in transportation enabled rapid movement of goods and people, further facilitating economic expansion.
          
`Second Industrial Revolution (19th Century)`
   * *Automation/Rationalization of Physical Labor*
     * Electricity-Powered Mass Production
       * The widespread adoption of electricity transformed manufacturing processes, allowing for faster and more efficient production 
     * First Production Lines
       * Assembly lines became a standard feature in factories, streamlining production and increasing productivity 
     * Power - Oil/Gas
       * Fossil fuels emerged as a primary source of energy, fueling further industrialization. 
     * Mobility - Planes, Oil-Powered Ships, Automobiles
       * Advances in transportation led to the development of new modes of travel, transforming global connectivity.

`Third Industrial Revolution (20th Century)`
   * *Automation of Individual Entities in an Organization*
     * Computers/Sensors
       * The rise of computers and sensors enabled automation within individual entities, enhancing efficiency and accuracy. 
     * First Programmable Logic Controller (PLC)
       * The introduction of PLCs revolutionized industrial control systems, allowing for greater flexibility and adaptability. 
     * Power - Renewables
       * Renewable energy sources began to gain prominence, reducing reliance on fossil fuels and promoting sustainability. 
     * Mobility - Satellite-Based Navigational Aids
       * Advances in satellite technology enabled precise navigation and communication, transforming industries such as aviation and maritime

`Fourth Industrial Revolution`
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
`Characteristics of Smart Manufacturing:`
   * *Digitization:* The integration of digital technologies to create a virtual representation of the physical world.
   * *Connected Devices and Distributed Intelligence for Real-Time Control:* The use of sensors, actuators, and control systems to monitor and control production processes in real-time.
   * *Collaborative Supply Chain Management:* The integration of supply chain management with manufacturing to optimize inventory levels, reduce lead times, and improve customer satisfaction.
   * *Energy and Resource Efficiency through Optimal Decision-Making:* The use of data analytics and machine learning algorithms to make informed decisions about energy consumption, resource allocation, and production planning.
   * *Advanced Sensors and Big Data Analytics Integrated into Product Lifecycle:* The integration of sensors and big data analytics to monitor product performance, predict maintenance needs, and optimize product design.
     
`Manufacturing Paradigms:`
   * *Lean Manufacturing:* A paradigm that focuses on minimizing waste and maximizing value-added activities through continuous improvement and elimination of non-value-added tasks.
   * *Cloud Manufacturing:* A paradigm that leverages cloud computing to enable flexible, scalable, and collaborative manufacturing processes.
   * *Intelligent Manufacturing:* A paradigm that incorporates artificial intelligence, machine learning, and data analytics to optimize production planning, quality control, and maintenance.
   * *Holonic Manufacturing:* A paradigm that uses multi-agent systems, decentralized decision-making, and model-based reasoning to create self-organizing production systems.
   * *Agile Manufacturing:* A paradigm that focuses on rapid response to changing market demands through flexible and adaptable manufacturing processes.
   * *Digital Manufacturing:* A paradigm that leverages digital technologies such as 3D printing, simulation, and virtual reality to design, test, and manufacture products virtually.
   * *Sustainable Manufacturing:* A paradigm that prioritizes environmental sustainability by reducing waste, conserving resources, and promoting eco-friendly practices throughout the product lifecycle.
   * *Flexible Manufacturing:* A paradigm that enables rapid changeover between different production runs through modularized designs, interoperability, and real-time visualization.
   * *Intelligent Manufacturing:* A paradigm that incorporates artificial intelligence, advanced sensing, control systems, optimization techniques, and knowledge management to optimize production processes.
     
`Benefits of Smart Manufacturing:`
   * *Increased Efficiency:* Smart manufacturing enables automation, streamlines processes, and reduces labor costs.
   * *Improved Product Quality:* Advanced sensors and analytics ensure consistent product quality, reducing defects and rework.
   * *Enhanced Customer Experience:* Smart manufacturing allows for real-time monitoring, predictive maintenance, and personalized products tailored to customer needs.
   * *Reduced Costs:* Smart manufacturing optimizes resource allocation, reduces energy consumption, and minimizes waste.
   * *Increased Competitiveness:* Smart manufacturing enables businesses to stay competitive in the global market by offering innovative products, services, and experiences. 
`Challenges and Limitations:`
   * *High Initial Investment:* Implementing smart manufacturing technologies requires significant upfront investments in hardware, software, and training.
   * *Integration Challenges:* Integrating different systems, devices, and data sources can be complex and time-consuming.
   * *Cybersecurity Risks:* Smart manufacturing introduces new cybersecurity risks due to the increased connectivity and data exchange between devices and systems.
   * *Skills Gap:* The adoption of smart manufacturing requires a significant shift in workforce skills, which can be challenging for companies to implement.
     
`Future Directions:`
   * *Artificial Intelligence and Machine Learning:* AI and ML will play an increasingly important role in optimizing production processes, predicting maintenance needs, and improving product quality.
   * *Internet of Things (IoT):* IoT will continue to expand its presence in manufacturing, enabling real-time monitoring, remote access, and predictive maintenance.
   * *5G Networks:* 5G networks will provide faster data transfer rates, lower latency, and increased connectivity, enabling more widespread adoption of smart manufacturing technologies.
   * *Sustainability and Environmental Impact:* Smart manufacturing will prioritize environmental sustainability by reducing waste, conserving resources, and promoting eco-friendly practices throughout the product lifecycle. 

-----

### Evolution of Digital Manufacturing
![EDM](https://raw.githubusercontent.com/kranthiB/tech-pulse/main/images/industrial-iot/industrial-iot/0003-EDM.png)
Digital manufacturing has revolutionized the way products are designed, manufactured, and delivered. From its humble beginnings in the 1970s to the present day, digital manufacturing has evolved significantly, driven by advances in technology, changing business needs, and shifting consumer demands.

`Notable Milestones`
   * *The Early Days of Digital Manufacturing*
     * Digital manufacturing began in the 1970s with the introduction of computer-aided design (CAD) software. CAD allowed designers to create detailed designs on computers, replacing traditional drafting methods. This marked the beginning of a new era in product development, enabling faster and more accurate design iterations. 
   * *The Rise of Computer-Aided Manufacturing (CAM)*
     * In the 1980s, computer-aided manufacturing (CAM) emerged as a natural extension of CAD. CAM software enabled manufacturers to create detailed instructions for machine tools, automating many production processes. This led to significant improvements in productivity and efficiency. 
   * *The Advent of Digital Mockups*
     * The 1990s saw the introduction of digital mockups, which allowed designers to create virtual prototypes of products or systems. This enabled faster testing and validation of designs, reducing the need for physical prototypes and accelerating time-to-market. 
   * *Collaborative Design and Manufacturing*
     * In the 2000s, collaborative design and manufacturing became increasingly important. Digital platforms enabled global teams to work together seamlessly, sharing data and expertise in real-time. This led to significant improvements in product quality, reducing errors and defect 
   * *The Internet of Things (IoT) and Industry 4.0*
     * The 2010s saw the rise of the Internet of Things (IoT) and Industry 4.0. IoT enabled the integration of sensors, actuators, and other devices into products and systems, creating a new level of connectivity and automation. Industry 4.0 built on this foundation, introducing advanced manufacturing technologies such as robotics, artificial intelligence, and cybersecurity.

`Impact on Industry`
   * The evolution of digital manufacturing has had a profound impact on various industries, including:
     * *Reduced production costs:* Automation and digitalization have led to cost savings and increased efficiency.
     * *Improved product quality:* Digital tools enable precise design and manufacturing, resulting in higher-quality products.
     * *Enhanced collaboration:* Global teams can collaborate more effectively using digital mockups and collaborative design tools.
     * *Increased speed-to-market:* Rapid prototyping and testing capabilities have accelerated the development cycle.

`Future of Digital Manufacturing`
   * As we look to the future, digital manufacturing will continue to evolve rapidly. Emerging trends include:
     * *Artificial Intelligence (AI):* AI will play an increasingly important role in product development, enabling designers to create more complex and sophisticated products.
     * *Blockchain:* Blockchain technology will provide a secure and transparent way to track products throughout their lifecycle.
     * *5G Networks:* 5G networks will enable faster and more reliable connectivity, supporting the growth of IoT and Industry 4.0.  

-----

### Discrete vs Process Manufacturing
![DMPM](https://raw.githubusercontent.com/kranthiB/tech-pulse/main/images/industrial-iot/industrial-iot/0004-DMPM.png)

`Discrete Manufacturing`
  * *Definition*
    * Discrete manufacturing involves creating products that are comprised of parts that can be easily touched, counted, sourced, or broken down at the end of their product lifecycle. This type of manufacturing is characterized by the production of individual units or components that are assembled together to form a final product.
  * *Characteristics*
    * Products are made up of discrete components
    * Parts can be broken down and recycled at the end of their product lifecycle
  * *Benefits*
    * Flexibility in production planning and scheduling
    * Ability to produce complex products with multiple parts
    * High level of control over the production process
  * *Challenges*
    * Higher upfront costs due to specialized equipment and training
    * Increased risk of errors or defects during production
    * Limited flexibility in responding to changes in market demand
  * *Industry Examples*
    * *Automotive industry:* discrete manufacturing is used to produce individual components such as engines, transmissions, and chassis.
    * *Electronics industry:* discrete manufacturing is used to produce individual components such as microprocessors, memory chips, and circuit boards.

`Process Manufacturing`
  * *Definition*
    * Process manufacturing involves transforming raw materials into intermediate goods through various processes. This type of manufacturing is characterized by the production of large quantities of standardized products using continuous processing techniques.
  * *Characteristics*
    * Products are created through a series of chemical or physical transformations
    * Raw materials are transformed into intermediate goods through various processes
  * *Benefits*
    * High level of efficiency and productivity due to automation and continuous processing
    * Ability to produce large quantities of standardized products quickly and efficiently
    * Lower upfront costs compared to discrete manufacturing
  * *Challenges*
    * Limited flexibility in responding to changes in market demand
    * Higher risk of errors or defects during production due to complex processes
    * Dependence on raw materials and suppliers
  * *Industry Examples*
    * *Pharmaceutical industry:* process manufacturing is used to transform raw materials into intermediate goods such as APIs (Active Pharmaceutical Ingredients) and finished dosage forms.
    * *Food processing industry:* process manufacturing is used to transform raw ingredients into final products such as beverages, snacks, and prepared meals.

-----

### Key Capabilities
![KP](https://raw.githubusercontent.com/kranthiB/tech-pulse/main/images/industrial-iot/industrial-iot/0005-KP.png)

Smart Manufacturing is a multifaceted concept that encompasses various aspects of production, including cost control and differentiation through four key areas: Productivity, Quality, Agility, and Sustainability.
These dimensions are interconnected and interdependent, working together to drive innovation, efficiency, and competitiveness in the manufacturing sector. By understanding these perspectives, businesses can better navigate the complexities of smart manufacturing and make informed decisions that align with their strategic goals

`Cost Control`
  * *Economic Benefits*: Customers are looking for cost-effective solutions that can help them save money on operational expenses.
    * This includes reducing energy consumption, minimizing waste, and optimizing resource allocation.
    * By implementing smart manufacturing technologies, customers can achieve significant cost savings and improve their bottom line.
  * *Efficiency and Productivity*: Customers want to see improvements in efficiency and productivity, as this will enable them to produce more with less effort and resources.
    * This includes streamlining processes, reducing downtime, and increasing throughput.
    * By leveraging smart manufacturing technologies, customers can achieve greater efficiency and productivity, leading to increased competitiveness and profitability.
  * *Innovation and Efficiency*: Customers are interested in innovative solutions that can help them stay ahead of the competition.
    * This includes adopting new technologies such as artificial intelligence (AI), machine learning (ML), and the Internet of Things (IoT).
    * By embracing these innovations, customers can gain a competitive edge and improve their overall performance.

`Differentiation`
  * *Quality and Reliability*: Customers place a high value on quality and reliability in their products.
    * This includes ensuring that products meet or exceed customer expectations in terms of performance, durability, and safety.
    * By implementing smart manufacturing technologies, customers can achieve higher levels of quality and reliability, leading to increased customer satisfaction and loyalty.
  * *Customization and Flexibility*: Customers are looking for manufacturers who can offer customized solutions tailored to their specific needs.
    * This includes providing flexible production processes that can accommodate changes in demand or product requirements.
    * By leveraging smart manufacturing technologies, customers can achieve greater customization and flexibility, enabling them to respond quickly to changing market conditions.
  * *Sustainability and Environmental Responsibility*: Customers are increasingly concerned about the environmental impact of their products and operations.
    * This includes reducing waste, minimizing energy consumption, and using sustainable materials.
    * By implementing smart manufacturing technologies, customers can achieve significant reductions in their environmental footprint, improving their reputation and competitiveness.

-----

### Design Principles & Smart System Elements
![DPSSE](https://raw.githubusercontent.com/kranthiB/tech-pulse/main/images/industrial-iot/industrial-iot/0006-DPSSE.png)
A comprehensive framework for designing and implementing industrial production systems in the modern era.

`Core Components`
  * *Interoperability*: This concept refers to the seamless integration and communication between various devices, systems, and software platforms within a manufacturing system. Interoperability enables different components to exchange data and work together efficiently.
  * *Virtualization*: Virtualization involves creating virtual representations of physical assets or processes in a digital environment. It allows for simulations, modeling, and analysis without the need for physical prototypes.
  * *Decentralization*: Decentralized systems distribute decision-making authority among various nodes or components within the system. This approach enhances flexibility, resilience, and adaptability.

`Key Principles`
  * *Modularity*: Modular systems consist of interchangeable components that can be easily reconfigured or replaced. This design principle promotes flexibility and reduces waste.
  * *Service orientation*: Smart manufacturing emphasizes providing services rather than just products. This approach enables businesses to offer customized solutions, enhance customer experience, and create new revenue streams.

`Smart System Elements`
  * *Self-awareness/ Autonomy*: Smart manufacturing systems are equipped with sensors and data analytics capabilities that enable them to monitor their own performance and make adjustments in real-time
  * *Connectivity*: These systems are connected through various networks (e.g., IoT, cloud computing) to facilitate data exchange and collaboration among different stakeholders.
  * *Data-driven decision-making*: Smart manufacturing relies heavily on data analysis and AI algorithms to optimize production processes, predict maintenance needs, and improve overall efficiency.
  * *Autonomous analytics on data to decide (Monitor / Diagnose / Correct)*: These systems use AI-powered tools to analyze vast amounts of data in real-time, enabling them to identify issues, predict maintenance needs, and optimize production processes.
  * *New design, manufacturing and communication technologies*: Smart manufacturing incorporates cutting-edge technologies like 3D printing, augmented reality (AR), and the Internet of Things (IoT) to streamline operations, improve product quality, and enhance collaboration among stakeholders.

-----

### Ecosystem
![ES](https://raw.githubusercontent.com/kranthiB/tech-pulse/main/images/industrial-iot/industrial-iot/0007-ES.png)
`Product Lifecycle Management (PLM)`
  * PLM is a set of business processes and tools that enable companies to design, manufacture, and manage products throughout their lifecycle.
  * *Capability Mapping*:
      * *Agility*: PLM enables rapid product development and iteration, allowing companies to quickly respond to changing market conditions.
      * *Quality*: PLM ensures that products meet quality standards by managing data across the entire product lifecycle.
      * *Sustainability*: PLM helps reduce waste and improve resource efficiency by optimizing production processes and supply chains.

`Supply Chain Management (SCM)`
  * SCM is a set of activities involved in sourcing, producing, and delivering products to customers.
  * *Capability Mapping*:
      * *Productivity*: SCM optimizes the flow of goods, services, and related information from raw materials to end customers, improving productivity and efficiency.
      * *Agility*: SCM enables rapid response to changing market conditions by streamlining supply chain operations.
      * *Quality*: SCM ensures that products meet quality standards by managing data across the entire supply chain.

`Design for Supply Chain Management (DFSCM)`
  * DFSCM is a design approach that considers the impact of product design on supply chain operations and costs
  * *Capability Mapping*:
      * *Agility*: DFSCM enables rapid response to changing market conditions by designing products that are easy to manufacture and distribute.
      * *Quality*: DFSCM ensures that products meet quality standards by considering the impact of design on supply chain operations.

`Continuous Process Improvement (CPI)`
  * CPI is a methodology for ongoing improvement of business processes based on data-driven insights.
  * *Capability Mapping*:
      * *Productivity*: CPI identifies areas for process optimization, leading to increased productivity and efficiency.
      * *Quality*: CPI ensures that products meet quality standards by continuously monitoring and improving production processes.
      * *Sustainability*: CPI helps reduce waste and improve resource efficiency by optimizing production processes and supply chains.

`Continuous Commissioning (CCX)`
  * CCX is a methodology for ongoing improvement of industrial operations based on data-driven insights
  * *Capability Mapping*:
      * *Productivity*: CCX identifies areas for process optimization, leading to increased productivity and efficiency.
      * *Agility*: CCX enables rapid response to changing market conditions by streamlining production processes.
      * *Quality*: CCX ensures that products meet quality standards by continuously monitoring and improving production processes.
      * *Sustainability*: CCX helps reduce waste and improve resource efficiency by optimizing production processes and supply chains.

`Design for Manufacturing and Assembly (DFMA)`
  * DFMA is a design approach that considers the impact of product design on manufacturing and assembly operations and cost
  * *Capability Mapping*:
      * *Productivity*: DFMA enables rapid response to changing market conditions by designing products that are easy to manufacture and assemble.
      * *Agility*: DFMA ensures that products meet quality standards by considering the impact of design on manufacturing and assembly operations.

`Flexible / Reconfiguration Manufacturing System (FMS/RMS)`
  * FMS/RMS is a system that enables rapid reconfiguration of production lines to respond to changing market conditions.
  * *Capability Mapping*:
      * *Agility*: FMS/RMS enables rapid response to changing market conditions by streamlining production processes.

`Manufacturing Pyramid`
  * Manufacturing pyramid is a framework for designing and implementing industrial production systems that are highly efficient, agile, and adaptable.
  * *Capability Mapping*:
      * *Productivity*: Manufacturing pyramid optimizes the flow of goods, services, and related information from raw materials to end customers, improving productivity and efficiency.
      * *Agility*: Manufacturing pyramid enables rapid response to changing market conditions by streamlining production processes.
      * *Quality*: Manufacturing pyramid ensures that products meet quality standards by managing data across the entire supply chain.
      * *Sustainability*: Manufacturing pyramid helps reduce waste and improve resource efficiency by optimizing production processes and supply chains.

`Fast Innovation Cycle`
  * Fast innovation cycle is a methodology for rapid product development and iteration, enabling companies to quickly respond to changing market conditions.
  * *Capability Mapping*:
      * *Agility*: Fast innovation cycle enables rapid response to changing market conditions by streamlining production processes.
      * *Quality*: Fast innovation cycle ensures that products meet quality standards by continuously monitoring and improving production processes.

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
