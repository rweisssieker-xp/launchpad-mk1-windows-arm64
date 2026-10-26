# Launchpad MK1 Bridge for Windows ARM64

Experimental support for the **original Novation Launchpad MK1 / NOVLPD01** on **Windows ARM64** (USB **1235:000E**).

[Download the preview and SHA-256 checksum](https://github.com/rweisssieker-xp/launchpad-mk1-windows-arm64/releases)

This is a user-mode USB/MIDI bridge using the Microsoft WinUSB driver already included in Windows. No custom kernel driver, third-party driver installer, signing bypass or trust certificate is included in the recommended download.

## Current preview

**v0.1.0-preview** includes a self-contained ARM64 EXE, English/German setup instructions, checksums and .NET runtime license notices. No separate .NET installation is required.

- Original MK1 only; Mini/MK2/MK3/X/Pro and Windows x64 are outside this build's support scope.
- Administrator rights are needed for the initial device-specific inbox WinUSB binding.
- The application itself is not Authenticode-signed. Keep Windows security protections enabled.
- Tested on one device and one ARM64 Windows system. This is not a Novation-, Ableton- or Microsoft-certified driver.

## What works in the tested setup

- Device-specific Microsoft WinUSB binding, USB input and LED output.
- All 80 LED addresses exercised in red, green and amber, with visible output confirmed.
- All eight upper round controls emitted real signals; all eight right controls completed mute-on/off tests in the companion drumcomputer.
- MIDI running status and device-sized 8-byte reads, including partial-timeout regression checks.
- A dedicated Windows MIDI Services loopback pair passed real WinMM traffic in both directions.
- The original hardware's authentication response was received and forwarded after the four challenge CC messages.

## Ableton status

The MIDI port is **Launchpad MK1 Ableton**. Select it for both input and output of the **Launchpad** control surface in Live. **LP MK1 Bridge** is the internal side and should not be selected in the DAW.

**The final Session/Mixer setup inside Ableton has not yet been verified end to end.** Tested MIDI ports and the independent hardware authentication path do not constitute a completed Live control-surface acceptance test. The preview does not advertise full Ableton compatibility yet.

Keep the bridge running while using MIDI software. Only one process may own the physical Launchpad USB interface, so close or disconnect other direct-USB controller applications first.

## Getting started

Download and extract the ZIP from Releases. Follow its `README.md` or `QUICKSTART.de.md` for the read-only preflight, one-time administrator binding, device reconnection and LED test. The initial binding changes only the exact connected 1235:000E device and refuses to replace an existing non-WinUSB driver automatically.

`LaunchpadBridge.exe --self-test` runs software checks without hardware. There are no automatic telemetry or log uploads. Before posting an issue, redact personal paths, credentials and unique device identifiers from any diagnostics you choose to share.

## Project scope

This repository hosts the experimental download and its documentation separately from the synthesizer project. The unsigned kernel-driver prototype, private test logs, developer tools and third-party installers are not distributed. Publishing source code under an open-source license is a separate decision; this preview preparation does not select such a license.
