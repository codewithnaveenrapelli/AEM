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

follow this link to creating instance **[AEM Instance Setup](./03_AEM_Instances_Setup.md)**
