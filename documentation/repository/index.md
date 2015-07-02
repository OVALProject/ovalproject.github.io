---
title: Submit an OVAL Definition
layout: flat
no_in_page_title: true
---
<a name="top"></a>
<h1>{{ page.title }}</h1>

<p>Members of the information security community may submit properly formatted OVAL Vulnerability, Compliance, Inventory, and Patch Definitions to the <a href="http://oval.mitre.org/community/registration.html">OVAL Repository Forum</a>, where they are reviewed by the OVAL Moderator before being put into the <a href="http://oval.mitre.org/repository/">OVAL Repository</a> for use by the community.</p>

<h3 style="margin-top:1.5em"><a name="guidelines" id="guidelines"></a>Guidelines</h3>
<p>Before submitting any content to the OVAL Repository, please review the following resources:</p>
<ul>
<li><a href="authorsresources">OVAL Author’s Resources</a></li>
<li><a href="https://github.com/OVALProject/Language">OVAL Definition Schema</a></li>
<li><a href="styleguide">Authoring Style Guide</a></li>
</ul>

<h4>New Content</h4>
<ol>
<li>Review existing OVAL Definitions in the OVAL Repository to ensure one does not already exist for the software vulnerability, configuration issue, program, or patch you are working on.</li>
<li>Set the version to 0 on all new definitions, tests, objects, states, and variables. The version will be incremented to 1 when the item is uploaded to the repository. The OVAL Repository manages versions. <em>PLEASE DO NOT MODIFY THE VERSION OF EXISTING ITEMS IN THE OVAL REPOSITORY.</em></li>
<li>For new definitions, assign a definition ID in a temporary namespace (e.g., org.your_organization.oval). Once the definition is added to the OVAL Repository it will be assigned an ID in the OVAL Repository namespace (org.mitre.oval) by the OVAL Moderator. <em>PLEASE DO NOT ISSUE NEW IDS IN THE OVAL REPOSITORY NAMESPACE.</em></li>
</ol>

<h4>Modified Content</h4>
<ol>
<li>Submit only the items you edit. If you edit a state, submit only that state and its dependencies. Please do not submit all definitions that use the edited item.</li>
<li>Do not modify the version of the items you edit. The OVAL Repository manages versions. <em>PLEASE DO NOT MODIFY THE VERSION OF EXISTING ITEMS IN THE OVAL REPOSITORY.</em></li>
</ol>

<h4>Submission Validation</h4>
<p>Please perform the following checks to ensure that the content being submitted is in the proper format.</p>
<ol>
<li><a href="/documentation/validation">Validate</a> the file to ensure that it is a valid OVAL document.</li>
<li>Run the current <a href="http://oval.mitre.org/language/latest/ovaldefinition/schematron/oval-definitions-schematron.sch">OVAL Schematron</a> rules (oval-definitions-schematron.sch) to ensure the document complies with the official OVAL Definition Schema.</li>
<li>Check against the <a href="http://oval.mitre.org/repository/download/schema/oval-repository-metadata-schema.xsd">OVAL Repository Metadata Schema</a> (oval-repository-metadata-schema.xsd) to verify that the repository element is formatted correctly.</li>
<li>Run the <a href="http://oval.mitre.org/repository/download/schema/oval-authoring-style-checker.sch">OVAL Authoring Style Checker</a> (oval-authoring-style-checker.sch) to check if the document follows the Authoring Style Guide.</li>
<li>Correct any errors returned by the preceding tests.</li>
</ol>

<h3><a name="submit" id="submit"></a>How to Submit</h3>
<ul>
<li>Draft an email that includes the following information:
	<ul>
	<li>The IDs of all modified items with a descriptive comment for each modification</li>
	<li>A description of all new content.</li>
	</ul>
</li>
<li>Send the <a href="mailto:oval-discussion-list@lists.mitre.org">email</a> to the OVAL Repository Forum and include the submission as an XML attachment. Note that you must be a <a href="http://oval.mitre.org/community/registration.html">member</a> of the OVAL Repository Forum to post.</li>
<li>Those wishing to submit sensitive information may send it directly to <a href="mailto:oval@mitre.org">oval@mitre.org</a>.</li>
</ul>

<div align="right" style="margin:5px 0px 5px 0px; clear:right"><a href="#top">Back to top</a></div>


<h3><a name="ids" id="ids"></a>Assigning of IDs</h3>
<p>The OVAL Repository uses the org.mitre.oval ID namespace for all of its community contributed content. New IDs are assigned randomly from a pool that is managed by the OVAL Repository. When submitting new content to the OVAL Repository, all new items (definitions, tests, objects, states, and variables) should be assigned temporary IDs in a temporary namespace (e.g., org.your_organization.oval). Once a new submission is reviewed and imported into the OVAL Repository, official IDs in the OVAL Repository namespace (oval.mitre.org) will be assigned by the OVAL Moderator.</p>

<div align="right" style="margin:5px 0px 5px 0px; clear:right"><a href="#top">Back to top</a></div>
	
