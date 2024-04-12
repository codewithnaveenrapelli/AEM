# Templates in AEM

Templates are used at various points in AEM:

* When you create a page, you select a template. This template is used as the base for the new page. 

* The template defines the structure of the page, any initial content, and the components that can be used (design properties).

* When you create a Content Fragment, you also select a template. This template defines the structure, initial elements, and variations.


The following templates are covered in detail:

1. Page Templates - Editable
2. Page Templates - Static
3. Content Fragment Templates
4. Adaptive Template Rendering

AEM now offers two basic types of templates for creating pages:

# 1. Editable Templates

Editable templates are now considered best practices for developing with AEM.

## The advantages of Editable Templates:

* Can be created and edited by your authors.

* Have been introduced to let you define the following for any pages created with the template:
    - the structure
    - the initial content
    - content policies

* After the new page is created, a **dynamic connection is maintained between the page and the template**. This connection means that changes to the template structure are reflected on any pages created with that template; changes to the initial content are not reflected.

* Uses content policies (edited from the template editor) to persist the design properties (does not use Design mode within the page editor).

* Are stored under /conf

# Template Creation 

## When creating an editable template.

1. Create a folder for the templates. This folder is not mandatory, but is recommended best practice.

2. Go to Tools --> General --> Configurations Browser.

![Folder](https://github.com/DeveloperResource-NaveenR/AEM/blob/main/Images/Editable%20Template/Editable%20Template%201.png) 

3. In the Create Configuration dialog, the following fields must be configured:

    - Title: Provide a title for the configuration folder
    - Editable Templates: Select to allow for editable templates within this folder

![Folder](https://github.com/DeveloperResource-NaveenR/AEM/blob/main/Images/Editable%20Template/Editable%20Template%202.png) 

4. Click Create Folder is created

![Folder](https://github.com/DeveloperResource-NaveenR/AEM/blob/main/Images/Editable%20Template/Editable%20Template%203.png) 


5. Check Weather this folder is saved in DB(CRX/DE).

![Folder](https://github.com/DeveloperResource-NaveenR/AEM/blob/main/Images/Editable%20Template/Editable%20Template%204.png) 


6. Open the folder called Template Type inside you will not any template type.

![Folder](https://github.com/DeveloperResource-NaveenR/AEM/blob/main/Images/Editable%20Template/Editable%20Template%205.png) 

## Create a Template Type

7. Go to Tools --> general --> Template Folder --> Click on it.

![Folder](https://github.com/DeveloperResource-NaveenR/AEM/blob/main/Images/Editable%20Template/Editable%20Template%206.png) 

8. Now you will be able to see the folder which is created earlier.

![Folder](https://github.com/DeveloperResource-NaveenR/AEM/blob/main/Images/Editable%20Template/Editable%20Template%207.png)

9. Go inside the folder and Click on Create Button.

![Folder](https://github.com/DeveloperResource-NaveenR/AEM/blob/main/Images/Editable%20Template/Editable%20Template%208.png) 

10. You will find one template type which is coming from other resource Example it will check in the relative path if template type is not available in our project. 
    - /conf/myproject/myproject/settings/wcm/template-types
    - /conf/myfolder/settings/wcm/template-types
    - /conf/global/settings/wcm/template-types
    - /apps/settings/wcm/template-types
    - /libs/settings/wcm/template-types

## 11. Create A Template Type 

    - Best of creating template type is you can copy from wknd(project) or Any other project

![Folder](https://github.com/DeveloperResource-NaveenR/AEM/blob/main/Images/Editable%20Template/Editable%20Template%209.png) 


11. Once you copied the filed you can paste the file to your folder under template type and renamed the file name

![Folder](https://github.com/DeveloperResource-NaveenR/AEM/blob/main/Images/Editable%20Template/Editable%20Template%2010.png) 

12. Inside the folder jcr:content change the jcr:title and jcr:description.

![Folder](https://github.com/DeveloperResource-NaveenR/AEM/blob/main/Images/Editable%20Template/Editable%20Template%2011.png) 

13. Go to initial content node and change the sling:resourceType 

![Folder](https://github.com/DeveloperResource-NaveenR/AEM/blob/main/Images/Editable%20Template/Editable%20Template%2012.png)

13. Go to structure node and change sling:resourceType

![Folder](https://github.com/DeveloperResource-NaveenR/AEM/blob/main/Images/Editable%20Template/Editable%20Template%2013.png)

14. Now we are ready with template type 

15. Go back to tools --> general --> template --> your-Project Folder --> Click on Create Button

16. You will find the template type which is created now.

![Folder](https://github.com/DeveloperResource-NaveenR/AEM/blob/main/Images/Editable%20Template/Editable%20Template%2014.png)

17. Select the template type and create a template 

    - Need to add title 

![Folder](https://github.com/DeveloperResource-NaveenR/AEM/blob/main/Images/Editable%20Template/Editable%20Template%2015.png)

18. Once you add the title click on create button

![Folder](https://github.com/DeveloperResource-NaveenR/AEM/blob/main/Images/Editable%20Template/Editable%20Template%2016.png)

19. Successfully we have created Template Type and using template type we created template.


Let's Understand below folder structure

1. structure
2. initial
3. policy

![Folder](https://github.com/DeveloperResource-NaveenR/AEM/blob/main/Images/Editable%20Template/Editable%20Template%2017.png)


## Structure

* The structure if you want any components to be available on the page and content for your template.

* Components defined in the template structure cannot be moved on or deleted from any resultant pages.

* Changes made to the structure are reflected in any pages created with the template.

* After a component is unlocked, the editable property is set to true.

* After a component that already contains content is unlocked, this content is moved to the initial branch.

* The cq:responsive node holds definitions for the responsive layout.

* Components can be unlocked and locked again to let you define initial content.

* If you want page authors to be able to add and remove components, add a paragraph system to the template.

## Initial Content

* initial you will defined the initial content and component which will be available when you create a page.
* Initial content can then be edited by page authors.

## Difference between initial/Structure 

* In both you can add component and content to available when creating a page.
* The component you add in initial you can remove it.
* The component you added in the structure you cannot remove it.

## policies
* You can define what component need to allowed in the template using policies

## Layout

You can define the template layout for a range of devices.
Responsive layout for templates operates as it does for page authoring.

Now let create template with some components.

![Folder](https://github.com/DeveloperResource-NaveenR/AEM/blob/main/Images/Editable%20Template/Editable%20Template%2018.png)

* In structure mode when you can on container component we don't have option to add component to it.

* so it enable that we need add policy to it.

![Folder](https://github.com/DeveloperResource-NaveenR/AEM/blob/main/Images/Editable%20Template/Editable%20Template%2019.png)

* Go the this url --> http://localhost:4502/sites.html/content/AEM-DeveloperResource/us/en 

![Folder](https://github.com/DeveloperResource-NaveenR/AEM/blob/main/Images/Editable%20Template/Editable%20Template%2021.png)

* you need to find your template in it. if your template is not visible 

    - Template is in draft mode
    - Template is not allowed 

* Let's make the template from draft to enable state.

![Folder](https://github.com/DeveloperResource-NaveenR/AEM/blob/main/Images/Editable%20Template/Editable%20Template%2020.png)

* After enable still you are not able find the template 

![Folder](https://github.com/DeveloperResource-NaveenR/AEM/blob/main/Images/Editable%20Template/Editable%20Template%2022.png)

* Next you add in page properties under US--> page properties

![Folder](https://github.com/DeveloperResource-NaveenR/AEM/blob/main/Images/Editable%20Template/Editable%20Template%2023.png)

* now you will find your template when you are creating page.

![Folder](https://github.com/DeveloperResource-NaveenR/AEM/blob/main/Images/Editable%20Template/Editable%20Template%2024.png)

* let's create a page using this template.

![Folder](https://github.com/DeveloperResource-NaveenR/AEM/blob/main/Images/Editable%20Template/Editable%20Template%2025.png)



# Templates - Static

* A Template is used to create a Page and defines which components can be used within the selected scope. A template is a hierarchy of nodes that has the same structure as the page to be created, but without any actual content.

* Each Template presents you with a selection of components available for use.

    - Templates are built up of Components;
    - Components use, and allow access to, Widgets and these are used to render the Content.





































