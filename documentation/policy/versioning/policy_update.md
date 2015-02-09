---
title: OVAL Language Versioning Policy Change 
layout: flat
---

<p>Starting with Version 5.11, the OVAL Language will have a new versioning 
policy that will allow the OVAL Community to refine the OVAL Language and quickly get those 
changes into a new release for use within content and tools.</p>

<h2>Summary</h2>

<p>Over the years, the OVAL Language Versioning Policy treated the OVAL Language 
and all of its components as one unit with a single version number. This approach 
to versioning resulted in infrequent large releases that required longer slower 
release cycles and typically greater implementation costs for OVAL Language users. 
Often times the core models of the OVAL Language would remain largely unchanged 
from one release to the next, but due to the need to create and refine language 
extensions the core models had the appearance of changing due to the assignment 
of new version numbers to those models. This appearance of change to the core of 
the language created a perception of instability in the core models and acted as 
an impediment to the development of needed language extensions. Ultimately, this 
approach resulted in long release timelines with significant delays to add support 
for new and evolving platforms.</p>

<p>A new versioning policy was developed to address these issues and enable the 
OVAL Community to more rapidly adopt new capabilities. Under this new approach 
to versioning the core models of the OVAL Language (OVAL Common, OVAL Definitions, 
OVAL System Characteristics, OVAL Results, OVAL Directives, and OVAL Variables) 
and individual platform extension models (Android, Cisco, Linux, UNIX, Windows, etc.) 
would be versioned independently. The core models should remain relatively stable 
while the more dynamic platform extensions are free to evolve as needed.</p>

<p>It is expected that for higher level usages of OVAL (for example SCAP) a rolled up
version of the various Core and Platform Extensions would be created to create a 
snapshot of OVAL for purposes of things like validation.</p>

<p>This new versioning policy went into effect on November 30, 2014 
with the official release of Version 5.11 of the OVAL Language and with the 
approval of the OVAL Board.</p>

<h2>Official OVAL Language Versioning Policy</h2>

<p>Starting with the 5.11 release, the OVAL Language now uses the policy described
<a href="./">here</a></p>

<h2>Archived OVAL Language Versioning Policy</h2>

<p>The OVAL Language Versioning Policy used prior to OVAL 5.11 was archived 
on November 30, 2014, but, is available <a href="oldpolicy">here</a> for 
informational purposes.</p>
