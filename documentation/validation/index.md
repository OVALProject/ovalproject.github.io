---
title: Validating an OVAL Document
layout: flat
no_in_page_title: true
---
<a name="top"></a>
<h1>{{ page.title }}</h1>
<div class="row" style="border-top:1px solid;border-bottom:1px solid">
	<div class="col-md-12 text-center">
		<a class="btn btn-link" href="#introduction">Introduction</a>|
		<a class="btn btn-link" href="#w3c_schema_validation">W3C Schema Validation</a>|
		<a class="btn btn-link" href="#schematron_validation">Schematron Validation</a>|
		<a class="btn btn-link" href="#references">References</a>
	</div>
</div>
<a name="introduction"></a>
<div class="row">
	<h3>Introduction</h3>
	<p>The structure of an XML document written in OVAL is guided by an XML schema. This schema determines things such as what entities are available to specific tests and the order of objects and states within the language. The goal of validation is enforce a common and expected structure amongst the OVAL documents being passed between different users. This allows tools to be written against this expectation.</p>
	<p>In a way, validation makes sure that an OVAL document is in fact an OVAL document.</p>
	<p>Note that an OVAL document could be an OVAL Definition file, an OVAL System Characteristics file, or an OVAL Results file.</p>
</div>
<div style="float:right"><a class="btn btn-link" href="#top">Back to Top</a></div>
<a name="w3c_schema_validation"></a>
<div class="row">
	<h3>W3C Schema Validation</h3>
	<p>W3C Schema, also known as XSD, is an XML format used to describe things like elements and types that are found within a specific XML instance document. A XML document is an OVAL document when it validates against the OVAL W3C Schema.</p>
	<p>Performing this validation step is provided in most XML tools. You will usually need to place the OVAL documents in the same directory as the OVAL Schema files. This requirement can be worked around but will not be discussed here.</p>
	<p>Once all the files are in the same directory, use your XML tool to open up the OVAL document you wish to validate. Then find the menu item that says Validate XML. You should be presented with a success or failure result and any problems should be pointed reported. Of course, each tool is different so consult your specific tool's documentation for more details.</p>
	<center><img src="/images/validation_1.jpg" alt="screenshot"/></center>
	<br />
	<center><img src="/images/validation_2.jpg" alt="screenshot"/></center>
	<br />
	<p>For those working on developing <a href="//oval.mitre.org/compatible/index.html">OVAL-Compatible</a> tools, W3C Schema validation can be performed behind the scenes and hidden from the user. Libraries are in many of the most popular languages and can be added to your code to perform the necessary validation. Validation of incoming documents is generally a good idea as it makes certain that it is an OVAL document that is being worked on. Some popular code libraries are included in the <a href="#references">References</a> below.</p>
</div>
<div style="float:right"><a class="btn btn-link" href="#top">Back to Top</a></div>
<a name="schematron_validation"></a>
<div class="row">
	<div class="col-md-8">
		<h3>Schematron Validation</h3>
		<p>Unfortunately, there are many things that cannot be validated with W3C Schema. Maybe the most pertinent example is trying to validate that a particular element exists based on the value of an attribute. To validate these types of conditions, ISO Schematron rules have been included with the OVAL Schema.</p>
		<p>The process of Schematron Validation is a bit more complex than W3C Schema Validation. The Schematron rules found imbedded within the OVAL Schema must be collected into their own file. This can be done one of two ways. The first (and by far the simplest) is to download the Schematron file from the OVAL Web site. The other is to use an XSL Stylesheet to pull the Schematron rules out from the OVAL Schema.</p>
		<p>Once a copy of the OVAL Schematron file has been found/generated, a Schematron implementation can be used to perform the validation. There are many different types of Schematron implementations available. Some convert the Schematron file into a XSL stylesheet and use standard XSL tools to perform the validation. Others read in the Schematron file directly and perform Schematron validation in a similar way to W3C Schema validation.</p>
		<p>As with W3C Schema validation, Schematron can be imbedded inside the code of an OVAL-Compatible tool. Schematron libraries have been for most major programming languages. See the <a href="#references">References</a> section below for some popular code libraries.</p>
	</div>
	<div class="col-md-4">
		<img src="/images/validation_3.gif" alt="Schematron Process" />
	</div>
</div>
<div style="float:right"><a class="btn btn-link" href="#top">Back to Top</a></div>
<a name="references"></a>
<div class="row">
	<h3>References</h3>
	<p>Answers to almost every question pertaining to XML, W3C Schema Validation, and Schematron can be found at:</p>
	<ul>
		<li>O'Reilly XML.com - <a href="http://www.xml.com">http://www.xml.com</a></li>
		<li>W3C XML Schema - <a href="http://www.w3.org/standards/xml/schema">http://www.w3.org/standards/xml/schema</a></li>
		<li>ISO Schematron - <a href="http://www.schematron.com">http://www.schematron.com</a></li>
	</ul>
	<p>W3C Schema Validation tools:</p>
	<ul>
		<li>NetBeans - <a href="http://www.netbeans.org">http://www.netbeans.org</a></li>
		<li>&lt;oXygen/&gt; - <a href="http://www.oxygenxml.com">http://www.oxygenxml.com</a></li>
		<li>Altova XMLSpy - <a href="http://www.altova.com">http://www.altova.com</a></li>
	</ul>
	<p>Code library:</p>
	<ul>
		<li>Xerces - <a href="http://xerces.apache.org">http://xerces.apache.org</a></li>
	</ul>
	<p>Schematron Validation tools:</p>
	<ul>
		<li>topologi - <a href="http://www.topologi.com">http://www.topologi.com</a></li>
	</ul>
</div>
<div style="float:right"><a class="btn btn-link" href="#top">Back to Top</a></div>