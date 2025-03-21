---
title: Transforming XML with XSLT
slug: Web/XSLT/Transforming_XML_with_XSLT
tags:
  - NeedsMigration
  - Transforming_XML_with_XSLT
  - XML
  - XSLT
---
{{XSLTRef}}

## An Overview

[An Overview](/en-US/docs/Web/XSLT/Transforming_XML_with_XSLT/An_Overview)

The separation of content and presentation is a key design feature of [XML](/en-US/docs/Web/XML). The structure of an XML document is designed to reflect and clarify important relationships among the individual aspects of the content itself, unhindered by a need to provide any indication about how this data should eventually be presented. This intelligent structuring is particularly important as more and more data transfers are automated and take place between highly heterogeneous machines linked by a network.

Yet eventually much of the content stored in XML documents will need to be presented to human readers. Because a browser provides a familiar and highly flexible interface, it is an ideal mechanism for delivering such presentation versions of XML content. Built from the ground up utilizing a wide variety of XML technologies, Firefox incorporates within itself all of the mechanisms needed to process both original XML documents and the specialized stylesheets used to style and lay them out for HTML display, reducing server load with client-side processing.

At present, Gecko (the layout engine behind Firefox) supports two forms of XML stylesheets. For basic control of appearance — fonts, colors, position, and so forth — Gecko uses [CSS](/en-US/docs/Web/CSS). 

Our focus here is on the second type of stylesheet that Gecko supports: the XSLT stylesheet. XSLT stands for eXtensible Stylesheet Language/Transform and the name is apt. XSLT allows a stylesheet author to transform a primary XML document in two significant ways: manipulating and sorting the content, including a wholesale reordering of it if so desired, and transforming the content into a different format (and in the case of Firefox, the focus is on converting it on the fly into HTML which can then be displayed by the browser).

## XSLT/XPath reference

### Elements

[Elements](/en-US/docs/Web/XSLT/Element)

- [xsl:apply-imports](/en-US/docs/Web/XSLT/Element/apply-imports) _(supported)_
- [xsl:apply-templates](/en-US/docs/Web/XSLT/Element/apply-templates) _(supported)_
- [xsl:attribute](/en-US/docs/Web/XSLT/Element/attribute) _(supported)_
- [xsl:attribute-set](/en-US/docs/Web/XSLT/Element/attribute-set) _(supported)_
- [xsl:call-template](/en-US/docs/Web/XSLT/Element/call-template) _(supported)_
- [xsl:choose](/en-US/docs/Web/XSLT/Element/choose) _(supported)_
- [xsl:comment](/en-US/docs/Web/XSLT/Element/comment) _(supported)_
- [xsl:copy](/en-US/docs/Web/XSLT/Element/copy) _(supported)_
- [xsl:copy-of](/en-US/docs/Web/XSLT/Element/copy-of) _(supported)_
- [xsl:decimal-format](/en-US/docs/Web/XSLT/Element/decimal-format) _(supported)_
- [xsl:element](/en-US/docs/Web/XSLT/Element/element) _(supported)_
- [xsl:fallback](/en-US/docs/Web/XSLT/Element/fallback) _(not supported)_
- [xsl:for-each](/en-US/docs/Web/XSLT/Element/for-each) _(supported)_
- [xsl:if](/en-US/docs/Web/XSLT/Element/if) _(supported)_
- [xsl:import](/en-US/docs/Web/XSLT/Element/import) _(mostly supported)_
- [xsl:include](/en-US/docs/Web/XSLT/Element/include) _(supported)_
- [xsl:key](/en-US/docs/Web/XSLT/Element/key) _(supported)_
- [xsl:message](/en-US/docs/Web/XSLT/Element/message) _(supported)_
- [xsl:namespace-alias](/en-US/docs/Web/XSLT/Element/namespace-alias) _(not supported)_
- [xsl:number](/en-US/docs/Web/XSLT/Element/number) _(partially supported)_
- [xsl:otherwise](/en-US/docs/Web/XSLT/Element/otherwise) _(supported)_
- [xsl:output](/en-US/docs/Web/XSLT/Element/output) _(partially supported)_
- [xsl:param](/en-US/docs/Web/XSLT/Element/param) _(supported)_
- [xsl:preserve-space](/en-US/docs/Web/XSLT/Element/preserve-space) _(supported)_
- [xsl:processing-instruction](/en-US/docs/Web/XSLT/Element/processing-instruction)
- [xsl:sort](/en-US/docs/Web/XSLT/Element/sort) _(supported)_
- [xsl:strip-space](/en-US/docs/Web/XSLT/Element/strip-space) _(supported)_
- [xsl:stylesheet](/en-US/docs/Web/XSLT/Element/stylesheet) _(partially supported)_
- [xsl:template](/en-US/docs/Web/XSLT/Element/template) _(supported)_
- [xsl:text](/en-US/docs/Web/XSLT/Element/text) _(partially supported)_
- [xsl:transform](/en-US/docs/Web/XSLT/Element/transform) _(supported)_
- [xsl:value-of](/en-US/docs/Web/XSLT/Element/value-of) _(partially supported)_
- [xsl:variable](/en-US/docs/Web/XSLT/Element/variable) _(supported)_
- [xsl:when](/en-US/docs/Web/XSLT/Element/when) _(supported)_
- [xsl:with-param](/en-US/docs/Web/XSLT/Element/with-param) _(supported)_

### Axes

[Axes](/en-US/docs/Web/XPath/Axes)

- [ancestor](/en-US/docs/Web/XPath/Axes/ancestor)
- [ancestor-or-self](/en-US/docs/Web/XPath/Axes/ancestor-or-self)
- [attribute](/en-US/docs/Web/XPath/Axes/attribute)
- [child](/en-US/docs/Web/XPath/Axes/child)
- [descendant](/en-US/docs/Web/XPath/Axes/descendant)
- [descendant-or-self](/en-US/docs/Web/XPath/Axes/descendant-or-self)
- [following](/en-US/docs/Web/XPath/Axes/following)
- [following-sibling](/en-US/docs/Web/XPath/Axes/following-sibling)
- [namespace](/en-US/docs/Web/XPath/Axes/namespace) _(not supported)_
- [parent](/en-US/docs/Web/XPath/Axes/parent)
- [preceding](/en-US/docs/Web/XPath/Axes/preceding)
- [preceding-sibling](/en-US/docs/Web/XPath/Axes/preceding-sibling)
- [self](/en-US/docs/Web/XPath/Axes/self)

### Functions

[Functions](/en-US/docs/Web/XPath/Functions)

- [boolean()](/en-US/docs/Web/XPath/Functions/boolean) _(supported)_
- [ceiling()](/en-US/docs/Web/XPath/Functions/ceiling) _(supported)_
- [concat()](/en-US/docs/Web/XPath/Functions/concat) _(supported)_
- [contains()](/en-US/docs/Web/XPath/Functions/contains) _(supported)_
- [count()](/en-US/docs/Web/XPath/Functions/count) _(supported)_
- [current()](/en-US/docs/Web/XPath/Functions/current) _(supported)_
- [document()](/en-US/docs/Web/XPath/Functions/document) _(supported)_
- [element-available()](/en-US/docs/Web/XPath/Functions/element-available) _(supported)_
- [false()](/en-US/docs/Web/XPath/Functions/false) _(supported)_
- [floor()](/en-US/docs/Web/XPath/Functions/floor) _(supported)_
- [format-number()](/en-US/docs/Web/XPath/Functions/format-number) _(supported)_
- [function-available()](/en-US/docs/Web/XPath/Functions/function-available) _(supported)_
- [generate-id()](/en-US/docs/Web/XPath/Functions/generate-id) _(supported)_
- [id()](/en-US/docs/Web/XPath/Functions/id) _(partially supported)_
- [key()](/en-US/docs/Web/XPath/Functions/key) _(supported)_
- [lang()](/en-US/docs/Web/XPath/Functions/lang) _(supported)_
- [last()](/en-US/docs/Web/XPath/Functions/last) _(supported)_
- [local-name()](/en-US/docs/Web/XPath/Functions/local-name) _(supported)_
- [name()](/en-US/docs/Web/XPath/Functions/name) _(supported)_
- [namespace-uri()](/en-US/docs/Web/XPath/Functions/namespace-uri) _(supported)_
- [normalize-space()](/en-US/docs/Web/XPath/Functions/normalize-space) _(supported)_
- [not()](/en-US/docs/Web/XPath/Functions/not) _(supported)_
- [number()](/en-US/docs/Web/XPath/Functions/number) _(supported)_
- [position()](/en-US/docs/Web/XPath/Functions/position) _(supported)_
- [round()](/en-US/docs/Web/XPath/Functions/round) _(supported)_
- [starts-with()](/en-US/docs/Web/XPath/Functions/starts-with) _(supported)_
- [string()](/en-US/docs/Web/XPath/Functions/string) _(supported)_
- [string-length()](/en-US/docs/Web/XPath/Functions/string-length) _(supported)_
- [substring()](/en-US/docs/Web/XPath/Functions/substring) _(supported)_
- [substring-after()](/en-US/docs/Web/XPath/Functions/substring-after) _(supported)_
- [substring-before()](/en-US/docs/Web/XPath/Functions/substring-before) _(supported)_
- [sum()](/en-US/docs/Web/XPath/Functions/sum) _(supported)_
- [system-property()](/en-US/docs/Web/XPath/Functions/system-property) _(supported)_
- [translate()](/en-US/docs/Web/XPath/Functions/translate) _(supported)_
- [true()](/en-US/docs/Web/XPath/Functions/true) _(supported)_
- [unparsed-entity-url()](/en-US/docs/Web/XPath/Functions/unparsed-entity-url) _(not supported)_

## For Further Reading

[For Further Reading](/en-US/docs/Web/XSLT/Transforming_XML_with_XSLT/For_Further_Reading)

- [Books](/en-US/docs/Web/XSLT/Transforming_XML_with_XSLT/For_Further_Reading#books)
- [Digital](/en-US/docs/Web/XSLT/Transforming_XML_with_XSLT/For_Further_Reading#digital)

  - [Websites](/en-US/docs/Web/XSLT/Transforming_XML_with_XSLT/For_Further_Reading#websites)
  - [Articles](/en-US/docs/Web/XSLT/Transforming_XML_with_XSLT/For_Further_Reading#articles)
  - [Tutorials/Examples](/en-US/docs/Web/XSLT/Transforming_XML_with_XSLT/For_Further_Reading#tutorials.2fexamples)
  - [Other](/en-US/docs/Web/XSLT/Transforming_XML_with_XSLT/For_Further_Reading#other)

## Original Document Information

- Copyright Information: Copyright © 2001-2003 Netscape. All rights reserved.
- Note: This reprinted article was originally part of the DevEdge site.
