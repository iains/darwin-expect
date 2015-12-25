
expect - 5.45 with two modifications to make it more reliable on Darwin

1. Increase buffer sizes.
2. Fix the handling of openpty to be more robust w.r.t the tty names returned.
   This is significant on darwin9, and might affect other versions.

