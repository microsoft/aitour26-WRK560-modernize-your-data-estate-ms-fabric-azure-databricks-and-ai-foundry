## Task 5.3: Build an AI Foundry agent grounded with Fabric data

In this task, you assist Reta to create an AI Foundry agent that leverages the Fabric Data Agent you created earlier. This agent will be able to answer questions about Zava's customer and sales data using natural language.

1. In the left navigation pane of the **Management center**, select the **Go to Project** button to return to the main project page.

    ![Screenshot showing how to go back to the project in Azure AI Foundry](media/azure-ai-foundry-go-to-project.png)

2. In the left navigation pane, select **Agents** the select the **+ New agent** button.

    ![Screenshot showing how to create a new agent in Azure AI Foundry](media/azure-ai-foundry-new-agent.png)

3. Select the newly created agent, then select the **Try in playground** button on the right hand pane.

    ![Screenshot showing how to try the agent in playground in Azure AI Foundry](media/azure-ai-foundry-try-in-playground.png)

4. On the right hand pane, under **Setup** provide the following details:

    - **Agent name**: Enter `Zava Insights Agent`
    - **Instructions**: Enter `You are an AI assistant that helps Zava to gain insights from customer churn and sales data. Use the Fabric Data Agent to answer questions about customer behavior and sales trends. Provide clear and concise answers with relevant details.`
    - **Deployment**: Leave as default `gpt-4o`

    ![Screenshot showing how to set up the agent in Azure AI Foundry](media/azure-ai-foundry-agent-setup.png)

5. Now let's ground the agent with Fabric Data. On the right hand pane, next to **Knowledge (0)** select the **+ Add** button.

    ![Screenshot showing how to add knowledge to the agent in Azure AI Foundry](media/azure-ai-foundry-add-knowledge.png)

6. In the **Add knowledge** dialog, select **Microsoft Fabric** from the list of knowledge types. Then select the **ZavaDataAgent** connection you created in the previous task. Select the **Connect** button to add the Fabric Data Agent as a knowledge source for the agent.

    ![Screenshot showing how to connect to Microsoft Fabric in Azure AI Foundry](media/azure-ai-foundry-connect-fabric-knowledge.png)

7. You will see the **ZavaDataAgent** listed under the **Knowledge** section on the right hand pane.

    ![Screenshot showing the Fabric Data Agent added as a knowledge source in Azure AI Foundry](media/azure-ai-foundry-fabric-knowledge-added.png)

8. Now, let's take a step further and enable the agent to use tools. On the right hand pane, next to **Actions (0)** select the **+ Add** button.

    ![Screenshot showing how to add tools to the agent in Azure AI Foundry](media/azure-ai-foundry-add-tools.png)

9. In the **Add actions** dialog, select **Code Interpreter** from the list of action types.

    ![Screenshot showing how to add Code Interpreter tool in Azure AI Foundry](media/azure-ai-foundry-add-code-interpreter.png)

10. In the **Add code interpreter action** dialog, select the **Save** button to add the Code Interpreter tool to the agent.

    ![Screenshot showing how to save Code Interpreter tool in Azure AI Foundry](media/azure-ai-foundry-save-code-interpreter.png)

    > [!NOTE]
    > You can also add your own custom code by using the **Select local files** option.

11. Enter the following question in the prompt box then select the **Send** button. The agent will use the Fabric Data Agent to fetch the relevant data and provide an answer to your question.

    - `What are the top 5 selling products by total revenue?`

    ![Screenshot showing how to interact with the agent in Azure AI Foundry](media/azure-ai-foundry-ask-agent.png)

    > [!IMPORTANT]
    > Your agent may take a few moments to respond as it fetches data from the Fabric Data Agent. If it does not respond with your expected answer, create a new thread or agent and try again.

12. Let's help Reta to visualize the sales data. Enter the following question in the prompt box then select the **Send** button. The agent will use the Code Interpreter tool to generate a bar chart of the top 5 selling products by total revenue.

    - `Can you show me a bar chart of the top 5 selling products by total revenue?`

    ![Screenshot showing how to ask for a bar chart in Azure AI Foundry](media/azure-ai-foundry-ask-bar-chart.png)

And there you go! You have successfully created an AI Foundry agent that leverages the Fabric Data Agent to answer questions about Zava's customer and sales data using natural language. Reta can now use this agent to gain insights and make data-driven decisions for Zava. This agent can be further enhanced by adding more knowledge sources, tools, refining its instructions and can be deployed to a custom web app or service for easy access by Zava's team. Congratulations you have completed this lab!

### Next Step

> Select **Next >** to Clean up the resources.
