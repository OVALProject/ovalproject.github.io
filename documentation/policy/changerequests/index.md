---
title: Requesting Changes to the OVAL Language
layout: flat
no_in_page_title: true
---
<a name="top"></a>
<h1>{{ page.title }}</h1>
<div class="row" style="border-top:1px solid;border-bottom:1px solid">
	<div class="col-md-12 text-center">
		<a class="btn btn-link" href="#new">New Constructs</a>|
		<a class="btn btn-link" href="#modify">Changes to Existing Constructs</a>|
		<a class="btn btn-link" href="#deprecate">Deprecating Constructs</a>|
		<a class="btn btn-link" href="#submit">Submission Instructions</a>
	</div>
</div>
<div class="row">
	<div class="col-md-12">
		<h3>Introduction</h3>
		<p>Community members are welcome to propose changes to the OVAL Language. This includes requests to:</p>
		<ul>
			<li>Add new OVAL Constructs (e.g., component schemas, core capabilities, tests, entities, or functions).</li>
			<li>Modify existing OVAL Constructs.</li>
			<li>Deprecate existing OVAL Constructs.</li>
		</ul>
		<p>Requests should be submitted to the <a href="https://oval.mitre.org/community/registration.html">OVAL Developer's Forum</a> for review by the OVAL community, or directly to <a href="mailto:oval@mitre.org">oval@mitre.org</a>. Guidelines for submitting change requests are included below.</p>
	</div>
</div>
<a name="new"></a>
<div class="row">
	<h3>Requests to Add New OVAL Constructs</h3>
	<p>To keep up with new technologies, platforms, and changing systems, it is often necessary to add new capabilities to the OVAL Language in order to support the collection of new system configuration information or to perform a new type of check. This may come in the form of new OVAL <a href="#new_component">Component Schemas</a>, <a href="#new_core">Core Capabilities</a>, <a href="#new_test">Tests</a>, <a href="#new_entity">Entities</a>, or <a href="#new_function">Functions</a>. Guidelines for submitting such constructs are noted below.</p>
	<a name="new_component"></a>
	<div class="panel panel-primary">
		<div class="panel-heading">
			<h4 class="panel-title">Submitting a New OVAL Component Schema</h4>
		</div>
		<div class="panel-body">
			<p>An OVAL Component Schema is a collection of OVAL Tests, Objects, States, and Items that are related based on the platform for which they can check or describe configuration information. In order to extend the OVAL Language to a new platform, it is necessary to develop a new OVAL Component Schema for that platform. The following describes the guidelines for proposing a new OVAL Component Schema for inclusion in the OVAL Language.</p>
			<ol>
				<li>What platform is the OVAL Component Schema for? Why is it needed?</li>
				<li>Provide a brief overview of each OVAL Test included in the proposed OVAL Component Schema. Please see <a href="#new_test">Submitting a New OVAL Test</a> below for more information on what to include.</li>
				<li>Provide the OVAL Definitions and System Characteristics schemas for the proposed OVAL Component Schema.</li>
				<li>Provide sample content that demonstrates the proposed OVAL Component Schema usage.</li>
				<li>How can the OVAL Tests in the proposed OVAL Component Schema be implemented?</li>
				<ol type="a">
					<li>Relevant APIs for each entity in the new OVAL Object, State, and Item</li>
					<li>Algorithms that can be followed</li>
					<li>Anything else that will help a developer implement support for the test</li>
				</ol>
				<li>Any additional information (references, caveats, etc.) that will be relevant in determining whether or not the OVAL Component Schema should be accepted as part of the OVAL Language.</li>
			</ol>
		</div>
	</div>
	<a name="new_core"></a>
	<div class="panel panel-primary">
		<div class="panel-heading">
			<h4 class="panel-title">Submitting a New OVAL Core Capability</h4>
		</div>
		<div class="panel-body">
			<p>The OVAL Core consists of the OVAL Definitions, System Characteristics, Results, Variables, and Directives Schemas. Additional functionality added to these schemas is considered a new OVAL Core Capability. The following describes the guidelines for proposing a new OVAL Core Capability to the OVAL Language.</p>
			<ol>
				<li>What is the proposed OVAL Core Capability? Why is it needed?</li>
				<li>What OVAL Core Schemas are affected by this new OVAL Core Capability?</li>
				<li>Are there multiple approaches to implementing the proposed OVAL Core Capability? If so, present each approach along with the relevant pros and cons.</li>
				<li>Does the proposed OVAL Core Capability represent a fundamental change to the OVAL Language?</li>
				<li>Provide sample content that demonstrates the proposed OVAL Core Capability use cases.</li>
				<li>Provide the relevant documentation associated with the proposed OVAL Core Capability.</li>
				<li>OPTIONAL: Implementing the proposal in the schema is recommended, but, not required.</li>
			</ol>
		</div>
	</div>
	<a name="new_test"></a>
	<div class="panel panel-primary">
		<div class="panel-heading">
			<h4 class="panel-title">Submitting a New OVAL Test</h4>
		</div>
		<div class="panel-body">
			<p>An OVAL Test is an OVAL Construct that correlates what OVAL Items on the system should be collected and how many of those OVAL Items must match the specified OVAL State(s) to evaluate to a result of 'true'. When proposing a new OVAL Test, it is necessary to also design the corresponding OVAL Object, State, and Item. The following describes the guidelines for proposing a new OVAL Test to the OVAL Language.</p>
			<ol>
				<li>What are the use cases for the proposed test? Why is it needed?</li>
				<li>What OVAL Component schema(s) are affected?</li>
				<li>What will the OVAL Object, State, and Item constructs look like?</li>
				<ol type="a">
					<li>Documentation explaining what each construct does.</li>
					<li>For each entity specify the following:</li>
					<ol type="i">
						<li>Name</li>
						<li>Documentation</li>
						<ol type="1">
							<li>What information does the OVAL Entity hold?</li>
							<li>If it makes use of the xsi:nil attribute, what does it mean when xsi:nil='true'?</li>
							<li>Are there any special restrictions on what the OVAL Entity can hold?</li>
						</ol>
						<li>Datatype</li>
						<li>Restrictions on the available operations</li>
						<li>Minimum/maximum occurrences</li>
						<li>Values if bound by an enumeration</li>
						<li>Does it make use of the xsi:nil attribute?</li>
						<li>How to implement the entity</li>
						<ol type="1">
							<li>Relevant APIs</li>
							<li>Algorithms that can be followed</li>
							<li>Anything else that will help a developer implement support for the entity</li>
						</ol>
					</ol>
					<li>OPTIONAL: Implementing the proposal in the schema is recommended, but, not required.</li>
				</ol>
				<li>Provide sample content that demonstrates the OVAL Test use cases.</li>
				<li>Any additional information (references, caveats, etc.) that will be relevant in determining whether or not the OVAL Test should be accepted as part of the OVAL Language.</li>
			</ol>
		</div>
	</div>
	<a name="new_entity"></a>
	<div class="panel panel-primary">
		<div class="panel-heading">
			<h4 class="panel-title">Submitting a New OVAL Entity</h4>
		</div>
		<div class="panel-body">
			<p>An OVAL Entity is a system configuration property in the OVAL Language. When an OVAL Entity is used in an OVAL Object or State, it represents something being specified about that system configuration property. When an OVAL Entity is used in an OVAL Item, it represents the system configuration property as collected from the system. The following describes the guidelines for proposing a new OVAL Entity to the OVAL Language.</p>
			<ol>
				<li>What are the use cases for the proposed OVAL Entity? Why is it needed?</li>
				<li>What constructs will be affected? Does it break backwards compatibility with previous versions of the OVAL Language? If so, please propose a new OVAL Test following the guidelines in <a href="#new_test">Submitting a New OVAL Test</a> above.</li>
				<li>For each entity specify the following:</li>
				<ol type="a">
					<li>Name</li>
					<li>Documentation</li>
					<ol type="i">
						<li>What information does the OVAL Entity hold?</li>
						<li>If it makes use of the xsi:nil attribute, what does it mean when xsi:nil='true'?</li>
						<li>Are there any special restrictions on what the OVAL Entity can hold?</li>
					</ol>
					<li>Datatype</li>
					<li>Restrictions on the available operations</li>
					<li>Minimum/maximum occurrences</li>
					<li>Values if bound by an enumeration</li>
					<li>Does it make use of the xsi:nil attribute?</li>
					<li>How to implement the entity</li>
					<ol type="i">
						<li>Relevant APIs</li>
						<li>Algorithms that can be followed</li>
						<li>Anything else that will help a developer implement support for the entity</li>
					</ol>
					<li>OPTIONAL: Implementing the proposal in the schema is recommended, but, not required.</li>
				</ol>
				<li>Any additional information (references, caveats, etc.) that will be relevant in determining whether or not the OVAL Entity should be accepted as part of the OVAL Language.</li>
			</ol>
		</div>
	</div>
	<a name="new_function"></a>
	<div class="panel panel-primary">
		<div class="panel-heading">
			<h4 class="panel-title">Adding a New OVAL Function</h4>
		</div>
		<div class="panel-body">
			<p>An OVAL Function is an OVAL Construct that is used to manipulate or perform some operation on a specified set of values at run-time. The following describes the guidelines for proposing a new OVAL Function to the OVAL Language.</p>
			<ol>
				<li>What does the function do? Why is it needed?</li>
				<li>Are there any requirements on the number of arguments or datatypes of those arguments?</li>
				<li>Any there any attributes necessary to drive the function?</li>
				<li>Provide documentation for the proposed OVAL Function</li>
				<ol type="a">
						<li>What does the function do?</li>
						<li>How should the function process the arguments?</li>
						<li>Functionality of attributes (if applicable)</li>
						<li>Boundary and error conditions (if applicable)</li>
						<li>Restrictions on the number of arguments or their datatypes (if applicable)</li>
						<li>Other useful documentation</li>
					</ol>
				<li>Sample content that demonstrates its use cases.</li>
				<li>OPTIONAL: Implementing the proposal in the schema is recommended, but, not required.</li>
			</ol>
		</div>
	</div>
	<div style="float:right"><a class="btn btn-link" href="#top">Back to Top</a></div>
</div>
<a name="modify"></a>
<div class="row">
	<h3>Requests to Add New OVAL Constructs</h3>
	<ol>
		<li>What construct needs to be modified? Why does it need to be modified (e.g. missing or ambiguous documentation, datatype does not match the value, incorrect minimum/maximum occurrences, etc.)?</li>
		<li>Does it break backwards compatibility with previous versions of the OVAL Language? If so, should it be considered under the Exceptions clause of the OVAL Language Versioning Methodology? Please see <a href="/documentation/policy/versioning/">OVAL Language Versioning Methodology</a> for more information.</li>
		<li>Present the improvements</li>
		<ol type="a">
			<li>Revised or additional documentation</li>
			<li>Describe changes to the schema</li>
			<li>OPTIONAL: Implementing the changes in the schema is recommended, but not required.</li>
		</ol>
	</ol>
	<div style="float:right"><a class="btn btn-link" href="#top">Back to Top</a></div>
</div>
<a name="deprecate"></a>
<div class="row">
	<h3>Requests to Deprecate OVAL Constructs</h3>
	<p>When an OVAL Construct contains security issues, results in inconsistency, or uses obsoleted technologies or methodologies it may be desirable to deprecate it in the OVAL Language. For more information please see the <a href="/documentation/policy/deprecation/">OVAL Language Deprecation Policy</a>. The following describes the guidelines for requesting the deprecation of OVAL Constructs in the OVAL Language.</p>
	<ol>
		<li>What OVAL Construct should be deprecated? Why should the OVAL Construct be deprecated?</li>
		<li>Should a new OVAL Construct be recommended to replace it? If so, please refer to relevant sub-section in Submitting a Request to <a href="#new">Add New OVAL Constructs</a> above.</li>
	</ol>
	<div style="float:right"><a class="btn btn-link" href="#top">Back to Top</a></div>
</div>
<a name="submit"></a>
<div class="row">
	<h3>Submission Instructions</h3>
	<ol>
		<li>Draft an email message that contains the information described above.</li>
		<li>Attach any relevant documents to the message such as schema changes, sample content, etc.</li>
		<li><p>Send the message to the <a href="https://oval.mitre.org/community/registration.html">OVAL Developers Forum</a> at <a href="mailto:oval-developer-list@lists.mitre.org">oval-developer-list@lists.mitre.org</a> for review by the OVAL Community. Note that you must be a member of the OVAL Developer's Forum to send a message to the list.</p><p>Alternatively, those wishing to submit sensitive information may send it directly to <a href="mailto:oval@mitre.org">oval@mitre.org</a>.</p></li>
	</ol>
	<div style="float:right"><a class="btn btn-link" href="#top">Back to Top</a></div>
</div>