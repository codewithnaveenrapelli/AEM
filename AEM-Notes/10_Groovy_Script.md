## How to Install Groovy Script in AEM.

## What is Groovy Script?

The AEM Groovy Console provides an interface for running Groovy scripts in Adobe Experience Manager. 

Scripts can be created to manipulate content in the JCR, call OSGi services, or execute arbitrary code using the AEM, Sling, or JCR APIs without any change in the core code of the AEM project.

Apache Groovy is an Object-oriented programming language used for Java platforms like AEM. It is almost like a super version of Java which offers all of Java’s enterprise capabilities. Learning/understanding groovy comes naturally to a java developer so the learning curve to learn groovy for a java developer is very minimal and easy enough. It can manipulate without much hustle, easy, fast, and simple to use provided UI.

## Installations.

Install groovy script console.


1. Install a groovy console package in AEM through the package

    - Download the groovy console package from https://github.com/CID15/aem-groovy-console/tags (For previous versions, tags can be checked out from GitHub )

    - Extract the ZIP file and go to the folder

    - Built directly from the source code by running **mvn clean install**

    - Install the package using the CRX package manager

    - Verify the installation on http://localhost:4502/apps/groovyconsole.html

2. Go to CRX/DE http://localhost:4502/crx/packmgr/index.jsp

    - Download the package from my github account here is the link [Groovy package](/AEM/AEM-Notes/aem-groovy-console-all-17.0.0.zip)

    - Install in CRX/DE

    ![Image CRX/DE](/AEM/Images/Groovy/groovy_1.png)
    
    - Verify the installation on http://localhost:4502/apps/groovyconsole.html

    ![Groovy Console](/AEM/Images/Groovy/groovy_2.png)

## Another way of doing 

1. By updating pom.xml

    - Update the pom.xml under the “all” folder

    - Add embedded under embeddeds

```html
<embedded>
    <groupId>org.cid15.aem.groovy.console</groupId>
    <artifactId>aem-groovy-console-all</artifactId>
    <type>zip</type>
    <target>/apps/gap-cloud-packages/groovyconsole/install</target>
</embedded>
```
- Add dependency under dependencies (Here 17.0.0 is the version you can update it with the required version)

```html
<dependency>
    <groupId>org.cid15.aem.groovy.console</groupId>
    <artifactId>aem-groovy-console-all</artifactId>
    <version>17.0.0</version>
    <type>zip</type>
</dependency>
```
And you are done!




