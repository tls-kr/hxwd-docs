---
draft: "true"
---

The documents here are meant to illuminate the intentions behind the design decisions and the actual implementation.  Hopefully, they will also serve as a documentation and help in project archaeology, once that becomes necessary.

# Overall architecture

`tls-app` is a monolithic app, serving HTML code and Javascript to the browser, which then calls back with interactions from the user.  I will call this a **kitchen table** design, since it seems like sitting in the middle of a kitchen and randomly assemble grab bits and pieces to shove into the mouth, instead of preparing a menu to be served in the hall.   So the idea is to get from here to the **restaurant** design, where items are ordered from the menu, prepared from organic ingredients and delivered in a well-balanced and nutritious form to the patrons. 

## The kitchen
This is the server back-end, where the lexical and text data are accessed.

## The menu
List our offerings, portion sizes and prizes. Technically speaking, this is the API specification, which defines what comes out of the kitchen and goes into the hall in what packaging. In addition to the orders from the hall, we might also offer take-out services. 
## The hall
This is where our patrons sit and enjoy the offerings.  Technically speaking, this is the browser window. 

## The basement
Here is where our data live.  We might also deliver to other outlets. 