---
created: 2024-11-08T16:37
updated: 2024-10-28T15:17
---
Every translation is stored separately in a translation file, together with the other translation files in an area of the database set aside for this purpose.  The files are stored in sub-folders by language, since the internal processing required, for example for the search functionality, has to be fine-tuned for the language of the translation.  The system also allows the creation of 'comment files', which can carry comments to specific translations.

It is thus important to indicate the **correct language** for a translation file and **not to change** this, once the file has been created. 

The whole process of creating a new translation file is demonstrated in the following screencast.
![[Adding a new translation file.webm]]

## Explanation of the steps involved
In this example, a new translation file for a new translation into German of the 'Odes' is created:
1. In the header line of an existing translation (in this case the one in Slot 1 by Bernhard Karlgren), the little downward-pointing triangle is clicked to reveal a list of existing translations.  At the bottom of this list is an item in yellow 'New translation / comments.'  This button is clicked on.
2. A new dialog with the title 'Start a new translation or comment file for 毛詩'. Be careful to review the different items and selections to correctly reflect what you would like to do.  It is recommended to fill in the field 'Creator' all the times. 
3. The translations in the drop-down list are displayed by publication date, so it is important to enter the publication date as shown.
4. Once everything is entered correctly, click 'Save' to actually instruct the browser to send the information to the server, which will then create the file.
5. The success of this operation is signaled by the server with a popup message that shows up in the upper right corner of the screen for q few seconds. 
6. The translation header line in gray will now change and display 'no translation available' (at 1:05 in the screen cast).  This is slightly misleading, but is a result of updating the list of translations. Clicking on the drop-down triangle as before will reveal that a new translation file has been created, which can now be selected. 
7. At 1:15 in the screencast, the translation area has been clicked, and the translation can be entered.  The 'tab' or 'enter' key can be used to send the translation to the server and move to the next line at the same time. It is important not to use any other key (or mouse click) to leave the translation field.  -- If this happens by accident, the system will try to catch this problem and alert you of it, but it is best to avoid it in the first place.