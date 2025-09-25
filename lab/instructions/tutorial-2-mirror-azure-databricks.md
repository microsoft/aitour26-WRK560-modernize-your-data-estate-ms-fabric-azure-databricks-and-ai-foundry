# Exercise 2: Build DLT Pipelines and Mirror Azure Databricks Catalog

This exercise shows how Microsoft Fabric with Azure Databricks enabled Zava to solve their integration challenges. The acquired company, Litware Inc., was already using Databricks heavily and they stored their churn and sales data in ADLS Gen2. We’ll see how Unity Catalog benefited Zava's data architects so they could quickly get up to speed on all Litware Inc.’s data.

## Task 2.1: Create Delta Live Table pipeline for Data Transformation

Delta Live Tables (DLT) allow you to build and manage reliable data pipelines that deliver high-quality data in Lakehouse. DLT helps data engineering teams simplify ETL development and management with declarative pipeline development, automatic data testing, and deep visibility for monitoring and recovery.

1. Open a new tab in your VM browser and sign in to the Azure Databricks Workspace, by navigating to this url: `https://@lab.Variable(workspaceurl)`.

2. Click on the **Sign in with Microsoft Entra ID**.

    ![Screenshot showing the sign in with Microsoft Entra ID option in Azure Databricks](/lab/media/databricks-signin.png)

3. On the left navigation pane, select **Jobs and pipelines**.

4. Select the **Create** dropdown and choose **ETL Pipeline**.

    ![Screenshot showing the create ETL pipeline option in Azure Databricks](/lab/media/databricks-createetl.png)

5. In the **Create ETL Pipeline** page, provide a name for your pipeline as `DLT_Pipeline`, scroll down to **Paths** and select the folder icon to browse the notebook.

    ![Screenshot showing the create ETL pipeline page in Azure Databricks](/lab/media/databricks-etl-details.png)

6. In the **Select file** dialog, select **Shared**, select **Analytics with ADB**, select **01 DLT Notebook** and then click on the **Select** button.

    ![Screenshot showing the selection of the 01 DLT Notebook in Azure Databricks](/lab/media/databricks-select-file.png)

7. In the **Destination** section, enter `dbo` as the **Default Schema** then select **Create**.

    ![Screenshot showing the destination selection for the pipeline in Azure Databricks](/lab/media/databricks-elt-destination.png)

8. Select **Start** to begin the pipeline execution.

    ![Screenshot showing the DLT pipeline start button in Azure Databricks](/lab/media/databricks-elt-pipeline-start.png)

Once the execution is completed, you will see a result similar to the following:

![Screenshot showing the DLT pipeline execution result in Azure Databricks](/lab/media/databricks-elt-result.png)

This beautiful lineage view showing the Medallion Architecture is a data design pattern commonly used in Databricks to organize and optimize data processing workflows in a lakehouse architecture. It structures data into three logical layers—Bronze, Silver, and Gold—ensuring data quality, accessibility, and scalability for analytics and machine learning.

![Screenshot showing the DLT pipeline execution result in Azure Databricks](/lab/media/databricks-elt-lineage.png)

### Next Step

> Select **Next >** to Mirror Azure Databricks Catalog in Fabric

===

!INSTRUCTIONS []()

## Task 2.2: Create a Mirrored Azure Databricks Catalog in Fabric and analyze data using T-SQL

Mirroring the Azure Databricks Catalog structure in Fabric allows seamless access to the underlying catalog data through shortcuts. This means that any changes made to the data are instantly reflected in Fabric, without the need for data movement or replication. Let’s step into Data Engineer, Eva’s shoes to create a Mirrored Azure Databricks Catalog and analyze the data using T-SQL. 

1. Navigate back to Microsoft Fabric tab on your browser (`https://app.fabric.microsoft.com`)

2. Select your **ZavaWorkspace_@lab.LabInstance.Id** workspace from the left navigation pane, and the select **+ New item** from the menu bar.

    ![Screenshot showing the new item option in Microsoft Fabric](/lab/media/create-new-item.png)

3. In the **New item** dialog, select **Mirrored Azure Databricks catalog** or search for it on the search bar.

    ![Screenshot showing the selection of Mirrored Azure Databricks catalog in Microsoft Fabric](/lab/media/fabric-mirrored-catalog.png)

4. When the **New Source** dialog appears, select the **New Connection** radio button.

5. Enter connection details by using the values in the table below. Make sure to leave all other settings at their default values.

    | Setting         | Value                                    |
    |--------------------|------------------------------------------|
    | Url               | `@lab.Variable(workspaceurl)`         |
    | Authentication Kind    | **Service Principal** |
    | Service principal client ID | `@lab.Variable(clientid)`          |
    | Service principal key              | `@lab.Variable(token)`                     |

6. Select **Connect** then select **Next**.

    ![Screenshot showing the connection details for the Mirrored Azure Databricks catalog in Microsoft Fabric](/lab/media/fabric-connect.png)

7. In the **Choose data** screen, select the Catalog name as **litware_unity_catalog** from the dropdown box. Ensure **default** and **rag** schemas are selected. Select **Next** and then select **Create**.

    ![Screenshot showing the selection of catalog and schemas in Microsoft Fabric](/lab/media/fabric-choose-catalog.png)

8. On the toolbar, select **Monitor catalog** to track the progress of the mirroring process. Wait for mirroring to complete.

9. On the toolbar, to the left of the **Share** button, select the dropdown list and then select **SQL analytics endpoint**.

10. On the toolbar, select **Refresh**. In the Explorer pane, in the **Schemas** section, expand **rag** and then expand **Tables**. You can view the Mirrored Azure Databricks catalog tables data here.

    ![Screenshot showing the Explorer pane with the expanded schemas and tables in Microsoft Fabric](/lab/media/fabric-explorer-pane.png)

11. Click on **New SQL Query**, then copy and paste the following **SQL query** in query editor and click on **Run** button.

     ```sql
        SELECT 
            [Campaign_Name],
            AVG([ROI]) AS Avg_ROI,
            SUM([Profit]) AS Total_Profit,
            SUM([Cost]) AS Total_Cost,
            AVG([Cost]) AS Avg_Cost
        FROM 
            [litware_unity_catalog].[rag].[campaigndata]
        GROUP BY 
            [Campaign_Name]
        ORDER BY 
            Avg_ROI DESC; 
    ```

This query gets campaign details from the mirrored database. It shows the average ROI, total profit, total cost, and average cost for each campaign, and sorts the results by highest average ROI.

### Next Step

> Select **Next >** to Build an AI Powered Chatbot with AI Foundry and Fabric