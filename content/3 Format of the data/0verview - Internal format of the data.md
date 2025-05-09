---
created: 2024-11-08T16:37
updated: 2025-05-09T15:03
---
# Format

The data format that has been chosen for this application is [[XML]], which is essentially a structured format of text.  This is important, since computers can store data either as '**binary**' or as '**text**'.  

The **binary format**, also called 'machine readable', is not directly accessible, but always relies on a process that decodes the binary data into something humans can understand and displays this derived version to a user. Any changes made to this version will then have to be translated back into the binary representation for storage and internal use by the application.  Many computer programs are written in a human readable form, but are stored for execution in a binary format that is more efficient to use.    

**Text format** on the other hand is directly readable, without any intervention, at least in principle.  In practice, a format like XML is highly structured and contains several layers of information in a formalized way, thus is not easily understood or modified by non-experts. 

The TLS tries to combine the flexibility of the XML format with an interface that hides most of the complexity for the user.  This makes it possible to work in the system without knowing about the underlying data structures.  This is similar to a railway car that can only travel on the pre-laid rails,  which makes it easy to connect big cities, but leaves many places without access.  Working directly with the underlying source data, on the other hand, will allow the user to travel to even the most distant and remote places, but requires **more effort**.  It is for these users, that the description of the data format will provide a map, whereas [[XQuery]] will provide the means of transportation. 

The source data that is described here is also available for use outside of this application, at https://github.com/tls-kr/tls-data for the descriptive data and https://github.com/tls-kr/tls-texts for the text data.  Both are licensed under a [Creative Commons Attribution 4.0 International License](http://creativecommons.org/licenses/by/4.0/) (except for some translations), which allows users to share, modify and adapt the data, as long as they are attributed to the TLS Project. 

## Content of tls-data

In this repository, all descriptive data are collected, which includes the following items (there are some items which are only used for internal book keeping, such as 'schema', 'statistics' and 'vault', they are not described here):
- [[bibliography]] Bibliographic description of sources and references
- [[3 Format of the data/concepts|concepts]] Definition of the hierarchy of concepts in the TLS
- [[core]] In this collection, the definition of a number of additional descriptive features are collected:
	- [[concept-taxonomy]]
	- [[facts]]
	- [[rhetorical-devices]]
	- [[semantic-features]]
	- [[syntactic-functions]]
	- [[tax-char|Taxonomy of characters]]
	- [[taxonomy|Taxonomy of concepts]]
	- [[tax-word|Taxonomy of words]]
	- [[word-relations]]
- [[domain]] Collections of concepts in specialized domains, such as medical concepts
- [[external]] Data collections which are imported from external sources
- [[guangyun]] Phonetic database, originally based on the Guangyun 廣韻 rhyme dictionary
- [[notes]] A collection of annotation types
	- [[doc]] [[Syntactic Word Location]], stored by text document.
	- [[facts]] 
	- [[links]]
	- [rdl] [[Rhetorical Device Location]] 
	- [[search]] stored search results
	- [[swl]] An older format of Syntactical Word Locations
- [[translations]]  Not all translations that are displayed in the web interface are collected here, but only those that can be shared. The exact license terms depend on the translator and might differ from the license for the data.  
- [[3 Format of the data/words|words]] The [[Syntactic Word]] definitions are stored here.

## Contents of tls-texts

There are two sub collections here
- [[data]] The actual texts are here, with in principle one XML file per text, arranged in a way similar to the classified catalog on the web site. The [[Text format]] is based on the [[TEI Guidelines]]
- [[meta]] Some catalog data and other information about the texts.  