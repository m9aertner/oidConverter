oidConverter
============

The OID converter is a handy little tool to convert ASN.1 OIDs from readable dotted
decimal notation to binary hexadecimal Distinguished Encoding Rules (DER) representation and vice versa.
If you're into x.509 certificates, this may be useful to you, too.

http://rtner.de/software/oid.html

# Synopsis

```
OID encoder/decoder - v1.3 - Matthias Gaertner 1999/2001 - Freeware
Usage:
 OID [-c|-C] [-o<outfile>] {-i<infile>|1.2.3.4}
   converts dotted form to ASCII HEX DER output.
 OID -x [-o<outfile>] {-i<infile>|hex-digits}
   decodes ASCII HEX DER and gives dotted form.
```

# Examples

The OID for [rsaSignatureWithripemd160](http://www.alvestrand.no/objectid/1.3.36.3.3.1.2.html) is 1.3.36.3.3.1.2 (just as an example).

```
Convert this to binary, hexadecimal output to stdout:
>oid 1.3.36.3.3.1.2
06 06 2B 24 03 03 01 02

Convert this to binary, "C" source output to stdout:
>oid -C 1.3.36.3.3.1.2
"\x06\x06\x2B\x24\x03\x03\x01\x02"

Convert this to binary, "C" array source output to stdout:
>oid -c 1.3.36.3.3.1.2
{ 0x06, 0x06, 0x2B, 0x24, 0x03, 0x03, 0x01, 0x02 }

Convert this to binary, write hex output to a file:
>oid -o r160oid.hex 1.3.36.3.3.1.2
This is similar to
>oid 1.3.36.3.3.1.2 > r160oid.hex

Use the decoder to get the dotted form back from the binary data:
>oid -x -i r160oid.hex
UNIVERSAL OID.1.3.36.3.3.1.2
```
