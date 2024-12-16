---
id: ops-mastery/dev-sec-ops
title: DevSecOps
sidebar_label: DevSecOps
next_page: ops-mastery/git-ops
---

Table of contents
=================

<!--ts-->
   * [Foundations](#foundations)
      * [Secure Software Development Framework](#secure-software-development-frameworkssdf)
      * [Software Supply Chain Continuum](#software-supply-chain-continuum)
      * [Evolution of Best Practices](#evolution-of-best-practices)
      * [DORA Capabilities](#dora-capabilities)
   * [DevSecOps](#devsecops)
      * [Conceptual Model](#conceptual-model)
      * [Core Practices](#core-practices)
         * [Analyze](#analyze)
         * [Secure](#secure)
         * [Verify](#verify)
         * [Defend](#defend)
         * [Additional Practices](#additional-practices)
      * [Lifecycle Phases](#lifecycle-phases)
      * [Continuous Feedback Loops](#continuous-feedback-loops)
      * [Activities & Tools](#activities-n-tools)
         * [Continuous Security](#continuous-security)
         * [Continuous Testing](#continuous-testing)
         * [Configuration Management](#configuration-management)
      * [SMART Metrics](#smart-metrics)
         * [Specific](#specific)
         * [Measurable](#measurable)
         * [Attainable](#attainable)
         * [Relevant](#relevant)
         * [Time Bound](#time-bound)
   * [References](#references)
      * [Container Application Pipeline Reference](#container-application-pipeline-reference)
      * [Enterprise DevSecOps](#enterprise-devsecops)
         * [CNCF Certified Kubernetes](#cncf-certified-kubernetes)
            * [Sidecar Container Security Stack (SCSS)](#sidecar-container-security-stack-scss)
         * [Multi-Cluster CNCF Kubernetes](#multi-cluster-cncf-kubernetes)
            * [K8s Global & Regional Control Plane](#k8s-global--regional-control-plane)
         * [AWS Managed Services](#aws-managed-services)
         * [Microsoft Azure + GitHub](#microsoft-azure--github)
         * [Container Monitoring Reference](#container-monitoring-reference)
   * [Patterns & Anti-Patterns](#patterns-antipatterns)
      * [Continuous Integration](#continuous-integration)
      * [Continuous Delivery](#continuous-delivery)
<!--te-->


## Foundations

### Secure-Software-Development-Framework(SSDF)
![SSDF](https://raw.githubusercontent.com/kranthiB/tech-pulse/main/images/ops-mastery/dev-sec-ops/0001-SSDF.png)

 * The importance of Secure Software Development: A comprehensive guide
   * `Prepare the Organization`
     * *Laying the Foundation: Setting Up Your Team for Success*
       * Establish clear security requirements and goals
       * Define roles and responsibilities within the organization
       * Implement a culture of security awareness and education
     * *Security is Not Just an IT problem, it's Everyone's Responsibility*
       * Explain how security affects all departments and stakeholders
       * Discuss the importance of collaboration and communication in security efforts
       * Provide examples of successful team-based security initiatives
   * `Protect the Software`
     * *The First Line of Defense: Protecting Your Code from Threats*
       * Explain the importance of code protection and encryption
       * Discuss various methods for protecting code, such as obfuscation and watermarking
       * Provide examples of successful code protection strategies
     * *Don't Let Bugs Bite: How to Secure Your Software from Within*
       * Discuss common software vulnerabilities and how to prevent them
       * Explain the importance of testing and quality assurance in security
       * Provide tips for identifying and fixing bugs that can compromise security
   * `Produce Well-Secured Software`
     * *Designing Security into Your Product: A Winning Strategy*
       * Explain how to incorporate security into the software development lifecycle
       * Discuss the importance of secure design principles and patterns
       * Provide examples of successful secure design initiatives
     * *The Art of Secure Coding: Tips and Tricks for Writing Secure Code*
       * Discuss common coding mistakes that can compromise security
       * Explain how to use secure coding practices, such as input validation and error handling
       * Provide tips for writing robust and secure code
   * `Respond to Vulnerabilities`
     * *The Threat is Real: How to Respond to Vulnerabilities in Your Software*
       * Explain the importance of vulnerability management and response
       * Discuss various methods for responding to vulnerabilities, such as patching and mitigation
       * Provide examples of successful vulnerability response initiatives
     * *Don't Panic! A Step-by-Step Guide to Responding to Security Incidents*
       * Explain the importance of having a incident response plan in place
       * Discuss various steps for responding to security incidents, such as containment and eradication
       * Provide tips for minimizing downtime and reducing the impact of security incidents

-----

### Software-Supply-Chain-Continuum
![SSCC](https://raw.githubusercontent.com/kranthiB/tech-pulse/main/images/ops-mastery/dev-sec-ops/0002-SSCC.png)

 * The Software Supply Chain Continuum is a conceptual framework that represents the flow of software development and deployment from its inception to its final delivery to users. It encompasses various stages, including hardware, software, and data collection, processing, and analysis
   * **Hardware**
     * *Sensors*: These are devices that detect and measure physical phenomena such as temperature, pressure, light, or sound
     * *IoT (Internet of Things)*: This refers to the network of physical devices embedded with sensors, software, and connectivity, allowing them to collect and exchange data
     * *5G*: The fifth generation of wireless network technology, offering faster data rates, lower latency, and greater connectivity
       
   * **Software**
     * *Cloud Native Applications*: A set of principles and practices for building software applications that are designed to run on cloud infrastructure, including scalability, flexibility, and automation.
     * *DevSecOps (Development Security Operations)*: An approach that integrates security into the development process, enabling faster and more secure delivery of software applications.It involves using tools like Jenkins, Docker, and Kubernetes to automate the build, deployment, and monitoring of applications
     * *Artificial Intelligence (AI)*: AI refers to the development of computer systems that can perform tasks that typically require human intelligence, such as visual perception, speech recognition, decision-making, and language translation.
       
   * **Data Collection, Processing, and Analysis**
     * *Big Data*: Big data refers to the large volume of structured and unstructured data that is generated by various sources, including social media, sensors, and IoT devices.
     * *Machine Learning (ML)*: ML is a subset of AI that involves training algorithms on data to enable them to make predictions or decisions without being explicitly programmed.

   * **Software Hub**: A centralized platform for managing software applications, including version control, deployment, and monitoring.
     
   * **CSP (Cloud Service Provider) Managed Service**
     * A Cloud Service Provider (CSP) managed service is a type of cloud computing model where the provider manages the entire lifecycle of a software application, including development, deployment, and maintenance. This approach allows businesses to focus on their core competencies while leaving the technical aspects of software management to the CSP
     * **Key Benefits**
       * *Reduced Costs*: By outsourcing software management to a CSP, businesses can reduce their operational costs associated with managing in-house IT teams.
       * *Improved Efficiency*: CSPs have extensive experience and expertise in managing complex software applications, ensuring that they are running smoothly and efficiently.
       * *Enhanced Security*: CSPs typically have robust security measures in place to protect against cyber threats and data breaches.
     * **Types of CSP Managed Services**
       * *IaaS (Infrastructure as a Service)*: IaaS is a cloud computing model where the CSP provides virtualized computing resources, such as servers, storage, and networking.
       * *PaaS (Platform as a Service)*: PaaS is a cloud computing model where the CSP provides a platform for developing, running, and managing applications without the need for underlying infrastructure.
       * *SaaS (Software as a Service)*: SaaS is a cloud computing model where the CSP hosts software applications over the internet, eliminating the need for on-premises installation and maintenance.

-----

### Evolution-of-Best-Practices
![EBSD](https://raw.githubusercontent.com/kranthiB/tech-pulse/main/images/ops-mastery/dev-sec-ops/0003-EBSD.png)

 * This represents evolution of best practices in software development, showcasing how various technologies and approached have transformed over time
   * **Development Process**
     * The traditional **waterfall** approach, which dominated in the past, is characterized by a linear sequence of phases with little overlap or iteration.
     * As software development evolved, **agile** methodologies emerged as an alternative, emphasizing flexibility, collaboration, and rapid delivery of working software through iterative and incremental development.
     * In recent years, the **devops** culture has gained popularity, focusing on bridging the gap between development and operations teams through collaboration, automation, and continuous delivery.
   * **Application Architecture**
     * In the past, **monolithic architecture** was prevalent, where a single unit contained all the functionality of an application.
     * However, with the rise of **microservices-based architecture**, applications are now designed as collections of small services that communicate with each other to achieve specific goals. This approach allows for greater scalability and flexibility, enabling organizations to respond quickly to changing market conditions
     * In recent years, **serverless computing** has gained popularity, allowing developers to focus on writing code without worrying about infrastructure management. This approach enables businesses to scale their applications more efficiently and reduce costs associated with managing servers
   * **Deployment & Packaging**
     * Historically, **physical deployments** were the standard practice, with applications being directly installed on hardware devices. However, the emergence of virtualization transformed this landscape by offering a cost-effective alternative.
     * **Virtualization** brought forth numerous benefits, including enhanced resource utilization and reduced costs. By allowing multiple virtual machines to run on a single physical host, organizations could optimize their infrastructure without incurring significant capital expenditures.
     * Fast-forwarding to recent years, **containers** have gained widespread adoption due to their lightweight and efficient nature. This innovation enables faster deployment cycles by providing a consistent and reliable environment for applications to operate within. The advent of containerization has significantly impacted the way organizations deploy and manage applications, empowering them to respond more quickly to shifting business requirements.
     * The shift from physical deployments to virtualized environments, and subsequently to containerized solutions, reflects an ongoing quest for greater **efficiency** and **agility** in application delivery. As technology continues to evolve, it is likely that even newer approaches will emerge to further enhance the deployment experience.
   * **Hosting Infrastructure**
     * The transition from **on-premises** hosting to **cloud computing** has unlocked significant benefits for organizations. This shift has afforded them greater flexibility, scalability, and cost savings
     * **Cloud computing's inherent agility** allows businesses to dynamically adjust their resource allocation according to demand, without the need for expensive hardware upgrades or large-scale IT investments. As a result, organizations can more effectively manage their resources and optimize their spending.
     * In response to the evolving cloud landscape, many organizations are now adopting **multi-cloud strategies** as a means of mitigating vendor lock-in risks. This approach enables businesses to select the most suitable services from multiple providers, rather than being confined to a single platform. By diversifying their cloud footprint, organizations can enhance their resilience and adaptability, better equipping them to navigate the complexities of an ever-changing business environment.
   * **Data Management**
     * The traditional approach to managing vast amounts of data centered around **data warehousing**, which had been the dominant paradigm for decades. However, as the volume and complexity of data continued to grow exponentially, organizations began to seek out more innovative solutions.
     * This led to the widespread adoption of **big data technologies** such as Hadoop and Spark, which enabled businesses to efficiently handle and process large volumes of structured and unstructured data. These tools revolutionized the way companies approached data management, empowering them to unlock new insights and drive business growth.
     * In recent years, the landscape has continued to evolve with the emergence of **cloud-native data platforms**. These cutting-edge solutions offer unparalleled scalability and cost-effectiveness, allowing businesses to store, process, and analyze massive datasets with unprecedented ease and speed.
     * Platforms such as Amazon Redshift and Google BigQuery have redefined the boundaries of data management, providing organizations with a flexible and efficient way to harness the power of their data. By leveraging these cloud-native solutions, companies can gain a deeper understanding of their operations, make more **informed decisions**, and stay ahead of the competition in an increasingly data-driven world.
   * **Data Interchange**
     * For decades, **XML** was the de facto standard for data exchange between applications, facilitating communication across disparate systems. However, as technology advanced, organizations began to seek out more streamlined alternatives.
     * The rise of **JSON** as a lightweight and user-friendly format marked a significant shift in this landscape. Its simplicity and flexibility made it an attractive choice for developers, who appreciated its ease of implementation and integration with various platform
     * In recent years, the evolution of data exchange has accelerated further with the advent of **GraphQL**. This innovative query language for APIs empowers clients to specify precisely what they need from the server, thereby optimizing resource utilization and minimizing data transfer.
   * **Cybersecurity Posture**
     * Historically, **traditional security measures** such as firewalls and intrusion detection systems were the norm for protecting against external threats. However, this approach was often static and reactive in nature, struggling to keep pace with the evolving threat landscape.
     * The advent of **cloud-based security solutions** marked a significant shift towards more dynamic and adaptive security strategies. Organizations began to adopt scalable and user-friendly tools like AWS IAM and Azure Active Directory, which offered a more robust and secure way to manage user identities and access controls
     * In recent years, **zero-trust architecture** has emerged as a critical component of modern cybersecurity strategies. This innovative approach assumes that all users and devices are potential threats, requiring verification and validation before granting access to sensitive resources. By adopting a zero-trust mindset, businesses can significantly reduce their attack surface and improve their overall cybersecurity posture.

-----

### DORA-Capabilities
![DORA](https://raw.githubusercontent.com/kranthiB/tech-pulse/main/images/ops-mastery/dev-sec-ops/0004-DORA.png)

 * **Technical**
   * `Why Use Cloud Infrastructure?`
     * It can quickly *scale up or down* as needed, ensuring resources are available when required. This approach is also *cost-effective*, as users only pay for what they use, unlike traditional on-premises solutions. Additionally, cloud infrastructure provides *flexibility* in deployment options, allowing users to choose between public, private, or hybrid cloud models to suit their needs.
   * `Why Use Code Maintainability?`
     * It helps *reduce technical debt*, making it easier to work with the code in the future. This also *makes collaboration among team members smoother*, as everyone can understand the codebase more easily. Furthermore, having well-maintained code allows developers to make changes quickly and confidently, which can *speed up the time* it takes for new features or updates to be released 
   * `Why Use Continuous Delivery?`
     * Continuous delivery can help *improve efficiency* in several ways.It automates tasks such as testing, deployment, and monitoring, freeing up developers' time for more important tasks. This approach also ensures that software is thoroughly tested before it's released, which leads to *higher quality* products. 
   * `Why Use Test Automation?`
     * It *saves time* by automating repetitive testing tasks, allowing teams to focus on more complex scenarios. This also ensures that the software is thoroughly tested before it's released, leading to *higher quality products*. 
   * `Why Use Database Change Management?`
     * Database change management is an important process. It helps maintain *data integrity* by controlling changes made to the database schema, which ensures that data remains accurate and reliable. 
   * `Why Use Empowering Teams to Choose Tools?`
     * When teams are given the freedom to select their own tools, it can have several benefits. This *increased autonomy* allows them to make decisions that are tailored to their specific needs, which can lead to *improved collaboration* among team members. Since everyone is working with familiar tools and processes, communication and cooperation become more efficient.
   * `Why Use Loosely Coupled Architecture?`
     * It allows teams to make changes to one part of the system without affecting other parts, which *improves flexibility* and makes it easier to adapt to changing needs. This approach also *reduces risk*, as changes are isolated and won't have unintended consequences elsewhere in the system.
   * `Why Use Monitoring and Observability?`
     * They provide *improved visibility* into system performance, enabling teams to identify issues quickly. This also *reduces downtime*, as teams can detect and respond to problems before they become major issues.
   * `Why Use Shifting Left on Security?`
     * It *improves security* by integrating security considerations into the development process from the start, which helps prevent potential vulnerabilities. This approach also *reduces risk* by identifying and addressing security issues early in the development cycle, rather than later down the line. 
   * `Why Use Testing Data Management?`
     * It *improves test coverage* by ensuring that all possible scenarios are thoroughly tested, which reduces the likelihood of unforeseen issues. 
   * `Why Use Trunk-Based Development?`
     * It *improves collaboration* among teams by enabling them to work together on a single codebase, which facilitates communication and reduces conflicts
       
 * **Process**
   * `Why Use Customer Feedback?`
     * Customer feedback is essential for improving product quality and overall customer experience. It *improves product quality* by ensuring that products meet customer needs and expectations, resulting in a more satisfying and effective solution. Additionally, it *increases customer satisfaction* by enabling organizations to address customer concerns and improve their overall experience 
   * `Why Use Monitoring Systems to Inform Business Decisions?`
     * They provide real-time data that informs business decisions, enabling organizations to respond quickly to changing market conditions. This enables *better decision making* and helps *mitigate risks* by identifying potential issues before they become major problem
   * `Why Use Proactive Failure Notification?`
     * It *reduces downtime* by enabling organizations to respond quickly to failures, minimizing the disruption to business operations. This approach also *improves uptime* by identifying potential issues before they cause failures, which helps prevent unexpected outages
   * `Why Use Streamlining Change Approval?`
     * It *reduces time-to-market* by enabling organizations to make changes quickly, without unnecessary delays, allowing them to adapt faster to changing market conditions. This approach also *improves collaboration* among stakeholders by ensuring that everyone is aligned on changes, reducing misunderstandings and miscommunications. Additionally, streamlining change approval *increases efficiency* by automating routine tasks, freeing up resources for more strategic activities and enabling teams to focus on higher-value tasks 
   * `Why Use Team Experimentation?`
     * It *encourages innovation* by allowing teams to experiment with new ideas and approaches, fostering a culture of creativity and entrepreneurship.
   * `Why Use Visibility of Work in the Value Stream?`
     * It *improves collaboration* among stakeholders by ensuring that everyone has a clear understanding of their role and how it contributes to overall goals, facilitating communication and alignment across teams. Also, *reduces waste* by enabling organizations to eliminate unnecessary steps and activities, streamlining workflows and improving productivity
   * `Why Use Visual Management?`
     * It *improves communication* by providing a clear and concise way to convey information and goals to all stakeholders, ensuring that everyone is aligned and working towards the same objectives. This approach also *increases transparency* by providing real-time visibility into progress and performance, enabling teams to make data-driven decisions based on facts rather than assumptions. Additionally, visual management *encourages accountability* by holding individuals and teams responsible for their actions and outcomes, promoting a culture of ownership and responsibility within the organization. 
   * `Why Use Work in Process Limits?`
     * It *improves efficiency* by ensuring that work is not over-subscribed, reducing delays and increasing productivity as teams are able to manage their workload effectively. This approach also *reduces bottlenecks* by identifying areas where capacity needs to be increased or improved processes implemented, helping to smooth out workflows and prevent congestion. 
   * `Why Use Working in Small Batches?`
     * It *improves quality* by enabling teams to focus on one task at a time, reducing errors and improving overall performance as they are able to concentrate on a single objective without distractions
      
 * **Culture**
   * `Why Develop a Generative Organizational Culture?`
     *  It *fosters innovation* by encouraging experimentation, creativity, and risk-taking, allowing teams to explore new ideas and approaches.
     *  This approach also *encourages collaboration* by promoting open communication, mutual respect, and trust among team members, breaking down silos and enabling cross-functional teamwork.
     *  Additionally, a generative organizational culture *increases employee engagement* by providing a sense of purpose, autonomy, and growth opportunities, leading to higher job satisfaction and reduced turnover rates.
     *  Furthermore, it *improves adaptability* by enabling teams to respond quickly to changing market conditions and customer needs, allowing the organization to stay agile and competitive in an ever-evolving landscape.
   
    * `Why Focus on Job Satisfaction?`
     *  It *boosts productivity* by increasing motivation, engagement, and overall well-being of employees, leading to improved work quality and efficiency.
     *  By focusing on job satisfaction, organizations can *reduce turnover*, creating a positive work environment that retains top talent and reducing the costs associated with recruiting and training new employees.
     *  A focus on job satisfaction *enhances reputation* by creating a positive employer brand that attracts top candidates, making it easier for organizations to attract and retain top talent in the future.
   *  `Why Develop a Learning Culture?`
     *  It encourages *continuous improvement* by promoting ongoing learning, experimentation, and innovation, allowing teams to stay ahead of the curve and respond quickly to changing market conditions.
     *  It *increases competitiveness* by staying ahead of industry trends, technologies, and best practices, giving the organization a competitive edge in the market.
     *  This approach also *fosters adaptability* by enabling teams to pivot when necessary, ensuring that the organization remains agile and responsive to customer needs.
   *  `Why Adopt Transformational Leadership?`
     *  Essential for organizations that want to thrive in today's complex and rapidly changing business landscape. It enables teams to stay adaptable, innovative, and responsive to changing conditions, ultimately driving growth and success

-----

## DevSecOps

### Conceptual Model
![CM](https://raw.githubusercontent.com/kranthiB/tech-pulse/main/images/ops-mastery/dev-sec-ops/0005-CM.png)

 * In today's fast-paced digital landscape, ensuring the security and resilience of software applications has become a top priority. This is where DevSecOps comes into play - an innovative approach that integrates cybersecurity practices into every stage of the software development lifecycle.
 * *DevSecOps Ecosystem*
   * The DevSecOps ecosystem is a comprehensive approach that integrates security into every stage of the software development lifecycle
   * Emphasizes collaboration between developers, security teams, and operations teams to ensure the secure and resilient delivery of software applications. 
 * *Software Hub*
   * The Software Hub is the central point where software development takes place
   * Provides a platform for developers to collaborate, manage code changes, and track progress. 
 * *Pipeline*
   * The Pipeline represents the CI/CD process that automates the building, testing, and deployment of software applications.
   * Ensures that software applications are thoroughly tested for security vulnerabilities and bugs before they are deployed to production 
 * *Application*
   * The Application section highlights the final stage of the DevSecOps pipeline.
   * Represents the deployed application, which is ready for use by end-users. 
 * *Artifact Repository*
   * The Artifact Repository is a centralized location where build artifacts, such as binaries, libraries, and configurations, are stored and managed.
   * Provides a single source of truth for all build artifacts, ensuring that the correct versions are used in production 
 * *Tool*
   * The Tool refers to various software applications used in the DevSecOps pipeline to automate tasks, such as:
     * Build tools like Maven, Gradle, or Ant
     * Testing frameworks like JUnit, TestNG, or PyUnit
     * Continuous integration servers like Jenkins, Travis CI, or CircleCI  
 * *Environment*
   * The Environment refers to the infrastructure and resources required to support the DevSecOps pipeline, such as
     * Development environments for testing and debugging
     * Staging environments for pre-production testing
     * Production environments for deployment
 * *Cyber Resiliency*
   * Cyber Resiliency refers to the ability of software applications to withstand various types of attacks or disruptions
   * Emphasizes the importance of continuous monitoring and feedback to ensure that software applications remain secure and resilient over time. 

-----

### Core-Practices
![CP](https://raw.githubusercontent.com/kranthiB/tech-pulse/main/images/ops-mastery/dev-sec-ops/0006-CP.png)

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

#### Analyze
![CPA](https://raw.githubusercontent.com/kranthiB/tech-pulse/main/images/ops-mastery/dev-sec-ops/0006A-CP.png)

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

#### Secure
![CPS](https://raw.githubusercontent.com/kranthiB/tech-pulse/main/images/ops-mastery/dev-sec-ops/0006B-CP.png)

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

#### Verify
![CPV](https://raw.githubusercontent.com/kranthiB/tech-pulse/main/images/ops-mastery/dev-sec-ops/0006C-CP.png)

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

#### Defend
![CPD](https://raw.githubusercontent.com/kranthiB/tech-pulse/main/images/ops-mastery/dev-sec-ops/0006D-CP.png)
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

#### Additional Practices
![CPAA](https://raw.githubusercontent.com/kranthiB/tech-pulse/main/images/ops-mastery/dev-sec-ops/0006EA-CP.png)
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

![CPAB](https://raw.githubusercontent.com/kranthiB/tech-pulse/main/images/ops-mastery/dev-sec-ops/0006EB-CP.png)
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

### Lifecycle-Phases
![LM](https://raw.githubusercontent.com/kranthiB/tech-pulse/main/images/ops-mastery/dev-sec-ops/0007-LP.png)
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

### Continuous-Feedback-Loops
![CFL](https://raw.githubusercontent.com/kranthiB/tech-pulse/main/images/ops-mastery/dev-sec-ops/0008-CFL.png)
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

### Activities-N-Tools

#### Continuous Security
![ATCS](https://raw.githubusercontent.com/kranthiB/tech-pulse/main/images/ops-mastery/dev-sec-ops/0009-CS.png)
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

#### Continuous Testing
![ATCTA](https://raw.githubusercontent.com/kranthiB/tech-pulse/main/images/ops-mastery/dev-sec-ops/0010A-CT.png)
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

![ATCTB](https://raw.githubusercontent.com/kranthiB/tech-pulse/main/images/ops-mastery/dev-sec-ops/0010B-CT.png)
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

#### Configuration Management
![ATCMA](https://raw.githubusercontent.com/kranthiB/tech-pulse/main/images/ops-mastery/dev-sec-ops/0011A-CM.png)
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

![ATCMB](https://raw.githubusercontent.com/kranthiB/tech-pulse/main/images/ops-mastery/dev-sec-ops/0011B-CM.png)
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

### SMART-Metrics

#### Specific
![SMS](https://raw.githubusercontent.com/kranthiB/tech-pulse/main/images/ops-mastery/dev-sec-ops/0012A-SM.png)
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

#### Measurable
![SMM](https://raw.githubusercontent.com/kranthiB/tech-pulse/main/images/ops-mastery/dev-sec-ops/0012B-SM.png)
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

#### Attainable
![SMA](https://raw.githubusercontent.com/kranthiB/tech-pulse/main/images/ops-mastery/dev-sec-ops/0012C-SM.png)
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

#### Relevant
![SMR](https://raw.githubusercontent.com/kranthiB/tech-pulse/main/images/ops-mastery/dev-sec-ops/0012D-SM.png)
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

#### Time Bound
![SMT](https://raw.githubusercontent.com/kranthiB/tech-pulse/main/images/ops-mastery/dev-sec-ops/0012E-SM.png)
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

## References
### Container Application Pipeline Reference
![CAPRA](https://raw.githubusercontent.com/kranthiB/tech-pulse/main/images/ops-mastery/dev-sec-ops/0013A-CAR.png)
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

![CAPRB](https://raw.githubusercontent.com/kranthiB/tech-pulse/main/images/ops-mastery/dev-sec-ops/0013B-CAR.png)
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

### Enterprise-DevSecOps

#### CNCF Certified Kubernetes
![CCK](https://raw.githubusercontent.com/kranthiB/tech-pulse/main/images/ops-mastery/dev-sec-ops/0014A-EM.png)
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

##### Sidecar Container Security Stack (SCSS)
![CCKS](https://raw.githubusercontent.com/kranthiB/tech-pulse/main/images/ops-mastery/dev-sec-ops/0014B-EM.png)
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

#### Multi-Cluster CNCF Kubernetes
![MCK](https://raw.githubusercontent.com/kranthiB/tech-pulse/main/images/ops-mastery/dev-sec-ops/0015A-EM.png)
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

##### K8s Global & Regional Control Plane
![MCKK](https://raw.githubusercontent.com/kranthiB/tech-pulse/main/images/ops-mastery/dev-sec-ops/0015B-EM.png)
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

#### AWS Managed Services
![AWS](https://raw.githubusercontent.com/kranthiB/tech-pulse/main/images/ops-mastery/dev-sec-ops/0016.png)
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

#### Microsoft Azure + GitHub
![Azure](https://raw.githubusercontent.com/kranthiB/tech-pulse/main/images/ops-mastery/dev-sec-ops/0017.png)
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

#### Container Monitoring Reference
![CM](https://raw.githubusercontent.com/kranthiB/tech-pulse/main/images/ops-mastery/dev-sec-ops/0018.png)
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

## Patterns-AntiPatterns

### Continuous-Integration
![CIPA](https://raw.githubusercontent.com/kranthiB/tech-pulse/main/images/ops-mastery/dev-sec-ops/0019A.png)
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

![CIPB](https://raw.githubusercontent.com/kranthiB/tech-pulse/main/images/ops-mastery/dev-sec-ops/0019B.png)
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

![CIPC](https://raw.githubusercontent.com/kranthiB/tech-pulse/main/images/ops-mastery/dev-sec-ops/0019C.png)
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

![CIPD](https://raw.githubusercontent.com/kranthiB/tech-pulse/main/images/ops-mastery/dev-sec-ops/0019D.png)
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

### Continuous-Delivery
![CDPA](https://raw.githubusercontent.com/kranthiB/tech-pulse/main/images/ops-mastery/dev-sec-ops/0020A.png)
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

![CDPB](https://raw.githubusercontent.com/kranthiB/tech-pulse/main/images/ops-mastery/dev-sec-ops/0020B.png)
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

![CDPC](https://raw.githubusercontent.com/kranthiB/tech-pulse/main/images/ops-mastery/dev-sec-ops/0020C.png)
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

![CDPD](https://raw.githubusercontent.com/kranthiB/tech-pulse/main/images/ops-mastery/dev-sec-ops/0020D.png)
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

![CDPE](https://raw.githubusercontent.com/kranthiB/tech-pulse/main/images/ops-mastery/dev-sec-ops/0020E.png)
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
