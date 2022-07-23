# handshake-root-zone

This is a copy of the DNS ROOT zone that includes all the names in the ICANN ROOT Zone
and all the names in the Handshake ROOT Zone **execpt** where a Handshake name clashes with
an ICANN name, in which case the ICANN name is retained in preferance to the Handshake Name.

It will be updated every hour at 25 mins past the hour.


It is signed using keys that I hold, if you want to do DNSSEC validation,
this is the `DS` you will need

    trust-anchors { . static-ds 7482 14 2 "313A31171A3D420E339EFD610CF967FA8F047C19ECAADE151DBF4D78870EEADF"; };

If you want a ready-to-run container that is a validating DNS Resolver
using this ROOT zone file, you can use this https://github.com/james-stevens/handshake-resolver

Due to file size limits imposed by github I've had to split the file into parts.
To recreate the entire ROOT zone into the file `ROOT.db`, just run this

      $ cat root_zone.* > ROOT.db

