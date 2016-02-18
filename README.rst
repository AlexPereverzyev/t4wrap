
T4Wrap
======

The T4 template provides an easy way to generate C# class proxy, regardless
whether lazy you just want a proxy to customize behavior or you want some 
framework class covered with your custom interface for better unit testing. 

What it does
------------

The T4 template does a few things:

- generates namespace for proxy
- generates class proxy, adding `virtual` where possible 
- generates proxy interface and implements all wrapped class’s top level 
  interfaces explicitly
- generates simple class factory and its interface

What is supported
-----------------

Here is a list of what's supported (not mentioned is not tested):

- constructors, methods
- properties and indexers
- events and event accessors
- top level explicit interfaces
- arrays
- `params`, `out` and `ref` arguments
- generics with exact types (no pure generics)
- nested types

Note: there is no usings or pretty alignment - I don't care as long as 
machine can read it (use _Ctrl+K-D_ if you really want to work with the code).

How to use it
=============

Finally, this is the best known way to use the template:

- Rename template file as you feel necessary. Better use target proxy class 
  name for this.
- Set target type and namespace in *NAMES* section of the template.
- Make sure type assembly is referenced by _assembly_ directive.
- Optionally (at your own risk), adjust metadata selectors in *SELECTORS* 
  section of the template.
- To tweak template, scroll down to the bottom. This is REAL stuff, so don't 
  ask why it's written that way. 

Testing
=======

Template is written and debugged in Visual Studio 2013, tested with 
`String`, `SortedDictionary<T,T>`, `SQLCommand` and a few other classes.
