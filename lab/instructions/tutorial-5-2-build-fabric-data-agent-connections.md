## Task 5.2: Establish Azure OpenAI and Fabric connections in AI Foundry

Zava integrated all of their data sources using Microsoft Fabric, including customer feedback, sales
records, social media interactions, and encompassing internal company policy documents such as SOPs
and research articles on customer behavior into Azure AI Search. This created a unified, searchable
knowledge base.

Let's continue stepping into the shoes of Reta, the Data Scientist to see how.

1. Open a new tab in your VM browser and sign in to the Azure Portal by clicking on `https://portal.azure.com`, enter your credentials if prompted (on the resources section). In the Azure portal, search for `rg-build25-@lab.LabInstance.Id`. Select the resource group from the search results.

    ![Screenshot showing how to search for a resource group in Azure Portal](media/azure-portal-search-rg.png)

2. In your resource group search for and select **prj-build@lab.LabInstance.Id** project then select the **Studio web URL** to launch Azure AI Foundry.

    ![Screenshot showing how to select a project in Azure AI Foundry](media/azure-ai-foundry-select-project.png)

    > [!NOTE]
    > Make sure to close any pop-ups that may appear.

3. In the **prj-build@lab.LabInstance.Id** project, scroll down to the bottom and select **Management center** from the left navigation pane.

    ![Screenshot showing how to select Management center in Azure AI Foundry](media/azure-ai-foundry-management-center.png)

4. In the **Management center**, select the **Connected resources** tab and then select the **+ New connection** button.

    ![Screenshot showing how to add a new connection in Azure AI Foundry](media/azure-ai-foundry-new-connection.png)

5. In the **New connection** pane, select **Azure OpenAI** from the list of connection types. You will find an Azure OpenAI resource with *gpt-4o* and *text-embedding-ada-002* models already deployed. Select the **Add connection** button to create a new connection.

    ![Screenshot showing how to select Azure OpenAI in Azure AI Foundry](media/azure-ai-foundry-select-azure-openai.png)

6. In the **New connection** dialog, select **Microsoft Fabric** from the list of connection types under **Agent Knowlegde Tools**. Provide the following details to connect to the Fabric Data Agent you created in the previous task:

    - **workspace-id**: Paste the workspace ID you copied from Fabric Data Agent URL. The workspace ID is the alphanumeric string after **/workspaces/<workspace-id>/** in the URL.
    - **artifact-id**: Paste the artifact ID you copied from Fabric Data Agent URL. The artifact ID is the alphanumeric string after **/aiskills/<artifact-id>/** in the URL.
    - **Connection name**: Enter `ZavaDataAgent`

    Select the **Add connection** button to create a new connection.

    ![Screenshot showing how to connect to Microsoft Fabric in Azure AI Foundry](media/azure-ai-foundry-connect-fabric.png)

7. Once the Azure AI Search services are connected, select **Close**. You will see both connections listed under the **Connected resources** tab.

### Next Step

> Select **Next >** to Build an AI Foundry agent grounded with Fabric data.
