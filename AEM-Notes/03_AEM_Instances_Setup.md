# AEM Instances

## What are Author and Publish Instances?
## Author Instance:
* The environment where content creators and marketers create, edit, and manage content.
* It’s a workspace for authoring pages, adding components, adjusting layouts, and previewing content before it goes live.
* Typically, this instance is restricted to internal networks for security purposes.
## Publish Instance:
* The environment where the end-users interact with the content.
* Once content is finalized and published from the Author instance, it becomes visible here.
* This instance is exposed to the public internet, allowing access to the website’s visitors.

## AEM Author Instance Setup

* AEM Author instance generally hosted on 4502 port. 

* This is an internal (not for end user) server mainly used for content authoring. Content will get publish or transfer to multiple AEM instances on content replication which is also called as activation.

![AEM AUthor](/AEM/Images/author.png)

* We can have one or more than one publish AEM instance.

![AEM AUthor](/AEM/Images/Multiple.png)

1. Creating an AEM instance required naming the AEM jar file as aem-author-p4502.jar

2. Double-click on the jar file to create a brand new AEM instance. After clicking on AEM Jar will open the below window. It will take a good amount of time around 15 to 20 min to start AEM for the first time. Next time onwards it will take max 5 minutes to start the instance

![AEM AUthor](/AEM/Images/start.png)


3. Once the AEM instance is up and running, it will open a browser with the below page open.

4. Provide username and password as admin which is OOTB that can also be changed.

![AEM Instance](/AEM/Images/start%202.png)


5. After login, it will open below screen

![AEM Login Page](/AEM/Images/login.png)

6. Clicking on the below question mark sign will help us to see the Adobe Experience Manager version.

![AEM Version Check](/AEM/Images/version.png)


## AEM Publish instance

AEM Publish instance generally hosted on 4503 port and available to access for end users.


As part of reverse replication, content will get replicate or deactivate from publish instance to author.

![AEM Version Check](/AEM/Images/AEM_Publish.png)

Below are the steps to create publish instance

1. Copy the jar to a new folder publish and rename it as aem-publish-p4503.jar

2. Open the command line on the current folder and run **java -jar aem-publish-p4503.jar** command to start the publish instance

3. Once AEM successfully starts, it is accessible on http://localhost:4503 using any browser of your choice


## The Differences Between Author and Publish Instances
* **Access Control**: The Author instance is a secured, internal environment with restricted access, while the Publish instance is publicly accessible.
* **Content Management**: Content creation and editing happen only on the Author instance. The Publish instance displays the content but doesn’t allow editing.
* **Workflow and Approval**: The Author instance often includes workflows for content approval before publishing.

## Why Two Instances?
* Security and Control: Separating environments ensures that in-progress content isn’t publicly visible and provides a controlled space for content creation.
* Performance Optimization: The Publish instance is optimized for fast content delivery, while the Author instance is optimized for content management functionalities.
* Stability and Reliability: This separation minimizes the risk of authoring activities impacting the performance of the live site.


## Important URL's

1. Content Page URL for all content website pages http://localhost:4503/sites.html/content 

2. Asset / DAM Page URL for all media files http://localhost:4503/sites.html/content

3. Code Editor URL to access code file http://localhost:4503/crx/de

4. Package Manager URL to access, build and install code and content packages. http://localhost:4503/crx/packmgr

5. System Console Bundle to access all bundles or jar files. It helps us to check bundle status as install, active, resolved, etc.  http://localhost:4503/system/console/bundles
 
6. System Console Components to check both out of the box and custom components.
http://localhost:4503/system/console/components

7. System Console Configurations to check and manage all the out of the box or system level configurations
http://localhost:4503/system/console/configMgr

