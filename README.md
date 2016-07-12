### Charrua DHCP core library.

[charrua-core](http://www.github.com/haesbaert/charrua-core) is an
_ISC-licensed_ DHCP library implementation in ocaml.

[![docs](https://img.shields.io/badge/doc-online-blue.svg)](http://haesbaert.github.io/charrua-core/api)
[![Build Status](https://travis-ci.org/haesbaert/charrua-core.png)](https://travis-ci.org/haesbaert/charrua-core)

It provides basically two modules, a `Dhcp` responsible for parsing and
constructing DHCP messages and a `Dhcp_server` module used for constructing DHCP
servers.

[charrua-unix](http://www.github.com/haesbaert/charrua-unix) is a Unix DHCP
server based on charrua-core.

[mirage](https://github.com/mirage/mirage-skeleton/tree/master/dhcp) is a Mirage
DHCP unikernel server based on charrua-core.

You can browse the API for [charrua-core](http://www.github.com/haesbaert/charrua-core) at
http://haesbaert.github.io/charrua-core/api

#### Features

* Dhcp_server supports a stripped down ISC dhcpd.conf, so you can probably just
  use your old dhcpd.conf, it also supports manual configuration building in
  ocaml.
* Logic/sequencing is agnostic of IO and platform, so it can run on Unix as a
  process, as a Mirage unikernel or anything else.
* Dhcp_wire provides marshalling and unmarshalling utilities for DHCP, it is the
  base for Dhcp_server.
* All DHCP options are supported at the time of this writing.
* Code is purely applicative.
* It's in ocaml, so it's pretty cool.

The name `charrua` is a reference to the, now extinct, semi-nomadic people of
southern South America.

This project became one of the [Mirage Pioneer]
(https://github.com/mirage/mirage-www/wiki/Pioneer-Projects) projects.

The master branch depends on upcoming mirage 2.9 at this point, if you want to
use it, you'll have to add the mirage development branch to opam:

```
opam remote add mirage-dev https://github.com/mirage/mirage-dev.git
opam update
opam upgrade
```