# AEM clientlibs clear cache and recompile clientlibs

Clientlibs or client libraries in aem is one of the most widely used features provided by Adobe, it allows us to not only manage our client-side resources like (JavaScript, CSS, images, fonts, etc) but also provide options to debug, minify, merge and gzip the client-side code.
As it consists of JS and CSS and in some instances they get cached and you can face some issues while developing.

To rebuild the clientlibs and invalidate the cache, you can follow the process below.

Go to ```<domain-name>```/libs/granite/ui/content/dumplibs.rebuild.html

Example: http://localhost:4502/libs/granite/ui/content/dumplibs.rebuild.html

You will see two options:
1. Invalidate Caches – To invalidate caches
2. Rebuild Libraries – To rebuild libraries

![URL](/AEM/Images/Clientlibs/clientlibs_11.png)

Now you can click on them based on your requirement.

