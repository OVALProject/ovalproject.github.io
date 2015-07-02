---
title: Authoring Style Guide
layout: flat
no_in_page_title: true
---
<a name="top"></a>
<h1>{{ page.title }}</h1>

<p>This is a living document that details style guidelines for content in the <a href="http://oval.mitre.org/repository/">OVAL Repository</a>. This document will be updated as new decisions are made and questions are answered on the <a href="http://oval.mitre.org/community/archives.html">OVAL Repository Forum</a>.</p>
<p>Please verify that all submissions to the OVAL Repository align with these guidelines prior to posting a submission. These stylistic decisions have been codified where possible as a set of <a href="http://oval.mitre.org/repository/download/schema/oval-authoring-style-checker.sch">Schematron rules</a>.</p>
<p>For information on submitting new and modified content to the OVAL Repository, please review the <a href="/documentation/repository">Submission Guidelines</a>.</p>
<h4><a name="general" id="general"></a>General</h4>
<ul>
<li>Include meaningful comments. Comments should always be used on definitions, definition criteria, tests, objects, states, and variables. Keep in mind that comments may be displayed in various tool user interfaces and comments are searchable in the OVAL Repository. Since many items are reused across multiple tests and definitions make sure that each comment has enough detail to stand alone.</li>
<li>Additional metadata beyond what is defined by the <a href="http://oval.mitre.org/language/latest/">OVAL Definition Schema</a> and the <a href="http://oval.mitre.org/repository/download/schema/oval-repository-metadata-schema.xsd">OVAL Repository Metadata Schema</a> is not permitted in the OVAL Repository.</li>
<li>Reuse existing content when possible. When creating a new item, care should be taken to ensure that any preexisting item is reused. Reusing items cuts down on content maintenance cost and greatly reduces the effort required to write a new OVAL Definition.</li>
<li>When deprecating an item, make sure it is not referenced by any other item that is not also deprecated.</li>
<li>When deprecating an item, also deprecate any referenced items that are not referenced by any other item that is not also deprecated.</li>
<li>When using regular expressions ensure that the expression is appropriately anchored (started with a ^ and ended with a $). Otherwise, the expression may match undesired strings.</li>
</ul>

<div align="right" style="margin:5px 0px 5px 0px; clear:right"><a href="#top">Back to top</a></div>


<h3><a name="definitions" id="definitions"></a>Definitions</h3>
<h4>General</h4>
<ul>
<li>Do NOT set a comment on the definition’s root criteria element.</li>
<li>Set a comment on all other criteria, criterion, and extend_definition elements.
	<ul>
	<li>On a criterion element the comment should match the comment on the referenced test.</li>
	<li>On an extend_definition element the comment should match the title on the extended definition.</li>
	<li>On a criteria element the comment should summarize the comments of its contents.</li>
	</ul>
</li>	
<li>Do NOT include the negate attribute on criteria, criterion, or extend_definition elements when the element is not negated. Setting negate to false simply reduces readability.</li>
<li>Reuse other OVAL Inventory Definitions for applicable platform detection.</li>
<li>Defintion references should comply with the following overall guidelines:
	<ul>
	<li>Reference IDs should comply with the particular enumeration's identifier conventions.  (For example, all CVE IDs start with 'CVE-')</li>
	<li>Any reference URLs should start with the pattern 'http(s)://'.</li>
	<li>Definitions should not have multiple references.</li>
	</ul>
</li>
</ul>

<h4>Vulnerability Definitions</h4>
<ul>
<li>Vulnerability based OVAL Definitions must have their class attribute set to "vulnerability".</li>
<li>Vulnerability based OVAL Definitions should include only the checks required to determine the presence of a vulnerability on a given host.</li>
<li>It is strongly recommended that Vulnerability based OVAL Definitions include a <a href="http://cve.mitre.org/cve" target="_blank">CVE reference</a>.  Additionally, non-CVE references are also allowed, though multiple CVE references are not.</li>
<li>Vulnerability based OVAL Definitions should have a one-to-one relationship with a given CVE name.</li>
<li>Vulnerability based OVAL Definitions must use the description of the referenced CVE. The OVAL Repository automatically updates the description of OVAL Definitions with CVE references to match the official description of the CVE.</li>
</ul>

<h4>Patch Definitions</h4>
<ul>
<li>Patch based OVAL Definitions must have their class attribute set to "patch".</li>
<li>Patch based OVAL Definitions should include checks for all items that a patch includes. If a patch includes 6 files and sets 2 registry keys, the corresponding OVAL Definition should include 6 file_tests and 2 registry_key tests.</li>
<li>Patch based OVAL Definitions should include a reference to the patch binary name for which the definition was written. This means that there may be many OVAL Definitions written for a given security bulletin.  The 'source' for the reference should be 'VENDOR'.</li>
<li>Patch based OVAL Definitions should have a one-to-one relationship with a given patch binary name.</li>
</ul>

<h4>Inventory Definitions</h4>
<ul>
<li>Inventory OVAL Definitions must have their class attribute set to "inventory".</li>
<li>Inventory OVAL Definitions should include only the checks required to determine the presence of an application or operating system on a given host.</li>
<li>Inventory OVAL Definitions should include one and only one <a href="http://cpe.mitre.org/dictionary/" target="_blank">CPE reference</a>.</li>
<li>Inventory OVAL Definitions should have a one-to-one relationship with a given CPE name.</li>
</ul>

<h4>Compliance Definitions</h4>
<ul>
<li>Compliance based OVAL Definitions must have their class attribute set to "compliance".</li>
<li>Compliance based OVAL Definitions should leverage external_variables for specifying compliance values.</li>
<li>Compliance based OVAL Definitions should include one and only one <a href="http://cce.mitre.org/lists/cce_list.html" target="_blank">CCE reference</a>.  Other references can be derived from the CCE reference.</li>
<li>Compliance based OVAL Definitions should have a one-to-one relationship with a given CCE name.</li>
</ul>

<h4>Definition Metadata</h4>
<ul>
<li>Reuse platform and product names. When selecting the affected platforms and products, review the platforms and products that are already in the OVAL Repository and reuse them or create new names that are similar. This will greatly improve searching the definition metadata.</li>
<li>Only include a single reference.</li>
<li>Do NOT use operating system names as products. Operating system names are treated as platforms.</li>
</ul>

<div align="right" style="margin:5px 0px 5px 0px; clear:right"><a class="backtop" href="#top">Back to top</a></div>


<h3><a name="tests" id="tests"></a>Tests</h3>
<ul>
<li>Always include the check_existence attribute on tests. The check_existence attribute was added to Version 5.3 of the OVAL Definition Schema and has a default value of "at_least_one". Since this is a new attribute on tests we have decided to always include it in the OVAL Repository, even when the desired value is the default value.</li>
</ul>

<h3><a name="objects" id="objects"></a>Objects</h3>
<ul>
<li>Do NOT set datatype and operation attributes on the child elements of an object when they are the default values. This greatly improves readability.</li>
<li>Avoid using regular expressions in objects. Regular expressions have historically been error prone, reduce readability, and their evaluation during data collection can be costly.</li>
</ul>

<h3><a name="states" id="states"></a>States</h3>
<ul>
<li>States tend to be the exception to the reuse rules mentioned above. The OVAL Repository allows duplicate states to accommodate situations where a given state may have different meanings. For example, a registry_state with a value of 1 could mean "enabled" in one test, and "version 1" in another test. Inappropriate reuse of states in the OVAL Repository will likely make content maintenance more difficult. When in doubt, create a new state. This will likely help cut down on content maintenance costs over time.</li>
<li>Do NOT set the operator attribute on the state element if it is the default value. Setting this attribute does not improve readability.</li>
<li>Do NOT set datatype and operation attributes on the child elements of a state when they are the default values. Setting these attributes does not improve readability.</li>
</ul>

<h3><a name="variables" id="variables"></a>Variables</h3>
<ul>
<li>External variables should make use of the possible_value and possible_restriction elements to tightly restrict the allowable set of input values. This will assist tools in processing the variable and help other content authors when reviewing the variable.</li>
</ul>

<div align="right" style="margin:5px 0px 5px 0px; clear:right"><a class="backtop" href="#top">Back to top</a></div>

