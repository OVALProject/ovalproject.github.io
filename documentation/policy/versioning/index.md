---
title: Versioning Policy
layout: flat
---

<div class="alert alert-info">
  <p><strong>Updated Versioning Policy:</strong> As of the 5.11 release of OVAL, 
a new versioning policy is in use (described below).  Additional background information 
about this change is available <a href="policy_update">here</a>.</p>
</div>

<p>This document details the methodology by which the different parts of the 
OVAL Language are versioned.  This includes the methods for determining whether 
a new revision will require a major version change, minor version change, or a 
version update, and how version information is represented and conveyed in the 
OVAL Language.  It also explains how each of the different parts of the Language(
the Core and Platform Extension models) are versioned.</p>

<h2>Core Model Versioning</h2>

<p>The Core Model's version are formatted to include a major, minor, and update version
number and look like:</p>

<p><div class="well well">MAJOR.MINOR.UPDATE</div></p>

<p>Note that the trailing UPDATE version number can be omitted when it is "0".  
Examples of this version look like:</p>

<p><div class="well well">
	<ul>
		<li>5.4</li>
		<li>5.10.1</li>
		<li>5.11</li>
	</ul>
</div></p>

<h2>Platform Extension Model Versioning</h2>

<p>Platform Extensions are independently versioned using a concatenation of the 
core language version that the extension is based upon followed by the version 
of the of the platform extension. Both the core language version and the platform 
extension version strings use the same basic structure including major, minor, 
and update components.  The full concatenated version for a platform extension will 
look like:</p>

<p><div class="well">
CORE-MAJOR.CORE-MINOR.CORE-UPDATE:PLAT-MAJOR.PLAT-MINOR.PLAT-UPDATE
</div></p>

<p>Where the first 3 version numbers correspond to the Core version from 
which the Platform Extension is built and the 3 version numbers following the 
colon (:) represent the Platform Extension’s version.  For example, the version 
5.11.0:1.0 would represent the initial version of an extension built off of the 
5.11 version of the OVAL Core.  The initial version of all Platform Extensions 
will use the '1.0' notation to the right of the colon to indicate the first version of the
extension.  Note that the trailing UPDATE version 
number can be omitted when it is "0".  Examples of this look like:</p>

<p><div class="well well">
	<ul>
		<li>5.11.0:1.0 – the initial release of the platform extension that supports 5.11 of the core model</li>
		<li>5.11.0:2.0 – a major update to the platform extension that supports the 5.11 core model</li>
		<li>5.11.0:2.1 – a minor revision to the platform extension that supports the 5.11 core</li>
		<li>5.11.0:2.1.1 - an update revision to the platform extension that supports the 5.11 core</li>
		<li>5.12.1:1.0 - the initial release of the platform extension that supporte the 5.12.1 core</li>
	</ul>
</div></p>

Also, note that the corresponding OVAL Definitions Model and OVAL System Characteristics Model, for a Platform Extension, must be versioned together.

<h2>Versioning Scheme</h2>

<p>Both the Core and the Platform Extensions are constructed using component identifiers.  
The Core uses a single three component identifier (e.g. 5.11.1) while the Platform Extensions use two, colon-separated 
three component identifiers (e.g. 5.11.0:1.3.2). The following describes how each of those 
three component identifiers are constructed.</p>

<p>Each component of the identifier is a numeric value and corresponds 
to one of the three release types — "Major", "Minor", and "Update" — each of 
which is subject to the <a href="../revisionprocess">OVAL Language Revision Policy</a>. 
The complete identifier uses the MAJOR.MINOR.UPDATE as stated above. 
For example, "5.10.1".</p>

<p>These three different types of OVAL releases and their relationship with 
the OVAL Language’s three component identifier are described below:</p>

<h3>Major Release</h3>

<p>A major release is for adding features that require breaking
<a href="../backwardscompat">backward compatibility</a> with previous versions or 
represent fundamental changes to concepts. For a major release, 
the MAJOR component must be incremented by one and the MINOR and UPDATE components 
must be set to zero.</p>

<h4>Example</h4>

<p>In OVAL 4.2, OVAL Objects and OVAL States were directly embedded in OVAL Tests. 
The community decided that an OVAL Test should not directly contain OVAL Objects 
and OVAL States but rather reference them. This change would break backward 
compatibility with previous versions of the OVAL Language. As a result, OVAL 5.0 
was created.</p>

<h3>Minor Release</h3>

<p>A minor release is for adding features that do not break backward compatibility 
with previous versions. For a minor release, the MINOR component must be incremented 
by one and the UPDATE component must be set to zero.</p>

<h4>Example</h4>

<p>In the OVAL 5.10 development cycle, a new function to count the number of values 
represented by one or more components was proposed.  Since the addition of this
function did not break backwards compatiblity, it was added as part of the 5.10
version of OVAL.</p>

<h3>Exception</h3>

<p>Critical defects that will result in invalid content, nonsensical content, 
interoperability issues, or other similar critical issues may be addressed in 
a minor release. Fixes may break backward compatibility if necessary. In order 
for such a change to be made, the following criteria must be met:
    <ul>
        <li>The OVAL Board must have agreed through consensus and consultation 
with the OVAL Community that the impact of such a change will be low.</li>
        <li>The OVAL Board must have agreed through consensus and consultation 
with the OVAL Community that the benefit of breaking backward compatibility 
outweighs any negative impact.</li>
    </ul></p>

<h3>Update Release</h3>

<p>An update release may only be initiated to address critical defects in a 
version that affects its usability. Fixes may break backward 
compatibility if necessary. New functionality outside of what was intended is 
not permitted. However, once an update release is agreed to, other non-critical 
fixes and clarifications may be addressed. When an update version change is made, 
the UPDATE component must be incremented by one. An update version change may be 
done at any time as long as the following conditions are met:
    <ul>
        <li>The OVAL Board must have agreed through consensus and consultation 
with the OVAL Community that the impact of such a change will be low.</li>
        <li>The OVAL Board must have agreed through consensus and consultation with 
the OVAL Community that any such changes are necessary and applying the changes 
outweighs any negative impact of issuing an update.</li>
    </ul></p>

<h4>Example</h4>

<p>In OVAL 5.10, it was discovered that the extended_name entity was missing from 
the linux-def:rpmverifypackage_state even though its proposal intended for the 
entity to be included. It was determined that this defect prevented the ability 
to check a system for unauthorized setuid programs which was the primary reason
for adding the entity. As a result, OVAL 5.10.1 was released to fix this defect.</p>

<h3>Deprecation</h3>

<p>OVAL Language constructs may be deprecated in either major or minor revisions. 
The complete deprecation policy is detailed in the 
<a href="../deprecation">OVAL Language Deprecation Policy</a>.</p>
