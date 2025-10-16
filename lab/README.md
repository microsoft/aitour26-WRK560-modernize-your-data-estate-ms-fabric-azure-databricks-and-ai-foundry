These instructions are for participants of the **instructor-led** Workshop **Modernize your data estate by using MS Fabric, Azure Databricks, and AI Foundry** at Microsoft AI Tour 2026.  Register to attend in a city near you at [Microsoft AI Tour](https://aitour.microsoft.com/).

## Get Started

> [!TIP]
> As you follow the instructions in this pane, whenever you see a `icon`, you can use it to copy text from the instruction pane into the virtual machine interface. This is particularly useful to copy code; but bear in mind you may need to modify the pasted code to fix indent levels or formatting before running it!

## Sign into Windows

1. In the virtual machine, sign into Windows using the following credentials:

   - Username: `@lab.VirtualMachine(Win11-Pro-Base-VM2).Username`
   - Password: `@lab.VirtualMachine(Win11-Pro-Base-VM2).Password`

## Replacement Tokens & Values

1. During the lab, you will use the following replacement tokens:
   - Storage Account Key: `@lab.Variable(storageaccountkey)`
   - Workspace URL: `@lab.Variable(workspaceurl)`

## Lab Overview

This lab demonstrates a cloud-native analytics solution using Microsoft Fabric with Copilot and Azure Databricks, designed for cost-efficiency and performance. It showcases how this architecture unifies data estates to accelerate value creation.

The scenario centers on Zava, a regional DIY retailer acquiring Litware Inc., which holds curated marketing and sales data processed via Azure Databricks and stored in ADLS Gen2. Zava also maintains customer churn data in the same storage layer.

Through the exercises, you'll explore how Zava:

- Ingests data from diverse sources into OneLake
- Uses shortcuts to reference Litware’s existing data
- Leverages Unity Catalog to understand and select relevant data
- Mirrors selected data into OneLake via Azure Databricks Catalog
- Builds LLM-powered chatbots to uncover market sentiment

The lab begins on January 30th, as Zava’s new CEO, Kayo, responds to troubling KPIs:

- High customer churn
- Declining sales
- Website bounce rate
- Rising costs
- Poor customer experience
- Low market sentiment

To address these, Kayo tasks CTO Carlos and his team, Bryan (data engineer), Reta (data scientist), and Eric (data analyst), with designing a data-driven solution. They tackle data silos and integration challenges using:

- OneLake for unified data storage
- Mirrored Azure Databricks Catalog for legacy data access
- ADLS Gen2 shortcuts for efficient data referencing
- Power BI for data visualization and reporting
- Data Agents and AI Foundry agents for conversational insights

You’ll walk in this team's shoes to execute key steps and help reverse Zava’s KPI trends. The exercises are designed to be completed in order because they build on the data and resources created in the previous exercises, so make sure you complete each exercise before moving on to the next one.

Select **Next >** to go to the first exercise.

===

!INSTRUCTIONS [Exercise 1: Data ingestion](https://raw.githubusercontent.com/microsoft/aitour26-WRK560-modernize-your-data-estate-ms-fabric-azure-databricks-and-ai-foundry/main/lab/instructions/tutorial-1-ingest-data.md)

===

!INSTRUCTIONS [Exercise 2: Mirror Azure Databricks in Fabric](https://raw.githubusercontent.com/microsoft/aitour26-WRK560-modernize-your-data-estate-ms-fabric-azure-databricks-and-ai-foundry/main/lab/instructions/tutorial-2-dlt-pipeline-with-azure-databricks.md)

===

!INSTRUCTIONS [Exercise 3: Build Conversational AI Insights](https://raw.githubusercontent.com/microsoft/aitour26-WRK560-modernize-your-data-estate-ms-fabric-azure-databricks-and-ai-foundry/main/lab/instructions/tutorial-3-power-bi-report.md)

===

!INSTRUCTIONS [Exercise 4: Build Power BI Report](https://raw.githubusercontent.com/microsoft/aitour26-WRK560-modernize-your-data-estate-ms-fabric-azure-databricks-and-ai-foundry/main/lab/instructions/tutorial-4-mirror-azure-databricks.md)

===

!INSTRUCTIONS [Exercise 5: Build Fabric Data Agents](https://raw.githubusercontent.com/microsoft/aitour26-WRK560-modernize-your-data-estate-ms-fabric-azure-databricks-and-ai-foundry/main/lab/instructions/tutorial-5-build-fabric-data-agents.md)

===

!INSTRUCTIONS [Exercise 6: Clean up resources](https://raw.githubusercontent.com/microsoft/aitour26-WRK560-modernize-your-data-estate-ms-fabric-azure-databricks-and-ai-foundry/main/lab/instructions/tutorial-6-clean-up-resources.md)

## Discussions

Build your first agent with Azure AI Agent Service is an open source project supported by Microsoft. See the [SUPPORT.md](../SUPPORT.md) file for details on how to raise issues or contribute. If you enjoyed this workshop please give the repository a ⭐ and share it with others.

## Source code

The source code for this session can be found in the [src folder](../src) of this repo.
