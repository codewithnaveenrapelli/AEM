# AEM Local Development Environment Setup

# Install Java

Experience Manager is a Java application, and thus requires the Java SDK to support the development and the AEM as a Cloud Service SDK.

1. **[Download and install the latest release Java 11 SDK](https://www.oracle.com/in/java/technologies/javase/jdk11-archive-downloads.html)**.
2. Verify Oracle Java 11 SDK is installed by running the command:
```js
Go to CMD Type Below Command

$ java -version
```
# Install Git

Git is the source control management system used by Adobe Cloud Manager, and thus is required for development.

1. **[Download and install Git](https://git-scm.com/downloads)**

2. Open your Terminal/Command Prompt

3. Verify Git is installed, using the command: **$ git --version**

# Install Node.js (and npm)

Node.js is a JavaScript runtime environment used to work with the front-end assets of an AEM project’s ui.frontend sub-project. Node.js is distributed with npm, is the defacto Node.js package manager, used to manage JavaScript dependencies.

1. **[Download and install Node.js](https://nodejs.org/en/download/)**

2. Open your Terminal/Command Prompt

3. Verify Node.js is installed, using the command: **$ node -v**

4. Verify npm is installed, using the command: **$ npm -v**

# Install Maven

Apache Maven is the open-source Java command-line tool used to build AEM Projects generated from the AEM Project Maven Archetype. All major IDE’s (IntelliJ IDEA, Visual Studio Code, Eclipse, etc.) have integrated Maven support.

1. **[Download Maven](https://maven.apache.org/download.cgi)**

2. **[Install Maven](https://maven.apache.org/install.html)**

3. Open your Terminal/Command Prompt

4. Verify Maven is installed, using the command: **$ mvn -v**

# Set up the development IDE

## IntelliJ IDEA

IntelliJ IDEA is a powerful IDE for Java development. IntelliJ IDEA comes in two flavors, a free Community edition and a commercial (paid) Ultimate version. The free Community version is sufficient for AEM development, however the Ultimate expands its capability set.

1. **[Download IntelliJ IDEA](https://www.jetbrains.com/idea/download/?section=windows)**
2. **[Download the Repo tool](https://github.com/Adobe-Marketing-Cloud/tools/tree/master/repo#installation)**  Optional

# AEM Setup In Local

1. Download the cloud SDK latest Jar from [Download](https://experience.adobe.com/#/downloads) using your organization's Adobe ID

2. Unzip downloaded aem-sdk-<version>.zip file

3. Copy the Jar file to a separate working folder of yours.

Before creating an instance we need to understand two different instances we have author and publish instance.

# Author Instance

The author instance is completely responsible for content and asset authoring which can only be handled by admins and content authors. It is generally hosted on 4502 port.

Follow the below steps to create an AEM instance

1. Creating an AEM instance required naming the AEM jar file as aem-author-p4502.jar

2. Double-click on the jar file to create a brand new AEM instance. After clicking on AEM Jar will open the below window. It will take a good amount of time around 15 to 20 min to start AEM for the first time. Next time onwards it will take max 5 minutes to start the instance


![AEM AUthor](/AEM/Images/AEM%20Author.webp)

3. Once the AEM instance is up and running, it will open a browser with the below page open.

4. Provide username and password as admin which is OOTB that can also be changed.

![AEM Instance](/AEM/Images/Instance.webp)

5. After login, it will open below screen

![AEM Login Page](/AEM/Images/login.webp)

6. Clicking on the below question mark sign will help us to see the Adobe Experience Manager version. Currently, we have having 6.5.0 version installed.

![AEM Version Check](/AEM/Images/version.webp)


![AEM Version Check](/AEM/Images/v1ersion.webp)


# Create the project

1. Create a folder and Open Command Prompt

2. Paste the following into the command line to generate the project in batch mode

```java
mvn -B org.apache.maven.plugins:maven-archetype-plugin:3.2.1:generate -D archetypeGroupId=com.adobe.aem -D archetypeArtifactId=aem-project-archetype -D archetypeVersion=37 -D appTitle="mySite" -D appId="AEM-MySite" -D aemVersion="cloud" -D groupId="com.mySite"
```
3. Go inside the folder generated and you will be able to see below generated files

```java
~/code/
    |--- aem-guides-wknd/
        |--- all/
        |--- core/
        |--- ui.apps/
        |--- ui.apps.structure/
        |--- ui.config/
        |--- ui.content/
        |--- ui.frontend/
        |--- ui.tests /
        |--- it.tests/
        |--- dispatcher/
        |--- pom.xml
        |--- README.md
        |--- .gitignore
```
# Deploy and build the project

1. Build and deploy the project code to a local instance of AEM.

2. Ensure you have an author instance of AEM running locally on port 4502.

```cmd
cd <project Folder>
```

3. Run the following command to build and deploy the entire project to AEM:

```java
$ mvn clean install -PautoInstallSinglePackage
```
The build takes around a minute and should end with the following message

```java
...
[INFO] ------------------------------------------------------------------------
[INFO] Reactor Summary for WKND Sites Project 0.0.1-SNAPSHOT:
[INFO]
[INFO] WKND Sites Project ................................. SUCCESS [  0.113 s]
[INFO] WKND Sites Project - Core .......................... SUCCESS [  3.136 s]
[INFO] WKND Sites Project - UI Frontend ................... SUCCESS [  4.461 s]
[INFO] WKND Sites Project - Repository Structure Package .. SUCCESS [  0.359 s]
[INFO] WKND Sites Project - UI apps ....................... SUCCESS [  1.732 s]
[INFO] WKND Sites Project - UI content .................... SUCCESS [  0.956 s]
[INFO] WKND Sites Project - UI config ..................... SUCCESS [  0.064 s]
[INFO] WKND Sites Project - All ........................... SUCCESS [  8.229 s]
[INFO] WKND Sites Project - Integration Tests ............. SUCCESS [  3.329 s]
[INFO] WKND Sites Project - Dispatcher .................... SUCCESS [  0.027 s]
[INFO] WKND Sites Project - UI Tests ...................... SUCCESS [  0.032 s]
[INFO] ------------------------------------------------------------------------
[INFO] BUILD SUCCESS
[INFO] ------------------------------------------------------------------------
[INFO] Total time:  23.189 s
[INFO] Finished at: 2023-01-10T11:12:23-05:00
[INFO] ------------------------------------------------------------------------

```

# **Most Common Error**

1. Dispatcher issue may occur, GO to POM.xml in project and UnCommit the as per below image


![Dispatcher Issue](/AEM/Images/image.png)

2. **npm install** This issue will cover while installing maven command To Resolve this issue.

3. Go to Ui.frontend --> Module

4. Go to Package.json --> Update TypeScript value -->  **"typescript": "^4.8.3",**

5. **ui.apps** Any issue occurred in ui.apps --> Just go an Delete the folder Mostly common issue will logo file under ecommerace



