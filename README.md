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

# Transformation Activities in ADF 

## Concept to be covered in next project

* Role Based Access Control (RBAC)
* Unity Catelog
* Various level of Ownership
* ADF Git Hub Versioning
* DBX comman command used in Data Cleaning Activities
* Few more interesting facts
