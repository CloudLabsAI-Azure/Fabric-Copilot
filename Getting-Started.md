# Fabric Copilot

## Overall Estimated Duration: 4 hours

## Overview

This hands-on lab introduces participants to Microsoft Fabric and its Copilot features. It covers setting up a Fabric workspace, ingesting data via pipelines, using Copilot in notebooks for data transformation, and leveraging Copilot in Power BI to generate visualizations and DAX queries—streamlining analytics through AI-powered assistance.

## Objective

This lab is designed to provide participants with practical experience in utilizing Microsoft Fabric and its Copilot feature to create workspaces, ingest and transform data, and analyze data within a warehouse.

- **Create a Fabric workspace**: Sign up for the Microsoft Fabric Trial and set up a workspace to explore data integration, analytics, and visualization tools..
- **Ingest data with a pipeline in Microsoft Fabric**: Implement ETL/ELT solutions using pipelines and Apache Spark to load and transform data into a Lakehouse for analysis.
- **Data Engineering - Ingest Data in Fabric with Fabric Copilot**: Utilize Fabric Copilot and Dataflow Gen2 to create a data pipeline, leveraging natural language for data ingestion and transformation.
- **Data Warehouse - Analyze Data in a Warehouse with Fabric Copilot**: Analyze data in a warehouse by connecting to data sources, running queries, and visualizing insights using Fabric Copilot to enhance decision-making.

## Prerequisites

Participants should have the following prerequisites:

- **Basic understanding of data management and analytics**: Familiarity with data concepts and terminology will aid in navigating Microsoft Fabric's features.
- **Familiarity with Microsoft 365 tools**: Experience with common Microsoft 365 applications, such as Excel and Power BI, will be beneficial.
- **Azure subscription with appropriate permissions**: Access to an Azure account with the necessary permissions to create and manage resources within Microsoft Fabric is required.
- **Access to Microsoft Fabric**: Participants should have access to Microsoft Fabric with Copilot enabled to perform the exercises.
- **Knowledge of SQL and data visualization**: Understanding SQL queries and data visualization techniques will assist in executing the lab tasks effectively.

## Architechture

The architecture for the **Microsoft Fabric with Copilot** lab enables end-to-end data integration, analytics, and visualization workflows using Fabric's advanced tools and AI capabilities. It begins with creating a dedicated **workspace** to manage resources and collaborate effectively. **Data ingestion** is facilitated through **pipelines** and **Spark-powered** notebooks, storing data in a **Lakehouse** for analysis. Structured data is processed in a **data warehouse**, where **tables** and **data models** are created for efficient querying and reporting. **Fabric Copilot** enhances automation by enabling natural language interactions for data ingestion, transformation, and report generation. This streamlined architecture provides scalability, productivity, and actionable insights, supporting complex data engineering and analytics scenarios.

## Architechture Diagram

![](Images/fabricarc.png)

## Explanation of Components

The architecture for this lab involves several key components:

- **Microsoft Fabric**: A comprehensive data analytics platform that integrates tools for data engineering, analytics, and visualization, including AI-powered capabilities like Fabric Copilot.

- **Workspace**: A collaborative environment within Microsoft Fabric where resources, projects, and tools are managed, enabling efficient organization and teamwork.

- **Lakehouse**: A unified data storage architecture combining the benefits of data lakes and data warehouses, optimized for both raw and structured data.  

- **Pipeline**: A sequence of data processing steps used to implement ETL (Extract, Transform, Load) or ELT (Extract, Load, Transform) workflows to move and process data.  

- **Notebook**: An interactive tool in Fabric that allows users to write and execute Apache Spark code for data analysis and transformation at scale.  

- **SQL**: A programming language used to query, manipulate, and analyze data stored in tables within the Lakehouse or other data stores.  

- **Visual Query**: A graphical interface that enables users to design and execute data queries without writing code, making data exploration more accessible.

- **Report**: A structured presentation of data insights, often with visualizations like charts and graphs, created for stakeholders to analyze results.

- **Fabric Copilot**: An AI-driven assistant in Microsoft Fabric that helps automate tasks such as data ingestion, transformation, and reporting using natural language commands.

- **Dataflow Gen2**: A modernized data pipeline tool in Fabric that enables the creation of scalable and automated workflows for ingesting and transforming data.

- **Data Warehouse**: A centralized, structured repository optimized for querying and reporting, used for storing processed data ready for analysis.

- **Table**: A structured arrangement of data in rows and columns, used to organize and store information in databases or warehouses.  

- **Data Model**: A structured representation of data and its relationships, designed to enhance analytical queries and reporting efficiency.  

## Getting Started with the Lab
 
Welcome to your Fabric Copilot Workshop! We've prepared a seamless environment for you to explore and learn about Azure services. Let's begin by making the most of this experience:
 
## Accessing Your Lab Environment
 
Once you're ready to dive in, your virtual machine and lab guide will be right at your fingertips within your web browser.

## Virtual Machine & Lab Guide
 
Your virtual machine is your workhorse throughout the workshop. The lab guide is your roadmap to success.

![](./images/overview-14.png) 

## Exploring Your Lab Resources
 
To get a better understanding of your lab resources and credentials, navigate to the **Environment** tab.
 
![](./images/overview-15.png) 
 
## Utilizing the Split Window Feature
 
For convenience, you can open the lab guide in a separate window by selecting the **Split Window** button from the Top right corner.
 
![](./images/overview-16.png) 
 
## Managing Your Virtual Machine
 
Feel free to start, stop, or restart your virtual machine as needed from the **Resources** tab. Your experience is in your hands!

![](./images/overview-17.png) 

## Login to Azure Portal

1. In the JumpVM, click on the Azure portal shortcut of the Microsoft Edge browser from the desktop.

    ![](./images/overview-6.png) 
   
1. On the **Sign in to Microsoft Azure** tab you will see a login screen, enter the following email/username and then click on **Next**. 
   * Email/Username: **<inject key="AzureAdUserEmail" enableCopy="true"/>** 
   
     ![](./images/overview-1.png) 
     
1. Now enter the following password and click on **Sign in**.
   * Password: **<inject key="AzureAdUserPassword" enableCopy="true"/>**
   
     ![](./images/overview-2.png) 

1. On **Action Required** pop-up, click on **Ask later**. Incase if you dont get the option to Skip this, then please follow the below steps to setup MFA.

     ![](./images/ask-later.png "Ask Later")

## Steps to Proceed with MFA Setup if "Ask Later" Option is Not Visible [Optional]

1. On **Action Required** pop-up, click on **Next**.

     ![](./images/mfa1.png "Ask Later")

1. In the Keep your account secure window, The window that appears and the steps that follow are for the Microsoft Authenticator app method. Select **Next**.

   ![](./images/mfa2.png "Ask Later")

    >**NOTE:** If you don't have the Microsoft Authenticator app installed on your mobile device , select **Download** now and follow the steps.

1. On the Set up your account page opens, select **Next.**

   ![](./images/mfa3.png "Ask Later")

1. Scan the QR code through your phone. On the phone, inside the Authenticator app select Work or school account, and scan the QR code. Select **Next**.

   ![](./images/mfa4.png "Ask Later")

1. On the Keep your account secure page. Enter the code, which is shown on the Authenticator app.

   ![](./images/mfa5.png "Ask Later")

1. Once the code is entered. click **Next**

   ![](./images/mfa6.png "Ask Later")

1. Select Done, on the Success! page.

    ![](./images/mfa7.png "Ask Later")

1. If you see the pop-up **Stay Signed in?**, click **Yes**.

1. If you see the pop-up **You have free Azure Advisor recommendations!**, close the window to continue the lab.

1. If a **Welcome to Microsoft Azure** popup window appears, click **Cancel** to skip the tour.

## Support Contact

The CloudLabs support team is available 24/7, 365 days a year, via email and live chat to ensure seamless assistance at any time. We offer dedicated support channels tailored specifically for both learners and instructors, ensuring that all your needs are promptly and efficiently addressed.

Learner Support Contacts:

- Email Support: cloudlabs-support@spektrasystems.com
- Live Chat Support: https://cloudlabs.ai/labs-support

Now, click on **Next** from the lower right corner to move on to the next page.

![](./images/overview-13.png)

### Happy Learning!!
