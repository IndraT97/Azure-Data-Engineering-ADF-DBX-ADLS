# Azure-Data-Engineering (ADF-DBX-CI/CD)
<a name="readme-top"></a>
# Project Objective
**Ingesting on-premise (SQL and SFTP) data and transforming it using Azure Data Factory, Databricks followed by analyzing and reporting using PowerBI**

In this project the main aim is to understand the Flow of data from On-Prem to Cloud Platform while transforming the data to get the final set of tables for further analysis

In real-time scenarios, organizations often grapple with petabytes of structured data dispersed across numerous on-premises locations. Leveraging cloud solutions streamlines data processing, circumventing the limitations and inefficiencies of current infrastructure. This shift not only sidesteps the extensive planning, time, and financial investment required for new infrastructure setup but also mitigates the risk of such investments becoming obsolete. Ultimately, transitioning to the cloud facilitates swift, cost-effective achievement of data processing objectives with minimal complexity

<!-- TABLE OF CONTENTS -->
<details>
  <summary>Table of Contents</summary>
  <ol>
    <li>
      <a href="#about-the-project">About The Project</a>
      <ul>
        <li><a href="#built-with">Built With</a></li>
      </ul>
    </li>
    <li>
      <a href="#getting-started">Getting Started</a>
      <ul>
        <li><a href="#prerequisites">Prerequisites</a></li>
        <li><a href="#installation">Installation</a></li>
      </ul>
    </li>
    <li><a href="#usage">Usage</a></li>
    <li><a href="#roadmap">Roadmap</a></li>
    <li><a href="#contributing">Contributing</a></li>
    <li><a href="#license">License</a></li>
    <li><a href="#contact">Contact</a></li>
    <li><a href="#acknowledgments">Acknowledgments</a></li>
  </ol>
</details>

# Architecture

### Overall Project Flow 
The depicted architecture illustrates the data migration from on-premises to the cloud, alongside the various stages of data transformation that occur throughout the process

<p align="center">
  <img src="https://github.com/IndraT97/Azure-Data-Engineering-ADF-DBX-CI-CD/blob/master/Images/Project%20Architecture.png">
</p>

### Linked Serive Architecture
The architecture outlined showcases the network of established links connecting on-premises data sources with cloud-based services, as well as the interconnectivity between various cloud services through Linked Services with the help of SAMI (System assigned managed Identity) and SPN (Service Principal)

<p align="center">
  <img src="https://github.com/IndraT97/Azure-Data-Engineering-ADF-DBX-CI-CD/blob/master/Images/Linked_Service.png">
</p>

The architecture provides three distinct methods for creating interconnectivity between various cloud services via Linked Services, each with its own unique advantages and strategic value

* System Assigned Managed Identity
* User Assigned Managed Identity
* Access Code

### MetaData Flow (Data Ingestion)
* The architecture highlighted delineates the pathways of Metadata exchange and the actual movement of Structured Data from On-Premises Data Sources
* The direction of Metadata and actual Data Flow is reciprocal
* In this context, the Metadata encompasses all necessary connection details for interfacing with On-Premises Sources, along with schema table information for each of the three storage layers

<p align="center">
  <img src="https://github.com/IndraT97/Azure-Data-Engineering-ADF-DBX-CI-CD/blob/master/Images/MetaData%20Flow.png">
</p>

### General Industry Pratice (Data Ingestion) 

* In real-world scenarios, an Azure Virtual Machine with Self-Hosted Integration Runtime (SHIR) is set up to serve as a conduit between on-premises environments and Azure serices (Azure Data Factory (ADF))
* Ports Azure VM are configured to allow communication with on-premises data sources, assuming that all on-premises resources are protected by a common firewall

<p align="center">
  <img src="https://github.com/IndraT97/Azure-Data-Engineering-ADF-DBX-CI-CD/blob/master/Images/Data%20Flow%20(Onprem%20to%20ADF%20Realtime%20flow).png">
</p>

<p align="right">(<a href="#readme-top">back to top</a>)</p>

# Azure Services used in the Project

<p>
  <a href="https://learn.microsoft.com/en-us/azure/devops/?view=azure-devops" target="_blank" rel="noreferrer">
    <img src="https://code.benco.io/icon-collection/azure-icons/Azure-DevOps.svg" alt="Azure DevOps" width="25" height="25" style="vertical-align:middle;"/>
  </a>
  <span style="vertical-align:middle; line-height:normal; display:inline-block; margin-left:5px;">Azure Devops</span>
</p>

<p>
  <a href="https://learn.microsoft.com/en-us/azure/devops/?view=azure-devops" target="_blank" rel="noreferrer">
    <img src="https://code.benco.io/icon-collection/azure-icons/Data-Factory.svg" alt="ADF" width="25" height="25" style="vertical-align:middle;"/>
  </a>
  <span style="vertical-align:middle; line-height:normal; display:inline-block; margin-left:5px;">Azure Devops</span>
</p>

<p>
  <a href="https://learn.microsoft.com/en-us/azure/devops/?view=azure-devops" target="_blank" rel="noreferrer">
    <img src="https://code.benco.io/icon-collection/azure-icons/Azure-DevOps.svg" alt="Azure DevOps" width="30" height="30" style="vertical-align:middle;"/>
  </a>
  <span style="vertical-align:middle; line-height:normal; display:inline-block; margin-left:5px;">Azure Devops</span>
</p>

<p>
  <a href="https://learn.microsoft.com/en-us/azure/devops/?view=azure-devops" target="_blank" rel="noreferrer">
    <img src="https://code.benco.io/icon-collection/azure-icons/Azure-DevOps.svg" alt="Azure DevOps" width="30" height="30" style="vertical-align:middle;"/>
  </a>
  <span style="vertical-align:middle; line-height:normal; display:inline-block; margin-left:5px;">Azure Devops</span>
</p>

<p>
  <a href="https://learn.microsoft.com/en-us/azure/devops/?view=azure-devops" target="_blank" rel="noreferrer">
    <img src="https://code.benco.io/icon-collection/azure-icons/Azure-DevOps.svg" alt="Azure DevOps" width="30" height="30" style="vertical-align:middle;"/>
  </a>
  <span style="vertical-align:middle; line-height:normal; display:inline-block; margin-left:5px;">Azure Devops</span>
</p>

<p>
  <a href="https://learn.microsoft.com/en-us/azure/devops/?view=azure-devops" target="_blank" rel="noreferrer">
    <img src="https://code.benco.io/icon-collection/azure-icons/Azure-DevOps.svg" alt="Azure DevOps" width="30" height="30" style="vertical-align:middle;"/>
  </a>
  <span style="vertical-align:middle; line-height:normal; display:inline-block; margin-left:5px;">Azure Devops</span>
</p>

<p>
  <a href="https://learn.microsoft.com/en-us/azure/devops/?view=azure-devops" target="_blank" rel="noreferrer">
    <img src="https://code.benco.io/icon-collection/azure-icons/Azure-DevOps.svg" alt="Azure DevOps" width="30" height="30" style="vertical-align:middle;"/>
  </a>
  <span style="vertical-align:middle; line-height:normal; display:inline-block; margin-left:5px;">Azure Devops</span>
</p>

<p>
  <a href="https://learn.microsoft.com/en-us/azure/devops/?view=azure-devops" target="_blank" rel="noreferrer">
    <img src="https://code.benco.io/icon-collection/azure-icons/Azure-DevOps.svg" alt="Azure DevOps" width="30" height="30" style="vertical-align:middle;"/>
  </a>
  <span style="vertical-align:middle; line-height:normal; display:inline-block; margin-left:5px;">Azure Devops</span>
</p>

<p align="right">(<a href="#readme-top">back to top</a>)</p>

## Components and Data flow:

•	SQL Server: On-premises Database which needs to be transformed. The SQL server was connected to Azure data factory using the self-hosted Integration runtime. The tables in the AdventureWorksLT2017 database was moved and transformed using Data factory into the Azure Data Lake storage. An user was created for the AdventureWorksLT2017 Database and the password was stored in the Key vault and was used by Data factory.

![image](https://github.com/DataCounsel/Azure-Data-Engineering/assets/71335870/1f0db421-328d-43d5-a5ef-42fdb02b0f05)

![image](https://github.com/DataCounsel/Azure-Data-Engineering/assets/71335870/aa45e31b-ee0c-40d9-b1da-fd5ca543de88)

•	Azure Data Factory: Used for ingesting data from SQL Server and Storing it in Azure Data Lake using automated pipelines and setup to perform initial transformations on the incoming tables. The ADF resource was added to the access control(IAM) policies of the Data lake so that it is able to perform read, write functions. The tables were converted to parquet format and had the default snappy compression. The tables were stored in their corresponding folder structure which was automated using the pipeline. The diagram below show the pipeline which ingests the data from the on-premises server and carries out the tasks in the pipeline to produce the final transformed data in the gold container.

![copy_all_tables_pipelineRun](https://github.com/DataCounsel/Azure-Data-Engineering/assets/71335870/0e674a62-817c-4ee4-b26a-3abc0f8efa65)


•	Azure Data Lake Gen 2: Used for storage of data. Three containers have been created Bronze, Silver and Gold. The three layers represent the stages of business logic and requirements. The initial data ingested from SQL Server is transformed to parquet format as it provides significant performance, storage, and query optimization benefits in big data processing and analytics scenarios and stored in the bronze container.  The next level transformation is performed on the bronze data and stored in the silver container. The final transformation is performed on the silver layer and the data is stored in the gold container. The delta lake abstraction layer has been used on the parquet format files for storing the data in the gold and silver containers to allow for versioning. The data in the gold layer is ideal for reporting and analysis. It can be consumed by Azure Synapse Analytics which in turn can be connected to PowerBI for creating visualizations.

![ADLS_IAM_Roles](https://github.com/DataCounsel/Azure-Data-Engineering/assets/71335870/98eb428b-95d8-4c41-af53-b3d460723f0f)

![bronze-silver-gold_containers](https://github.com/DataCounsel/Azure-Data-Engineering/assets/71335870/0c97afe5-f176-4797-8581-6ca5c7ef3470)

![delta_lake_format_gold](https://github.com/DataCounsel/Azure-Data-Engineering/assets/71335870/8af32197-7d36-47d2-bae3-5bd4d95ad8ce)

![gold_files](https://github.com/DataCounsel/Azure-Data-Engineering/assets/71335870/32008f97-614f-4880-ba1c-7a8c651054a7)

•	Databricks: Databricks was the compute engine of choice as it provides the power of Apache spark without the requirement for setting up the environment and since it is cloud native it was well suited for the requirement of this project. It was convenient to access the storage using the credential passthrough feature as the email ID being used for this project was already added to the IAM policy of the data lake. The Data Factory could be connected by using an access token generated from Databricks and saving it as a secret in the Key vault and the storage was mounted using the ‘mount storage’ notebook.
There were two levels of transformation performed, first transformation was performed on the data in the bronze container. The output from this layer was stored in the silver container. The second level was performed on the silver data and was stored in the gold container. The idea behind this is in a real business scenario there may be multiple levels of transformation and the final transformed data which is the data in the gold container is used for analytics and reporting. The data in the AdventureWorksLT table is already structured and is mostly readily usable but for the purpose of demonstration the ModifiedDate column has been converted from UTC timestamp to the YYYY-MM-DD format in the bronze to silver transformation and In the silver to gold transformation step, the column names have been changed from two words joined together and each starting with a capital letter to being separated by an ‘_’.

![Bronze_to_silver](https://github.com/DataCounsel/Azure-Data-Engineering/assets/71335870/499a2584-aaa2-4f44-8135-4885b26825a4)


![silver-to-gold](https://github.com/DataCounsel/Azure-Data-Engineering/assets/71335870/9ce0517e-c12d-4877-a3b2-c770ec79ed1f)



•	Azure Synapse Analytics: This was chosen as it integrates data warehousing, big data, and data integration capabilities into a single platform. It is built on a massively parallel processing architecture and an extremely robust analytics tool which shares many functionalities with Azure Data factory. It makes setting up a database and enables querying it in a very short span of time. Costs can be optimized as it supports on-demand provisioning and automatic pause and resume capabilities. It can be easily integrated with the Azure data lake and other Azure services.


![synapse1](https://github.com/DataCounsel/Azure-Data-Engineering/assets/71335870/5c20a560-fb69-4f52-b522-2f1778be8336)

![synapse2](https://github.com/DataCounsel/Azure-Data-Engineering/assets/71335870/1e7c897e-9445-4797-a54a-63fa6056dc3a)

![synapse3](https://github.com/DataCounsel/Azure-Data-Engineering/assets/71335870/4a2fb43a-258f-4ee6-92a7-d64c9c53a053)


PowerBI : Now that the data can be analyzed using Azure Synapse. We can use that to create dashboards. In this project I have used PowerBI to accomplish that. PowerBI needs to be connected to the the synapse database. We can connect using the Azure Synapse option under Azure from the Data Source option in PowerBI and then entering the severless endpoint of the Synapse in the source and the database name. We can connect using the Sign in option instead of using credentials. This requires the same email address be used for the Azure account and PowerBI sign in. Else, a guest can be invited using Azure active directory and required permission be added to that user. That is the mode that I had to use in this case. The data can be loaded directly onto the device or using direct query. Once the data is loaded it needs to be modelled using the models tab. The relationships generated by PowerBI are usually not correct and it needs to be done manually. This can be achieved using the manage relationship option from the visualizations in ribbon. Once the relationships are set the cross-filter direction needs to be set to both to allow all the fields to be updated across all visualizations in PowerBI. 


![connect_table_powerbi](https://github.com/DataCounsel/Azure-Data-Engineering/assets/71335870/4a184896-eea1-4257-9342-b28fc57e45e4)
Database connected

![table_data_load_powerbi](https://github.com/DataCounsel/Azure-Data-Engineering/assets/71335870/16300aad-a37c-42f0-8852-f175e37b74db)

Data Loaded

![manage_relationship_powerbi](https://github.com/DataCounsel/Azure-Data-Engineering/assets/71335870/2d906536-9cc9-43e4-ac0e-3d24b1681a00)
Manage Relationship

## Concept to be covered in next project

* RBAC
* Unity Catelog
* Various level of Ownership
* ADF Git hub Versioning
* DBX comman command used in Data Cleaning Activities
* Few more interesting facts
