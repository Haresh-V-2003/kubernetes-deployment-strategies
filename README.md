# GitOps-Driven Service Mesh Deployment on Kubernetes

An end-to-end implementation of a **GitOps-powered Service Mesh** using
**Argo CD** and **Istio sidecar injection**. This repository
demonstrates how to achieve secure, observable, and controlled
microservice communication in Kubernetes while maintaining full
automation and versioned deployments.

------------------------------------------------------------------------

## 📘 Overview

This project showcases a production-ready architecture where: -
**Istio** manages traffic routing, security, and observability. -
**Envoy sidecars** act as intelligent proxies for every service. -
**Argo CD** handles continuous delivery through GitOps principles. - The
entire stack (apps + mesh configs) is declaratively managed in Git.

This setup enables deterministic rollouts, secure service-to-service
communication, and deep visibility into microservice behavior.

------------------------------------------------------------------------

## 🚦 Traffic Management & Routing

Traffic flow is controlled through Istio networking resources: -
**Gateway** -- Exposes the application to external traffic. -
**VirtualService** -- Defines routing rules for incoming requests. -
**DestinationRule** -- Configures subsets, load balancing, and
connection policies.

**Traffic Flow:**

    Client → Istio Gateway → VirtualService → DestinationRule → Envoy Sidecar Proxy → Service

This ensures fine-grained traffic shaping, retries, timeouts, and
reliability.

------------------------------------------------------------------------

## 🔐 Service-to-Service Security

To secure internal communication: - **PeerAuthentication** is configured
to enforce mutual TLS (mTLS). - **DestinationRule** applies TLS policies
for workloads. - A **self-signed certificate** is used to establish
trusted mTLS communication within the mesh.

This setup ensures encrypted in-cluster traffic and prevents
unauthorized access.

------------------------------------------------------------------------

## 🧭 Envoy Proxies

Every service in the mesh is injected with an **Envoy sidecar**,
enabling: - Intelligent routing - Load balancing - Traffic policy
enforcement - Telemetry collection

Envoy plays a key role in ensuring service resilience and observability.

------------------------------------------------------------------------

## 📊 Observability Stack

### **Kiali**

-   Visualizes the service mesh topology
-   Shows traffic flow, validations, and mTLS status

### **Prometheus**

-   Collects mesh and application metrics (latency, errors, RPS)

### **Grafana**

-   Dashboard visualizations for time-series metrics

### **Jaeger**

-   Distributed tracing across microservices
-   Identifies bottlenecks and latency hotspots

------------------------------------------------------------------------

## 🔁 GitOps with Argo CD

All deployments, configurations, and Istio manifests are
version-controlled.

Argo CD enables: - Automated syncing from Git to cluster - Rollbacks and
audit history - Declarative environment management

This results in reliable, reproducible, and self-healing deployments.

------------------------------------------------------------------------


## 📚 Documentation

-   **Istio:** https://istio.io/latest/docs/setup/getting-started/
-   **Argo CD:** https://argo-cd.readthedocs.io/en/stable/
-   **Kubernetes:** https://kubernetes.io/docs/

------------------------------------------------------------------------

## 🚀 Key Takeaways

By combining **Istio** with **Argo CD**, this project demonstrates how
to build: - Secure microservice communication - Intelligent traffic
management - End-to-end observability - Fully automated GitOps-driven
operations

This architecture is ideal for cloud-native, scalable, and
production-grade deployments.

------------------------------------------------------------------------

## 🏷️ Tags

**Kubernetes • Service Mesh • Istio • GitOps • Argo CD • Observability •
DevOps**
