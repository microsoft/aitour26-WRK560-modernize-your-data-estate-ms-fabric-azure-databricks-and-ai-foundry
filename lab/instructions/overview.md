# Lab Overview

This lab showcases Microsoft Fabric with Copilot and Azure Databricks, featuring a cost-effective, performance-optimized, and cloud-native Analytics solution pattern. This architecture unifies our customers' data estate to accelerate data value creation.

The visual illustrates the real-world example for Zava, a fictitious company.

Zava is a retailer with thousands of brick-and-mortar stores across the world and an online store. Zava is acquiring Litware Inc., which has curated marketing data and sales data processed by Azure Databricks and stored in the gold layer in ADLS Gen2. Zava also has their customer churn data stored in the gold layer in ADLS Gen2.

In the following exercises, you will see how the Zava team leveraged the power of Microsoft Fabric to ingest data from a spectrum of sources, combine Litware's data with their existing data from ADLS Gen2, and derive meaningful insights. Explore how they used a shortcut to reference Litware’s existing data from ADLS Gen2. Finally, you will see how Zava’s data architects utilized Unity Catalog to quickly get up to speed on the acquired company’s data. After Zava's data architects got up to speed, they chose which data to pick from the Unity catalog and include that in OneLake using Mirrored Azure Databricks Catalog. You will also see the power of creating LLM Chatbots with the Databricks Data Intelligence Platform to uncover an unprecedented market sentiment for Zava.

The lab scenario begins on January 30th. The new CEO, Kayo, has noticed some negative trends in the company’s key metrics, including:

- A high number of their customers leaving

- Falling sales revenue

- High bounce rate on their website

- High operating costs

- Poor customer experience

And most importantly, low market sentiment

To address the high customer churn, Kayo and the Zava team decided to acquire Litware Inc., which carries products popular with millennials. Kayo asks Carlos, the Chief Technology Officer, how they could create a data-driven organization and reverse these adverse KPI trends. Carlos talks to his technical team, including Bryan, the data engineer; Reta, the data scientist; and Eric, the data analyst. He tasks them with designing and implementing a solution pattern to realize this vision of a data-driven organization.

The team recognizes that the existence of data silos within Zava's various departments presents a significant integration challenge, which is intensified by the need to combine subsidiary data with data from Litware Inc. To overcome these challenges, they plan to utilize Fast Copy for efficient data ingestion, Task Flow for streamlined workflows, Real-time Intelligence for immediate insights, and Azure SQL DB Mirroring in Fabric to ensure seamless access to relational data across the organization.

During this lab you will execute some of these steps as a part of this team to reverse these adverse KPI trends. First, you will ingest data from a spectrum of data sources into OneLake for Zava. Let's get started!