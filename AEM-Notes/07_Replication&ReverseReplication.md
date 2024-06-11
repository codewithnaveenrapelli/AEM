## AEM Replication and Reverse Replication

* Replication allows to push content from an author to publish AEM instance.

* AEM Author instance generally hosted on 4502 port. This is an internal (not for end user) server mainly used for content authoring. Content will get publish or transfer to multiple AEM instances on content replication which is also called as activation.

* We can have one or more than one publish AEM instance.

![AEM Replication Image](/AEM/Images/Multiple.png)

## Replication Agent

* Replication agent is a configuration which help us to publish content from author to publish instance. Replication agents needs to be created for each publish instance.

## Follow below steps to create replication agent:

1. Navigate to below URL and select Configuration tile.

http://localhost:4502/sites.html/content

![AEM Replication Image](/AEM/Images/Replication%20Image/replication1.png)

2. Traverse to Replication option which will have Agents on author and Agents on publish option.

http://localhost:4502/etc/replication.html


![AEM Replication Image](/AEM/Images/Replication%20Image/rep.png)


3. Click Default Agent to open the default replication agent 

![AEM Replication Image](/AEM/Images/Replication%20Image/replication%20Image%20Author.png)


4. Then click on “Edit” after Settings to open the Agent Settings dialog box to enter the details.

![AEM Replication Edit](/AEM/Images/Replication%20Image/replication%203.png)

5. Under the settings tab, update the following

6. Enabled — check true

7. Agent user ID — Leave this empty

![AEM Replication Edit](/AEM/Images/Replication%20Image/replication%204.png)

8. Under the transport tab  update The “URI” with the host name and port number 

9. Configure URI — http://localhost:4503/bin/receive?sling:authRequestLogin=1

10. update the “User” and “Password“, As per your publish instance User Name and Password. (For me: User: admin, Password: admin)

![AEM Replication Edit](/AEM/Images/Replication%20Image/replication%205.png)

11. Click on “OK” and then click on “Test Connection“

![AEM Replication Edit](/AEM/Images/Replication%20Image/replication%206.png)

12. If all are okay then you can see a page with “Replication test succeeded“

13. you can go to the author package manager, select a package and from the more option replicate the package.

![AEM Replication Edit](/AEM/Images/Replication%20Image/replicate2.png)

## Reverse Replication

* AEM Publish instance generally hosted on 4503 port and available to access for end users.

* As part of reverse replication, content will get replicate or transfer from publish instance to author.

* Out of the box, only cq:Page is applicable for reverse replication. For other node it require to write custom code.

* Reverse replication needs to be triggered if there is any change in the content. Add cq:lastModified, cq:lastModifiedBy, cq:distribute properties as part of an event to fire reverse replication agent.

* At the time of activation please clear cq:lastModified, cq:lastModifiedBy, cq:distribute properties to avoid infinite loop.


**Reverse Replication is not available in AEM cloud version**