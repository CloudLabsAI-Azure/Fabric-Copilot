# Fabric Copilot Hands On Lab

## Estimated Duration: 4 hours

## Lab Overview

This hands-on lab provides comprehensive training on leveraging Microsoft Fabric and Copilot capabilities for data ingestion, preparation, and visualization. Participants will create and set up a Fabric workspace, including starting a free trial and linking it with Copilot-enabled capacity (F2). They will ingest datasets into the Lakehouse via Data Pipelines, explore Copilot’s AI-assisted features in Fabric notebooks, and connect to Fabric datasets to generate visualizations in Power BI using Copilot. Additionally, participants will use Copilot to write DAX queries, update measure descriptions, and optionally explore Copilot as a report consumer, gaining a solid understanding of its potential across the data and analytics workflows in Microsoft Fabric.

## Lab objectives

In this lab, you will complete the following exercises:

- Exercise 1: Create and set up Fabric Workspace 

- Exercise 2: Explore Copilot for Data Flows

- Exercise 3: Visualizing and gaining Insights using Copilot for Power BI

## Prerequisites

Participants should have:

- Basic familiarity with data concepts – understanding of datasets, dataflows, and data pipelines.
- Fundamental knowledge of Power BI – ability to create simple reports and visualizations.
- Awareness of Azure and Microsoft services – basic understanding of Azure portal navigation and Microsoft Fabric concepts.
- Comfort with web-based tools – ability to use cloud services and tools like notebooks and dashboards.

## Exercise 1: Create and set up Fabric Workspace

### Task 1: Start Free fabric trial

1. On the lab VM desktop, open the **Edge browser** and open Microsoft Fabric in a new tab by copy pasting the link [Microsoft Fabric](https://app.fabric.microsoft.com/home). You will be navigated to the login page.

1. On the **Microsoft** tab, you will see the login screen. Enter the following **Email/Username** and then click on **Next**.

   - **Email/Username:** <inject key="AzureAdUserEmail"></inject>

        ![](images1/media/exercise-1-img-89.png)

1. Now, enter the following **Password** and click on **Sign in.**

   - **Password:** <inject key="AzureAdUserPassword"></inject>

        ![](images1/media/exercise-1-img-90.png)

1. On the **Stay signed in?** tab click on **Yes**.

    ![](images1/media/exercise-1-img-91.png)

1. You will be navigated to the **Fabric Service Home page**.

1. We assume you are familiar with the layout of Fabric Service. If you have any questions, please do not hesitate to ask the instructor.

1. Currently, you are in the **My Workspace**. To work with Fabric items, you will need a trial license and a workspace that has Fabric license assigned. Let's set this up.

1. On the top right corner of the screen, select the **user icon (1)** and select **Free trial (2)**.

    ![](images1/media/image9.png)

1. Upgrade to a free Microsoft Fabric trial dialog opens. Select **Activate**.

    ![](images1/media/image-10.png)

1. Successfully upgraded to Microsoft Fabric dialog opens. Select **Fabric Home Page**.

    ![](images1/media/image-11.png)

1. You will be navigated to the **Microsoft** **Fabric Home page**.

    ![](images1/media/image-12.png)

### Task 2: Create workspace and link with Fabric Copilot enabled capacity (F2)

1. Now let's create a workspace with a Fabric license. Select **Workspaces** **(1)** from the left navigation bar.

2. Click **+ New workspace (2)** found at the bottom of the pop-out menu.

    ![](images1/media/exercise-1-img-92.png)

3. **Create a workspace** dialog opens on the right side of the browser.

4. Type the name **Workspace<inject key="DeploymentID" enableCopy="false"/> (1)**, validate the availability of the name, and click on **Advanced (2)**.

    >**Note:** Only use the workspace name provided above.

    ![works-apply.png](images1/media/exercise-1-img-2.png)

5. Ensure **Fabric capacity (1)** is enabled, verify that **capacity<inject key="DeploymentID" enableCopy="false"/> - <inject key="Region" enableCopy="false"/> (2)** is selected under **Capacity**, and then click **Apply (3)**.

    ![works-apply.png](images1/media/exercise-1-img-3.png)

    >**Note:** Close any pop-up that appears on the screen.

    ![gotit-popup.png](images1/media/gotit-popup.png)

    >**Note:** Wait for the Power BI Workspace to load.

1. A new workspace has been created, and you will be able to navigate into this workspace. We will bring data from the different data sources into a Lakehouse and use the data from the Lakehouse to build our model and report on it.

## Exercise 2: Explore Copilot for Data Flows

Microsoft has integrated Copilot and other generative AI features into
Fabric to introduce new ways for you to transform and analyze data,
generate insights, and create visualizations and reports. You must
enable Copilot before you can use it. Copilot in Fabric is not available
in all regions. In this activity, you will integrate Copilot for data
analysis and visualization.

### Task 1: Ingest the dataset via Data Pipelines to Lakehouse File Section

1. Ensure you're logged into your Fabric workspace before proceeding.

1. Click on **+ New item (1)** button. In the pop-up window search for **Lakehouse (2)** in the search bar and click on **Lakehouse (3)**.

    ![Lakehouse](images1/media/exercise-1-img-28.png)

1. Copy the name **lakehouse<inject key="DeploymentID" enableCopy="false"/> (1)** and paste it in the **Name** field. Click on the **Lakehouse schemas (2)** checkbox and then click on the **Create (3)** button.

    ![Lakehouse](images1/media/exercise-1-img-93.png)

1. You will be navigated to the newly created lakehouse.

1. From the lakehouse page, select the **Get data (1)** option from the toolbar and select **New Dataflow Gen2 (2)** option.

    ![Lakehouse](images1/media/exercise-1-img-94.png)

1. Select the **Dataflow Gen2** in the menu, select the **Dataflow 1 (1)** then in the **Name** field, enter **North Wind Data (2)** and then press **Enter** from the keyboard.

    ![A screenshot of a computer AI-generated content may be incorrect.](images1/media/exercise-1-img-95.png)

1. On the **North Wind Data** dataflow gen2 **Home** tab, select **Get data (1)** >> **More (2)**.

    ![Get data dropdown menu options displayed.](images1/media/exercise-1-img-96.png)

1. In the **Choose data source** field, enter **OData (1)** to filter the possible data sources, and then select **OData (2).**

    ![Choose data source options](images1/media/exercise-1-img-97.png)

1. In the **Connect to data source** window, under **Connection settings**, in the **URL** field, copy and paste **https://services.odata.org/V4/Northwind/Northwind.svc/** and then select **Next.**

    ![Connect to data source options men](images1/media/exercise-1-img-9.png)

1. In the **Choose Data** window, select the following seven tables **Customers**, **Employees**, **Order_Details**, **Orders**, **Products**, **Shippers**, **Suppliers**, and then select **Create.** 

    ![A screenshot of a computer AI-generated content may be incorrect.](images1/media/exercise-1-img-10.png)

1. Check that the **Lakehouse (1)** selected is the one you created previously in the lab. You can hover to **(i)** box to see the lakehouse details. Load the data to the Lakehouse by selecting **Publish (2)**.

    ![A screenshot of a computer AI-generated content may be incorrect.](images1/media/exercise-1-img-98.png)

1. The query should look like the following:

    ![Queries created](images1/media/exercise-1-img-12.png)

In this task, you will ingest the dataset into the **Lakehouse File** section using Data Pipelines.

1. You will be navigated to your workspace. Select **North Wind Data** dataflow that you have created.

    ![Queries created](images1/media/exercise-1-img-99.png)

1. Select the **Customers** table, scroll to the right and examine the **Country** column. Notice that the countries include **Argentina** and **Mexico**.

    ![Customers table](images1/media/exercise-1-img-13.png)

1. On the **Power Query** toolbar, on the **Home** tab select **Copilot**.

    ![Power Query toolbar](images1/media/exercise-1-img-100.png)

    >**Note**: If the Copilot option isn't visible, try zooming out in your browser.

1. In the **Copilot** pane enter **Only keep South American customers** and then select **Send**.

    ![Copilto pane](images1/media/image13.png)

    >**Note**: Due to the nature of Copilot you may end up with differing results. You can also try **Only keep customers from South American countries**.

    The desired Applied Step text is :
    ```
    Table.SelectRows(#"Navigation 1", each List.Contains({"Mexico", "Brazil", "Argentina", "Chile", "Peru", "Colombia", "Venezuela", "Ecuador", "Bolivia", "Paraguay", "Uruguay", "Guyana", "Suriname"}, [Country]))
    ```
1. It will select Mexico only:

    ![A screenshot of a computer Description automatically generated](images1/media/exercise-1-img-15.png)

1. You can undo the step by selecting **Undo**. Afterwards, type: **Only keep South American customers**. If this step returns Mexico only, then insert the following step in the **transformation** tab:

    ```
    Table.SelectRows(#"Navigation 1", each List.Contains({"Mexico", "Brazil", "Argentina", "Chile", "Peru", "Colombia", "Venezuela", "Ecuador", "Bolivia", "Paraguay", "Uruguay", "Guyana", "Suriname"}, [Country]))
    ```
    ![Customers table](images1/media/exercise-1-img-102.png)

1. The **Country** column has been filtered and now only includes customers from South America.

    ![Country colum](images1/media/exercise-1-img-103.png)

1. In the **Copilot** pane, select **Undo** to revert the changes, as we want to use Copilot against the whole dataset.

    ![Country colum](images1/media/exercise-2-img-1.png)

1. In the **Copilot** pane, enter **How many customers in each country?** and then select **Send**.

    ![Copilot pane](images1/media/image17.png)

1. Sometimes, due to the nature of Copilot, you may end up with different results or errors. Select **Undo** in the Copilot chat.

    ![Example screen showing errors in the Country column.](images1/media/exercise-1-img-17.png)

    ![Undo button located above the Copilot pane.](images1/media/exercise-2-img-1.png)

    >**Note**: You need to have an accurate question, so you can also try: **What is the total number of customers in each country?**

    The desired Applied Step text is :

    ```
    Table.Group(#"Navigation 1", {"Country"}, {{"Total Customers", each Table.RowCount(_)}})
    ```

1. The query outputs a list displaying the number of customers per country.

    ![Query outputs](images1/media/image20.png)

1. In the **Copilot** pane, select **Undo** to revert the changes.

    ![Undo button on the Copilot pane ](images1/media/image21.png)

1. Select the **Order_Details** query, then in the **Copilot** pane, enter **Only keep orders whose quantities are above the median value** and then select **Send**.

    ![Copilot pane](images1/media/image22.png)

1. The **Quantity** column now displays all values above 20.

    ![Quantity column results](images1/media/exercise-2-img-2.png)

1. On the **Power Query** toolbar, on the **Home** tab, select **Advanced editor** under **Query** section.

    ![Power Query toolbar](images1/media/exercise-1-img-19.png)

1. Review the definition of the formula used in the query.

1. Select **Cancel** to exit the Advanced editor without making changes.

    ![Formula used in the query.](images1/media/exercise-1-img-20.png)

1. In the **Copilot** pane, select **Undo** to revert the changes.

    ![A screenshot of a computer AI-generated content may be incorrect.](images1/media/image26.png)


1. In the **Copilot** pane, enter **Create a new query with data for official public holidays for Australia in 2024** and then select **Send**.

    ![Copilot pane](images1/media/exercise-1-img-21.png)

    ![Table with the Query results](images1/media/exercise-2-img-3.png)

1. Australian public holidays have been added to the list. Review them as needed.

1. In the **Copilot** pane, select **Undo** to revert the changes.

    ![Table with the Query results](images1/media/exercise-2-img-4.png)

1. In the **Copilot** pane, enter the following text: **Create a new query with average monthly temperatures for Spain between 2022 and 2025. Display the Months in columns** and then select **Send**

    ![A screenshot of a computer ](images1/media/image29.png)

    ![Copilot pane](images1/media/exercise-1-img-23.png)

1. In the **Copilot** pane, select **Undo** to revert the changes.

    ![A screenshot of a computer AI-generated content may be incorrect.](images1/media/image30.png)

1. Select the **Orders** query.

1. In the **Copilot** pane, enter the following text: **Create a new query named "Value By Delivery Country" showing the order value aggregated by shipCountry** and then select **Send**

    ![A screenshot of a computer AI-generated content may be incorrect.](images1/media/exercise-1-img-24.png)

1. A table containing the **shipCountry** and **Order value aggregates** is displayed.

    ![Table containing the shipCountry](images1/media/exercise-1-img-25.png)

1. On the **Power Query** toolbar, on the **Home** tab, select **Advanced editor** under **Query** section to verify the correct formula.

    ![Power Querytoolbar](images1/media/exercise-1-img-19.png)

1. The value of Freight is being used. Should this be the intended behavior? Review Copilot's actions to confirm.

    ![Advance editor](images1/media/image34.png)

1. Select **Cancel** to close the Advanced editor, and then in the **Copilot** pane, select **Undo** to revert the changes.

1. Check the destination location of the dataset in the bottom right corner. 

    ![A screenshot of a computer AI-generated content may be incorrect.](images1/media/exercise-2-img-5.png)

1. Select **Publish** to publish your data to your lake house. Select your target Lakehouse connection before publishing. (Skip this step if you already published the dataset in an earlier step.)

### Task 2: Exploring Copilot capabilities in Fabric notebooks

In this exercise, you will explore Copilot capabilities in Fabric notebooks.

1. Open a new browser tab and go to
    [PowerBI](https://app.powerbi.com/)

2. Open the Fabric training Workspace you created previously.

3. In the lower left of the navigation pane for the workspace, select **Fabric**.

4. Select the bronze Lakehouse you created previously. 

5. On the menu for the Fabric workshop Lakehouse and then select **Open notebook** >> **New notebook**.

    ![Bronze lakehouse meny](images1/media/image38.png)

6. At the upper left of the page, select the notebook name. Replace the name with CopilotDemoNotebook and select **Enter**

    ![Notebook options](images1/media/image39.png)

7. On the menu for the notebook, select **Copilot**.

8. Select **Get Started**. Copilot adds a new cell to the notebook.

    ![Notebook menu](images1/media/image40.png)

    ![Notebook screen with Copilot pane on the side](images1/media/image41.jpeg)

9. Select **Run cell** (the triangular Play button) to install the packages that Copilot needs.

    ![Run cell screen](images1/media/image42.png)

    >**Note**: The following command may error out. Please copy and paste the entire code snippet to Copilot to get the correct code and replace it.

10. Move the cursor to the lower left of the last cell in the notebook and select **+ code** to add a new cell.

    ![Last cell of the notebook](images1/media/image43.png)

11. Enter the following code in the new cell and then select **Run cell**.

    >**Note**: This code specifies Azure storage access and connectivity information for the NYC Yellow Taxi open dataset. The last line of code filters the data to limit the volume of data that you'll ingest for this exercise.

    ```
    storage_account_name = "azureopendatastorage"
    container_name = "nyctlc"

    sas_token = r"" # Specify blank since container is public with anonymous access

    spark.conf.set("fs.azure.sas.%s.%s.blob.core.windows.net" % (container_name, storage_account_name),sas_token)

    directory = "yellow"
    year = 2016
    months = "1,2,3,4,5,6"
    wasbs_path = f"wasbs://{container_name}@{storage_account_name}.blob.core.windows.net/{directory}"
    nyc_yellowtaxi_df = spark.read.parquet(wasbs_path)

    filtered_nyc_yellowtaxi_df = nyc_yellowtaxi_df.filter(f"puYear = {year} AND puMonth IN ({months})")
    ```

    >**Warning**: As each cell runs, a message will indicate that Spark jobs are in progress. Once processing is complete, a message will confirm the success of the Spark jobs. If the code in a particular cell fails, processing for the other cells will not continue.*

12. Add another cell to the notebook. Add the following code to the new cell and then select the **Run cell** button. This code saves the data as a delta table in the Lakehouse.

    ```
    table_name = "nyc_yellowtaxi_raw"

    filtered_nyc_yellowtaxi_df.write.mode("overwrite").format("delta").saveAsTable(f"{table_name}")
    print(f"Spark dataframe (filtered_nyc_yellowtaxi_df) saved to a delta table: {table_name}")
    ```

    ![Notebook text](images1/media/image44.jpeg)

13. Add another cell to the notebook. Add the following code to the new cell and then select the **Run cell** button. This code runs a query to select and aggregate data.

    ```
    %%sql
    select puYear, puMonth, count(*) from nyc_yellowtaxi_raw group by puYear, puMonth order by puYear, puMonth
    ```

    >**Note**: The output dataset from the query should contain 6 rows, with each row showing the year, month, and the number of records for that period.

    ![Notebook with the output dataset](images1/media/image45.png)

14. Add another cell to the notebook. Add the following code to the new cell and then select the **Run cell** button. This code counts the number of records returned.

    ```
    filtered_nyc_yellowtaxi_df.count()
    ```
    ![Notebook screen](images1/media/image46.jpeg)

    During testing, 69,402,938 rows were returned.

15. At the bottom of the Copilot pane, enter the following prompt and then select **Enter**:

    Describe the structure of the filtered_nyc_yellowtaxi_df dataframe

    ![Copilot lateral pane](images1/media/image47.png)

    >**Warning**: Copilot for Fabric notebooks is in preview. During lab testing, we experienced mixed results when we submitted this prompt. In some cases, Copilot responds with a Python command that you can enter in a cell to describe the dataframe structure. The command should resemble the following:

    ```
    filtered_nyc_yellowtaxi_df.describe().show()
    ```

    In other cases, Copilot responded with "I'm unable to provide a description without more context or the structure of the dataset" or "I must decline to assist with that request." These issues should be resolved as this Copilot evolves.

    ![Filtered_nyc_yellowtaxi_df dataframe structure](images1/media/image48.png)

16. If Copilot does not create a command for you, add a new cell to the notebook. Add the following code to the new cell and then select the **Run cell** button:

    ```
    filtered_nyc_yellowtaxi_df.describe().show()
    ```
    ![](images1/media/image49.png)

17. At the bottom of the **Copilot** pane, enter the following prompt and then select **Enter**. Copilot should respond with a command that you can run to create the dataframe.

    ```
    Create a dataframe by loading data from nyc_yellowtaxi_raw table and sampling it with 1 percentage, count the rows in the dataframe and show the amount.
    ```
    ![Notebook screen](images1/media/image50.png)


18. Select **Insert code** to create a new cell in the Notebook. Run the cell:

    ![Notebook screen](images1/media/image51.jpeg)

19. If Copilot does not create the command for you, add a new cell to the notebook. Then, add the following code to the new cell and then select the **Run cell** button.

    ```
    %%code
    Create a dataframe by loading data from nyc_yellowtaxi_raw table and sampling it with 1 percentage, count the rows in the dataframe and show the amount.
    ```
**Important:** If you want to learn more about Chat-Magics, go to [Overview of chat-magics in Microsoft Fabric
notebook](https://learn.microsoft.com/en-us/fabric/get-started/copilot-notebooks-chat-magics)

# Exercise 3: Visualizing and gaining Insights using Copilot for Power BI

Let's leverage Copilot for Power BI to create interactive reports using curated data stored in OneLake. This exercise will guide you through the end-to-end process: connecting to your dataset, using Copilot for Power BI to explore data, and generating insightful visualizations with
minimal manual effort.

**Power BI:** This integration incorporates generative AI to
automatically build reports based on topics you select or prompts you
create.

In this exercise, you'll explore the capabilities of Copilot in Data Factory. The Power BI Copilot will be covered in a later exercise within this lab.

Prerequisite:

- Ensure that the Power BI Desktop application is installed on your local machine.

- Ensure Copilot for Power BI is enabled.

- You must have the necessary permission to read the curated dataset from OneLake.

- Copilot is turned on by default in Fabric and now generally available, however it is not supported in sovereign clouds due to GPU availability. 

In this exercise, you will use Copilot in Power BI to generate reports and enhance your data analysis process.

### Task 1: Connect to a Fabric dataset and create visualizations using Copilot

1. Open the **Power BI** application and select **Blank Report** to create a new dashboard. 

    ![Power BI menu](images1/media/image52.png)

2. Ensure the Copilot button is enabled.  

    ![](images1/media/image53.png) 

3. Select **Get Data** >> **More...** to connect to the dataset needed for your report.

4. Select **Microsoft Fabric** and then select **Lakehouses** >> **Connect**

    ![Get Data menu](images1/media/image54.png)

5. Select the Lakehouse created in the earlier activity and select **Connect to SQL endpoint** by selecting the arrow next to **Connect**.

    ![Lakehouse view](images1/media/image55.png)

    ![Connect option](images1/media/image56.png)

6. Then, login with your odl credentials.

6. A navigator window appears to select the targeted dataset. Select the following entities and then select **Load**:

    Customers, employees, orders, order_details, products, shippers 

    ![Targeted dataset](images1/media/image57.png)

7. Create a real-time connection to your Lakehouse by selecting
    **Direct Query:**

    ![A screenshot of a computer AI-generated content may be incorrect.](images1/media/image58.png)

8. Once connected, let\'s use Copilot to summarize our data. Select the **Prompt Guide**, then select **"Give me an executive summary."**

9. Next, select **"Suggest content for a new report page"** based on the semantic model.

10. Select **Sales Performance** to generate a report analyzing order details, unit prices, and quantities sold.

### Task 2:  Create DAX queries and update measures descriptions using Copilot

Let's use Dax query copilot to generate a new measure for **total Sales after Discount (measure)** and update the description of the current measure.

1. Select on **Dax query view**, then **Copilot (Preview).**

    ![A screenshot of a computer AI-generated content may be incorrect.](images1/media/image59.png)

    ![A screenshot shows a Copilot prompt in Dax query view. The Copilot prompt field has the text "Ask Copilot to write or edit a DAX query or ask a related question."](images1/media/image60.png)
 

2. Ensure that the 'Measure Descriptions with Copilot' feature is enabled. Navigate to **File >> Options and settings >> Options >> Preview Features**, then enable **Measure descriptions with Copilot** at the bottom of the list.

    ![A screenshot of a computer AI-generated content may be incorrect.](images1/media/image61.png)

    ![A screenshot of a computer AI-generated content may be incorrect.](images1/media/image62.png)

3. Navigate to the **Model** and select the **new measure** created. 

4. Navigate to the **Properties** section for the model and select **Create with Copilot (preview).** Copilot generates a new measure description in a few seconds.

    ![A screenshot of a computer AI-generated content may be incorrect.](images1/media/image63.png)

5. Review the measure description to ensure that it aligns with your model. Select **Keep it** to save the description.

    ![A screenshot of a computer AI-generated content may be incorrect.](images1/media/image64.png)

    Now, let's publish the report to the Power BI service so that consumers can visualize and derive insights from it.

6. Select **File** and then select **Publish.** 

    ![](images1/media/image65.png)

7. Select **Save** and then save the report as **Northwind Order Analysis** under your desired location on your machine.

8. Publish it under **'My Workspace'** or the workspace created during Activity 7.

### Task 3: Explore Copilot for PowerBI as a report consumer(optional)

1. Open your published report by selecting [Microsoft Fabric](https://app.fabric.microsoft.com/). Navigate to your workspace and then select the **Northwind Order Analysis.**

    ![A screenshot of a computer AI-generated content may be incorrect.](images1/media/image66.png)

    ![A screenshot of a computer AI-generated content may be incorrect.](images1/media/image67.png)

2. Select the **Copilot** logo on the top-right and open the prompt guide. 

    ![A screenshot of a computer AI-generated content may be incorrect.](images1/media/image68.png)

3. Select **Summarize visual on the page** to gain insights from each visual.

    ```
    The total sales amount to 56.5K.

    Sales by region show that each region, including AK, BC, CA, Co. Cork, DF, ID, Isle of Wight, Lara, MT, NM, Nueva Esparta, OR, Québec, RJ, SP, Táchira, WA, and WY, has a sales value of 56.5K.

    Sales by product reveal a wide range of sales values. Product 38 had the highest sales at 5.9K, accounting for 10.45% of the total sales. The lowest sales were for Product 48, with a value of 71.4. Other notable products include Product 29 with sales of 3.71K and Product 59 with sales of 2.76K.

    The calculated insights highlight that Product 38's sales were 8,166.67% higher than Product 48's sales. The sales values across all 77 products ranged from 71.4 to 5.9K.
    ```

4. Select "**Answer questions for leadership**" to prepare for your upcoming meeting with leadership.

    ```
    The Northwind Order Analysis report provides an overview of sales performance across different products and regions. The total sales amount to 56.5K. Sales by region indicate that each region, including AK, BC, CA, Co. Cork, DF, ID, Isle of Wight, Lara, MT, NM, Nueva Esparta, OR, Québec, RJ, SP, Táchira, WA, and WY, has a uniform sales value of 56.5K.

    Sales by product show a wide range of sales values. Product 38 had the highest sales at 5.9K, accounting for 10.45% of the total sales. The lowest sales were for Product 48, with a value of 71.4. Other notable products include Product 29 with sales of 3.71K and Product 59 with sales of 2.76K.

    The calculated insights highlight that Product 38's sales were 8,166.67% higher than Product 48's sales. The sales values across all 77 products ranged from 71.4 to 5.9K.

    ### Questions Leadership Could Ask:
    - Why do all regions have the same sales value of 56.5K?
    - What factors contributed to Product 38 achieving the highest sales?
    - How can we improve sales for products with lower sales values, such as Product 48?
    - Are there any seasonal trends or external factors affecting the sales distribution across products?
    - What strategies can be implemented to increase overall sales performance?
    - How do the sales figures compare to previous periods or forecasts?
    - What are the key drivers behind the sales performance of top-selling products like Product 38 and Product 29?
    - Are there any specific regions or products that require targeted marketing efforts?
    ```
5. Select **Edit.**

    ![Toolbar](images1/media/image69.png)

6. Ask Copilot to generate a report to monitor the current inventory by submitting the following prompt: *Create a report monitoring the product inventory.*

    ![Toolbar](images1/media/image70.png)

7. Save the report so any other report consumer has access to it. 

## You have successfully completed the lab.