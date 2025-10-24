# Tutorial 1: Data ingestion from a spectrum of analytical data sources into OneLake

*Before we start executing the steps, we will open a backup Click-by-Click lab using the following hyperlink in a new tab and navigate back to the VM browser:*

[Click-by-Click](https://regale.cloud/microsoft/play/3781/modern-analytics-with-microsoft-fabrikam-copilot-and-azure-databricks-dream-lab-#/0/0)

## Task 1.1: Create a Microsoft Fabric enabled workspace

In this exercise, you will act as the Data Engineer, Bryan, to transfer Zava's data from ADLS Gen2 into the Lakehouse and initiate data preparation for the upcoming merger between Zava and Litware Inc.

1. In the virtual machine, open a web browser and browse to `https://app.fabric.microsoft.com`.
2. When prompted, sign in using the following credentials:

    * **Email**: `@lab.CloudPortalCredential(User1).Username`
    * **Password**: `@lab.CloudPortalCredential(User1).Password`

3. If prompted to stay signed in, select **Yes**.

    > [!NOTE]
    > **Note**: Close any pop-up dialogs that appear on the screen.

4. Select **Continue** and on the **Job Title** box enter `Data Expert`. On the **Business Phone Number** box enter `1230000849` then select **Get Started**.

    > [!NOTE]
    > **Note:** Wait for the Power BI workspace to load and *close* the top bar for a better view.

5. Select **Workspaces** from the left navigation pane. Then select **+ New workspace**.

    ![Screenshot showing how to create a new workspace in Microsoft Fabric.](media/create-new-workspace.png)

6. Enter a name for the workspace, such as `ZavaWorkspace_@lab.LabInstance.Id`. Expand the **Advanced** option and make sure **Fabric Capacity** is selected then select **Apply** when done.

    ![Screenshot showing options to create a new workspace in Microsoft Fabric.](media/create-workspace-side-pane.png)

    ![Screenshot showing advanced options to create a new workspace in Microsoft Fabric.](media/create-workspace-side-pane-advanced.png)

    > [!NOTE]
    > **Note**: The workspace name must be unique across the Fabric tenant. If you receive an error, try a different name. Close any pop-up dialogs that appear on the screen.

### Create a Lakehouse

Now, let's see how each department can easily create a Lakehouse in the Zava workspace without any provision. They simply provide a name, given the proper access rights of course!

1. In the Zava workspace you created, select **+ New Item** from the top menu.

    ![Screenshot showing how to create a new item in Microsoft Fabric.](media/create-new-item.png)

2. In the **New Item** pane, search for **Lakehouse** and select **Lakehouse**.

    ![Screenshot showing how to create a new Lakehouse.](media/create-lakehouse.png)

3. Enter a name for the Lakehouse, such as `ZavaLakehouse`.

4. Select the **Lakehouse schemas** checkbox and then select **Create**.

    ![Screenshot showing how to fill the new Lakehouse form in Microsoft Fabric.](media/create-new-lakehouse.png)

In just a few seconds, Lakehouse was created by simply providing a name and no resource provisioning was needed. With the right access, you, as a Data Engineer, can effortlessly create a new Lakehouse. There is no need to set up any storage accounts or worry about network, infrastructure, key vault, Azure subscriptions, etc.

### Next Step

> Select **Next >** to Ingest data from external sources using shortcuts.
