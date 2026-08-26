## go-directory

The Go Directory project is working towards releasing an LDAP package suite written entirely in Go.

## Status

The go-directory suite as a whole is undergoing heavy development and is considered purely EXPERIMENTAL. Breaking changes are expected during this development phase. This suite, as a whole, is not yet suitable for production environments.

## License

All packages in this suite are released under the terms of the MIT license. See each repository's LICENSE file for details.

## Help Wanted

Community participation is greatly desired. This project is a gargantuan effort, and every bit helps. [Email me](mailto:jesse.coretta@icloud.com) if interested.

## Packages

The [go-directory](https://github.com/go-directory) suite is comprised of the following packages.

### go-directory/dsa

The **UNRELEASED** [go-directory/dsa](https://github.com/go-directory/dsa) package implements the directory system agent (an server). It incorporates [vjeantet/ldapserver](https://github.com/vjeantet/ldapserver) and [vjeantet/goldap/message](https://github.com/vjeantet/goldap) through _vendoring_. 

This package, though bulky in its own right, mainly serves as a conductor for all of the other packages (below) that are imported.

### go-directory/common

The [go-directory/common](https://github.com/go-directory/common) package provides fundamental "common elements", such as error constants, helpers. It is considered a LOW LEVEL package, in that it does not import any other suite package itself, while all other suite packages import it.

Over time, this package will grow in attempt to address [this issue](https://github.com/go-directory/.github/discussions/1).

### go-directory/config

The [go-directory/config](https://github.com/go-directory/config) package implements a `cn=config` abstraction layer for use by [go-directory/dsa](https://github.com/go-directory/dsa). It serves as the persistent configuration element of the DSA, controlling runtime behavior and many other facets.

### go-directory/dib

The [go-directory/dib](https://github.com/go-directory/dib) package implements the basis of the X.500 directory information base, from which directory information trees can emerge. The package supports both ephemeral (memory-based) and persistent (bolt DB file) storage backend options through simple transparent interfaces.

[boltdb/bolt](https://github.com/boltdb/bolt) is an integral imported component of this package.

### go-directory/dua

The [go-directory/dua](https://github.com//go-directory/dua) package implements the directory user agent (client). It is a (renamed) fork of [go-ldap/ldap](https://github.com/go-ldap/ldap).

WARNING: Users should NOT import this package for their own client purposes. This package exists solely as a component of the [go-directory/dsa](https://github.com/go-directory/dsa) package for communicating with other DSAs for the purposes of chaining, replication and other distribution-related functions. 

Users should continue using the original [go-ldap/ldap](https://github.com/go-ldap/ldap) package.

This package is slated to be radically modified in service to [this issue](https://github.com/go-directory/.github/discussions/1).

### go-directory/ldif

The [go-directory/ldif](https://github.com//go-directory/dua) package implements the LDAP Data Interchange Format. It is a fork of [go-ldap/ldif](https://github.com/go-ldap/ldif).

WARNING: Users should NOT import this package for their own purposes. This package exists solely as a component of the [go-directory/dsa](https://github.com/go-directory/dsa) package for backend purposes.

Users should continue using the original [go-ldap/ldif](https://github.com/go-ldap/ldif) package.

### go-directory/schema

The [go-directory/schema](https://github.com/go-directory/schema) package implements a complete [RFC 4512](https://www.rfc-editor.org/info/rfc4512/)-compliant schema definition store and parser. The package supports the concepts of _views_, in which an authoritative `*schema.SubschemaSubentry` instance can "seed" specific separate and independents `subschemaSubentry` contexts.

The package contains the `ldapSyntaxes`, `matchingRules`, `attributeTypes`, `matchingRuleUses`, `objectClasses`, `dITContentRules`, `nameForms` and `dITStructureRules` syntax definitions not included in the [go-directory/syntax](https://github.com/go-directory/syntax) package merely for reasons of logical separation.

The package also includes a package subdirectory at [go-directory/schema/indexer](https://github.com/go-directory/schema/tree/main/indexer). This package serves to "digest" an instance of `*schema.SubschemaSubentry` into a matrix of fast-lookup tables (maps).

### go-directory/syntax

The [go-directory/syntax](https://github.com/go-directory/syntax) package is a near-complete implementation of [RFC 4517](https://www.rfc-editor.org/info/rfc4517/). It contains myriad types and methods for most of the constructs defined in the aforementioned standard.

The main purpose of this package is to confirm a particular value complies with the associated syntax and, where applicable, to conduct EQUALITY, SUBSTR and ORDERING matching operations between so-called "real" values and an assertion value delivered by way of an LDAP search filter.

See the following subsections for more specialized syntaxes implemented from other standards or pseudo standards.

#### go-directory/syntax/aci

The [go-directory/syntax/aci](https://github.com/go-directory/syntax/tree/main/aci) package is a complete Netscape/Sun ACIv3 implementation. It incorporates the _ENTIRE_ specification into simple interrogative types produced by a reliable parser.

Though not a true standard, the ACIv3 specification has been adopted by nearly all directory server products on the market today. It is hardened and time tested.

This package does NOT include an ACDF (or, Access Control Decision Function). This functionality is intended to reside within the [go-directory/dsa](https://github.com/go-directory/dsa) package itself, as it will involve both an analysis of one or more rules and correlative queries to the storage backend.

#### go-directory/syntax/filter

The [go-directory/syntax/filter](https://github.com/go-directory/syntax/tree/main/filter) package is a complete interface-based [RFC 4515](https://www.rfc-editor.org/info/rfc4515/) implementation. It offers a fast, reliable parser which produces easly-traversable types for assertion processing.

An ASN.1 BER codec is not yet implemented in this package, but this effort is coming.

#### go-directory/syntax/subspec

The [go-directory/syntax/subspec](https://github.com/go-directory/syntax/tree/main/subspec) package is a complete interface-based [RFC 3672](https://www.rfc-editor.org/info/rfc3672/) `subtreeSpecification` implementation.

The package offers a fast, reliable parser which produces easily-traversable types for subtree processing. In many respects, it mirrors the design and functionality of [go-directory/syntax/filter](https://github.com/go-directory/syntax/tree/main/filter). This package will be pivotal in terms of subentries and collective attribute functionality implementation planned for later this year.

This package includes an ASN.1 DER codec.

#### go-directory/syntax/x509

The [go-directory/syntax/x509](https://github.com/go-directory/syntax/tree/main/x509) package is a near-complete [RFC 4523](https://www.rfc-editor.org/info/rfc4523/) implementation, offering syntaxes and matching rules for X.509 elements defined in the standard.

This package includes an ASN.1 DER codec.

## Members

  - Jesse Coretta (project lead, maintainer)

# Acknowledgements

  - Valere Jeantet (maintainer of [ldapserver](https://github.com/vjeantet/ldapserver) and [goldap](https://github.com/vjeantet/goldap))
  - The maintainers of [boltdb/bolt](https://github.com/boltdb/bolt)
  - The maintainers of [go-asn1-ber](https://github.com/go-asn1-ber/asn1-ber)
  - The maintainers of [go-ldap/ldap](https://github.com/go-ldap/ldap) and [go-ldap/ldif](https://github.com/go-ldap/ldif)
