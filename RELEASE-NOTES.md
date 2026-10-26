# v0.1.0-preview — Launchpad MK1 Bridge, Windows ARM64

First experimental download for original NOVLPD01 hardware (USB 1235:000E).

Includes a self-contained ARM64 user-mode EXE, inbox WinUSB binding helper, endpoint-aware USB input, a three-color all-LED test, and an optional bidirectional Windows MIDI Services loopback for MIDI software.

Hardware LEDs and button input were exercised on one device. Native loopback traffic passed both ways, including the original Launchpad's authentication response. Full Ableton control-surface configuration remains pending, so Session/Mixer support is not yet advertised as fully verified.

No custom kernel driver or signing bypass is distributed. Application code signing is still pending. Windows ARM64 only; other Launchpad models and Windows x64 are outside this release's test scope.

The archive excludes local backups, device logs, personal paths in documentation, developer tools, third-party installers, PDBs and the unsigned kernel-driver prototype. .NET runtime license and third-party notices accompany the self-contained runtime.
