
expect - 5.45 with two modifications to make it more reliable on Darwin

1. Increase buffer sizes.
2. Fix the handling of openpty to be more robust w.r.t the tty names returned.
   This is significant on darwin9, and might affect other versions.

BUILD
=====

I find it useful to build a completely statically-linked expect exe.
Using tcl-8.6 is a good idea, since that has a better stack profile.

tcl config : "--disable-shared"

expect config :
export LDFLAGS="-Wl,-L,<path to tcl build>,-ltclstubN.M,-framework,CoreFoundation,-lz"

Changes
=======

darwin-expect-5-45r1:

Further revised handling of openpty() slave name returns.

