# Azure-Data-Engineering (ADF-DBX-ADLS)
<a name="readme-top"></a>
# Project Objective
**Ingesting on-premise (SQL and SFTP) data and transforming it using Azure Data Factory, Databricks followed by analyzing and reporting using PowerBI**

In this project the main aim is to understand the Flow of data from On-Prem to Cloud Platform while transforming the data to get the final set of tables for further analysis

In real-time scenarios, organizations often grapple with petabytes of structured data dispersed across numerous on-premises locations. Leveraging cloud solutions streamlines data processing, circumventing the limitations and inefficiencies of current infrastructure. This shift not only sidesteps the extensive planning, time, and financial investment required for new infrastructure setup but also mitigates the risk of such investments becoming obsolete. Ultimately, transitioning to the cloud facilitates swift, cost-effective achievement of data processing objectives with minimal complexity

# Table of Content
<details>
  <summary>Table of Content</summary>
  <ol>
    <li><a href="#project-architecture">Project Architecture</a>
      <ul>
        <li><a href="#overall-project-flow">Overall Project Flow</a></li>
        <li><a href="#Linked-Serive-Architecture">Linked Service Architecture</a></li>
        <li><a href="#metadata-flow-data-ingestion">MetaData Flow (Data Ingestion)</a></li>
        <li><a href="#General-Industry-Practice-Data-Ingestion">General Industry Practice (Data Ingestion)</a></li>
      </ul>
    </li>
    <li><a href="#azure-services-used-in-the-project">Azure Services used in the Project</a></li>
    <li><a href="#transformation-activities-in-adf">Transformation Activities in ADF</a></li>
    <li><a href="#concept-to-be-covered-in-next-project">Concept to be covered in next project</a></li>
  </ol>
</details>

# Project Architecture

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

Note : Databricks Delta lake is logical storage layer for Databricks even though we are using ADLS Gen 2 for actual storage. 
So whenever we want to establish connection between ADF to Databricks we need to create two linked services. 1 - ADF and Databricks Compute and 2 - ADF and Databricks Deltalake   

### MetaData Flow (Data Ingestion)
* The architecture highlighted delineates the pathways of Metadata exchange and the actual movement of Structured Data from On-Premises Data Sources
* The direction of Metadata and actual Data Flow is reciprocal
* In this context, the Metadata encompasses all necessary connection details for interfacing with On-Premises Sources, along with schema table information for each of the three storage layers

<p align="center">
  <img src="https://github.com/IndraT97/Azure-Data-Engineering-ADF-DBX-CI-CD/blob/master/Images/MetaData%20Flow.png">
</p>

### General Industry Practice (Data Ingestion) 

* In real-world scenarios, an Azure Virtual Machine with Self-Hosted Integration Runtime (SHIR) is set up to serve as a conduit between on-premises environments and Azure serices (Azure Data Factory (ADF))
* Ports Azure VM are configured to allow communication with on-premises data sources, assuming that all on-premises resources are protected by a common firewall

<p align="right">(<a href="#readme-top">back to top</a>)</p>

<!-- Azure Services used in the Project -->
# Azure Services used in the Project

<p>
  <a href="https://learn.microsoft.com/en-us/azure/storage/blobs/data-lake-storage-introduction" target="_blank" rel="noreferrer">
    <img src="https://code.benco.io/icon-collection/azure-icons/Data-Lake-Storage-Gen1.svg" alt="ADLS Gen2" width="25" height="25" style="vertical-align:middle;"/>
  </a>
  <span style="vertical-align:middle; line-height:normal; display:inline-block; margin-left:5px;">ADLS Gen2</span>
</p>

<p>
  <a href="https://learn.microsoft.com/en-us/azure/azure-resource-manager/management/manage-resource-groups-portal" target="_blank" rel="noreferrer">
    <img src="https://code.benco.io/icon-collection/azure-icons/Resource-Groups.svg" alt="Azure Resource Group" width="30" height="30" style="vertical-align:middle;"/>
  </a>
  <span style="vertical-align:middle; line-height:normal; display:inline-block; margin-left:5px;">Azure Resource Group</span>
</p>

<p>
  <a href="https://learn.microsoft.com/en-us/azure/virtual-network/" target="_blank" rel="noreferrer">
    <img src="https://code.benco.io/icon-collection/azure-icons/Virtual-Networks-(Classic).svg" alt="Azure Virtual Network" width="30" height="30" style="vertical-align:middle;"/>
  </a>
  <span style="vertical-align:middle; line-height:normal; display:inline-block; margin-left:5px;">Azure Virtual Network</span>
</p>

<p>
  <a href="https://learn.microsoft.com/en-us/azure/virtual-network/" target="_blank" rel="noreferrer">
    <img src="https://code.benco.io/icon-collection/azure-icons/Data-Factory.svg" alt="ADF" width="30" height="30" style="vertical-align:middle;"/>
  </a>
  <span style="vertical-align:middle; line-height:normal; display:inline-block; margin-left:5px;">Azure Data Factory</span>
</p>

<p>
  <a href="https://learn.microsoft.com/en-us/azure/databricks/" target="_blank" rel="noreferrer">
    <img src="https://www.vectorlogo.zone/logos/databricks/databricks-icon.svg" alt="DBX" width="30" height="30" style="vertical-align:middle;"/>
  </a>
  <span style="vertical-align:middle; line-height:normal; display:inline-block; margin-left:5px;">Azure Databricks</span>
</p>

<p>
  <a href="https://learn.microsoft.com/en-us/azure/data-factory/create-self-hosted-integration-runtime?tabs=data-factory" target="_blank" rel="noreferrer">
    <img src="https://code.benco.io/icon-collection/azure-icons/App-Service-Plans.svg" alt="Azure SHIR" width="30" height="30" style="vertical-align:middle;"/>
  </a>
  <span style="vertical-align:middle; line-height:normal; display:inline-block; margin-left:5px;">Azure SHIR</span>
</p>

<p>
  <a href="https://learn.microsoft.com/en-us/azure/logic-apps/" target="_blank" rel="noreferrer">
    <img src="https://code.benco.io/icon-collection/azure-icons/Logic-Apps.svg" alt="Azure Logic App" width="30" height="30" style="vertical-align:middle;"/>
  </a>
  <span style="vertical-align:middle; line-height:normal; display:inline-block; margin-left:5px;">Azure Logic App</span>
</p>

<p>
  <a href="https://learn.microsoft.com/en-us/azure/key-vault/" target="_blank" rel="noreferrer">
    <img src="https://code.benco.io/icon-collection/azure-icons/Key-Vaults.svg" alt="Azure Key Vault" width="30" height="30" style="vertical-align:middle;"/>
  </a>
  <span style="vertical-align:middle; line-height:normal; display:inline-block; margin-left:5px;">Azure Key Vault</span>
</p>

<p>
  <a href="https://learn.microsoft.com/en-us/azure/devops/?view=azure-devops" target="_blank" rel="noreferrer">
    <img src="https://code.benco.io/icon-collection/azure-icons/Azure-DevOps.svg" alt="Azure DevOps" width="25" height="25" style="vertical-align:middle;"/>
  </a>
  <span style="vertical-align:middle; line-height:normal; display:inline-block; margin-left:5px;">Azure Devops</span>
</p>


<p align="right">(<a href="#readme-top">back to top</a>)</p>

# Transformation Activities in ADF 

* **Azure SHIR** - *Used to ingest data into ADF from On-Prem Via Azure VM*.\
&nbsp;

The Self-Hosted Integration Runtime (SHIR) is a feature in Azure Data Factory that enables secure data transfer between different network environments, such as between on-premises data stores and cloud services, without requiring data to pass through the public internet​

* **Azure Resource Group** - *Created azure Services (ADF, DBX, ADLS, etc) under one resources one Group*.\
&nbsp;

An Azure Resource Group is a container that holds related resources for an Azure solution, allowing you to manage and organize them as a single entity, often reflecting an application or service. It simplifies the management of resources, including their lifecycle, access control, and billing

* **Azure Data Factory** - *Primarily utilized for transforming and modeling data during the transition from the raw stage to a more refined, curated layer*.\
&nbsp;

Azure Data Factory is a cloud-based data integration service that allows you to create, schedule, and orchestrate data workflows for moving and transforming data between different services and data stores. It supports building data-driven pipelines to direct the flow of data and transform it into a structured format for analysis and reporting

* **Azure Databricks** - *Mainly utilized for scripting table creation, logging activities, and data transformation tasks*.\
&nbsp;

Azure Databricks is a cloud-based analytics platform optimized for the Microsoft Azure cloud services platform. It offers an integrated environment for big data processing, analytics, and machine learning, facilitating collaboration between data scientists, data engineers, and business analysts

* **Azure Virtual Network** - *Created a VN in order to deploy Azure Databricks*.\
&nbsp;

Azure Virtual Network (VNet) is a fundamental building block for your private network in Azure, allowing you to securely link Azure services to each other and to on-premise networks. It enables the creation of a logically isolated section within the Azure cloud where you can launch and manage virtual machines, specify DNS settings, and configure network security groups and routing

* **Azure ADLS Gen2** - *Utilized ADLS Gen2 for storing both ingested raw data and processed data within specifically created containers inside ADLS Gen2*.\
&nbsp;

Azure ADLS Gen2 (Azure Data Lake Storage Generation 2) combines the capabilities of Azure Data Lake Storage Gen1 with Azure Blob storage, offering a highly scalable and cost-effective data lake solution for big data analytics. It provides advanced security features, performance, and management ease, making it suitable for a wide range of big data analytics and storage scenarios

* **Azure Logic App** - *Leveraged Logic Apps for email notifications, configuring it to send alerts upon the start, stop, and failure of pipelines through a Web Service activity within Azure Data Factory*.\
&nbsp;

Azure Logic Apps is a cloud service that helps you automate workflows and integrate apps, data, services, and systems across enterprises or organizations. It provides a visual designer to model and automate processes as a series of steps known as a workflow, enabling tasks and business processes to be automated without writing code

* **Azure Key Vault** - *Utilized Azure Key Vault for securely storing secrets crucial for on-premises and interservice connectivity, ensuring protected access to sensitive information*.\
&nbsp;

Azure Key Vault is a cloud service that provides a secure store for secrets, keys, certificates, and other sensitive information. It enables users to securely manage and protect cryptographic keys and secrets used by cloud applications and services, minimizing the risks associated with directly storing these in code or elsewhere

* **Azure Devops** - *Used Azure DevOps Boards to organize sprints and user stories, and implemented Git for version control to manage and track changes in the project codebase*.\
&nbsp;

Azure Logic Apps is a cloud service that helps you automate workflows and integrate apps, data, services, and systems across enterprises or organizations. It provides a visual designer to model and automate processes as a series of steps known as a workflow, enabling tasks and business processes to be automated without writing code

## Concept to be covered in next project

* Role Based Access Control (RBAC)
* Unity Catelog
* Various level of Enviroment Ownership
* ADF Git Hub Versioning
* DBX comman command used in Data Cleaning Activities
* Few more interesting facts


## 👩🏻‍💻 Usage Instructions

To explore the contents of this repository:

1. **Clone the repository**:

    ```sh
    git clone https://github.com/IndraT97/Azure-Data-Engineering-ADF-DBX-ADLS.git
    ```

2. **Navigate through the directories** to find case studies, platform solutions, or projects of interest.

3. **Review the SQL queries and accompanying documentation** to understand the problem-solving approaches and methodologies.


## ✏️ Contribution Guidelines

Contributions to this repository are welcome. 🚀

If you have suggestions for improvements, additional case studies, solutions, or projects, please follow these steps:

1. Fork the repository.

2. Create a new branch (`git checkout -b feature-branch`).

3. Commit your changes with detailed messages (`git commit -m 'Add detailed feature description'`).

4. Push to the branch (`git push origin feature-branch`).

5. Submit a pull request for review.

## Support

Do ⭐ the repository, if it inspired you, gave you ideas of your own or helped you in any way !!

I hope you find these resources informative and useful for your SQL learning and application. Should you have any questions or feedback, feel free to reach out to me on [LinkedIn](https://www.linkedin.com/in/i97/). 🙌

