## go-directory

The [go-directory](https://github.com/go-directory) suite is comprised of the following packages

  - [go-directory/dsa](https://github.com/go-directory/dsa); directory system agent (server) and listener, operation handlers
    - Incorporates [vjeantet/ldapserver](https://github.com/vjeantet/ldapserver) and [vjeantet/goldap/message](https://github.com/vjeantet/goldap)
  - [go-directory/dib](https://github.com/go-directory/dib); directory information base/tree; ephemeral and persistent storage backend options
    - Imports [boltdb/bolt](https://github.com/boltdb/bolt)
  - [go-directory/dua](https://github.com//go-directory/dua); directory user agent (client)
    - Fork of [go-ldap/ldap](https://github.com/go-ldap/ldap)
  - [go-directory/config](https://github.com/go-directory/config); `cn=config` configuration abstraction for use by [go-directory/dsa](https://github.com/go-directory/dsa)
  - [go-directory/schema](https://github.com/go-directory/schema); complete schema definition store, parser
  - [go-directory/syntax](https://github.com/go-directory/syntax); syntax checking and matching rule assertions
  - [go-directory/common](https://github.com/go-directory/common); common elements -- error constants, helpers -- imported by any of the above
