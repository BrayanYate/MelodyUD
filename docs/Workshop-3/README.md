# 📊 Workshop 1 – Spotify Business & Data Architecture

**Authors:**  
- Brayan Stiven Yate Prada – *Student ID:* 20192020151  
- Holman Andres Alvarado Diaz – *Student ID:* 20201020032  

**University:** Universidad Distrital Francisco José de Caldas  
**Faculty:** Faculty of Engineering  
**Course:** Databases II  
**Professor:** Carlos Andrés Sierra Virgüez  
**Year:** 2025  

---

## 📌 Project Overview

This workshop presents a comprehensive analysis and system design for a Spotify-like streaming platform. The document covers the business model, functional and non-functional requirements, user stories for multiple roles, and a robust database architecture using open-source technologies.

---

## 🧩 Business Model Canvas

Spotify operates on a **freemium** model:
- **Free Tier:** Supported by ads, with limited functionality.
- **Premium Tier:** Subscription-based with ad-free playback, high-quality audio, offline downloads, and full access to features.

Revenue is primarily driven by premium users, with additional income from targeted advertising.

---

## 📋 Functional & Non-Functional Requirements

### ✅ Functional Requirements

Requirements span key domains such as:
- **Account & Identity** (e.g., user registration, MFA, subscription lifecycle)
- **Content Catalog** (e.g., audio ingestion, metadata enrichment)
- **Discovery & Personalization** (e.g., search, recommendations)
- **Playback & Delivery** (e.g., ABR streaming, CDN negotiation)
- **Social & Advertising Features**
- **Creator Tools** and **Analytics Dashboards**
- **Compliance & Governance**

### ⚙️ Non-Functional Requirements

Highlights include:
- **Performance:** Search ≤ 150ms, Ad decisions ≤ 50ms  
- **Scalability:** 1B+ users, 10TB/day ingestion  
- **Availability:** ≥ 99.95% SLA  
- **Security:** TLS 1.3, AES-256, tokenization  
- **Observability:** Full traceability, log retention  
- **Maintainability & Extensibility**

---

## 👥 User Stories

Defined across key roles:

### 🎧 Listener
- Register account, listen with ads or ad-free (Premium)
- Create/share playlists, receive recommendations
- Integrate with smart devices, manage subscription

### 🎙️ Creator
- Upload content, view analytics
- Schedule promotions, edit metadata

### 📢 Advertiser
- Launch and monitor campaigns
- Perform real-time creative updates

### 🛠️ Engineer
- Ensure SLA uptime, auto-scale ingestion
- Enable tracing, log retention, CI/CD deployments

### 🔐 Compliance Officer
- Tokenize payments, enforce GDPR
- Maintain immutable audit logs and access reviews

---

## 🗄️ Database Architecture

The platform adopts a **distributed, modular, and open-source** data architecture:

| Layer               | Purpose                                              | Technologies                                   |
|--------------------|------------------------------------------------------|------------------------------------------------|
| Hot OLTP Data      | Strongly consistent user/billing data                | CockroachDB, PostgreSQL + Citus                |
| Session Store      | Low-latency access to playback & telemetry           | Apache Cassandra, Scylla                       |
| Object Storage     | Store audio/artwork/audit logs                       | MinIO, Ceph RGW                                |
| Search Index       | Full-text search & autocomplete                      | OpenSearch                                     |
| Graph Store        | Social graph & rec engine                            | JanusGraph, Neo4j                              |
| Stream Backbone    | Event log of all user actions                        | Apache Kafka                                   |
| Real-Time Analytics| Dashboards for creators/advertisers                 | Apache Flink/Spark, ClickHouse, Druid          |
| Deep Analytics     | Machine learning, royalty calcs                      | Trino + Iceberg, ClickHouse, Apache Druid      |

---

## 🔄 ER Diagram Overview

Key entities and relationships:
- **User**: central node linked to subscriptions, playlists, payments, impressions.
- **Track / Album / Artist**: core catalog.
- **Playlist / PlaylistTrack**: many-to-many relation between tracks and lists.
- **Play Events**: logs streams for royalties.
- **Advertiser / Ad Campaign**: tied to user impressions.
- **Payment & Transactions**: tokenized and user-linked.

---

## 🔗 References

- [Spotify Business Model – Business Model Analyst](https://businessmodelanalyst.com/spotify-business-model/)  
- [Music Business Research (2024)](https://musicbusinessresearch.wordpress.com/2024/08/19/the-music-streaming-economy-part-10-spotifys-business-model/)  
- [Investopedia: How Spotify Makes Money](https://www.investopedia.com/articles/investing/120314/spotify-makes-internet-music-make-money.asp)  
- [Intuji: Spotify Tech Stack](https://intuji.com/how-does-spotify-work-tech-stack-explored/)