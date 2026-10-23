# Fundamental of Database Design & Inormation System

## Part 1: Management Levels & Information Flow - 3-Tier Pyramid

**Flow Explanation:**

- **Data Aggregation flows UPWARD:** Raw TPS data -> Summarized by MIS/DSS -> Used as strategic KPIs by ESS
- **Decisions flow DOWNWARD:** Strategic decisions set direction for Tactical and Operational levels

#### Tier 1: Bottom - Operational Level
- **Management Level:** Operational Management
- **Corresponding IS Type:** TPS - Transaction Processing System
- **Data Flow & Purpose:** Processes daily, detailed, raw data like sales, payroll, inventory. Keeps daily business running and collects base data for higher levels. Structured, routine decisions.

#### Tier 2: Middle - Tactical Level
- **Management Level:** Tactical / Middle Management  
- **IS Type:** MIS / DSS - Management Information System / Decision Support System
- **Data & Purpose:** Summarizes TPS data into periodic reports and what-if models (e.g. monthly sales, budget analysis). Monitors performance and supports short/medium-term decisions.

#### Tier 3: Top - Strategic Level
- **Management Level:** Strategic / Top Management
- **IS Type:** ESS / EIS - Executive Support System
- **Data & Purpose:** Highly aggregated internal + external data like market trends, forecasts, KPIs. Supports unstructured, long-term strategic planning.

## Part 2: Technical Architecture Definitions

#### 1. IT Infrastructure Diagram
An IT Infrastructure Diagram shows the physical reality. It lists actual hardware - servers, PCs, routers, switches, cables, data centers - and where they are physically located with specs like IP and model. It answers "what box is where and how is it wired?"

#### 2. IT Landscape Diagram
A Landscape Diagram shows the logical inventory, not the physical boxes. It shows the types of systems - applications, databases, OS, cloud services like ERP, CRM, MySQL - and how they logically connect and integrate. It answers "what types of software do we have and how do they talk?"

#### 3. IT Architecture Diagram
An Architecture Diagram shows the concepts, norms and standards. It defines principles and rules forhow to build in the future, for example "all apps must use SSO" or "use 3-tier architecture" or "encrypt all data". It is the governance blueprint.

