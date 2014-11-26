===========
Description
===========

The SALB system is a software framework for speech synthesis 
using HMM based voice models built by HTS (http://hts.sp.nitech.ac.jp/).

The package currently includes:

A C++ framework that abstracts the backend functionality and
provides a SAPI5 interface, a command line interface 
and a C++ API.

Backend functionality is provided by 
- an internal text analysis module for (Austrian) German,
- flite as text analysis module for English and
- hts_engine for parameter generation/synthesis.
(see COPYING for information on 3rd party libraries)

Also included are an Austrian German male and a Scottish English female voice model.

For information on how to build the system see BUILD.

To train your own voices, you can use the demo packages on
http://hts.sp.nitech.ac.jp/
This package currently includes hts_engine 1.08 for synthesis, so 
you need a (.htsvoice)-model compatible with this version.


===================
Directory structure
===================

api
---
APIs for other language (e.g. python).

cli
---
Command-Line-Interface.

data
----
Voice models and text rules provided with the system.

sapi
----
SAPI5 interface.

engine/text
-----------
Text analysis modules.
Currently flite and an internal module.

engine/synthesis
----------------
Synthesis modules.
Currently hts_engine.

engine/manager
--------------
TTS engine coordinating text analysis and synthesis.
Used as an interface for frontends (sapi, cli, api).


======================
Coding style guideline
======================

- Code formatting is done using astyle (http://astyle.sourceforge.net/) using the provided astyle config file (astyle.config)
- Naming conventions for classes and methods:
  Classes and methods in CamelCase with first character uppercase (class FooBar { void GetStuff(); };)
  Member variables camelCase with first character lowercase (int someVal;)
  Functions in lowercase with underscores (void get_stuff();)
- no "using"-directives in header files
