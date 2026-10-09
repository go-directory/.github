## go-directory

The Go Directory project is working towards releasing an LDAP package suite written entirely in Go.

## Status

This suite as a whole is undergoing ***heavy development*** and is considered purely EXPERIMENTAL. Breaking changes are guaranteed during this development phase. As such, it is not yet suitable for use in any production environment.

## License

All packages in this suite are released under the terms of the MIT license. See each repository's LICENSE file for details.

## Help Wanted

Community participation is greatly desired. This project is a gargantuan effort, and every bit helps. [Email me](mailto:jesse.coretta@icloud.com) if interested.

## Packages

The [go-directory](https://github.com/go-directory) suite is comprised of the following packages.

### go-directory/dsa

The **UNRELEASED** [go-directory/dsa](https://github.com/go-directory/dsa) package implements the directory system agent (an LDAP server). It incorporates [vjeantet/ldapserver](https://github.com/vjeantet/ldapserver) and [vjeantet/goldap/message](https://github.com/vjeantet/goldap) through _vendoring_. 

This package, though bulky in its own right, mainly serves as the importer and caller of all of the other packages (below).

### go-directory/common

The [go-directory/common](https://github.com/go-directory/common) package provides fundamental "common elements", such as error constants, helpers. It is considered a LOW LEVEL package, in that it does not import any other suite package itself, while all other suite packages import it.

Over time, this package will grow in attempt to address [this issue](https://github.com/go-directory/.github/discussions/1).

### go-directory/config

The [go-directory/config](https://github.com/go-directory/config) package implements a `cn=config` abstraction layer for use by [go-directory/dsa](https://github.com/go-directory/dsa). It serves as the persistent configuration element of the DSA, controlling runtime behavior and many other facets.

### go-directory/encoding

The [go-directory/encoding](https://github.com/go-directory/encoding) package contains various package subdirectories, each offering encoding/decoding features for various encoding standards such as ASN.1, VLQ and Percent.

### go-directory/dib

The [go-directory/dib](https://github.com/go-directory/dib) package implements the basis of the X.500 directory information base, from which directory information trees can emerge. The package supports both ephemeral (memory-based) and persistent (bolt DB file) storage backend options through simple transparent interfaces.

[boltdb/bolt](https://github.com/boltdb/bolt) is an integral imported component of this package. Though currently imported by the [Go Directory Project](https://github.com/go-directory), it may be vendored-in at some point in the near future for reasons of safety and continuity, given [boltdb/bolt](https://github.com/boltdb/bolt) is no longer maintained as of March 2019.

### go-directory/protocol

The [go-directory/protocol](https://github.com/go-directory/protocol) package is a near-complete implementation of [RFC 4511](https://www.rfc-editor.org/info/rfc4511/), and offers the fundamental types and methods needed for LDAP wire protocol activity. This package currently includes "request", "response" and "control" package subdirectories.

### go-directory/util

The [go-directory/util](https://github.com/go-directory/util) package provides miscellaneous utility packages. This package will grow over time.

### go-directory/schema

The [go-directory/schema](https://github.com/go-directory/schema) package implements a complete [RFC 4512](https://www.rfc-editor.org/info/rfc4512/)-compliant schema performance index map and parser. It is designed to exhibited the best performance possible.

The package contains the `ldapSyntaxes`, `matchingRules`, `attributeTypes`, `matchingRuleUses`, `objectClasses`, `dITContentRules`, `nameForms` and `dITStructureRules` syntax definitions not included in the [go-directory/syntax](https://github.com/go-directory/syntax) package merely for reasons of logical separation and avoidance of cyclical dependencies.

### go-directory/syntax

The [go-directory/syntax](https://github.com/go-directory/syntax) package is a near-complete implementation of [RFC 4517](https://www.rfc-editor.org/info/rfc4517/). It contains myriad types and methods for most of the constructs defined in the aforementioned standard.

The main purpose of this package is to confirm a particular value complies with the associated syntax and, where applicable, to conduct EQUALITY, SUBSTR and ORDERING matching operations between so-called "real" values and an assertion value delivered by way of an LDAP search filter.

#### go-directory/syntax/aci

The [go-directory/syntax/aci](https://github.com/go-directory/syntax/tree/main/aci) package is a complete Netscape/Sun ACIv3 implementation. It incorporates the _ENTIRE_ specification into simple interrogative types produced by a reliable parser. It is released as a _package subdirectory_ merely due to its massive size and complexity.

Though not a true standard, the ACIv3 specification has been adopted by nearly all directory server products on the market today. It is hardened, time-tested and battle-tested.

This package does NOT include an ACDF (an **A**ccess **C**ontrol **D**ecision _(making)_ **F**unction). This functionality is intended to reside within the [go-directory/dsa](https://github.com/go-directory/dsa) package itself, as it will involve both an analysis of one or more rules ***and*** correlative queries to the storage backend.

## Members

  - Jesse Coretta (SME, project lead, maintainer)

## Acknowledgements

This project would not be where it is today without the quality contributions by these individuals/teams:

  - Valere Jeantet (maintainer of [ldapserver](https://github.com/vjeantet/ldapserver) and [goldap](https://github.com/vjeantet/goldap))
  - The maintainers of [boltdb/bolt](https://github.com/boltdb/bolt)
  - The maintainers of [go-ldap/ldap](https://github.com/go-ldap/ldap) and [go-ldap/ldif](https://github.com/go-ldap/ldif)

Thank you. :)
