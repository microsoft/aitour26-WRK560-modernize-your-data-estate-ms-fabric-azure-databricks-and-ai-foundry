## Task 1.2: Use the New Shortcut option from external data sources

Now, this is something exciting! This section shows how easy it is to create Shortcuts without moving data. That is the power of OneLake! In this exercise, you will ingest the curated bounce rate data for Litware from ADLS Gen2 using the New Shortcut option. Let’s see how!

1. Inside the *ZavaLakehouse*, select the **three dots (ellipses)** on the right side of Files.

2. Select **New Shortcut**.

    > [!NOTE]
    > **Note:** Make sure you create a shortcut under **Files** and not under **tables** in the lakehouse explorer pane.

    ![Screenshot showing how to create a new shortcut in a Lakehouse.](media/create-new-shortcut.png)

3. In the pop-up window, under **External sources**, select the **Azure Data Lake Storage Gen2** source.

    ![Screenshot showing the selection of Azure Data Lake Storage Gen2 as the external source.](media/adls-gen2-source.png)

4. On the pop-up window, select **New connection**.

5. In the screen below, we need to enter the connection details for the **ADLS Gen2** shortcut.

    ![Screenshot showing the connection details for the ADLS Gen2 shortcut.](media/adls-gen2-connection.png)

6. Enter the following connection details:
   - **URL**: `https://stbuild@lab.LabInstance.Id.dfs.core.windows.net/`
   - **Authentication Kind**: Select **Account Key**
   - **Account Key**: `@lab.Variable(storageaccountkey)`

7. Then select **Next**.

    ![Screenshot showing filled in connection details for the ADLS Gen2 shortcut.](media/adls-gen2-connection-filled.png)

8. Select the **data** and **litwaredata** checkbox and then click on the **Next** button.

    ![Screenshot showing the selection of data and litwaredata checkboxes.](media/litwaredata-checkboxes.png)

9. Click on the **Create** button.

    ![Screenshot showing the creation of the ADLS Gen2 shortcut.](media/adls-gen2-creation.png)

10. And there you go! Your shortcut is now ready! Click (do not expand) on the newly created shortcut named **litwaredata**.

    ![Screenshot showing the newly created shortcut named litwaredata.](media/new-shortcut-created.png)

Prior to Microsoft Fabric, departments at Zava had to move the data they needed from other departments via time-consuming ETL processes. But look, now they have created shortcuts. No need to move any of this data. That is the power of OneLake!

### Next Step

> Select **Next >** to Create Delta Tables using a Spark Notebook.
