# Church Video Production Documentation

Complete documentation for the Blackmagic-based video production system.

## System Overview

This system separates ProPresenter content into two streams:
- **Sanctuary Screens:** Clean backgrounds/slides (no lyrics)
- **Live Stream:** Camera switching with lyrics overlay

## Documentation Files

### 1. OVERVIEW.md
**Start here** - Understand the complete system architecture, signal flow, and equipment inventory.

**Read this if you:**
- Are new to the system
- Need to understand how everything connects
- Want to see the big picture before diving into details

### 2. UPGRADE-GUIDE.md
**Step-by-step implementation** of the new system configuration.

**Use this when:**
- Installing the UltraStudio Monitor 3G
- Configuring ProPresenter dual outputs
- Setting up the 1 M/E switcher for the new routing
- First-time system setup

**Time required:** 2-3 hours

### 3. MACRO-GUIDE.md
**Programming macros** for automated switcher operations.

**Use this to:**
- Create one-button operations for common tasks
- Automate camera switching with lyrics
- Reduce operator errors
- Speed up service production

**Recommended macros included:**
- Pre-service setup
- Song start (with lyrics)
- Sermon start (no lyrics)
- Video playback
- Emergency procedures

### 4. OPERATIONS-MANUAL.md
**Day-to-day operation** procedures for running services.

**Use this for:**
- Pre-service setup checklist
- During-service switching procedures
- Troubleshooting common issues
- Training new operators
- Post-service shutdown

**Essential for all operators** - print and keep at operator station.

## Quick Start

### For First-Time Setup
1. Read **OVERVIEW.md** - understand the system
2. Follow **UPGRADE-GUIDE.md** - implement the configuration
3. Program macros using **MACRO-GUIDE.md** - automate operations
4. Train operators with **OPERATIONS-MANUAL.md** - run services

### For New Operators
1. Read **OVERVIEW.md** - learn system architecture
2. Review **OPERATIONS-MANUAL.md** - understand procedures
3. Practice with macros from **MACRO-GUIDE.md**
4. Shadow experienced operator during live service

### For Regular Operation
- **OPERATIONS-MANUAL.md** - your daily reference
- **MACRO-GUIDE.md** - when creating new automated operations
- **OVERVIEW.md** - when troubleshooting or understanding signal flow

## System Requirements

### Hardware
- Blackmagic 1 M/E Production Switcher 4K
- Blackmagic ATEM Mini (HDMI, first generation)
- **Blackmagic UltraStudio Monitor 3G** (to be purchased ~$145)
- Mac running ProPresenter
- Windows 11 PC for ATEM Software Control
- 4x SDI cameras
- SDI-to-HDMI converter
- SDI cables (2x additional for UltraStudio outputs)

### Software
- **On Mac:** ProPresenter 6 or 7, Blackmagic Desktop Video drivers (for UltraStudio)
- **On Windows 11 PC:** ATEM Software Control (for switcher programming/control)
- **Streaming:** castr.io account

## Key Concepts

### Dual ProPresenter Outputs
ProPresenter sends two separate feeds:
- **Output 1 (UltraStudio SDI 1):** Backgrounds only → Sanctuary screens
- **Output 2 (UltraStudio SDI 2):** Lyrics key (alpha) → Stream overlay

### Downstream Keyer (DSK)
Overlays lyrics on top of camera shots for streaming:
- **On Air:** Lyrics visible on stream
- **Off Air:** Camera only (no lyrics)

### Auxiliary Output
Dedicated output on 1 M/E that shows one input directly:
- **Aux 1:** Always shows ProPresenter backgrounds → Sanctuary screens
- Bypasses all switching and effects

## Typical Service Flow

```
Pre-Service → Songs (cameras + lyrics) → Sermon (camera, no lyrics) → Closing Song (cameras + lyrics)
     ↓              ↓                            ↓                              ↓
   Input 5     Cameras 1-4                   Camera 2                      Cameras 1-4
   DSK Off      DSK On                        DSK Off                        DSK On
```

## Common Questions

**Q: How do I get lyrics on the stream but not on screens?**
A: ProPresenter sends backgrounds to screens (via Aux output) and lyrics key to DSK (overlays on Program output).

**Q: How do I switch cameras during songs without losing lyrics?**
A: Just switch cameras - DSK stays enabled and overlays lyrics on whatever camera is on Program.

**Q: What if sanctuary screens start showing lyrics?**
A: Check ProPresenter "Sanctuary Backgrounds" output - ensure text layers are disabled.

**Q: How do I show sermon notes on both stream and screens?**
A: Switch Program to Input 5 (ProPresenter Backgrounds) with DSK off. Use "Sermon - Notes" macro.

**Q: What's the emergency procedure?**
A: Execute "EMERGENCY - Black Screen" macro or press Black + CUT on switcher.

## Troubleshooting Quick Reference

| Problem | Solution |
|---------|----------|
| Screens show lyrics | Check ProPresenter output layers |
| No lyrics on stream | Enable DSK 1 On Air |
| No camera image | Check camera power and SDI cables |
| Stream offline | Restart castr.io, verify internet |
| Wrong content on screens | Verify Aux 1 = Input 5 |

See **OPERATIONS-MANUAL.md** for detailed troubleshooting.

## Training Resources

**Included in this documentation:**
- Complete system overview
- Step-by-step upgrade guide
- Macro programming tutorial
- Daily operations procedures

**External resources:**
- Blackmagic ATEM Training: https://www.blackmagicdesign.com/products/atem/training
- ProPresenter Learn: https://learn.renewedvision.com
- Blackmagic Forum: https://forum.blackmagicdesign.com

## Support

**For system-specific questions:**
- Consult the relevant documentation file
- Review troubleshooting sections
- Contact technical director

**For equipment support:**
- Blackmagic: https://www.blackmagicdesign.com/support
- ProPresenter: support@renewedvision.com
- castr.io: https://castr.io/support

## Document Version Control

- **Version:** 1.0
- **Created:** 2026-01-07
- **Last Updated:** 2026-01-07
- **Next Review:** _______________

## Contributing

**To update documentation:**
1. Make changes to relevant .md file
2. Update "Last Updated" date
3. Note changes in version history below
4. Distribute to all operators

### Version History
- **1.0 (2026-01-07):** Initial documentation created

---

## File Structure

```
church-video-production-docs/
├── README.md                  (this file - start here)
├── OVERVIEW.md               (system architecture and signal flow)
├── UPGRADE-GUIDE.md          (step-by-step implementation)
├── MACRO-GUIDE.md            (programming ATEM macros)
└── OPERATIONS-MANUAL.md      (daily operation procedures)
```

**Print and keep** OPERATIONS-MANUAL.md at operator station for quick reference during services.

---

*Generated for [Church Name] video production system*
*For questions or updates, contact: [Technical Director Name/Email]*
