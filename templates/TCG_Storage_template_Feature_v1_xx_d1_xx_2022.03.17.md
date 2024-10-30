![](media/image1.png){width="8.49720363079615in"
height="10.478021653543307in"}![](media/image2.png){width="2.1724048556430446in"
height="0.9993055555555556in"}**\
**

Version_1.xx\
Revision_D1.xx\
March 17, 2022

Contact: <admin@trustedcomputinggroup.org>

DRAFT

**TCG Storage Feature Set: \<template\>**

**SPECIFICATION**

# DISCLAIMERS, NOTICES, AND LICENSE TERMS {#disclaimers-notices-and-license-terms .TCG-Heading-1-with-No-Number}

THIS SPECIFICATION IS PROVIDED "AS IS" WITH NO WARRANTIES WHATSOEVER,
INCLUDING ANY WARRANTY OF MERCHANTABILITY, NONINFRINGEMENT, FITNESS FOR
ANY PARTICULAR PURPOSE, OR ANY WARRANTY OTHERWISE ARISING OUT OF ANY
PROPOSAL, SPECIFICATION OR SAMPLE.

Without limitation, TCG disclaims all liability, including liability for
infringement of any proprietary rights, relating to use of information
in this specification and to the implementation of this specification,
and TCG disclaims all liability for cost of procurement of substitute
goods or services, lost profits, loss of use, loss of data or any
incidental, consequential, direct, indirect, or special damages, whether
under contract, tort, warranty or otherwise, arising in any way out of
use or reliance upon this specification or any information herein.

This document is copyrighted by Trusted Computing Group (TCG), and no
license, express or implied, is granted herein other than as follows:
You may not copy or reproduce the document or distribute it to others
without written permission from TCG, except that you may freely do so
for the purposes of (a) examining or implementing TCG specifications or
(b) developing, testing, or promoting information technology standards
and best practices, so long as you distribute the document with these
disclaimers, notices, and license terms.

Contact the Trusted Computing Group at www.trustedcomputinggroup.org for
information on specification licensing through membership agreements.

Any marks and brands contained herein are the property of their
respective owners.

# CHANGE HISTORY  {#change-history .unnumbered}

+-------------+------------+-------------------------------------------+
| *           | **DATE**   | **DESCRIPTION**                           |
| *REVISION** |            |                                           |
+=============+============+===========================================+
| V1.xx/D1.xx | YYYY.MM.DD | -                                         |
+-------------+------------+-------------------------------------------+
|             |            | -                                         |
+-------------+------------+-------------------------------------------+
|             |            | -                                         |
+-------------+------------+-------------------------------------------+
|             |            | -                                         |
+-------------+------------+-------------------------------------------+
|             |            | -                                         |
+-------------+------------+-------------------------------------------+

: Table 1 - SP Table Legend

# CONTENTS {#contents .TCG-Heading-1-with-No-Number}

[CHANGE HISTORY [2](#change-history)](#change-history)

[1 Introduction [6](#introduction)](#introduction)

[1.1 Document Purpose [6](#document-purpose)](#document-purpose)

[1.2 Scope and Intended Audience
[6](#scope-and-intended-audience)](#scope-and-intended-audience)

[1.3 Conventions [6](#conventions)](#conventions)

[1.3.1 Key Words [6](#key-words)](#key-words)

[1.3.2 Font Conventions [6](#font-conventions)](#font-conventions)

[1.3.3 Statement Type [6](#statement-type)](#statement-type)

[1.3.4 SP Table Cell Color Legend
[7](#sp-table-cell-color-legend)](#sp-table-cell-color-legend)

[1.3.5 List Conventions [8](#list-conventions)](#list-conventions)

[1.3.5.1 Lists overview [8](#lists-overview)](#lists-overview)

[1.3.5.2 Unordered lists [8](#unordered-lists)](#unordered-lists)

[1.3.5.3 Ordered lists [8](#ordered-lists)](#ordered-lists)

[1.3.6 Numbering [9](#numbering)](#numbering)

[1.3.7 Bit conventions [9](#bit-conventions)](#bit-conventions)

[1.3.8 Number range convention
[9](#number-range-convention)](#number-range-convention)

[1.4 Document References
[9](#document-references)](#document-references)

[1.4.1 Document Precedence
[9](#document-precedence)](#document-precedence)

[1.4.2 Approved References
[10](#approved-references)](#approved-references)

[1.4.3 References Under Development
[10](#references-under-development)](#references-under-development)

[1.5 Dependencies on Other Feature Sets
[10](#dependencies-on-other-feature-sets)](#dependencies-on-other-feature-sets)

[1.6 Interactions with Other Feature Sets
[10](#interactions-with-other-feature-sets)](#interactions-with-other-feature-sets)

[1.7 Definitions of Terms
[10](#definitions-of-terms)](#definitions-of-terms)

[2 xxx Overview [12](#xxx-overview)](#xxx-overview)

[3 SSC Specific Functionality
[13](#ssc-specific-functionality)](#ssc-specific-functionality)

[3.1 Methods [13](#methods)](#methods)

[3.1.1 New Methods [13](#new-methods)](#new-methods)

[3.1.1.1 xxx (M) [13](#xxx-m)](#xxx-m)

[3.1.1.1.1 Parameter Descriptions
[13](#parameter-descriptions)](#parameter-descriptions)

[3.1.1.1.2 Returned Value Descriptions
[14](#returned-value-descriptions)](#returned-value-descriptions)

[3.1.1.1.3 xxx Method Operation
[14](#xxx-method-operation)](#xxx-method-operation)

[3.1.2 Modified Methods [15](#modified-methods)](#modified-methods)

[3.1.2.1 Xxx [15](#xxx)](#xxx)

[3.2 Tables [16](#tables)](#tables)

[3.2.1 New Tables [16](#new-tables)](#new-tables)

[3.2.2 Modified Tables [16](#modified-tables)](#modified-tables)

[3.2.2.1 XXX [16](#xxx-1)](#xxx-1)

[3.2.2.1.1 Xxx (M) [16](#xxx-m-1)](#xxx-m-1)

[3.2.2.2 Access Control (M) [16](#access-control-m)](#access-control-m)

[3.2.2.3 ACE (M) [18](#ace-m)](#ace-m)

[3.3 Types [19](#types)](#types)

[3.3.1 New Types [19](#new-types)](#new-types)

[3.3.2 Modified Types [19](#modified-types)](#modified-types)

[4 Feature Set Requirements
[20](#feature-set-requirements)](#feature-set-requirements)

[4.1 Requirements Overview
[20](#requirements-overview)](#requirements-overview)

[4.2 Level 0 Discovery [20](#level-0-discovery)](#level-0-discovery)

[4.2.1 xxx Descriptor (Feature Code = 0x000) (M)
[20](#xxx-descriptor-feature-code-0x000-m)](#xxx-descriptor-feature-code-0x000-m)

[4.2.1.1 Feature Code [20](#feature-code)](#feature-code)

[4.2.1.2 Feature Descriptor Version Number
[20](#feature-descriptor-version-number)](#feature-descriptor-version-number)

[4.2.1.3 Feature Set Minor Version Number
[20](#feature-set-minor-version-number)](#feature-set-minor-version-number)

[4.2.1.4 Length [21](#length)](#length)

[4.2.1.5 Range_C [21](#range_c)](#range_c)

[4.3 Admin SP [22](#admin-sp)](#admin-sp)

[4.4 Locking SP [22](#locking-sp)](#locking-sp)

[4.4.1 Tables [22](#tables-1)](#tables-1)

[4.4.1.1 Locking table (M) [22](#locking-table-m)](#locking-table-m)

[4.4.1.1.1 Global Range (M) [22](#global-range-m)](#global-range-m)

[4.4.1.1.2 Preconfiguration [22](#preconfiguration)](#preconfiguration)

[4.5 Additional SPs [25](#additional-sps)](#additional-sps)

[4.6 Otherxxx Feature Set Interactions
[25](#otherxxx-feature-set-interactions)](#otherxxx-feature-set-interactions)

[4.6.1 Overview [25](#overview)](#overview)

[4.6.2 Modified Methods [25](#modified-methods-1)](#modified-methods-1)

[4.6.2.1 Xxx [25](#xxx-2)](#xxx-2)

# List of Tables {#list-of-tables .TOC-Heading .unnumbered}

[Table 1 - SP Table Legend [5](#_Toc98327192)](#_Toc98327192)

[Table 2 - Sample Table [10](#_Toc98327193)](#_Toc98327193)

# List of Figures {#list-of-figures .TOC-Heading .unnumbered}

[Figure 1 - Sample Figure [11](#_Toc98328839)](#_Toc98328839)

# Introduction

## Document Purpose

The Storage Workgroup specifications provide a comprehensive
architecture for SDs under policy control as determined by the trusted
platform host, the capabilities of the SD to conform to the policies of
the trusted platform, and the lifecycle state of the SD as a Trusted
Peripheral.

## Scope and Intended Audience

This specification defines the \<template\> Feature Set. Any SD that
claims compliance to the \<template\> Feature Set SHALL conform to this
specification.

The intended audience for this specification is both trusted SD
manufacturers and developers that want to use these SDs in their
systems.

## Conventions

### Key Words 

Key words are used to signify requirements.

The Key Words "SHALL", "SHALL NOT", "SHOULD," and "MAY" are used in this
document. These words are a subset of the RFC 2119 (see \[1\]) key words
used by TCG. These key words are to be interpreted as described in
\[1\].

In addition to the above key words, the following are also used in this
document to describe the requirements of particular features, including
tables, methods, and usages thereof.

-   Mandatory (M): When a feature is Mandatory, the feature SHALL be
    implemented. A Compliance test SHALL validate that the feature is
    operational.

-   Optional (O): When a feature is Optional, the feature MAY be
    implemented. If implemented, a Compliance test SHALL validate that
    the feature is operational.

-   Excluded (X): When a feature is Excluded, the feature SHALL NOT be
    implemented. A Compliance test SHALL validate that the feature is
    not operational.

-   Not Required (N) When a feature is Not Required, the feature MAY be
    implemented. No Compliance test is required.

### Font Conventions

Names of methods and SP tables are in Courier New font (e.g., the Set
method, the Locking table). This convention does not apply to method and
table names appearing in headings or captions.

Hexadecimal numbers are in Courier New font.

All other text is in the Ariel font.

### Statement Type

There are two distinctive kinds of text: informative comment and
normative statements.

By default, all statements are normative statements.

Informative statements are specifically marked by flagging the beginning
and end of each informative comment and highlighting its text in gray.

**EXAMPLE:**

*Start of Informative Comment*

This is the first paragraph of 1-n paragraphs containing text of the
kind informative comment \...

This is the second paragraph of text of the kind informative comment
\...

This is the nth paragraph of text of the kind informative comment \...

To understand the TCG specification the user must read the
specification. (This use of MUST does not require any action).

*End of Informative Comment*

### SP Table Cell Color Legend

The legend in Table 1 defines the SP table cell color coding, with the
RGB values for the shading of each cell indicated in parentheses. This
color coding is informative only. The table cell content is normative.

+---------+--------+-------------+-----------+------------------------+
| **Table | *      | **Value**   | **Access  | **Comment**            |
| Cell    | *R-W** |             | Control** |                        |
| L       |        |             |           |                        |
| egend** |        |             |           |                        |
+=========+========+=============+===========+========================+
| Arial   | Rea    | \           | Fixed     | -   Cell content is    |
| -Narrow | d-only | <template\> |           |     Read-Only.         |
|         |        | Feature Set |           |                        |
| (230,   |        | specified   |           | -   Access control is  |
| 230,    |        |             |           |     fixed.             |
| 230)    |        |             |           |                        |
|         |        |             |           | -   Value is specified |
|         |        |             |           |     by the             |
|         |        |             |           |     \<template\>       |
|         |        |             |           |     Feature Set        |
+---------+--------+-------------+-----------+------------------------+
| *       | Rea    | VU          | Fixed     | -   Cell content is    |
| *[Arial | d-only |             |           |     Read-Only.         |
| Narrow  |        |             |           |                        |
| bold    |        |             |           | -   Access Control is  |
| -under] |        |             |           |     fixed.             |
| {.under |        |             |           |                        |
| line}** |        |             |           | -   Values are Vendor  |
|         |        |             |           |     Unique (VU). A     |
| (230,   |        |             |           |     minimum or maximum |
| 230,    |        |             |           |     value may be       |
| 230)    |        |             |           |     specified.         |
+---------+--------+-------------+-----------+------------------------+
| Arial   | Not    | \(N\)       | Not       | -   Cell content is    |
| -Narrow | D      |             | Defined   |     (N).               |
|         | efined |             |           |                        |
| (0, 0,  |        |             |           | -   Access control is  |
| 0)      |        |             |           |     not defined.       |
|         |        |             |           |                        |
|         |        |             |           | -   Any text in table  |
|         |        |             |           |     cell is            |
|         |        |             |           |     informative only.  |
|         |        |             |           |                        |
|         |        |             |           | -   A Get MAY omit     |
|         |        |             |           |     this column from   |
|         |        |             |           |     the method         |
|         |        |             |           |     response.          |
+---------+--------+-------------+-----------+------------------------+
| *       | Write  | Prec        | Precon    | -   Cell content is    |
| *[Arial |        | onfigured,\ | figured,\ |     writable.          |
| Narrow  |        | user        | user      |                        |
| bold    |        | per         | perso     | -   Access control is  |
| -under] |        | sonalizable | nalizable |     personalizable     |
| {.under |        |             |           |                        |
| line}** |        |             |           | -   Get Access Control |
|         |        |             |           |     is not described   |
| (179,   |        |             |           |     by this color      |
| 179,    |        |             |           |     coding             |
| 179)    |        |             |           |                        |
+---------+--------+-------------+-----------+------------------------+
| Arial   | Write  | Prec        | Fixed     | -   Cell content is    |
| -Narrow |        | onfigured,\ |           |     writable.          |
|         |        | user        |           |                        |
| (179,   |        | per         |           | -   Access control is  |
| 179,    |        | sonalizable |           |     fixed.             |
| 179)    |        |             |           |                        |
|         |        |             |           | -   Get Access Control |
|         |        |             |           |     is not described   |
|         |        |             |           |     by this color      |
|         |        |             |           |     coding             |
+---------+--------+-------------+-----------+------------------------+

: Table 2 - Xxx -- Xxx Table Columns

### List Conventions

#### Lists overview

Lists are associated with an introductory paragraph or phrase, and are
numbered relative to that paragraph or

phrase (i.e., all lists begin with an a) or 1) entry).

Each item in a list is preceded by an identification with the style of
the identification being determined by whether

the list is intended to be an ordered list or an unordered list.

If the item in a list is not a complete sentence, the first word in the
item is not capitalized. If the item in a list is a

complete sentence, the first word in the item is capitalized.

Each item in a list ends with a semicolon, except the last item, which
ends in a period. The next to the last entry

in the list ends with a semicolon followed by an "and" or an "or" (i.e.,
"...; and", or "...; or"). The "and" is used if all

the items in the list are required. The "or" is used if only one or more
items in the list are required.

#### Unordered lists

An unordered list is one in which the order of the listed items is
unimportant (i.e., it does not matter where in the

list an item occurs as all items have equal importance). Each list item
shall start with a lower case letter followed

by a close parenthesis. If it is necessary to subdivide a list item
further with an additional unordered list (i.e.,

have a nested unordered list), then the nested unordered list shall be
indented and each item in the nested

unordered list shall start with an upper case letter followed by a close
parenthesis.

The following is an example of an unordered list with a nested unordered
list:

> EXAMPLE - The following are the items for the assembly:
>
> a\) a box containing:
>
> A\) a bolt;
>
> B\) a nut; and
>
> C\) a washer;
>
> b\) a screwdriver; and
>
> c\) a wrench.

#### Ordered lists

An ordered list is one in which the order of the listed items is
important (i.e., item n is required before item n+1).

Each listed item starts with a Western-Arabic numeral followed by a
close parenthesis. If it is necessary to

subdivide a list item further with an additional unordered list (i.e.,
have a nested unordered list), then the nested

unordered list shall be indented and each item in the nested unordered
list shall start with an upper case letter

followed by a close parenthesis.

The following is an example of an ordered list with a nested unordered
list:

> EXAMPLE - The following are the instructions for the assembly:
>
> 1\) remove the contents from the box;
>
> 2\) assemble the item;
>
> A\) use a screwdriver to tighten the screws; and
>
> B\) use a wrench to tighten the bolts;
>
> and
>
> 3\) take a break.

### Numbering

A binary number is represented in this standard by any sequence of
digits consisting of only the Western-Arabic

numerals 0 and 1 immediately followed by a lower-case b (e.g., 0101b).
Underscores or spaces may be included

between characters in binary number representations to increase
readability or delineate field boundaries (e.g., 0

0101 1010b or 0_0101_1010b).

A hexadecimal number is represented in this standard by any sequence of
digits consisting of only the

Western-Arabic numerals 0 through 9 and/or the upper-case English
letters A through F immediately preceded by

"0x". Underscores or spaces may be included between characters in
hexadecimal number representations to increase readability or delineate
field boundaries (e.g., 0xFD8C FA23 or 0x0B_FD8C_FA23). Hexadecimal
numbers are in Courier New font.

A decimal number is represented in this standard by any sequence of
digits consisting of only the Western-Arabic

numerals 0 through 9 not immediately followed by a lower-case b or
lower-case h (e.g., 25). This standard uses

the following conventions for representing decimal numbers:

a)  the decimal separator (i.e., separating the integer and fractional
    portions of the number) is a period;

b)  the thousands separator (i.e., separating groups of three digits in
    a portion of the number) is a space; and

c)  the thousands separator is used in both the integer portion and the
    fraction portion of a number.

A decimal number represented in this standard with an overline over one
or more digits following the decimal point is a number where the
overlined digits are infinitely repeating (e.g.,
666.$\overline{\text{6}}$ means 666.666 666... or 666 2/3, and
12.$\overline{\text{142857}}$ means 12.142 857 142 857... or 12 1/7).

### Bit conventions

Name (n:m), where n is greater than m, denotes a set of bits (e.g.,
Feature (7:0)).

### Number range convention

p..q, where p is less than q, represents a range of numbers (e.g., words
100..103 represents words 100, 101,

102, and 103).

## Document References

### Document Precedence

If there is a conflict between this specification and any other
reference, then the precedence is (where a lower number indicates higher
precedence):

1.  this specification;

2.  TCG Storage Security Subsystem Class: Opal (see \[4\]);

3.  TCG Storage Interface Interactions Specification (see \[3\]);

4.  TCG Storage Architecture Core Specification (see \[2\]);

5.  references under development (see section 1.4.3); and

6.  approved references (see section 1.4.2) .

Each reference under development and each approved reference may specify
additional document precedence for itself.

### Approved References

IETF RFC 2119, 1997, "Key words for use in RFCs to Indicate Requirement
Levels"

Trusted Computing Group (TCG), "TCG Storage Architecture Core
Specification", Version 2.01

Trusted Computing Group (TCG), "Storage Interface Interactions
Specification", Version 1.09

Trusted Computing Group (TCG), "TCG Storage Security Subsystem Class:
Opal", Version 2.02

### References Under Development

xxx

## Dependencies on Other Feature Sets

This feature set does not depend upon any other feature sets.

## Interactions with Other Feature Sets

This feature set defines the interactions with the xxx Feature Set (see
xxx).

## Definitions of Terms

  -----------------------------------------------------------------------
  **Term**              **Definition**
  --------------------- -------------------------------------------------
  Eradicate             irrevocably erase (e.g., cryptographically erase)

  IF-RECV               An interface command used to retrieve security
                        protocol data from the TPer (see \[3\])

  IF-SEND               An interface command used to transmit security
                        protocol data to the TPer (see \[3\])

  Locking SP            A security provider that incorporates the Locking
                        Template as described in the Core Spec (see
                        \[2\])

  Locking SP is owned   A condition in which specific modifications of an
                        SP have been made (see \[3\])

  Opal family           Any of: Opal SSC, Opalite SSC, Ruby SSC, or
                        Pyrite SSC

  Read Locked           the state of a Locking object with a
                        ReadLockEnabled column value of TRUE and a
                        ReadLocked column value of TRUE (see \[2\])

  Read Unlocked         the state of a Locking object with a
                        ReadLockEnabled column value of FALSE or a
                        ReadLocked column value of FALSE (see \[2\])

  SD                    Storage Device

  SP                    Security Provider

  SSC                   Security Subsystem Class. SSC specifications
                        describe profiled sets of TCG functionality

  TPer                  The Trusted Peripheral is the subset of a SD for
                        which TCG manages security

  Write Locked          the state of a Locking object with a
                        WriteLockEnabled column value of TRUE and a
                        WriteLocked column value of TRUE (see \[2\])

  Write Unlocked        the state of a Locking object with a
                        WriteLockEnabled column value of FALSE or a
                        WriteLocked column value of FALSE (see \[2\])
  -----------------------------------------------------------------------

  : Table 3 - Level 0 Discovery -- xxx Feature Descriptor

# xxx Overview

# SSC Specific Functionality

xxx This section specifies the additional SSC-specific functionality
(not contained in xxxx) required to support the \<template\> Feature
Set.

## Methods

This section defines new methods and modifications to existing methods
required for this feature set.

### New Methods

This section defines the new methods that are required to support this
feature set.

#### xxx (M)

The Xxx method is a Locking Template-specific method.

*Start of Informative Comment*

xxx

*End of Informative Comment*

The following pseudo-code is the signature of the xxxx method (see xxx
for more information).

+-----------------------------------------------------------------------+
| LockingTableUID.Xxx \[                                                |
|                                                                       |
| Xxx1 : bytes_4,                                                       |
|                                                                       |
| Xxx2 = uinteger_8,                                                    |
|                                                                       |
| Xxx3 = uinteger_8,                                                    |
|                                                                       |
| Xxx4 = boolean\]                                                      |
|                                                                       |
| =\>                                                                   |
|                                                                       |
| \[ UID : uidref,                                                      |
|                                                                       |
| Result2 : boolean \]                                                  |
+=======================================================================+
+-----------------------------------------------------------------------+

: Table 4 - Feature Set Minor Versions

Method UID: 00 00 00 00 00 00 00 00

##### Parameter Descriptions

###### Xxx1

The xxx1 parameter specifies the value to which the xxx column of the
Locking object (see 3.2.2.1.1) SHALL be set.

###### Xxx2

The xxx2 parameter (if present) specifies the value to which the xxx
column of the Locking object SHALL be set.

###### Xxx3

The xxx3 parameter (if present) specifies the value to which the xxx
column of the Locking object SHALL be set.

###### Xxx4

*Start of Informative Comment*

xxx

*End of Informative Comment*

The xxx4 parameter (if present) specifies that the SD should xxx.

##### Returned Value Descriptions

###### UID

The UID value is the UID column value of the selected Locking object.

###### Xxx5

The xxx5 value is the xxx column value of the selected

##### xxx Method Operation

The operation of the Xxx method Deassign (M) is xxxx

### Modified Methods

This feature set modifies the following methods:

a)  Xxx;

b)  Xxx; and

c)  Xxx.

#### Xxx

*Start of Informative Comment*

The Xxx method is

.

## Tables

This section defines new tables and modifications to existing tables
required for this feature set.

### New Tables

There are no new tables defined by this feature set.

### Modified Tables

This feature set modifies the following tables:

a)  Xxx.

#### XXX

This feature set modifies the Xxx table by adding the following columns
(see Table 2), in addition to those defined in \[2\]:

  ---------------------------------------------------------------------------
  **Column Number**  **Column Name**           **IsUnique**   **Column Type**
  ------------------ ------------------------- -------------- ---------------
                     Xxx                                      

                                                              
  ---------------------------------------------------------------------------

  : Table 9 - Locking SP -- MethodID Table Preconfiguration

##### Xxx (M)

*Start of Informative Comment*

The Xxx column name

*End of Informative Comment*

 

#### Access Control (M)

The \<template\> Feature Set modifies the AccessControl table by adding
and modifying the following rows defined in \[4\]:

<table>
<caption><p>Table 10 - Locking SP – AccessControl Table
Preconfiguration</p></caption>
<colgroup>
<col style="width: 13%" />
<col style="width: 4%" />
<col style="width: 8%" />
<col style="width: 8%" />
<col style="width: 3%" />
<col style="width: 4%" />
<col style="width: 12%" />
<col style="width: 4%" />
<col style="width: 4%" />
<col style="width: 4%" />
<col style="width: 4%" />
<col style="width: 4%" />
<col style="width: 4%" />
<col style="width: 4%" />
<col style="width: 4%" />
<col style="width: 4%" />
<col style="width: 4%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Table Association</p>
<p>- informative only</p></th>
<th><blockquote>
<p><strong>UID</strong></p>
</blockquote></th>
<th><strong>InvokingID</strong></th>
<th><p>InvokingID Name</p>
<p>- informative only</p></th>
<th><strong>MethodID</strong></th>
<th><strong>CommonName</strong></th>
<th><strong>ACL</strong></th>
<th><strong>Log</strong></th>
<th><strong>AddACEACL</strong></th>
<th><strong>RemoveACEACL</strong></th>
<th><strong>GetACLACL</strong></th>
<th><strong>DeleteMethodACL</strong></th>
<th><strong>AddACELog</strong></th>
<th><strong>RemoveACELog</strong></th>
<th><strong>GetACLLog</strong></th>
<th><strong>DeleteMethodLog</strong></th>
<th><strong>LogTo</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><em><strong>ACE</strong></em></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td> </td>
<td></td>
<td>00 00 00 08<br />
00 03 80 02</td>
<td>ACE_Locking_Namespace_IdtoGlbRng</td>
<td>Set</td>
<td></td>
<td>ACE_ACE_Set_BooleanExpression</td>
<td></td>
<td></td>
<td></td>
<td>ACE_Anybody</td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td></td>
<td></td>
<td>00 00 00 08<br />
00 03 80 02</td>
<td>ACE_Locking_Namespace_IdtoGlbRng</td>
<td>Get</td>
<td></td>
<td>ACE_ACE_Get_All</td>
<td></td>
<td></td>
<td></td>
<td>ACE_Anybody</td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td><em><strong>Locking</strong></em></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td> </td>
<td></td>
<td>00 00 08 02<br />
00 03 00 01</td>
<td>Locking_Range1</td>
<td>Get</td>
<td></td>
<td>ACE_Locking_Range1_Get_<br />
RangeStartToActiveKey, ACE_Anybody_Get_CommonName,,<br />
ACE_Locking_Namespace_IDtoGlbRng</td>
<td></td>
<td></td>
<td></td>
<td>ACE_Anybody</td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td></td>
<td></td>
<td>00 00 08 02<br />
00 03 00 00 (+NN NN)</td>
<td>Locking_RangeNNNN</td>
<td>Get</td>
<td></td>
<td>ACE_Locking_RangeNNNN_Get_<br />
RangeStartToActiveKey, ACE_Anybody_Get_CommonName,<br />
ACE_Locking_Namespace_IDtoGlbRng</td>
<td></td>
<td></td>
<td></td>
<td>ACE_Anybody</td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
</tbody>
</table>

: Table 10 - Locking SP -- AccessControl Table Preconfiguration

#### ACE (M)

The \<template\> Feature Sett modifies the ACE Table by adding the
following rows, in addition to those defined in \[4\]:

+------+-------+-------------------------+---+----------+-------------+
| T    | **    | **Name**                | * | **Boole  | **Columns** |
| able | UID** |                         | * | anExpr** |             |
| Ass  |       |                         | C |          |             |
| ocia |       |                         | o |          |             |
| tion |       |                         | m |          |             |
|      |       |                         | m |          |             |
| -Inf |       |                         | o |          |             |
| orma |       |                         | n |          |             |
| tive |       |                         | N |          |             |
| Co   |       |                         | a |          |             |
| lumn |       |                         | m |          |             |
|      |       |                         | e |          |             |
|      |       |                         | * |          |             |
|      |       |                         | * |          |             |
+======+=======+=========================+===+==========+=============+
| *    |       |                         |   |          |             |
| **Lo |       |                         |   |          |             |
| ckin |       |                         |   |          |             |
| g*** |       |                         |   |          |             |
+------+-------+-------------------------+---+----------+-------------+
|      | 00 00 | \"ACE_Locking           |   | Admins   | N           |
|      | 00    | _Namespace_IdtoGlbRng\" |   |          | amespaceID, |
|      | 08\   |                         |   |          | Namespace   |
|      | 00 03 |                         |   |          | GlobalRange |
|      | 80 02 |                         |   |          |             |
+------+-------+-------------------------+---+----------+-------------+

: Table 11 - Locking SP -- ACE Table Preconfiguration

## Types

This section defines new types and modifications to existing types
required for this feature set.

### New Types

There are no new types defined by this feature set.

### Modified Types

There are no types modified by this feature set.

# Feature Set Requirements

This section defines the Mandatory (M) and Optional (O) requirements for
the \<template\> Feature Set.

## Requirements Overview

The \<template\> Feature Set consists of xxx capabilities that MAY be
implemented in a TPer. A Host discovers the xxx specific capabilities
and properties of a TPer by examining xxx

## Level 0 Discovery

A SD implementing the \<template\> Feature Set SHALL:

a)  Xxx.

### xxx Descriptor (Feature Code = 0x000) (M)

The xxx Feature Descriptor SHALL be returned when the SD supports the
\<template\> Feature Set. The contents of the feature descriptor are
defined in Table 3.

+------+------+-------+------+------+------+------+-------+-------+
| **B  | *    | **6** | *    | *    | *    | *    | **1** | **0** |
| it** | *7** |       | *5** | *4** | *3** | *2** |       |       |
|      |      |       |      |      |      |      |       |       |
| **By |      |       |      |      |      |      |       |       |
| te** |      |       |      |      |      |      |       |       |
+======+======+=======+======+======+======+======+=======+=======+
| 0    | (    | Fe    |      |      |      |      |       |       |
|      | MSB) | ature |      |      |      |      |       |       |
|      |      | Code  |      |      |      |      |       |       |
+------+------+-------+------+------+------+------+-------+-------+
| 1    |      |       |      |      |      |      |       | (LSB) |
+------+------+-------+------+------+------+------+-------+-------+
| 2    | Fea  |       |      |      | Fea  |      |       |       |
|      | ture |       |      |      | ture |      |       |       |
|      | De   |       |      |      | Set  |      |       |       |
|      | scri |       |      |      | M    |      |       |       |
|      | ptor |       |      |      | inor |      |       |       |
|      | Ver  |       |      |      | Ver  |      |       |       |
|      | sion |       |      |      | sion |      |       |       |
|      | Nu   |       |      |      | Nu   |      |       |       |
|      | mber |       |      |      | mber |      |       |       |
+------+------+-------+------+------+------+------+-------+-------+
| 3    | Le   |       |      |      |      |      |       |       |
|      | ngth |       |      |      |      |      |       |       |
+------+------+-------+------+------+------+------+-------+-------+
| 4    |      |       |      |      |      |      |       |       |
+------+------+-------+------+------+------+------+-------+-------+
| 5 -- | Rese |       |      |      |      |      |       |       |
| 7    | rved |       |      |      |      |      |       |       |
+------+------+-------+------+------+------+------+-------+-------+
| 8    | (    | xxx   |      |      |      |      |       |       |
|      | MSB) |       |      |      |      |      |       |       |
+------+------+-------+------+------+------+------+-------+-------+
| ...  |      |       |      |      |      |      |       |       |
+------+------+-------+------+------+------+------+-------+-------+
| 11   |      |       |      |      |      |      |       | (LSB) |
+------+------+-------+------+------+------+------+-------+-------+

: Table 12 - Locking SP -- Locking Table Preconfiguration

#### Feature Code

The Feature Code field value SHALL be set to 0x0000.

#### Feature Descriptor Version Number

The Feature Descriptor Version Number field SHALL be set to 0x1.

#### Feature Set Minor Version Number

The Feature Set Minor Version Number represents the minor version of the
\<template\> Feature Set supported by the SD.

The Feature Set Minor Version Number field SHALL be set to a value as
specified in Table 4.

  -----------------------------------------------------------------------
  Feature Set   Specification Referenced
  Minor Version 
  Number        
  ------------- ---------------------------------------------------------
  0x00          \<template\> Feature Set v1.00

  All others    Reserved
  -----------------------------------------------------------------------

#### Length

The Length field indicates the number of bytes in the descriptor
following byte 3. The value of the Length field SHALL be set to 0x10.

#### Range_C

The xxx (xxx) field is set to one to indicate that the SD supports xxx.
The xxx field is set to zero to indicate that the SD does not support
xxx.

If the Range_C field is set to one, then the SD SHALL support Namespace
Level 0 Discovery as defined in 4.2.2.

If the Range_C field is set to zero, then the SD SHOULD support
Namespace Level 0 Discovery as defined in 4.2.2.

**\
**

## Admin SP

This feature set modifies the behavior of the Revert method (see xxx).

## Locking SP

A SD implementing this feature set SHALL support the additions to the
Locking SP specified in this section, in addition to the Locking SP
requirements defined in \[4\].

This feature set modifies the behavior of the RevertSP method (see xxx).

### Tables

#### Locking table (M)

##### Global Range (M)

The Global Range Locking object .

##### Preconfiguration

In addition to the requirements in \[4\], the MethodID table
preconfiguration SHALL be modified as specified in Table 9:

+----------------+--------------+--------------------+----------------+
| **UID**        | **Name**     | **CommonName**     | **TemplateID** |
+================+==============+====================+================+
| 00 00 00 06    | "Assign"     |                    |                |
|                |              |                    |                |
| 00 00 08 04    |              |                    |                |
+----------------+--------------+--------------------+----------------+
| 00 00 00 06    | "Deassign"   |                    |                |
|                |              |                    |                |
| 00 00 08 05    |              |                    |                |
+----------------+--------------+--------------------+----------------+

In addition to the requirements in \[4\], the AccessControl table SHALL
be preconfigured as specified in Table 10:

<table>
<colgroup>
<col style="width: 10%" />
<col style="width: 4%" />
<col style="width: 12%" />
<col style="width: 6%" />
<col style="width: 6%" />
<col style="width: 4%" />
<col style="width: 6%" />
<col style="width: 4%" />
<col style="width: 4%" />
<col style="width: 4%" />
<col style="width: 6%" />
<col style="width: 4%" />
<col style="width: 4%" />
<col style="width: 4%" />
<col style="width: 4%" />
<col style="width: 4%" />
<col style="width: 4%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Table Association</p>
<p>– informative only</p></th>
<th><blockquote>
<p><strong>UID</strong></p>
</blockquote></th>
<th><blockquote>
<p><strong>InvokingID</strong></p>
</blockquote></th>
<th><blockquote>
<p>InvokingID Name – informative only</p>
</blockquote></th>
<th><blockquote>
<p><strong>MethodID</strong></p>
</blockquote></th>
<th><blockquote>
<p><strong>CommonName</strong></p>
</blockquote></th>
<th><blockquote>
<p><strong>ACL</strong></p>
</blockquote></th>
<th><blockquote>
<p><strong>Log</strong></p>
</blockquote></th>
<th><blockquote>
<p><strong>AddACEACL</strong></p>
</blockquote></th>
<th><blockquote>
<p><strong>RemoveACEACL</strong></p>
</blockquote></th>
<th><blockquote>
<p><strong>GetACLACL</strong></p>
</blockquote></th>
<th><blockquote>
<p><strong>DeleteMethodAC</strong>L</p>
</blockquote></th>
<th><blockquote>
<p><strong>AddACELog</strong></p>
</blockquote></th>
<th><blockquote>
<p><strong>RemoveACELog</strong></p>
</blockquote></th>
<th><blockquote>
<p><strong>GetACLLog</strong></p>
</blockquote></th>
<th><blockquote>
<p><strong>DeleteMethodLog</strong></p>
</blockquote></th>
<th><blockquote>
<p><strong>LogTo</strong></p>
</blockquote></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><em>SP</em></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td></td>
<td></td>
<td><blockquote>
<p>00 00 08 02</p>
<p>00 00 00 00</p>
</blockquote></td>
<td><blockquote>
<p>LockingTableUID</p>
</blockquote></td>
<td><blockquote>
<p>Assign</p>
</blockquote></td>
<td></td>
<td><blockquote>
<p>ACE_Assign</p>
</blockquote></td>
<td></td>
<td></td>
<td></td>
<td><blockquote>
<p>ACE_Anybody</p>
</blockquote></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td></td>
<td></td>
<td><blockquote>
<p>00 00 08 02</p>
<p>00 00 00 00</p>
</blockquote></td>
<td><blockquote>
<p>LockingTableUID</p>
</blockquote></td>
<td><blockquote>
<p>Deassign</p>
</blockquote></td>
<td></td>
<td><blockquote>
<p>ACE_Deassign</p>
</blockquote></td>
<td></td>
<td></td>
<td></td>
<td><blockquote>
<p>ACE_Anybody</p>
</blockquote></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td><em>ACE</em></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td></td>
<td></td>
<td><blockquote>
<p>00 00 00 08</p>
<p>00 03 F9 01</p>
</blockquote></td>
<td><blockquote>
<p>ACE_Assign</p>
</blockquote></td>
<td><blockquote>
<p>Get</p>
</blockquote></td>
<td></td>
<td><blockquote>
<p>ACE_ACE_Get_All</p>
</blockquote></td>
<td></td>
<td></td>
<td></td>
<td><blockquote>
<p>ACE_Anybody</p>
</blockquote></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td></td>
<td></td>
<td><blockquote>
<p>00 00 00 08</p>
<p>00 03 F9 01</p>
</blockquote></td>
<td><blockquote>
<p>ACE_Assign</p>
</blockquote></td>
<td><blockquote>
<p>Set</p>
</blockquote></td>
<td></td>
<td><blockquote>
<p>ACE_ACE_Set_BooleanExpression</p>
</blockquote></td>
<td></td>
<td></td>
<td></td>
<td><blockquote>
<p>ACE_Anybody</p>
</blockquote></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td></td>
<td></td>
<td><blockquote>
<p>00 00 00 08</p>
<p>00 03 F9 02</p>
</blockquote></td>
<td><blockquote>
<p>ACE_Deassign</p>
</blockquote></td>
<td><blockquote>
<p>Get</p>
</blockquote></td>
<td></td>
<td><blockquote>
<p>ACE_ACE_Get_All</p>
</blockquote></td>
<td></td>
<td></td>
<td></td>
<td><blockquote>
<p>ACE_Anybody</p>
</blockquote></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td></td>
<td></td>
<td><blockquote>
<p>00 00 00 08</p>
<p>00 03 F9 02</p>
</blockquote></td>
<td><blockquote>
<p>ACE_Deassign</p>
</blockquote></td>
<td><blockquote>
<p>Set</p>
</blockquote></td>
<td></td>
<td><blockquote>
<p>ACE_ACE_Set_BooleanExpression</p>
</blockquote></td>
<td></td>
<td></td>
<td></td>
<td><blockquote>
<p>ACE_Anybody</p>
</blockquote></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
</tbody>
</table>

In addition to the requirements in \[4\], the ACE Table SHALL be
preconfigured as specified in Table 11:

+---+-----------+-------------------------+---+----------+-------------+
| T | > **UID** | > **Name**              | > | >        | >           |
| a |           |                         |   |  **Boole | **Columns** |
| b |           |                         | * | anExpr** |             |
| l |           |                         | * |          |             |
| e |           |                         | C |          |             |
| A |           |                         | o |          |             |
| s |           |                         | m |          |             |
| s |           |                         | m |          |             |
| o |           |                         | o |          |             |
| c |           |                         | n |          |             |
| i |           |                         | N |          |             |
| a |           |                         | a |          |             |
| t |           |                         | m |          |             |
| i |           |                         | e |          |             |
| o |           |                         | * |          |             |
| n |           |                         | * |          |             |
|   |           |                         |   |          |             |
| - |           |                         |   |          |             |
| - |           |                         |   |          |             |
| i |           |                         |   |          |             |
| n |           |                         |   |          |             |
| f |           |                         |   |          |             |
| o |           |                         |   |          |             |
| r |           |                         |   |          |             |
| m |           |                         |   |          |             |
| a |           |                         |   |          |             |
| t |           |                         |   |          |             |
| i |           |                         |   |          |             |
| v |           |                         |   |          |             |
| e |           |                         |   |          |             |
| o |           |                         |   |          |             |
| n |           |                         |   |          |             |
| l |           |                         |   |          |             |
| y |           |                         |   |          |             |
+===+===========+=========================+===+==========+=============+
| * |           |                         |   |          |             |
| A |           |                         |   |          |             |
| C |           |                         |   |          |             |
| E |           |                         |   |          |             |
| * |           |                         |   |          |             |
+---+-----------+-------------------------+---+----------+-------------+
|   | > 00 00   | "ACE_Assign"            |   | Admins   | All         |
|   | > 00 08   |                         |   |          |             |
|   |           |                         |   |          |             |
|   | 00 03 F9  |                         |   |          |             |
|   | 01        |                         |   |          |             |
+---+-----------+-------------------------+---+----------+-------------+
|   | > 00 00   | "ACE_Deassign"          |   | Admins   | All         |
|   | > 00 08   |                         |   |          |             |
|   |           |                         |   |          |             |
|   | 00 03 F9  |                         |   |          |             |
|   | 02        |                         |   |          |             |
+---+-----------+-------------------------+---+----------+-------------+

In addition to the requirements in \[4\], the added columns in the
Locking table SHALL be preconfigured as specified in Table 12.

\*LT1 = indirectly writeable using the Assign method and the Deassign
method.

+------------+---------------------+-------------+-------------------+
| **UID**    | **Name**            | **Na        | **Names           |
|            |                     | mespaceID** | paceGlobalRange** |
+============+=====================+=============+===================+
| 00 00 08   | "L                  | 0x0000_0000 | **T**             |
| 02         | ocking_GlobalRange" |             |                   |
|            |                     |             |                   |
| 00 00 00   |                     |             |                   |
| 01         |                     |             |                   |
+------------+---------------------+-------------+-------------------+
| 00 00 08   | "Locking_Range1"    | 0x0000_0000 | **F**             |
| 02         |                     |             |                   |
|            |                     | \*LT1       | \*LT1             |
| 00 03 00   |                     |             |                   |
| 01         |                     |             |                   |
+------------+---------------------+-------------+-------------------+
| 00 00 08   | "Locking_RangeNNNN" | 0x0000_0000 | **F**             |
| 02         |                     |             |                   |
|            |                     | \*LT1       | \*LT1             |
| 00 03 NN   |                     |             |                   |
| NN         |                     |             |                   |
+------------+---------------------+-------------+-------------------+

## Additional SPs

This feature set requires no additional SPs.

 

## Otherxxx Feature Set Interactions

### Overview

The Otherxxx Feature Set (see xxx) MAY be supported on a TPer that
supports the \<template\> Feature Set.

This section describes the interactions when the \<template\> Feature
Set and the Otherxxx Feature Set (see xxx) are both supported and
present (enabled or disabled).

xxx

### Modified Methods

This section defines modifications to methods that are required to
support the Single User Mode Feature Set (see \[6\]) in addition to the
Configurable Locking for NVMe Namespaces and SCSI LUNs Feature Set.

#### Xxx

Xxx method interactions with Otherxxx are xxx