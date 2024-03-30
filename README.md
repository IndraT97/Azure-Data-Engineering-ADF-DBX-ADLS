# Azure-Data-Engineering (ADF-DBX-ADLS)
<a name="readme-top"></a>
# Project Objective
**Ingesting on-premise (SQL and SFTP) data and transforming it using Azure Data Factory, Databricks followed by analyzing and reporting using PowerBI**

In this project the main aim is to understand the Flow of data from On-Prem to Cloud Platform while transforming the data to get the final set of tables for further analysis

In real-time scenarios, organizations often grapple with petabytes of structured data dispersed across numerous on-premises locations. Leveraging cloud solutions streamlines data processing, circumventing the limitations and inefficiencies of current infrastructure. This shift not only sidesteps the extensive planning, time, and financial investment required for new infrastructure setup but also mitigates the risk of such investments becoming obsolete. Ultimately, transitioning to the cloud facilitates swift, cost-effective achievement of data processing objectives with minimal complexity

# Table of Contents
- [Project Architecture](#project-architecture)
   * [Overall-Project-Flow](#Overall-Project-Flow)
   * [Linked-Serive-Architecture](#Linked-Serive-Architecture)
   * [MetaData Flow (Data Ingestion)](#MetaData-Flow-Data-Ingestion)
   * [General Industry Pratice (Data Ingestion)](#General-Industry-Pratice-Data-Ingestion)
- [Azure Services used in the Project](#Azure-Services-used-in-the-Project)
- [Transformation Activities in ADF](#Transformation-Activities-in-ADF)
- [Concept to be covered in next project](#Concept-to-be-covered-in-next-project)

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

*
*
*
*
*
*

## Concept to be covered in next project

* Role Based Access Control (RBAC)
* Unity Catelog
* Various level of Enviroment Ownership
* ADF Git Hub Versioning
* DBX comman command used in Data Cleaning Activities
* Few more interesting facts
