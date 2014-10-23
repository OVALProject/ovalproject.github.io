---
title: Archived OVAL Versioning Policy
layout: flat
---

<p>This document details the current methodology for determining whether a new 
revision will require a major version change, minor version change, or a version 
update, and how version information is represented and conveyed in the OVAL Language.</p>

<p>A three-component version identifier is used to track the evolution of the 
OVAL Language over time. Each component of the version identifier is a numeric 
value and corresponds to one of the three release types 
&mdash; &quot;Major&quot;, &quot;Minor&quot;, and &quot;Update&quot; &mdash; 
each of which is subject to the OVAL Language Revision Policy. The complete 
version identifier has the following form: MAJOR.MINOR.UPDATE. 
For example, &quot;5.10.1&quot;.</p>

<p>These three different types of OVAL releases and their relationship with 
the OVAL Language&#8217;s version identifier are described below:</p>

<h4><a name="major" id="major"></a>Major Release</h4>
<p>A major release is for adding features that require breaking backward compatibility 
with previous versions of the OVAL Language or represent fundamental changes to
 concepts in the OVAL Language. For a major release, the MAJOR component must be 
incremented by one and the MINOR and UPDATE components must be set to zero.</p>

<h5 class="subhead">Example</h5>
<p>In OVAL 4.2, OVAL Objects and OVAL States were directly embedded in OVAL Tests. 
The community decided that OVAL Test should not directly contain OVAL Objects and 
OVAL States but rather reference them. This change would break backward 
compatibility with previous versions of the OVAL Language. As a result, OVAL 5.0 
was created.</p>

<h4><a name="minor" id="minor"></a>Minor Release</h4>
<p>A minor release is for adding features to the OVAL Language that do not break
backward compatibility with previous versions of the OVAL Language. For a minor 
release, the MINOR component must be incremented by one and the UPDATE component 
must be set to zero.</p>

<h5 class="subhead">Example</h5>
<p>In the OVAL 5.10 development process, the win-def:cmdlet_test was proposed 
to the community and accepted. Since the new OVAL Test did not break backward 
compatibility with previous versions of the OVAL Language, it was added in OVAL 5.10.</p>

<h5 class="subhead">Exception</h5>
<p>Critical defects that will result in invalid content, nonsensical content, 
interoperability issues, or other similar critical issues may be addressed in
a minor release. Fixes may break backward compatibility if necessary. In order 
for such a change to be made, the following criteria must be met:</p>
<ul>
<li>The OVAL Board must have agreed through consensus and consultation with the 
OVAL Community that the impact of such a change will be low.</li>
<li>The OVAL Board must have agreed through consensus and consultation with the
OVAL Community that the benefit of breaking backward compatibility outweighs 
any negative impact.</li>
</ul>

<h5 class="subhead">Example</h5>
<p>During the OVAL 5.6 development process, it was discovered that there can 
only be one value for the max_uses entity in the win-sc:sharedresource_item. 
However, the maxOccurs attribute for the entity was set to unbounded allowing 
for nonsensical content. As a result, in OVAL 5.8, the maxOccurs attribute was 
set to one.</p>

<h4><a name="update" id="update"></a>Update Release</h4>
<p>An update release may only be initiated to address critical defects in a 
version of the OVAL Language that affects its usability. Fixes may break 
backward compatibility if necessary. New functionality outside of what was 
intended is not permitted. However, once an update release is agreed to, other 
non-critical fixes and clarifications may be addressed. When an update version 
change is made, the UPDATE component must be incremented by one. An update 
version change may be done at any time as long as the following conditions are met:</p>
<ul>
<li>The OVAL Board must have agreed through consensus and consultation with 
the OVAL Community that the impact of such a change will be low.</li>
<li>The OVAL Board must have agreed through consensus and consultation with 
the OVAL Community that any such changes are necessary and applying the changes 
outweighs any negative impact of issuing an update.</li>
</ul>

<h5 class="subhead">Example</h5>
<p>In OVAL 5.10, it was discovered that the extended_name entity was missing 
from the linux-def:rpmverifypackage_state even though its proposal intended for 
the entity to be included. It was determined that this defect prevented the 
ability to check a system for unauthorized setuid programs which was the primary 
reason for adding the entity. As a result, OVAL 5.10.1 was released to fix this defect.</p>
 
<h4><a name="deprecation" id="deprecation"></a>Deprecation</h4>
<p>OVAL Language constructs may be deprecated in either major or minor revisions. 
The complete deprecation policy is detailed in the OVAL Language Deprecation Policy.</p>
