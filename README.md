# puppet-module-bind

Manage bind9. This module's approach is to manage the configuration of bind9
while not managing the data in the actual zones, which is up to you. Recommend
keeping zone data in another repo and having a process sync that data to your
bind servers.

===

### Table of Contents
1. [Compatibility](#compatibility)
1. [Parameters](#class-bind-parameters)
1. [Examples](#sample-usage)

===

# Compatibility

This module has been tested to work on the following systems with Puppet
versions v3, v3 with future parser and v4 with Ruby versions 1.8.7 (Puppet v3
only) and 2.1.0.

 * EL 6

===

# class bind parameters

param
-----
Enable greatness

- *Types*: boolean and stringified boolean

- *Default*: true

controls
--------
Specifies information for controls lines in the named.conf. The key is the IP
address or `'*'`. The hash has subkeys that must include 'port' (string),
'allows' (array) and optionally 'keys' (array).

```
# example

bind::controls:
  '*':
    port: '953'
    allows:
      - '127.0.0.1'
    keys:
      - 'rndc-key'
```

- *Types*: hash or undef

- *Default*: undef



# define bind::acl parameters

===

# sample usage
