* Document that the 'instance Storable a => Store (SV.Vector a)' means that
  every Store instance must be compatible with its Storable.

* Consider how to handle exceptions for pure encode / decode functions

* Benchmark generics instance vs TH

* Look at core for generics instances

* Benchmark whether throwing exceptions is faster than plumbing 'Either String'

* Have 'deriveManyStoreFromStorable' take both a whitelist and blacklist. This
  will allow the TH to notify the user when there's some new 'Store' type that
  could have an instance. This allows them to make a conscious decision about
  it.

* Mention that we're not concerned with alignment issues.  Have a test suite
  show that the base Store instances don't care about alignment on x86 / 64

* Sanity check length values peeked (and throw errors)

* Export utilities for types based on bytearray / foreignptr / ptr / etc

* Move test utilities into an external package

* Why is Bool taking up 4 bytes?

* Instance for PV.Vector

* Storable instance in Base for Ratio throws errors when denominator is 0.
  Fixed via custom instance, but a patch to base should maybe be made.