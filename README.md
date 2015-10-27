Lelei: XML -> WireShark Generic Dissector
=========================================

### Disclaimer ###
[![Build Status](https://travis-ci.org/alfateam123/lelei.svg?branch=master)](https://travis-ci.org/alfateam123/lelei)

PLEASE NOTE THAT THIS PROJECT IS NOT FULLY FUNCTIONAL, SO USE IT AT YOUR OWN RISK. CONSIDER IT TO BE INCOMPLET AND INKORRECT. YOU HAVE BEEN WARNED.

### What is that? ###

Lelei is a [cute sorceress](http://gate-thus-the-jsdf-fought-there.wikia.com/wiki/Lelei_La_Lalena)... no, wait, nevermind.
Lelei is an automatic WireShark Generic Dissector that, starting from an XML description,
generates the `.fdesc` and `.wsgd` files you need to perform network analysis.

Please note that Lelei is not a validating generator: it means it may generate generic
dissectors that violate the WSGD grammar or context (using basic types incorrectly, 
passing wrong values to transform specifications, ...). If you have a problem,
please open an issue and we'll help you sorting it out.

### How to use ###

1. Define your packet structure in XML
2. `lelei rory.xml rory`
3. Copy the resulting `rory.fdesc` and `rory.wsgd` to your Wireshark folders
4. Open Wireshark and analyze your net traffic!

### Yet another generator, I see... ###

I don't know if Wireshark offers the same functionality, or other programs that do
the same thing.
If you're interested in alternatives, you may use [Csjark](https://csjark.readthedocs.org/en/latest/),
which translates C structures to Lua-based dissectors.

### Important things: state of work ###

Does it write things yet? **Yes**.

How much of the grammar has been implemented?  
This is a list of the thing that will be implemented

- Basic Types
  - [x] spare
  - [x] char, schar, uchar
  - [x] bool1, bool8, bool16, bool32
  - [x]  int2 ->  int32,  int40,  int48, int64
  - [x] uint1 -> uint32, uint40, uint48
  - [x] float32, float64
  - [x] string, string(size)
  - [x] string_nl, string_nl(size)
  - [x] raw(size)
  - [x] padding_bits [type = `padding`]

- [x] Struct
- [x] Local byte order spec
- [ ] Enum
- [ ] Transform spec
- [x] Arrays
- [ ] Multiple structures support

This is a list of things that will be implemented,
but not in the nearest future.

- [ ] Display spec
- [ ] Constraint spec
- [ ] No Statement value

The rest of the specification may come even later, if it's ever implemented.
If you really need it _now_, please feel free to contribute with a Pull Request
via Github.
