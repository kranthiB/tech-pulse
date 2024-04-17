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
      * [Continuous Feedback Loops](#Continuous-Feedback-Loops)
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
         * [cncf-certified-kubernetes](#cncf-certified-kubernetes)
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

### Software-Supply-Chain-Continuum
![SSCC](https://raw.githubusercontent.com/kranthiB/tech-pulse/main/images/ops-mastery/dev-sec-ops/0002-SSCC.png)

### Evolution-of-Best-Practices
![EBSD](https://raw.githubusercontent.com/kranthiB/tech-pulse/main/images/ops-mastery/dev-sec-ops/0003-EBSD.png)

### DORA-Capabilities
![DORA](https://raw.githubusercontent.com/kranthiB/tech-pulse/main/images/ops-mastery/dev-sec-ops/0004-DORA.png)

## DevSecOps

### Conceptual Model
![CM](https://raw.githubusercontent.com/kranthiB/tech-pulse/main/images/ops-mastery/dev-sec-ops/0005-CM.png)

### Core-Practices
![CP](https://raw.githubusercontent.com/kranthiB/tech-pulse/main/images/ops-mastery/dev-sec-ops/0006-CP.png)

#### Analyze
![CPA](https://raw.githubusercontent.com/kranthiB/tech-pulse/main/images/ops-mastery/dev-sec-ops/0006A-CP.png)

#### Secure
![CPS](https://raw.githubusercontent.com/kranthiB/tech-pulse/main/images/ops-mastery/dev-sec-ops/0006B-CP.png)

#### Verify
![CPV](https://raw.githubusercontent.com/kranthiB/tech-pulse/main/images/ops-mastery/dev-sec-ops/0006C-CP.png)

#### Defend
![CPD](https://raw.githubusercontent.com/kranthiB/tech-pulse/main/images/ops-mastery/dev-sec-ops/0006D-CP.png)

#### Additional Practices
![CPAA](https://raw.githubusercontent.com/kranthiB/tech-pulse/main/images/ops-mastery/dev-sec-ops/0006EA-CP.png)

![CPAB](https://raw.githubusercontent.com/kranthiB/tech-pulse/main/images/ops-mastery/dev-sec-ops/0006EB-CP.png)

### Lifecycle-Phases
![LM](https://raw.githubusercontent.com/kranthiB/tech-pulse/main/images/ops-mastery/dev-sec-ops/0007-CP.png)

### Continuous-Feedback-Loops
![CFL](https://raw.githubusercontent.com/kranthiB/tech-pulse/main/images/ops-mastery/dev-sec-ops/0008-CFL.png)

### Activities-N-Tools

#### Continuous Security
![ATCS](https://raw.githubusercontent.com/kranthiB/tech-pulse/main/images/ops-mastery/dev-sec-ops/0009-CS.png)

#### Continuous Testing
![ATCTA](https://raw.githubusercontent.com/kranthiB/tech-pulse/main/images/ops-mastery/dev-sec-ops/00010A-CS.png)

![ATCTB](https://raw.githubusercontent.com/kranthiB/tech-pulse/main/images/ops-mastery/dev-sec-ops/00010B-CS.png)

#### Configuration Management
![ATCMA](https://raw.githubusercontent.com/kranthiB/tech-pulse/main/images/ops-mastery/dev-sec-ops/00011A-CM.png)

![ATCMB](https://raw.githubusercontent.com/kranthiB/tech-pulse/main/images/ops-mastery/dev-sec-ops/00011B-CM.png)

SMART-Metrics
-------------

#### Specific
![SMS](https://raw.githubusercontent.com/kranthiB/tech-pulse/main/images/ops-mastery/dev-sec-ops/00012A-SM.png)

#### Measurable
![SMM](https://raw.githubusercontent.com/kranthiB/tech-pulse/main/images/ops-mastery/dev-sec-ops/00012B-SM.png)

#### Attainable
![SMA](https://raw.githubusercontent.com/kranthiB/tech-pulse/main/images/ops-mastery/dev-sec-ops/00012C-SM.png)

#### Relevant
![SMR](https://raw.githubusercontent.com/kranthiB/tech-pulse/main/images/ops-mastery/dev-sec-ops/00012D-SM.png)

#### Time Bound
![SMT](https://raw.githubusercontent.com/kranthiB/tech-pulse/main/images/ops-mastery/dev-sec-ops/00012E-SM.png)

## References

### Container Application Pipeline Reference
![CAPRA](https://raw.githubusercontent.com/kranthiB/tech-pulse/main/images/ops-mastery/dev-sec-ops/00013A-CAR.png)

![CAPRB](https://raw.githubusercontent.com/kranthiB/tech-pulse/main/images/ops-mastery/dev-sec-ops/00013B-CAR.png)

### Enterprise-DevSecOps

#### CNCF Certified Kubernetes
![CCK](https://raw.githubusercontent.com/kranthiB/tech-pulse/main/images/ops-mastery/dev-sec-ops/00014A-EM.png)

##### Sidecar Container Security Stack (SCSS)
![CCKS](https://raw.githubusercontent.com/kranthiB/tech-pulse/main/images/ops-mastery/dev-sec-ops/00014B-EM.png)

#### Multi-Cluster CNCF Kubernetes
![MCK](https://raw.githubusercontent.com/kranthiB/tech-pulse/main/images/ops-mastery/dev-sec-ops/00015A-EM.png)

##### K8s Global & Regional Control Plane
![MCKK](https://raw.githubusercontent.com/kranthiB/tech-pulse/main/images/ops-mastery/dev-sec-ops/00015B-EM.png)

#### AWS Managed Services
![AWS](https://raw.githubusercontent.com/kranthiB/tech-pulse/main/images/ops-mastery/dev-sec-ops/00016.png)

#### Microsoft Azure + GitHub
![Azure](https://raw.githubusercontent.com/kranthiB/tech-pulse/main/images/ops-mastery/dev-sec-ops/00017.png)

#### Container Monitoring Reference
![CM](https://raw.githubusercontent.com/kranthiB/tech-pulse/main/images/ops-mastery/dev-sec-ops/00018.png)

## Patterns-AntiPatterns

### Continuous-Integration
![CIPA](https://raw.githubusercontent.com/kranthiB/tech-pulse/main/images/ops-mastery/dev-sec-ops/00019A.png)

![CIPB](https://raw.githubusercontent.com/kranthiB/tech-pulse/main/images/ops-mastery/dev-sec-ops/00019B.png)

![CIPC](https://raw.githubusercontent.com/kranthiB/tech-pulse/main/images/ops-mastery/dev-sec-ops/00019C.png)

![CIPD](https://raw.githubusercontent.com/kranthiB/tech-pulse/main/images/ops-mastery/dev-sec-ops/00019D.png)

### Continuous-Delivery
![CDPA](https://raw.githubusercontent.com/kranthiB/tech-pulse/main/images/ops-mastery/dev-sec-ops/00020A.png)

![CDPB](https://raw.githubusercontent.com/kranthiB/tech-pulse/main/images/ops-mastery/dev-sec-ops/00020B.png)

![CDPC](https://raw.githubusercontent.com/kranthiB/tech-pulse/main/images/ops-mastery/dev-sec-ops/00020C.png)

![CDPD](https://raw.githubusercontent.com/kranthiB/tech-pulse/main/images/ops-mastery/dev-sec-ops/00020D.png)

![CDPE](https://raw.githubusercontent.com/kranthiB/tech-pulse/main/images/ops-mastery/dev-sec-ops/00020E.png)