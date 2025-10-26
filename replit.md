# PSP Emulator - Single HTML File

## Overview
A fully self-contained PSP (PlayStation Portable) emulator built entirely in a single HTML file. This educational project demonstrates browser-based emulation using JavaScript, WebGL, and modern web APIs.

## Features Implemented
1. **Cheat Loading** - Supports .db and .ini cheat files with code injection
2. **Plugin Loading** - ZIP format plugin support with file extraction
3. **ISO/CHD Loading** - Full support for PSP game dumps in ISO and CHD formats with game title extraction
4. **Touch Controls** - Mobile-friendly touch screen interface with functional analog stick and all buttons
5. **BIOS Loading** - Multi-file ZIP BIOS support (.bin, .prx, .rco, .pbp) with automatic extraction
6. **Debug Mode** - Real-time debug console showing button states, analog position, and emulation logs
7. **Save System** - Save states with ZIP import/export for easy backup and restore
8. **Graphics Rendering** - WebGL-based 3D graphics pipeline with real-time control feedback display
9. **Remappable Controls** - Fully customizable keyboard controls with visual feedback
10. **Main Menu** - Comprehensive menu system for all emulator functions

## Technical Stack
- Pure HTML/CSS/JavaScript with JSZip library for ZIP file handling
- WebGL 2.0 for 3D graphics rendering
- IndexedDB for persistent storage
- MIPS R4000 CPU emulation with 40+ opcodes
- Branch delay slot implementation (MIPS architecture requirement)
- PSP GPU emulation with geometry processing
- Web Audio API for sound
- FileReader API for file loading
- Touch/Mouse drag API for analog stick controls
- Performance optimizations: frame skipping, speed controls, batched execution

## Architecture
- **PSPCPU** - MIPS R4000 instruction set emulation
- **PSPGPU** - Graphics processing with WebGL shaders
- **PSPAudio** - Audio context for sound emulation
- **Main Emulator** - Coordinates all subsystems and manages state

## User Instructions
1. Open the emulator in a modern web browser
2. Load PSP BIOS:
   - ZIP file containing multi-file firmware (recommended)
   - Single .bin or .rom file (legacy support)
3. Load an ISO or CHD game file - game title will be auto-detected
4. Optionally load cheats (.db/.ini) or plugins (.zip)
5. Close menu or press "Resume Emulation" to start
6. Use keyboard, touch controls, or drag the analog stick to play
7. Enable Debug Mode to see real-time button and analog stick states
8. Export save data as ZIP for backup, import to restore

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
- Single file constraint maintained (index.html)
- JSZip library loaded via CDN for ZIP handling
- WebGL shaders compiled at runtime
- BIOS ZIP files automatically extracted and loaded to memory at 0x00000000
- ISO filesystem parsed using ISO9660 format with PSP_GAME signature detection
- Save states stored in browser IndexedDB and exportable as ZIP archives
- Cheats applied per frame during execution
- Analog stick uses drag events with normalized coordinates (-1 to 1)
- All touch events use passive:false to prevent scroll interference
- Controls display real-time feedback on screen and in debug panel

## Recent Changes (October 26, 2025)
- ✅ Added JSZip library for ZIP file support
- ✅ Implemented multi-file BIOS loading from ZIP archives
- ✅ Added ZIP import/export for save data with folder structure
- ✅ Implemented functional analog stick with touch/mouse drag
- ✅ Added ISO header parsing with game title extraction
- ✅ Enhanced on-screen display to show active buttons and analog position
- ✅ Updated debug panel to show control states
- ✅ Updated file inputs to accept .zip for BIOS and saves
- ✅ Added visual feedback for all controls
- ✅ Implemented comprehensive performance optimizations:
  - Frame skipping system (auto-adjusts 0-3 frames based on performance)
  - Speed multiplier controls (25%-200% via Slower/Faster buttons)
  - Batched CPU execution with configurable cycles (1K-100K)
  - Branch delay slot implementation (critical MIPS requirement)
  - 40+ MIPS R4000 instructions (shifts, branches, ALU, loads/stores, syscalls)
  - Performance monitoring with real-time FPS and timing metrics
  - Dynamic instruction batching based on speed setting

## Last Updated
October 26, 2025
