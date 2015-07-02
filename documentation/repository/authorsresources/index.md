---
title: Author’s Resources
layout: flat
no_in_page_title: true
---
<a name="top"></a>
<h1>{{ page.title }}</h1>

<p>This page gathers documents and tools for authoring content in the <a href="https://github.com/OVALProject/Language">OVAL Language</a> into a single location. As with any software language, your ability to successfully author OVAL content will continue to grow the more you work with the language. We encourage you to familiarize yourself with the information here as part of that process, and to offer feedback and ask any questions you might have on the <a href="http://oval.mitre.org/community/registration.html">OVAL Community Forums</a> as you continue the ongoing process of developing your knowledge of OVAL.</p>

<h3 style="margin-top:1.5em"><a name="prerequisites" id="prerequisites"></a>Prerequisites</h3>
<ul>
<li>A working knowledge of XML is highly recommended before attempting to author content in the OVAL Language.</li>
<li>A strong knowledge of the technical nuances of the operating system or application for which you intend to write OVAL Definitions.</li>
<li>A basic understanding of the most recent version of the OVAL Language.</li>
</ul>

<h3 style="margin-top:1.5em"><a name="docs" id="docs"></a>Instructional Documents</h3>

<p><a href="/getting-started/tutorial" style="font-weight:bold">Definition Tutorial</a> — A primer on how OVAL Definitions are structured in the OVAL Language.</p>

<p><a href="/documentation/validation" style="font-weight:bold">Validating a Document</a> — Explains how to validate an OVAL document to ensure a common and expected structure amongst OVAL documents being passed between different users.</p>

<p><a href="/documentation/repository/styleguide" style="font-weight:bold">OVAL Repository Style Guide</a> — A living document detailing the stylistic decisions that have been made for OVAL Language content including definitions, tests, objects, states, and variables.</p>

<h3 style="margin-top:1.5em"><a name="tools" id="tools"></a>Useful Tools</h3>

<p><a href="http://sourceforge.net/projects/ovalutils/files/oval_checker/" target="_blank" style="font-weight:bold">OVAL Checker</a> — This free Schematron-based utility will flag common mistakes and poor stylistic decisions in OVAL Definition documents. The list of issues that the utility detects and reports is ever-evolving as the community identifies OVAL authoring best practices. The current listing of authoring style guidelines is based on the <a href="http://oval.mitre.org/repository/about/style.html">OVAL Repository Style Guide</a>.</p>

<p><a href="http://sourceforge.net/projects/ovalutils/files/oval_merge/oval_merge_v5.10.1/" target="_blank" style="font-weight:bold">OVAL Merge</a> — This free utility takes one or more files that contain valid OVAL content and combines them into a single, valid OVAL file that contains the union of all of the definitions, tests, objects, states, and variables found in the individual OVAL files.</p>

<p><a href="http://sourceforge.net/projects/ovalutils/files/oval_splitter/" target="_blank" style="font-weight:bold">OVAL Splitter</a> — This free utility takes an XML file that contains one or more definitions as a command line input and splits the input document in one of two ways: (1) the user indicates on the command line the OVAL-ID of a definition, test, object, state, or variable and each of the items is split into its own new valid document; or (2) the user indicates on the command line that the input document should be fully split at a specified level (definitions, test, object, state, variable) and the utility creates a new XML file for each item at the designated level (for example, if the input document has five definitions and the user indicates that the document should be split at the definition level the utility will create a new XML file for each definition in the input document).</p>

<p><a href="http://sourceforge.net/projects/ovalutils/files/oval_normalizer/" target="_blank" style="font-weight:bold">OVAL Normalizer</a> — This is a free command-line utility that takes an XML file containing one or more OVAL Definitions as input and validates the document(s) against the OVAL Definitions Schema and the OVAL Definitions Schema Schematron rules. If the input document is valid, the utility will normalize the input XML file and output to a user-specified XML file. During the normalization process, unused XML namespaces will be removed and an attempt is made to clean-up comments on all items, simplify the usage of XML namespaces, and remove optional attributes. This normalization process is intended to make the input definition more easily readable and give users some consistency in the format of the OVAL Definitions with which they are working.</p>

<p><a href="http://sourceforge.net/projects/ovalutils/files/xccdf_splitter/" target="_blank" style="font-weight:bold">XCCDF Splitter</a> — This free utility allows you to input a complete SCAP Benchmark, such as the FDCC for Windows XP, and create a new benchmark that contains only one user-elected Rule and all related material. This enables a user to easily create a new benchmark to check for a single rule in an existing SCAP Benchmark for evaluation with an SCAP Validated Compliance Scanner. The utility takes as input the XCCDF document portion of an SCAP Benchmark and the ID of the user’s desired rule and outputs to a new directory a pared-down XCCDF document that contains only the user’s selected rule and the minimal required set of OVAL Definitions.</p>

<p><a href="http://sourceforge.net/projects/ovalutils/files/xsl_transforms/" target="_blank" style="font-weight:bold">XSL Transforms</a> — A free set of independent transformations that will perform specific functions upon an OVAL or XCCDF file. These include commonly performed operations for handling subsets of data, or to change the way the user interacts with the content. All may be called in a similar fashion with varying input parameters.</p>

<p><a href="https://github.com/OVALProject/Test-Content" style="font-weight:bold">OVAL Test Content</a> — A set of OVAL Definitions that provides a simple way to test the capability of OVAL Definition Evaluators. After running the OVAL Test Content through an OVAL Definition Evaluator, the OVAL Results will show which tests are properly supported by that tool. This allows unit testing of tools against the language. Content authors may use the content as a reference for writing new content.</p>

<p><a href="http://sourceforge.net/projects/ovaldi/" target="_blank" style="font-weight:bold">OVAL Interpreter</a> — This free reference implementation can be used by definition writers to test content and ensure correct syntax and adherence to the OVAL Schemas.</p>

<p><a href="http://oval.mitre.org/adoption/capabilitylist.html#at" style="font-weight:bold">Additional OVAL Authoring Tools</a> — Tools for Authoring OVAL Content available from participants in the OVAL Adoption Program.</p>

<h3 style="margin-top:1.5em"><a name="assistance" id="assistance"></a>Further Assistance</h3>

<p><a href="http://oval.mitre.org/community/registration.html" style="font-weight:bold">OVAL Developer’s Forum</a> — Contact for questions about the OVAL Language itself.</p>
<p><a href="http://oval.mitre.org/community/registration.html" style="font-weight:bold">OVAL Repository Forum</a> — Contact for questions about creating OVAL content.</p>
<p><a href="mailto:oval@mitre.org" style="font-weight:bold">OVAL Team</a> — Contact directly for questions about the OVAL Language and/or about creating OVAL content.</p>

<div align="right" style="margin:5px 0px 5px 0px; clear:right"><a href="http://oval.mitre.org/repository/about/authorsresources.html#top">Back to top</a></div>
