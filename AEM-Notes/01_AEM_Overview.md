# AEM Overview
AEM (Adobe Experience Manager) is a CMS(Content Management Solution) tool used for managing content and digital media assets. It is used for content authoring and maintaining websites on desktop, mobile and tablet.

There are two ways to setup an AEM instance:

## 1. AEM on Prem:
* It requires a huge cost towards license and infrastructure management.
* It require more attention towards ownership as everything managed mostly by client.
* Upgrade will not be an easy task.
* Any CI can be use as part of code deployment such as Jenkins, Bamboo, ACM etc.

## 2. AEM as a cloud service allows us to use AEM as SaaS(Software as a Service) which mainly manage by Adobe.

* It provides as architecture to auto scale to have additional instances on demand.
* It reduce cost of ownership as server, space and upgradation all manage by Adobe.
* Adobe recommend to use Adobe managed CDN and adobe managed CDN will be pointing by client CDN.
* Cloud manager which is mandatory to use as a CI tool looks for standard dispatcher configuration structure.

# AEM Modules
Below are some of the important AEM modules:

## AEM Sites
* AEM site allows us to author and manage content pages.

## AEM Assets
* AEM site allows us to author and manages assets.

## AEM Forms
* AEM forms provides us a capability to create, update, publish and manage forms at run time. Using AEM forms we can add, update and delete any field in AEM Forms.

## AEM Headless
* It as an architecture which allows us to create two separate frontend and backend application. Here, we expose data using backend application in some predefined format such as JSON, XML, etc. to get consume by any of the third party front application. Similarly, on the other hand create a front end application which can consume or expecting predefined format data from third party backend application.

* Headless architecture can be achieve by GrphQL query, Content and experience fragment.