## go-directory

The [go-directory](https://github.com/go-directory) suite is comprised of the following packages

  - [go-directory/dsa](https://github.com/go-directory/dsa); directory system agent (server) and listener, operation handlers
    - Incorporates [vjeantet/ldapserver](https://github.com/vjeantet/ldapserver) and [vjeantet/goldap/message](https://github.com/vjeantet/goldap)
  - [go-directory/dib](https://github.com/go-directory/dib); directory information base/tree; ephemeral and persistent storage backend options
    - Imports [boltdb/bolt](https://github.com/boltdb/bolt)
  - [go-directory/dua](https://github.com//go-directory/dua); directory user agent (client)
    - Fork of [go-ldap/ldap](https://github.com/go-ldap/ldap)
  - [go-directory/ldif](https://github.com//go-directory/ldif); LDAP Data Interchange Format
    - Fork of [go-ldap/ldif](https://github.com/go-ldap/ldif)
  - [go-directory/config](https://github.com/go-directory/config); `cn=config` configuration abstraction for use by [go-directory/dsa](https://github.com/go-directory/dsa)
  - [go-directory/schema](https://github.com/go-directory/schema); complete schema definition store, parser
  - [go-directory/syntax](https://github.com/go-directory/syntax); syntax checking and matching rule assertions
  - [go-directory/common](https://github.com/go-directory/common); common elements -- error constants, helpers -- imported by any of the above

# Status

The go-directory suite as a whole is undergoing heavy development and is considered purely EXPERIMENTAL. Breaking changes are expected during this development phase. This suite, as a whole, is not yet suitable for production environments.

# License

All packages in this suite are released under the terms of the MIT license. See each repository's LICENSE file for details.

# Help Wanted

Community participation is greatly desired. This project is a gargantuan effort, and every bit helps.

# Members

  - Jesse Coretta (project lead, maintainer of [go-directory/syntax](https://github.com/go-directory/syntax), [go-directory/schema](https://github.com/go-directory/schema), [go-directory/config](https://github.com/go-directory/config), [go-directory/common](https://github.com/go-directory/common), [go-directory/dib](https://github.com/go-directory/dib) and [go-directory/dsa](https://github.com/go-directory/dsa))

# Acknowledgements

  - Valere Jeantet (maintainer of [ldapserver](https://github.com/vjeantet/ldapserver) and [goldap](https://github.com/vjeantet/goldap))
  - The maintainers of [boltdb/bolt](https://github.com/boltdb/bolt)
  - The maintainers of [go-asn1-ber](https://github.com/go-asn1-ber/asn1-ber)
  - The maintainers of [go-ldap/ldap](https://github.com/go-ldap/ldap) and [go-ldap/ldif](https://github.com/go-ldap/ldif)
