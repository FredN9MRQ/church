# Church Video Production System Overview

## System Purpose

This production system enables:
- Live camera switching with lyric overlays for streaming to Facebook/YouTube
- Clean ProPresenter backgrounds/slides on sanctuary screens
- Professional-quality video production for worship services

## Equipment Inventory

### Video Switchers
- **Blackmagic 1 M/E Production Switcher 4K** - Main switcher for camera/source switching
- **Blackmagic ATEM Mini (HDMI)** - Streaming encoder to castr.io

### Cameras
- 4x SDI cameras (connected to 1 M/E inputs 1-4)

### Computers
- **Windows 11 PC** - Runs ATEM Software Control for switcher programming/monitoring
- **Mac** - Runs ProPresenter software for presentation/lyrics
- **Blackmagic UltraStudio Monitor 3G** - Connects to Mac, provides dual SDI outputs

### Signal Conversion
- 1x SDI-to-HDMI converter (between 1 M/E Program output and ATEM Mini)

### Outputs
- Sanctuary screens (SDI input)
- Internet streaming via castr.io → Facebook/YouTube

## Signal Flow Diagram

```
┌─────────────────────────────────────────────────────────────────┐
│                         Mac + ProPresenter                       │
│                                                                   │
│  ┌─────────────────────────────────────────────────────────┐   │
│  │         UltraStudio Monitor 3G                           │   │
│  │  SDI Out 1: Backgrounds/Slides                          │   │
│  │  SDI Out 2: Lyrics Key (alpha/transparent background)   │   │
│  └─────────────────────────────────────────────────────────┘   │
└──────────────────┬────────────────────┬────────────────────────┘
                   │                     │
                   │ SDI                 │ SDI
                   │ (Backgrounds)       │ (Lyrics Key)
                   ▼                     ▼
        ┌──────────────────────────────────────────────┐
        │  Blackmagic 1 M/E Production Switcher 4K     │
        │                                               │
        │  Inputs:                                      │
        │    1-4: SDI Cameras                          │
        │    5: ProPresenter Backgrounds               │
        │    6: ProPresenter Lyrics Key                │
        │                                               │
        │  Program Bus: Camera switching               │
        │  DSK (Downstream Keyer): Lyrics overlay      │
        │                                               │
        │  Outputs:                                     │
        │    Program → Streaming                       │
        │    Aux 1 → Sanctuary Screens                 │
        └──────────┬────────────────────┬──────────────┘
                   │                     │
                   │ SDI                 │ SDI
                   │ (Program)           │ (Backgrounds only)
                   ▼                     ▼
        ┌──────────────────┐   ┌────────────────────┐
        │ SDI-to-HDMI      │   │ Sanctuary Screens  │
        │ Converter        │   │                    │
        └────────┬─────────┘   └────────────────────┘
                 │ HDMI
                 ▼
        ┌──────────────────┐
        │  ATEM Mini       │
        │  (HDMI)          │
        └────────┬─────────┘
                 │ USB/Ethernet
                 ▼
        ┌──────────────────┐
        │   castr.io       │
        │                  │
        ├──────────────────┤
        │  Facebook Live   │
        │  YouTube Live    │
        └──────────────────┘
```

## Network Architecture

### Video Signal Path

**For Streaming (with lyrics):**
1. Cameras (1-4) → 1 M/E inputs
2. 1 M/E Program bus switches between cameras
3. ProPresenter Lyrics Key → 1 M/E DSK → overlays on Program
4. Program output → SDI-to-HDMI converter
5. HDMI → ATEM Mini
6. ATEM Mini → castr.io → Facebook/YouTube

**For Sanctuary Screens (backgrounds only):**
1. ProPresenter Backgrounds → UltraStudio SDI 1
2. UltraStudio SDI 1 → 1 M/E Input 5
3. 1 M/E Aux 1 set to Input 5 (fixed)
4. Aux 1 output → Sanctuary Screens

## Input Assignments (1 M/E Switcher)

| Input # | Source | Cable Type | Usage |
|---------|--------|------------|-------|
| 1 | Camera 1 (wide shot) | SDI | Program switching |
| 2 | Camera 2 (pulpit/center) | SDI | Program switching |
| 3 | Camera 3 (choir/musicians) | SDI | Program switching |
| 4 | Camera 4 (detail/roving) | SDI | Program switching |
| 5 | ProPresenter Backgrounds | SDI | Aux output to screens |
| 6 | ProPresenter Lyrics Key | SDI | DSK overlay source |

## Output Assignments (1 M/E Switcher)

| Output | Destination | Cable Type | Content |
|--------|-------------|------------|---------|
| Program Out 1 | SDI-to-HDMI Converter | SDI | Cameras + Lyrics (streaming) |
| Aux 1 | Sanctuary Screens | SDI | ProPresenter backgrounds only |

## Key System Features

### Downstream Keyer (DSK)
- **Purpose:** Overlays lyrics on top of camera shots
- **Fill Source:** Input 6 (ProPresenter Lyrics Key)
- **Key Type:** Luma key or Linear key (depending on ProPresenter output)
- **Always On:** DSK should be enabled for Program output during services

### Auxiliary Output
- **Purpose:** Sends clean backgrounds to sanctuary screens
- **Source:** Fixed to Input 5 (ProPresenter Backgrounds)
- **Bypass:** Aux outputs bypass all switching/effects - shows input directly

## Streaming Configuration

### ATEM Mini Settings
- **Input 1:** Receives Program output from 1 M/E (cameras + lyrics)
- **Output:** USB or Ethernet to castr.io streaming service
- **Resolution:** 1080p59.94 or 1080p60 (match 1 M/E output format)

### castr.io Configuration
- Receives stream from ATEM Mini
- Restreams simultaneously to:
  - Facebook Live
  - YouTube Live

## ProPresenter Configuration

### UltraStudio Output 1 - Backgrounds
- **Content:** Slides and backgrounds only
- **Layers:** Background/media layers enabled, text layers disabled
- **Destination:** 1 M/E Input 5 → Sanctuary screens

### UltraStudio Output 2 - Lyrics Key
- **Content:** Text/lyrics only
- **Layers:** Text layers enabled, background layers disabled
- **Output Mode:** Alpha key (transparent background)
- **Destination:** 1 M/E Input 6 → DSK overlay

## Audio Routing

*Note: This document covers video routing only. Audio from cameras, microphones, and ProPresenter should be mixed separately and fed to:*
- Sanctuary sound system
- ATEM Mini audio input (for streaming)
- Ensure audio is embedded in SDI if using embedded audio, or use separate audio mixer

## Backup/Redundancy Considerations

- **Camera failure:** Switch to another camera or ProPresenter backgrounds
- **ProPresenter crash:** Have backup slides ready, can show camera-only feed
- **Internet failure:** Service continues normally (only streaming affected)
- **1 M/E failure:** ATEM Mini can be used as backup switcher (limited inputs)

## System State During Service

### Normal Operation
- **1 M/E Program bus:** Switching between cameras (Inputs 1-4)
- **DSK:** On Air (overlaying lyrics)
- **Aux 1:** Fixed to Input 5 (backgrounds to screens)
- **ATEM Mini:** Receiving Program output, streaming to castr.io
- **Windows PC:** Running ATEM Software Control for monitoring/control
- **Mac:** Running ProPresenter for presentation content

### Pre-Service Setup
- All equipment powered on 30 minutes before service
- Windows PC running ATEM Software Control
- Mac running ProPresenter with service playlist loaded
- ATEM Mini connected to castr.io
- Test camera switching and lyrics overlay
- Verify sanctuary screens showing ProPresenter backgrounds

### Post-Service Teardown
- Stop castr.io streaming
- Save any custom macros or settings
- Power down in reverse order (computers last)

## Reference Documents

- **UPGRADE-GUIDE.md** - How to implement this system from current setup
- **MACRO-GUIDE.md** - Programming macros for common operations
- **OPERATIONS-MANUAL.md** - Day-to-day operation procedures

## Support Contacts

**Equipment Manufacturers:**
- Blackmagic Design Support: https://www.blackmagicdesign.com/support
- ProPresenter Support: https://learn.renewedvision.com
- castr.io Support: https://castr.io/support

**System Documentation Version:** 1.0
**Last Updated:** 2026-01-07
