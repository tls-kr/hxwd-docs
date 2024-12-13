---
created: 2024-12-13T14:12
updated: 2024-12-13T15:49
---
Below is an example of the currently used internal format for attributions.   What this achieves is basically establishing a connection between a 'text line'  and an entry in the 'dictionary', more specifically, one 'sense' -- this is how the [[Syntactic Word]]s are actually stored.  Strictly speaking, only the information in the **\<link\>** element on line 4 is necessary, all other information items could be constructed from the database at the time of retrieval.  However, since the information in the database is constantly updated,  this might differ from what the user saw when creating this attribution, so it was deemed necessary to retain this information.  This also makes it easier to query the attributions as for example is done on the [[Citations]] screen.    In the database, these \<seg\> elements are in a XML file, which apart from the content marked with **tls:** conforms to the specifications of the TEI, with general information about the text, such as title and date of creation, available in the \<teiHeader\>.

```xml
<seg xml:id="T48n2020_CBETA_001-1006b0814.s2" xmlns="http://www.tei-c.org/ns/1.0">
    <line>「汝言見性，</line>
    <tls:ann xmlns:tls="http://hxwd.org/ns/1.0" concept="UNDERSTAND" concept-id="uuid-1a85cf98-.." xml:id="uuid-8c5eda8b...">
        <link target="#T48n2020_CBETA_001-1006b0814.s2 #uuid-c7d8bffd-4a23-443d-a76a-3dc190109701"/>
        <tls:text>
	        <tls:srcline title="高麗國普照禪師修心訣" target="#T48n2020_CBETA_001-1006b0814.s2" pos="1">「汝言見性，</tls:srcline>
	        <tls:line title="" transl-id="T48n2020-en-9555d308" src=""/>
        </tls:text>
        <form corresp="#uuid-9cb6b5ab.." orig="">
            <orth>見性</orth>
            <pron xml:lang="zh-Latn-x-pinyin">jiàn xìng</pron>
        </form>
        <sense corresp="#uuid-c7d8bffd-4a23-443d-a76a-3dc190109701">
            <gramGrp>
                <pos>V</pos>
                <tls:syn-func corresp="#uuid-091af450..">VPi</tls:syn-func>
                <tls:sem-feat corresp="#uuid-9b914785..">event</tls:sem-feat>
            </gramGrp>
            <def>understand one's essence</def>
        </sense>
        <tls:metadata resp="#chris" created="2024-11-13T21:39:12.08+09:00">
            <respStmt>
                <resp>added</resp>
                <name notBefore="2024-11-13T21:39:12.08+09:00">chris</name>
            </respStmt>
        </tls:metadata>
    </tls:ann>
</seg>
```

I will give a short explanation of the items represented here. For the purpose of making the example more readable, some of the internal id references have been shortened. 

The example starts out with a **\<seg\>** element, which contains one **\<line\>** element and a **\<tls:ann\>** element.  If there were more annotations to this line, they would all be listed here, one after the other, in no specific order. 

One annotation is contained in one single \<tls:ann\> element.  As explained above, all the information is also available elsewhere in the database and has simply been copied here, except for the last item \<tls:metadata\>, which has specific information on when and by whom this attribution was created.

As the database evolves and the analytic possibilities are increasing, it might become necessary to add information specific to this instance to the annotation, rather than simply treating it as an instance of the [[Syntactic Word]] to which it is linked. 