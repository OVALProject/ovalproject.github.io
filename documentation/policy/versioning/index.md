---
title: Versioning Policy
layout: flat
---

<div class="alert alert-tip">
  <p><strong>Updated Versioning Policy:</strong> As of the 5.11 release of OVAL, a new versioning policy is in use (described below).  For additional background and context
regarding the new policy, please <a href="policy_update">click here</a>.</p>
</div>

<p>This document details the methodology by which the different parts of the 
OVAL Language are versioned.  This includes the methods for determining whether 
a new revision will require a major version change, minor version change, or a 
version update, and how version information is represented and conveyed in the 
OVAL Language.  It also explains how each of the different parts of the Language, 
the core XML Schemas as well as the platform extensions, are versioned.</p>

<p>In versions of the Language previous to 5.11, all of the parts of the Language, 
including both the core schema as well as the platform extensions, were versioned 
in one collection, receiving a single version number (such as 5.8, 5.10.1, etc.).  
As of version 5.11, each of these parts are now versioned independently.  This 
allows the core schemas to stay unchanged, while the more dynamic platform extensions 
continue to evolve as needed.</p>

<h2>Separate Versions Policy (> OVAL 5.11_)</h2>

<p>The core schema, which contains the basic building block for the OVAL Language, 
including oval-common, oval-definitions, oval-system-characteristics, and other related 
schema, are versioned separate from each of the platform extensions starting 
with the 5.11 release of OVAL.  The platform extensions are then versioned 
separately from the core.  Since the core schema is quite stable, the revision 
cycle for the core is very infrequent, while it is expected that the platform 
schemas will be revised regularly.</p>

<p>The version numbers OVAL versions that use this policy will follow the following pattern:</p>

<p><strong>
CORE-MAJOR.CORE-MINOR.CORE-UPDATE:PLAT-MAJOR.PLAT-MINOR.PLAT-UPDATE
</strong></p>

<p>Where the first 3 version numbers correspond to the core schema version from 
which the platform extension is built and the 3 version numbers following the 
colon (:) represent the platform extension’s version.  For example, the version 
5.11.0:5.11 would represent the initial version of a platform built off of the 
5.11 version of the core OVAL schemas.  Note that the trailing UPDATE version 
number can be omitted when not necessary.</p>

<p>It is expected that for higher level usages of OVAL (for example SCAP) a “rolled up” 
version of the various core and platform schemas would be created to create a 
snapshot of OVAL for purposes of things like validation.</p>

<h2>Versioning Scheme</h2>
A three-component version identifier is used to track the evolution of the OVAL 
Language over time. The description below applies to both the core and platform 
schemas final 3 numbers.</p>

<p>Each component of the version identifier is a numeric value and corresponds 
to one of the three release types — "Major", "Minor", and "Update" — each of 
which is subject to the <a href="documentation/policy/revisionprocess">OVAL Language Revision Policy</a>. 
The complete version identifier has the following form: MAJOR.MINOR.UPDATE. 
For example, "5.10.1".</p>

<p>These three different types of OVAL releases and their relationship with 
the OVAL Language’s version identifier are described below:</p>

<h3>Major Release</h3>

<p>A major release is for adding features that require breaking
<a href="documentation/policy/backwardscompat">backward 
compatibility</a> with previous versions of the OVAL Language or represent 
fundamental changes to concepts in the OVAL Language. For a major release, 
the MAJOR component must be incremented by one and the MINOR and UPDATE components 
must be set to zero.</p>

<h4>Example</h4>

<p>In OVAL 4.2, OVAL Objects and OVAL States were directly embedded in OVAL Tests. 
The community decided that OVAL Test should not directly contain OVAL Objects 
and OVAL States but rather reference them. This change would break backward 
compatibility with previous versions of the OVAL Language. As a result, OVAL 5.0 was created.</p>

<h3>Minor Release</h3>

<p>A minor release is for adding features to the OVAL Language that do not break 
backward compatibility with previous versions of the OVAL Language. For a minor 
release, the MINOR component must be incremented by one and the UPDATE component 
must be set to zero.</p>

<h4>Example</h4>

<p>In the OVAL 5.10 development process, the win-def:cmdlet_test was proposed to 
the community and accepted. Since the new OVAL Test did not break backward 
compatibility with previous versions of the OVAL Language, it was added in 
OVAL 5.10.</p>

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
version of the OVAL Language that affects its usability. Fixes may break backward 
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
<a href="documentation/policy/deprecation">OVAL Language Deprecation Policy</a>.</p>
