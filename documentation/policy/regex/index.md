---
title: Regular Expression Support
layout: flat
---

<h2>Regular Expression Support</h2>

<h3>Overview</h3>
<p>
The OVAL Language supports a common subset of the regular expression character classes, operations, expressions and other lexical tokens defined within Perl 5's regular expression specification. This common subset was identified through a survey of several regular expression libraries in an effort to ensure that the regular expression elements supported by OVAL will be compatible with a wide variety of regular expression libraries. A listing of the surveyed regular expression libraries is provided later in this document.
</p> 

<h3>Supported Regular Expression Syntax</h3>

<p>
Perl regular expression modifiers (m, i, s, x) are not supported. These modifiers should be considered to always be 'OFF' unless specifically permitted by documentation on an OVAL Language construct.
</p>
<p>
Character matching assumes a Unicode character set.  Note that no syntax is supplied for specifying code points in hex; actual Unicode characters must be used instead.
</p>
<p>
The following regular expression elements are specifically identified as supported in the OVAL Language. For more detailed definitions of the regular expression elements listed below, refer to their descriptions in the Perl 5.004 Regular Expression documentation. A copy of the this documentation has been preserved <a href="perlre.html" target="_blank">here</a> for reference purposes. Regular expression elements that are not listed below should be avoided as they are likely to be incompatible or have different meanings with commonly used regular expression libraries.
</p>

<h4>Metacharacters</h4>
<pre>
\   Quote the next metacharacter
^   Match the beginning of the line
.   Match any character (except newline)
$   Match the end of the line (or before newline at the end)
|   Alternation
()  Grouping
[]  Character class
</pre>

<h4>Greedy Quantifiers</h4>

<pre>
*      Match 0 or more times
+      Match 1 or more times
?      Match 1 or 0 times
{n}    Match exactly n times
{n,}   Match at least n times
{n,m}  Match at least n but not more than m times
</pre>

<h4>Reluctant Quantifiers</h4>

<pre>
*?     Match 0 or more times
+?     Match 1 or more times
??     Match 0 or 1 time
{n}?   Match exactly n times
{n,}?  Match at least n times
{n,m}? Match at least n but not more than m times
</pre>

<h4>Escape Sequences</h4>

<pre>
\t          tab                   (HT, TAB)
\n          newline               (LF, NL)
\r          return                (CR)
\f          form feed             (FF)
\033        octal char (think of a PDP-11)
\x1B        hex char
\c[         control char
</pre>

<h4>Character Classes</h4>

<pre>
\w  Match a "word" character (alphanumeric plus "_")
\W  Match a non-word character
\s  Match a whitespace character
\S  Match a non-whitespace character
\d  Match a digit character
\D  Match a non-digit character
</pre>

<h4>Zero Width Assertions</h4>

<pre>
\b  Match a word boundary
\B  Match a non-(word boundary)
</pre>

<h4>Extensions</h4>

<pre>
(?:regexp)     - Group without capture
(?=regexp)     - Zero-width positive lookahead assertion
(?!regexp)     - Zero-width negative lookahead assertion
</pre>


<h4>Version 8 Regular Expressions</h4>

<pre>
[chars]  - Match any of the specified characters
[^chars] - Match anything that is not one of the specified characters
[a-b]    - Match any character in the range between "a" and "b", inclusive
a|b      - Alternation; match either the left side of the "|" or the right side
\n       - When 'n' is a single digit: the nth capturing group matched.
</pre>

<h3>Surveyed Regular Expression Libraries</h3>
<p>The following regular expression libraries were surveyed to identify a common subset of the Perl 5 regular expression specification that is widely supported:
	<ul>
		<li>.NET</li>
		<li>BOOST</li>
		<li>Java</li>
		<li>JavaScript</li>
		<li>PCRE</li>
		<li>Perl 5.004 (as a baseline and reference for the detailed definitions of regular exrpression elements.)</li>
		<li>Python</li>
	</ul>
</p>
