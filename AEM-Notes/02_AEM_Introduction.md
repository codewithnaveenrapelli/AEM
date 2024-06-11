# AEM as a Cloud Service (AEMaaCS) – Introduction

If you are working in content management space, you must have heard of Adobe Experience Manager (AEM, previously known as CQ5). It is one of the core products offered by Adobe as part of their Adobe Experience Cloud. AEM has evolved over the time from all perspectives (features, maturity, stability, integration with other products and deployment model).

-  As of today, organizations have 3 options to deploy AEM:
    - AEM on premisses
    - AMS – Adobe Managed Service (mainly hosted on AWS)
    - AEM as a Cloud Service (AEMaaCS) 


We will Focus on AEM as a Cloud Service (AEMaaCS). Adobe Experience Manager as a Cloud Service is a new generation software-as-a-service for AEM by Adobe.

AEMaaCS is based on the leading solution Adobe Experience Manager (AEM) and offers outstanding content management (CMS) capabilities and digital asset management (DAM) for marketing and communication teams.

The solution has been entirely designed for the cloud and is scalable, secure, always available, and up to date.

## What is AEM as a Cloud Service?

AEM as a Cloud Service (AEMaaCS) is the cloud-native version of Adobe Experience Manager, designed to leverage the benefits of cloud computing to deliver more agility, scalability, and resilience. It is part of the Adobe Experience Cloud and offers a range of features optimized for cloud deployment.

- AEM as a Cloud Service lets you capitalize on the AEM applications in a cloud-native way, so that you can:

    - Scale your DevOps efforts with Cloud Manager: CI/CD framework, autoscaling, API connectivity, flexible deployment modes, code quality gates, service delivery transparency, and guided updates.

    - Enable developers to add automation to application development practices.

    - Deliver content quickly and efficiently on a global scale, using a built-in Content Delivery Network (CDN) and other network-layer best practices.

    - Leverage a dynamic architecture that auto-scales, thus removing infrastructure considerations.

    - Stay on top of threats and security-risk mitigation, using automated tests to scan for common vulnerabilities.

    - Ensure maximum resilience and efficiency backed by optimized performance topologies.

    - Take advantage of AEM as a Cloud Service’s deep integration with the Adobe Experience Cloud to provide better customer experiences with online marketing and web analytics products.

    - Utilize tools that help accelerate the migration tasks, such as code refactoring, transfer of content, and more.



## Typical AEM as a Cloud Service environment

- A new project that is getting onboarded on AEMaaCS will be provisioned under a Program. There are three types of environments available with a Program of AEM as a Cloud Service:

    - Production environment: hosts the applications for the business practitioners.
    - Stage environment: is always coupled to a single production environment in a 1:1 relationship. The stage environment is used for various performance and quality tests before changes to the application are pushed to the production environment.
    - Development environment: allows developers to implement AEM applications under the same runtime conditions as the stage and production environments.

![AEM Cloud Service environment](./AEM%20Cloud.png)


- Any new AEM project is always bound to exactly one specific codebase, where you can store both configuration and custom code for your project. This information is stored in a code repository, accessible via the usual Git clients, made available to you at the time new programs are created.

    - AEM Cloud Sites Service
    - AEM Cloud Assets Service

Both of these allow access to a number of features and functionalities. The author tier will contain all Sites and Assets functionality for all programs, but the Assets programs will not have a publish tier, nor a preview tier, by default.

 

- ## Core benefits of AEM as a Cloud Service:

    - It is always on with zero downtime
    - It is always at scale
    - It is always current with latest features/upgrades
    - It is always evolving (Adobe is adding new set of standards and best practices-constantly, those are by default included automatically)
    - Low cost of ownership
    - Usage based license model
    - More secure as it is always on the latest security level

## Why AEM as a Cloud Service?

why AEM as a Cloud Service, we need to look at the expectation of consumers and businesses in today’s era. Also, we need to look at the limitations/challenges with either AEM classic/on-premisses or AMS.

 
- At high-high customers want:

    - Better experience (personalization, just in time experience)
    -  Relevant content/information
    - Fast and seamless experience

- On the other hand, businesses expectation is:

    - Customer satisfaction
    - Lower cost of delivery
    - Self-resilient applications/IT infrastructure
    - Modernized and scalable applications
    - From business perspective, let’s also look at quick comparison of 2 modes in which AEM was offered (before AEMaaCS):

From business perspective, let’s also look at quick comparison of 2 modes in which AEM was offered (before AEMaaCS):

![AEM Cloud Service environment](./AEM%20Cloud%202.png)

- Also, there were challenges that exists in both offerings (above):

    - Scalability limitation because of the way Oka/JCR repository works in classic AEM
    - Computational limitations (e.g., asset processing and rendition generation)
    - Content replication related issues (performance, reliability etc.) 

Some of these limitations (highlight) directly translates into a need of cloud native solution so that AEM can be scaled, inherit the security benefits of cloud along with lower cost of ownership and therefore Adobe came up with AEMaaCS offering.

- For now, consider that old classic AEM has been refactored into following:

    - A containerized architecture for scalability and to make AEM cloud-native
    - Set of smaller and scalable services (repository service, asset computer service etc.) for extensibility and performance improvements 
 