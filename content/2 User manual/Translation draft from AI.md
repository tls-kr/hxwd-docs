---
created: 2025-04-25T11:31
updated: 2025-04-25T14:40
---
While I recognize that the current turn to AI is speeding up the waste of precious water and increases the dependency on non-sustainable sources of energy, and although it is often hallucinating, still presenting its result eloquently and without any trace of shame, there is a pull from the sheer pleasure and convenience of having an astonishingly readable and in many cases justifiable translation of **any** passage of Classical Chinese appearing in an instance before your eyes!  You might have to try this to believe, so here is how you can do so.

**Experimental** support for requesting a draft translation has been implemented in HXWD now (as of 2025-04-25). Since this is experimental, I tried to minimize the user interface elements that need to be implement to support this properly, and just made some arrangements behind the scenes, that would make a new button (with the label 'AI' to minimize screen space) appear on the header of a translation: 

![[translation-with-ai-button.png]]

## How to get the AI button

This button is enabled for all users who are logged in by default, based on the following condition:

The field *Creator* in the 'Edit [[Translation files|translation file]]' dialog has to have the value 'TLS Project',
as shown here:

![[edit-translation-file-tls-project.png]]

That is all for the moment.  With this in place, the system should display the blue 'AI' button for you. To be clear, this works only for *translation files*, not for *comment files*.

## What happens when the AI button is clicked

The AI button will trigger a request to the **Google Gemini** server requesting a translation draft of the **currently displayed text section** [^1], using the model **gemini-2.0-flash**. The language to translate in is based on the language in the translation file, so for different languages, different files have to be created.

The translation is saved into the system with the name of the model as 'responsible user'.  This translation can of course be modified (as always); any modification will be credited to the currently logged in user. 

Repeated clicking of the AI button for the same text passage will overwrite the previous translation draft, **unless** it has been modified.  Modified translations will **not** be overwritten by a new version. 

[^1]: To provide a bit more context to the AI engine, some lines are added before and after the text passage on display.  At the moment, of these extra lines only the lines that *follow* the passage currently displayed are actually saved, while the preceding lines are discarded.
