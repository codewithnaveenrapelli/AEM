## AEM Clientlibs

Adobe Introduced clientlibs to manage css, js files and required resource(font,image)

Node type of clientlibs -->  cq:ClientLibraryFolder.

Js.txt & css.txt are mandatory files to manage JS and CSS files.

![clientlibs](/AEM/Images/Clientlibs/clientlibs_1.png)


## How to create clientlibs using crx/de

step 1: Go to crx/de --> http://localhost:4502/crx/de/index.jsp

step 2: Go inside apps folder --> Go to clientlibs 

Step 3: Right Click on clientlibs folder and click on create --> node

node type cq:ClientLibraryFolder and name can be anything.

![clientlibs](/AEM/Images/Clientlibs/clientlibs_2.png)

Step 4: 3. Create CSS and JS folders to place respective CSS and JS files.

![clientlibs](/AEM/Images/Clientlibs/clientlibs_3.png)

Step 5: create sample.js and sample.css files.

Step 6: Create below js.txt file inside JS folder to declare file names which needs to be load as part of custom-clientlibs category.

base=js represents .js files root folder name.
```js
#base=js
sample.js
```
Step 7. Create below css.txt file inside CSS folder to declare file names which needs to be load as part of practice.custom-clientlibs category.

base=css represents CSS files root folder name.
```cs
#base=css
site.css
```
Step 8: once you are done with creating the folder structure 

Step 9: you can test weather clientlibs is working or no, Hit the below url to test.

Example: http://localhost:4502/apps/AEM-DeveloperResource/clientlibs/custom_clientlibs.js


Step 10: Create one more client library folder follow above steps.

![clientlibs](/AEM/Images/Clientlibs/clientlibs_5.png)


Step 10: create below properties under custom-clientlibs.

![clientlibs](/AEM/Images/Clientlibs/clientlibs_6.png)

Step 11: Once you added all the properties you need load your clientlibs.

Step 12: Go to page http://localhost:4502/editor.html/content/AEM-DeveloperResource/us/en/search.html

Step 13. Click on editable template.

![clientlibs](/AEM/Images/Clientlibs/clientlibs_7.png)

Step 14. Click on page policy

![clientlibs](/AEM/Images/Clientlibs/clientlibs_8.png)

Step 15. add your clientlibs --> category name and click on done.

![clientlibs](/AEM/Images/Clientlibs/clientlibs_9.png)

step 16. Once added your category name refresh the page and go to view page source

Step 17. You will find desktop is loaded first and custom-clientlibs is loaded next this worked by adding dependencies.

![clientlibs](/AEM/Images/Clientlibs/clientlibs_10.png)


Lets Understand.

- categories is a use to store custom client category JS and CSS

- dependencies --> is used to load the another clientlibs before our clientlibs.

example:
 
custom-clientlibs and desktop clientlibs so i want to load the desktop clientlibs before the custom-clientlibs to active we use dependencies.

- embed helps us in combining all clientlibraries and load it as single CSS and JS file. If A category embeds two different categories as B and C. The resulting CSS and JS will have one single JS and CSS file.

- allowProxy allows access client libraries via proxy servlet.

- cssProcessor is to process CSS file using min:yui compiler

- jsProcessor is to process JS file using min:yui compiler


## Using Policy
Using page component policy we can load client library on the page as shown below.
```html
<page jcr:primaryType="nt:unstructured">
    <policy
        jcr:description="Include Client libraries."
        jcr:primaryType="nt:unstructured"
        jcr:title="Page Component"
        sling:resourceType="wcm/core/components/policy/policy"
        clientlibs="[desktop,custom-clientlibs]"
        clientlibsJsHead="desktop">
        <jcr:content jcr:primaryType="nt:unstructured"/>
    </policy>
</page>
```
clientlibs is a multiple value property which allows us to load multiple client categories at the same time.

clientlibsJsHead allows us to load only JS for mentioned client category.

clientlibsCssHead allows us to load only CSS for mentioned client category.

## Using Javascript use API
Below is the code snippet to load both js and css for mentioned clientlib category as shown below:

```html
<sly data-sly-use.clientlib="core/wcm/components/commons/v1/templates/clientlib.html">
    <sly data-sly-call="${clientlib.all @ categories='AEM-DeveloperResource.base'}"/>
</sly>
```

clientlib.all to load both CSS an js files

clientlib.css to load both CSS files. Below statement helps us to load CSS as part of header.
```html
<sly data-sly-call=”${clientlib.css @ categories=’practice.base’}”/>
```
clientlib.js to load both JS files. Below statement helps us to load JS as part of footer.
```html
<sly data-sly-call=”${clientlib.js@ categories=’practice.base’}”/>
```








 
