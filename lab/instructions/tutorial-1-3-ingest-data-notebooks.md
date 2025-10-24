## Task 1.3: Create Delta Tables using Spark Notebook

Now, let’s see how Data Engineer, Bryan, got the remaining data into OneLake by creating Delta tables using Spark Notebook. By using a Spark Notebook to create Delta tables, Bryan can ensure more reliable, scalable, and efficient data management, which is essential for handling big data workflows.

1. Inside the **ZavaLakehouse**, select **Open Notebook** then choose **New Notebook**.

    ![Screenshot showing how to create a new notebook in Microsoft Fabric.](media/create-new-notebook.png)

2. Once the notebook is created, paste the **below code** in the existing cell and run the cell by clicking on the **Run cell** icon.

    ```python
    import os
    import pandas as pd
     
    # List all CSV files in the 'litwaredata' folder
    file_path = '/lakehouse/default/Files/litwaredata/'
    csv_files = [file for file in os.listdir(file_path) if file.endswith('.csv')]
     
    # Load each CSV file into a table
    for file in csv_files:
        table_name = file.split('.')[0]
        df = pd.read_csv(file_path + file)
        spark.createDataFrame(df).write.mode("ignore").format("delta").saveAsTable(table_name)
    ```

3. Once the code cell runs successfully, you will see a green tick at the bottom of the cell. Now, expand the **Tables** section, expand **dbo**, select on the **three dots** and the select **Refresh**. You should see the newly created Delta tables listed here.

    ![Screenshot showing the refreshed Delta tables in the Tables section](media/refresh-delta-tables.png)

4. You now have all the tables in **OneLake** for Zava to leverage.

### Next Step

> Select **Next >** to Build DLT Pipelines in Azure Databricks
