---
title: Collaborative editing
draft: "false"
created: 2024-11-08T16:37
updated: 2024-12-13T15:51
---
# Collaborative editing

The HXWD website is built for distributed collaborative [[Translation|translation]] and [[Annotation|annotation]]. As long as you do not use the special features that support this kind of work, you can use it just as any other website. 
Once you start with the work, however, you need to be aware of some properties of the underlying technology. 
The protocol that enables browsers to display content from websites is a so-called asynchronous protocol.  What this means is that the browser will make a request to the server, wait for the answer and after receiving it will immediately close the connection until the user initiates the next request.  

For collaborative editing, this means that if a user requests a page, edits some content on that page, for example by adding a new line to a translation, that new content will **not** show up on the browser of other users that already loaded the page -- those other users will only learn of the new content when they refresh the page, for example by clicking on the reload button on your browser.

One additional result is, that if the other users edit *that same line* of translation on their own device, this line will be saved to the server and **overwrite** the line of the first user, without either of the two being aware of this fact.  Neither browser, nor the server has a way of even knowing that this kind of thing is happening. 

Most of the time, this does not pose a problem because there are thousands and thousands of pages on the system and it is quite rare for users to work on the same line at the same time. 

For **classroom** settings, however, this situation is **extremely likely**, if some text is translated together.  Users in such settings should thus get into the habit of frequently refreshing the page they are looking at together, in order to see the latest addition to a translation that is worked on together.  It would be best in such a situation to coordinate the editing and have one person entering the suggestions on behalf of all the contributors. 

A slightly different way of working around this problem is by having each of the participants working on separate files.  In this case, the risk of overwriting each others translation is smaller.  The whole group could still get an overview of the different translations suggested for a line by clicking on the line of Chinese texts without selecting anything -- this will trigger a display of all translations that are registered in the system for that line as a popup in the [[The attribution floater|floater]], in this case the information will be displayed as it is current on the server at the time this request is issued. 


