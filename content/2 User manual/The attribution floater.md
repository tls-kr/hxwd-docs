# The floater
This is a panel that shows at the right hand part of the screen upon selecting one or more characters from a text line or clicking on the text line.  Originally, it was used to conveniently add attributions to the text, hence the name *Attribution floater*, which was originally coined by Tobias Wilke. 
Since then, it acquired a number of other duties, so here we will simply call it *floater*.  Much of the interaction with the system happens in the floater, which can change shape in various ways, hence a number of different screenshots to explain.
Most of these have in common that they act on a specific line that has been the source of the selection, this is marked as **section 4** in the following image.  It gives in a greyish font the internal identifier ('At:')of the [[Segment|line]], followed by the textual content of the line. This identifier uniquely identifies this specific location in this text. When reporting errors in the system, you might be ask to provide this to allow narrow down the problem. 
# The many faces of the floater
## Listing by concept
![[floater-xue-by-concept.png]]
This is the original and still most common display of the list of [[Syntactical Word|Syntactical Words]] (SW) for a given character. The first layer of this list gives only the character, the reading (pronunciation) relevant for this case and the [[Concept]] to which the SW under this heading have been assigned.  The exact content of this top line is given below in **section 6**.

### Explanation for the numbered sections
1. The search facility. While the floater is shown, the behavior of the search button has been changed in the way that instead of displaying the [[Search results|results on a separate page]], the results are [[Search results floater|displayed on the floater]], replacing the list of characters. 
2. Here we have the title for the floater, we are looking at existing Syntactical Words for 學. This is the term that has been used to evoke the floater, here it also serve as a link to a separate external dictionary. The button labeled 'WD' in turquoise  is also an external link, activating this button will execute a search on this term in [Wikidata](https://www.wikidata.org), which might or might not be useful.  It offers to link the WD item to the current term, which is a way to link from our system to the wild world of external data. 
3. The lookup domain is 'Core' for most purposes; we have a mechanism here to provide for specialized vocabulary that should not clutter up the core display.  At the moment, the only other domain is 'Medical'.
4. As a reminder of what [[Segment|line]] we are talking about, here is the identifier and content of the line.
5. This is a section that looks not much here, but for some users it can become quite crowded. The upper area of the box here is the bookmarking tool -- you can bookmark any location here if you want to find it again at some later point. The lower part has three items:
	1. The *speak-bubble icon* will call up a general mechanism for [[Recording observations|recording observations]] on this text location, either for this line, or for a text passage starting at this line. 
	2. The *gear icon* is a shape-shifter: It will cycle you through a number of different ways to display the list of SW, as explained below.  At this moment, there are three ways to display the list, repeated clicking on this icon will bring you back to the first one at some point. 
	3. The *question mark icon* is your way out everywhere when you are lost, this will call up the documentation, for your convenience opened at the page most needed in this situation: As is to be expected, on this specific screen, it will open this very page you are reading now. 
6. And finally, this is the 'by concept' listing of the SW. To make it easier to find the concept you are looking for, this list is alphabetical by name of concept.  One row in the list has several items:
	1. The character (or term) we are talking about, followed by the reading for this use case. The character is a link to the [[Character taxonomy]] for this character. 
	2. The uppercase term in blue is the label for a [[Concept]]. Hovering over this will give you a definition of this Concept, clicking will leave this page and bring you to the concept, at the place where this SW is mentioned.   In some cases, such as 'INVESTIGATE' on this screen, there are initials of the contributor who provided this specific addition; these are only available for relatively recent additions.
	3. The button *New SW* will allow you to [[Adding a new SW|define a new SW]] and associate it with this Concept.
	4. The button *LW* is used to [[Adding a word relation|record word relations]], which are a *left word* and a *right word* connected by one of a number of relations.
	5. The button *SYN* (for *synonyms*) shows a discussion of the various characters that have been used for aspects of the Concept in question, the term under examination here is not necessarily part of that discussion.  A sample is shown below.
	6. Finally, and importantly, the last item in this box is a button labelled *1*: the number here indicates that for this specific concept, *this* number of Syntactic Words has been defined. The number does **not** indicate how many times this has been used. 
### Some more examples
#### Syntactic words for 學 / STUDY
![[floater-xue-study-25-sw-src.png]]

Clicking on the button *25* in the first screen will open the display as shown here.  We can now look at the 25 syntactical words defined for the different usages and shades of meaning of 學 within the broad Concept of STUDY. 
The section starts out with a general definition, that governs all specific usages. We show then, in alphabetical order of the [[Syntactical function]] the list of 25 SWs. There are two places were further interaction is possible:
1. The *Use* button will register the current [[Syntactical Word Location|SWL]]  as a citation for this text location for this specific use.
2. The button *SWL:number* can be used to actually show the previously register citations. One example for this is shown below.
#### Syntactic word locations for a **vt+V[0]**
As promised, here are 9 SWLs.
![[floater-xue-study-swl-src.png]]
Every attribution indicates the text with a shortened title and text section (as a link to the actual text location), followed by the line and one possible translation of this line, lastly there are again the initials of the contributor. 
## Listing by syntactical function
![[floater-xue-by-syn-func-src.png]]
## Listing by frequency
![[floater-xue-by-freq-src.png]]