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

![AEM AUthor](https://github.com/DeveloperResource-NaveenR/AEM/blob/main/Images/author.png)

* We can have one or more than one publish AEM instance.

![AEM AUthor](https://github.com/DeveloperResource-NaveenR/AEM/blob/main/Images/Multiple.png)

1. Creating an AEM instance required naming the AEM jar file as aem-author-p4502.jar

2. Double-click on the jar file to create a brand new AEM instance. After clicking on AEM Jar will open the below window. It will take a good amount of time around 15 to 20 min to start AEM for the first time. Next time onwards it will take max 5 minutes to start the instance

![AEM AUthor](https://github.com/DeveloperResource-NaveenR/AEM/blob/main/Images/start.png)

3. Once the AEM instance is up and running, it will open a browser with the below page open.

4. Provide username and password as admin which is OOTB that can also be changed.

![AEM Instance](https://github.com/DeveloperResource-NaveenR/AEM/blob/main/Images/start%202.png)

5. After login, it will open below screen

![AEM Login Page](https://github.com/DeveloperResource-NaveenR/AEM/blob/main/Images/login.png)

6. Clicking on the below question mark sign will help us to see the Adobe Experience Manager version.

![AEM Version Check](https://github.com/DeveloperResource-NaveenR/AEM/blob/main/Images/version.png)


## AEM Publish instance

AEM Publish instance generally hosted on 4503 port and available to access for end users.


As part of reverse replication, content will get replicate or deactivate from publish instance to author.

![AEM Version Check](https://github.com/DeveloperResource-NaveenR/AEM/blob/main/Images/AEM%20Publish.png)

Below are the steps to create publish instance

1. Copy the jar to a new folder publish and rename it as aem-publish-p4503.jar

2. Open the command line on the current folder and run **java -jar aem-publish-p4503.jar** command to start the publish instance

3. Once AEM successfully starts, it is accessible on http://localhost:4503 using any browser of your choice

## Setting up Replication Agents on Author:

1. Log in to the Author instance and navigate to http://localhost:4502/etc/replication/agents.author.html

2. Click Default Agent to open the default replication agent

![AEM Replication Image](https://github.com/DeveloperResource-NaveenR/AEM/blob/main/Images/Replication%20Image/replication%20Image%20Author.png)


3. Then click on “Edit” after Settings to open the Agent Settings dialog box to enter the details.

![AEM Replication Edit](https://github.com/DeveloperResource-NaveenR/AEM/blob/main/Images/Replication%20Image/replication%203.png)

8. Under the settings tab, update the following

9. Enabled — check true

10. Agent user ID — Leave this empty

![AEM Replication Edit](https://github.com/DeveloperResource-NaveenR/AEM/blob/main/Images/Replication%20Image/replication%204.png)

11. Under the transport tab  update The “URI” with the host name and port number 

12. Configure URI — http://localhost:4503/bin/receive?sling:authRequestLogin=1

13. update the “User” and “Password“, which are your publish instance User Name and Password. (For me: User: admin, Password: admin)

![AEM Replication Edit](https://github.com/DeveloperResource-NaveenR/AEM/blob/main/Images/Replication%20Image/replication%205.png)


14. Click on “OK” and then click on “Test Connection“

15. If all are okay then you can see a page with “Replication test succeeded“

![AEM Replication Edit](https://github.com/DeveloperResource-NaveenR/AEM/blob/main/Images/Replication%20Image/replication%206.png)

16. you can go to the author package manager, select a package and from the more option replicate the package.

![AEM Replication Edit](https://github.com/DeveloperResource-NaveenR/AEM/blob/main/Images/Replication%20Image/replicate2.png)




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

