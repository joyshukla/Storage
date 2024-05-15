> ![](media/image1.wmf)

TCG Storage

Opal SSC Feature Set:\
PSID

Specification Version 1.00

1.  1.00

August 5, 2015

Contact: admin@trustedcomputinggroup.org

**PUBLISHED**

Copyright © TCG 2015

Copyright ^©^ 2015 Trusted Computing Group, Incorporated.

**Disclaimers, Notices, and License Terms**

THIS SPECIFICATION IS PROVIDED \"AS IS\" WITH NO WARRANTIES WHATSOEVER,
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

Contact the Trusted Computing Group at
[www.trustedcomputinggroup.org](http://www.trustedcomputinggroup.org)
for information on specification licensing through membership
agreements.

Any marks and brands contained herein are the property of their
respective owners.

Table of Contents

[1 Introduction [1](#introduction)](#introduction)

[1.1 Document Purpose [1](#document-purpose)](#document-purpose)

[1.2 Scope and Intended Audience
[1](#scope-and-intended-audience)](#scope-and-intended-audience)

[1.3 Key Words [1](#key-words)](#key-words)

[1.4 Document References
[1](#document-references)](#document-references)

[1.5 Document Precedence
[1](#document-precedence)](#document-precedence)

[1.6 Dependencies on Other Feature Sets
[2](#dependencies-on-other-feature-sets)](#dependencies-on-other-feature-sets)

[1.7 Interactions with Other Feature Sets
[2](#interactions-with-other-feature-sets)](#interactions-with-other-feature-sets)

[1.8 Terminology [2](#terminology)](#terminology)

[1.9 Legend [3](#legend)](#legend)

[2 PSID Feature Set Overview
[4](#psid-feature-set-overview)](#psid-feature-set-overview)

[3 SSC Specific Functionality
[5](#ssc-specific-functionality)](#ssc-specific-functionality)

[4 Feature Set Requirements
[6](#feature-set-requirements)](#feature-set-requirements)

[4.1 Level 0 Discovery [6](#level-0-discovery)](#level-0-discovery)

[4.2 Admin SP [6](#admin-sp)](#admin-sp)

[4.2.1 PSID Authority (M) [6](#psid-authority-m)](#psid-authority-m)

[4.2.1.1 PSID Authority Object Access Control
[6](#psid-authority-object-access-control)](#psid-authority-object-access-control)

[4.2.2 PSID Authority Associated Credential
[7](#psid-authority-associated-credential)](#psid-authority-associated-credential)

[4.2.2.1 PSID C_PIN Object Access Control
[7](#psid-c_pin-object-access-control)](#psid-c_pin-object-access-control)

[4.2.3 New ACEs [7](#new-aces)](#new-aces)

[4.2.3.1 ACE_C_PIN_Get_PSID_NoPIN
[7](#ace_c_pin_get_psid_nopin)](#ace_c_pin_get_psid_nopin)

[4.2.3.1.1 ACE_C_PIN_Get_PSID_NoPIN Access Control
[8](#ace_c_pin_get_psid_nopin-access-control)](#ace_c_pin_get_psid_nopin-access-control)

[4.2.3.2 ACE_SP_PSID [8](#ace_sp_psid)](#ace_sp_psid)

[4.2.3.2.1 ACE_SP_PSID Access Control
[8](#ace_sp_psid-access-control)](#ace_sp_psid-access-control)

[4.2.4 Performing Device Reversion
[8](#performing-device-reversion)](#performing-device-reversion)

[4.3 Locking SP [9](#locking-sp)](#locking-sp)

[4.4 Additional SPs [9](#additional-sps)](#additional-sps)

**Tables**

[Table 1 PSID Authority [6](#psid-authority)](#psid-authority)

[Table 2 PSID Authority Access Control Settings
[6](#psid-authority-access-control-settings)](#psid-authority-access-control-settings)

[Table 3 PSID C_PIN [7](#psid-c_pin)](#psid-c_pin)

[Table 4 PSID C_PIN Access Control Settings
[7](#psid-c_pin-access-control-settings)](#psid-c_pin-access-control-settings)

[Table 5 ACE_C_PIN_Get_PSID_NoPIN ACE
[8](#ace_c_pin_get_psid_nopin-ace)](#ace_c_pin_get_psid_nopin-ace)

[Table 6 ACE_SP_PSID ACE [8](#ace_sp_psid-ace)](#ace_sp_psid-ace)

[Table 7 Device Reversion Access Control Settings
[9](#device-reversion-access-control-settings)](#device-reversion-access-control-settings)

# Introduction

## Document Purpose

The Storage Workgroup specifications provide a comprehensive
architecture for putting Storage Devices under policy control as
determined by the trusted platform host, the capabilities of the Storage
Device to conform with the policies of the trusted platform, and the
lifecycle state of the Storage Device as a Trusted Peripheral.

## Scope and Intended Audience

This specification defines the PSID Feature Set for the Opal Security
Subsystem Class (SSC). Any Storage Device that claims Opal SSC PSID
Feature Set compatibility SHALL conform to this specification.

The intended audience for this specification is both trusted Storage
Device manufacturers and developers that want to use these Storage
Devices in their systems.

## Key Words 

Key words are used to signify SSC requirements.

The Key Words "**SHALL**", "**SHALL NOT**", "**SHOULD**," and "**MAY**"
are used in this document. These words are a subset of the RFC 2119 key
words used by TCG, and have been chosen since they map to key words used
in T10/T13 specifications. These key words are to be interpreted as
described in \[1\].

In addition to the above key words, the following are also used in this
document to describe the requirements of particular features, including
tables, methods, and usages thereof.

-   **Mandatory (M):** When a feature is Mandatory, the feature SHALL be
    implemented. A Compliance test SHALL validate that the feature is
    operational.

-   **Optional (O):** When a feature is Optional, the feature MAY be
    implemented. If implemented, a Compliance test SHALL validate that
    the feature is operational.

-   **Excluded (X):** When a feature is Excluded, the feature SHALL NOT
    be implemented. A Compliance test SHALL validate that the feature is
    [not]{.underline} operational.

-   **Not Required (N)** When a feature is Not Required, the feature MAY
    be implemented. No Compliance test is required.

## Document References

1.  IETF RFC 2119, 1997, "Key words for use in RFCs to Indicate
    Requirement Levels"

2.  Trusted Computing Group (TCG), "TCG Storage Architecture Core
    Specification", see \[3\] for the applicable specification version

3.  Trusted Computing Group (TCG), "TCG Storage Security Subsystem
    Class: Opal", Versions 1.00, 2.00, 2.01, or compatible

4.  Trusted Computing Group (TCG), "TCG Storage Storage Interface
    Interactions Specification", see \[3\] for the applicable
    specification version

## Document Precedence

In the event of conflicting information in this specification and other
documents, the precedence for requirements is:

1.  This specification and TCG Storage Security Subsystem Class: Opal
    \[3\] (these two documents are at the same level of precedence, and
    SHALL NOT conflict with each other)

2.  Storage Interface Interactions Specification \[4\]

3.  TCG Storage Architecture Core Specification \[2\]

## Dependencies on Other Feature Sets

This feature set has no dependencies on other feature sets.

## Interactions with Other Feature Sets

This feature set has no interactions with other feature sets.

## Terminology

This section provides special definitions that are not defined in the
Core Specification.

  -----------------------------------------------------------------------
  **Term**              **Definition**
  --------------------- -------------------------------------------------
  PSID                  Physical Presence SID

  -----------------------------------------------------------------------

  : PSID Feature Set Terminology

## Legend

The following legend defines SP table cell coloring coding. This color
coding is informative only. The table cell content is normative.

+------+-------+-------------+--------------+------------------------+
| **T  | **    | **Value**   | **Access     | **Comment**            |
| able | R-W** |             | Control**    |                        |
| Cell |       |             |              |                        |
| Lege |       |             |              |                        |
| nd** |       |             |              |                        |
+======+=======+=============+==============+========================+
| Aria | Read  | Opal SSC    | Fixed        | -   Cell content is    |
| l-Na | -only | specified   |              |     Read-Only.         |
| rrow |       |             |              |                        |
|      |       |             |              | -   Access control is  |
|      |       |             |              |     fixed.             |
|      |       |             |              |                        |
|      |       |             |              | -   Value is specified |
|      |       |             |              |     by the Opal SSC    |
+------+-------+-------------+--------------+------------------------+
| **[A | Read  | VU          | Fixed        | -   Cell content is    |
| rial | -only |             |              |     Read-Only.         |
| Na   |       |             |              |                        |
| rrow |       |             |              | -   Access Control is  |
| b    |       |             |              |     fixed.             |
| old- |       |             |              |                        |
| unde |       |             |              | -   Values are Vendor  |
| r]{. |       |             |              |     Unique (VU). A     |
| unde |       |             |              |     minimum or maximum |
| rlin |       |             |              |     value may be       |
| e}** |       |             |              |     specified.         |
+------+-------+-------------+--------------+------------------------+
| Aria | Not   | \(N\)       | Not Defined  | -   Cell content       |
| l-Na | De    |             |              |     content is (N).    |
| rrow | fined |             |              |                        |
|      |       |             |              | -   Access control is  |
|      |       |             |              |     not defined.       |
|      |       |             |              |                        |
|      |       |             |              | -   Any text in table  |
|      |       |             |              |     cell is            |
|      |       |             |              |     informative only.  |
|      |       |             |              |                        |
|      |       |             |              | -   A Get MAY omit     |
|      |       |             |              |     this column from   |
|      |       |             |              |     the method         |
|      |       |             |              |     response.          |
+------+-------+-------------+--------------+------------------------+
| **[A | Write | Prec        | Pre          | -   Cell content is    |
| rial |       | onfigured,\ | configured,\ |     writable.          |
| Na   |       | user        | user         |                        |
| rrow |       | per         | pe           | -   Access control is  |
| b    |       | sonalizable | rsonalizable |     personalizable     |
| old- |       |             |              |                        |
| unde |       |             |              | -   Get Access Control |
| r]{. |       |             |              |     is not described   |
| unde |       |             |              |     by this color      |
| rlin |       |             |              |     coding             |
| e}** |       |             |              |                        |
+------+-------+-------------+--------------+------------------------+
| Aria | Write | Prec        | Fixed        | -   Cell content is    |
| l-Na |       | onfigured,\ |              |     writable.          |
| rrow |       | user        |              |                        |
|      |       | per         |              | -   Access control is  |
|      |       | sonalizable |              |     fixed.             |
|      |       |             |              |                        |
|      |       |             |              | -   Get Access Control |
|      |       |             |              |     is not described   |
|      |       |             |              |     by this color      |
|      |       |             |              |     coding             |
+------+-------+-------------+--------------+------------------------+

: SP Table Legend

# PSID Feature Set Overview

*Begin Informative Content*

The goal of the PSID Feature Set is to:

-   Define an authority/credential pair whose C_PIN object's PIN column
    value is not discoverable via the interface.

-   Provide access control settings that permit invocation of the Revert
    method if the PSID authority has been successfully authenticated.

The primary use case for this is one where the SID is not known, or
manageability of the device has been lost, and the owner wishes to
attempt to reset the device to OFS via the Revert method defined in
\[3\].

Because the PSID credential value is specified such that it is not
discoverable via the interface, it is necessary that the credential
value be delivered via an alternative mechanism. Examples of these
mechanisms include printing the PSID credential on a device label; or
including the value as an insert in the device packaging. The delivery
mechanism is vendor unique.

*End Informative Content*

# SSC Specific Functionality

This feature set requires no additional SSC-specific functionality.

# Feature Set Requirements

This section defines the Mandatory (M) and Optional (O) requirements for
the PSID Feature Set, when it is implemented in an Opal-compliant
device.

## Level 0 Discovery

No Level 0 Feature Descriptor is needed for this feature set. Support
for the PSID Feature Set can be determined by inspection of the Admin
SP's Authority table.

## Admin SP

An Opal-compliant SD that contains the PSID Feature Set SHALL contain
the additions to the Admin SP specified in this section, in addition to
the Admin SP requirements defined in \[3\].

### PSID Authority (M)

The PSID authority SHALL have the characteristics defined in this
section.

## PSID Authority {#psid-authority .Table}

<table>
<colgroup>
<col style="width: 13%" />
<col style="width: 4%" />
<col style="width: 6%" />
<col style="width: 3%" />
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
<col style="width: 4%" />
<col style="width: 4%" />
<col style="width: 4%" />
<col style="width: 4%" />
<col style="width: 4%" />
</colgroup>
<thead>
<tr class="header">
<th><strong>UID</strong></th>
<th><strong>Name</strong></th>
<th><strong>CommonName</strong></th>
<th><strong>IsClass</strong></th>
<th><strong>Class</strong></th>
<th><strong>Enabled</strong></th>
<th><strong>Secure</strong></th>
<th><strong>HashAndSign</strong></th>
<th><strong>PresentCertificate</strong></th>
<th><strong>Operation</strong></th>
<th><strong>Credential</strong></th>
<th><strong>ResponseSign</strong></th>
<th><strong>ResponseExch</strong></th>
<th><strong>ClockStart</strong></th>
<th><strong>ClockEnd</strong></th>
<th><strong>Limit</strong></th>
<th><strong>Uses</strong></th>
<th><strong>Log</strong></th>
<th><strong>LogTo</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>00 00 00 09 00 01 FF 01</td>
<td>"PSID"</td>
<td><blockquote>
<p>“PhysicalDriveOwner”</p>
</blockquote></td>
<td>F</td>
<td>Null</td>
<td>T</td>
<td><blockquote>
<p>None</p>
</blockquote></td>
<td><blockquote>
<p>None</p>
</blockquote></td>
<td>F</td>
<td><blockquote>
<p>Password</p>
</blockquote></td>
<td>C_PIN_PSID</td>
<td>Null</td>
<td>Null</td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
</tbody>
</table>

#### PSID Authority Object Access Control

Access control on methods applicable to the PSID authority object are as
defined in this section.

## PSID Authority Access Control Settings {#psid-authority-access-control-settings .Table}

<table>
<colgroup>
<col style="width: 16%" />
<col style="width: 3%" />
<col style="width: 9%" />
<col style="width: 5%" />
<col style="width: 3%" />
<col style="width: 4%" />
<col style="width: 8%" />
<col style="width: 2%" />
<col style="width: 4%" />
<col style="width: 4%" />
<col style="width: 6%" />
<col style="width: 4%" />
<col style="width: 4%" />
<col style="width: 4%" />
<col style="width: 4%" />
<col style="width: 3%" />
<col style="width: 6%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Table Association</p>
<p>- informative oly</p></th>
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
<td><em><strong>Authority</strong></em></td>
<td><blockquote>
<p> </p>
</blockquote></td>
<td> </td>
<td> </td>
<td> </td>
<td> </td>
<td> </td>
<td> </td>
<td> </td>
<td> </td>
<td> </td>
<td> </td>
<td> </td>
<td> </td>
<td> </td>
<td> </td>
<td> </td>
</tr>
<tr class="even">
<td></td>
<td></td>
<td><p>00 00 00 09</p>
<p>00 01 FF 01</p></td>
<td>PSID</td>
<td>Get</td>
<td></td>
<td>ACE_Anybody</td>
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

### PSID Authority Associated Credential

This section defines the attributes of the credential associated with
the PSID authority, C_PIN_PSID. Support for this credential is Mandatory
(M) if the PSID authority is supported.

The PIN column value SHALL contain a vendor unique value that is a
statistically unique value for each device.

## PSID C_PIN {#psid-c_pin .Table}

+---------+---------+-----------+----+------+------+----+---------+
| **UID** | *       | **Com     | *  | **C  | **Tr | *  | *       |
|         | *Name** | monName** | *P | harS | yLim | *T | *Persis |
|         |         |           | IN | et** | it** | ri | tence** |
|         |         |           | ** |      |      | es |         |
|         |         |           |    |      |      | ** |         |
+=========+=========+===========+====+======+======+====+=========+
| 00 00   | \"C_PIN | "P        | ** | Null | **[V | ** | FALSE   |
| 00 0B   | _PSID\" | hysicalDr | [V |      | U]{. | [V |         |
|         |         | iveOwner" | U] |      | unde | U] |         |
| 00 01   |         |           | {. |      | rlin | {. |         |
| FF 01   |         |           | un |      | e}** | un |         |
|         |         |           | de |      |      | de |         |
|         |         |           | rl |      |      | rl |         |
|         |         |           | in |      |      | in |         |
|         |         |           | e} |      |      | e} |         |
|         |         |           | ** |      |      | ** |         |
+---------+---------+-----------+----+------+------+----+---------+

#### PSID C_PIN Object Access Control

Access control on methods applicable to the PSID C_PIN object are as
defined in this section.

## PSID C_PIN Access Control Settings  {#psid-c_pin-access-control-settings .Table}

<table>
<colgroup>
<col style="width: 14%" />
<col style="width: 4%" />
<col style="width: 9%" />
<col style="width: 6%" />
<col style="width: 6%" />
<col style="width: 6%" />
<col style="width: 5%" />
<col style="width: 4%" />
<col style="width: 4%" />
<col style="width: 4%" />
<col style="width: 5%" />
<col style="width: 4%" />
<col style="width: 4%" />
<col style="width: 4%" />
<col style="width: 4%" />
<col style="width: 4%" />
<col style="width: 4%" />
</colgroup>
<thead>
<tr class="header">
<th><p><strong>Table association</strong></p>
<p><strong>- Informative text</strong></p></th>
<th><strong>UID</strong></th>
<th><strong>InvokingID</strong></th>
<th><p>InvokingID Name</p>
<p>- Iinformative text</p></th>
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
<td><em><strong>C_PIN</strong></em></td>
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
<p>00 00 00 0B</p>
<p>00 01 FF 01</p>
</blockquote></td>
<td>C_PIN_PSID</td>
<td>Get</td>
<td></td>
<td>ACE_C_PIN_Get_PSID_NoPIN</td>
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

##  {#section .Table .unnumbered}

### New ACEs

This section defines new ACEs to be added in conjunction with the PSID
authority/credential.

#### ACE_C_PIN_Get_PSID_NoPIN

This section defines the ACE that enables retrieval of the attributes of
C_PIN_PSID.

Support for this ACE is Mandatory (M) if the PSID authority is
supported.

## ACE_C_PIN_Get_PSID_NoPIN ACE {#ace_c_pin_get_psid_nopin-ace .Table}

+----------+--------+---------------------+---+------+-----------------+
| **Table  | *      | **Name**            | * | **B  | **Columns**     |
| Assocu   | *UID** |                     | * | oole |                 |
| iation** |        |                     | C | anEx |                 |
|          |        |                     | o | pr** |                 |
| **-      |        |                     | m |      |                 |
| Inf      |        |                     | m |      |                 |
| ormative |        |                     | o |      |                 |
| text**   |        |                     | n |      |                 |
|          |        |                     | N |      |                 |
|          |        |                     | a |      |                 |
|          |        |                     | m |      |                 |
|          |        |                     | e |      |                 |
|          |        |                     | * |      |                 |
|          |        |                     | * |      |                 |
+==========+========+=====================+===+======+=================+
| **ACE**  |        |                     |   |      |                 |
+----------+--------+---------------------+---+------+-----------------+
|          | 00 00  | "ACE_C_             |   | Any  | UID,            |
|          | 00 08  | PIN_Get_PSID_NoPIN" |   | body |                 |
|          | 00 01  |                     |   |      | CharSet,        |
|          | 00 E1  |                     |   |      | TryLimit,       |
|          |        |                     |   |      | Tries,          |
|          |        |                     |   |      | Persistence     |
+----------+--------+---------------------+---+------+-----------------+

##### ACE_C_PIN_Get_PSID_NoPIN Access Control

Get access to ACE objects is as defined by \[3\].

#### ACE_SP_PSID

This section defines the ACE that allows the PSID authority to be used
to perform a device reversion operation.

Support for this ACE is Mandatory (M) if the PSID authority is
supported.

## ACE_SP_PSID ACE {#ace_sp_psid-ace .Table}

+----------+--------+---------------------+---+------+-----------------+
| **Table  | *      | **Name**            | * | **B  | **Columns**     |
| Assocu   | *UID** |                     | * | oole |                 |
| iation** |        |                     | C | anEx |                 |
|          |        |                     | o | pr** |                 |
| **-      |        |                     | m |      |                 |
| Inf      |        |                     | m |      |                 |
| ormative |        |                     | o |      |                 |
| text**   |        |                     | n |      |                 |
|          |        |                     | N |      |                 |
|          |        |                     | a |      |                 |
|          |        |                     | m |      |                 |
|          |        |                     | e |      |                 |
|          |        |                     | * |      |                 |
|          |        |                     | * |      |                 |
+==========+========+=====================+===+======+=================+
| **ACE**  |        |                     |   |      |                 |
+----------+--------+---------------------+---+------+-----------------+
|          | 00 00  | "ACE_SP_PSID"       |   | PSID | All             |
|          | 00 08  |                     |   |      |                 |
|          | 00 01  |                     |   |      |                 |
|          | 00 E0  |                     |   |      |                 |
+----------+--------+---------------------+---+------+-----------------+

##### ACE_SP_PSID Access Control

Get access to ACE objects is as defined by \[3\].

### Performing Device Reversion

This section details the access control settings for using the PSID
authority to invoke the Revert method.

Support for this capability is Mandatory (M) if the PSID authority is
supported.

## Device Reversion Access Control Settings {#device-reversion-access-control-settings .Table}

<table>
<colgroup>
<col style="width: 16%" />
<col style="width: 3%" />
<col style="width: 9%" />
<col style="width: 5%" />
<col style="width: 3%" />
<col style="width: 4%" />
<col style="width: 8%" />
<col style="width: 2%" />
<col style="width: 4%" />
<col style="width: 4%" />
<col style="width: 6%" />
<col style="width: 4%" />
<col style="width: 4%" />
<col style="width: 4%" />
<col style="width: 4%" />
<col style="width: 3%" />
<col style="width: 6%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Table Association</p>
<p>- informative oly</p></th>
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
<td><blockquote>
<p> </p>
</blockquote></td>
<td> </td>
<td> </td>
<td> </td>
<td> </td>
<td> </td>
<td> </td>
<td> </td>
<td> </td>
<td> </td>
<td> </td>
<td> </td>
<td> </td>
<td> </td>
<td> </td>
<td> </td>
</tr>
<tr class="even">
<td></td>
<td></td>
<td><p>00 00 02 05</p>
<p>00 00 00 01</p></td>
<td>AdminSPObj</td>
<td>Revert</td>
<td></td>
<td>ACE_SP_SID, ACE_SP_PSID</td>
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

## Locking SP

This feature set requires no additions to the Locking SP.

## Additional SPs

This feature set requires no additional SPs.
