![Microsoft](https://img.shields.io/badge/Microsoft%20Azure-0078D4?style=for-the-badge&logo=microsoft&logoColor=white) <img src="https://github.com/user-attachments/assets/eef773fe-dc21-49ca-8006-27d6e232e7dc" data-canonical-src="[https://gyazo.com/eb5c5741b6a9a16c692170a41a49c858.png](https://codehub.gr/wp-content/uploads/2020/11/CodeHub-logo_Full-e1515417616834-1.png)" width="112" height="28" />


# Code.Hub Team2 Cloud Engeneering
This is our final project deliverable to conclude our Seminar on Cloud Engeneering by Code.Hub

## Table of Contents
- [Code.Hub Team2 Cloud Engeneering](#codehub-team2-cloud-engeneering)
  * [Table of Contents](#table-of-contents)
  * [Project Objective](#project-objective)
  * [Infrastructure Design](#infrastructure-design)
  * [Justification for Service Selections](#justification-for-service-selections)
  * [Cost Analysis & Comparison](#cost-analysis--comparison)
    + [Azure](#azure)
    + [On-Premise](#on-premise)
    + [Cost Comparison](#cost-comparison)
  * [Project conclusions](#project-conclusions)
  * [Credits](#credits)

## Project Objective
This project's main objective was to provide us with hands-on experience while working with Azure Cloud Services. 
The scenario was to design and implement a cloud infrastructure on Microsoft Azure for a fictional software company, MultiSoftware Enterprise, transitioning from an outdated on-premises architecture. The cloud solution aims to:

1. Establish secure, multi-factor authentication and access control for internal and external services.
2. Host company websites, APIs, and databases, supporting user access and data integrity.
3. Implement serverless operations for stateless workloads.
4. Ensure scalable storage and compliant data retention for large volumes of public and private content.
5. Provide detailed resource billing insights to separate costs for internal operations.
6. The outcome includes creating detailed architecture diagrams, deployment scripts, cost analysis, and a presentation of the project’s implementation and management aspects.

## Infrastructure Design 
Here is the designed diagram, showing the services we decided to use
![image](https://github.com/user-attachments/assets/acef53ec-2c4b-4ff1-abed-871b22e6f0a3)

## Justification for Service Selections
**1. Azure Entra ID**

  * Provides authentication with Office 365 and supports multi-factor authentication (2FA) to secure user access.

**2. Web Application Firewall (WAF)**

  * Ensures a secure endpoint at the network edge.
  * Protects against unwanted external access and enhances network security.

**3. Azure App Service**

  * We chose the `Premium P0V3` instance, which we estimate will sufficiently meet our production environment needs.

**4. Azure Functions**

  * Offers serverless capabilities to streamline stateless operations.

**5. Virtual Network**

  * Internal network designed to protect and isolate specific resources.
  * Database, Blob Storage, and Archive Storage are connected within this Virtual Network and are accessible only by App Services and Functions.

**6. Database**

  * Using a PostgreSQL flexible server `(D2sV3, 8GB RAM, 128GB Storage)` for familiarity with PostgreSQL and expected workload suitability.

**7. Blob Storage**

  * Stores multimedia files accessible via the website.
  * `Hot Storage` tier selected to ensure high availability for frequently accessed files.

**8. Archive Storage**

  * `Cold storage` chosen to retain company logs that are infrequently accessed.
  * Files older than one day are automatically archived for cost efficiency.

## Cost Analysis & Comparison
The prices of the services are individualy listed below:
### Azure

| **Service Name** | **Upfront Cost** | **Monthly Cost**  | 
|------------------|------------------|-------------------|
| App Service      | 75\.92€          | 42\.59€           |
| Hot Storage      | 0\.00€           | 5\.64€            |
| Archive Storage  | 0\.00€           | 58\.90€           |
| PostgreSQL DB    | 0\.00€           | 281\.36€          |
| Azure Functions  | 0\.00€           | \*0\.00€          |
| Virtual Network  | 0\.00€           | 0\.00€            |
| Entra ID         | 0\.00€           | 101\.40€          |
| WAF              | 0\.00€           | 324\.83€          |
|                  |                  |                   | 
| **Total:**       | **75\.92€**      | **907\.33€**      |


\* First 1.000.000 Requests are free of charge

### On-Premise
| **Service Name** | **Cost over 5 Years**  | **Estimated Monthly (Over 5 Years)** | 
|------------------|------------------------|--------------------------------------|
| Compute          | 15,926\.58€            | 265\.44€                             |
| Data Center      | 11,077\.10€            | 184\.61€                             |
| Networking       | 1,574\.95€             | 26\.24€                              |
| Storage          | 2,088\.48€             | 34\.80€                              |
| IT Labor         | 3,510\.95€             | 58\.51€                              |
|                  |                        |                                      |
| **Total:**       | **34,177\.90€**        | **569\.63€**                         |



### Cost Comparison
|                                    | **Azure** | **On\-Premise** |
|------------------------------------|-----------|-----------------|
| **Total Cost \(Over 5 Years\)**    | 54,439\.8€| 34,177\.90€    |

Overall, while the On-Premise option might appear cheaper, it lacks the cost calculation for substitute services to replace Azure services like EntraID, WAF etc.
In addition, the On-Premise calculation is estimated over a 5 year span. It won't take into account any potential hardware failiures or cost fluctuations.


## Project conclusions
This project provided hands-on experience with Azure, presenting it as a viable alternative to on-premises setups. While Azure offers flexibility and scalability, on-premises remains cost-effective over time. The demanding yet rewarding experience deepened our understanding of both options, preparing us for diverse, future infrastructure needs.

## Credits
This project was made possiblle with the valueable contribution of the following members:
* Dimitris Manos
* Michail Selvesakis    [![Linkedin](https://i.sstatic.net/gVE0j.png)](https://www.linkedin.com/in/michael-selvesakis-010b65242/)
* Apostolos Kefalos     [![Linkedin](https://i.sstatic.net/gVE0j.png)](https://www.linkedin.com/in/apostkef/)
* Euaggelia Maria Kaia  [![Linkedin](https://i.sstatic.net/gVE0j.png)](https://www.linkedin.com/in/evangelia-kaia-85118322b/)
* Christos Kerigkas     [![Linkedin](https://i.sstatic.net/gVE0j.png)](https://www.linkedin.com/in/χρήστος-κέριγκας-452205211/)
