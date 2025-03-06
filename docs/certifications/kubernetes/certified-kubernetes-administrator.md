---
id: certifications/kubernetes/certified-kubernetes-administrator
title: Certified Kubernetes Administrator
sidebar_label: Certified Kubernetes Administrator
---

<div style="text-align: right;">
    <a href="https://kranthib.github.io/tech-pulse/" style="display: inline-block; padding: 6px 14px; background-color: #2054a6; color: white; text-decoration: none; border-radius: 3px; font-size: 14px; font-weight: 500; transition: background-color 0.3s;">Back to Home →</a>
</div>

# Certified Kubernetes Administrator

Table of contents
=================

<!--ts-->
  * [Preparation Plan](#preparation-plan)
    * [Kubernetes Fundamentals & Cluster Architecture](#kubernetes-fundamentals--cluster-architecture)
    * [Workloads, Services & Networking](#workloads-services--networking)
    * [Storage & Advanced Scheduling](#storage--advanced-scheduling)
    * [Troubleshooting](#troubleshooting)
  * [Knowledge Base](#knowledge-base)
    * [Kubernetes Fundamentals & Cluster Architecture](#kubernetes-fundamentals--cluster-architecture-1)
      * [1. Kubernetes Architecture Overview](#1-kubernetes-architecture-overview)
      * [2. Key Kubernetes Resources](#2-key-kubernetes-resources)
      * [3. Kubernetes Communication Flows](#3-kubernetes-communication-flows)
      * [4. Cluster Deployment Options](#4-cluster-deployment-options)
      * [5. kubeadm Deep Dive](#5-kubeadm-deep-dive)
      * [6. Cluster Networking Fundamentals](#6-cluster-networking-fundamentals)
      * [7. Kubernetes Security Model](#7-kubernetes-security-model)
      * [8. Role-Based Access Control (RBAC)](#8-role-based-access-control-rbac)
      * [9. Security Context and Pod Security](#9-security-context-and-pod-security)
      * [Lab 1: Setting Up a Development Environment](#lab-1-setting-up-a-development-environment)
      * [Lab 2: Understanding Kubernetes Objects](#lab-2-understanding-kubernetes-objects)
      * [Lab 3: Exploring the Control Plane](#lab-3-exploring-the-control-plane)
      * [Lab 4: Preparing Nodes for Kubernetes](#lab-4-preparing-nodes-for-kubernetes)
      * [Lab 5: Bootstrapping a Kubernetes Cluster](#lab-5-bootstrapping-a-kubernetes-cluster)
      * [Lab 6: Adding Nodes and Managing the Cluster](#lab-6-adding-nodes-and-managing-the-cluster)
      * [Lab 7: Configuring Authentication and Authorization](#lab-7-configuring-authentication-and-authorization)
      * [Lab 8: Implementing Security Contexts](#lab-8-implementing-security-contexts)
      * [Lab 9: Securing the Kubernetes API Server](#lab-9-securing-the-kubernetes-api-server)
      * [Practice Exercises](#practice-exercises)
    * [Workloads, Services & Networking](#workloads-services--networking-1)
      * [Kubernetes Deployments](#kubernetes-deployments)
      * [StatefulSets](#statefulsets)
      * [DaemonSets](#daemonsets)
      * [Jobs and CronJobs](#jobs-and-cronjobs)
      * [ConfigMaps and Secrets](#configmaps-and-secrets)
      * [Pod Scheduling](#pod-scheduling)
      * [Pod Networking Model](#pod-networking-model)
      * [Service Types](#service-types)
      * [Endpoints](#endpoints)
      * [Network Policies](#network-policies)
      * [Gateway API](#gateway-api)
      * [Ingress Controllers and Resources](#ingress-controllers-and-resources)
      * [CoreDNS](#coredns)
      * [Lab 1: Working with Deployments, ConfigMaps, and Secrets](#lab-1-working-with-deployments-configmaps-and-secrets)
      * [Lab 2: Working with Services, NetworkPolicies, and DNS](#lab-2-working-with-services-networkpolicies-and-dns)
      * [Lab 3: Working with Ingress Controllers and Gateway API](#lab-3-working-with-ingress-controllers-and-gateway-api)
      * [Practice Exercises](#practice-exercises-1)
    * [Storage & Advanced Scheduling](#storage--advanced-scheduling-1)
      * [Persistent Volumes (PV)](#persistent-volumes-pv)
      * [Persistent Volume Claims (PVC)](#persistent-volume-claims-pvc)
      * [Storage Classes](#storage-classes)
      * [Dynamic Provisioning](#dynamic-provisioning)
      * [Volume Types](#volume-types)
      * [Reclaim Policies](#reclaim-policies)
      * [Container Storage Interface (CSI)](#container-storage-interface-csi)
      * [Node Selectors and Labels](#node-selectors-and-labels)
      * [Node Affinity and Anti-Affinity](#node-affinity-and-anti-affinity)
      * [Pod Affinity and Anti-Affinity](#pod-affinity-and-anti-affinity)
      * [Taints and Tolerations](#taints-and-tolerations)
      * [Resource Limits and Requests](#resource-limits-and-requests)
      * [Pod Priority and Preemption](#pod-priority-and-preemption)
      * [Pod Disruption Budgets (PDB)](#pod-disruption-budgets-pdb)
      * [Topology Spread Constraints](#topology-spread-constraints)
      * [Lab 1: Working with Persistent Volumes and Persistent Volume Claims](#lab-1-working-with-persistent-volumes-and-persistent-volume-claims)
      * [Lab 2: Working with Storage Classes and Dynamic Provisioning](#lab-2-working-with-storage-classes-and-dynamic-provisioning)
      * [Lab 3: Advanced Pod Scheduling with Affinity and Anti-Affinity](#lab-3-advanced-pod-scheduling-with-affinity-and-anti-affinity)
      * [Lab 4: Working with Taints and Tolerations](#lab-4-working-with-taints-and-tolerations)
      * [Lab 5: Advanced Pod Scheduling with Resource Limits and Requests](#lab-5-advanced-pod-scheduling-with-resource-limits-and-requests)
      * [Practice Exercises](#practice-exercises-2)
    * [Troubleshooting](#troubleshooting-1)
      * [1. Troubleshooting Clusters and Nodes](#1-troubleshooting-clusters-and-nodes)
      * [2. Troubleshooting Cluster Components](#2-troubleshooting-cluster-components)
      * [3. Monitoring Cluster and Application Resource Usage](#3-monitoring-cluster-and-application-resource-usage)
      * [4. Managing and Evaluating Container Output Streams](#4-managing-and-evaluating-container-output-streams)
      * [5. Troubleshooting Services and Networking](#5-troubleshooting-services-and-networking)
      * [Lab 1: Troubleshooting Cluster Nodes](#lab-1-troubleshooting-cluster-nodes)
      * [Lab 2: Troubleshooting Cluster Components](#lab-2-troubleshooting-cluster-components)
      * [Lab 3: Monitoring and Resource Management](#lab-3-monitoring-and-resource-management)
      * [Lab 4: Troubleshooting Application Logs and Container Output](#lab-4-troubleshooting-application-logs-and-container-output)
      * [Lab 5: Troubleshooting Services and Networking](#lab-5-troubleshooting-services-and-networking)
      * [Practice Exercises](#practice-exercises-3)
    * [Mock Exams & Exam Strategy](#mock-exams--exam-strategy)
      * [Understanding the CKA Exam Format](#understanding-the-cka-exam-format)
      * [Time Management Strategies](#time-management-strategies)
      * [Command Line Efficiency Techniques](#command-line-efficiency-techniques)
      * [Common Exam Scenarios and Approaches](#common-exam-scenarios-and-approaches)
      * [Exam Day Preparation](#exam-day-preparation)
      * [Full-Length Mock Exam](#full-length-mock-exam)
      * [Exam Strategies and Final Preparation](#exam-strategies-and-final-preparation)
<!--te-->

# Preparation Plan

## Kubernetes Fundamentals & Cluster Architecture

- Kubernetes Architecture Overview
- Key Kubernetes Resources
- Kubernetes Communication Flows
- Cluster Deployment Options
- kubeadm Deep Dive
- Cluster Networking Fundamentals
- Kubernetes Security Model
- Role-Based Access Control (RBAC)
- Security Context and Pod Security]
- Lab 1: Setting Up a Development Environment
- Lab 2: Understanding Kubernetes Objects
- Lab 3: Exploring the Control Plane
- Lab 4: Preparing Nodes for Kubernetes
- Lab 5: Bootstrapping a Kubernetes Cluster
- Lab 6: Adding Nodes and Managing the Cluster
- Lab 7: Configuring Authentication and Authorization
- Lab 8: Implementing Security Contexts
- Lab 9: Securing the Kubernetes API Server
- Practice Exercises

---

## Workloads, Services & Networking
- Kubernetes Deployments
- StatefulSets
- DaemonSets
- Jobs and CronJobs
- ConfigMaps and Secrets
- Pod Scheduling
- Pod Networking Model
- Service Types
- Network Policies
- Gateway API
- Ingress Controllers and Resources
- CoreDNS
- Lab 1: Working with Deployments, ConfigMaps, and Secrets
- Lab 2: Working with Services, NetworkPolicies, and DNS
- Lab 3: Working with Ingress Controllers and Gateway API
- Practice Exercises

---

## Storage & Advanced Scheduling

- Persistent Volumes (PV)
- Persistent Volume Claims (PVC)
- Storage Classes
- Dynamic Provisioning
- Volume Types
- Reclaim Policies
- Container Storage Interface (CSI)
- Node Selectors and Labels
- Node Affinity and Anti-Affinity
- Pod Affinity and Anti-Affinity
- Taints and Tolerations
- Resource Limits and Requests
- Pod Priority and Preemption
- Pod Disruption Budgets (PDB)
- Topology Spread Constraints
- Lab 1: Working with Persistent Volumes and Persistent Volume Claims
- Lab 2: Working with Storage Classes and Dynamic Provisioning
- Lab 3: Advanced Pod Scheduling with Affinity and Anti-Affinity
- Lab 4: Working with Taints and Tolerations
- Lab 5: Advanced Pod Scheduling with Resource Limits and Requests
- Practice Exercises

---

## Troubleshooting

- Troubleshooting Clusters and Nodes
- Troubleshooting Cluster Components
- Monitoring Cluster and Application Resource Usage
- Managing and Evaluating Container Output Streams
- Troubleshooting Services and Networking
- Lab 1: Troubleshooting Cluster Nodes
- Lab 2: Troubleshooting Cluster Components
- Lab 3: Monitoring and Resource Management
- Lab 4: Troubleshooting Application Logs and Container Output
- Lab 5: Troubleshooting Services and Networking
- Practice Exercises

---

# Knowledge Base

## Kubernetes Fundamentals & Cluster Architecture

### 1. Kubernetes Architecture Overview

Kubernetes is a container orchestration platform designed to automate the deployment, scaling, and management of containerized applications. Its architecture follows a primary/replica pattern, with a clear separation between the control plane (management components) and the data plane (worker nodes that run applications).

**Control Plane Components:**

The control plane is the brain of Kubernetes, making global decisions about the cluster and responding to cluster events.

1. **API Server**: Acts as the frontend for Kubernetes control plane. All communications, both internal and external, go through the API server. It validates and processes RESTful requests and updates the corresponding objects in etcd.

2. **etcd**: A consistent and highly-available key-value store used as Kubernetes' backing store for all cluster data. Consider it the source of truth for the cluster state.

3. **Scheduler**: Watches for newly created Pods with no assigned node and selects a node for them to run on. Factors considered include individual and collective resource requirements, hardware/software/policy constraints, affinity and anti-affinity specifications, and more.

4. **Controller Manager**: Runs controller processes that regulate the state of the cluster. Each controller is a separate process, but they are compiled into a single binary and run in a single process for simplicity. Examples include Node Controller, Job Controller, and Replication Controller.

**Node Components:**

These components run on every node in the cluster, maintaining running pods and providing the Kubernetes runtime environment.

1. **kubelet**: An agent that runs on each node and ensures containers are running in a Pod as expected. It takes a set of PodSpecs provided through various mechanisms and ensures the containers described in those PodSpecs are running and healthy.

2. **kube-proxy**: A network proxy that runs on each node, implementing part of the Kubernetes Service concept. It maintains network rules that allow network communication to Pods from network sessions inside or outside of the cluster.

3. **Container Runtime**: The software responsible for running containers. Kubernetes supports container runtimes such as containerd, CRI-O, and any implementation of the Kubernetes CRI (Container Runtime Interface).

---

### 2. Key Kubernetes Resources

Kubernetes objects are persistent entities in the system that represent the state of your cluster. They describe what containerized applications are running, the resources available to them, and the policies affecting their behavior.

**Essential Resources:**

1. **Pods**: The smallest deployable units in Kubernetes that can be created and managed. A Pod represents a single instance of a running process in your cluster and can contain one or more containers that share storage, network, and a specification for how to run the containers.

2. **ReplicaSets**: Ensures that a specified number of Pod replicas are running at any given time. It's often used to guarantee the availability of a specified number of identical Pods.

3. **Deployments**: Provides declarative updates for Pods and ReplicaSets. You describe a desired state in a Deployment, and the Deployment Controller changes the actual state to match the desired state at a controlled rate.

**Configuration Resources:**

1. **ConfigMaps**: Allow you to decouple configuration artifacts from image content to keep containerized applications portable. ConfigMaps hold configuration data as key-value pairs.

2. **Secrets**: Similar to ConfigMaps but designed for storing sensitive information such as passwords, OAuth tokens, and ssh keys. They can be mounted as data volumes or exposed as environment variables.

**Networking Resources:**

1. **Services**: An abstraction which defines a logical set of Pods and a policy by which to access them. As Pods are ephemeral, Services allow clients to reliably discover and connect to containers running in the Pods.

2. **Endpoints**: A list of all the IP addresses and ports that provide a Service. Kubernetes automatically creates and manages Endpoint objects for Services except for Services of type ExternalName.

**Storage Resources:**

1. **PersistentVolumes (PV)**: Pieces of storage in the cluster that have been provisioned by an administrator or dynamically provisioned using Storage Classes.

2. **PersistentVolumeClaims (PVC)**: A request for storage by a user that can be fulfilled by a PersistentVolume.

---

### 3. Kubernetes Communication Flows

Understanding how Kubernetes components communicate is essential for troubleshooting and securing your cluster.

**Component Communication:**

1. **API Server as Central Hub**: All communications between components flow through the API server. The API server is the only component that communicates with etcd.

2. **Controller to API Server**: Controllers watch the API server for changes to their respective resources and take action to ensure the current state matches the desired state.

3. **Scheduler to API Server**: The scheduler watches for newly created Pods with no assigned node and selects a node for them to run on.

4. **Kubelet to API Server**: Kubelets on worker nodes register themselves with the API server and report the status of containers they are running.

**Authentication and Authorization Flow:**

1. **Authentication**: When a request reaches the API server, it goes through the authentication step first, which identifies the client making the request.

2. **Authorization**: Once authenticated, the request is authorized to ensure the client has permissions to perform the requested operation on the specified resource.

3. **Admission Control**: If the request creates or modifies a resource, it passes through admission controllers, which can modify the resource or reject the request based on custom criteria.

**Watch and Reconciliation Patterns:**

1. **Watch API**: Kubernetes components use the Watch API to efficiently observe changes to resources they are interested in.

2. **Reconciliation Loop**: Controllers implement a reconciliation loop that continuously compares the desired state (specification) with the current state, making changes as necessary to achieve the desired state.

3. **Level-Triggered Logic**: Kubernetes uses level-triggered logic (rather than edge-triggered), meaning it continues to process objects until they reach the desired state, making the system more resilient to failures.

---

### 4. Cluster Deployment Options

When planning a Kubernetes deployment, several architectural decisions must be made based on your organization's requirements.

**Single-node vs Multi-node Architectures:**

1. **Single-node**: All components run on a single machine. This is suitable for development and testing but lacks high availability and scalability for production.

2. **Multi-node**: Components are distributed across multiple machines, with dedicated control plane nodes and worker nodes. This setup provides better resilience, scalability, and resource isolation.

**High-availability Considerations:**

1. **Control Plane Redundancy**: For production environments, running multiple control plane nodes (typically 3 or 5) ensures that the cluster remains operational even if some control plane nodes fail.

2. **etcd Clustering**: etcd should be deployed as a cluster with an odd number of members (typically 3, 5, or 7) to maintain quorum and ensure data consistency.

3. **Load Balancing**: A load balancer should be placed in front of the API servers to distribute client requests across multiple API server instances.

**Control Plane vs Worker Node Requirements:**

1. **Control Plane Nodes**: Require less CPU and memory compared to worker nodes but benefit from faster storage (SSD) for etcd. Typically need 2 CPUs and 4GB RAM at minimum.

2. **Worker Nodes**: Resource requirements depend on the workloads they will run. Need sufficient CPU, memory, and storage to accommodate all pods scheduled on the node.

**Networking Prerequisites:**

1. **Node Connectivity**: All nodes must be able to communicate with each other through a network.

2. **Port Requirements**: Specific ports must be open for Kubernetes components to communicate.

3. **Network Policies**: Consideration for how to implement network policies to control pod-to-pod communication.

---

### 5. kubeadm Deep Dive

kubeadm is a tool built to provide best-practice "fast paths" for creating Kubernetes clusters. It performs the necessary actions to get a minimum viable cluster up and running quickly.

**kubeadm Phases and Workflow:**

1. **preflight**: Runs a set of checks to validate the system state before making changes.

2. **certs**: Generates the self-signed CA and certificates for all Kubernetes components.

3. **kubeconfig**: Generates kubeconfig files for the controller manager, scheduler, admin, and kubelet.

4. **kubelet-start**: Configures and starts the kubelet.

5. **control-plane**: Creates control plane components as static Pod manifests.

6. **etcd**: Creates a local etcd instance as a static Pod.

7. **upload-config**: Uploads the kubeadm and kubelet configurations to a ConfigMap.

8. **mark-control-plane**: Applies labels and taints to the control plane node.

9. **bootstrap-token**: Creates a bootstrap token to join additional nodes.

10. **addon**: Installs required addons like kube-proxy and CoreDNS.

**Certificate Management:**

1. **PKI Infrastructure**: kubeadm sets up a PKI infrastructure using self-signed certificates stored in `/etc/kubernetes/pki`.

2. **Certificate Authority (CA)**: kubeadm creates a root CA that issues certificates for each component.

3. **Component Certificates**: Each component (API server, kubelet, etc.) receives its own certificate with appropriate SANs (Subject Alternative Names).

- **Certificate Rotation**: For security reasons, certificates should be rotated periodically.

**kubelet Configuration:**

1. **kubelet-config**: kubeadm generates a kubelet configuration file with appropriate settings.

2. **Systemd Service**: kubelet runs as a systemd service on each node.

3. **Authorization Mode**: kubeadm configures the kubelet to use the Node Authorizer, which restricts kubelet access to only the resources it needs.

**Container Runtime Interfaces (CRI):**

1. **CRI Standard**: Kubernetes uses the Container Runtime Interface to interact with different container runtimes.

2. **Supported Runtimes**: Common runtimes include containerd, CRI-O, and Docker (via the dockershim, which is deprecated in newer versions).

3. **Runtime Configuration**: kubeadm detects and configures the available container runtime.

---

### 6. Cluster Networking Fundamentals

Kubernetes has specific requirements for networking, and understanding these fundamentals is crucial for a successful deployment.

**Pod Network Fundamentals:**

1. **Pod IP Addressing**: Each Pod receives its own IP address. All containers within a Pod share the same network namespace and IP address.

2. **Pod-to-Pod Communication**: Pods should be able to communicate with all other pods in the cluster without NAT.

3. **Flat Network Space**: The Pod network is typically implemented as a flat, layer 3 network.

**Container Network Interface (CNI):**

1. **CNI Specification**: A standard for configuring network interfaces in Linux containers, used by Kubernetes to set up Pod networking.

2. **CNI Plugins**: Software components that implement the CNI specification, such as Calico, Flannel, Cilium, and Weave Net.

3. **Plugin Selection**: Factors to consider include performance, network policy support, encryption, and integration with existing infrastructure.

**Service Networking and kube-proxy Modes:**

1. **Service IP Range**: A separate CIDR block allocated for Service ClusterIPs. This range is different from the Pod network range.

2. **kube-proxy Modes**:
  - **userspace**: The original mode, where kube-proxy watches the API server for new Services and creates proxy servers for each Service.
  - **iptables**: Default mode, where kube-proxy configures iptables rules to capture traffic to Service IPs and redirect it to backends.
  - **ipvs**: For high-performance requirements, using the Linux IPVS (IP Virtual Server) module for load balancing.

**DNS Architecture with CoreDNS:**

1. **Cluster DNS**: CoreDNS serves as the DNS server for the cluster, providing name resolution for Services and Pods.

2. **DNS Records**: CoreDNS creates DNS records for Services and (optionally) for Pods.

3. **Service Discovery**: Containers can discover Services through DNS names like `service-name.namespace.svc.cluster.local`.

4. **DNS Configuration**: Pod DNS settings are configured through the kubelet, which sets up `/etc/resolv.conf` in each container.

---

### 7. Kubernetes Security Model

Kubernetes has a comprehensive security model that addresses various aspects of cluster and application security.

**Authentication Methods:**

1. **X.509 Client Certificates**: Using client certificates for authentication to the API server.

2. **Service Account Tokens**: JWT tokens that are automatically mounted into Pods.

3. **OpenID Connect (OIDC)**: Integration with external identity providers like Google, Azure AD, or Okta.

4. **Webhook Token Authentication**: Allowing an external service to determine authentication decisions.

5. **Authentication Proxy**: Using a proxy in front of the API server to handle authentication.

**Authorization Mechanisms:**

1. **RBAC (Role-Based Access Control)**: Fine-grained control over what actions users and service accounts can perform on which resources.

2. **ABAC (Attribute-Based Access Control)**: Policy-based access control using attributes of users, resources, and environment.

3. **Node Authorization**: Special-purpose authorizer that grants permissions to kubelets based on the Pods they are scheduled to run.

4. **Webhook Authorization**: Delegates authorization decisions to an external service.

**Admission Controllers:**

1. **Validating Admission Controllers**: Validate requests against a set of rules before processing them.

2. **Mutating Admission Controllers**: Can modify objects before they are persisted.

3. **Common Admission Controllers**: Include PodSecurityPolicy, ResourceQuota, LimitRanger, and ServiceAccount.

**Pod Security Standards:**

1. **Privileged**: No restrictions on Pod capabilities, equivalent to root on the host.

2. **Baseline**: Minimally restrictive policy, preventing known privilege escalations while allowing the default (minimally specified) Pod configuration.

3. **Restricted**: Heavily restricted policy for hardened environments, requiring Pods to run with a more restrictive security context.

---

### 8. Role-Based Access Control (RBAC)

RBAC is a method of regulating access to computer or network resources based on the roles of individual users.

**Roles and ClusterRoles:**

1. **Role**: Defines permissions within a specific namespace.

2. **ClusterRole**: Defines permissions across the entire cluster.

3. **Permission Structure**: Each role contains rules that specify which API groups, resources, and verbs (actions) are allowed.

**RoleBindings and ClusterRoleBindings:**

1. **RoleBinding**: Binds a Role to users, groups, or service accounts within a namespace.

2. **ClusterRoleBinding**: Binds a ClusterRole to users, groups, or service accounts cluster-wide.

3. **Binding Subjects**: Can reference users, groups, or service accounts.

**Service Accounts and Their Uses:**

1. **Default Service Account**: Every namespace has a default service account that is automatically assigned to Pods if no service account is specified.

2. **Custom Service Accounts**: Created for applications that need specific permissions.

3. **Token Mounting**: Service account tokens are automatically mounted into Pods at `/var/run/secrets/kubernetes.io/serviceaccount/token`.

4. **Usage Scenarios**: Used for Pods that need to interact with the Kubernetes API or for external applications that need cluster access.

**Best Practices for Least Privilege:**

1. **Granular Permissions**: Grant only the permissions needed for the task at hand.

2. **Namespace Isolation**: Use namespaces to isolate resources and limit the scope of permissions.

3. **Avoid Cluster-Admin**: Minimize the use of cluster-admin role, which grants unrestricted access.

4. **Regular Auditing**: Regularly review and audit RBAC policies to ensure they follow the principle of least privilege.

### 9. Security Context and Pod Security

Security contexts define privilege and access control settings for Pods and containers.

**Container Security Contexts:**

1. **User and Group Settings**: Specify the user and group IDs under which the container processes run.

2. **Capabilities**: Add or drop Linux capabilities. For example, adding NET_ADMIN allows network administration operations.

3. **Privilege Settings**: Control whether the container can gain additional privileges beyond its parent process.

4. **Read-Only Root Filesystem**: Prevent writes to the container's root filesystem for added security.

**Pod Security Contexts:**

1. **Pod-level Settings**: Apply to all containers in the Pod.

2. **runAsUser/runAsGroup**: Set the user and group IDs for all containers.

3. **fsGroup**: Set the group ID for volumes mounted in the Pod.

4. **supplementalGroups**: Additional groups that apply to all containers.

**SecurityContext Fields:**

1. **allowPrivilegeEscalation**: Controls whether a process can gain more privileges than its parent process.

2. **privileged**: Gives the container nearly all the same access as processes on the host.

3. **readOnlyRootFilesystem**: Forces the container's root filesystem to be read-only.

4. **seccompProfile**: Specifies the seccomp profile for syscall restriction.

5. **seLinuxOptions**: Configures SELinux options for the container.

**Pod Security Standards:**

1. **Migration from PodSecurityPolicies**: Pod Security Standards are the successor to the deprecated PodSecurityPolicy.

2. **Enforcement Levels**: Pod Security Admission Controller can enforce standards at different levels: warn, audit, or enforce.

3. **Implementation**: Enabled through the Pod Security Admission Controller, which is built into Kubernetes from v1.22 onwards.

4. **Security Levels**: Define different levels of restrictions (privileged, baseline, restricted) based on the security requirements of your workloads.

This comprehensive coverage of key concepts provides you with the foundational knowledge needed to understand Kubernetes architecture, deployment, and security. These concepts directly align with the hands-on labs that follow, where you'll apply this knowledge in practical scenarios that mirror the CKA exam.

---

### Lab 1: Setting Up a Development Environment

#### Objective
Set up your local environment with kubectl and essential tools for interacting with Kubernetes clusters.

#### Prerequisites
- Linux/macOS/Windows system with admin/sudo privileges
- Internet connectivity to download packages

#### Step 1: Install kubectl
```bash
# For Ubuntu/Debian
sudo apt-get update
sudo apt-get install -y apt-transport-https ca-certificates curl
curl -fsSL https://pkgs.k8s.io/core:/stable:/v1.28/deb/Release.key | sudo gpg --dearmor -o /etc/apt/keyrings/kubernetes-apt-keyring.gpg
echo 'deb [signed-by=/etc/apt/keyrings/kubernetes-apt-keyring.gpg] https://pkgs.k8s.io/core:/stable:/v1.28/deb/ /' | sudo tee /etc/apt/sources.list.d/kubernetes.list
sudo apt-get update
sudo apt-get install -y kubectl

# Verify installation
kubectl version --client
```

#### Step 2: Configure kubectl auto-completion
```bash
# For bash
echo 'source <(kubectl completion bash)' >>~/.bashrc
echo 'alias k=kubectl' >>~/.bashrc
echo 'complete -o default -F __start_kubectl k' >>~/.bashrc
source ~/.bashrc

# For zsh
echo 'source <(kubectl completion zsh)' >>~/.zshrc
echo 'alias k=kubectl' >>~/.zshrc
echo 'complete -o default -F __start_kubectl k' >>~/.zshrc
source ~/.zshrc
```

#### Step 3: Explore kubectl commands
```bash
# Get a list of all API resources
kubectl api-resources

# Explore kubectl help
kubectl --help

# Explore a specific command help
kubectl create --help

# Use kubectl explain to understand resource definitions
kubectl explain pod
kubectl explain pod.spec
kubectl explain pod.spec.containers
```

#### Step 4: Create a test configuration
```bash
# Create a sample kubeconfig file for practice
mkdir -p ~/.kube
cat > ~/.kube/config-practice << EOF
apiVersion: v1
kind: Config
clusters:
- cluster:
    server: https://example-cluster:6443
  name: example-cluster
contexts:
- context:
    cluster: example-cluster
    user: example-user
    namespace: default
  name: example-context
current-context: example-context
users:
- name: example-user
  user:
    token: example-token
EOF

# Set KUBECONFIG to use this file (temporary)
export KUBECONFIG=~/.kube/config-practice

# View the contexts
kubectl config get-contexts

# Switch back to your regular config
export KUBECONFIG=~/.kube/config
```

---

### Lab 2: Understanding Kubernetes Objects

#### Objective
Create and explore Kubernetes objects using YAML manifests and kubectl commands.

#### Prerequisites
- kubectl installed and configured
- Access to a Kubernetes cluster or minikube

#### Step 1: Create a simple Pod YAML manifest
```bash
# Create a directory for your manifests
mkdir -p ~/k8s-practice/pods

# Create a Pod manifest
cat > ~/k8s-practice/pods/nginx-pod.yaml << EOF
apiVersion: v1
kind: Pod
metadata:
  name: nginx
  labels:
    app: nginx
spec:
  containers:
  - name: nginx
    image: nginx:1.21
    ports:
    - containerPort: 80
EOF
```

#### Step 2: Create the Pod and explore it
```bash
# Create the Pod
kubectl apply -f ~/k8s-practice/pods/nginx-pod.yaml

# Get Pod information
kubectl get pods
kubectl get pod nginx -o wide

# Describe the Pod
kubectl describe pod nginx

# Get the Pod YAML with kubectl
kubectl get pod nginx -o yaml > ~/k8s-practice/pods/nginx-pod-full.yaml

# Examine the full YAML to see all the fields Kubernetes adds
cat ~/k8s-practice/pods/nginx-pod-full.yaml
```

#### Step 3: Work with labels and selectors
```bash
# Create a Pod with multiple labels
cat > ~/k8s-practice/pods/nginx-labels.yaml << EOF
apiVersion: v1
kind: Pod
metadata:
  name: nginx-labels
  labels:
    app: nginx
    environment: test
    tier: frontend
spec:
  containers:
  - name: nginx
    image: nginx:1.21
EOF

# Apply the manifest
kubectl apply -f ~/k8s-practice/pods/nginx-labels.yaml

# Query Pods using different label selectors
kubectl get pods -l app=nginx
kubectl get pods -l 'environment in (test,prod)'
kubectl get pods -l 'app=nginx,tier=frontend'

# Add a new label to an existing Pod
kubectl label pod nginx version=v1

# Remove a label
kubectl label pod nginx version-

# List Pods with custom columns showing labels
kubectl get pods -L app,environment,tier
```

#### Step 4: Explore Pod lifecycle
```bash
# Create a Pod that will complete quickly
cat > ~/k8s-practice/pods/oneshot-pod.yaml << EOF
apiVersion: v1
kind: Pod
metadata:
  name: oneshot
spec:
  restartPolicy: Never
  containers:
  - name: busybox
    image: busybox
    command: ['sh', '-c', 'echo Hello Kubernetes && sleep 5']
EOF

# Create the Pod
kubectl apply -f ~/k8s-practice/pods/oneshot-pod.yaml

# Watch the Pod status change
kubectl get pods -w

# Once completed, describe to see completion information
kubectl describe pod oneshot

# View Pod logs
kubectl logs oneshot

# Create a Pod that fails
cat > ~/k8s-practice/pods/failing-pod.yaml << EOF
apiVersion: v1
kind: Pod
metadata:
  name: failing-pod
spec:
  restartPolicy: OnFailure
  containers:
  - name: busybox
    image: busybox
    command: ['sh', '-c', 'echo Starting && exit 1']
EOF

# Create the Pod
kubectl apply -f ~/k8s-practice/pods/failing-pod.yaml

# Watch the Pod restart
kubectl get pods -w

# Check the restart count and last state
kubectl describe pod failing-pod
```

---

### Lab 3: Exploring the Control Plane

#### Objective
Examine Kubernetes control plane components and their functions.

#### Prerequisites
- Access to a Kubernetes cluster with admin permissions
- kubectl configured to communicate with the cluster

#### Step 1: Inspect control plane components
```bash
# Get control plane Pods (on a kubeadm-based cluster)
kubectl get pods -n kube-system

# Describe the API server Pod
kubectl describe pod -n kube-system -l component=kube-apiserver

# Examine the scheduler
kubectl describe pod -n kube-system -l component=kube-scheduler

# Look at the controller manager
kubectl describe pod -n kube-system -l component=kube-controller-manager

# Check etcd configuration
kubectl describe pod -n kube-system -l component=etcd
```

#### Step 2: Understand leader election
```bash
# Examine the Kubernetes endpoints for leader election
kubectl -n kube-system get endpoints kube-scheduler -o yaml
kubectl -n kube-system get endpoints kube-controller-manager -o yaml

# In a multi-master setup, you would see annotations indicating which instance is the leader
```

#### Step 3: Explore API server request flow
```bash
# Generate a verbose API request to see the complete flow
kubectl get pods -v=8

# Look at the API server audit logs (if enabled)
kubectl logs -n kube-system -l component=kube-apiserver | grep audit

# List admission controllers enabled in the API server
kubectl describe pod -n kube-system -l component=kube-apiserver | grep enable-admission-plugins

# List mutating admission webhook configurations
kubectl get mutatingwebhookconfigurations

# List validating admission webhook configurations
kubectl get validatingwebhookconfigurations
```

---

### Lab 4: Preparing Nodes for Kubernetes

#### Objective
Prepare Linux nodes to serve as Kubernetes cluster nodes.

#### Prerequisites
- Access to multiple Linux machines (at least 2 - one control plane, one worker)
- Root/sudo access on all machines
- Network connectivity between nodes

#### Step 1: System configuration requirements
```bash
# Run on all nodes

# Update system
sudo apt-get update
sudo apt-get upgrade -y

# Disable swap
sudo swapoff -a
sudo sed -i '/ swap / s/^\(.*\)$/#\1/g' /etc/fstab

# Load required kernel modules
cat <<EOF | sudo tee /etc/modules-load.d/k8s.conf
overlay
br_netfilter
EOF

sudo modprobe overlay
sudo modprobe br_netfilter

# Set kernel parameters
cat <<EOF | sudo tee /etc/sysctl.d/k8s.conf
net.bridge.bridge-nf-call-iptables  = 1
net.bridge.bridge-nf-call-ip6tables = 1
net.ipv4.ip_forward                 = 1
EOF

sudo sysctl --system

# Verify the modules are loaded
lsmod | grep overlay
lsmod | grep br_netfilter

# Verify kernel parameters
sysctl net.bridge.bridge-nf-call-iptables net.bridge.bridge-nf-call-ip6tables net.ipv4.ip_forward
```

#### Step 2: Installing container runtime (containerd)
```bash
# Run on all nodes

# Install prerequisites
sudo apt-get update
sudo apt-get install -y apt-transport-https ca-certificates curl gnupg lsb-release

# Add Docker's official GPG key
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /usr/share/keyrings/docker-archive-keyring.gpg

# Set up the repository
echo "deb [arch=amd64 signed-by=/usr/share/keyrings/docker-archive-keyring.gpg] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null

# Install containerd
sudo apt-get update
sudo apt-get install -y containerd.io

# Configure containerd to use systemd cgroup driver
sudo mkdir -p /etc/containerd
containerd config default | sudo tee /etc/containerd/config.toml
sudo sed -i 's/SystemdCgroup = false/SystemdCgroup = true/g' /etc/containerd/config.toml

# Restart containerd
sudo systemctl restart containerd
sudo systemctl enable containerd
```

#### Step 3: Install kubeadm, kubelet, and kubectl
```bash
# Run on all nodes

# Add Kubernetes apt repository signing key
sudo curl -fsSLo /usr/share/keyrings/kubernetes-archive-keyring.gpg https://packages.cloud.google.com/apt/doc/apt-key.gpg

# Add Kubernetes apt repository
echo "deb [signed-by=/usr/share/keyrings/kubernetes-archive-keyring.gpg] https://apt.kubernetes.io/ kubernetes-xenial main" | sudo tee /etc/apt/sources.list.d/kubernetes.list

# Install kubeadm, kubelet, and kubectl
sudo apt-get update
sudo apt-get install -y kubelet kubeadm kubectl

# Pin their versions to prevent accidental upgrades
sudo apt-mark hold kubelet kubeadm kubectl

# Check versions
kubeadm version
kubectl version --client
kubelet --version
```

#### Step 4: Verify network prerequisites
```bash
# Run on all nodes

# Check if the node is ready for Kubernetes networking
ip link
ip addr

# Make sure all nodes can reach each other
# Replace <IP> with the IP of other nodes
ping -c 3 <IP>

# Check firewall rules or disable firewall for testing
sudo ufw status
sudo ufw disable  # For testing only

# Ensure required ports are open (using netcat or telnet)
# Replace <IP> with the IP of control plane node
nc -zv <IP> 6443  # API server
```

---

### Lab 5: Bootstrapping a Kubernetes Cluster

#### Objective
Initialize a Kubernetes control plane using kubeadm and set up networking.

#### Prerequisites
- Nodes prepared according to Lab 1
- Network connectivity between nodes
- Required ports open

#### Step 1: Initialize control plane
```bash
# Run on control plane node only

# Create a kubeadm configuration file
cat > ~/kubeadm-config.yaml << EOF
apiVersion: kubeadm.k8s.io/v1beta3
kind: InitConfiguration
nodeRegistration:
  criSocket: "unix:///run/containerd/containerd.sock"
---
apiVersion: kubeadm.k8s.io/v1beta3
kind: ClusterConfiguration
networking:
  podSubnet: "192.168.0.0/16"  # Required for Calico
EOF

# Initialize the control plane
sudo kubeadm init --config=~/kubeadm-config.yaml --upload-certs | tee ~/kubeadm-init.log

# Set up kubectl for the current user
mkdir -p $HOME/.kube
sudo cp -i /etc/kubernetes/admin.conf $HOME/.kube/config
sudo chown $(id -u):$(id -g) $HOME/.kube/config

# Verify the control plane is running
kubectl get nodes
kubectl get pods -n kube-system
```

#### Step 2: Install Calico network plugin
```bash
# Run on control plane node only

# Install Calico operator
kubectl create -f https://raw.githubusercontent.com/projectcalico/calico/v3.26.1/manifests/tigera-operator.yaml

# Install Calico custom resources
kubectl create -f https://raw.githubusercontent.com/projectcalico/calico/v3.26.1/manifests/custom-resources.yaml

# Verify that Calico pods are running
kubectl get pods -n calico-system -w

# Verify that CoreDNS pods are running (they will transition to Running once the network is ready)
kubectl get pods -n kube-system -l k8s-app=kube-dns
```

#### Step 3: Join worker nodes
```bash
# Get the join command from the control plane node
# Look for the line starting with "kubeadm join" in the kubeadm-init.log file
cat ~/kubeadm-init.log | grep -A 2 "kubeadm join"

# Run the join command on each worker node
# Example (the actual command will be different):
sudo kubeadm join 192.168.1.100:6443 --token abcdef.0123456789abcdef \
    --discovery-token-ca-cert-hash sha256:1234567890abcdef1234567890abcdef1234567890abcdef1234567890abcdef

# If the token has expired, generate a new one on the control plane node
kubeadm token create --print-join-command
```

#### Step 4: Verify cluster status
```bash
# Run on control plane node

# Check node status (wait for all nodes to be Ready)
kubectl get nodes -w

# Check that system pods are running
kubectl get pods --all-namespaces

# Verify cluster info
kubectl cluster-info

# Test pod networking by creating a test deployment
kubectl create deployment nginx --image=nginx
kubectl scale deployment nginx --replicas=3

# Check that pods are distributed across nodes
kubectl get pods -o wide
```

---

### Lab 6: Adding Nodes and Managing the Cluster

#### Objective
Learn how to manage a Kubernetes cluster, including node operations, upgrades, and backups.

#### Prerequisites
- Running Kubernetes cluster from Lab 2
- kubectl configured to communicate with the cluster

#### Step 1: Verify node status and readiness
```bash
# Check node status
kubectl get nodes
kubectl describe nodes

# Check resource usage on nodes
kubectl top nodes

# View node labels
kubectl get nodes --show-labels
```

#### Step 2: Perform a cluster upgrade
```bash
# On control plane node:

# Check current versions
kubectl version
kubelet --version

# Install the new kubeadm version
sudo apt-get update
sudo apt-mark unhold kubeadm
sudo apt-get install -y kubeadm=1.28.1-00
sudo apt-mark hold kubeadm

# Plan the upgrade
sudo kubeadm upgrade plan

# Apply the upgrade
sudo kubeadm upgrade apply v1.28.1

# Upgrade kubelet and kubectl on control plane
sudo apt-mark unhold kubelet kubectl
sudo apt-get install -y kubelet=1.28.1-00 kubectl=1.28.1-00
sudo apt-mark hold kubelet kubectl
sudo systemctl daemon-reload
sudo systemctl restart kubelet

# On worker nodes:
# Drain the node
kubectl drain <node-name> --ignore-daemonsets

# Upgrade kubeadm
sudo apt-mark unhold kubeadm
sudo apt-get update
sudo apt-get install -y kubeadm=1.28.1-00
sudo apt-mark hold kubeadm

# Upgrade node configuration
sudo kubeadm upgrade node

# Upgrade kubelet and kubectl
sudo apt-mark unhold kubelet kubectl
sudo apt-get install -y kubelet=1.28.1-00 kubectl=1.28.1-00
sudo apt-mark hold kubelet kubectl
sudo systemctl daemon-reload
sudo systemctl restart kubelet

# Uncordon the node
kubectl uncordon <node-name>
```

#### Step 3: Backup and restore etcd
```bash
# Backup etcd
# First, find the etcd pod
kubectl get pods -n kube-system | grep etcd

# Get etcd certificates location
sudo ls -la /etc/kubernetes/pki/etcd/

# Create a backup of etcd
sudo ETCDCTL_API=3 etcdctl --endpoints=https://127.0.0.1:2379 \
  --cacert=/etc/kubernetes/pki/etcd/ca.crt \
  --cert=/etc/kubernetes/pki/etcd/server.crt \
  --key=/etc/kubernetes/pki/etcd/server.key \
  snapshot save /tmp/etcd-backup.db

# Verify the backup
sudo ETCDCTL_API=3 etcdctl --write-out=table snapshot status /tmp/etcd-backup.db

# To restore from a backup (in a disaster scenario)
# First, stop the API server
sudo systemctl stop kubelet
sudo docker ps | grep kube-apiserver | awk '{print $1}' | xargs sudo docker kill

# Then restore from backup
sudo ETCDCTL_API=3 etcdctl --endpoints=https://127.0.0.1:2379 \
  --cacert=/etc/kubernetes/pki/etcd/ca.crt \
  --cert=/etc/kubernetes/pki/etcd/server.crt \
  --key=/etc/kubernetes/pki/etcd/server.key \
  --data-dir=/var/lib/etcd-backup \
  snapshot restore /tmp/etcd-backup.db

# Update etcd manifest to use restored data
sudo sed -i 's/\/var\/lib\/etcd/\/var\/lib\/etcd-backup/g' /etc/kubernetes/manifests/etcd.yaml

# Restart kubelet
sudo systemctl start kubelet
```

---

### Lab 7: Configuring Authentication and Authorization

#### Objective
Create and manage RBAC configurations for different users and service accounts.

#### Prerequisites
- Running Kubernetes cluster
- Admin access to the cluster

#### Step 1: Create service accounts
```bash
# Create a namespace for our experiments
kubectl create namespace rbac-test

# Create a service account
kubectl create serviceaccount restricted-sa -n rbac-test

# View the service account
kubectl get serviceaccount -n rbac-test
kubectl describe serviceaccount restricted-sa -n rbac-test
```

#### Step 2: Create Roles and RoleBindings
```bash
# Create a Role that allows read-only access to pods
cat > ~/k8s-practice/rbac/read-pods-role.yaml << EOF
apiVersion: rbac.authorization.k8s.io/v1
kind: Role
metadata:
  namespace: rbac-test
  name: pod-reader
rules:
- apiGroups: [""]
  resources: ["pods"]
  verbs: ["get", "watch", "list"]
EOF

kubectl apply -f ~/k8s-practice/rbac/read-pods-role.yaml

# Create a RoleBinding to bind the Role to the service account
cat > ~/k8s-practice/rbac/read-pods-rolebinding.yaml << EOF
apiVersion: rbac.authorization.k8s.io/v1
kind: RoleBinding
metadata:
  name: read-pods
  namespace: rbac-test
subjects:
- kind: ServiceAccount
  name: restricted-sa
  namespace: rbac-test
roleRef:
  kind: Role
  name: pod-reader
  apiGroup: rbac.authorization.k8s.io
EOF

kubectl apply -f ~/k8s-practice/rbac/read-pods-rolebinding.yaml
```

#### Step 3: Create ClusterRoles and ClusterRoleBindings
```bash
# Create a ClusterRole that allows read-only access to nodes
cat > ~/k8s-practice/rbac/node-reader-clusterrole.yaml << EOF
apiVersion: rbac.authorization.k8s.io/v1
kind: ClusterRole
metadata:
  name: node-reader
rules:
- apiGroups: [""]
  resources: ["nodes"]
  verbs: ["get", "watch", "list"]
EOF

kubectl apply -f ~/k8s-practice/rbac/node-reader-clusterrole.yaml

# Create a ClusterRoleBinding to bind the ClusterRole to the service account
cat > ~/k8s-practice/rbac/node-reader-clusterrolebinding.yaml << EOF
apiVersion: rbac.authorization.k8s.io/v1
kind: ClusterRoleBinding
metadata:
  name: read-nodes
subjects:
- kind: ServiceAccount
  name: restricted-sa
  namespace: rbac-test
roleRef:
  kind: ClusterRole
  name: node-reader
  apiGroup: rbac.authorization.k8s.io
EOF

kubectl apply -f ~/k8s-practice/rbac/node-reader-clusterrolebinding.yaml
```

#### Step 4: Test RBAC configurations
```bash
# Create a Pod to test the permissions
cat > ~/k8s-practice/rbac/auth-tester-pod.yaml << EOF
apiVersion: v1
kind: Pod
metadata:
  name: auth-tester
  namespace: rbac-test
spec:
  serviceAccountName: restricted-sa
  containers:
  - name: auth-tester
    image: curlimages/curl
    command: ["sleep", "3600"]
EOF

kubectl apply -f ~/k8s-practice/rbac/auth-tester-pod.yaml

# Execute commands in the Pod to test permissions
kubectl exec -it -n rbac-test auth-tester -- sh

# Inside the Pod, try to access different resources
# Get a token
TOKEN=$(cat /var/run/secrets/kubernetes.io/serviceaccount/token)

# Try to list pods in the namespace (should succeed)
curl -s -k -H "Authorization: Bearer $TOKEN" \
  https://kubernetes.default.svc/api/v1/namespaces/rbac-test/pods/

# Try to list services in the namespace (should fail)
curl -s -k -H "Authorization: Bearer $TOKEN" \
  https://kubernetes.default.svc/api/v1/namespaces/rbac-test/services/

# Try to list nodes (should succeed)
curl -s -k -H "Authorization: Bearer $TOKEN" \
  https://kubernetes.default.svc/api/v1/nodes/

# Exit the pod
exit
```

---

### Lab 8: Implementing Security Contexts

#### Objective
Configure security contexts for Pods and containers to enhance security posture.

#### Prerequisites
- Running Kubernetes cluster
- kubectl access to the cluster

#### Step 1: Create Pods with security contexts
```bash
# Create a Pod with a security context that sets user and group IDs
cat > ~/k8s-practice/security/security-context-pod.yaml << EOF
apiVersion: v1
kind: Pod
metadata:
  name: security-context-demo
namespace: rbac-test
spec:
  securityContext:
    runAsUser: 1000
    runAsGroup: 3000
    fsGroup: 2000
  containers:
  - name: sec-ctx-container
    image: busybox
    command: ["sh", "-c", "sleep 3600"]
    securityContext:
      allowPrivilegeEscalation: false
    volumeMounts:
    - name: sec-ctx-vol
      mountPath: /data/demo
  volumes:
  - name: sec-ctx-vol
    emptyDir: {}
EOF

kubectl apply -f ~/k8s-practice/security/security-context-pod.yaml

# Verify the Pod is running
kubectl get pod security-context-demo -n rbac-test
```

#### Step 2: Test user and group settings
```bash
# Check the security context settings
kubectl exec -it security-context-demo -n rbac-test -- sh

# Inside the Pod, check the user and group IDs
id

# Check file permissions on the mounted volume
ls -la /data/demo

# Try to create a file
touch /data/demo/file1
ls -la /data/demo/file1

# Exit the Pod
exit
```

#### Step 3: Create a Pod with capabilities
```bash
# Create a Pod with specific Linux capabilities
cat > ~/k8s-practice/security/capabilities-pod.yaml << EOF
apiVersion: v1
kind: Pod
metadata:
  name: capabilities-demo
  namespace: rbac-test
spec:
  containers:
  - name: capabilities-container
    image: ubuntu
    command: ["sleep", "3600"]
    securityContext:
      capabilities:
        add: ["NET_ADMIN", "SYS_TIME"]
        drop: ["ALL"]
EOF

kubectl apply -f ~/k8s-practice/security/capabilities-pod.yaml

# Verify the Pod is running
kubectl get pod capabilities-demo -n rbac-test
```

#### Step 4: Create a Pod with a read-only root filesystem
```bash
# Create a Pod with a read-only root filesystem
cat > ~/k8s-practice/security/readonly-pod.yaml << EOF
apiVersion: v1
kind: Pod
metadata:
  name: readonly-demo
  namespace: rbac-test
spec:
  containers:
  - name: readonly-container
    image: nginx
    securityContext:
      readOnlyRootFilesystem: true
    volumeMounts:
    - name: var-run
      mountPath: /var/run
    - name: var-cache-nginx
      mountPath: /var/cache/nginx
    - name: var-log-nginx
      mountPath: /var/log/nginx
  volumes:
  - name: var-run
    emptyDir: {}
  - name: var-cache-nginx
    emptyDir: {}
  - name: var-log-nginx
    emptyDir: {}
EOF

kubectl apply -f ~/k8s-practice/security/readonly-pod.yaml

# Verify the Pod is running
kubectl get pod readonly-demo -n rbac-test

# Test the read-only filesystem
kubectl exec -it readonly-demo -n rbac-test -- sh

# Try to create a file in the root filesystem (should fail)
touch /test-file

# Try to create a file in a mounted volume (should succeed)
touch /var/run/test-file
ls -la /var/run/test-file

# Exit the Pod
exit
```

---

### Lab 9: Securing the Kubernetes API Server

#### Objective
Examine and configure API server security settings.

#### Prerequisites
- Running Kubernetes cluster with administrative access
- Control plane access

#### Step 1: Examine current API server configuration
```bash
# View API server Pod definition
kubectl get pod -n kube-system -l component=kube-apiserver -o yaml

# Examine the command-line arguments
kubectl describe pod -n kube-system -l component=kube-apiserver | grep "\--"

# Check the currently enabled admission controllers
kubectl describe pod -n kube-system -l component=kube-apiserver | grep enable-admission-plugins
```

#### Step 2: Configure API server audit logging
```bash
# Create an audit policy file on the control plane node
sudo mkdir -p /etc/kubernetes/audit

sudo cat > /etc/kubernetes/audit/policy.yaml << EOF
apiVersion: audit.k8s.io/v1
kind: Policy
rules:
- level: Metadata
  resources:
  - group: ""
    resources: ["pods", "services"]
- level: RequestResponse
  resources:
  - group: ""
    resources: ["secrets"]
  namespaces: ["rbac-test"]
- level: None
  users: ["system:serviceaccount:kube-system:default"]
  resources:
  - group: ""
    resources: ["configmaps"]
    resourceNames: ["controller-leader"]
- level: None
  nonResourceURLs:
  - /healthz*
  - /version
  - /swagger*
EOF

# Modify the API server manifest to enable audit logging
sudo cp /etc/kubernetes/manifests/kube-apiserver.yaml /etc/kubernetes/kube-apiserver.yaml.bak

# Edit the API server manifest (manually with an editor)
sudo nano /etc/kubernetes/manifests/kube-apiserver.yaml

# Add the following parameters to the command section:
# - --audit-policy-file=/etc/kubernetes/audit/policy.yaml
# - --audit-log-path=/var/log/kubernetes/audit/audit.log
# - --audit-log-maxage=30
# - --audit-log-maxbackup=3
# - --audit-log-maxsize=100

# Add the following volumeMounts to the container section:
# - mountPath: /etc/kubernetes/audit
#   name: audit-policy
#   readOnly: true
# - mountPath: /var/log/kubernetes/audit
#   name: audit-log

# Add the following volumes to the volumes section:
# - hostPath:
#     path: /etc/kubernetes/audit
#     type: DirectoryOrCreate
#   name: audit-policy
# - hostPath:
#     path: /var/log/kubernetes/audit
#     type: DirectoryOrCreate
#   name: audit-log

# Create the audit log directory
sudo mkdir -p /var/log/kubernetes/audit

# The kubelet will automatically pick up the changes and restart the API server
# Wait for the API server to restart
sleep 30
kubectl get pods -n kube-system

# Check that audit logs are being generated
sudo ls -la /var/log/kubernetes/audit/
```

#### Step 3: Implement admission controllers
```bash
# Examine existing admission controllers
kubectl describe pod -n kube-system -l component=kube-apiserver | grep enable-admission-plugins

# Edit the API server manifest to add additional admission controllers
sudo nano /etc/kubernetes/manifests/kube-apiserver.yaml

# Add or modify the --enable-admission-plugins flag to include:
# --enable-admission-plugins=NodeRestriction,PodSecurityPolicy,EventRateLimit

# The kubelet will automatically pick up the changes and restart the API server
# Wait for the API server to restart
sleep 30
kubectl get pods -n kube-system
```

#### Step 4: Configure authentication methods
```bash
# Create a directory for certificates
mkdir -p ~/k8s-practice/certs

# Create a private key for a new user
openssl genrsa -out ~/k8s-practice/certs/jane.key 2048

# Create a certificate signing request
openssl req -new -key ~/k8s-practice/certs/jane.key -out ~/k8s-practice/certs/jane.csr -subj "/CN=jane/O=development"

# Get the CSR in base64 format
cat ~/k8s-practice/certs/jane.csr | base64 | tr -d '\n'

# Create a Kubernetes CSR object
cat > ~/k8s-practice/certs/jane-csr.yaml << EOF
apiVersion: certificates.k8s.io/v1
kind: CertificateSigningRequest
metadata:
  name: jane
spec:
  request: $(cat ~/k8s-practice/certs/jane.csr | base64 | tr -d '\n')
  signerName: kubernetes.io/kube-apiserver-client
  expirationSeconds: 86400  # one day
  usages:
  - client auth
EOF

kubectl apply -f ~/k8s-practice/certs/jane-csr.yaml

# Approve the CSR
kubectl certificate approve jane

# Get the signed certificate
kubectl get csr jane -o jsonpath='{.status.certificate}' | base64 --decode > ~/k8s-practice/certs/jane.crt

# Create a role and role binding for the new user
cat > ~/k8s-practice/certs/developer-role.yaml << EOF
apiVersion: rbac.authorization.k8s.io/v1
kind: Role
metadata:
  namespace: rbac-test
  name: developer
rules:
- apiGroups: [""]
  resources: ["pods", "services"]
  verbs: ["get", "list", "watch", "create", "update", "patch", "delete"]
---
apiVersion: rbac.authorization.k8s.io/v1
kind: RoleBinding
metadata:
  name: jane-developer
  namespace: rbac-test
subjects:
- kind: User
  name: jane
  apiGroup: rbac.authorization.k8s.io
roleRef:
  kind: Role
  name: developer
  apiGroup: rbac.authorization.k8s.io
EOF

kubectl apply -f ~/k8s-practice/certs/developer-role.yaml

# Create a new kubeconfig for the user
CLUSTER_NAME=$(kubectl config view --minify -o jsonpath='{.clusters[0].name}')
SERVER=$(kubectl config view --minify -o jsonpath='{.clusters[0].cluster.server}')
CA_CERT=$(kubectl config view --raw --minify --flatten -o jsonpath='{.clusters[0].cluster.certificate-authority-data}')

kubectl config set-cluster ${CLUSTER_NAME} \
    --server=${SERVER} \
    --certificate-authority=~/k8s-practice/certs/ca.crt \
    --embed-certs=true \
    --kubeconfig=~/k8s-practice/certs/jane-kubeconfig

kubectl config set-credentials jane \
    --client-certificate=~/k8s-practice/certs/jane.crt \
    --client-key=~/k8s-practice/certs/jane.key \
    --embed-certs=true \
    --kubeconfig=~/k8s-practice/certs/jane-kubeconfig

kubectl config set-context jane-context \
    --cluster=${CLUSTER_NAME} \
    --namespace=rbac-test \
    --user=jane \
    --kubeconfig=~/k8s-practice/certs/jane-kubeconfig

kubectl config use-context jane-context --kubeconfig=~/k8s-practice/certs/jane-kubeconfig

# Test the new kubeconfig
kubectl --kubeconfig=~/k8s-practice/certs/jane-kubeconfig get pods -n rbac-test
```
---

### Practice Exercises

The following practice exercises cover important CKA topics that complement our lab work. Each exercise focuses on key skills you'll need for the certification exam.

#### Exercise 1: Inspecting and Troubleshooting Control Plane Components

##### Scenario
You're an administrator of a Kubernetes cluster and need to investigate why the scheduler is not functioning properly.

##### Tasks
1. Identify all control plane components running in the cluster
2. Check the status and logs of the scheduler Pod
3. Determine if there are any configuration issues
4. Restore scheduler functionality

##### Steps
```bash
# 1. List all control plane components
kubectl get pods -n kube-system

# 2. Check the scheduler logs
kubectl logs -n kube-system kube-scheduler-<control-plane-node-name>

# If you see error logs, examine the scheduler manifest
sudo cat /etc/kubernetes/manifests/kube-scheduler.yaml

# 3. Check for configuration issues (common problems include):
# - Incorrect flags or configuration
# - Path issues for certificates
# - Permission problems

# 4. To fix a broken scheduler, you might need to:
sudo cp /etc/kubernetes/manifests/kube-scheduler.yaml /tmp/kube-scheduler-backup.yaml
sudo nano /etc/kubernetes/manifests/kube-scheduler.yaml
# Fix any identified issues
# The kubelet will automatically recreate the Pod

# Verify the scheduler is functioning
kubectl get pods -n kube-system | grep scheduler
```

---

#### Exercise 2: Advanced etcd Backup and Restore

##### Scenario
Your organization requires regular backups of etcd data. You need to create a backup strategy and successfully perform a restore operation.

##### Tasks
1. Create a proper etcd backup with appropriate certificates
2. Simulate a data loss scenario
3. Restore etcd from your backup
4. Verify the cluster is functioning correctly post-restoration

##### Steps
```bash
# 1. Create a proper backup
# First, identify the etcd container
kubectl -n kube-system get pods | grep etcd

# Find the endpoint and certificate locations from the etcd pod definition
kubectl -n kube-system describe pod etcd-<control-plane-node-name>

# Create a backup with proper certificates
sudo ETCDCTL_API=3 etcdctl snapshot save /tmp/etcd-backup-$(date +%Y%m%d-%H%M%S).db \
  --endpoints=https://127.0.0.1:2379 \
  --cacert=/etc/kubernetes/pki/etcd/ca.crt \
  --cert=/etc/kubernetes/pki/etcd/server.crt \
  --key=/etc/kubernetes/pki/etcd/server.key

# Verify the backup is valid
sudo ETCDCTL_API=3 etcdctl --write-out=table snapshot status \
  /tmp/etcd-backup-*.db

# 2. Simulate data loss (in a real scenario, you'd never do this in production)
# For practice purposes, you might create a test namespace and some resources, then "break" something

# 3. To restore from backup, first stop the API server and etcd
sudo systemctl stop kubelet
sudo docker ps | grep etcd | awk '{print $1}' | xargs sudo docker stop

# Restore the etcd data
sudo ETCDCTL_API=3 etcdctl snapshot restore /tmp/etcd-backup-*.db \
  --data-dir=/var/lib/etcd-restore \
  --name=<control-plane-node-name> \
  --initial-cluster=<control-plane-node-name>=https://127.0.0.1:2380 \
  --initial-cluster-token=etcd-cluster-1 \
  --initial-advertise-peer-urls=https://127.0.0.1:2380

# Update etcd manifest to use the restored data directory
sudo sed -i.bak "s|/var/lib/etcd|/var/lib/etcd-restore|g" /etc/kubernetes/manifests/etcd.yaml

# Restart the kubelet
sudo systemctl restart kubelet

# 4. Verify the cluster is functioning
kubectl get nodes
kubectl get pods --all-namespaces
```

---

#### Exercise 3: Installing and Using Helm

##### Scenario
Your team has decided to use Helm to manage applications in the Kubernetes cluster. You need to set up Helm and deploy an application.

##### Tasks
1. Install Helm
2. Add the Bitnami repository
3. Install the Nginx chart
4. List, upgrade, and remove the release

##### Steps
```bash
# 1. Install Helm
curl -fsSL -o get_helm.sh https://raw.githubusercontent.com/helm/helm/main/scripts/get-helm-3
chmod 700 get_helm.sh
./get_helm.sh

# Verify installation
helm version

# 2. Add a chart repository
helm repo add bitnami https://charts.bitnami.com/bitnami
helm repo update

# 3. Install a chart
# First create a namespace for your Helm deployment
kubectl create namespace helm-test

# Install Nginx
helm install my-nginx bitnami/nginx --namespace helm-test

# Check status
helm status my-nginx -n helm-test
kubectl get all -n helm-test

# 4. Upgrade a release
helm upgrade my-nginx bitnami/nginx --set replicaCount=2 -n helm-test

# Verify the change
kubectl get pods -n helm-test

# Rollback to previous version
helm rollback my-nginx 1 -n helm-test

# List all releases
helm list --all-namespaces

# Uninstall a release
helm uninstall my-nginx -n helm-test
```

---

#### Exercise 4: Using Kustomize for Configuration Management

##### Scenario
You need to deploy the same application with different configurations across development, staging, and production environments.

##### Tasks
1. Create a base Kustomize configuration
2. Create overlays for different environments
3. Preview and apply the configurations

##### Steps
```bash
# 1. Create a base configuration
mkdir -p ~/kustomize-practice/base
cd ~/kustomize-practice/base

# Create a deployment.yaml file
cat > deployment.yaml << EOF
apiVersion: apps/v1
kind: Deployment
metadata:
  name: nginx-deployment
spec:
  replicas: 1
  selector:
    matchLabels:
      app: nginx
  template:
    metadata:
      labels:
        app: nginx
    spec:
      containers:
      - name: nginx
        image: nginx:1.21
        ports:
        - containerPort: 80
EOF

# Create a service.yaml file
cat > service.yaml << EOF
apiVersion: v1
kind: Service
metadata:
  name: nginx-service
spec:
  selector:
    app: nginx
  ports:
  - port: 80
    targetPort: 80
  type: ClusterIP
EOF

# Create a kustomization.yaml file
cat > kustomization.yaml << EOF
apiVersion: kustomize.config.k8s.io/v1beta1
kind: Kustomization
resources:
- deployment.yaml
- service.yaml
EOF

# 2. Create overlays for different environments
mkdir -p ~/kustomize-practice/overlays/{dev,staging,prod}

# Development overlay
cd ~/kustomize-practice/overlays/dev
cat > kustomization.yaml << EOF
apiVersion: kustomize.config.k8s.io/v1beta1
kind: Kustomization
namePrefix: dev-
resources:
- ../../base
namespace: development
patchesStrategicMerge:
- deployment-patch.yaml
EOF

cat > deployment-patch.yaml << EOF
apiVersion: apps/v1
kind: Deployment
metadata:
  name: nginx-deployment
spec:
  replicas: 1
EOF

# Staging overlay
cd ~/kustomize-practice/overlays/staging
cat > kustomization.yaml << EOF
apiVersion: kustomize.config.k8s.io/v1beta1
kind: Kustomization
namePrefix: staging-
resources:
- ../../base
namespace: staging
patchesStrategicMerge:
- deployment-patch.yaml
EOF

cat > deployment-patch.yaml << EOF
apiVersion: apps/v1
kind: Deployment
metadata:
  name: nginx-deployment
spec:
  replicas: 2
EOF

# Production overlay
cd ~/kustomize-practice/overlays/prod
cat > kustomization.yaml << EOF
apiVersion: kustomize.config.k8s.io/v1beta1
kind: Kustomization
namePrefix: prod-
resources:
- ../../base
namespace: production
patchesStrategicMerge:
- deployment-patch.yaml
EOF

cat > deployment-patch.yaml << EOF
apiVersion: apps/v1
kind: Deployment
metadata:
  name: nginx-deployment
spec:
  replicas: 3
EOF

# 3. Preview and apply the configurations
# Create namespaces
kubectl create namespace development
kubectl create namespace staging
kubectl create namespace production

# Preview development configuration
kubectl kustomize ~/kustomize-practice/overlays/dev

# Apply development configuration
kubectl apply -k ~/kustomize-practice/overlays/dev

# Apply other environments
kubectl apply -k ~/kustomize-practice/overlays/staging
kubectl apply -k ~/kustomize-practice/overlays/prod

# Verify deployments
kubectl get deployments --all-namespaces | grep nginx
```

---

#### Exercise 5: Understanding CRDs and Custom Resources

##### Scenario
You need to understand how Custom Resource Definitions work in Kubernetes and how to interact with custom resources.

##### Tasks
1. Create a simple Custom Resource Definition
2. Create a Custom Resource based on your CRD
3. Interact with your Custom Resources using kubectl

##### Steps
```bash
# 1. Create a Custom Resource Definition
cat > ~/crd-practice/crontab-crd.yaml << EOF
apiVersion: apiextensions.k8s.io/v1
kind: CustomResourceDefinition
metadata:
  name: crontabs.stable.example.com
spec:
  group: stable.example.com
  versions:
    - name: v1
      served: true
      storage: true
      schema:
        openAPIV3Schema:
          type: object
          properties:
            spec:
              type: object
              properties:
                cronSpec:
                  type: string
                image:
                  type: string
                replicas:
                  type: integer
              required: ["cronSpec", "image"]
  scope: Namespaced
  names:
    plural: crontabs
    singular: crontab
    kind: CronTab
    shortNames:
    - ct
EOF

kubectl apply -f ~/crd-practice/crontab-crd.yaml

# 2. Create a Custom Resource
cat > ~/crd-practice/my-crontab.yaml << EOF
apiVersion: stable.example.com/v1
kind: CronTab
metadata:
  name: my-cron
spec:
  cronSpec: "* * * * */5"
  image: my-cron-image:v1
  replicas: 3
EOF

kubectl apply -f ~/crd-practice/my-crontab.yaml

# 3. Interact with the Custom Resource
kubectl get crontabs
kubectl get ct  # Using the short name
kubectl describe crontab my-cron

# Edit the custom resource
kubectl edit crontab my-cron

# Delete the custom resource
kubectl delete crontab my-cron

# Clean up
kubectl delete -f ~/crd-practice/crontab-crd.yaml
```

---

#### Exercise 6: Configuring High-Availability for the Control Plane

##### Scenario
Your organization needs a highly available Kubernetes control plane to minimize downtime. You need to understand the requirements and steps for setting up an HA control plane.

##### Tasks
1. Identify the components needed for HA control plane
2. Configure a load balancer for API server (conceptual exercise)
3. Understand how to join additional control plane nodes
4. Verify control plane redundancy

##### Steps
```bash
# 1. Identify requirements for HA
# - Multiple control plane nodes (typically 3 or 5)
# - Load balancer for API server
# - Shared etcd cluster or stacked etcd

# 2. Set up a load balancer (conceptual - actual implementation depends on environment)
# This could be HAProxy, Nginx, cloud provider load balancer, etc.
# Example HAProxy configuration for Kubernetes API server:

cat > haproxy.cfg << EOF
frontend kubernetes-frontend
  bind *:6443
  mode tcp
  option tcplog
  default_backend kubernetes-backend

backend kubernetes-backend
  mode tcp
  option tcp-check
  balance roundrobin
  server control-plane1 192.168.1.101:6443 check fall 3 rise 2
  server control-plane2 192.168.1.102:6443 check fall 3 rise 2
  server control-plane3 192.168.1.103:6443 check fall 3 rise 2
EOF

# 3. Initialize the first control plane node with the load balancer endpoint
# When initializing with kubeadm, you'd use:
sudo kubeadm init --control-plane-endpoint "LOAD_BALANCER_DNS:LOAD_BALANCER_PORT" \
  --upload-certs \
  --pod-network-cidr=192.168.0.0/16

# This will output a command for joining additional control plane nodes, like:
# kubeadm join 192.168.1.100:6443 --token abcdef.0123456789abcdef \
#   --discovery-token-ca-cert-hash sha256:1234... \
#   --control-plane --certificate-key 0123456789abcdef...

# 4. Verify the control plane components
kubectl get pods -n kube-system
kubectl get nodes

# 5. Test failover (conceptual)
# In a real HA setup, you would:
# - Shutdown one control plane node
# - Verify the cluster still functions
# - Verify API requests still work
# - Bring the node back online
```

---

#### Exercise 7: Analyzing and Troubleshooting Cluster Networking

##### Scenario
You're investigating networking issues in your Kubernetes cluster. Pod-to-pod communication is failing, and you need to diagnose and fix the problems.

##### Tasks
1. Verify the CNI configuration
2. Check node-to-node connectivity
3. Diagnose pod-to-pod communication issues
4. Test service resolution

##### Steps
```bash
# 1. Verify the CNI configuration
# Check if CNI plugins are installed
ls -la /opt/cni/bin/

# Check CNI configuration
sudo cat /etc/cni/net.d/*

# Verify CNI pods are running
kubectl get pods -n kube-system | grep -E 'calico|flannel|cilium|weave'

# Check CNI logs
kubectl logs -n kube-system calico-node-xxxxx

# 2. Check node-to-node connectivity
# Check node IPs
kubectl get nodes -o wide

# Test connectivity between nodes (run on each node)
ping <node-ip>

# Check if required ports are open
sudo netstat -tulpn | grep -E '6443|10250|10251|10252|2379|2380'

# 3. Diagnose pod-to-pod communication issues
# Create test pods in different namespaces
kubectl create namespace network-test-1
kubectl create namespace network-test-2

kubectl run -n network-test-1 nginx --image=nginx
kubectl run -n network-test-1 busybox --image=busybox -- sleep 3600
kubectl run -n network-test-2 busybox --image=busybox -- sleep 3600

# Get pod IPs
kubectl get pods -n network-test-1 -o wide
kubectl get pods -n network-test-2 -o wide

# Test connectivity from one pod to another
kubectl exec -n network-test-1 busybox -- ping -c 4 <nginx-pod-ip>
kubectl exec -n network-test-2 busybox -- ping -c 4 <nginx-pod-ip>

# 4. Test service resolution
# Create a service
kubectl expose -n network-test-1 pod nginx --port=80

# Test DNS resolution from pods
kubectl exec -n network-test-1 busybox -- nslookup nginx.network-test-1.svc.cluster.local
kubectl exec -n network-test-2 busybox -- nslookup nginx.network-test-1.svc.cluster.local

# Test connecting to the service
kubectl exec -n network-test-1 busybox -- wget -O- nginx.network-test-1.svc.cluster.local
kubectl exec -n network-test-2 busybox -- wget -O- nginx.network-test-1.svc.cluster.local

# Clean up
kubectl delete namespace network-test-1
kubectl delete namespace network-test-2
```

---

## Workloads, Services & Networking

### Kubernetes Deployments

Deployments are one of the most common Kubernetes resources, providing declarative updates for Pods and ReplicaSets. They represent a set of identical Pods, and the Deployment controller ensures that the actual state matches the desired state at a controlled rate. This makes Deployments ideal for stateless applications.

Key features of Deployments include:

- **Scaling**: Easily scale the number of replicas up or down
- **Rolling Updates**: Update containers within Pods with minimal downtime
- **Rollbacks**: Quickly revert to previous versions if issues arise
- **Pause/Resume**: Temporarily pause rollouts to apply multiple changes at once
- **Deployment Strategies**: Control how updates happen (e.g., RollingUpdate or Recreate)

The Deployment controller continuously monitors the health of Pods and replaces any that fail, ensuring high availability of your applications.

---

### StatefulSets

StatefulSets are specialized workload controllers designed for applications that require one or more of the following:

- Stable, unique network identifiers
- Stable, persistent storage
- Ordered, graceful deployment and scaling
- Ordered, automated rolling updates

Unlike Deployments, StatefulSets maintain a sticky identity for each Pod. These Pods are created from the same specification but are not interchangeable—each has a persistent identifier that it maintains across any rescheduling.

StatefulSets are valuable for applications that require:
- Stable, persistent storage
- Ordered, graceful deployment and scaling
- Ordered, automated rolling updates
- Stable network identifiers

Examples include databases (MySQL, PostgreSQL), distributed systems (Kafka, ZooKeeper), and other stateful applications.

---

### DaemonSets

DaemonSets ensure that all (or some) nodes run a copy of a Pod. As nodes are added to the cluster, Pods are added to them. As nodes are removed from the cluster, those Pods are garbage collected.

Use cases for DaemonSets include:
- Running a cluster storage daemon on every node
- Running a logs collection daemon on every node
- Running a node monitoring daemon on every node

DaemonSets are perfect for node-level operations, monitoring, and infrastructure components that need to run on each node.

---

### Jobs and CronJobs

Jobs create one or more Pods and ensure that a specified number of them successfully terminate. Jobs track the successful completions of Pods, and when a specified number of successful completions is reached, the Job is complete.

CronJobs build on Jobs, allowing you to run Jobs on a time-based schedule. They are useful for creating periodic and recurring tasks, like running backups, generating reports, or sending emails.

Key aspects of Jobs and CronJobs:
- **Jobs**: Run-to-completion workloads
- **Parallelism**: Control how many Pods run simultaneously
- **Completions**: Specify how many successful Pod completions are needed
- **CronJobs**: Schedule Jobs to run at specific times using cron syntax
- **Concurrency Policy**: Control how to handle concurrent executions

---

### ConfigMaps and Secrets

ConfigMaps and Secrets are resources for decoupling configuration from container images, allowing for greater portability.

**ConfigMaps** provide a way to inject configuration data into Pods. The data stored in a ConfigMap can be referenced in a volume of type `configMap` and then consumed by containerized applications running in a Pod, or provided as environment variables.

**Secrets** are similar to ConfigMaps but are specifically intended for confidential data such as passwords, OAuth tokens, or SSH keys. Kubernetes Secrets are, by default, stored as unencrypted base64-encoded strings in etcd. For improved security, consider using:
- Encryption at rest for Secrets
- Third-party secret management systems integrated with Kubernetes

ConfigMaps and Secrets can be mounted as:
- Environment variables
- Command-line arguments
- Files in a volume

---

### Pod Scheduling

Pod scheduling in Kubernetes determines where Pods are placed within the cluster. Key concepts include:

**Node Affinity/Anti-Affinity**: Constrain which nodes your Pod can be scheduled on based on node labels.
- `requiredDuringSchedulingIgnoredDuringExecution`: Hard requirement that must be met
- `preferredDuringSchedulingIgnoredDuringExecution`: Soft preference that the scheduler will try to enforce

**Pod Affinity/Anti-Affinity**: Control how Pods are scheduled relative to other Pods.
- Specify that Pods should run on the same node as other Pods
- Ensure Pods don't run on the same node as other Pods

**Taints and Tolerations**: Taints are applied to nodes, allowing them to repel certain Pods. Tolerations are applied to Pods, allowing them to schedule onto nodes with matching taints.

**Node Selectors**: A simple, straightforward way to constrain Pods to nodes with specific labels.

**Resource Limits and Requests**:
- **Requests**: The amount of resources guaranteed to the container
- **Limits**: The maximum amount of resources the container can use

---

### Pod Networking Model

The Kubernetes networking model requires:
- Every Pod gets its own unique IP address
- Pods on a node can communicate with all Pods on all nodes without NAT
- Agents on a node can communicate with all Pods on that node

This model is implemented through Container Network Interface (CNI) plugins like Calico, Flannel, Cilium, and others.

---

### Service Types

Services in Kubernetes are an abstraction that defines a logical set of Pods and a policy to access them. They enable loose coupling between dependent Pods.

There are four types of Services:

1. **ClusterIP**: Exposes the Service on a cluster-internal IP. This makes the Service only reachable from within the cluster.

2. **NodePort**: Exposes the Service on each Node's IP at a static port (the NodePort). A ClusterIP Service, to which the NodePort Service routes, is automatically created.

3. **LoadBalancer**: Exposes the Service externally using a cloud provider's load balancer. NodePort and ClusterIP Services, to which the external load balancer routes, are automatically created.

4. **ExternalName**: Maps the Service to the contents of the externalName field (e.g., foo.bar.example.com), by returning a CNAME record with its value. No proxying of any kind is set up.

---

### Endpoints

Endpoints track the IP addresses of Pods that match a Service's selector. They are automatically created and updated by Kubernetes whenever Pods that match the Service's selector come online or go offline.

Endpoints are especially useful for integrating external services. By manually creating Endpoint objects (instead of relying on selectors), you can point a Service to specific IP addresses outside your cluster.

---

### Network Policies

Network Policies are specifications of how groups of Pods are allowed to communicate with each other and other network endpoints. They use labels to select Pods and define rules which specify what traffic is allowed to and from the selected Pods.

Key aspects of Network Policies:
- **Pod Selectors**: Define which Pods the policy applies to
- **Ingress Rules**: Define allowed incoming traffic
- **Egress Rules**: Define allowed outgoing traffic
- **CIDR Blocks**: Specify IP ranges for rules
- **Port Specifications**: Restrict traffic to specific ports

Note that to enforce Network Policies, you need a networking solution that supports them. Not all CNI plugins do—Calico, Cilium, and some others have good Network Policy support.

---

### Gateway API

The Gateway API is a newer, more expressive API for Kubernetes networking, offering significant improvements over Ingress. It provides a more flexible and extensible model for exposing services outside the cluster.

Key components of the Gateway API include:
- **GatewayClass**: Defines a type of Gateway with a specific implementation
- **Gateway**: Represents an instance that can be configured to manage network traffic
- **HTTPRoute, TCPRoute, etc.**: Define how traffic should be routed to Services within the cluster
- **ReferenceGrant**: Allows cross-namespace references, enhancing security

The Gateway API is designed to support various layer 7 protocols, not just HTTP, and provides better support for multi-team environments through clear role separation.

---

### Ingress Controllers and Resources

Ingress exposes HTTP and HTTPS routes from outside the cluster to services within the cluster. Traffic routing is controlled by rules defined on the Ingress resource.

An Ingress controller is responsible for fulfilling the Ingress, usually with a load balancer. Various Ingress controllers are available, including:
- NGINX Ingress Controller
- HAProxy Ingress
- Traefik
- Kong
- Istio

Ingress resources define rules for routing external HTTP/HTTPS traffic to internal services, including:
- Host-based routing (e.g., foo.bar.com -> service1)
- Path-based routing (e.g., foo.bar.com/path1 -> service1, foo.bar.com/path2 -> service2)
- TLS termination

---

### CoreDNS

CoreDNS is the DNS server used within Kubernetes clusters. It provides:
- Service discovery for cluster services
- Pod DNS resolution
- External DNS name resolution
- DNS-based service discovery for services

CoreDNS is configured through a Corefile, which defines how DNS requests are processed. It supports various plugins for different functionality, including:
- Kubernetes plugin for service discovery
- Forward plugin for external name resolution
- Rewrite plugin for modifying queries
- Cache plugin for caching responses

Understanding how CoreDNS works is essential for troubleshooting networking issues in Kubernetes, especially those related to service discovery.

---

### Lab 1: Working with Deployments, ConfigMaps, and Secrets

#### Objective
Create, configure, and manage Deployments with ConfigMaps and Secrets for application configuration.

#### Prerequisites
- Running Kubernetes cluster
- kubectl configured to access your cluster

#### Step 1: Create a ConfigMap for application configuration

```bash
# Create a directory for our exercise files
mkdir -p ~/k8s-labs/configmaps-secrets

# Create a ConfigMap from literal values
cat > ~/k8s-labs/configmaps-secrets/app-config.yaml << EOF
apiVersion: v1
kind: ConfigMap
metadata:
  name: webapp-config
  namespace: default
data:
  DB_HOST: "mysql-service"
  DB_PORT: "3306"
  APP_COLOR: "blue"
  APP_MODE: "production"
  CACHE_ENABLED: "true"
EOF

# Apply the ConfigMap
kubectl apply -f ~/k8s-labs/configmaps-secrets/app-config.yaml

# Verify the ConfigMap
kubectl get configmap webapp-config
kubectl describe configmap webapp-config
```

#### Step 2: Create a Secret for sensitive data

```bash
# Create a Secret for database credentials
cat > ~/k8s-labs/configmaps-secrets/app-secret.yaml << EOF
apiVersion: v1
kind: Secret
metadata:
  name: webapp-secret
  namespace: default
type: Opaque
data:
  DB_USER: $(echo -n "admin" | base64)
  DB_PASSWORD: $(echo -n "password123" | base64)
  API_KEY: $(echo -n "c2VjcmV0LWFwaS1rZXktMTIzNDU2Nzg5MA==" | base64)
EOF

# Apply the Secret
kubectl apply -f ~/k8s-labs/configmaps-secrets/app-secret.yaml

# Verify the Secret
kubectl get secret webapp-secret
kubectl describe secret webapp-secret
```

#### Step 3: Create a Deployment using ConfigMap and Secret

```bash
# Create a Deployment that uses ConfigMap and Secret
cat > ~/k8s-labs/configmaps-secrets/webapp-deployment.yaml << EOF
apiVersion: apps/v1
kind: Deployment
metadata:
  name: webapp
  namespace: default
spec:
  replicas: 3
  selector:
    matchLabels:
      app: webapp
  template:
    metadata:
      labels:
        app: webapp
    spec:
      containers:
      - name: webapp
        image: nginx:1.21
        ports:
        - containerPort: 80
        envFrom:
        - configMapRef:
            name: webapp-config
        - secretRef:
            name: webapp-secret
        volumeMounts:
        - name: config-volume
          mountPath: /etc/config
        - name: secret-volume
          mountPath: /etc/secret
          readOnly: true
      volumes:
      - name: config-volume
        configMap:
          name: webapp-config
      - name: secret-volume
        secret:
          secretName: webapp-secret
EOF

# Apply the Deployment
kubectl apply -f ~/k8s-labs/configmaps-secrets/webapp-deployment.yaml

# Verify the Deployment
kubectl get deployments
kubectl get pods -l app=webapp
```

#### Step 4: Verify configuration in Pods

```bash
# Get one of the Pod names
POD_NAME=$(kubectl get pods -l app=webapp -o jsonpath='{.items[0].metadata.name}')

# Verify ConfigMap values as environment variables
kubectl exec $POD_NAME -- env | grep -E 'DB_HOST|APP_COLOR'

# Verify ConfigMap values as mounted files
kubectl exec $POD_NAME -- ls -la /etc/config
kubectl exec $POD_NAME -- cat /etc/config/APP_COLOR

# Verify Secret values as environment variables (they will be decoded)
kubectl exec $POD_NAME -- env | grep -E 'DB_USER|DB_PASSWORD'

# Verify Secret values as mounted files
kubectl exec $POD_NAME -- ls -la /etc/secret
kubectl exec $POD_NAME -- cat /etc/secret/DB_USER
```

#### Step 5: Update ConfigMap and observe changes

```bash
# Update the ConfigMap
kubectl edit configmap webapp-config

# Change APP_COLOR from "blue" to "green"
# Save and exit

# Wait a moment for the changes to propagate to the mounted files
sleep 10

# Check if the mounted file was updated
kubectl exec $POD_NAME -- cat /etc/config/APP_COLOR

# Note: Environment variables from ConfigMaps don't update automatically
# You need to restart the Pod to pick up changes
kubectl exec $POD_NAME -- env | grep APP_COLOR

# Restart the deployment to pick up environment variable changes
kubectl rollout restart deployment webapp

# Wait for the rollout to complete
kubectl rollout status deployment webapp

# Get a new Pod name
POD_NAME=$(kubectl get pods -l app=webapp -o jsonpath='{.items[0].metadata.name}')

# Verify the updated environment variable
kubectl exec $POD_NAME -- env | grep APP_COLOR
```

#### Step 6: Perform a rolling update

```bash
# Update the Deployment image
kubectl set image deployment/webapp webapp=nginx:1.22 --record

# Watch the rolling update
kubectl rollout status deployment webapp

# View the rollout history
kubectl rollout history deployment webapp

# Verify the updated image version
kubectl describe deployment webapp | grep Image

# Roll back to the previous version
kubectl rollout undo deployment webapp

# Verify the rollback
kubectl rollout status deployment webapp
kubectl describe deployment webapp | grep Image
```

#### Step 7: Clean up resources

```bash
# Delete the resources we created
kubectl delete deployment webapp
kubectl delete configmap webapp-config
kubectl delete secret webapp-secret
```

---

### Lab 2: Working with Services, NetworkPolicies, and DNS

#### Objective
Configure Services for Pod discovery, implement NetworkPolicies, and understand DNS resolution in Kubernetes.

#### Prerequisites
- Running Kubernetes cluster with NetworkPolicy support
- kubectl configured to access your cluster

#### Step 1: Create namespaces for network isolation

```bash
# Create namespaces for our networking lab
kubectl create namespace frontend
kubectl create namespace backend
kubectl create namespace restricted

# Label the namespaces for better visibility
kubectl label namespace frontend purpose=networking-lab tier=frontend
kubectl label namespace backend purpose=networking-lab tier=backend
kubectl label namespace restricted purpose=networking-lab tier=restricted
```

#### Step 2: Deploy applications in different namespaces

```bash
# Create a backend API deployment and service
cat > ~/k8s-labs/networking/backend-deployment.yaml << EOF
apiVersion: apps/v1
kind: Deployment
metadata:
  name: api
  namespace: backend
spec:
  replicas: 2
  selector:
    matchLabels:
      app: api
  template:
    metadata:
      labels:
        app: api
    spec:
      containers:
      - name: api
        image: nginx:1.21
        ports:
        - containerPort: 80
        volumeMounts:
        - name: html
          mountPath: /usr/share/nginx/html
      initContainers:
      - name: init-html
        image: busybox
        command: ['/bin/sh', '-c', 'echo "<h1>Backend API</h1>" > /html/index.html']
        volumeMounts:
        - name: html
          mountPath: /html
      volumes:
      - name: html
        emptyDir: {}
---
apiVersion: v1
kind: Service
metadata:
  name: api-service
  namespace: backend
spec:
  selector:
    app: api
  ports:
  - port: 80
    targetPort: 80
  type: ClusterIP
EOF

kubectl apply -f ~/k8s-labs/networking/backend-deployment.yaml

# Create a frontend web deployment and service
cat > ~/k8s-labs/networking/frontend-deployment.yaml << EOF
apiVersion: apps/v1
kind: Deployment
metadata:
  name: web
  namespace: frontend
spec:
  replicas: 2
  selector:
    matchLabels:
      app: web
  template:
    metadata:
      labels:
        app: web
    spec:
      containers:
      - name: web
        image: nginx:1.21
        ports:
        - containerPort: 80
        volumeMounts:
        - name: html
          mountPath: /usr/share/nginx/html
      initContainers:
      - name: init-html
        image: busybox
        command: ['/bin/sh', '-c', 'echo "<h1>Frontend Web</h1>" > /html/index.html']
        volumeMounts:
        - name: html
          mountPath: /html
      volumes:
      - name: html
        emptyDir: {}
---
apiVersion: v1
kind: Service
metadata:
  name: web-service
  namespace: frontend
spec:
  selector:
    app: web
  ports:
  - port: 80
    targetPort: 80
  type: ClusterIP
EOF

kubectl apply -f ~/k8s-labs/networking/frontend-deployment.yaml

# Create a restricted deployment for testing network policies
cat > ~/k8s-labs/networking/restricted-deployment.yaml << EOF
apiVersion: apps/v1
kind: Deployment
metadata:
  name: tester
  namespace: restricted
spec:
  replicas: 1
  selector:
    matchLabels:
      app: tester
  template:
    metadata:
      labels:
        app: tester
    spec:
      containers:
      - name: tester
        image: busybox
        command: ['sh', '-c', 'while true; do sleep 3600; done']
EOF

kubectl apply -f ~/k8s-labs/networking/restricted-deployment.yaml
```

#### Step 3: Test basic connectivity between namespaces

```bash
# Get Pod names
FRONTEND_POD=$(kubectl get pods -n frontend -l app=web -o jsonpath='{.items[0].metadata.name}')
BACKEND_POD=$(kubectl get pods -n backend -l app=api -o jsonpath='{.items[0].metadata.name}')
RESTRICTED_POD=$(kubectl get pods -n restricted -l app=tester -o jsonpath='{.items[0].metadata.name}')

# Test frontend to backend connectivity (should work)
kubectl exec -n frontend $FRONTEND_POD -- curl -s api-service.backend.svc.cluster.local

# Test backend to frontend connectivity (should work)
kubectl exec -n backend $BACKEND_POD -- curl -s web-service.frontend.svc.cluster.local

# Test restricted to backend connectivity (should work)
kubectl exec -n restricted $RESTRICTED_POD -- wget -qO- api-service.backend.svc.cluster.local

# Test restricted to frontend connectivity (should work)
kubectl exec -n restricted $RESTRICTED_POD -- wget -qO- web-service.frontend.svc.cluster.local
```

#### Step 4: Create NetworkPolicies for isolation

```bash
# Create default deny policy for the backend namespace
cat > ~/k8s-labs/networking/backend-default-deny.yaml << EOF
apiVersion: networking.k8s.io/v1
kind: NetworkPolicy
metadata:
  name: default-deny
  namespace: backend
spec:
  podSelector: {}
  policyTypes:
  - Ingress
  - Egress
EOF

kubectl apply -f ~/k8s-labs/networking/backend-default-deny.yaml

# Test connectivity again (should fail)
kubectl exec -n frontend $FRONTEND_POD -- curl -s --connect-timeout 5 api-service.backend.svc.cluster.local
kubectl exec -n restricted $RESTRICTED_POD -- wget -qO- --timeout=5 api-service.backend.svc.cluster.local

# Create a NetworkPolicy to allow frontend to backend traffic
cat > ~/k8s-labs/networking/backend-allow-frontend.yaml << EOF
apiVersion: networking.k8s.io/v1
kind: NetworkPolicy
metadata:
  name: allow-frontend
  namespace: backend
spec:
  podSelector:
    matchLabels:
      app: api
  policyTypes:
  - Ingress
  ingress:
  - from:
    - namespaceSelector:
        matchLabels:
          tier: frontend
      podSelector:
        matchLabels:
          app: web
    ports:
    - protocol: TCP
      port: 80
EOF

kubectl apply -f ~/k8s-labs/networking/backend-allow-frontend.yaml

# Create a NetworkPolicy to allow outbound DNS
cat > ~/k8s-labs/networking/backend-allow-dns.yaml << EOF
apiVersion: networking.k8s.io/v1
kind: NetworkPolicy
metadata:
  name: allow-dns
  namespace: backend
spec:
  podSelector: {}
  policyTypes:
  - Egress
  egress:
  - to:
    - namespaceSelector:
        matchLabels:
          kubernetes.io/metadata.name: kube-system
      podSelector:
        matchLabels:
          k8s-app: kube-dns
    ports:
    - protocol: UDP
      port: 53
    - protocol: TCP
      port: 53
EOF

kubectl apply -f ~/k8s-labs/networking/backend-allow-dns.yaml
```

#### Step 5: Test NetworkPolicy implementation

```bash
# Test frontend to backend connectivity (should work)
kubectl exec -n frontend $FRONTEND_POD -- curl -s api-service.backend.svc.cluster.local

# Test restricted to backend connectivity (should still fail)
kubectl exec -n restricted $RESTRICTED_POD -- wget -qO- --timeout=5 api-service.backend.svc.cluster.local || echo "Connection timed out as expected"

# Test backend Pod's ability to resolve DNS
kubectl exec -n backend $BACKEND_POD -- nslookup kubernetes.default.svc.cluster.local
```

#### Step 6: Explore and test DNS resolution

```bash
# Create a temporary debugging Pod to explore DNS
kubectl run dns-test --image=busybox -n default -- sleep 3600

# Wait for the Pod to be running
kubectl wait --for=condition=Ready pod/dns-test -n default

# Test DNS resolution for services
kubectl exec -it dns-test -- nslookup kubernetes.default.svc.cluster.local
kubectl exec -it dns-test -- nslookup api-service.backend.svc.cluster.local
kubectl exec -it dns-test -- nslookup web-service.frontend.svc.cluster.local

# Check DNS configuration
kubectl exec -it dns-test -- cat /etc/resolv.conf

# Test Pod DNS (if enabled in your cluster)
BACKEND_POD_IP=$(kubectl get pod $BACKEND_POD -n backend -o jsonpath='{.status.podIP}')
kubectl exec -it dns-test -- nslookup $BACKEND_POD_IP.backend.pod.cluster.local

# Delete the debugging Pod
kubectl delete pod dns-test -n default
```

#### Step 7: Create NodePort and LoadBalancer Services

```bash
# Create a NodePort service for frontend
cat > ~/k8s-labs/networking/frontend-nodeport.yaml << EOF
apiVersion: v1
kind: Service
metadata:
  name: web-nodeport
  namespace: frontend
spec:
  selector:
    app: web
  ports:
  - port: 80
    targetPort: 80
    nodePort: 30080
  type: NodePort
EOF

kubectl apply -f ~/k8s-labs/networking/frontend-nodeport.yaml

# Check the NodePort service
kubectl get service web-nodeport -n frontend

# If in a cloud environment, create a LoadBalancer service
# (Skip this step if not in a cloud environment)
cat > ~/k8s-labs/networking/frontend-loadbalancer.yaml << EOF
apiVersion: v1
kind: Service
metadata:
  name: web-lb
  namespace: frontend
spec:
  selector:
    app: web
  ports:
  - port: 80
    targetPort: 80
  type: LoadBalancer
EOF

kubectl apply -f ~/k8s-labs/networking/frontend-loadbalancer.yaml

# Check the LoadBalancer service
kubectl get service web-lb -n frontend -w
```

---

### Lab 3: Working with Ingress Controllers and Gateway API

#### Objective
Install and configure Ingress controllers, create Ingress resources, and explore the Gateway API features.

#### Prerequisites
- Running Kubernetes cluster
- kubectl configured to access your cluster

#### Step 1: Install NGINX Ingress Controller

```bash
# Create a namespace for the ingress controller
kubectl create namespace ingress-nginx

# Install the NGINX Ingress Controller using Helm or Manifests
# Option 1: Using Helm
helm repo add ingress-nginx https://kubernetes.github.io/ingress-nginx
helm repo update
helm install ingress-nginx ingress-nginx/ingress-nginx -n ingress-nginx

# Option 2: Using Manifests
kubectl apply -f https://raw.githubusercontent.com/kubernetes/ingress-nginx/controller-v1.8.0/deploy/static/provider/cloud/deploy.yaml

# Wait for the Ingress controller to be ready
kubectl wait --namespace ingress-nginx \
  --for=condition=ready pod \
  --selector=app.kubernetes.io/component=controller \
  --timeout=120s
```

#### Step 2: Create Ingress resources for existing applications

```bash
# Create an Ingress resource for the frontend application
cat > ~/k8s-labs/ingress/frontend-ingress.yaml << EOF
apiVersion: networking.k8s.io/v1
kind: Ingress
metadata:
  name: frontend-ingress
  namespace: frontend
  annotations:
    nginx.ingress.kubernetes.io/rewrite-target: /
spec:
  ingressClassName: nginx
  rules:
  - host: frontend.example.com
    http:
      paths:
      - path: /
        pathType: Prefix
        backend:
          service:
            name: web-service
            port:
              number: 80
EOF

kubectl apply -f ~/k8s-labs/ingress/frontend-ingress.yaml

# Create an Ingress resource for the backend application
cat > ~/k8s-labs/ingress/backend-ingress.yaml << EOF
apiVersion: networking.k8s.io/v1
kind: Ingress
metadata:
  name: backend-ingress
  namespace: backend
  annotations:
    nginx.ingress.kubernetes.io/rewrite-target: /
spec:
  ingressClassName: nginx
  rules:
  - host: api.example.com
    http:
      paths:
      - path: /
        pathType: Prefix
        backend:
          service:
            name: api-service
            port:
              number: 80
EOF

kubectl apply -f ~/k8s-labs/ingress/backend-ingress.yaml
```

#### Step 3: Test Ingress resources

```bash
# Get the Ingress controller's external IP or hostname
INGRESS_HOST=$(kubectl get svc -n ingress-nginx ingress-nginx-controller -o jsonpath='{.status.loadBalancer.ingress[0].ip}')
# If the above command doesn't work, try this one (for hostname-based load balancers)
if [ -z "$INGRESS_HOST" ]; then
  INGRESS_HOST=$(kubectl get svc -n ingress-nginx ingress-nginx-controller -o jsonpath='{.status.loadBalancer.ingress[0].hostname}')
fi

# If running locally or on minikube, you may need to use the NodePort
if [ -z "$INGRESS_HOST" ]; then
  INGRESS_HOST=$(kubectl get nodes -o jsonpath='{.items[0].status.addresses[0].address}')
  INGRESS_PORT=$(kubectl get svc -n ingress-nginx ingress-nginx-controller -o jsonpath='{.spec.ports[0].nodePort}')
fi

# Test the Ingress for frontend
curl -H "Host: frontend.example.com" http://$INGRESS_HOST

# Test the Ingress for backend
curl -H "Host: api.example.com" http://$INGRESS_HOST
```

#### Step 4: Configure TLS for Ingress (self-signed certificate for testing)

```bash
# Generate a self-signed certificate
mkdir -p ~/k8s-labs/ingress/certs
openssl req -x509 -nodes -days 365 -newkey rsa:2048 \
  -keyout ~/k8s-labs/ingress/certs/tls.key \
  -out ~/k8s-labs/ingress/certs/tls.crt \
  -subj "/CN=*.example.com"

# Create TLS Secret for frontend
kubectl create secret tls frontend-tls \
  --key ~/k8s-labs/ingress/certs/tls.key \
  --cert ~/k8s-labs/ingress/certs/tls.crt \
  -n frontend

# Create TLS Secret for backend
kubectl create secret tls backend-tls \
  --key ~/k8s-labs/ingress/certs/tls.key \
  --cert ~/k8s-labs/ingress/certs/tls.crt \
  -n backend

# Update the Ingress resources to use TLS
cat > ~/k8s-labs/ingress/frontend-ingress-tls.yaml << EOF
apiVersion: networking.k8s.io/v1
kind: Ingress
metadata:
  name: frontend-ingress
  namespace: frontend
  annotations:
    nginx.ingress.kubernetes.io/rewrite-target: /
spec:
  ingressClassName: nginx
  tls:
  - hosts:
    - frontend.example.com
    secretName: frontend-tls
  rules:
  - host: frontend.example.com
    http:
      paths:
      - path: /
        pathType: Prefix
        backend:
          service:
            name: web-service
            port:
              number: 80
EOF

kubectl apply -f ~/k8s-labs/ingress/frontend-ingress-tls.yaml

cat > ~/k8s-labs/ingress/backend-ingress-tls.yaml << EOF
apiVersion: networking.k8s.io/v1
kind: Ingress
metadata:
  name: backend-ingress
  namespace: backend
  annotations:
    nginx.ingress.kubernetes.io/rewrite-target: /
spec:
  ingressClassName: nginx
  tls:
  - hosts:
    - api.example.com
    secretName: backend-tls
  rules:
  - host: api.example.com
    http:
      paths:
      - path: /
        pathType: Prefix
        backend:
          service:
            name: api-service
            port:
              number: 80
EOF

kubectl apply -f ~/k8s-labs/ingress/backend-ingress-tls.yaml
```

#### Step 5: Explore Gateway API (if available in your cluster)

```bash
# Check if Gateway API CRDs are installed
kubectl get crd gateways.gateway.networking.k8s.io &> /dev/null
if [ $? -ne 0 ]; then
  echo "Gateway API CRDs not found. Installing..."
  
  # Install Gateway API CRDs
  kubectl apply -f https://github.com/kubernetes-sigs/gateway-api/releases/download/v0.6.2/standard-install.yaml
  
  # Wait for CRDs to be established
  kubectl wait --for=condition=established crd/gateways.gateway.networking.k8s.io --timeout=60s
  kubectl wait --for=condition=established crd/httproutes.gateway.networking.k8s.io --timeout=60s
fi

# Create a GatewayClass
cat > ~/k8s-labs/gateway-api/gateway-class.yaml << EOF
apiVersion: gateway.networking.k8s.io/v1beta1
kind: GatewayClass
metadata:
  name: example-gateway-class
spec:
  controllerName: example.com/gateway-controller
EOF

kubectl apply -f ~/k8s-labs/gateway-api/gateway-class.yaml

# Create a Gateway
cat > ~/k8s-labs/gateway-api/gateway.yaml << EOF
apiVersion: gateway.networking.k8s.io/v1beta1
kind: Gateway
metadata:
  name: example-gateway
  namespace: default
spec:
  gatewayClassName: example-gateway-class
  listeners:
  - name: http
    protocol: HTTP
    port: 80
    allowedRoutes:
      namespaces:
        from: All
EOF

kubectl apply -f ~/k8s-labs/gateway-api/gateway.yaml

# Create HTTPRoute resources for our services
cat > ~/k8s-labs/gateway-api/frontend-route.yaml << EOF
apiVersion: gateway.networking.k8s.io/v1beta1
kind: HTTPRoute
metadata:
  name: frontend-route
  namespace: frontend
spec:
  parentRefs:
  - name: example-gateway
    namespace: default
  hostnames:
  - "frontend.example.com"
  rules:
  - matches:
    - path:
        type: PathPrefix
        value: /
    backendRefs:
    - name: web-service
      port: 80
EOF

kubectl apply -f ~/k8s-labs/gateway-api/frontend-route.yaml

cat > ~/k8s-labs/gateway-api/backend-route.yaml << EOF
apiVersion: gateway.networking.k8s.io/v1beta1
kind: HTTPRoute
metadata:
  name: backend-route
  namespace: backend
spec:
  parentRefs:
  - name: example-gateway
    namespace: default
  hostnames:
  - "api.example.com"
  rules:
  - matches:
    - path:
        type: PathPrefix
        value: /
    backendRefs:
    - name: api-service
      port: 80
EOF

kubectl apply -f ~/k8s-labs/gateway-api/backend-route.yaml

# Note: To actually use these Gateway API resources, you need a gateway controller
# that implements the Gateway API (e.g., Contour, Istio, etc.)
```

#### Step 6: Clean up resources

```bash
# Delete Gateway API resources (if created)
kubectl delete httproute frontend-route -n frontend --ignore-not-found
kubectl delete httproute backend-route -n backend --ignore-not-found
kubectl delete gateway example-gateway -n default --ignore-not-found
kubectl delete gatewayclass example-gateway-class --ignore-not-found

# Delete Ingress resources
kubectl delete ingress frontend-ingress -n frontend --ignore-not-found
kubectl delete ingress backend-ingress -n backend --ignore-not-found
kubectl delete secret frontend-tls -n frontend --ignore-not-found
kubectl delete secret backend-tls -n backend --ignore-not-found

# Delete the NGINX Ingress Controller
helm uninstall ingress-nginx -n ingress-nginx --ignore-not-found
# Or if installed via manifests:
# kubectl delete -f https://raw.githubusercontent.com/kubernetes/ingress-nginx/controller-v1.8.0/deploy/static/provider/cloud/deploy.yaml

# Delete namespace
kubectl delete namespace ingress-nginx --ignore-not-found

# Delete deployments and services
kubectl delete -f ~/k8s-labs/networking/frontend-deployment.yaml --ignore-not-found
kubectl delete -f ~/k8s-labs/networking/backend-deployment.yaml --ignore-not-found
kubectl delete -f ~/k8s-labs/networking/restricted-deployment.yaml --ignore-not-found
kubectl delete -f ~/k8s-labs/networking/frontend-nodeport.yaml --ignore-not-found
kubectl delete -f ~/k8s-labs/networking/frontend-loadbalancer.yaml --ignore-not-found

# Delete NetworkPolicies
kubectl delete -f ~/k8s-labs/networking/backend-default-deny.yaml --ignore-not-found
kubectl delete -f ~/k8s-labs/networking/backend-allow-frontend.yaml --ignore-not-found
kubectl delete -f ~/k8s-labs/networking/backend-allow-dns.yaml --ignore-not-found

# Delete namespaces
kubectl delete namespace frontend --ignore-not-found
kubectl delete namespace backend --ignore-not-found
kubectl delete namespace restricted --ignore-not-found
```

---


### Practice Exercises

The following exercises build upon our lab work to cover additional workload and networking scenarios that commonly appear in the CKA exam.

#### Exercise 1: Working with StatefulSets and Headless Services

##### Scenario
You need to deploy a stateful application that requires stable network identities and persistent storage. The pods must maintain their identity across rescheduling and restarts.

##### Tasks
1. Create a headless service for stable network identities
2. Deploy a StatefulSet with 3 replicas
3. Verify the identity persistence of the pods
4. Scale the StatefulSet and observe the naming convention
5. Delete a pod and verify that its identity is preserved when recreated

##### Steps
```bash
# Create a namespace for our StatefulSet exercise
kubectl create namespace stateful-demo

# Create a headless service (service with no cluster IP)
cat > ~/k8s-practice/statefulset/headless-service.yaml << EOF
apiVersion: v1
kind: Service
metadata:
  name: nginx-headless
  namespace: stateful-demo
spec:
  selector:
    app: nginx-stateful
  ports:
  - port: 80
    name: web
  clusterIP: None  # This makes it a headless service
EOF

kubectl apply -f ~/k8s-practice/statefulset/headless-service.yaml

# Create a StatefulSet with 3 replicas
cat > ~/k8s-practice/statefulset/nginx-statefulset.yaml << EOF
apiVersion: apps/v1
kind: StatefulSet
metadata:
  name: web
  namespace: stateful-demo
spec:
  serviceName: "nginx-headless"
  replicas: 3
  selector:
    matchLabels:
      app: nginx-stateful
  template:
    metadata:
      labels:
        app: nginx-stateful
    spec:
      containers:
      - name: nginx
        image: nginx:1.21
        ports:
        - containerPort: 80
          name: web
        volumeMounts:
        - name: data
          mountPath: /usr/share/nginx/html
  volumeClaimTemplates:
  - metadata:
      name: data
    spec:
      accessModes: [ "ReadWriteOnce" ]
      resources:
        requests:
          storage: 1Gi
EOF

kubectl apply -f ~/k8s-practice/statefulset/nginx-statefulset.yaml

# Wait for all pods to be created
kubectl rollout status statefulset/web -n stateful-demo

# Verify pod creation and naming convention
kubectl get pods -n stateful-demo

# Check the DNS names of the pods
kubectl run -n stateful-demo dns-test --image=busybox --restart=Never -- sleep 3600
kubectl wait --for=condition=Ready pod/dns-test -n stateful-demo
kubectl exec -n stateful-demo dns-test -- nslookup web-0.nginx-headless.stateful-demo.svc.cluster.local
kubectl exec -n stateful-demo dns-test -- nslookup web-1.nginx-headless.stateful-demo.svc.cluster.local
kubectl exec -n stateful-demo dns-test -- nslookup web-2.nginx-headless.stateful-demo.svc.cluster.local

# Scale the StatefulSet to 5 replicas
kubectl scale statefulset web -n stateful-demo --replicas=5

# Verify the new pods follow the naming convention
kubectl get pods -n stateful-demo -w
# (Press Ctrl+C to exit the watch when all pods are ready)

# Delete one pod and observe it being recreated with the same name
kubectl delete pod web-2 -n stateful-demo
kubectl get pods -n stateful-demo -w
# (Press Ctrl+C to exit the watch when all pods are ready)

# Check that the PVCs are preserved
kubectl get pvc -n stateful-demo

# Clean up
kubectl delete statefulset web -n stateful-demo
kubectl delete service nginx-headless -n stateful-demo
kubectl delete pod dns-test -n stateful-demo
kubectl delete pvc --all -n stateful-demo
kubectl delete namespace stateful-demo
```

---

#### Exercise 2: DaemonSets and Node Affinity

##### Scenario
You need to deploy a monitoring agent that must run on all nodes in your cluster. Additionally, you want to deploy a specialized logging agent that should only run on nodes with an SSD.

##### Tasks
1. Create a DaemonSet that deploys a monitoring agent on all nodes
2. Label some nodes to indicate they have SSDs
3. Create a DaemonSet with node affinity that only runs on nodes with SSDs
4. Verify both DaemonSets are running on the correct nodes

##### Steps
```bash
# Create a namespace for our DaemonSet exercise
kubectl create namespace daemon-demo

# Create a DaemonSet for a monitoring agent
cat > ~/k8s-practice/daemonset/monitoring-agent.yaml << EOF
apiVersion: apps/v1
kind: DaemonSet
metadata:
  name: monitoring-agent
  namespace: daemon-demo
spec:
  selector:
    matchLabels:
      app: monitoring-agent
  template:
    metadata:
      labels:
        app: monitoring-agent
    spec:
      containers:
      - name: agent
        image: busybox
        command: ['sh', '-c', 'while true; do echo "Monitoring node $(hostname)..."; sleep 300; done']
EOF

kubectl apply -f ~/k8s-practice/daemonset/monitoring-agent.yaml

# Verify the monitoring agent is deployed on all nodes
kubectl get pods -n daemon-demo -o wide

# Label some nodes to indicate they have SSDs
# Get a list of nodes and label half of them with disk=ssd
NODE_LIST=$(kubectl get nodes -o jsonpath='{.items[*].metadata.name}')
NODE_ARRAY=($NODE_LIST)
HALF_COUNT=$((${#NODE_ARRAY[@]} / 2))

for ((i=0; i<HALF_COUNT; i++)); do
  kubectl label node ${NODE_ARRAY[$i]} disk=ssd
done

# Verify the labels
kubectl get nodes --show-labels | grep disk=ssd

# Create a DaemonSet for a logging agent that only runs on SSD nodes
cat > ~/k8s-practice/daemonset/logging-agent.yaml << EOF
apiVersion: apps/v1
kind: DaemonSet
metadata:
  name: logging-agent
  namespace: daemon-demo
spec:
  selector:
    matchLabels:
      app: logging-agent
  template:
    metadata:
      labels:
        app: logging-agent
    spec:
      affinity:
        nodeAffinity:
          requiredDuringSchedulingIgnoredDuringExecution:
            nodeSelectorTerms:
            - matchExpressions:
              - key: disk
                operator: In
                values:
                - ssd
      containers:
      - name: agent
        image: busybox
        command: ['sh', '-c', 'while true; do echo "Logging from SSD node $(hostname)..."; sleep 300; done']
EOF

kubectl apply -f ~/k8s-practice/daemonset/logging-agent.yaml

# Verify the logging agent is only deployed on nodes with the SSD label
kubectl get pods -n daemon-demo -l app=logging-agent -o wide

# Clean up
kubectl delete daemonset monitoring-agent logging-agent -n daemon-demo
kubectl delete namespace daemon-demo

# Remove the disk=ssd label from nodes
for ((i=0; i<HALF_COUNT; i++)); do
  kubectl label node ${NODE_ARRAY[$i]} disk-
done
```

---

#### Exercise 3: Multi-Container Pods and Inter-container Communication

##### Scenario
You need to deploy an application that requires a sidecar container for log processing. The main application will write logs to a shared volume, and the sidecar container will process these logs.

##### Tasks
1. Create a Pod with two containers sharing a volume
2. Configure the main container to write logs to the shared volume
3. Configure the sidecar container to process logs from the shared volume
4. Verify logs are being processed correctly

##### Steps
```bash
# Create a namespace for our multi-container exercise
kubectl create namespace multicontainer-demo

# Create a multi-container Pod with a shared volume
cat > ~/k8s-practice/multicontainer/sidecar-pod.yaml << EOF
apiVersion: v1
kind: Pod
metadata:
  name: log-processor
  namespace: multicontainer-demo
spec:
  containers:
  - name: main-app
    image: busybox
    command: ['sh', '-c', 'while true; do echo "$(date): Application log entry $(RANDOM)" >> /var/log/app.log; sleep 5; done']
    volumeMounts:
    - name: log-volume
      mountPath: /var/log
  - name: log-processor
    image: busybox
    command: ['sh', '-c', 'tail -f /var/log/app.log | while read log; do echo "Processed: $log" >> /var/log/processed.log; done']
    volumeMounts:
    - name: log-volume
      mountPath: /var/log
  volumes:
  - name: log-volume
    emptyDir: {}
EOF

kubectl apply -f ~/k8s-practice/multicontainer/sidecar-pod.yaml

# Wait for the Pod to be running
kubectl get pod log-processor -n multicontainer-demo -w
# (Press Ctrl+C to exit the watch when the pod is ready)

# Verify that logs are being generated
kubectl exec -n multicontainer-demo log-processor -c main-app -- cat /var/log/app.log | tail -5

# Verify that logs are being processed
kubectl exec -n multicontainer-demo log-processor -c log-processor -- cat /var/log/processed.log | tail -5

# Check the logs of the sidecar container
kubectl logs -n multicontainer-demo log-processor -c log-processor

# Clean up
kubectl delete pod log-processor -n multicontainer-demo
kubectl delete namespace multicontainer-demo
```

---

#### Exercise 4: Jobs and CronJobs

##### Scenario
You need to create a one-time job that processes data and a recurring job that performs a backup every 5 minutes.

##### Tasks
1. Create a Job that runs a data processing task
2. Configure the Job to handle retries and parallelism
3. Create a CronJob that runs a backup task every 5 minutes
4. Verify the execution of both jobs

##### Steps
```bash
# Create a namespace for our jobs exercise
kubectl create namespace jobs-demo

# Create a Job to process data
cat > ~/k8s-practice/jobs/data-processor.yaml << EOF
apiVersion: batch/v1
kind: Job
metadata:
  name: data-processor
  namespace: jobs-demo
spec:
  completions: 5     # Run 5 successful pod completions
  parallelism: 2     # Run 2 pods in parallel
  backoffLimit: 3    # Retry 3 times before marking job as failed
  template:
    spec:
      containers:
      - name: processor
        image: busybox
        command: ['sh', '-c', 'echo "Processing data chunk $RANDOM..."; sleep 10; echo "Data processing complete"']
      restartPolicy: Never
EOF

kubectl apply -f ~/k8s-practice/jobs/data-processor.yaml

# Watch the job progress
kubectl get jobs -n jobs-demo -w
# (Press Ctrl+C to exit the watch when the job completes)

# View the pods created by the job
kubectl get pods -n jobs-demo

# View the logs from one of the completed pods
POD_NAME=$(kubectl get pods -n jobs-demo -l job-name=data-processor -o jsonpath='{.items[0].metadata.name}')
kubectl logs $POD_NAME -n jobs-demo

# Create a CronJob for periodic backups
cat > ~/k8s-practice/jobs/backup-cronjob.yaml << EOF
apiVersion: batch/v1
kind: CronJob
metadata:
  name: backup-job
  namespace: jobs-demo
spec:
  schedule: "*/5 * * * *"    # Run every 5 minutes
  concurrencyPolicy: Forbid  # Don't allow concurrent executions
  successfulJobsHistoryLimit: 3
  failedJobsHistoryLimit: 1
  jobTemplate:
    spec:
      template:
        spec:
          containers:
          - name: backup
            image: busybox
            command: ['sh', '-c', 'echo "Backup started at $(date)"; sleep 30; echo "Backup completed at $(date)"']
          restartPolicy: OnFailure
EOF

kubectl apply -f ~/k8s-practice/jobs/backup-cronjob.yaml

# Check the CronJob
kubectl get cronjobs -n jobs-demo

# Wait for the first execution (this may take up to 5 minutes)
echo "Waiting for the first CronJob execution..."
sleep 300
kubectl get jobs -n jobs-demo

# View the logs from the CronJob's most recent execution
CRONJOB_POD=$(kubectl get pods -n jobs-demo -l job-name=backup-job-$(date +%s | cut -c 1-10) -o jsonpath='{.items[0].metadata.name}' 2>/dev/null)
if [ -z "$CRONJOB_POD" ]; then
  CRONJOB_POD=$(kubectl get pods -n jobs-demo -o name | grep backup-job | head -1 | sed 's/pod\///')
fi
kubectl logs $CRONJOB_POD -n jobs-demo

# Clean up
kubectl delete job data-processor -n jobs-demo
kubectl delete cronjob backup-job -n jobs-demo
kubectl delete namespace jobs-demo
```

---

#### Exercise 5: Advanced Network Policies and Service Types

##### Scenario
You are securing a multi-tier application with network policies and need to expose different components using various service types.

##### Tasks
1. Create a three-tier application (database, backend API, frontend)
2. Implement Network Policies to restrict traffic between tiers
3. Create different types of Services (ClusterIP, NodePort, ExternalName)
4. Test the connectivity between components

##### Steps
```bash
# Create a namespace for our networking exercise
kubectl create namespace advanced-networking

# Deploy a three-tier application
# 1. Database tier
cat > ~/k8s-practice/networking/database.yaml << EOF
apiVersion: apps/v1
kind: Deployment
metadata:
  name: database
  namespace: advanced-networking
spec:
  replicas: 1
  selector:
    matchLabels:
      app: database
      tier: db
  template:
    metadata:
      labels:
        app: database
        tier: db
    spec:
      containers:
      - name: mysql
        image: mysql:5.7
        env:
        - name: MYSQL_ROOT_PASSWORD
          value: "password"
        - name: MYSQL_DATABASE
          value: "testdb"
        ports:
        - containerPort: 3306
---
apiVersion: v1
kind: Service
metadata:
  name: database-service
  namespace: advanced-networking
spec:
  selector:
    app: database
    tier: db
  ports:
  - port: 3306
    targetPort: 3306
  type: ClusterIP
EOF

kubectl apply -f ~/k8s-practice/networking/database.yaml

# 2. Backend API tier
cat > ~/k8s-practice/networking/backend.yaml << EOF
apiVersion: apps/v1
kind: Deployment
metadata:
  name: backend-api
  namespace: advanced-networking
spec:
  replicas: 2
  selector:
    matchLabels:
      app: backend-api
      tier: backend
  template:
    metadata:
      labels:
        app: backend-api
        tier: backend
    spec:
      containers:
      - name: api
        image: nginx:1.21
        ports:
        - containerPort: 80
---
apiVersion: v1
kind: Service
metadata:
  name: backend-service
  namespace: advanced-networking
spec:
  selector:
    app: backend-api
    tier: backend
  ports:
  - port: 80
    targetPort: 80
  type: ClusterIP
EOF

kubectl apply -f ~/k8s-practice/networking/backend.yaml

# 3. Frontend tier
cat > ~/k8s-practice/networking/frontend.yaml << EOF
apiVersion: apps/v1
kind: Deployment
metadata:
  name: frontend
  namespace: advanced-networking
spec:
  replicas: 3
  selector:
    matchLabels:
      app: frontend
      tier: frontend
  template:
    metadata:
      labels:
        app: frontend
        tier: frontend
    spec:
      containers:
      - name: web
        image: nginx:1.21
        ports:
        - containerPort: 80
---
apiVersion: v1
kind: Service
metadata:
  name: frontend-service
  namespace: advanced-networking
spec:
  selector:
    app: frontend
    tier: frontend
  ports:
  - port: 80
    targetPort: 80
    nodePort: 30080
  type: NodePort
EOF

kubectl apply -f ~/k8s-practice/networking/frontend.yaml

# 4. Create an ExternalName service for an external API
cat > ~/k8s-practice/networking/external-service.yaml << EOF
apiVersion: v1
kind: Service
metadata:
  name: external-api
  namespace: advanced-networking
spec:
  type: ExternalName
  externalName: api.example.com
EOF

kubectl apply -f ~/k8s-practice/networking/external-service.yaml

# Create Network Policies

# 1. Default deny all ingress and egress traffic
cat > ~/k8s-practice/networking/default-deny.yaml << EOF
apiVersion: networking.k8s.io/v1
kind: NetworkPolicy
metadata:
  name: default-deny-all
  namespace: advanced-networking
spec:
  podSelector: {}
  policyTypes:
  - Ingress
  - Egress
EOF

kubectl apply -f ~/k8s-practice/networking/default-deny.yaml

# 2. Allow backend to access database
cat > ~/k8s-practice/networking/backend-to-db.yaml << EOF
apiVersion: networking.k8s.io/v1
kind: NetworkPolicy
metadata:
  name: backend-to-db
  namespace: advanced-networking
spec:
  podSelector:
    matchLabels:
      app: database
      tier: db
  policyTypes:
  - Ingress
  ingress:
  - from:
    - podSelector:
        matchLabels:
          app: backend-api
          tier: backend
    ports:
    - protocol: TCP
      port: 3306
EOF

kubectl apply -f ~/k8s-practice/networking/backend-to-db.yaml

# 3. Allow frontend to access backend
cat > ~/k8s-practice/networking/frontend-to-backend.yaml << EOF
apiVersion: networking.k8s.io/v1
kind: NetworkPolicy
metadata:
  name: frontend-to-backend
  namespace: advanced-networking
spec:
  podSelector:
    matchLabels:
      app: backend-api
      tier: backend
  policyTypes:
  - Ingress
  ingress:
  - from:
    - podSelector:
        matchLabels:
          app: frontend
          tier: frontend
    ports:
    - protocol: TCP
      port: 80
EOF

kubectl apply -f ~/k8s-practice/networking/frontend-to-backend.yaml

# 4. Allow external access to frontend
cat > ~/k8s-practice/networking/external-to-frontend.yaml << EOF
apiVersion: networking.k8s.io/v1
kind: NetworkPolicy
metadata:
  name: external-to-frontend
  namespace: advanced-networking
spec:
  podSelector:
    matchLabels:
      app: frontend
      tier: frontend
  policyTypes:
  - Ingress
  ingress:
  - from: []
    ports:
    - protocol: TCP
      port: 80
EOF

kubectl apply -f ~/k8s-practice/networking/external-to-frontend.yaml

# 5. Allow DNS resolution
cat > ~/k8s-practice/networking/allow-dns.yaml << EOF
apiVersion: networking.k8s.io/v1
kind: NetworkPolicy
metadata:
  name: allow-dns
  namespace: advanced-networking
spec:
  podSelector: {}
  policyTypes:
  - Egress
  egress:
  - to:
    - namespaceSelector:
        matchLabels:
          kubernetes.io/metadata.name: kube-system
    ports:
    - protocol: UDP
      port: 53
    - protocol: TCP
      port: 53
EOF

kubectl apply -f ~/k8s-practice/networking/allow-dns.yaml

# Test connectivity
# Create a debugging pod
kubectl run -n advanced-networking debug-pod --image=nicolaka/netshoot --restart=Never

# Wait for the pod to be ready
kubectl wait --for=condition=Ready pod/debug-pod -n advanced-networking

# Test connectivity from debug pod to database (should fail due to network policy)
kubectl exec -n advanced-networking debug-pod -- curl -s --connect-timeout 5 database-service:3306
# Expected result: Connection times out

# Test connectivity from debug pod to backend (should fail due to network policy)
kubectl exec -n advanced-networking debug-pod -- curl -s --connect-timeout 5 backend-service
# Expected result: Connection times out

# Test connectivity from debug pod to frontend (should fail due to network policy)
kubectl exec -n advanced-networking debug-pod -- curl -s --connect-timeout 5 frontend-service
# Expected result: Connection times out

# Test connectivity from frontend pod to backend (should work)
FRONTEND_POD=$(kubectl get pods -n advanced-networking -l app=frontend -o jsonpath='{.items[0].metadata.name}')
kubectl exec -n advanced-networking $FRONTEND_POD -- curl -s backend-service
# Expected result: Returns the NGINX welcome page

# Test connectivity from backend pod to database (should work but we'll see a MySQL error)
BACKEND_POD=$(kubectl get pods -n advanced-networking -l app=backend-api -o jsonpath='{.items[0].metadata.name}')
kubectl exec -n advanced-networking $BACKEND_POD -- bash -c "apt-get update && apt-get install -y netcat && nc -zv database-service 3306"
# Expected result: Connection succeeds to the MySQL port

# Test ExternalName service resolution
kubectl exec -n advanced-networking $FRONTEND_POD -- nslookup external-api
# Expected result: Shows CNAME record pointing to api.example.com

# Clean up
kubectl delete -f ~/k8s-practice/networking/default-deny.yaml
kubectl delete -f ~/k8s-practice/networking/backend-to-db.yaml
kubectl delete -f ~/k8s-practice/networking/frontend-to-backend.yaml
kubectl delete -f ~/k8s-practice/networking/external-to-frontend.yaml
kubectl delete -f ~/k8s-practice/networking/allow-dns.yaml
kubectl delete -f ~/k8s-practice/networking/database.yaml
kubectl delete -f ~/k8s-practice/networking/backend.yaml
kubectl delete -f ~/k8s-practice/networking/frontend.yaml
kubectl delete -f ~/k8s-practice/networking/external-service.yaml
kubectl delete pod debug-pod -n advanced-networking
kubectl delete namespace advanced-networking
```

---

#### Exercise 6: Implementing Pod Resource Limits and Health Checks

##### Scenario
You need to deploy an application with appropriate resource limits and health checks to ensure it's scheduled correctly and remains healthy.

##### Tasks
1. Create a Deployment with resource requests and limits
2. Configure liveness and readiness probes
3. Test the health check mechanisms
4. Simulate resource pressure and observe behavior

##### Steps
```bash
# Create a namespace for our resource management exercise
kubectl create namespace resource-demo

# Deploy an application with resource constraints and health checks
cat > ~/k8s-practice/resources/app-deployment.yaml << EOF
apiVersion: apps/v1
kind: Deployment
metadata:
  name: resource-app
  namespace: resource-demo
spec:
  replicas: 2
  selector:
    matchLabels:
      app: resource-app
  template:
    metadata:
      labels:
        app: resource-app
    spec:
      containers:
      - name: nginx
        image: nginx:1.21
        ports:
        - containerPort: 80
        resources:
          requests:
            memory: "64Mi"
            cpu: "100m"
          limits:
            memory: "128Mi"
            cpu: "200m"
        livenessProbe:
          httpGet:
            path: /
            port: 80
          initialDelaySeconds: 10
          periodSeconds: 5
          timeoutSeconds: 2
          failureThreshold: 3
        readinessProbe:
          httpGet:
            path: /
            port: 80
          initialDelaySeconds: 5
          periodSeconds: 3
        volumeMounts:
        - name: health-toggle
          mountPath: /usr/share/nginx/html/health
      volumes:
      - name: health-toggle
        emptyDir: {}
---
apiVersion: v1
kind: Service
metadata:
  name: resource-app-service
  namespace: resource-demo
spec:
  selector:
    app: resource-app
  ports:
  - port: 80
    targetPort: 80
  type: ClusterIP
EOF

kubectl apply -f ~/k8s-practice/resources/app-deployment.yaml

# Check pod status and resource assignments
kubectl get pods -n resource-demo -o wide
kubectl describe pods -n resource-demo | grep -A 8 "Limits"

# Test health checks
POD_NAME=$(kubectl get pods -n resource-demo -o jsonpath='{.items[0].metadata.name}')

# Check if probes are working properly
kubectl describe pod $POD_NAME -n resource-demo | grep -A 15 "Liveness"
kubectl describe pod $POD_NAME -n resource-demo | grep -A 15 "Readiness"

# Cause the liveness probe to fail (creates a file that will return 404)
kubectl exec $POD_NAME -n resource-demo -- mkdir -p /usr/share/nginx/html/health
kubectl exec $POD_NAME -n resource-demo -- touch /usr/share/nginx/html/health/unhealthy

# Watch the pod being restarted by the kubelet due to failing liveness probe
kubectl get pods -n resource-demo -w
# (Wait for ~15-20 seconds until you see the pod restart, then press Ctrl+C)

# Verify the restart count increased
kubectl get pod $POD_NAME -n resource-demo -o jsonpath='{.status.containerStatuses[0].restartCount}'

# Create a second Pod with excessive resource requests to test scheduling
cat > ~/k8s-practice/resources/large-pod.yaml << EOF
apiVersion: v1
kind: Pod
metadata:
  name: large-pod
  namespace: resource-demo
spec:
  containers:
  - name: memory-hog
    image: ubuntu
    command: ["sleep", "3600"]
    resources:
      requests:
        memory: "4Gi"
        cpu: "2000m"
      limits:
        memory: "4Gi"
        cpu: "2000m"
EOF

kubectl apply -f ~/k8s-practice/resources/large-pod.yaml

# Check if the pod was scheduled or is pending
kubectl get pods -n resource-demo

# Check the pod's events to understand scheduling decisions
kubectl describe pod large-pod -n resource-demo | grep -A 10 "Events"

# Clean up
kubectl delete -f ~/k8s-practice/resources/app-deployment.yaml
kubectl delete -f ~/k8s-practice/resources/large-pod.yaml
kubectl delete namespace resource-demo
```

---

## Storage & Advanced Scheduling

### Persistent Volumes (PV)

Persistent Volumes are cluster resources that provide storage in Kubernetes. They are provisioned by an administrator or dynamically using Storage Classes. PVs are volume plugins like Volumes, but have a lifecycle independent of any individual pod that uses the PV.

Key characteristics of Persistent Volumes include:

- They exist as API resources in the cluster
- They are provisioned either statically by administrators or dynamically via Storage Classes
- They have specific capacity, access modes, and storage class attributes
- They can be mounted as file systems or block devices
- They support retention policies that determine what happens to the volume when released
- They exist outside the Pod lifecycle, persisting through Pod deletion or rescheduling

The PV subsystem provides an API abstraction that hides how storage is provided from how it is consumed. This separation enables administrators to manage the storage resources independently from applications that use them.

---

### Persistent Volume Claims (PVC)

Persistent Volume Claims are requests for storage by a user or application. They express the desired characteristics of storage, similar to how Pods consume node resources. PVCs request specific size, access modes, and storage classes.

Important aspects of PVCs include:

- They are namespaced objects, unlike PVs which are cluster-wide
- They can request specific sizes and access modes
- They can specify storage class requirements
- They connect Pods to PVs through a binding process
- They can remain unbound if no matching PV exists
- Pod specifications reference PVCs, not PVs directly

The PVC acts as an abstraction layer between the Pod and the underlying storage, allowing developers to request storage without needing to know the specifics of the underlying infrastructure.

---

### Storage Classes

Storage Classes provide a way to describe different "classes" of storage offered in a cluster. They help to abstract the underlying storage provider, provisioner, and parameters, enabling dynamic provisioning of storage.

Key features of Storage Classes include:

- They define the provisioner that creates the volume (e.g., AWS EBS, GCE PD, Azure Disk)
- They specify parameters required by the provisioner
- They control reclaim policies for dynamically provisioned volumes
- They can be set as the default Storage Class for the cluster
- They enable different quality of service levels, backup policies, or arbitrary policies
- They allow storage to be provisioned with different performance characteristics

Storage Classes make it possible for administrators to offer various storage options without users needing to know the details of how they are implemented.

---

### Dynamic Provisioning

Dynamic provisioning allows storage volumes to be created on-demand, eliminating the need for cluster administrators to pre-provision storage. When a user creates a PVC that requests a Storage Class, a new PV is automatically created to fulfill the claim.

Benefits of dynamic provisioning include:

- Automation of storage lifecycle management
- On-demand allocation of storage resources
- Reduced administrative overhead
- Consistency in storage provisioning
- Integration with cloud provider storage services
- The ability to define different storage profiles for different applications

Dynamic provisioning requires a properly configured Storage Class and a storage backend that supports it. Many cloud providers offer Storage Class implementations that integrate with their storage services.

---

### Volume Types

Kubernetes supports many volume types, each providing different storage capabilities:

- **EmptyDir**: Temporary storage that exists for the lifetime of a Pod
- **HostPath**: Mounts a file or directory from the host node's filesystem
- **ConfigMap and Secret**: Special volumes that expose Kubernetes ConfigMap and Secret objects
- **Cloud Provider Volumes**: Volumes specific to cloud providers like AWS EBS, GCE PD, or Azure Disk
- **NFS and iSCSI**: Network storage options
- **CSI Volumes**: Container Storage Interface compliant volumes
- **Persistent Volumes**: Abstraction for more permanent storage requirements

The selection of volume type depends on factors like data persistence requirements, sharing needs, performance characteristics, and the underlying infrastructure.

---

### Access Modes

Access modes determine how a volume can be mounted on hosts. The three access modes are:

- **ReadWriteOnce (RWO)**: The volume can be mounted as read-write by a single node
- **ReadOnlyMany (ROX)**: The volume can be mounted read-only by many nodes
- **ReadWriteMany (RWX)**: The volume can be mounted as read-write by many nodes

Not all volume types support all access modes. For example, AWS EBS volumes only support ReadWriteOnce, while NFS volumes typically support all three modes.

The access mode is a property of the PV and is requested in the PVC. During binding, the PV and PVC must have compatible access modes.

---

### Reclaim Policies

Reclaim policies determine what happens to a Persistent Volume when its claim is deleted. The available policies are:

- **Retain**: The volume is kept along with the data. It requires manual reclamation by an administrator.
- **Delete**: The volume and its data are automatically deleted when the PVC is deleted.
- **Recycle**: Basic scrub (rm -rf /thevolume/*) is performed, making it available for a new claim.

The Recycle policy is deprecated and will be removed in a future release. The recommended alternatives are dynamic provisioning or a custom operator for volume lifecycle management.

The reclaim policy is specified when a PV is created or can be part of a Storage Class definition for dynamically provisioned volumes.

---

### Container Storage Interface (CSI)

The Container Storage Interface (CSI) is a standard for exposing arbitrary block and file storage systems to containerized workloads in Kubernetes. It allows storage vendors to develop a plugin once and have it work across multiple container orchestration systems.

Key aspects of CSI include:

- A standardized API between container orchestrators and storage providers
- Out-of-tree volume plugins that are deployed as pods
- Support for volume snapshots, cloning, and resizing
- Simplified development and maintenance of storage plugins
- Increased security through separation of storage plugin code from core Kubernetes

CSI has become the preferred way to integrate storage systems with Kubernetes, replacing the older in-tree volume plugins which required changes to the core Kubernetes code.

---

### Node Selectors and Labels

Node selectors provide a simple way to constrain pods to nodes with specific labels. This basic form of scheduling ensures that pods run only on nodes that have required labels.

Key aspects include:

- Labels are key-value pairs attached to Kubernetes objects
- Node selectors use labels to determine pod placement
- The `nodeSelector` field in pod specifications defines required node labels
- Simple equality-based selection (node must have all the specified labels)
- Can be used to direct pods to nodes with specific hardware or in specific regions

While node selectors are simple to use, they lack the expressiveness of node affinity for more complex scheduling requirements.

---

### Node Affinity and Anti-Affinity

Node affinity is a more expressive way to constrain which nodes a pod can be scheduled on, based on node labels. It provides more control than simple node selectors, including "soft" preferences and complex matching expressions.

Node affinity types include:

- **requiredDuringSchedulingIgnoredDuringExecution**: Hard requirement that must be met for a pod to be scheduled
- **preferredDuringSchedulingIgnoredDuringExecution**: Soft preference that the scheduler will try to enforce but will not guarantee

Node anti-affinity can be achieved by using the `NotIn` or `DoesNotExist` operators in node affinity rules to prevent pods from being scheduled on specific nodes.

The "IgnoredDuringExecution" part means that if node labels change after pod scheduling, the pod will not be evicted.

---

### Pod Affinity and Anti-Affinity

Pod affinity and anti-affinity allow you to constrain which nodes pods can be scheduled on based on the labels of pods already running on the node, rather than the node labels themselves.

This enables scenarios such as:

- Co-locating related pods on the same node or zone for reduced latency
- Spreading pods across nodes or zones for high availability
- Preventing certain pods from running together due to resource contention

Like node affinity, pod affinity comes in required and preferred varieties and uses the same "DuringSchedulingIgnoredDuringExecution" suffix.

Pod anti-affinity is particularly useful for ensuring high availability by spreading replicas across failure domains like nodes, racks, or availability zones.

---

### Taints and Tolerations

Taints and tolerations work together to ensure that pods are not scheduled onto inappropriate nodes. Taints are applied to nodes, and tolerations are applied to pods.

Key concepts include:

- Taints mark nodes as unsuitable for certain pods
- Tolerations allow pods to schedule onto nodes with matching taints
- Taints have a key, value, and effect (NoSchedule, PreferNoSchedule, or NoExecute)
- NoExecute taints cause existing pods to be evicted if they don't have a matching toleration
- Tolerations don't guarantee that a pod will be scheduled on a tainted node; they only permit it
- System-critical pods often have tolerations for node problems

Taints and tolerations are particularly useful for dedicating nodes to specific workloads, creating specialized nodes, or gracefully draining nodes for maintenance.

---

### Resource Limits and Requests

Resource limits and requests are specifications for CPU and memory usage that help the scheduler make better decisions about pod placement and resource allocation.

Key concepts include:

- **Requests**: The minimum amount of resources that must be available for a pod to be scheduled
- **Limits**: The maximum amount of resources a pod can use
- Resources that can be specified include CPU, memory, ephemeral storage, and extended resources
- The scheduler uses requests to determine which nodes have sufficient resources
- The kubelet enforces limits by throttling CPU or potentially terminating pods that exceed memory limits
- QoS (Quality of Service) classes are determined by how requests and limits are configured

Properly configuring resource requests and limits is essential for cluster stability and efficient resource utilization. Under-requesting resources can lead to resource contention, while over-requesting can lead to resource waste.

---

### Pod Priority and Preemption

Pod priority and preemption allow higher-priority pods to be scheduled before lower-priority pods, and if necessary, by preempting (evicting) lower-priority pods.

Key aspects include:

- PriorityClasses define the relative importance of pods
- Pods with higher priority are scheduled ahead of pods with lower priority
- When resources are constrained, the scheduler can evict lower-priority pods to make room for higher-priority ones
- System-critical pods have built-in high priority
- Preemption respects pod disruption budgets when possible

This feature is crucial for ensuring that critical workloads get resources even in a constrained cluster, implementing service-level objectives for different workloads, and providing graceful degradation under pressure.

---

### Pod Disruption Budgets (PDB)

Pod Disruption Budgets protect applications from voluntary disruptions by limiting how many pods can be down simultaneously due to voluntary disruptions like node drains or scaling operations.

Key concepts include:

- PDBs specify the minimum number or percentage of pods that must remain available
- They only protect against voluntary disruptions, not involuntary ones like node failures
- They integrate with operations like node drains, ensuring application availability
- They require pod selectors to identify which pods they protect
- They work with the Eviction API to prevent harmful disruptions

PDBs are essential for maintaining application availability during cluster maintenance operations, ensuring high availability and meeting service-level objectives.

---

### Topology Spread Constraints

Topology Spread Constraints allow control over how pods are spread across the cluster among failure domains such as regions, zones, nodes, or other user-defined topology domains.

Important aspects include:

- They help distribute pods evenly across different domains
- They improve application availability and resource utilization
- They can be made required or best-effort (soft)
- They use node labels to identify topological domains
- They can be combined with node affinity and pod affinity for complex scheduling requirements

When properly configured, topology spread constraints ensure that replicas of an application are distributed to maximize resilience to domain-level failures.

----

### Lab 1: Working with Persistent Volumes and Persistent Volume Claims

#### Objective
Create and manage Persistent Volumes, Persistent Volume Claims, and understand the binding process between them.

#### Prerequisites
- Running Kubernetes cluster
- kubectl configured to access your cluster
- Storage providers accessible to your cluster (local storage will be used for demonstration)

#### Step 1: Create a Persistent Volume (PV) using a hostPath

```bash
# Create a directory for our storage exercises
mkdir -p ~/k8s-labs/storage

# Create a simple Persistent Volume using hostPath (for demonstration purposes)
cat > ~/k8s-labs/storage/local-pv.yaml << EOF
apiVersion: v1
kind: PersistentVolume
metadata:
  name: local-pv
spec:
  capacity:
    storage: 1Gi
  volumeMode: Filesystem
  accessModes:
    - ReadWriteOnce
  persistentVolumeReclaimPolicy: Retain
  storageClassName: manual
  hostPath:
    path: /mnt/data
EOF

# Before applying, ensure the directory exists on your node
# Note: In a real cluster environment, you would need to ensure this directory exists on the target node
# For this lab, we'll create it on the control plane node
sudo mkdir -p /mnt/data

# Apply the PV configuration
kubectl apply -f ~/k8s-labs/storage/local-pv.yaml

# Verify the PV has been created and is in Available status
kubectl get pv
kubectl describe pv local-pv
```

#### Step 2: Create a Persistent Volume Claim (PVC)

```bash
# Create a PVC that matches our PV
cat > ~/k8s-labs/storage/my-pvc.yaml << EOF
apiVersion: v1
kind: PersistentVolumeClaim
metadata:
  name: my-pvc
spec:
  accessModes:
    - ReadWriteOnce
  volumeMode: Filesystem
  resources:
    requests:
      storage: 1Gi
  storageClassName: manual
EOF

# Apply the PVC configuration
kubectl apply -f ~/k8s-labs/storage/my-pvc.yaml

# Verify the PVC has been created and bound to our PV
kubectl get pvc
kubectl describe pvc my-pvc

# Check the PV status to confirm it's now bound
kubectl get pv
```

#### Step 3: Create a Pod that uses the PVC

```bash
# Create a Pod that uses our PVC
cat > ~/k8s-labs/storage/pv-pod.yaml << EOF
apiVersion: v1
kind: Pod
metadata:
  name: pv-pod
spec:
  containers:
    - name: task-pv-container
      image: nginx
      ports:
        - containerPort: 80
          name: "http-server"
      volumeMounts:
        - mountPath: "/usr/share/nginx/html"
          name: task-pv-storage
  volumes:
    - name: task-pv-storage
      persistentVolumeClaim:
        claimName: my-pvc
EOF

# Apply the Pod configuration
kubectl apply -f ~/k8s-labs/storage/pv-pod.yaml

# Verify the Pod is running
kubectl get pods
kubectl describe pod pv-pod
```

#### Step 4: Write and read data from the volume

```bash
# Wait for the Pod to be Running
kubectl wait --for=condition=Ready pod/pv-pod

# Write data to the persistent volume
kubectl exec pv-pod -- sh -c "echo 'Hello from Kubernetes storage' > /usr/share/nginx/html/index.html"

# Verify the data is written
kubectl exec pv-pod -- cat /usr/share/nginx/html/index.html

# Delete the Pod
kubectl delete pod pv-pod

# Create another Pod using the same PVC
cat > ~/k8s-labs/storage/pv-pod2.yaml << EOF
apiVersion: v1
kind: Pod
metadata:
  name: pv-pod2
spec:
  containers:
    - name: task-pv-container
      image: nginx
      ports:
        - containerPort: 80
          name: "http-server"
      volumeMounts:
        - mountPath: "/usr/share/nginx/html"
          name: task-pv-storage
  volumes:
    - name: task-pv-storage
      persistentVolumeClaim:
        claimName: my-pvc
EOF

# Apply the second Pod configuration
kubectl apply -f ~/k8s-labs/storage/pv-pod2.yaml

# Wait for the Pod to be Running
kubectl wait --for=condition=Ready pod/pv-pod2

# Verify the data is still there (demonstrating persistence)
kubectl exec pv-pod2 -- cat /usr/share/nginx/html/index.html
```

#### Step 5: Understand PV reclaim policies

```bash
# Delete the PVC
kubectl delete pvc my-pvc

# Check the status of the PV (should be Released, but not deleted due to Retain policy)
kubectl get pv

# Change the reclaim policy to Delete
kubectl patch pv local-pv -p '{"spec":{"persistentVolumeReclaimPolicy":"Delete"}}'

# Create a new PVC
cat > ~/k8s-labs/storage/new-pvc.yaml << EOF
apiVersion: v1
kind: PersistentVolumeClaim
metadata:
  name: new-pvc
spec:
  accessModes:
    - ReadWriteOnce
  volumeMode: Filesystem
  resources:
    requests:
      storage: 1Gi
  storageClassName: manual
EOF

# Since our PV is in Released state, we need to manually make it Available again
# In a real environment, an admin would reclaim the volume
kubectl patch pv local-pv -p '{"spec":{"claimRef": null}}'

# Apply the new PVC
kubectl apply -f ~/k8s-labs/storage/new-pvc.yaml

# Verify binding
kubectl get pvc
kubectl get pv

# Delete the PVC to see the Delete policy in action
kubectl delete pvc new-pvc

# Check if the PV is also deleted
kubectl get pv
```

#### Step 6: Clean up resources

```bash
# Delete any remaining pods
kubectl delete pod pv-pod2 --ignore-not-found

# Delete any remaining PVCs
kubectl delete pvc --all

# Delete the PV
kubectl delete pv local-pv
```

---

### Lab 2: Working with Storage Classes and Dynamic Provisioning

#### Objective
Configure Storage Classes for dynamic provisioning of Persistent Volumes and understand how to use different provisioners.

#### Prerequisites
- Running Kubernetes cluster
- kubectl configured to access your cluster
- A storage provider that supports dynamic provisioning (varies by environment)

#### Step 1: Examine default StorageClasses in your cluster

```bash
# List the StorageClasses in your cluster
kubectl get storageclass

# Examine the default StorageClass (if any)
kubectl get storageclass -o yaml
```

#### Step 2: Create a custom StorageClass

```bash
# Create a StorageClass based on your environment
# The example below is for a generic environment and may need adaptation

# For GKE (Google Kubernetes Engine)
cat > ~/k8s-labs/storage/sc-standard.yaml << EOF
apiVersion: storage.k8s.io/v1
kind: StorageClass
metadata:
  name: standard
provisioner: kubernetes.io/gce-pd
parameters:
  type: pd-standard
  replication-type: none
reclaimPolicy: Delete
allowVolumeExpansion: true
volumeBindingMode: Immediate
EOF

# For AKS (Azure Kubernetes Service)
cat > ~/k8s-labs/storage/sc-standard.yaml << EOF
apiVersion: storage.k8s.io/v1
kind: StorageClass
metadata:
  name: standard
provisioner: kubernetes.io/azure-disk
parameters:
  storageaccounttype: Standard_LRS
  kind: Managed
reclaimPolicy: Delete
allowVolumeExpansion: true
volumeBindingMode: Immediate
EOF

# For EKS (Amazon Elastic Kubernetes Service)
cat > ~/k8s-labs/storage/sc-standard.yaml << EOF
apiVersion: storage.k8s.io/v1
kind: StorageClass
metadata:
  name: standard
provisioner: kubernetes.io/aws-ebs
parameters:
  type: gp2
reclaimPolicy: Delete
allowVolumeExpansion: true
volumeBindingMode: Immediate
EOF

# For Minikube or local development (with hostpath provisioner)
cat > ~/k8s-labs/storage/sc-standard.yaml << EOF
apiVersion: storage.k8s.io/v1
kind: StorageClass
metadata:
  name: standard
provisioner: k8s.io/minikube-hostpath
reclaimPolicy: Delete
volumeBindingMode: Immediate
EOF

# Apply the StorageClass that matches your environment
kubectl apply -f ~/k8s-labs/storage/sc-standard.yaml

# Verify the StorageClass
kubectl get storageclass
kubectl describe storageclass standard
```

#### Step 3: Create a PVC using dynamic provisioning

```bash
# Create a PVC that uses the StorageClass
cat > ~/k8s-labs/storage/dynamic-pvc.yaml << EOF
apiVersion: v1
kind: PersistentVolumeClaim
metadata:
  name: dynamic-pvc
spec:
  accessModes:
    - ReadWriteOnce
  volumeMode: Filesystem
  resources:
    requests:
      storage: 1Gi
  storageClassName: standard
EOF

# Apply the PVC
kubectl apply -f ~/k8s-labs/storage/dynamic-pvc.yaml

# Verify the PVC is bound and a PV is dynamically created
kubectl get pvc
kubectl get pv
```

#### Step 4: Create a Pod that uses the dynamically provisioned volume

```bash
# Create a Pod that uses our dynamic PVC
cat > ~/k8s-labs/storage/dynamic-pod.yaml << EOF
apiVersion: v1
kind: Pod
metadata:
  name: dynamic-pod
spec:
  containers:
    - name: dynamic-container
      image: nginx
      ports:
        - containerPort: 80
          name: "http-server"
      volumeMounts:
        - mountPath: "/usr/share/nginx/html"
          name: dynamic-storage
  volumes:
    - name: dynamic-storage
      persistentVolumeClaim:
        claimName: dynamic-pvc
EOF

# Apply the Pod configuration
kubectl apply -f ~/k8s-labs/storage/dynamic-pod.yaml

# Verify the Pod is running
kubectl get pods
kubectl describe pod dynamic-pod

# Write data to the dynamically provisioned volume
kubectl wait --for=condition=Ready pod/dynamic-pod
kubectl exec dynamic-pod -- sh -c "echo 'This is from a dynamically provisioned volume' > /usr/share/nginx/html/index.html"

# Verify the data is written
kubectl exec dynamic-pod -- cat /usr/share/nginx/html/index.html
```

#### Step 5: Create a StorageClass with different parameters

```bash
# Create a StorageClass with different parameters (example for a premium class)

# For GKE
cat > ~/k8s-labs/storage/sc-premium.yaml << EOF
apiVersion: storage.k8s.io/v1
kind: StorageClass
metadata:
  name: premium
provisioner: kubernetes.io/gce-pd
parameters:
  type: pd-ssd
  replication-type: none
reclaimPolicy: Retain
allowVolumeExpansion: true
volumeBindingMode: Immediate
EOF

# For AKS
cat > ~/k8s-labs/storage/sc-premium.yaml << EOF
apiVersion: storage.k8s.io/v1
kind: StorageClass
metadata:
  name: premium
provisioner: kubernetes.io/azure-disk
parameters:
  storageaccounttype: Premium_LRS
  kind: Managed
reclaimPolicy: Retain
allowVolumeExpansion: true
volumeBindingMode: Immediate
EOF

# For EKS
cat > ~/k8s-labs/storage/sc-premium.yaml << EOF
apiVersion: storage.k8s.io/v1
kind: StorageClass
metadata:
  name: premium
provisioner: kubernetes.io/aws-ebs
parameters:
  type: io1
  iopsPerGB: "10"
reclaimPolicy: Retain
allowVolumeExpansion: true
volumeBindingMode: Immediate
EOF

# For local development (with different reclaim policy)
cat > ~/k8s-labs/storage/sc-premium.yaml << EOF
apiVersion: storage.k8s.io/v1
kind: StorageClass
metadata:
  name: premium
provisioner: k8s.io/minikube-hostpath
reclaimPolicy: Retain
volumeBindingMode: Immediate
EOF

# Apply the premium StorageClass
kubectl apply -f ~/k8s-labs/storage/sc-premium.yaml

# Create a PVC using the premium StorageClass
cat > ~/k8s-labs/storage/premium-pvc.yaml << EOF
apiVersion: v1
kind: PersistentVolumeClaim
metadata:
  name: premium-pvc
spec:
  accessModes:
    - ReadWriteOnce
  volumeMode: Filesystem
  resources:
    requests:
      storage: 1Gi
  storageClassName: premium
EOF

kubectl apply -f ~/k8s-labs/storage/premium-pvc.yaml

# Verify the PVC is bound and a PV is dynamically created
kubectl get pvc
kubectl get pv
```

#### Step 6: Set a default StorageClass

```bash
# Check current default StorageClass
kubectl get storageclass

# Remove the default annotation from any existing default StorageClass
CURRENT_DEFAULT=$(kubectl get storageclass -o jsonpath='{.items[?(@.metadata.annotations.storageclass\.kubernetes\.io/is-default-class=="true")].metadata.name}')
if [ -n "$CURRENT_DEFAULT" ]; then
  kubectl patch storageclass $CURRENT_DEFAULT -p '{"metadata": {"annotations": {"storageclass.kubernetes.io/is-default-class": "false"}}}'
fi

# Set our standard StorageClass as the default
kubectl patch storageclass standard -p '{"metadata": {"annotations": {"storageclass.kubernetes.io/is-default-class": "true"}}}'

# Verify the change
kubectl get storageclass

# Create a PVC without specifying a StorageClass (should use the default)
cat > ~/k8s-labs/storage/default-pvc.yaml << EOF
apiVersion: v1
kind: PersistentVolumeClaim
metadata:
  name: default-pvc
spec:
  accessModes:
    - ReadWriteOnce
  volumeMode: Filesystem
  resources:
    requests:
      storage: 1Gi
EOF

kubectl apply -f ~/k8s-labs/storage/default-pvc.yaml

# Verify which StorageClass was used
kubectl get pvc default-pvc -o jsonpath='{.spec.storageClassName}'
```

#### Step 7: Clean up resources

```bash
# Delete all the pods
kubectl delete pod dynamic-pod --ignore-not-found

# Delete all the PVCs
kubectl delete pvc dynamic-pvc premium-pvc default-pvc --ignore-not-found

# Delete the StorageClasses
kubectl delete storageclass standard premium --ignore-not-found
```

---

### Lab 3: Advanced Pod Scheduling with Affinity and Anti-Affinity

#### Objective
Configure advanced scheduling constraints for Pods using node selectors, node affinity, pod affinity, and anti-affinity.

#### Prerequisites
- Running Kubernetes cluster with multiple nodes
- kubectl configured to access your cluster

#### Step 1: Label nodes for scheduling

```bash
# List nodes in the cluster
kubectl get nodes

# Add labels to your nodes (adjust the node names to match your cluster)
# If you have only one node, apply different labels to the same node
NODE1=$(kubectl get nodes -o jsonpath='{.items[0].metadata.name}')
NODE2=$(kubectl get nodes -o jsonpath='{.items[1].metadata.name}' 2>/dev/null || echo $NODE1)

kubectl label nodes $NODE1 disktype=ssd zone=us-east-1a
kubectl label nodes $NODE2 disktype=hdd zone=us-east-1b

# Verify node labels
kubectl get nodes --show-labels
```

#### Step 2: Create a Pod with node selectors

```bash
# Create a directory for scheduling exercises
mkdir -p ~/k8s-labs/scheduling

# Create a Pod that uses nodeSelector
cat > ~/k8s-labs/scheduling/nodeselector-pod.yaml << EOF
apiVersion: v1
kind: Pod
metadata:
  name: nginx-nodeselector
spec:
  containers:
  - name: nginx
    image: nginx
    ports:
    - containerPort: 80
  nodeSelector:
    disktype: ssd
EOF

# Apply the Pod configuration
kubectl apply -f ~/k8s-labs/scheduling/nodeselector-pod.yaml

# Verify the Pod got scheduled on the node with disktype=ssd
kubectl get pod nginx-nodeselector -o wide
```

#### Step 3: Create a Pod with node affinity

```bash
# Create a Pod with required node affinity
cat > ~/k8s-labs/scheduling/nodeaffinity-pod.yaml << EOF
apiVersion: v1
kind: Pod
metadata:
  name: nginx-nodeaffinity
spec:
  affinity:
    nodeAffinity:
      requiredDuringSchedulingIgnoredDuringExecution:
        nodeSelectorTerms:
        - matchExpressions:
          - key: zone
            operator: In
            values:
            - us-east-1a
      preferredDuringSchedulingIgnoredDuringExecution:
      - weight: 1
        preference:
          matchExpressions:
          - key: disktype
            operator: In
            values:
            - ssd
  containers:
  - name: nginx
    image: nginx
    ports:
    - containerPort: 80
EOF

# Apply the Pod configuration
kubectl apply -f ~/k8s-labs/scheduling/nodeaffinity-pod.yaml

# Verify the Pod got scheduled on the node with zone=us-east-1a
kubectl get pod nginx-nodeaffinity -o wide
```

#### Step 4: Create Pods with pod affinity and anti-affinity

```bash
# First, create a Pod that other Pods will reference
cat > ~/k8s-labs/scheduling/webapp.yaml << EOF
apiVersion: v1
kind: Pod
metadata:
  name: webapp
  labels:
    app: webapp
spec:
  containers:
  - name: webapp
    image: nginx
    ports:
    - containerPort: 80
EOF

# Apply the Pod configuration
kubectl apply -f ~/k8s-labs/scheduling/webapp.yaml

# Wait for the webapp Pod to be Running
kubectl wait --for=condition=Ready pod/webapp

# Create a Pod with pod affinity (wants to run on the same node as the webapp)
cat > ~/k8s-labs/scheduling/podaffinity-pod.yaml << EOF
apiVersion: v1
kind: Pod
metadata:
  name: redis-cache
spec:
  affinity:
    podAffinity:
      requiredDuringSchedulingIgnoredDuringExecution:
      - labelSelector:
          matchExpressions:
          - key: app
            operator: In
            values:
            - webapp
        topologyKey: kubernetes.io/hostname
  containers:
  - name: redis
    image: redis
    ports:
    - containerPort: 6379
EOF

# Apply the Pod configuration
kubectl apply -f ~/k8s-labs/scheduling/podaffinity-pod.yaml

# Create a Pod with pod anti-affinity (doesn't want to run on the same node as the webapp)
cat > ~/k8s-labs/scheduling/podantiaffinity-pod.yaml << EOF
apiVersion: v1
kind: Pod
metadata:
  name: analytics
spec:
  affinity:
    podAntiAffinity:
      requiredDuringSchedulingIgnoredDuringExecution:
      - labelSelector:
          matchExpressions:
          - key: app
            operator: In
            values:
            - webapp
        topologyKey: kubernetes.io/hostname
  containers:
  - name: analytics
    image: nginx
    ports:
    - containerPort: 80
EOF

# Apply the Pod configuration
kubectl apply -f ~/k8s-labs/scheduling/podantiaffinity-pod.yaml

# Verify where the Pods got scheduled
kubectl get pods -o wide

# The redis-cache Pod should be on the same node as webapp
# The analytics Pod should be on a different node than webapp
# If you have only one node, the analytics Pod will remain in Pending state
```

#### Step 5: Test scheduling with more complex affinity rules

```bash
# Create a Deployment that spreads Pods across nodes with preferred anti-affinity
cat > ~/k8s-labs/scheduling/deployment-antiaffinity.yaml << EOF
apiVersion: apps/v1
kind: Deployment
metadata:
  name: web-server
spec:
  replicas: 3
  selector:
    matchLabels:
      app: web-server
  template:
    metadata:
      labels:
        app: web-server
    spec:
      affinity:
        podAntiAffinity:
          preferredDuringSchedulingIgnoredDuringExecution:
          - weight: 100
            podAffinityTerm:
              labelSelector:
                matchExpressions:
                - key: app
                  operator: In
                  values:
                  - web-server
              topologyKey: kubernetes.io/hostname
      containers:
      - name: web-app
        image: nginx
        ports:
        - containerPort: 80
EOF

# Apply the Deployment configuration
kubectl apply -f ~/k8s-labs/scheduling/deployment-antiaffinity.yaml

# Verify the Pods distribution across nodes
kubectl get pods -l app=web-server -o wide

# The Pods should be distributed across different nodes if possible
# If you have only one node, all Pods will still be scheduled but on the same node
```

#### Step 6: Clean up resources

```bash
# Delete all the created Pods and Deployments
kubectl delete -f ~/k8s-labs/scheduling/nodeselector-pod.yaml --ignore-not-found
kubectl delete -f ~/k8s-labs/scheduling/nodeaffinity-pod.yaml --ignore-not-found
kubectl delete -f ~/k8s-labs/scheduling/webapp.yaml --ignore-not-found
kubectl delete -f ~/k8s-labs/scheduling/podaffinity-pod.yaml --ignore-not-found
kubectl delete -f ~/k8s-labs/scheduling/podantiaffinity-pod.yaml --ignore-not-found
kubectl delete -f ~/k8s-labs/scheduling/deployment-antiaffinity.yaml --ignore-not-found

# Remove the labels from the nodes
kubectl label nodes $NODE1 disktype- zone-
kubectl label nodes $NODE2 disktype- zone-
```

---

### Lab 4: Working with Taints and Tolerations

#### Objective
Understand how taints and tolerations work to control which Pods can be scheduled on which nodes.

#### Prerequisites
- Running Kubernetes cluster with at least one node
- kubectl configured to access your cluster

#### Step 1: Add taints to nodes

```bash
# List nodes in the cluster
kubectl get nodes

# Add a taint to a node (adjust the node name to match your cluster)
NODE1=$(kubectl get nodes -o jsonpath='{.items[0].metadata.name}')
kubectl taint nodes $NODE1 key=value:NoSchedule

# Verify the taint
kubectl describe node $NODE1 | grep Taints
```

#### Step 2: Create a Pod without tolerations

```bash
# Create a Pod without tolerations
cat > ~/k8s-labs/scheduling/pod-without-toleration.yaml << EOF
apiVersion: v1
kind: Pod
metadata:
  name: pod-without-toleration
spec:
  containers:
  - name: nginx
    image: nginx
EOF

# Apply the Pod configuration
kubectl apply -f ~/k8s-labs/scheduling/pod-without-toleration.yaml

# Check if the Pod was scheduled
kubectl get pods
kubectl describe pod pod-without-toleration

# If you have multiple nodes, the Pod should be scheduled on a node without the taint
# If you have only one node, the Pod will remain in Pending state
```

#### Step 3: Create a Pod with matching toleration

```bash
# Create a Pod with a toleration that matches the taint
cat > ~/k8s-labs/scheduling/pod-with-toleration.yaml << EOF
apiVersion: v1
kind: Pod
metadata:
  name: pod-with-toleration
spec:
  tolerations:
  - key: "key"
    operator: "Equal"
    value: "value"
    effect: "NoSchedule"
  containers:
  - name: nginx
    image: nginx
EOF

# Apply the Pod configuration
kubectl apply -f ~/k8s-labs/scheduling/pod-with-toleration.yaml

# Check if the Pod was scheduled
kubectl get pods
kubectl describe pod pod-with-toleration

# The Pod should be scheduled, even on the tainted node
```

#### Step 4: Create a Pod with a different toleration

```bash
# Create a Pod with a toleration that doesn't match the taint
cat > ~/k8s-labs/scheduling/pod-with-different-toleration.yaml << EOF
apiVersion: v1
kind: Pod
metadata:
  name: pod-with-different-toleration
spec:
  tolerations:
  - key: "different-key"
    operator: "Equal"
    value: "different-value"
    effect: "NoSchedule"
  containers:
  - name: nginx
    image: nginx
EOF

# Apply the Pod configuration
kubectl apply -f ~/k8s-labs/scheduling/pod-with-different-toleration.yaml

# Check if the Pod was scheduled
kubectl get pods
kubectl describe pod pod-with-different-toleration

# If you have multiple nodes, the Pod should be scheduled on a node without the taint
# If you have only one node, the Pod will remain in Pending state
```

#### Step 5: Test NoExecute taint effect

```bash
# Add a NoExecute taint to the node (this will evict existing Pods without matching tolerations)
kubectl taint nodes $NODE1 another-key=another-value:NoExecute

# Create a Pod with a toleration for the NoExecute taint
cat > ~/k8s-labs/scheduling/pod-with-noexecute-toleration.yaml << EOF
apiVersion: v1
kind: Pod
metadata:
  name: pod-with-noexecute-toleration
spec:
  tolerations:
  - key: "another-key"
    operator: "Equal"
    value: "another-value"
    effect: "NoExecute"
  - key: "key"
    operator: "Equal"
    value: "value"
    effect: "NoSchedule"
  containers:
  - name: nginx
    image: nginx
EOF

# Apply the Pod configuration
kubectl apply -f ~/k8s-labs/scheduling/pod-with-noexecute-toleration.yaml

# Check if the Pod was scheduled and other Pods were evicted
kubectl get pods
kubectl describe pod pod-with-noexecute-toleration

# The new Pod should be scheduled, while Pods without the NoExecute toleration
# should have been evicted (or never scheduled if they were created after the taint)
```

#### Step 6: Clean up resources

```bash
# Delete all the created Pods
kubectl delete pod pod-without-toleration pod-with-toleration pod-with-different-toleration pod-with-noexecute-toleration --ignore-not-found

# Remove the taints from the nodes
kubectl taint nodes $NODE1 key=value:NoSchedule- another-key=another-value:NoExecute-
```

---

### Lab 5: Advanced Pod Scheduling with Resource Limits and Requests

#### Objective
Configure resource requests and limits for Pods to ensure proper scheduling and resource allocation.

#### Prerequisites
- Running Kubernetes cluster
- kubectl configured to access your cluster

#### Step 1: Create Pods with different resource requirements

```bash
# Create a Pod with minimal resource requests
cat > ~/k8s-labs/scheduling/small-pod.yaml << EOF
apiVersion: v1
kind: Pod
metadata:
  name: small-pod
spec:
  containers:
  - name: small-container
    image: nginx
    resources:
      requests:
        memory: "64Mi"
        cpu: "100m"
      limits:
        memory: "128Mi"
        cpu: "200m"
EOF

# Apply the Pod configuration
kubectl apply -f ~/k8s-labs/scheduling/small-pod.yaml

# Create a Pod with medium resource requests
cat > ~/k8s-labs/scheduling/medium-pod.yaml << EOF
apiVersion: v1
kind: Pod
metadata:
  name: medium-pod
spec:
  containers:
  - name: medium-container
    image: nginx
    resources:
      requests:
        memory: "256Mi"
        cpu: "500m"
      limits:
        memory: "512Mi"
        cpu: "1000m"
EOF

# Apply the Pod configuration
kubectl apply -f ~/k8s-labs/scheduling/medium-pod.yaml

# Create a Pod with large resource requests
cat > ~/k8s-labs/scheduling/large-pod.yaml << EOF
apiVersion: v1
kind: Pod
metadata:
  name: large-pod
spec:
  containers:
  - name: large-container
    image: nginx
    resources:
      requests:
        memory: "1Gi"
        cpu: "1"
      limits:
        memory: "2Gi"
        cpu: "2"
EOF

# Apply the Pod configuration
kubectl apply -f ~/k8s-labs/scheduling/large-pod.yaml

# Check the status of the Pods
kubectl get pods
```

#### Step 2: Examine Pod scheduling decisions

```bash
# Check where the Pods were scheduled
kubectl get pods -o wide

# Get detailed information on each Pod
kubectl describe pod small-pod
kubectl describe pod medium-pod
kubectl describe pod large-pod

# Check resource usage on the nodes
kubectl describe nodes | grep -A 5 "Allocated resources"
```

#### Step 3: Test resource constraints with a stress-testing Pod

```bash
# Create a Pod that tries to use more memory than its limit
cat > ~/k8s-labs/scheduling/memory-stress-pod.yaml << EOF
apiVersion: v1
kind: Pod
metadata:
  name: memory-stress-pod
spec:
  containers:
  - name: memory-stress
    image: polinux/stress
    resources:
      requests:
        memory: "100Mi"
        cpu: "100m"
      limits:
        memory: "200Mi"
        cpu: "200m"
    command: ["stress"]
    args: ["--vm", "1", "--vm-bytes", "250M", "--vm-hang", "1"]
EOF

# Apply the Pod configuration
kubectl apply -f ~/k8s-labs/scheduling/memory-stress-pod.yaml

# Watch the Pod status (it should be OOMKilled)
kubectl get pods -w
# (Press Ctrl+C to exit the watch after a while)

# Check the events associated with the Pod
kubectl describe pod memory-stress-pod
```

#### Step 4: Create a Pod with impossible resource requirements

```bash
# Create a Pod with resource requests that exceed node capacity
cat > ~/k8s-labs/scheduling/impossible-pod.yaml << EOF
apiVersion: v1
kind: Pod
metadata:
  name: impossible-pod
spec:
  containers:
  - name: impossible-container
    image: nginx
    resources:
      requests:
        memory: "100Gi"
        cpu: "100"
EOF

# Apply the Pod configuration
kubectl apply -f ~/k8s-labs/scheduling/impossible-pod.yaml

# Check the status of the Pod (should remain in Pending state)
kubectl get pods
kubectl describe pod impossible-pod

# You should see events indicating that the Pod cannot be scheduled due to insufficient resources
```

#### Step 5: Create a multi-container Pod with resource specifications

```bash
# Create a Pod with multiple containers, each with its own resource specifications
cat > ~/k8s-labs/scheduling/multi-container-pod.yaml << EOF
apiVersion: v1
kind: Pod
metadata:
  name: multi-container-pod
spec:
  containers:
  - name: nginx
    image: nginx
    resources:
      requests:
        memory: "64Mi"
        cpu: "100m"
      limits:
        memory: "128Mi"
        cpu: "200m"
  - name: redis
    image: redis
    resources:
      requests:
        memory: "128Mi"
        cpu: "100m"
      limits:
        memory: "256Mi"
        cpu: "200m"
EOF

# Apply the Pod configuration
kubectl apply -f ~/k8s-labs/scheduling/multi-container-pod.yaml

# Check the status of the Pod
kubectl get pods
kubectl describe pod multi-container-pod

# The total resource request for the Pod is the sum of all containers' requests
```

#### Step 6: Clean up resources

```bash
# Delete all the created Pods
kubectl delete pod small-pod medium-pod large-pod memory-stress-pod impossible-pod multi-container-pod --ignore-not-found
```

---

### Practice Exercises

#### Exercise 1: EmptyDir for Data Sharing Between Containers

##### Scenario
You need to set up a log collection system where one container generates logs and another container processes them. Both containers need to share a volume for this purpose.

##### Tasks
1. Create a multi-container Pod using emptyDir for log sharing
2. Configure a log generator container
3. Configure a log processor container
4. Verify data is being shared between containers

##### Steps
```bash
# Create a namespace for our exercises
kubectl create namespace storage-exercises

# Create a multi-container Pod with emptyDir volume
cat > ~/k8s-practice/storage/logging-pod.yaml << EOF
apiVersion: v1
kind: Pod
metadata:
  name: logging-pod
  namespace: storage-exercises
spec:
  containers:
  - name: log-generator
    image: busybox
    command: ["/bin/sh", "-c"]
    args:
    - >
      i=0;
      while true;
      do
        echo "$(date) - Log entry $i" >> /var/log/shared/app.log;
        i=$((i+1));
        sleep 1;
      done
    volumeMounts:
    - name: shared-logs
      mountPath: /var/log/shared
  - name: log-processor
    image: busybox
    command: ["/bin/sh", "-c"]
    args:
    - >
      tail -f /var/log/shared/app.log | while read line;
      do
        echo "Processed: $line" >> /var/log/shared/processed.log;
      done
    volumeMounts:
    - name: shared-logs
      mountPath: /var/log/shared
  volumes:
  - name: shared-logs
    emptyDir: {}
EOF

# Apply the Pod configuration
kubectl apply -f ~/k8s-practice/storage/logging-pod.yaml

# Wait for the Pod to be running
kubectl wait --for=condition=Ready pod/logging-pod -n storage-exercises

# Verify logs are being generated
kubectl exec -n storage-exercises logging-pod -c log-generator -- ls -la /var/log/shared
kubectl exec -n storage-exercises logging-pod -c log-generator -- cat /var/log/shared/app.log | tail -5

# Verify logs are being processed
kubectl exec -n storage-exercises logging-pod -c log-processor -- ls -la /var/log/shared
kubectl exec -n storage-exercises logging-pod -c log-processor -- cat /var/log/shared/processed.log | tail -5

# You can also check container logs
kubectl logs -n storage-exercises logging-pod -c log-generator
kubectl logs -n storage-exercises logging-pod -c log-processor
```

---

#### Exercise 2: Working with Different Volume Access Modes

##### Scenario
You need to understand the different access modes for PersistentVolumes and how they affect your applications.

##### Tasks
1. Create PVs with different access modes (RWO, ROX, RWX)
2. Create PVCs that request specific access modes
3. Deploy Pods that use the PVCs
4. Test the access restrictions

##### Steps
```bash
# First, create directories on the node for our volumes
# Note: In a multi-node cluster, this would only work for RWO volumes
# RWX would require a proper network filesystem like NFS
sudo mkdir -p /mnt/data-rwo /mnt/data-rox /mnt/data-rwx

# Create PVs with different access modes
cat > ~/k8s-practice/storage/access-modes-pvs.yaml << EOF
apiVersion: v1
kind: PersistentVolume
metadata:
  name: pv-rwo
spec:
  capacity:
    storage: 1Gi
  accessModes:
    - ReadWriteOnce
  persistentVolumeReclaimPolicy: Recycle
  storageClassName: manual
  hostPath:
    path: /mnt/data-rwo

---
apiVersion: v1
kind: PersistentVolume
metadata:
  name: pv-rox
spec:
  capacity:
    storage: 1Gi
  accessModes:
    - ReadOnlyMany
  persistentVolumeReclaimPolicy: Recycle
  storageClassName: manual
  hostPath:
    path: /mnt/data-rox

---
apiVersion: v1
kind: PersistentVolume
metadata:
  name: pv-rwx
spec:
  capacity:
    storage: 1Gi
  accessModes:
    - ReadWriteMany
  persistentVolumeReclaimPolicy: Recycle
  storageClassName: manual
  hostPath:
    path: /mnt/data-rwx
EOF

kubectl apply -f ~/k8s-practice/storage/access-modes-pvs.yaml

# Create PVCs with matching access modes
cat > ~/k8s-practice/storage/access-modes-pvcs.yaml << EOF
apiVersion: v1
kind: PersistentVolumeClaim
metadata:
  name: pvc-rwo
  namespace: storage-exercises
spec:
  accessModes:
    - ReadWriteOnce
  resources:
    requests:
      storage: 1Gi
  storageClassName: manual

---
apiVersion: v1
kind: PersistentVolumeClaim
metadata:
  name: pvc-rox
  namespace: storage-exercises
spec:
  accessModes:
    - ReadOnlyMany
  resources:
    requests:
      storage: 1Gi
  storageClassName: manual

---
apiVersion: v1
kind: PersistentVolumeClaim
metadata:
  name: pvc-rwx
  namespace: storage-exercises
spec:
  accessModes:
    - ReadWriteMany
  resources:
    requests:
      storage: 1Gi
  storageClassName: manual
EOF

kubectl apply -f ~/k8s-practice/storage/access-modes-pvcs.yaml

# Verify the PVCs are bound
kubectl get pvc -n storage-exercises
kubectl get pv

# Create Pods that use the PVCs
cat > ~/k8s-practice/storage/rwo-pod.yaml << EOF
apiVersion: v1
kind: Pod
metadata:
  name: rwo-pod
  namespace: storage-exercises
spec:
  containers:
  - name: container
    image: nginx
    volumeMounts:
    - name: rwo-volume
      mountPath: /usr/share/nginx/html
  volumes:
  - name: rwo-volume
    persistentVolumeClaim:
      claimName: pvc-rwo
EOF

kubectl apply -f ~/k8s-practice/storage/rwo-pod.yaml

cat > ~/k8s-practice/storage/rox-pod.yaml << EOF
apiVersion: v1
kind: Pod
metadata:
  name: rox-pod
  namespace: storage-exercises
spec:
  containers:
  - name: container
    image: nginx
    volumeMounts:
    - name: rox-volume
      mountPath: /usr/share/nginx/html
      readOnly: true
  volumes:
  - name: rox-volume
    persistentVolumeClaim:
      claimName: pvc-rox
EOF

kubectl apply -f ~/k8s-practice/storage/rox-pod.yaml

cat > ~/k8s-practice/storage/rwx-pod.yaml << EOF
apiVersion: v1
kind: Pod
metadata:
  name: rwx-pod
  namespace: storage-exercises
spec:
  containers:
  - name: container
    image: nginx
    volumeMounts:
    - name: rwx-volume
      mountPath: /usr/share/nginx/html
  volumes:
  - name: rwx-volume
    persistentVolumeClaim:
      claimName: pvc-rwx
EOF

kubectl apply -f ~/k8s-practice/storage/rwx-pod.yaml

# Wait for the Pods to be running
kubectl wait --for=condition=Ready pod/rwo-pod -n storage-exercises
kubectl wait --for=condition=Ready pod/rox-pod -n storage-exercises
kubectl wait --for=condition=Ready pod/rwx-pod -n storage-exercises

# Test writing to each volume
kubectl exec -n storage-exercises rwo-pod -- sh -c 'echo "RWO test" > /usr/share/nginx/html/test.txt'
kubectl exec -n storage-exercises rox-pod -- sh -c 'echo "ROX test" > /usr/share/nginx/html/test.txt' || echo "Failed as expected - volume is read-only"
kubectl exec -n storage-exercises rwx-pod -- sh -c 'echo "RWX test" > /usr/share/nginx/html/test.txt'

# Verify the content
kubectl exec -n storage-exercises rwo-pod -- cat /usr/share/nginx/html/test.txt
kubectl exec -n storage-exercises rox-pod -- cat /usr/share/nginx/html/test.txt 2>/dev/null || echo "No file found in ROX volume"
kubectl exec -n storage-exercises rwx-pod -- cat /usr/share/nginx/html/test.txt
```

---

#### Exercise 3: Implementing Pod Topology Spread Constraints

##### Scenario
You need to deploy a highly available application that should be distributed evenly across different topology domains (nodes, zones, etc.) to ensure resilience.

##### Tasks
1. Label nodes with topology information
2. Create a Deployment with topology spread constraints
3. Verify the distribution of Pods across the topology

##### Steps
```bash
# Create a namespace for topology exercises
kubectl create namespace topology-exercises

# Label nodes with topology information
# Get list of nodes
NODES=$(kubectl get nodes -o jsonpath='{.items[*].metadata.name}')
NODE_ARRAY=($NODES)
NODE_COUNT=${#NODE_ARRAY[@]}

# If you have multiple nodes, label them with different zones
# If you have only one node, we'll simulate multiple zones on the same node
if [ "$NODE_COUNT" -gt 1 ]; then
  # Label half the nodes as zone-a and half as zone-b
  HALF_COUNT=$((NODE_COUNT / 2))
  for ((i=0; i<HALF_COUNT; i++)); do
    kubectl label node ${NODE_ARRAY[$i]} topology.kubernetes.io/zone=zone-a
  done
  for ((i=HALF_COUNT; i<NODE_COUNT; i++)); do
    kubectl label node ${NODE_ARRAY[$i]} topology.kubernetes.io/zone=zone-b
  done
else
  # With only one node, just label it as zone-a
  kubectl label node ${NODE_ARRAY[0]} topology.kubernetes.io/zone=zone-a
fi

# Verify node labels
kubectl get nodes --show-labels | grep zone

# Create a Deployment with topology spread constraints
cat > ~/k8s-practice/scheduling/topology-deployment.yaml << EOF
apiVersion: apps/v1
kind: Deployment
metadata:
  name: webapp-topology
  namespace: topology-exercises
spec:
  replicas: 6
  selector:
    matchLabels:
      app: webapp-topology
  template:
    metadata:
      labels:
        app: webapp-topology
    spec:
      topologySpreadConstraints:
      - maxSkew: 1
        topologyKey: topology.kubernetes.io/zone
        whenUnsatisfiable: DoNotSchedule
        labelSelector:
          matchLabels:
            app: webapp-topology
      - maxSkew: 1
        topologyKey: kubernetes.io/hostname
        whenUnsatisfiable: ScheduleAnyway
        labelSelector:
          matchLabels:
            app: webapp-topology
      containers:
      - name: nginx
        image: nginx:1.21
EOF

kubectl apply -f ~/k8s-practice/scheduling/topology-deployment.yaml

# Wait for the deployment
kubectl rollout status deployment/webapp-topology -n topology-exercises

# Verify the Pod distribution
kubectl get pods -n topology-exercises -o wide

# Analyze the distribution across zones
echo "Distribution across zones:"
kubectl get pods -n topology-exercises -o wide | grep -v NAME | awk '{print $7}' | sort | uniq -c

# Analyze the distribution across nodes
echo "Distribution across nodes:"
kubectl get pods -n topology-exercises -o wide | grep -v NAME | awk '{print $8}' | sort | uniq -c

# Examine a Pod's topology spread constraints
kubectl get pods -n topology-exercises -o name | head -1 | xargs kubectl describe -n topology-exercises
```

--

#### Exercise 4: Working with Pod Disruption Budgets (PDB)

##### Scenario
You have a critical application that requires high availability. You need to ensure that voluntary disruptions (like node drains or Pod evictions) don't cause service outages.

##### Tasks
1. Deploy a stateless application with multiple replicas
2. Configure a Pod Disruption Budget for the application
3. Test the Pod Disruption Budget during node maintenance

##### Steps
```bash
# Create a namespace for PDB exercises
kubectl create namespace pdb-exercises

# Create a Deployment with multiple replicas
cat > ~/k8s-practice/scheduling/ha-deployment.yaml << EOF
apiVersion: apps/v1
kind: Deployment
metadata:
  name: ha-webapp
  namespace: pdb-exercises
spec:
  replicas: 5
  selector:
    matchLabels:
      app: ha-webapp
  template:
    metadata:
      labels:
        app: ha-webapp
    spec:
      containers:
      - name: nginx
        image: nginx:1.21
        ports:
        - containerPort: 80
EOF

kubectl apply -f ~/k8s-practice/scheduling/ha-deployment.yaml

# Wait for the deployment to be ready
kubectl rollout status deployment/ha-webapp -n pdb-exercises

# Create a Pod Disruption Budget
cat > ~/k8s-practice/scheduling/webapp-pdb.yaml << EOF
apiVersion: policy/v1
kind: PodDisruptionBudget
metadata:
  name: ha-webapp-pdb
  namespace: pdb-exercises
spec:
  minAvailable: 4
  selector:
    matchLabels:
      app: ha-webapp
EOF

kubectl apply -f ~/k8s-practice/scheduling/webapp-pdb.yaml

# Verify the PDB
kubectl get pdb -n pdb-exercises
kubectl describe pdb ha-webapp-pdb -n pdb-exercises

# Simulate node maintenance by cordoning and draining a node
# First, find a node running one of our Pods
POD_NODE=$(kubectl get pods -n pdb-exercises -l app=ha-webapp -o jsonpath='{.items[0].spec.nodeName}')
echo "Cordoning node $POD_NODE"

# Cordon the node (mark it as unschedulable)
kubectl cordon $POD_NODE

# Try to evict Pods from the node
echo "Attempting to drain node $POD_NODE"
kubectl drain $POD_NODE --ignore-daemonsets --delete-emptydir-data --force

# Check the status of our Pods
kubectl get pods -n pdb-exercises -o wide

# Verify the PDB status
kubectl get pdb -n pdb-exercises

# Uncordon the node
kubectl uncordon $POD_NODE
```

---

#### Exercise 5: Implementing Pod Priority and Preemption

##### Scenario
You have different types of workloads with varying levels of importance. You need to ensure that high-priority workloads get scheduled even when the cluster is under resource pressure.

##### Tasks
1. Create PriorityClasses for different priority levels
2. Deploy Pods with different priorities
3. Test preemption by creating resource pressure

##### Steps
```bash
# Create a namespace for priority exercises
kubectl create namespace priority-exercises

# Create PriorityClasses
cat > ~/k8s-practice/scheduling/priority-classes.yaml << EOF
apiVersion: scheduling.k8s.io/v1
kind: PriorityClass
metadata:
  name: high-priority
value: 1000000
globalDefault: false
description: "This priority class should be used for high priority service pods only."
---
apiVersion: scheduling.k8s.io/v1
kind: PriorityClass
metadata:
  name: medium-priority
value: 100000
globalDefault: false
description: "This priority class should be used for medium priority service pods."
---
apiVersion: scheduling.k8s.io/v1
kind: PriorityClass
metadata:
  name: low-priority
value: 10000
globalDefault: true
description: "This priority class should be used for low priority service pods."
EOF

kubectl apply -f ~/k8s-practice/scheduling/priority-classes.yaml

# Verify PriorityClasses
kubectl get priorityclasses

# Create a low-priority deployment that consumes resources
cat > ~/k8s-practice/scheduling/low-priority-deployment.yaml << EOF
apiVersion: apps/v1
kind: Deployment
metadata:
  name: low-priority-app
  namespace: priority-exercises
spec:
  replicas: 10
  selector:
    matchLabels:
      app: low-priority-app
  template:
    metadata:
      labels:
        app: low-priority-app
    spec:
      priorityClassName: low-priority
      containers:
      - name: nginx
        image: nginx
        resources:
          requests:
            memory: "100Mi"
            cpu: "100m"
          limits:
            memory: "200Mi"
            cpu: "200m"
EOF

kubectl apply -f ~/k8s-practice/scheduling/low-priority-deployment.yaml

# Wait for the deployment
kubectl rollout status deployment/low-priority-app -n priority-exercises

# Create a high-priority Pod with significant resource requests
cat > ~/k8s-practice/scheduling/high-priority-pod.yaml << EOF
apiVersion: v1
kind: Pod
metadata:
  name: high-priority-pod
  namespace: priority-exercises
spec:
  priorityClassName: high-priority
  containers:
  - name: nginx
    image: nginx
    resources:
      requests:
        memory: "500Mi"
        cpu: "500m"
      limits:
        memory: "1Gi"
        cpu: "1"
EOF

kubectl apply -f ~/k8s-practice/scheduling/high-priority-pod.yaml

# Watch what happens to the Pods
kubectl get pods -n priority-exercises -o wide -w
# (Press Ctrl+C after observing for a while)

# Check which Pods were preempted
kubectl get events -n priority-exercises | grep -i preempt

# Check the status of the high-priority Pod
kubectl describe pod high-priority-pod -n priority-exercises
```

---

#### Exercise 6: Using Ephemeral Volumes for Temporary Storage

##### Scenario
You need to provide scratch space for an application that requires more temporary storage than the container's writable layer can offer, without persisting the data beyond the Pod's lifecycle.

##### Tasks
1. Create a Pod with an ephemeral volume
2. Store and retrieve data from the ephemeral volume
3. Verify the data is lost when the Pod is deleted

##### Steps
```bash
# Create a namespace for ephemeral volume exercises
kubectl create namespace ephemeral-exercises

# Create a Pod with an emptyDir volume with a size limit
cat > ~/k8s-practice/storage/ephemeral-pod.yaml << EOF
apiVersion: v1
kind: Pod
metadata:
  name: ephemeral-pod
  namespace: ephemeral-exercises
spec:
  containers:
  - name: main-container
    image: ubuntu
    command: ["sleep", "3600"]
    volumeMounts:
    - name: scratch-volume
      mountPath: /scratch
  volumes:
  - name: scratch-volume
    emptyDir:
      sizeLimit: 500Mi  # Limit the size of the volume
EOF

kubectl apply -f ~/k8s-practice/storage/ephemeral-pod.yaml

# Wait for the Pod to be running
kubectl wait --for=condition=Ready pod/ephemeral-pod -n ephemeral-exercises

# Store data in the ephemeral volume
kubectl exec -n ephemeral-exercises ephemeral-pod -- sh -c 'dd if=/dev/zero of=/scratch/testfile bs=1M count=100'
kubectl exec -n ephemeral-exercises ephemeral-pod -- ls -lh /scratch/testfile

# Verify the data exists
kubectl exec -n ephemeral-exercises ephemeral-pod -- sh -c 'ls -la /scratch'

# Delete the Pod
kubectl delete pod ephemeral-pod -n ephemeral-exercises

# Recreate the Pod
kubectl apply -f ~/k8s-practice/storage/ephemeral-pod.yaml

# Wait for the Pod to be running
kubectl wait --for=condition=Ready pod/ephemeral-pod -n ephemeral-exercises

# Verify the data is gone
kubectl exec -n ephemeral-exercises ephemeral-pod -- sh -c 'ls -la /scratch'
```

#### Clean Up

After completing all exercises, clean up the resources to avoid unnecessary resource usage:

```bash
# Delete namespaces
kubectl delete namespace storage-exercises
kubectl delete namespace topology-exercises
kubectl delete namespace pdb-exercises
kubectl delete namespace priority-exercises
kubectl delete namespace ephemeral-exercises

# Delete PriorityClasses
kubectl delete priorityclass high-priority medium-priority low-priority

# Remove labels from nodes
kubectl label nodes --all topology.kubernetes.io/zone-

# Delete PVs
kubectl delete pv pv-rwo pv-rox pv-rwx
```
---

## Troubleshooting

### 1. Troubleshooting Clusters and Nodes

Troubleshooting Kubernetes clusters requires a systematic approach to identify and resolve issues across the distributed system. When problems occur, you need to methodically investigate the cluster's health from multiple perspectives.

#### Cluster Health Verification

The first step in troubleshooting a cluster is to verify its overall health. This includes:

**Control Plane Status**: The control plane is the brain of your Kubernetes cluster. Checking its components ensures that the cluster can properly manage workloads.

**Node Health**: Worker nodes are where your applications run. Unhealthy nodes can cause application disruptions and scheduling issues.

**API Server Accessibility**: Since all operations go through the API server, ensuring it's accessible is critical to troubleshooting efforts.

**etcd Data Store Integrity**: As the persistent store for all cluster data, etcd's health directly impacts the stability of your entire cluster.

#### Node-Level Troubleshooting

When troubleshooting node-related issues, you should investigate:

**Kubelet Status**: The kubelet is the primary node agent that ensures containers are running in a Pod. If it fails, the node cannot host workloads.

**Container Runtime Health**: Issues with container runtimes like containerd or CRI-O can prevent containers from starting or functioning correctly.

**System Resource Utilization**: CPU, memory, disk space, and I/O pressure can all affect node performance and stability.

**Operating System Issues**: Kernel parameters, file descriptor limits, network configuration, and other OS-level settings can impact node functionality.

**Certificate Problems**: Expired or invalid certificates can cause communication failures between nodes and the control plane.

#### Common Node Problems

Common problems that occur at the node level include:

**Node NotReady Status**: This indicates the kubelet is not reporting status to the API server, which can be caused by network issues, kubelet failures, or resource exhaustion.

**Unexpected Pod Evictions**: High resource utilization can trigger the kubelet to evict Pods to free up resources.

**Node Pressure Conditions**: These include DiskPressure, MemoryPressure, PIDPressure, and NetworkUnavailable, each requiring specific remediation approaches.

**Container Runtime Issues**: Problems such as image pull failures, container crash loops, or filesystem errors.

**Networking Misconfigurations**: Issues with the CNI plugin, Pod networking, or node-level firewall rules can disrupt cluster communications.

---

### 2. Troubleshooting Cluster Components

Each component in the Kubernetes control plane serves a specific purpose, and understanding their roles is essential for effective troubleshooting.

#### API Server Issues

The API server is the front-end for the Kubernetes control plane and the gateway for all REST operations.

**Common API Server Problems**:
- Connection refusals or timeouts
- Authentication and authorization failures
- Excessive latency in request handling
- Certificate expiration or misconfiguration
- Improper feature gate configuration
- Resource exhaustion (memory, CPU)

#### Controller Manager Issues

The controller manager runs controller processes that regulate the state of the cluster, such as node controller, replication controller, and endpoint controller.

**Common Controller Manager Problems**:
- Leader election failures in HA setups
- Configuration inconsistencies
- Slow reconciliation loops
- Inability to communicate with the API server
- Resource exhaustion
- Improper permissions

#### Scheduler Issues

The scheduler watches for newly created Pods with no assigned node and selects a node for them to run on.

**Common Scheduler Problems**:
- Pod stuck in "Pending" state
- Unintended node selections
- Resource calculation errors
- Affinity/anti-affinity rule issues
- Custom scheduler conflicts
- Taints and tolerations misconfiguration

#### etcd Issues

etcd is the distributed key-value store used by Kubernetes to store all cluster data.

**Common etcd Problems**:
- Split-brain scenarios in multi-node etcd clusters
- Database corruption
- Performance degradation under load
- Insufficient resources
- Network partition between etcd members
- Certificate expiration
- Disk I/O bottlenecks

#### kubelet Issues

The kubelet is an agent that runs on each node and ensures that containers are running in a Pod.

**Common kubelet Problems**:
- Failed to register node with the API server
- Container runtime interface issues
- Volume mount failures
- Pod startup delays
- Garbage collection issues
- Health check failures
- Certificate problems

#### kube-proxy Issues

kube-proxy maintains network rules on nodes to allow network communication to Pods from inside and outside the cluster.

**Common kube-proxy Problems**:
- Service connectivity issues
- IPVS or iptables mode configuration errors
- NodePort service failures
- Proxy mode inconsistencies
- Endpoint resolution problems
- Network plugin compatibility issues

---

### 3. Monitoring Cluster and Application Resource Usage

Effective monitoring is essential for both troubleshooting immediate issues and preventing future problems through proactive management.

#### Cluster-Level Monitoring

Cluster monitoring provides insights into the health and performance of the Kubernetes cluster infrastructure.

**Key Cluster Metrics**:
- Node CPU, memory, and disk usage
- Control plane component health
- API server request latency and throughput
- etcd performance metrics
- kubelet and container runtime status
- Network throughput and latency
- Persistent volume status

#### Application Resource Monitoring

Application monitoring focuses on the resource usage and performance of your workloads running in the cluster.

**Key Application Metrics**:
- Pod CPU and memory utilization
- Pod restart count and reasons
- Container startup time
- Application response latency
- Network traffic patterns
- Storage I/O operations
- Service request rates and errors

#### Resource Quotas and Limits

Understanding and properly configuring resource constraints is vital for cluster stability.

**Quota and Limit Concepts**:
- Namespace ResourceQuotas for limiting aggregate resource consumption
- LimitRanges for setting default and constraint values
- Pod resource requests and limits
- Impact of overcommitment on node stability
- Quality of Service (QoS) classes: Guaranteed, Burstable, and BestEffort
- Eviction policies and thresholds

#### Monitoring Tools and Approaches

Kubernetes provides built-in tools for basic monitoring, while ecosystem solutions offer more comprehensive capabilities.

**Built-in Monitoring Tools**:
- Kubernetes API for resource metrics
- kubectl top command for basic resource usage
- Kubernetes Events API for cluster events
- Kubernetes Dashboard for visualization

**Ecosystem Monitoring Solutions**:
- Prometheus for metrics collection and alerting
- Grafana for metrics visualization
- kube-state-metrics for cluster state metrics
- node-exporter for hardware and OS metrics
- Loki for log aggregation
- Jaeger or Zipkin for distributed tracing

---

### 4. Managing and Evaluating Container Output Streams

Effective log management is crucial for debugging applications and understanding system behavior in a Kubernetes environment.

#### Container Logging Architecture

Understanding how logs flow in Kubernetes helps troubleshoot logging-related issues effectively.

**Logging Flow**:
- Application writes to stdout/stderr
- Container runtime captures output
- kubelet makes logs available via the Kubernetes API
- Optional cluster-level log aggregation systems collect and store logs

#### Accessing Container Logs

Kubernetes provides multiple methods to access container logs, each with different capabilities.

**Log Access Methods**:
- kubectl logs command for direct access to container logs
- Kubernetes API for programmatic log retrieval
- Log rotation and limits to prevent disk exhaustion
- Access to previous container logs when containers restart
- Multi-container pod log access

#### Structured Logging and Log Formats

Properly formatted logs are easier to parse, filter, and analyze.

**Log Format Considerations**:
- JSON structured logging for machine parsing
- Log levels for differentiating importance
- Timestamp and correlation ID inclusion
- Container-specific log contexts
- Application-specific log formats

#### Log Aggregation and Analysis

In production environments, centralized logging systems are essential for effective troubleshooting.

**Aggregation Solutions**:
- Elasticsearch, Fluentd/Fluent Bit, and Kibana (EFK stack)
- Loki with Grafana
- Cloud provider logging solutions (CloudWatch, Stackdriver, etc.)
- Log search and filtering capabilities
- Log retention policies and storage considerations

---

### 5. Troubleshooting Services and Networking

Kubernetes networking is complex, with multiple layers that can cause issues. Understanding these layers is key to effective troubleshooting.

#### Pod Networking Issues

Pod networking provides the foundation for application connectivity.

**Common Pod Networking Problems**:
- Pod-to-Pod communication failures
- DNS resolution issues
- CNI plugin misconfiguration
- MTU mismatches
- Network policy restrictions
- IP address exhaustion
- Cross-node communication failures

#### Service Discovery and Resolution

Services provide stable endpoints for pods, but they can encounter various issues.

**Common Service Issues**:
- Service not routing traffic to pods
- Endpoint selection problems based on label selectors
- kube-proxy configuration or operation issues
- Service CIDR configuration problems
- Service port misconfigurations
- ClusterIP, NodePort, and LoadBalancer type-specific issues
- External name resolution failures

#### Ingress Controllers and Routing

Ingress resources manage external access to services, adding another layer of complexity.

**Common Ingress Issues**:
- Ingress controller deployment problems
- Ingress resource configuration errors
- TLS certificate issues
- Path-based routing failures
- Backend service connectivity problems
- Host-based routing misconfiguration
- Annotations for specific ingress controller features

#### Network Policies

Network Policies provide security controls for pod communication, but can also cause connectivity issues when misconfigured.

**Common Network Policy Issues**:
- Overly restrictive policies blocking legitimate traffic
- Missing ingress or egress rules
- Incorrect pod selector matching
- Namespace selector misconfiguration
- CIDR range specification errors
- Interaction between multiple network policies
- Network policy controller deployment issues

#### CoreDNS and DNS Resolution

DNS is critical for service discovery in Kubernetes but can encounter various problems.

**Common DNS Issues**:
- CoreDNS pod failures
- DNS resolution timeouts or failures
- DNS caching issues
- Custom DNS configuration errors
- Search domain and ndots configuration problems
- Pod hostname and subdomain issues
- Service domain name format misunderstandings

#### LoadBalancer and External Connectivity

External access to cluster services can be complex to troubleshoot.

**Common External Connectivity Issues**:
- Cloud provider LoadBalancer provisioning failures
- Health check configuration for external load balancers
- NodePort access restrictions
- External IP assignment problems
- Firewall or security group configurations
- ExternalName service resolution issues
- MetalLB or other bare-metal load balancer issues

---

### Lab 1: Troubleshooting Cluster Nodes

#### Objective
Learn how to identify and resolve common issues with Kubernetes nodes, including investigating node status, checking system resources, and diagnosing kubelet problems.

#### Prerequisites
- Running Kubernetes cluster
- kubectl configured to access your cluster
- Administrative access to nodes (SSH access)

#### Step 1: Investigating Node Status

```bash
# Create a directory for our troubleshooting exercises
mkdir -p ~/k8s-labs/troubleshooting

# List all nodes and their status
kubectl get nodes

# Get detailed information about a specific node
NODE_NAME=$(kubectl get nodes -o jsonpath='{.items[0].metadata.name}')
kubectl describe node $NODE_NAME

# Check for node conditions (look for "True" vs "False" or "Unknown")
kubectl get nodes -o custom-columns=NAME:.metadata.name,STATUS:.status.conditions[*].type,CONDITION:.status.conditions[*].status

# Check Kubernetes events related to nodes
kubectl get events --field-selector involvedObject.kind=Node

# Output node resource usage statistics
kubectl top nodes
```

#### Step 2: Diagnosing Kubelet Issues

```bash
# SSH into the node (only if you have direct access to nodes)
# Alternatively, you can use a privileged debugging pod

# Create a debugging pod that runs on a specific node
cat > ~/k8s-labs/troubleshooting/node-debugger.yaml << EOF
apiVersion: v1
kind: Pod
metadata:
  name: node-debugger
spec:
  containers:
  - name: debugger
    image: nicolaka/netshoot
    command: ["sleep", "3600"]
    securityContext:
      privileged: true
  nodeName: $NODE_NAME
  hostNetwork: true
  hostPID: true
  hostIPC: true
EOF

kubectl apply -f ~/k8s-labs/troubleshooting/node-debugger.yaml

# Wait for the debugging pod to be running
kubectl wait --for=condition=Ready pod/node-debugger

# Check kubelet process status
kubectl exec node-debugger -- systemctl status kubelet

# Check kubelet logs
kubectl exec node-debugger -- journalctl -u kubelet -n 100

# Check kubelet configuration
kubectl exec node-debugger -- cat /var/lib/kubelet/config.yaml

# Verify kubelet certificates
kubectl exec node-debugger -- ls -la /var/lib/kubelet/pki/

# Check if kubelet can reach the API server
kubectl exec node-debugger -- curl -k https://kubernetes.default.svc:443/healthz
```

#### Step 3: Investigating Resource Utilization

```bash
# Check CPU, memory, and disk usage on the node
kubectl exec node-debugger -- top -b -n 1

# Check disk usage
kubectl exec node-debugger -- df -h

# Check memory usage details
kubectl exec node-debugger -- free -h

# Check for processes consuming high resources
kubectl exec node-debugger -- ps aux --sort=-%cpu | head -10
kubectl exec node-debugger -- ps aux --sort=-%mem | head -10

# Check system load
kubectl exec node-debugger -- cat /proc/loadavg

# Check if there are any disk I/O issues
kubectl exec node-debugger -- iostat -x 1 5
```

#### Step 4: Simulating and Resolving Common Node Issues

```bash
# Simulate a "NotReady" node scenario (Only do this in a test environment!)
echo "Note: This will temporarily make your node unavailable - only do this in a test environment"
echo "Press Enter to continue or Ctrl+C to abort"
read

# Option 1: Stop the kubelet service
kubectl exec node-debugger -- systemctl stop kubelet

# Verify the node status (should become NotReady after about 30-60 seconds)
kubectl get nodes
kubectl describe node $NODE_NAME

# Resolve the issue by restarting the kubelet
kubectl exec node-debugger -- systemctl start kubelet

# Verify the node returns to Ready status
kubectl get nodes -w
# (Press Ctrl+C when the node shows Ready)

# Option 2: Simulate disk pressure
echo "Simulating disk pressure..."
kubectl exec node-debugger -- mkdir -p /tmp/large-files
kubectl exec node-debugger -- dd if=/dev/zero of=/tmp/large-files/big-file bs=1M count=1000

# Check if the node reports disk pressure
kubectl describe node $NODE_NAME | grep DiskPressure

# Resolve the disk pressure issue
kubectl exec node-debugger -- rm -f /tmp/large-files/big-file
```

#### Step 5: Cleaning Up

```bash
# Delete the debugging pod
kubectl delete pod node-debugger

# Ensure the node is in a healthy state
kubectl get nodes
```

---

### Lab 2: Troubleshooting Cluster Components

#### Objective
Learn how to identify and resolve issues with Kubernetes control plane components, and understand how component failures affect cluster operations.

#### Prerequisites
- Running Kubernetes cluster
- kubectl configured to access your cluster
- Administrative access to the control plane node (for kubeadm-based clusters)

#### Step 1: Examining Control Plane Components

```bash
# List all pods in the kube-system namespace
kubectl get pods -n kube-system

# Check the status of control plane components
kubectl get pods -n kube-system -l tier=control-plane -o wide

# Create a function to quickly check control plane logs
view_cp_logs() {
  local component=$1
  local lines=${2:-50}
  local pod=$(kubectl get pods -n kube-system -l component=$component -o jsonpath='{.items[0].metadata.name}')
  echo "Viewing logs for $component ($pod)..."
  kubectl logs -n kube-system $pod --tail=$lines
}

# Check logs for each control plane component
view_cp_logs kube-apiserver
view_cp_logs kube-controller-manager
view_cp_logs kube-scheduler
view_cp_logs etcd
```

#### Step 2: Investigating API Server Issues

```bash
# Get detailed information about the API server pod
APISERVER_POD=$(kubectl get pods -n kube-system -l component=kube-apiserver -o jsonpath='{.items[0].metadata.name}')
kubectl describe pod $APISERVER_POD -n kube-system

# Check API server's health
kubectl get --raw /healthz
kubectl get --raw /healthz/etcd
kubectl get --raw /livez
kubectl get --raw /readyz

# Examine API server metrics
kubectl get --raw /metrics | grep apiserver_request_total

# Create a debugging pod on the control plane node (if running kubeadm)
CONTROL_PLANE_NODE=$(kubectl get pods -n kube-system $APISERVER_POD -o jsonpath='{.spec.nodeName}')
cat > ~/k8s-labs/troubleshooting/control-plane-debugger.yaml << EOF
apiVersion: v1
kind: Pod
metadata:
  name: control-plane-debugger
spec:
  containers:
  - name: debugger
    image: nicolaka/netshoot
    command: ["sleep", "3600"]
    securityContext:
      privileged: true
  nodeName: $CONTROL_PLANE_NODE
  hostNetwork: true
  hostPID: true
  hostIPC: true
EOF

kubectl apply -f ~/k8s-labs/troubleshooting/control-plane-debugger.yaml

# Wait for the debugging pod to be running
kubectl wait --for=condition=Ready pod/control-plane-debugger

# Check if API server manifest has correct settings (for kubeadm clusters)
kubectl exec control-plane-debugger -- cat /etc/kubernetes/manifests/kube-apiserver.yaml

# Check API server certificates
kubectl exec control-plane-debugger -- ls -la /etc/kubernetes/pki/
```

#### Step 3: Investigating etcd Issues

```bash
# Get detailed information about the etcd pod
ETCD_POD=$(kubectl get pods -n kube-system -l component=etcd -o jsonpath='{.items[0].metadata.name}')
kubectl describe pod $ETCD_POD -n kube-system

# Check etcd health using etcdctl
kubectl exec -n kube-system $ETCD_POD -- etcdctl --cacert /etc/kubernetes/pki/etcd/ca.crt \
  --cert /etc/kubernetes/pki/etcd/server.crt \
  --key /etc/kubernetes/pki/etcd/server.key \
  endpoint health

# Check etcd member list
kubectl exec -n kube-system $ETCD_POD -- etcdctl --cacert /etc/kubernetes/pki/etcd/ca.crt \
  --cert /etc/kubernetes/pki/etcd/server.crt \
  --key /etc/kubernetes/pki/etcd/server.key \
  member list

# Check etcd disk usage
kubectl exec -n kube-system $ETCD_POD -- etcdctl --cacert /etc/kubernetes/pki/etcd/ca.crt \
  --cert /etc/kubernetes/pki/etcd/server.crt \
  --key /etc/kubernetes/pki/etcd/server.key \
  endpoint status -w table
```

#### Step 4: Resolving Controller Manager and Scheduler Issues

```bash
# Get information about the controller manager
CONTROLLER_POD=$(kubectl get pods -n kube-system -l component=kube-controller-manager -o jsonpath='{.items[0].metadata.name}')
kubectl describe pod $CONTROLLER_POD -n kube-system

# Check controller manager logs
kubectl logs -n kube-system $CONTROLLER_POD

# Get information about the scheduler
SCHEDULER_POD=$(kubectl get pods -n kube-system -l component=kube-scheduler -o jsonpath='{.items[0].metadata.name}')
kubectl describe pod $SCHEDULER_POD -n kube-system

# Check scheduler logs
kubectl logs -n kube-system $SCHEDULER_POD

# For kubeadm clusters, you can check manifest files
kubectl exec control-plane-debugger -- cat /etc/kubernetes/manifests/kube-controller-manager.yaml
kubectl exec control-plane-debugger -- cat /etc/kubernetes/manifests/kube-scheduler.yaml
```

#### Step 5: Simulating and Resolving Control Plane Issues (for kubeadm clusters)

```bash
# IMPORTANT: Only perform these steps in a test environment!
echo "Note: This will temporarily disrupt your control plane - only do this in a test environment"
echo "Press Enter to continue or Ctrl+C to abort"
read

# Simulate API server failure by moving its manifest
kubectl exec control-plane-debugger -- mv /etc/kubernetes/manifests/kube-apiserver.yaml /tmp/

# Wait for the API server to go down (the command should eventually fail)
kubectl get pods -n kube-system

# Restore the API server
kubectl exec control-plane-debugger -- mv /tmp/kube-apiserver.yaml /etc/kubernetes/manifests/

# Wait for the API server to recover
echo "Waiting for API server to recover..."
sleep 30
kubectl get pods -n kube-system
```

#### Step 6: Cleaning Up

```bash
# Delete the debugging pod
kubectl delete pod control-plane-debugger

# Ensure all control plane components are running
kubectl get pods -n kube-system -l tier=control-plane
```

---

### Lab 3: Monitoring and Resource Management

#### Objective
Learn how to monitor resource usage in a Kubernetes cluster, understand resource constraints, and troubleshoot resource-related issues.

#### Prerequisites
- Running Kubernetes cluster
- kubectl configured to access your cluster
- metrics-server installed (if not installed, we'll install it)

#### Step 1: Setting Up Monitoring Tools

```bash
# Check if metrics-server is installed
kubectl get deployments -n kube-system metrics-server 2>/dev/null || echo "metrics-server not found"

# If metrics-server is not installed, install it
if ! kubectl get deployments -n kube-system metrics-server 2>/dev/null; then
  echo "Installing metrics-server..."
  kubectl apply -f https://github.com/kubernetes-sigs/metrics-server/releases/latest/download/components.yaml
  
  # Wait for metrics-server to be ready
  kubectl rollout status deployment metrics-server -n kube-system
fi

# Verify metrics-server is working
kubectl top nodes || echo "Waiting for metrics-server to collect data..."
sleep 15
kubectl top nodes
```

#### Step 2: Monitoring Node and Pod Resources

```bash
# Create a namespace for our monitoring exercise
kubectl create namespace monitoring-demo

# Deploy resource-consuming pods
cat > ~/k8s-labs/troubleshooting/resource-consumer.yaml << EOF
apiVersion: apps/v1
kind: Deployment
metadata:
  name: resource-consumer
  namespace: monitoring-demo
spec:
  replicas: 3
  selector:
    matchLabels:
      app: resource-consumer
  template:
    metadata:
      labels:
        app: resource-consumer
    spec:
      containers:
      - name: stress
        image: polinux/stress
        resources:
          requests:
            memory: "50Mi"
            cpu: "100m"
          limits:
            memory: "100Mi"
            cpu: "200m"
        command: ["stress"]
        args: ["--cpu", "1", "--vm", "1", "--vm-bytes", "50M", "--timeout", "600s"]
EOF

kubectl apply -f ~/k8s-labs/troubleshooting/resource-consumer.yaml

# Wait for pods to be running
kubectl rollout status deployment/resource-consumer -n monitoring-demo

# Monitor node resource usage
kubectl top nodes

# Monitor pod resource usage
kubectl top pods -n monitoring-demo

# Get detailed resource usage for pods
kubectl top pods -n monitoring-demo --containers

# Check resource usage trends (run multiple times)
echo "Checking resource usage trends..."
for i in {1..5}; do
  echo "Check $i:"
  kubectl top pods -n monitoring-demo
  sleep 5
done
```

#### Step 3: Understanding Resource Constraints and QoS Classes

```bash
# Deploy pods with different QoS classes
cat > ~/k8s-labs/troubleshooting/qos-pods.yaml << EOF
apiVersion: v1
kind: Pod
metadata:
  name: guaranteed-pod
  namespace: monitoring-demo
spec:
  containers:
  - name: guaranteed
    image: nginx
    resources:
      requests:
        memory: "100Mi"
        cpu: "100m"
      limits:
        memory: "100Mi"
        cpu: "100m"
---
apiVersion: v1
kind: Pod
metadata:
  name: burstable-pod
  namespace: monitoring-demo
spec:
  containers:
  - name: burstable
    image: nginx
    resources:
      requests:
        memory: "50Mi"
        cpu: "50m"
      limits:
        memory: "100Mi"
        cpu: "100m"
---
apiVersion: v1
kind: Pod
metadata:
  name: besteffort-pod
  namespace: monitoring-demo
spec:
  containers:
  - name: besteffort
    image: nginx
EOF

kubectl apply -f ~/k8s-labs/troubleshooting/qos-pods.yaml

# Wait for pods to be running
kubectl wait --for=condition=Ready pod/guaranteed-pod -n monitoring-demo
kubectl wait --for=condition=Ready pod/burstable-pod -n monitoring-demo
kubectl wait --for=condition=Ready pod/besteffort-pod -n monitoring-demo

# Check QoS classes for each pod
kubectl get pod guaranteed-pod -n monitoring-demo -o jsonpath='{.status.qosClass}'; echo
kubectl get pod burstable-pod -n monitoring-demo -o jsonpath='{.status.qosClass}'; echo
kubectl get pod besteffort-pod -n monitoring-demo -o jsonpath='{.status.qosClass}'; echo
```

#### Step 4: Working with Resource Quotas and Limits

```bash
# Create a namespace with resource quota
kubectl create namespace quota-demo

# Create a resource quota
cat > ~/k8s-labs/troubleshooting/resource-quota.yaml << EOF
apiVersion: v1
kind: ResourceQuota
metadata:
  name: compute-quota
  namespace: quota-demo
spec:
  hard:
    pods: "5"
    requests.cpu: "500m"
    requests.memory: "500Mi"
    limits.cpu: "1"
    limits.memory: "1Gi"
EOF

kubectl apply -f ~/k8s-labs/troubleshooting/resource-quota.yaml

# Check the quota status
kubectl describe resourcequota compute-quota -n quota-demo

# Create pods that fit within the quota
cat > ~/k8s-labs/troubleshooting/quota-pods.yaml << EOF
apiVersion: apps/v1
kind: Deployment
metadata:
  name: quota-test
  namespace: quota-demo
spec:
  replicas: 2
  selector:
    matchLabels:
      app: quota-test
  template:
    metadata:
      labels:
        app: quota-test
    spec:
      containers:
      - name: nginx
        image: nginx
        resources:
          requests:
            memory: "100Mi"
            cpu: "100m"
          limits:
            memory: "200Mi"
            cpu: "200m"
EOF

kubectl apply -f ~/k8s-labs/troubleshooting/quota-pods.yaml

# Check the quota usage
kubectl describe resourcequota compute-quota -n quota-demo

# Try to exceed the quota
kubectl scale deployment quota-test -n quota-demo --replicas=6

# Check if the scaling was limited by the quota
kubectl get pods -n quota-demo
kubectl describe deployment quota-test -n quota-demo
kubectl get events -n quota-demo | grep -i quota
```

#### Step 5: Troubleshooting Resource-Related Issues

```bash
# Create a pod that exceeds its memory limits
cat > ~/k8s-labs/troubleshooting/memory-hogger.yaml << EOF
apiVersion: v1
kind: Pod
metadata:
  name: memory-hogger
  namespace: monitoring-demo
spec:
  containers:
  - name: memory-hogger
    image: polinux/stress
    resources:
      requests:
        memory: "50Mi"
      limits:
        memory: "100Mi"
    command: ["stress"]
    args: ["--vm", "1", "--vm-bytes", "150M", "--vm-hang", "60"]
EOF

kubectl apply -f ~/k8s-labs/troubleshooting/memory-hogger.yaml

# Watch the pod status
kubectl get pod memory-hogger -n monitoring-demo -w
# (Wait until you see the pod restart, then press Ctrl+C)

# Check the pod events and status
kubectl describe pod memory-hogger -n monitoring-demo

# Check the container restart count
kubectl get pod memory-hogger -n monitoring-demo -o jsonpath='{.status.containerStatuses[0].restartCount}'; echo

# Check the last state termination reason
kubectl get pod memory-hogger -n monitoring-demo -o jsonpath='{.status.containerStatuses[0].lastState.terminated.reason}'; echo
```

#### Step 6: Cleaning Up

```bash
# Delete the namespaces and resources
kubectl delete namespace monitoring-demo
kubectl delete namespace quota-demo
```

---

### Lab 4: Troubleshooting Application Logs and Container Output

#### Objective
Learn how to access, analyze, and troubleshoot application logs and container output streams in Kubernetes.

#### Prerequisites
- Running Kubernetes cluster
- kubectl configured to access your cluster

#### Step 1: Basic Log Access and Analysis

```bash
# Create a namespace for our logging exercises
kubectl create namespace logging-demo

# Deploy a simple application that generates logs
cat > ~/k8s-labs/troubleshooting/logging-app.yaml << EOF
apiVersion: apps/v1
kind: Deployment
metadata:
  name: logging-app
  namespace: logging-demo
spec:
  replicas: 1
  selector:
    matchLabels:
      app: logging-app
  template:
    metadata:
      labels:
        app: logging-app
    spec:
      containers:
      - name: counter
        image: busybox
        command: ["/bin/sh", "-c"]
        args:
        - >
          i=0;
          while true;
          do
            echo "$(date) - INFO: Counter: $i";
            if [ $((i % 10)) -eq 0 ]; then
              echo "$(date) - ERROR: Simulated error at count $i" >&2;
            fi
            i=$((i+1));
            sleep 1;
          done
EOF

kubectl apply -f ~/k8s-labs/troubleshooting/logging-app.yaml

# Wait for the pod to be running
kubectl rollout status deployment/logging-app -n logging-demo

# Get the pod name
LOGGING_POD=$(kubectl get pods -n logging-demo -l app=logging-app -o jsonpath='{.items[0].metadata.name}')

# View the most recent logs
kubectl logs -n logging-demo $LOGGING_POD

# Follow the logs in real-time
kubectl logs -n logging-demo $LOGGING_POD -f
# (Press Ctrl+C after a few seconds)

# View only error logs
kubectl logs -n logging-demo $LOGGING_POD | grep ERROR

# View logs with timestamps
kubectl logs -n logging-demo $LOGGING_POD --timestamps

# Specify the number of lines to show
kubectl logs -n logging-demo $LOGGING_POD --tail=20
```

#### Step 2: Working with Multi-Container Pods

```bash
# Deploy a pod with multiple containers
cat > ~/k8s-labs/troubleshooting/multi-container-pod.yaml << EOF
apiVersion: v1
kind: Pod
metadata:
  name: multi-container-pod
  namespace: logging-demo
spec:
  containers:
  - name: web
    image: nginx
    ports:
    - containerPort: 80
  - name: logger
    image: busybox
    command: ["/bin/sh", "-c"]
    args:
    - >
      while true;
      do
        echo "$(date) - Logger container is running";
        sleep 5;
      done
EOF

kubectl apply -f ~/k8s-labs/troubleshooting/multi-container-pod.yaml

# Wait for the pod to be running
kubectl wait --for=condition=Ready pod/multi-container-pod -n logging-demo

# View logs from a specific container
kubectl logs -n logging-demo multi-container-pod -c web
kubectl logs -n logging-demo multi-container-pod -c logger

# Follow logs from multiple containers
kubectl logs -n logging-demo multi-container-pod --all-containers=true -f
# (Press Ctrl+C after a few seconds)
```

#### Step 3: Troubleshooting Container Startup Issues

```bash
# Deploy a pod with a startup problem
cat > ~/k8s-labs/troubleshooting/startup-problem.yaml << EOF
apiVersion: v1
kind: Pod
metadata:
  name: startup-problem
  namespace: logging-demo
spec:
  containers:
  - name: nginx
    image: nginx
    command: ["/bin/sh", "-c"]
    args:
    - >
      echo "Starting up...";
      echo "Looking for configuration...";
      cat /config/nginx.conf;
      echo "Failed to find configuration, exiting!";
      exit 1;
EOF

kubectl apply -f ~/k8s-labs/troubleshooting/startup-problem.yaml

# Check the pod status
kubectl get pod startup-problem -n logging-demo

# View logs from the failing container
kubectl logs -n logging-demo startup-problem

# Get detailed information about the pod
kubectl describe pod startup-problem -n logging-demo

# Check the container status and restart count
kubectl get pod startup-problem -n logging-demo -o jsonpath='{.status.containerStatuses[0].restartCount}'; echo

# Fix the startup problem by providing the missing configuration
cat > ~/k8s-labs/troubleshooting/startup-fixed.yaml << EOF
apiVersion: v1
kind: ConfigMap
metadata:
  name: nginx-config
  namespace: logging-demo
data:
  nginx.conf: |
    events {
      worker_connections 1024;
    }
    http {
      server {
        listen 80;
        location / {
          return 200 'Hello, Kubernetes!';
        }
      }
    }
---
apiVersion: v1
kind: Pod
metadata:
  name: startup-fixed
  namespace: logging-demo
spec:
  containers:
  - name: nginx
    image: nginx
    command: ["/bin/sh", "-c"]
    args:
    - >
      echo "Starting up...";
      echo "Looking for configuration...";
      cat /config/nginx.conf;
      echo "Found configuration, starting nginx!";
      nginx -c /config/nginx.conf -g "daemon off;";
    volumeMounts:
    - name: config-volume
      mountPath: /config
  volumes:
  - name: config-volume
    configMap:
      name: nginx-config
EOF

kubectl apply -f ~/k8s-labs/troubleshooting/startup-fixed.yaml

# Check the pod status
kubectl get pod startup-fixed -n logging-demo

# View logs from the fixed container
kubectl logs -n logging-demo startup-fixed
```

#### Step 4: Analyzing Container Crashes and Restarts

```bash
# Deploy a pod that crashes after a while
cat > ~/k8s-labs/troubleshooting/crashing-pod.yaml << EOF
apiVersion: v1
kind: Pod
metadata:
  name: crashing-pod
  namespace: logging-demo
spec:
  containers:
  - name: crasher
    image: busybox
    command: ["/bin/sh", "-c"]
    args:
    - >
      echo "Starting up...";
      for i in \$(seq 1 5); do
        echo "Running iteration \$i";
        sleep 2;
      done;
      echo "Simulating a crash now!";
      exit 1;
EOF

kubectl apply -f ~/k8s-labs/troubleshooting/crashing-pod.yaml

# Watch the pod status
kubectl get pod crashing-pod -n logging-demo -w
# (Wait until you see the pod restart a few times, then press Ctrl+C)

# View previous container logs
kubectl logs -n logging-demo crashing-pod --previous

# Get detailed information about the pod
kubectl describe pod crashing-pod -n logging-demo

# Check the container status, state, and reason
kubectl get pod crashing-pod -n logging-demo -o jsonpath='{.status.containerStatuses[0].state}'; echo
```

#### Step 5: Debugging Init Containers

```bash
# Deploy a pod with init containers
cat > ~/k8s-labs/troubleshooting/init-container-pod.yaml << EOF
apiVersion: v1
kind: Pod
metadata:
  name: init-container-pod
  namespace: logging-demo
spec:
  initContainers:
  - name: init-db-check
    image: busybox
    command: ["/bin/sh", "-c"]
    args:
    - >
      echo "Checking if database is available...";
      if nc -z database-service 3306; then
        echo "Database is available!";
        exit 0;
      else
        echo "Database is not available, failing...";
        exit 1;
      fi
  containers:
  - name: app
    image: nginx
EOF

kubectl apply -f ~/k8s-labs/troubleshooting/init-container-pod.yaml

# Check the pod status
kubectl get pod init-container-pod -n logging-demo

# View logs from the init container
kubectl logs -n logging-demo init-container-pod -c init-db-check

# Get detailed information about the pod
kubectl describe pod init-container-pod -n logging-demo

# Create the missing service to fix the init container
cat > ~/k8s-labs/troubleshooting/database-service.yaml << EOF
apiVersion: v1
kind: Service
metadata:
  name: database-service
  namespace: logging-demo
spec:
  ports:
  - port: 3306
    targetPort: 3306
  selector:
    app: mysql
---
apiVersion: v1
kind: Pod
metadata:
  name: mysql-pod
  namespace: logging-demo
  labels:
    app: mysql
spec:
  containers:
  - name: mysql
    image: mysql:5.7
    ports:
    - containerPort: 3306
    env:
    - name: MYSQL_ROOT_PASSWORD
      value: "password"
EOF

kubectl apply -f ~/k8s-labs/troubleshooting/database-service.yaml

# Delete and recreate the init container pod
kubectl delete pod init-container-pod -n logging-demo
kubectl apply -f ~/k8s-labs/troubleshooting/init-container-pod.yaml

# Watch the pod status
kubectl get pod init-container-pod -n logging-demo -w
# (Wait until the pod is Running, then press Ctrl+C)
```

#### Step 6: Cleaning Up

```bash
# Delete the namespace and resources
kubectl delete namespace logging-demo
```

---

### Lab 5: Troubleshooting Services and Networking

#### Objective
Learn how to identify and resolve common networking and service-related issues in Kubernetes.

#### Prerequisites
- Running Kubernetes cluster
- kubectl configured to access your cluster

#### Step 1: Diagnosing Service Resolution Issues

```bash
# Create a namespace for our networking exercises
kubectl create namespace networking-demo

# Deploy a simple web application
cat > ~/k8s-labs/troubleshooting/web-app.yaml << EOF
apiVersion: apps/v1
kind: Deployment
metadata:
  name: web-app
  namespace: networking-demo
spec:
  replicas: 2
  selector:
    matchLabels:
      app: web-app
  template:
    metadata:
      labels:
        app: web-app
    spec:
      containers:
      - name: nginx
        image: nginx
        ports:
        - containerPort: 80
---
apiVersion: v1
kind: Service
metadata:
  name: web-service
  namespace: networking-demo
spec:
  selector:
    app: web-app
  ports:
  - port: 80
    targetPort: 80
EOF

kubectl apply -f ~/k8s-labs/troubleshooting/web-app.yaml

# Wait for the deployment to be ready
kubectl rollout status deployment/web-app -n networking-demo

# Create a debugging pod to test service connectivity
cat > ~/k8s-labs/troubleshooting/debug-pod.yaml << EOF
apiVersion: v1
kind: Pod
metadata:
  name: debug-pod
  namespace: networking-demo
spec:
  containers:
  - name: debug-container
    image: nicolaka/netshoot
    command: ["sleep", "3600"]
EOF

kubectl apply -f ~/k8s-labs/troubleshooting/debug-pod.yaml

# Wait for the debug pod to be running
kubectl wait --for=condition=Ready pod/debug-pod -n networking-demo

# Test DNS resolution
kubectl exec -n networking-demo debug-pod -- nslookup kubernetes.default.svc.cluster.local
kubectl exec -n networking-demo debug-pod -- nslookup web-service.networking-demo.svc.cluster.local

# Test service connectivity
kubectl exec -n networking-demo debug-pod -- curl -I web-service.networking-demo.svc.cluster.local

# Check service details
kubectl get service web-service -n networking-demo
kubectl describe service web-service -n networking-demo

# Check endpoints
kubectl get endpoints web-service -n networking-demo
```

#### Step 2: Troubleshooting Service-Pod Connectivity

```bash
# Deploy a service with incorrect selector
cat > ~/k8s-labs/troubleshooting/mismatched-service.yaml << EOF
apiVersion: apps/v1
kind: Deployment
metadata:
  name: backend-app
  namespace: networking-demo
spec:
  replicas: 2
  selector:
    matchLabels:
      app: backend-app
  template:
    metadata:
      labels:
        app: backend-app
    spec:
      containers:
      - name: nginx
        image: nginx
        ports:
        - containerPort: 80
---
apiVersion: v1
kind: Service
metadata:
  name: backend-service
  namespace: networking-demo
spec:
  selector:
    app: backend  # Mismatched selector (should be backend-app)
  ports:
  - port: 80
    targetPort: 80
EOF

kubectl apply -f ~/k8s-labs/troubleshooting/mismatched-service.yaml

# Check service and endpoints
kubectl get service backend-service -n networking-demo
kubectl get endpoints backend-service -n networking-demo

# Test connectivity to the mismatched service
kubectl exec -n networking-demo debug-pod -- curl -I backend-service.networking-demo.svc.cluster.local --connect-timeout 5 || echo "Connection failed"

# Fix the service selector
kubectl patch service backend-service -n networking-demo -p '{"spec":{"selector":{"app":"backend-app"}}}'

# Verify the endpoints are now correctly populated
kubectl get endpoints backend-service -n networking-demo

# Test connectivity again
kubectl exec -n networking-demo debug-pod -- curl -I backend-service.networking-demo.svc.cluster.local
```

#### Step 3: Investigating Pod-to-Pod Communication Issues

```bash
# Create pods in different namespaces to test cross-namespace communication
kubectl create namespace secondary-namespace

# Create a pod in the secondary namespace
cat > ~/k8s-labs/troubleshooting/secondary-pod.yaml << EOF
apiVersion: v1
kind: Pod
metadata:
  name: secondary-pod
  namespace: secondary-namespace
  labels:
    app: secondary-app
spec:
  containers:
  - name: nginx
    image: nginx
    ports:
    - containerPort: 80
---
apiVersion: v1
kind: Service
metadata:
  name: secondary-service
  namespace: secondary-namespace
spec:
  selector:
    app: secondary-app
  ports:
  - port: 80
    targetPort: 80
EOF

kubectl apply -f ~/k8s-labs/troubleshooting/secondary-pod.yaml

# Wait for the pod to be running
kubectl wait --for=condition=Ready pod/secondary-pod -n secondary-namespace

# Test cross-namespace DNS resolution and connectivity
kubectl exec -n networking-demo debug-pod -- nslookup secondary-service.secondary-namespace.svc.cluster.local
kubectl exec -n networking-demo debug-pod -- curl -I secondary-service.secondary-namespace.svc.cluster.local
```

#### Step 4: Debugging Network Policies

```bash
# Create a default deny network policy
cat > ~/k8s-labs/troubleshooting/default-deny.yaml << EOF
apiVersion: networking.k8s.io/v1
kind: NetworkPolicy
metadata:
  name: default-deny-all
  namespace: networking-demo
spec:
  podSelector: {}
  policyTypes:
  - Ingress
  - Egress
EOF

kubectl apply -f ~/k8s-labs/troubleshooting/default-deny.yaml

# Test connectivity after applying the deny policy
kubectl exec -n networking-demo debug-pod -- curl -I web-service.networking-demo.svc.cluster.local --connect-timeout 5 || echo "Connection failed"
kubectl exec -n networking-demo debug-pod -- curl -I secondary-service.secondary-namespace.svc.cluster.local --connect-timeout 5 || echo "Connection failed"

# Create a policy to allow specific communication
cat > ~/k8s-labs/troubleshooting/allow-web-policy.yaml << EOF
apiVersion: networking.k8s.io/v1
kind: NetworkPolicy
metadata:
  name: allow-web-access
  namespace: networking-demo
spec:
  podSelector:
    matchLabels:
      app: web-app
  policyTypes:
  - Ingress
  ingress:
  - from:
    - podSelector: {}
    ports:
    - protocol: TCP
      port: 80
EOF

kubectl apply -f ~/k8s-labs/troubleshooting/allow-web-policy.yaml

cat > ~/k8s-labs/troubleshooting/allow-debug-egress.yaml << EOF
apiVersion: networking.k8s.io/v1
kind: NetworkPolicy
metadata:
  name: allow-debug-egress
  namespace: networking-demo
spec:
  podSelector:
    matchLabels:
      app: web-app
  policyTypes:
  - Egress
  egress:
  - to:
    - namespaceSelector: {}
    ports:
    - protocol: TCP
      port: 80
    - protocol: TCP
      port: 443
    - protocol: TCP
      port: 53
    - protocol: UDP
      port: 53
EOF

kubectl apply -f ~/k8s-labs/troubleshooting/allow-debug-egress.yaml

# Label the debug pod to match the egress policy
kubectl label pod debug-pod -n networking-demo app=web-app

# Test connectivity after applying the allow policies
kubectl exec -n networking-demo debug-pod -- curl -I web-service.networking-demo.svc.cluster.local
kubectl exec -n networking-demo debug-pod -- curl -I secondary-service.secondary-namespace.svc.cluster.local
```

#### Step 5: Troubleshooting Ingress

```bash
# Deploy an ingress controller if not already installed
# Note: This uses nginx-ingress controller, but the actual controller may vary
# based on your environment
kubectl get namespace ingress-nginx 2>/dev/null || kubectl create namespace ingress-nginx

if ! kubectl get deployment -n ingress-nginx ingress-nginx-controller 2>/dev/null; then
  echo "Installing NGINX Ingress Controller..."
  kubectl apply -f https://raw.githubusercontent.com/kubernetes/ingress-nginx/controller-v1.8.0/deploy/static/provider/cloud/deploy.yaml
  
  # Wait for the ingress controller to be ready
  kubectl wait --namespace ingress-nginx \
    --for=condition=ready pod \
    --selector=app.kubernetes.io/component=controller \
    --timeout=120s
fi

# Create an ingress resource
cat > ~/k8s-labs/troubleshooting/web-ingress.yaml << EOF
apiVersion: networking.k8s.io/v1
kind: Ingress
metadata:
  name: web-ingress
  namespace: networking-demo
  annotations:
    nginx.ingress.kubernetes.io/rewrite-target: /
spec:
  ingressClassName: nginx
  rules:
  - host: web-app.example.com
    http:
      paths:
      - path: /
        pathType: Prefix
        backend:
          service:
            name: web-service
            port:
              number: 80
EOF

kubectl apply -f ~/k8s-labs/troubleshooting/web-ingress.yaml

# Check the ingress status
kubectl get ingress -n networking-demo
kubectl describe ingress web-ingress -n networking-demo

# Test the ingress (requires external connectivity, may not work in all environments)
INGRESS_IP=$(kubectl get svc -n ingress-nginx ingress-nginx-controller -o jsonpath='{.status.loadBalancer.ingress[0].ip}')
if [ -n "$INGRESS_IP" ]; then
  curl -H "Host: web-app.example.com" http://$INGRESS_IP/
else
  echo "Ingress IP not available. If using Minikube, use 'minikube tunnel' in another terminal."
fi

# Create an ingress with a service that doesn't exist
cat > ~/k8s-labs/troubleshooting/broken-ingress.yaml << EOF
apiVersion: networking.k8s.io/v1
kind: Ingress
metadata:
  name: broken-ingress
  namespace: networking-demo
  annotations:
    nginx.ingress.kubernetes.io/rewrite-target: /
spec:
  ingressClassName: nginx
  rules:
  - host: broken.example.com
    http:
      paths:
      - path: /
        pathType: Prefix
        backend:
          service:
            name: nonexistent-service
            port:
              number: 80
EOF

kubectl apply -f ~/k8s-labs/troubleshooting/broken-ingress.yaml

# Check the ingress status
kubectl get ingress broken-ingress -n networking-demo
kubectl describe ingress broken-ingress -n networking-demo
```

#### Step 6: Troubleshooting CoreDNS

```bash
# Check CoreDNS deployment status
kubectl get deployment -n kube-system coredns
kubectl describe deployment -n kube-system coredns

# Check CoreDNS pod logs
COREDNS_POD=$(kubectl get pods -n kube-system -l k8s-app=kube-dns -o jsonpath='{.items[0].metadata.name}')
kubectl logs -n kube-system $COREDNS_POD

# Check CoreDNS ConfigMap
kubectl get configmap -n kube-system coredns -o yaml

# Test DNS resolution from a pod
kubectl exec -n networking-demo debug-pod -- nslookup kubernetes.default.svc.cluster.local
kubectl exec -n networking-demo debug-pod -- nslookup web-service.networking-demo.svc.cluster.local

# Test DNS resolution for a non-existent service
kubectl exec -n networking-demo debug-pod -- nslookup nonexistent-service.networking-demo.svc.cluster.local || echo "Not found, as expected"

# Create a custom DNS entry using a ConfigMap
cat > ~/k8s-labs/troubleshooting/custom-dns.yaml << EOF
apiVersion: v1
kind: ConfigMap
metadata:
  name: coredns-custom
  namespace: kube-system
data:
  example.server: |
    example.com:53 {
        errors
        cache 30
        forward . 8.8.8.8
    }
EOF

kubectl apply -f ~/k8s-labs/troubleshooting/custom-dns.yaml

# Restart CoreDNS to apply the custom config (only in test environments)
kubectl rollout restart deployment -n kube-system coredns

# Wait for CoreDNS to be ready
kubectl rollout status deployment -n kube-system coredns
```

#### Step 7: Cleaning Up

```bash
# Delete all the resources
kubectl delete namespace networking-demo
kubectl delete namespace secondary-namespace
```

---

### Practice Exercises

The following practice exercises build upon our troubleshooting labs to help you develop the diagnostic skills essential for the CKA exam. Each exercise presents a realistic scenario you might encounter as a Kubernetes administrator.

#### Exercise 1: Troubleshooting Failed API Server

##### Scenario
You're the Kubernetes administrator for a production cluster. Users report they can't access the cluster with kubectl commands, receiving connection refused errors. You need to diagnose and fix the issue with the API server.

##### Tasks
1. Identify whether the API server is running
2. Determine the root cause of the failure
3. Fix the issue to restore cluster functionality
4. Verify the cluster is operational again

##### Steps
```bash
# First, verify the cluster is indeed inaccessible
kubectl get nodes

# Check the API server pod specifically
# If kubectl isn't working, SSH to the control plane node
ssh user@control-plane-node

# Check if the API server pod is running (for kubeadm-based clusters)
sudo crictl ps | grep kube-apiserver

# If the API server container isn't running, check static pod manifests
ls -la /etc/kubernetes/manifests/kube-apiserver.yaml

# Check API server logs
sudo crictl logs $(sudo crictl ps -a | grep kube-apiserver | awk '{print $1}')

# Common issues to look for:
# 1. Certificate problems
sudo ls -la /etc/kubernetes/pki/apiserver*

# 2. Configuration issues in the manifest
sudo cat /etc/kubernetes/manifests/kube-apiserver.yaml

# 3. Check if etcd is running (API server depends on it)
sudo crictl ps | grep etcd
sudo crictl logs $(sudo crictl ps | grep etcd | awk '{print $1}')

# 4. Check process status at the node level
sudo systemctl status kubelet

# Fix common issues:
# If the manifest has syntax errors, correct them
sudo vi /etc/kubernetes/manifests/kube-apiserver.yaml

# If certificates are expired or corrupt, you may need to regenerate them
# For kubeadm clusters:
sudo kubeadm init phase certs apiserver

# After fixing the issue, restart the kubelet to pick up changes
sudo systemctl restart kubelet

# Verify that the API server is now running
sudo crictl ps | grep kube-apiserver

# Exit the control plane node and test from your workstation
exit
kubectl get nodes
```

---

#### Exercise 2: Troubleshooting a Deployment that Won't Scale

##### Scenario
Your application team has requested to scale a critical deployment from 3 to 10 replicas, but the scaling operation seems stuck. The deployment shows the desired count as 10, but the current count remains at 3.

##### Tasks
1. Identify why the deployment cannot scale to the requested replicas
2. Determine if it's a resource constraint, quota issue, or scheduler problem
3. Resolve the issue to allow the deployment to scale properly
4. Verify that scaling works correctly after your fix

##### Steps
```bash
# First, confirm the issue by checking the deployment
kubectl get deployment critical-app -n production

# Check the replica status and events
kubectl describe deployment critical-app -n production

# Look for events indicating why pods aren't being scheduled
kubectl get events -n production | grep -i critical-app

# Check if any pods are stuck in Pending state
kubectl get pods -n production | grep critical-app

# If pods are pending, examine one to see the exact reason
PENDING_POD=$(kubectl get pods -n production | grep critical-app | grep Pending | head -1 | awk '{print $1}')
kubectl describe pod $PENDING_POD -n production

# Check for resource constraints at the node level
kubectl get nodes
kubectl describe nodes | grep -A 5 "Allocated resources"

# Check for resource quotas at the namespace level
kubectl get resourcequota -n production
kubectl describe resourcequota -n production

# Possible solutions based on cause:

# 1. If there's a node resource constraint, add more nodes or resize existing ones
# For cloud environments:
# - Scale your node group or cluster
# - For managed K8s: Use cloud console or CLI to add nodes

# 2. If there's a quota issue, increase the quota
kubectl edit resourcequota compute-quota -n production
# Modify the spec.hard values as needed

# 3. If there's a scheduling issue due to node selectors, taints, or affinity rules
# Check the deployment's pod template:
kubectl get deployment critical-app -n production -o yaml | grep -A 20 template:

# You might need to modify node selectors, tolerations, or affinity rules:
kubectl edit deployment critical-app -n production

# 4. If there are pod disruption budgets preventing scale-down
kubectl get pdb -n production
kubectl describe pdb -n production

# After fixing the issue, check if pods are now scaling properly
kubectl get deployment critical-app -n production -w
# (Press Ctrl+C after confirming)
```

---

#### Exercise 3: Diagnosing and Fixing Container Crash Loops

##### Scenario
A newly deployed application is continuously crashing and restarting. The deployment shows all pods are running, but users can't access the application. You need to diagnose and fix the root cause of the crashes.

##### Tasks
1. Identify the crashing container(s) and the crash pattern
2. Determine the root cause by analyzing logs and container state
3. Implement a fix to address the issue
4. Verify the application runs stably after your fix

##### Steps
```bash
# First, check the status of the pods in the deployment
kubectl get pods -n application

# Look for pods with high restart counts
kubectl get pods -n application -o custom-columns=NAME:.metadata.name,STATUS:.status.phase,RESTARTS:.status.containerStatuses[0].restartCount

# Identify a problematic pod
PROBLEM_POD=$(kubectl get pods -n application | grep -v NAME | sort -rk4 | head -1 | awk '{print $1}')

# Check the pod details
kubectl describe pod $PROBLEM_POD -n application

# Check the current container logs
kubectl logs $PROBLEM_POD -n application

# If the container just restarted, check the previous container's logs
kubectl logs $PROBLEM_POD -n application --previous

# Check container startup and liveness probe configurations
kubectl get pod $PROBLEM_POD -n application -o yaml | grep -A 10 livenessProbe
kubectl get pod $PROBLEM_POD -n application -o yaml | grep -A 10 startupProbe
kubectl get pod $PROBLEM_POD -n application -o yaml | grep -A 10 readinessProbe

# Common issues to look for:
# 1. Configuration errors (missing files or environment variables)
# 2. Incorrect startup commands
# 3. Resource constraints (OOMKilled)
# 4. Incorrect image versions
# 5. Liveness/readiness probes that fail

# Sample fixes based on potential issues:

# If it's a configuration issue, create or fix a ConfigMap:
kubectl create configmap app-config -n application --from-file=config.json

# If it's a resource issue, increase limits:
kubectl edit deployment app-deployment -n application
# Modify the resources.limits section

# If it's a probe issue, modify the probe configuration:
kubectl edit deployment app-deployment -n application
# Adjust the livenessProbe or readinessProbe parameters

# If it's an image issue, update to a correct image:
kubectl set image deployment/app-deployment app=myapp:stable -n application

# After fixing, monitor the pods to ensure they're stable
kubectl get pods -n application -w
# (Press Ctrl+C after confirming stability)

# Verify application functionality
kubectl port-forward service/app-service 8080:80 -n application
# In another terminal: curl localhost:8080
```

---

#### Exercise 4: Resolving Service Connectivity Issues

##### Scenario
Applications in your cluster are reporting connection timeouts when trying to reach a backend service. The service and pods appear to be running correctly, but connectivity is failing.

##### Tasks
1. Diagnose the service connectivity issue
2. Check for issues in the service definition, endpoints, or network policies
3. Implement the necessary fixes
4. Verify connectivity is restored

##### Steps
```bash
# First, check the service configuration
kubectl get service backend-service -n application

# Examine the service details, particularly the selector and endpoints
kubectl describe service backend-service -n application

# Check if endpoints are configured correctly
kubectl get endpoints backend-service -n application

# If no endpoints are found, verify pod labels match the service selector
kubectl get pods -n application --show-labels | grep backend

# Check for network policies that might block traffic
kubectl get networkpolicy -n application
kubectl describe networkpolicy -n application

# Create a debugging pod to test connectivity
kubectl run -n application debug-pod --image=nicolaka/netshoot --restart=Never -- sleep 3600

# Wait for the pod to be ready
kubectl wait --for=condition=Ready pod/debug-pod -n application

# Test DNS resolution
kubectl exec -n application debug-pod -- nslookup backend-service
kubectl exec -n application debug-pod -- nslookup backend-service.application.svc.cluster.local

# Test direct connection to endpoints
kubectl exec -n application debug-pod -- curl -v backend-service:80
ENDPOINT_IP=$(kubectl get endpoints backend-service -n application -o jsonpath='{.subsets[0].addresses[0].ip}')
ENDPOINT_PORT=$(kubectl get endpoints backend-service -n application -o jsonpath='{.subsets[0].ports[0].port}')
kubectl exec -n application debug-pod -- curl -v $ENDPOINT_IP:$ENDPOINT_PORT

# Check kube-proxy status on the nodes
kubectl get pods -n kube-system | grep kube-proxy
PROXY_POD=$(kubectl get pods -n kube-system | grep kube-proxy | head -1 | awk '{print $1}')
kubectl logs $PROXY_POD -n kube-system

# Possible fixes based on identified issues:

# 1. If the service selector doesn't match pod labels, update the service:
kubectl patch service backend-service -n application -p '{"spec":{"selector":{"app":"backend"}}}'

# 2. If network policies are blocking traffic, create or modify a policy:
cat > ~/allow-traffic.yaml << EOF
apiVersion: networking.k8s.io/v1
kind: NetworkPolicy
metadata:
  name: allow-service-traffic
  namespace: application
spec:
  podSelector:
    matchLabels:
      app: backend
  ingress:
  - from:
    - podSelector: {}
    ports:
    - protocol: TCP
      port: 80
EOF
kubectl apply -f ~/allow-traffic.yaml

# 3. If kube-proxy has issues, restart it:
kubectl rollout restart daemonset kube-proxy -n kube-system

# After fixing, verify connectivity again
kubectl exec -n application debug-pod -- curl -v backend-service:80

# Clean up the debug pod
kubectl delete pod debug-pod -n application
```

---

#### Exercise 5: Troubleshooting Persistent Volume Claims that Won't Bind

##### Scenario
Your development team has created a StatefulSet that requires persistent storage, but the Persistent Volume Claims (PVCs) are stuck in a Pending state, preventing the application from starting properly.

##### Tasks
1. Investigate why the PVCs remain in Pending state
2. Identify issues with storage classes, persistent volumes, or claim specifications
3. Implement the necessary fixes to allow the PVCs to bind
4. Verify the StatefulSet can successfully use the storage

##### Steps
```bash
# First, check the status of the PVCs
kubectl get pvc -n development

# Examine the details of a pending PVC
PENDING_PVC=$(kubectl get pvc -n development | grep Pending | head -1 | awk '{print $1}')
kubectl describe pvc $PENDING_PVC -n development

# Check available Persistent Volumes
kubectl get pv

# Check storage classes
kubectl get storageclass
kubectl describe storageclass standard

# Check if there's a default storage class
kubectl get storageclass -o custom-columns=NAME:.metadata.name,DEFAULT:.metadata.annotations.storageclass\\.kubernetes\\.io/is-default-class

# Common issues to investigate:

# 1. No matching PVs available for the PVC
# Check the PVC access mode, storage size, and other requirements

# 2. No storage class specified and no default class exists
# 3. Storage class exists but provisioner isn't working
# 4. Volumebindingmode is set to WaitForFirstConsumer

# Possible fixes based on identified issues:

# 1. If no matching PVs exist, create a PV manually:
cat > ~/k8s-labs/troubleshooting/manual-pv.yaml << EOF
apiVersion: v1
kind: PersistentVolume
metadata:
  name: manual-pv
spec:
  capacity:
    storage: 5Gi
  accessModes:
    - ReadWriteOnce
  persistentVolumeReclaimPolicy: Retain
  storageClassName: standard
  hostPath:
    path: /mnt/data
EOF
kubectl apply -f ~/k8s-labs/troubleshooting/manual-pv.yaml

# 2. If no default storage class exists, create one or mark an existing one as default:
kubectl patch storageclass standard -p '{"metadata": {"annotations":{"storageclass.kubernetes.io/is-default-class":"true"}}}'

# 3. If the storage class provisioner isn't working, check provisioner pods:
kubectl get pods -n kube-system | grep provisioner
PROVISIONER_POD=$(kubectl get pods -n kube-system | grep provisioner | head -1 | awk '{print $1}')
kubectl logs $PROVISIONER_POD -n kube-system

# 4. If the issue is WaitForFirstConsumer binding mode, create a pod that uses the PVC:
kubectl get statefulset -n development
kubectl describe statefulset data-store -n development

# After fixing the issues, check if PVCs are now bound
kubectl get pvc -n development

# If the StatefulSet isn't automatically recovering, you might need to restart it
kubectl rollout restart statefulset data-store -n development

# Verify the pods are now running correctly
kubectl get pods -n development -l app=data-store
```

---

#### Exercise 6: Debugging Control Plane Component Failures in an HA Cluster

##### Scenario
You manage a high-availability Kubernetes cluster with multiple control plane nodes. Users report intermittent API server failures and slow response times. You need to diagnose and resolve the issues with the control plane components.

##### Tasks
1. Identify which control plane components are having problems
2. Determine if the issues affect all control plane nodes or just some
3. Diagnose the root cause of the failures
4. Implement fixes to restore full control plane functionality

##### Steps
```bash
# Get a list of all control plane nodes
kubectl get nodes -l node-role.kubernetes.io/control-plane=

# Check the status of control plane pods across all nodes
kubectl get pods -n kube-system -o wide | grep -E 'apiserver|controller|scheduler|etcd'

# Examine events related to control plane components
kubectl get events -n kube-system | grep -E 'apiserver|controller|scheduler|etcd'

# Check API server health across all control plane nodes
for node in $(kubectl get nodes -l node-role.kubernetes.io/control-plane= -o jsonpath='{.items[*].metadata.name}'); do
  echo "Checking API server on $node"
  kubectl get pods -n kube-system -o wide | grep apiserver | grep $node
done

# Check control plane component logs for errors
# For a specific API server pod:
API_POD=$(kubectl get pods -n kube-system | grep apiserver | head -1 | awk '{print $1}')
kubectl logs $API_POD -n kube-system | grep -i error

# Check etcd cluster health (critical for API server)
ETCD_POD=$(kubectl get pods -n kube-system | grep etcd | head -1 | awk '{print $1}')
kubectl exec -n kube-system $ETCD_POD -- etcdctl --cacert /etc/kubernetes/pki/etcd/ca.crt \
  --cert /etc/kubernetes/pki/etcd/server.crt --key /etc/kubernetes/pki/etcd/server.key \
  endpoint health --cluster

# Check etcd member list
kubectl exec -n kube-system $ETCD_POD -- etcdctl --cacert /etc/kubernetes/pki/etcd/ca.crt \
  --cert /etc/kubernetes/pki/etcd/server.crt --key /etc/kubernetes/pki/etcd/server.key \
  member list -w table

# Common HA cluster issues to look for:
# 1. Leader election conflicts
# 2. Etcd quorum issues
# 3. Network connectivity between control plane nodes
# 4. Certificate expiration on some nodes but not others
# 5. Resource constraints on specific nodes

# Check certificate expiration
CERT_DIR="/etc/kubernetes/pki"
for node in $(kubectl get nodes -l node-role.kubernetes.io/control-plane= -o jsonpath='{.items[*].metadata.name}'); do
  echo "Checking certificates on $node"
  # You'd need to SSH to each node to check this
  # ssh $node "sudo openssl x509 -in $CERT_DIR/apiserver.crt -text -noout | grep -A2 Validity"
done

# Check for leader election status
kubectl get endpoints -n kube-system kube-scheduler -o yaml
kubectl get endpoints -n kube-system kube-controller-manager -o yaml

# Remediation steps based on identified issues:

# 1. If a specific control plane node is problematic, cordon and drain it:
kubectl cordon control-plane-2
kubectl drain control-plane-2 --ignore-daemonsets

# 2. For etcd member issues, you might need to remove and re-add the problematic member:
# First, get the member ID to remove
MEMBER_ID=$(kubectl exec -n kube-system $ETCD_POD -- etcdctl --cacert /etc/kubernetes/pki/etcd/ca.crt \
  --cert /etc/kubernetes/pki/etcd/server.crt --key /etc/kubernetes/pki/etcd/server.key \
  member list | grep control-plane-2 | cut -d',' -f1)

# Remove the problematic etcd member
kubectl exec -n kube-system $ETCD_POD -- etcdctl --cacert /etc/kubernetes/pki/etcd/ca.crt \
  --cert /etc/kubernetes/pki/etcd/server.crt --key /etc/kubernetes/pki/etcd/server.key \
  member remove $MEMBER_ID

# 3. For certificate issues, renew certificates:
# On the problematic node:
# sudo kubeadm certs renew all

# 4. If resource constraints are the issue, check and adjust limits:
kubectl top nodes

# After implementing fixes, verify control plane health
kubectl get pods -n kube-system -o wide | grep -E 'apiserver|controller|scheduler|etcd'

# Check API server performance
time kubectl get nodes
```

---

## Mock Exams & Exam Strategy

### Understanding the CKA Exam Format

The Certified Kubernetes Administrator (CKA) exam is a hands-on, performance-based test that assesses your ability to perform the tasks of a Kubernetes administrator. Understanding the exam format is crucial for effective preparation.

#### Exam Structure

The CKA exam consists of a series of performance-based tasks that must be completed within a 2-hour timeframe. These tasks involve managing real Kubernetes clusters through the command line interface. Unlike traditional multiple-choice exams, the CKA requires you to solve actual problems by implementing solutions in live environments.

The exam includes approximately 15-20 questions of varying difficulty and point values. Questions are weighted differently based on their complexity, with more challenging tasks carrying higher point values. The questions cover the full range of topics in the CKA curriculum, with particular emphasis on troubleshooting (30%), cluster architecture (25%), and services/networking (20%).

You will work in a browser-based terminal environment with access to multiple clusters. Each question specifies which cluster to use, and you must ensure you're working in the correct context for each task.

#### Available Resources During the Exam

During the exam, you have access to:

- The Kubernetes documentation website (https://kubernetes.io/docs)
- The Kubernetes GitHub repository (https://github.com/kubernetes/)
- The kubectl cheat sheet
- The kubectl reference documentation

You cannot access other external resources, personal notes, or additional browser tabs beyond those provided. However, the official documentation should be sufficient for any reference needs during the exam.

#### Passing Score and Certification

The CKA exam requires a passing score of 66%. This means you need to correctly complete enough tasks to earn at least 66% of the total possible points. The certification is valid for three years from the date of certification.

---

### Time Management Strategies

Effective time management is critical for success in the CKA exam, given the 2-hour time constraint and the number of tasks to complete.

#### Task Prioritization

Begin by quickly reviewing all questions to understand their complexity and point values. Prioritize tasks based on:

1. Point value - Start with higher-value questions to maximize your score
2. Difficulty level - Complete easier tasks first to build confidence and secure points
3. Familiarity - Tackle questions on topics you're most comfortable with first

This approach ensures you accumulate as many points as possible within the time constraints. If you encounter a particularly challenging question, it's sometimes better to temporarily skip it and return later rather than spend too much time on a single task.

#### Time Allocation

Allocate your time based on the weight of each question. As a general guideline:

- For a 4% question, spend no more than 5 minutes
- For an 8% question, allocate 10 minutes
- For a 12% question, dedicate 15 minutes

This proportional allocation helps ensure you have enough time to attempt all questions. Set a mental timer for each question, and if you exceed your allocated time, consider moving on and returning later if time permits.

#### Using Bookmarks Effectively

The exam interface allows you to bookmark questions for later review. Use this feature to mark:

- Questions you decide to skip temporarily
- Tasks you've completed but want to double-check
- Complex questions where you've implemented a solution but aren't entirely confident

In the last 15 minutes of the exam, return to your bookmarked questions to ensure you haven't missed any tasks and to verify your solutions.

---

### Command Line Efficiency Techniques

Mastering kubectl and Linux command line techniques will significantly improve your speed and accuracy during the exam.

#### kubectl Command Shortcuts

Become familiar with these time-saving shortcuts:

- Use aliases: `k` instead of `kubectl` (often pre-configured in the exam environment)
- Use shorthand resource names: `po` for pods, `svc` for services, `deploy` for deployments
- Leverage the `-o` output flag with various formats like `yaml`, `json`, `wide`, `name`
- Use `--dry-run=client -o yaml` to generate resource manifests quickly
- Master `kubectl explain` for quick field reference

#### YAML Generation Techniques

Creating YAML manifests efficiently is essential for many exam tasks:

1. Generate template YAML files with the imperative commands:
   ```bash
   kubectl create deployment nginx --image=nginx --dry-run=client -o yaml > deployment.yaml
   ```

2. Use existing resources as templates:
   ```bash
   kubectl get deployment existing-deploy -o yaml > new-deploy.yaml
   ```

3. Use kubectl explain to verify field requirements:
   ```bash
   kubectl explain deployment.spec.template.spec.containers
   ```

4. Leverage shell history to recall and modify previous commands

#### Efficient Editing with Vim

The exam environment provides vim as the primary text editor. Knowing these vim commands will save valuable time:

- Basic navigation: `h` (left), `j` (down), `k` (up), `l` (right)
- Quick operations: `dd` (delete line), `yy` (copy line), `p` (paste)
- Search: `/search_term` then `n` for next occurrence
- Search and replace: `:%s/old/new/g` to replace all occurrences
- Save and exit: `:wq`
- Exit without saving: `:q!`
- Go to line number: `:line_number`

#### Multi-cluster Management

The exam involves working with multiple clusters. Master these techniques:

- Check the current context: `kubectl config current-context`
- List all contexts: `kubectl config get-contexts`
- Switch contexts: `kubectl config use-context context_name`
- Create temporary aliases for different contexts:
  ```bash
  alias k1='kubectl --context=cluster1'
  alias k2='kubectl --context=cluster2'
  ```

---

### Common Exam Scenarios and Approaches

Understanding typical exam scenarios and developing systematic approaches will help you tackle tasks efficiently.

#### Troubleshooting Methodology

Develop a structured approach to troubleshooting issues:

1. Identify the problem by checking resource status:
   ```bash
   kubectl get all -n namespace
   kubectl describe resource resource_name
   kubectl logs pod_name
   ```

2. Examine related resources that could impact the issue (services, network policies, etc.)

3. Check events for clues:
   ```bash
   kubectl get events -n namespace --sort-by='.lastTimestamp'
   ```

4. Verify configurations and relationships between components

5. Implement your solution incrementally, testing at each step

#### Cluster Setup Approach

For cluster installation and configuration tasks:

1. Review requirements carefully, noting specific versions, networking plugins, etc.

2. Use kubeadm config files when possible for repeatable configurations

3. Follow a checklist approach:
   - Initialize control plane with proper configurations
   - Install networking plugin
   - Join worker nodes
   - Verify cluster status
   - Apply required add-ons or configurations

4. Test the setup by deploying a simple workload

#### Application Deployment Strategy

When deploying applications:

1. Determine the appropriate workload controller (Deployment, StatefulSet, DaemonSet)

2. Generate the basic YAML template using imperative commands

3. Modify the template to add required configurations:
   - Resource requests and limits
   - Environment variables or ConfigMaps
   - Persistent storage if needed
   - Service definitions
   - Network policies

4. Apply the configurations and verify functionality

5. Troubleshoot any issues using logs and describe commands

---

### Exam Day Preparation

Proper preparation immediately before and during the exam can significantly impact your performance.

#### Technical Setup

1. Ensure a stable internet connection, preferably wired

2. Use a computer with adequate resources (minimum 4GB RAM, modern processor)

3. Configure a quiet, distraction-free environment

4. Have a backup device and internet connection available if possible

5. Test your webcam, microphone, and screen sharing capabilities beforehand

#### Mental Preparation

1. Get adequate rest the night before the exam

2. Review key concepts and commands, but avoid cramming new material

3. Practice with a full-length mock exam under timed conditions

4. Develop a positive mindset and confidence in your preparation

5. Plan to arrive at your exam setup 15 minutes early to complete proctoring procedures

#### During the Exam

1. Stay calm if you encounter difficult questions; remember your strategy to prioritize and allocate time

2. Use the notepad feature to track your progress and remember which questions you've bookmarked

3. Take short 30-second breaks if needed to maintain focus and reduce stress

4. Double-check your work, especially context switching between clusters

5. Submit your exam once complete or when time is nearly expired

This comprehensive understanding of the exam format, time management strategies, command efficiency techniques, and structured approaches to common scenarios will position you for success on the CKA exam. Next, we'll proceed with a full-length mock exam to apply these concepts in practice.

---

### Full-Length Mock Exam

#### Instructions

This mock exam simulates the actual CKA exam format and difficulty level. It consists of 15 questions covering all domains of the curriculum. The total point value is 100%, and you need 66% to pass.

Time: 2 hours
Passing Score: 66%

For maximum benefit:
1. Set up a timer for 2 hours
2. Work through the questions in a real Kubernetes environment if possible
3. Use only the officially allowed documentation resources
4. Record which questions you complete and which you bookmark
5. After completing the exam, review your answers and understand any mistakes

#### Question 1: Cluster Upgrade (8%)

**Task**: You have a Kubernetes cluster running version 1.24.0 that needs to be upgraded to version 1.25.0. The cluster consists of a control plane node named `cp-node` and two worker nodes named `worker-1` and `worker-2`. Perform the upgrade with minimal disruption to the workloads.

#### Question 2: Troubleshooting Control Plane (8%)

**Task**: The API server on the cluster `k8s-cluster-2` is not functioning properly. Users are unable to deploy new workloads. Identify the issue and fix it to restore full functionality.

#### Question 3: Storage Configuration (6%)

**Task**: Create a new StorageClass named `fast-storage` with the provisioner `kubernetes.io/no-provisioner` and volumeBindingMode set to `WaitForFirstConsumer`. Then create a 2Gi Persistent Volume (PV) with the name `pv-fast` that uses this StorageClass. The PV should use a hostPath of `/mnt/fast-data` and have AccessMode ReadWriteOnce. Finally, create a PersistentVolumeClaim named `pvc-fast` in the namespace `project-tiger` that requests 1Gi from this StorageClass.

#### Question 4: Pod Troubleshooting (7%)

**Task**: A Pod named `web-app` in the `production` namespace is showing as `CrashLoopBackOff`. Investigate the issue and fix it so that the Pod runs properly. The Pod should be running an nginx container on port 80.

#### Question 5: Network Policy (6%)

**Task**: Create a NetworkPolicy named `db-policy` in the namespace `project-snake` that allows Pods with the label `role=frontend` to connect to Pods with the label `role=db` only on port 3306. The policy should also allow all outbound traffic from the database pods.

#### Question 6: Multi-Container Pod (6%)

**Task**: Create a Pod named `sidecar-pod` in the namespace `project-tiger` with two containers. The first container, named `main`, should use the `nginx` image and expose port 80. The second container, named `logger`, should use the `busybox` image and run the command `sh -c "while true; do echo 'Logging at $(date)' >> /var/log/output.log; sleep 10; done"`. Both containers should mount a shared volume named `log-volume` at `/var/log`.

#### Question 7: Service Account Configuration (5%)

**Task**: Create a new ServiceAccount named `deployment-sa` in the namespace `project-ram`. Then, create a ClusterRole named `deployment-manager` that allows creating, listing, and updating deployments. Create a RoleBinding in the namespace `project-ram` that binds the ClusterRole to the ServiceAccount. Finally, create a Pod named `deploy-manager` in the namespace `project-ram` that uses this ServiceAccount, with the image `bitnami/kubectl`.

#### Question 8: Pod Scheduling (7%)

**Task**: Create a Deployment named `frontend` in the namespace `project-tiger` with 3 replicas, using the image `nginx`. The Pods should be scheduled on nodes with the label `disk=ssd`. Additionally, configure the Pods to have a node anti-affinity rule that prevents multiple Pods from the deployment from running on the same node.

#### Question 9: Cluster Backup and Restore (8%)

**Task**: Perform a backup of the etcd database on the cluster and save it to `/opt/etcd-backup.db`. Then simulate a failure by stopping the etcd service. Restore the etcd database from the backup file and ensure the cluster is functioning properly.

#### Question 10: Service Configuration (6%)

**Task**: A Deployment named `web-server` is running in the namespace `project-snake` with 3 replicas. Create a Service named `web-service` that exposes the deployment on port 80 using a ClusterIP. Then create an additional Service named `web-nodeport` that exposes the same deployment using a NodePort on port 32000.

#### Question 11: Log Analysis (7%)

**Task**: Analyze the logs for the Pod `api-server` in the namespace `project-lion`. Find all ERROR level log entries and save them to the file `/opt/api-errors.log`. Then identify the most common error message and create a new ConfigMap named `error-config` in the namespace `project-lion` with the data `most-common-error: <error-message>`.

#### Question 12: Resource Quota Management (6%)

**Task**: Create a ResourceQuota named `project-quota` in the namespace `project-tiger` with the following constraints: pods=10, requests.cpu=2, requests.memory=2Gi, limits.cpu=4, limits.memory=4Gi. Then create a LimitRange named `default-limits` in the same namespace with default request values of cpu=100m and memory=256Mi, and default limit values of cpu=200m and memory=512Mi.

#### Question 13: Persistent Volume Configuration (7%)

**Task**: The development team has requested persistent storage for a new database application. Create a PersistentVolume named `db-pv` with capacity of 5Gi, using hostPath storage at `/mnt/db-data`. It should use the ReadWriteOnce access mode. Then create a PersistentVolumeClaim named `db-pvc` in the namespace `project-snake` that requests 3Gi from this PersistentVolume. Finally, create a Pod named `db-pod` in the namespace `project-snake` that uses the `mysql:5.7` image and mounts the PersistentVolumeClaim at `/var/lib/mysql`. Set the environment variable `MYSQL_ROOT_PASSWORD` to `password`.

#### Question 14: Cluster Node Management (7%)

**Task**: One of your worker nodes, `worker-1`, needs maintenance. Safely drain the node to ensure that workloads are moved to other nodes. After the maintenance is completed (simulated), make the node schedulable again. During the process, ensure that Pods without PersistentVolumeClaims are rescheduled to other nodes.

#### Question 15: Troubleshooting Pod Networking (6%)

**Task**: Pods in the namespace `project-cobra` are unable to communicate with the service `auth-service` in the namespace `project-tiger`. Investigate the issue and fix the problem so that Pods in `project-cobra` can successfully connect to the service. Do not modify the service or the pods in the `project-tiger` namespace.

---

### Exam Strategies and Final Preparation

#### Effective Time Management During the Exam

The CKA exam requires not just technical knowledge but also strategic time management. Here are specific techniques to maximize your efficiency:

##### Question Triage Strategy

When you first access the exam, spend the first 5 minutes scanning all questions. Create a quick prioritization plan:

1. **First pass (60-75 minutes)**: Focus on questions that:
   - Are worth higher points
   - You can complete quickly and confidently
   - Cover fundamental topics (Pod creation, deployments, services)

2. **Second pass (30-45 minutes)**: Address:
   - Moderately difficult questions
   - Questions requiring more complex configurations
   - Tasks with multiple steps

3. **Final pass (15-20 minutes)**: Tackle:
   - The most challenging questions
   - Any remaining unattempted questions
   - Review and verification of completed work

##### Context Switching Efficiency

Moving between different clusters and contexts can be time-consuming. Optimize this process by:

1. Creating context-specific aliases at the beginning of the exam:
   ```bash
   alias kc1='kubectl --context=cluster1'
   alias kc2='kubectl --context=cluster2'
   ```

2. Completing all tasks for one context before switching to another when possible

3. Verifying your current context before starting each question:
   ```bash
   kubectl config current-context
   ```

4. Using split terminal windows if the exam interface allows it—one for each context

##### Answer Verification Protocol

Develop a consistent process to verify your solutions before moving to the next question:

1. Re-read the question requirements to ensure you've addressed all parts

2. Verify resource creation with targeted commands:
   ```bash
   kubectl get <resource> -n <namespace>
   kubectl describe <resource> <name> -n <namespace>
   ```

3. Check resource functionality when applicable (test service connectivity, pod functionality)

4. Look for common mistakes:
   - Incorrect namespace
   - Typos in resource names
   - Missing labels or selectors
   - Incorrect ports or protocols

#### Command Efficiency Mastery

Beyond basic shortcuts, these advanced techniques can save critical time during the exam:

##### Template Generation Strategies

Create a library of command templates in a notepad at the start of the exam:

1. Pod template:
   ```bash
   k run nginx --image=nginx --dry-run=client -o yaml > pod.yaml
   ```

2. Deployment template:
   ```bash
   k create deployment nginx --image=nginx --replicas=3 --dry-run=client -o yaml > deploy.yaml
   ```

3. Service template:
   ```bash
   k expose deployment nginx --port=80 --target-port=80 --dry-run=client -o yaml > svc.yaml
   ```

4. ConfigMap from literal values:
   ```bash
   k create configmap my-config --from-literal=key1=value1 --from-literal=key2=value2 --dry-run=client -o yaml > cm.yaml
   ```

5. PersistentVolumeClaim template:
   ```bash
   k create pvc my-pvc --storage-class=standard --access-modes=ReadWriteOnce --storage=1Gi --dry-run=client -o yaml > pvc.yaml
   ```

##### Field Selection and Filtering Mastery

Master these commands to quickly extract and filter information:

1. Get specific fields from resources:
   ```bash
   k get pods -o jsonpath='{.items[*].metadata.name}'
   ```

2. Filter resources by label:
   ```bash
   k get pods -l app=nginx,environment=production
   ```

3. Sort resources by field:
   ```bash
   k get pods --sort-by='.status.containerStatuses[0].restartCount'
   ```

4. Get resources across all namespaces:
   ```bash
   k get pods --all-namespaces
   ```

5. Custom columns for focused output:
   ```bash
   k get pods -o custom-columns=NAME:.metadata.name,STATUS:.status.phase,NODE:.spec.nodeName
   ```

##### Advanced Vim Navigation

These additional vim techniques can significantly speed up editing:

1. Fast movement:
   - `gg` - Go to the first line
   - `G` - Go to the last line
   - `0` - Go to the beginning of the line
   - `$` - Go to the end of the line

2. Efficient editing:
   - `ciw` - Change inner word
   - `di(` - Delete everything inside parentheses
   - `yi{` - Copy everything inside curly braces
   - `>G` - Indent from current line to end of file

3. Multiple file navigation:
   - `:e filename` - Edit a new file
   - `:bn` - Switch to the next buffer
   - `:bp` - Switch to the previous buffer

#### Common Pitfalls and How to Avoid Them

Being aware of frequent mistakes can help you prevent them during the exam:

##### Context and Namespace Confusion

**Problem**: Working in the wrong context or namespace is a common source of errors.

**Solution**:
1. Begin each question by explicitly setting both the context and namespace:
   ```bash
   kubectl config use-context <context-name>
   kubectl config set-context --current --namespace=<namespace>
   ```

2. Create a visual reminder by adding this information to your command prompt:
   ```bash
   PS1='$(kubectl config current-context):$(kubectl config view --minify --output "jsonpath={..namespace}") \$ '
   ```

##### Resource Creation Verification Failure

**Problem**: Creating resources without verifying they're running correctly.

**Solution**:
1. Implement a consistent verification workflow:
   ```bash
   # Create resource
   kubectl apply -f resource.yaml
   
   # Verify creation
   kubectl get <resource-type> <resource-name>
   
   # Check details for correctness
   kubectl describe <resource-type> <resource-name>
   
   # For pods, check logs if applicable
   kubectl logs <pod-name>
   ```

2. Don't mark a question as complete until you've verified the resource is in the desired state

##### YAML Indentation and Syntax Errors

**Problem**: Incorrect indentation or syntax in YAML files causes resource creation failures.

**Solution**:
1. Use spaces, not tabs, for indentation (4 spaces per level is recommended)

2. Maintain consistent indentation level increments

3. When copying from existing resources, carefully adjust indentation of new fields

4. For complex resources, generate template YAML with kubectl and modify rather than writing from scratch

##### Access Control Misconfigurations

**Problem**: Incorrectly configured RBAC settings that either grant too much or too little access.

**Solution**:
1. Always test RBAC configurations after implementation:
   ```bash
   kubectl auth can-i <verb> <resource> --as=system:serviceaccount:<namespace>:<serviceaccount>
   ```

2. Verify proper binding between roles and service accounts:
   ```bash
   kubectl get rolebinding <binding-name> -o yaml
   ```

3. Check namespace-specific access separately from cluster-wide access

#### Final Day Preparation

The day before your exam, focus on these activities:

##### Knowledge Consolidation

1. Review your notes on frequently used commands and workflows

2. Practice kubectl command generation and resource creation without referring to documentation

3. Mentally walk through the troubleshooting process for common issues

4. Focus on understanding the relationship between different Kubernetes components

##### Technical Environment Setup

1. Test your computer, internet connection, webcam, and microphone

2. Ensure your exam space is quiet, well-lit, and free from unauthorized materials

3. Clear your desk except for allowed items

4. Close all unnecessary applications on your computer

5. Check that your browser allows for the exam portal requirements

##### Mental Preparation

1. Get a good night's sleep before the exam

2. Have a light meal before the exam starts

3. Prepare water and any other permitted items

4. Plan to be ready 15 minutes before the scheduled start time

5. Use relaxation techniques if you feel anxious

##### Additional References

- https://www.youtube.com/watch?v=wS277TdV3f8

---