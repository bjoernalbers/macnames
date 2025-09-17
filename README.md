# macnames - Get or set all macOS device names at once

Your Mac has three different names:

1. `ComputerName`: The user-friendly name for the system.
2. `LocalHostName`: The local (Bonjour) host name.
3. `HostName`: The name associated with `hostname(1)` and your terminal prompt.

This shell script allows to get/set these names all at once using `scutil`.
