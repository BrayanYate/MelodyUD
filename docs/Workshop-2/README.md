# 🎵 Workshop 2: Data System Architecture and Information Retrieval for a Music Streaming Platform Based on Spotify

**Authors:**  
Brayan Stiven Yate Prada (ID: 20192020151)  
Holman Andres Alvarado Diaz (ID: 20201020032)  

**University:** Universidad Distrital Francisco José de Caldas  
**Faculty:** Faculty of Engineering  
**Course:** Databases II  
**Professor:** Carlos Andrés Sierra Virgüez  
**Date:** May 29, 2025

---

## 📘 Overview

This workshop presents the technical design of a scalable data architecture for a music streaming platform inspired by Spotify. It aligns with business, technical, and regulatory requirements, emphasizing real-time analytics, low-latency playback, and full financial traceability.

---

## 📁 Contents

- **1. Data System Architecture**
  - Technology Stack Justification
  - End-to-End Data Flow
  - Design Rationale
- **2. Information Requirements**
  - Business and user story alignment
- **3. Query Proposals**
  - PostgreSQL, OpenSearch & ClickHouse sample queries
- **4. Improvements Over Workshop 1**
  - Updated architecture, bottlenecks, and solutions
  - Entity-Relationship (ER) Model and Relational Overview
- **5. References**
  - External sources on Spotify's tech stack and business model

---

## 🧰 Technologies Used

| Component            | Technology     | Description                                   |
|----------------------|----------------|-----------------------------------------------|
| API Gateway          | NGINX          | Ingress with TLS and Kubernetes compatibility |
| Authentication       | Keycloak       | OAuth2/OIDC, SSO, token management            |
| OLTP Database        | PostgreSQL 16  | Partitioned, ACID-compliant core data         |
| Search Engine        | OpenSearch     | Real-time, fuzzy, full-text search            |
| Object Storage       | MinIO          | S3-compatible binary storage                  |
| Event Streaming      | Apache Kafka   | Durable logs, CDC, decoupled systems          |
| Analytics DB         | ClickHouse     | Columnar DB for real-time aggregations        |
| Workflow Orchestration | Apache Airflow | ETL pipelines and scheduled jobs            |
| Business Intelligence | Apache Superset| Visual dashboards with RBAC & SSO            |

---

## 🧾 Key Features

- **Microservice-oriented architecture** with horizontal scalability.
- **Real-time insights** without Hadoop using ClickHouse.
- **Fast search integration** using Kafka + Debezium + OpenSearch.
- **Royalty and ad campaign tracking**, ensuring legal compliance.
- **Traceable financials** with tokenized payment and audit logs.
- **Data governance** via secure storage, encryption, and backups.

---

## 🔍 Sample Use Cases

- Identify active premium users in top usage countries.
- Detect potential account sharing.
- Provide real-time content recommendations.
- Monitor user churn through skip patterns.
- Analyze effectiveness of advertising campaigns.
- Calculate artist royalties and cross-check payouts.

---

## 📊 ER Model Domains

- **User & Subscription**: Profiles, plans, and payments
- **Catalog**: Artists, albums, and tracks
- **Playback & Events**: Detailed user interactions
- **Social**: Follows and collaborative playlists
- **Advertising**: Campaigns and impressions
- **Royalties**: Regional and contractual payouts

---

## 📚 References

See the full list of references on [page 14](./workshop_2.pdf) of the report for deeper insights into Spotify’s business model and architecture.

---

## 📝 License

This project is for academic purposes under the supervision of Universidad Distrital Francisco José de Caldas. Redistribution or commercial use is not permitted without permission.

