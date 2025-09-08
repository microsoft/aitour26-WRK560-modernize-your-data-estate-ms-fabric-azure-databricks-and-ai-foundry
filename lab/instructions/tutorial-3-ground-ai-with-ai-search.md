# Exercise 3: Building an AI-Powered Chatbot with Azure AI Foundry and Microsoft Fabric

Zava encountered a major issue with customer churn, especially among millennials. The executives
at Zava struggled to understand this customer segment and figure out how to earn their loyalty.
Despite having extensive data from customer interactions, surveys, and market research, Zava found
it difficult to pinpoint the root cause of the churn and determine effective solutions.
The main problem was the lack of integration in their existing systems. This prevented Zava's
executives from utilizing their data for root cause analysis and strategic insights, which in turn,
hampered their ability to improve marketing strategies, product offerings, and customer experiences.
To solve the data silos issue, Zava implemented an advanced AI solution using Azure OpenAI, Azure
AI Search, and Microsoft Fabric. Once the team discovered that millennials were leaving because they
couldn't find products, they developed an Azure OpenAI-powered shopping assistant to help with
product search and recommendations.

## Task 3.1: Integrate Fabric with Azure AI Foundry using Azure AI Search

Let's step into the shoes of Reta, the Data Scientist, as she launches Azure AI Foundry and leverages
data from Bryan stored in Microsoft OneLake as knowledge base.

1. Navigate back to Microsoft Fabric tab on your browser (+++https://app.fabric.microsoft.com+++)

2. Select your **ZavaWorkspace_@lab.LabInstance.Id** workspace from the left navigation pane, and then select **Manage access** from the top right corner.

    ![Screenshot showing how to manage access in Microsoft Fabric](/lab/media/fabric-manage-access.png)

3. In the **Manage access** pane, select the **+ Add people or groups** button then type +++src-@lab.LabInstance.Id+++. Select **Contributor** role from the dropdown and then select **Add**.

    ![Screenshot showing how to add people or groups in Microsoft Fabric](/lab/media/fabric-add-people.png)

4. Close the **Manage access** pane and then select your **ZavaLakehouse** inside the workspace.

5. Copy the URL from the browser address bar and paste it into a notepad for later use. It should look something like this:
   `https://<your-region>.lakehouse.fabric.microsoft.com/lakehouses/<lakehouse-id>`

6. Open a new tab in your VM browser and sign in to the Azure Portal by clicking on +++https://portal.azure.com+++, enter your credentials if prompted (on the resources tab). In the Azure portal, search for +++**rg-build25-@lab.LabInstance.Id**+++. Select the resource group from the search results.

    ![Screenshot showing how to search for a resource group in Azure Portal](/lab/media/azure-portal-search-rg.png)

7. In the **rg-build25-@lab.LabInstance.Id** resource group, search for +++**Search Service**+++ and select the **srch-@lab.LabInstance.Id** service from the results.

8. In the **Search service**, select the **Import data** option to begin setting up the data source.

    ![Screenshot showing how to import data in Azure AI Search](/lab/media/azure-ai-search-import-data.png)

9. On the **Existing data source** dropdown, select **OneLake files (preview)** option.

10. In the Connect your data tab, provide the following details:

| Setting         | Value                                    |
|--------------------|------------------------------------------|
| Data Source Type        | **OneLake files (preview)**              |
| Data source name               | Enter +++**onelake**+++          |
| Data to extract               | Select **All metadata**                     |
| Parsing mode               | Select **JSON Array**                     |
| Connect by               | Choose **Lakehouse URL**                     |
| OneLake URL              | Paste the URL you copied earlier from the Fabric Lakehouse.          |
| Lakehouse folder/shortcut | Enter +++**products**+++          |
| Managed identity authentication | Select **System-assigned**                     |

![Screenshot showing how to connect data in Azure AI Search](/lab/media/azure-ai-search-connect-data.png)

11. Select **Next: Add cognitive skills (optional)** to proceed then select **Skip to: Customize target index**.

12. In the **Customize target index** tab, enter the following details:
| Setting         | Value                                    |
|--------------------|------------------------------------------|
| Index name        | Enter +++**onelake-index**+++              |
| Key              | Select **id**                     |

13. For the fields listed, configure them as provide in the image below:

    ![Screenshot showing how to customize target index in Azure AI Search](/lab/media/azure-ai-search-customize-index.png)

14. Once done, select **Create an indexer** and enter **+++onelake-indexer+++** as the name then select **Submit** to finalize the setup.

    ![Screenshot showing how to create an indexer in Azure AI Search](/lab/media/azure-ai-search-create-indexer.png)

---

## Task 3.2: Establish Azure OpenAI and Azure AI Search connections in AI Foundry

Zava integrated all of their data sources using Microsoft Fabric, including customer feedback, sales
records, social media interactions, and encompassing internal company policy documents such as SOPs
and research articles on customer behavior into Azure AI Search. This created a unified, searchable
knowledge base.

Let's continue stepping into the shoes of Reta, the Data Scientist to see how.

1. In a new tab of your VM browser, navigate to +++https://ai.azure.com/projects+++ and sign in with your credentials if prompted. Now, in the Azure AI Foundry, select the **prj-build@lab.LabInstance.Id** project.

    ![Screenshot showing how to select a project in Azure AI Foundry](/lab/media/azure-ai-foundry-select-project.png)

> [!NOTE]
> Make sure to close any pop-ups that may appear.

2. In the **prj-build@lab.LabInstance.Id** project, scroll down to the bottom and select **Management center** from the left navigation pane.

    ![Screenshot showing how to select Management center in Azure AI Foundry](/lab/media/azure-ai-foundry-management-center.png)

3. In the **Management center**, select the **Connected resources** tab and then select the **+ New connection** button.

    ![Screenshot showing how to add a new connection in Azure AI Foundry](/lab/media/azure-ai-foundry-new-connection.png)

4. In the **New connection** pane, select **Azure OpenAI** from the list of connection types. You will find an Azure OpenAI resource with *gpt-4o* and *text-embedding-ada-002* models already deployed. Select the **Add connection** button to create a new connection.

    ![Screenshot showing how to select Azure OpenAI in Azure AI Foundry](/lab/media/azure-ai-foundry-select-azure-openai.png)

5. Once the OpenAI services are connected, select **Back to select an asset type**. Select **Azure AI Search** from the list of connection types then select the **Add connection** button.

    ![Screenshot showing how to select Azure AI Search in Azure AI Foundry](/lab/media/azure-ai-foundry-select-azure-ai-search.png)

6. Once the Azure AI Search services are connected, select **Close**. You will see both connections listed under the **Connected resources** tab.

    ![Screenshot showing connected resources in Azure AI Foundry](/lab/media/azure-ai-foundry-connected-resources.png)

---

## Task 3.3: Setup and use Prompt Flow in Azure AI Foundry

Prompt flow in Azure AI Foundry offers a comprehensive, streamlined environment for creating AI
applications. It provides a visual interface for orchestrating flows, and enables iterative prompt
engineering. Azure AI Foundry includes built-in evaluation tools, seamless deployment options, and
integration with Azure's ecosystem. It also offers enterprise-level security and scalability, making it ideal for developing, testing, and deploying sophisticated AI solutions efficiently. Let's explore how Zava deployed and tested a Prompt flow.

1. In the left navigation pane of the **Management center**, select the **Go to Project** button to return to the main project page.

    ![Screenshot showing how to go back to the project in Azure AI Foundry](/lab/media/azure-ai-foundry-go-to-project.png)

2. Under the **Build and customize** section on the left navigation pane, select **Prompt flow** then select the **+ Create** button.

    ![Screenshot showing how to create a new prompt flow in Azure AI Foundry](/lab/media/azure-ai-foundry-create-prompt-flow.png)

3. In the **Create a new flow** dialog, scroll down and select the **Upload** button in the *Upload from local* section. In the **Upload from local** dialog, select **Zip file** then select the **Browse** button to locate the file.

    ![Screenshot showing how to upload a prompt flow in Azure AI Foundry](/lab/media/azure-ai-foundry-upload-prompt-flow.png)

4. Copy the path ++C:\Lab Assets\01_Main_Lab_Assets\artifacts\aistudio++, paste it into the **File name** textbox and select the **Open** button.

    ![Screenshot showing how to select a file in Azure AI Foundry](/lab/media/azure-ai-foundry-browse-file.png)

5. Select the **shopping-assistant-prompt-flow.zip** file and then select the **Open** button. In the **Select flow type** dropdown, select **Chat flow** then select the **Upload button**.

    ![Screenshot showing how to select a flow type in Azure AI Foundry](/lab/media/azure-ai-foundry-select-flow-type.png)

> [!NOTE]
> If clicking on the Upload button doesn't redirect you to the Prompt Flow screen, click the
Upload button again. If it still doesn't work, refresh the page and try uploading again.

6. Select the **Start compute session** button to initialize the flow. It will take approximately 2-3 minutes to start the compute session. Please wait for some time.

    ![Screenshot showing how to start a compute session in Azure AI Foundry](/lab/media/azure-ai-foundry-start-compute-session.png)

7. Once the session is started, scroll down to the **lookup** node in the Prompt flow graph and select it.

8. Select the **edit icon** to modify the value for **mlindex_content** as shown in the screenshot below.

    ![Screenshot showing how to edit a node in Azure AI Foundry](/lab/media/azure-ai-foundry-edit-node.png)

9. In the **Generate** dialog, update the following details:
| Setting         | Value                                    |
|--------------------|------------------------------------------|
| acs_index_connection        | Select **srch@lab.LabInstance.Id**              |
| acs_index_name              | Select **onelake-index**         |
| embedding_type              | Select **Azure OpenAI**                     |
| aoi_embedding_connection              | Select **openAIResource2@lab.LabInstance.Id**    |

10. Select the **Save** button to save the changes made to the node.

    ![Screenshot showing how to save changes in Azure AI Foundry](/lab/media/azure-ai-foundry-save-changes.png)

11. In the **lookup** node, set the **query_type** value to **Keyword**.

    ![Screenshot showing how to set query type in Azure AI Foundry](/lab/media/azure-ai-foundry-set-query-type.png)

12. Select the **prompt_for_looks** node in the Graph, select the **Connection** dropdown and choose **openAIResources2@lab.LabInstance.Id** then select **gpt-4o** in the **Deployment_name** dropdown.

    ![Screenshot showing how to set connection in Azure AI Foundry](/lab/media/azure-ai-foundry-set-connection.png)

13. Select the **Chat** button on the top right corner to test the prompt flow. Select the **+ icon** to start a new session and replace the default prompt and paste the following prompt:

    ++
    Can you show me some Indian dresses for for a wedding in Udaipur?
    ++

    ![Screenshot showing how to test a prompt flow in Azure AI Foundry](/lab/media/azure-ai-foundry-test-prompt-flow.png)

15. Select the **Send** button to see the response generated by the prompt flow.

    ![Screenshot showing the response from a prompt flow in Azure AI Foundry](/lab/media/azure-ai-foundry-prompt-flow-response.png)

And there you go! You have successfully created and tested a Prompt flow in Azure AI Foundry using data from Microsoft Fabric. Reta can now further enhance this flow to improve Zava's customer experience and reduce churn. Once the Prompt flow is deployed as an endpoint, It can be consumed in the web application.