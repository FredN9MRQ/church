# Video Production System Upgrade Guide

## Overview

This guide walks through upgrading your current video production system to separate ProPresenter backgrounds (for sanctuary screens) from the camera feed with lyrics overlay (for streaming).

## Pre-Upgrade Checklist

### Equipment to Purchase

- [ ] **Blackmagic UltraStudio Monitor 3G** (~$145)
  - Provides dual SDI outputs from Mac
  - Part #: BDLKULSDMINHD3G
  - Buy from: B&H Photo, Amazon, or Blackmagic authorized dealer

### Tools Needed

- [ ] Screwdriver (if mounting UltraStudio)
- [ ] Label maker or labels for cables
- [ ] Laptop with ATEM Software Control installed
- [ ] Spare SDI cables (2x, appropriate lengths for your rack)
- [ ] Thunderbolt cable (for UltraStudio to Mac connection)

### Before You Begin

- [ ] **Schedule upgrade during non-service time** (weekday recommended)
- [ ] **Allow 2-3 hours** for installation and testing
- [ ] **Back up ProPresenter presentations** to external drive (on Mac)
- [ ] **Take photos** of current cable connections for reference
- [ ] **Download latest drivers:**
  - Blackmagic Desktop Video (for UltraStudio on Mac): https://www.blackmagicdesign.com/support/
  - ATEM Software Control (for 1 M/E on Windows PC): https://www.blackmagicdesign.com/support/
- [ ] **Have volunteer help** for testing during setup
- [ ] **Ensure Windows PC has network/USB connection to 1 M/E switcher**

## Current System Documentation

### Current Signal Flow
```
ProPresenter (Mac) → [Single output] → 1 M/E Input
                                       ├─ Program → Screens (cameras + lyrics)
                                       └─ Aux → ATEM Mini → Streaming
```

### What's Changing
```
ProPresenter (Mac) → UltraStudio (dual SDI outputs)
                     ├─ SDI 1: Backgrounds → 1 M/E Input 5 → Aux → Screens
                     └─ SDI 2: Lyrics Key → 1 M/E Input 6 → DSK → Program → ATEM Mini → Streaming
```

## Installation Steps

### Phase 1: Install UltraStudio Monitor 3G (30 minutes)

**Computer: Mac (running ProPresenter)**

#### 1.1 Driver Installation (on Mac)
1. **Download** Blackmagic Desktop Video software from https://www.blackmagicdesign.com/support/
2. **Install** on Mac running ProPresenter
3. **Restart** Mac after installation
4. **Verify** installation: System Preferences should show "Blackmagic Desktop Video" panel

#### 1.2 Physical Installation
1. **Power off** Mac
2. **Connect** UltraStudio to Mac via Thunderbolt cable
3. **Connect** UltraStudio power supply
4. **Power on** Mac
5. **Verify** UltraStudio is recognized:
   - Open "Blackmagic Desktop Video Setup" utility (on Mac)
   - Should show UltraStudio Monitor 3G detected

#### 1.3 Configure UltraStudio Settings (on Mac)
1. Open **Blackmagic Desktop Video Setup** (on Mac)
2. Set **Video Output** format: **1080p59.94** (or 1080p60 - match your 1 M/E format)
3. Set **SDI Output 1:** Enabled
4. Set **SDI Output 2:** Enabled
5. Click **Save**

### Phase 2: Configure ProPresenter (45 minutes)

**Computer: Mac (running ProPresenter)**

#### 2.1 Backup Current Configuration (on Mac)
1. ProPresenter → Preferences → Screens
2. **Screenshot** current screen configuration
3. File → Export → Save current presentation library (backup)

#### 2.2 Configure Screen Outputs

**For ProPresenter 7:**

1. Open **ProPresenter Preferences** → **Screens** tab

2. **Configure Output 1 - Sanctuary Backgrounds:**
   - Click **+** to add new screen
   - Name: "Sanctuary Backgrounds"
   - Output Device: **Blackmagic UltraStudio Monitor 3G (SDI 1)**
   - Resolution: 1920x1080 (or match your screens)
   - Content Configuration:
     - **Slide** layer: ✓ Enabled
     - **Media** layer: ✓ Enabled
     - **Props** layer: ✓ Enabled (if used)
     - **Text** layers: ✗ Disabled (important!)
     - **Announcement** layer: ✗ Disabled
   - Click **Apply**

3. **Configure Output 2 - Lyrics Key:**
   - Click **+** to add new screen
   - Name: "Lyrics Key"
   - Output Device: **Blackmagic UltraStudio Monitor 3G (SDI 2)**
   - Resolution: 1920x1080
   - **Enable "Output as Key"** or **"Alpha Channel Output"** (if available)
   - Content Configuration:
     - **Slide** layer: ✗ Disabled
     - **Media** layer: ✗ Disabled
     - **Text** layers: ✓ Enabled (important!)
     - **Announcement** layer: ✓ Enabled (if you announce on lyrics)
   - Background: **Transparent** or **Black** (transparent preferred)
   - Click **Apply**

**For ProPresenter 6:**

1. Preferences → Screens
2. Configure **Audience Screen 1:**
   - Output: Blackmagic SDI 1
   - Layers: Slides only, disable text
3. Configure **Key Output:**
   - Enable "Show key output"
   - Output: Blackmagic SDI 2
   - Layers: Text only, disable slides

#### 2.3 Test ProPresenter Outputs

1. **Create test presentation:**
   - Slide 1: Image background with song lyrics
   - Slide 2: Video background with announcement text

2. **Run presentation** and verify:
   - UltraStudio SDI 1 shows backgrounds/images only (no text)
   - UltraStudio SDI 2 shows lyrics text only (on black or transparent)

3. **Troubleshooting:**
   - If both outputs show same content: Recheck layer settings
   - If no output on SDI 2: Verify "Output as Key" enabled
   - If wrong resolution: Check UltraStudio Desktop Video settings

### Phase 3: Cable Routing (30 minutes)

#### 3.1 Document Current Connections

**Before disconnecting anything:**
1. **Photo** current 1 M/E front/back panel connections
2. **Note** which Program output goes to screens
3. **Note** which Aux output goes to SDI-to-HDMI converter
4. **Label** current ProPresenter output cable

#### 3.2 New SDI Connections

**From UltraStudio to 1 M/E:**
1. **SDI cable 1:**
   - From: UltraStudio Monitor 3G **SDI Output 1**
   - To: 1 M/E **Input 5** (or first available input)
   - **Label:** "ProPresenter Backgrounds"

2. **SDI cable 2:**
   - From: UltraStudio Monitor 3G **SDI Output 2**
   - To: 1 M/E **Input 6** (or next available input)
   - **Label:** "ProPresenter Lyrics Key"

**Disconnect old ProPresenter connection:**
- Remove previous ProPresenter output cable from 1 M/E
- Store cable as spare

#### 3.3 Reroute Outputs

**Sanctuary Screens:**
1. **Disconnect** screens from current Program output
2. **Connect** screens to **1 M/E Aux 1 output**
3. **Label:** "Screens - Backgrounds Only"

**Streaming (ATEM Mini):**
1. **Disconnect** SDI-to-HDMI converter from current Aux output
2. **Connect** SDI-to-HDMI converter to **1 M/E Program Output**
3. **Verify** HDMI connection to ATEM Mini
4. **Label:** "Stream - Program with Lyrics"

#### 3.4 Cable Management
- Secure all SDI cables with velcro ties
- Ensure cables have appropriate bend radius (not kinked)
- Route cables to avoid power cables (reduce interference)
- Update cable diagram/rack layout documentation

### Phase 4: Configure 1 M/E Switcher (45 minutes)

**Computer: Windows 11 PC (running ATEM Software Control)**

#### 4.1 Connect to ATEM Software Control (on Windows PC)

1. **Connect** Windows PC to 1 M/E via Ethernet or USB
2. **Launch** ATEM Software Control (on Windows PC)
3. **Verify** connection to switcher (should show model name)

#### 4.2 Configure Input Labels (on Windows PC)

1. In ATEM Software Control (on Windows PC) → **Switcher** menu → **Input Labels**
2. Set labels:
   - Input 1: "Camera 1 - Wide"
   - Input 2: "Camera 2 - Pulpit"
   - Input 3: "Camera 3 - Choir"
   - Input 4: "Camera 4 - Detail"
   - Input 5: "PP Backgrounds"
   - Input 6: "PP Lyrics Key"
3. Click **Save**

#### 4.3 Configure Auxiliary Output (on Windows PC)

1. In ATEM Software Control (on Windows PC), locate **Aux Source** buttons
2. Click **Aux 1** button
3. Select **Input 5** ("PP Backgrounds")
4. **Verify:** Sanctuary screens should now show ProPresenter backgrounds

**Alternative method:**
- Switcher menu → Change Aux Source → Aux 1 → Select Input 5

#### 4.4 Configure Downstream Keyer (DSK) (on Windows PC)

This is the critical step for overlaying lyrics on camera shots.

1. **In ATEM Software Control (on Windows PC):**
   - Navigate to **Palette** panel (or DSK section)
   - Select **Downstream Key 1** (or DSK 1)

2. **Set Key Sources:**
   - **Fill Source:** Input 6 ("PP Lyrics Key")
   - **Key Source:** Input 6 ("PP Lyrics Key")
   - *Note: Fill and Key are often the same when using luma key*

3. **Configure Key Type:**
   - **Key Type:** Start with **Luma Key**
   - Alternative: **Linear Key** (if ProPresenter outputs true alpha channel)

4. **Adjust Key Parameters:**

   **For Luma Key:**
   - **Clip:** 50-70% (adjust so lyrics appear crisp)
   - **Gain:** 0-20% (adjust for edge softness)
   - **Pre-Multiplied:** Off (unless ProPresenter pre-multiplies alpha)
   - **Invert Key:** Off (unless lyrics appear inverted)

   **For Linear Key (if using alpha channel):**
   - Typically requires less adjustment
   - Enable if ProPresenter outputs true transparency

5. **Test the Key:**
   - Put a camera on Program (press Camera 1 button)
   - Enable **DSK 1 On Air** (press the "On Air" button for DSK 1)
   - Run ProPresenter presentation
   - **Verify:** Lyrics should overlay on camera shot

6. **Fine-tune:**
   - Adjust Clip/Gain until lyrics are clean
   - No black box around text
   - No fringing or halos around letters
   - Text appears sharp and readable

#### 4.5 Set Video Format

1. **Switcher** menu → **Video Format**
2. Set to match all equipment (typically **1080p59.94**)
3. Verify all inputs show correct format in Software Control

#### 4.6 Save Configuration

1. **Switcher** menu → **Save Startup State**
2. This preserves:
   - Aux 1 source assignment
   - DSK configuration
   - Input labels
3. Switcher will restore these settings on power-up

### Phase 5: Configure ATEM Mini (15 minutes)

#### 5.1 Verify Input

1. **Power on** ATEM Mini
2. **Press Input 1 button** (should receive Program output from 1 M/E)
3. **Verify** HDMI signal present (check ATEM Mini display or output)

#### 5.2 Configure Streaming

1. **Connect** to ATEM Mini via ATEM Software Control (or Mini app)
2. **Output Settings:**
   - Resolution: 1080p59.94 or 1080p60
   - Quality: High (for streaming)
3. **Streaming Settings:**
   - Platform: castr.io (custom RTMP if needed)
   - Enter castr.io stream key and server URL
   - Alternative: Use castr.io's software to pull from ATEM USB output

#### 5.3 Audio Configuration

*Ensure audio is properly routed to ATEM Mini:*
- If using embedded SDI audio: Should pass through automatically
- If using separate audio: Connect to ATEM Mini audio input
- Test audio levels in streaming software

### Phase 6: System Testing (30 minutes)

#### 6.1 Test Sanctuary Screens

1. **Run ProPresenter** with test presentation
2. **Change slides** and verify:
   - Screens show backgrounds/images
   - Screens do NOT show lyrics text
   - Screens do NOT change when switching cameras on 1 M/E
3. **Test videos/media:**
   - Play video in ProPresenter
   - Verify video appears on screens

#### 6.2 Test Streaming Output

1. **Switch cameras** on 1 M/E Program bus
2. **Verify:**
   - Camera switching works
   - Each camera shows clearly
   - No black frames or glitches

3. **Enable DSK 1 On Air**
4. **Run ProPresenter** with lyrics
5. **Verify:**
   - Lyrics overlay on camera shots
   - Text is readable and properly positioned
   - No black boxes around text
   - Background of lyrics is transparent

#### 6.3 Test Complete Workflow

**Simulate a worship service:**

1. **Pre-service:**
   - Switch to camera 1 (wide shot) on Program
   - Sanctuary screens show announcement slide (backgrounds only)
   - Stream shows camera with no lyrics (DSK off)

2. **Song begins:**
   - Keep camera 1 on Program
   - Enable DSK On Air
   - Advance ProPresenter to first song slide
   - **Verify:** Stream shows camera + lyrics, screens show backgrounds

3. **During song:**
   - Switch between cameras (1, 2, 3, 4)
   - Advance lyrics in ProPresenter
   - **Verify:** Stream shows camera switching with lyrics, screens show static backgrounds

4. **Song ends:**
   - Switch to Camera 2 (pulpit)
   - Disable DSK On Air
   - Advance ProPresenter to sermon notes/blank
   - **Verify:** Stream shows camera only, screens show sermon notes backgrounds

5. **Full service test:**
   - Run through entire service order
   - Note any issues or adjustments needed

#### 6.4 Test castr.io Streaming

1. **Start test stream** on castr.io
2. **Verify** stream reaches Facebook/YouTube
3. **Check** stream quality and audio sync
4. **Monitor** for dropped frames or buffering
5. **Stop** test stream

### Phase 7: Documentation and Training (30 minutes)

#### 7.1 Update Documentation

- [ ] Take photos of new cable routing
- [ ] Create labeled diagram of connections
- [ ] Document input assignments on 1 M/E
- [ ] Note DSK settings that worked best
- [ ] Update equipment rack labels

#### 7.2 Create Quick Reference Card

Print and laminate quick reference showing:
- Which cameras are which inputs
- How to enable/disable DSK (for lyrics on/off)
- How to verify Aux 1 source (for screen troubleshooting)
- Emergency contact info

#### 7.3 Train Operators

**Key operators should practice:**
- Switching cameras during songs
- Enabling DSK for worship, disabling for sermon
- Advancing ProPresenter slides
- Verifying sanctuary screens show correct content
- Starting/stopping castr.io stream

## Troubleshooting Guide

### Problem: Sanctuary screens show lyrics

**Cause:** Aux 1 not set to Input 5, or ProPresenter layers misconfigured

**Solution:**
1. Check ATEM Software Control → Aux 1 source = Input 5
2. Check ProPresenter → Screen 1 → Text layers disabled

### Problem: No lyrics on stream

**Cause:** DSK not enabled, or DSK misconfigured

**Solution:**
1. ATEM Software Control → DSK 1 → Press "On Air"
2. Verify DSK Fill source = Input 6
3. Adjust Clip/Gain settings

### Problem: Lyrics have black box around them

**Cause:** Key type or settings incorrect

**Solution:**
1. Try Linear Key instead of Luma Key
2. Increase Clip value
3. Verify ProPresenter outputs alpha/key correctly

### Problem: UltraStudio not detected

**Cause:** Driver not installed, or Thunderbolt connection issue

**Solution:**
1. Reinstall Blackmagic Desktop Video drivers
2. Try different Thunderbolt port on Mac
3. Verify UltraStudio power connected
4. Restart Mac

### Problem: Stream shows wrong content

**Cause:** SDI-to-HDMI converter connected to wrong output

**Solution:**
1. Verify converter input connected to 1 M/E Program output (not Aux)
2. Check ATEM Mini receiving correct input

### Problem: ProPresenter outputs show same content

**Cause:** Layer configuration incorrect

**Solution:**
1. Output 1: Enable slides, disable text
2. Output 2: Enable text, disable slides
3. Ensure "Output as Key" enabled for Output 2

## Post-Upgrade Checklist

- [ ] All equipment powered and connected
- [ ] ProPresenter shows dual outputs (backgrounds + key)
- [ ] Sanctuary screens show backgrounds only
- [ ] ATEM Mini receives Program with lyrics overlay
- [ ] Streaming to castr.io works
- [ ] DSK enables/disables lyrics on stream
- [ ] All cables labeled
- [ ] Documentation updated
- [ ] Operators trained
- [ ] Quick reference card created and posted
- [ ] Test during rehearsal before first service

## Rollback Plan

If upgrade fails and service is imminent:

1. **Reconnect old ProPresenter output** to 1 M/E input
2. **Reconnect screens** to 1 M/E Program output
3. **Reconnect ATEM Mini** to 1 M/E Aux output
4. **Disable DSK** on 1 M/E
5. **Set Aux source** to ProPresenter input
6. System returns to original configuration

**Keep old cables accessible during first few services until confident in new setup.**

## Next Steps

After successful upgrade:
1. Review **OPERATIONS-MANUAL.md** for day-to-day procedures
2. Review **MACRO-GUIDE.md** to program macros for common operations
3. Schedule training session for all video operators
4. Consider backup/redundancy improvements

## Support

**If you encounter issues:**
- Consult OVERVIEW.md for system architecture
- Check Blackmagic support forums: https://forum.blackmagicdesign.com
- ProPresenter community: https://learn.renewedvision.com

**Equipment Support:**
- Blackmagic: https://www.blackmagicdesign.com/support
- ProPresenter: support@renewedvision.com

---

**Document Version:** 1.0
**Last Updated:** 2026-01-07
**Tested By:** _____________
**Date Completed:** _____________
