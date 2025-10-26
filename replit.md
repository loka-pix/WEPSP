# PSP Emulator - Single HTML File

## Overview
A fully self-contained PSP (PlayStation Portable) emulator built entirely in a single HTML file. This educational project demonstrates browser-based emulation using JavaScript, WebGL, and modern web APIs.

## Features Implemented
1. **Cheat Loading** - Supports .db and .ini cheat files with code injection
2. **Plugin Loading** - ZIP format plugin support with file extraction
3. **ISO/CHD Loading** - Full support for PSP game dumps in ISO and CHD formats
4. **Touch Controls** - Mobile-friendly touch screen interface with landscape/fullscreen modes
5. **BIOS Loading** - PSP BIOS support with HLE (High-Level Emulation) fallback
6. **Debug Mode** - Real-time debug console with emulation logs
7. **Save System** - Save states, save data export/import using IndexedDB
8. **Graphics Rendering** - WebGL-based 3D graphics pipeline with shader support
9. **Remappable Controls** - Fully customizable keyboard controls
10. **Main Menu** - Comprehensive menu system for all emulator functions

## Technical Stack
- Pure HTML/CSS/JavaScript (no external dependencies)
- WebGL 2.0 for 3D graphics rendering
- IndexedDB for persistent storage
- MIPS R4000 CPU emulation
- PSP GPU emulation with geometry processing
- Web Audio API for sound
- FileReader API for file loading

## Architecture
- **PSPCPU** - MIPS R4000 instruction set emulation
- **PSPGPU** - Graphics processing with WebGL shaders
- **PSPAudio** - Audio context for sound emulation
- **Main Emulator** - Coordinates all subsystems and manages state

## User Instructions
1. Open `psp-emulator.html` in a modern web browser
2. Load PSP BIOS (optional - HLE mode available)
3. Load an ISO or CHD game file
4. Optionally load cheats or plugins
5. Click "Start" to begin emulation
6. Use keyboard or touch controls to play

## Controls (Default)
- Arrow Keys: D-Pad
- X: Cross (×)
- Z: Circle (○)
- A: Square (□)
- S: Triangle (△)
- Q: L Shoulder
- W: R Shoulder
- Enter: Start
- Right Shift: Select

All controls are remappable through the Controls menu.

## Development Notes
- Single file constraint maintained
- All code embedded in HTML
- WebGL shaders compiled at runtime
- BIOS files loaded into memory at 0x00000000
- ISO filesystem parsed using ISO9660 format
- Save states stored in browser IndexedDB
- Cheats applied per frame during execution

## Last Updated
October 26, 2025
