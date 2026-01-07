# Video Production Operations Manual

## Daily Operations Guide

This manual covers routine operation of the video production system for church services.

## Operator Roles

### Primary Switcher Operator
- **Computer:** Windows 11 PC (running ATEM Software Control)
- **Responsibilities:**
  - Camera switching during service
  - Enabling/disabling lyrics overlay (DSK)
  - Monitoring Program output (stream)
  - Executing macros

### ProPresenter Operator
- **Computer:** Mac (running ProPresenter)
- **Responsibilities:**
  - Advancing slides during service
  - Loading presentations
  - Triggering videos/media
  - Ensuring correct content on screens

### Camera Operators (4)
- **Responsibilities:**
  - Framing shots as assigned
  - Maintaining focus and exposure
  - Following shot list/rundown

### Streaming Operator (can be combined with Switcher)
- **Responsibilities:**
  - Starting/stopping castr.io stream
  - Monitoring stream health
  - Verifying Facebook/YouTube feeds

## Pre-Service Setup (45-60 minutes before)

### Step 1: Power On Equipment (30 min before)

**Order matters - power on in this sequence:**

1. **Camera Equipment:**
   - [ ] All 4 cameras
   - [ ] Camera power supplies/batteries
   - [ ] Allow 5 minutes for cameras to warm up

2. **Computers and Switchers:**
   - [ ] Mac running ProPresenter
   - [ ] Wait for Mac to fully boot
   - [ ] Windows 11 PC for ATEM Software Control
   - [ ] Wait for Windows PC to fully boot
   - [ ] Blackmagic 1 M/E Production Switcher
   - [ ] ATEM Mini
   - [ ] SDI-to-HDMI converter (if separate power)

3. **Display Outputs:**
   - [ ] Sanctuary screen system
   - [ ] Monitor displays for operators

**Warm-up time:** Allow all equipment 5-10 minutes to stabilize before testing.

### Step 2: Verify ProPresenter Configuration (25 min before)

**Computer: Mac**

1. **Launch ProPresenter** on Mac

2. **Verify Outputs:**
   - [ ] **Screens** tab shows two outputs enabled:
     - "Sanctuary Backgrounds" (UltraStudio SDI 1)
     - "Lyrics Key" (UltraStudio SDI 2)

3. **Load Today's Presentation:**
   - [ ] Open service playlist
   - [ ] Preview first slide
   - [ ] Check spelling/formatting

4. **Test Outputs:**
   - [ ] Advance to slide with lyrics
   - [ ] **Verify on sanctuary screens:** Backgrounds visible, NO lyrics visible
   - [ ] **Verify on 1 M/E monitor:** Lyrics key shows text only on black

**Troubleshooting:**
- If screens show lyrics: Check ProPresenter output layer settings
- If no output: Check UltraStudio connection, relaunch ProPresenter

### Step 3: Configure ATEM Switcher (20 min before)

**Computer: Windows 11 PC**

**Option A: Using Macros (Recommended)**

1. **Launch ATEM Software Control** on Windows PC
2. **Verify connection** to 1 M/E switcher
3. **Execute "Pre-Service - Announcements" macro**
   - Sets Program to Input 5 (ProPresenter Backgrounds)
   - Disables DSK 1 (no lyrics)
   - Aux 1 already fixed to Input 5

**Option B: Manual Setup**

1. **Launch ATEM Software Control** on Windows PC

2. **Set Program Output:**
   - Press **Input 5** button on Program bus (ProPresenter Backgrounds)
   - This shows announcements on stream before service

3. **Verify Aux 1 Output:**
   - Check software: Aux 1 source = Input 5 (ProPresenter Backgrounds)
   - Should be set automatically from saved state

4. **Verify DSK (Downstream Keyer):**
   - DSK 1 should be **Off Air**
   - Fill source = Input 6 (ProPresenter Lyrics Key)
   - Settings preserved from configuration

5. **Transition Settings:**
   - Type: Mix (dissolve)
   - Duration: 1 second (30 frames if 30fps, 60 frames if 60fps)

### Step 4: Camera Check (15 min before)

**For each camera (1-4):**

1. **Preview Camera:**
   - Press camera button on **Preview** bus
   - Check monitor/program preview

2. **Verify:**
   - [ ] Image appears (camera is on)
   - [ ] Focus is sharp
   - [ ] Framing is appropriate for shot
   - [ ] Exposure is correct (not too bright/dark)
   - [ ] White balance is correct (not too blue/orange)

3. **Test Switching:**
   - Press **AUTO** button to transition camera to Program
   - Verify smooth transition
   - Press next camera on Preview, press AUTO again

**Camera Assignments (example - customize for your church):**
- **Camera 1:** Wide shot of platform/worship team
- **Camera 2:** Pulpit/center (pastor, worship leader)
- **Camera 3:** Choir/musicians (instruments, singers)
- **Camera 4:** Detail/roving (close-ups, congregation, special shots)

### Step 5: Test DSK (Lyrics Overlay) (10 min before)

1. **Set Program to Camera 1:**
   - Press **Input 1** on Program bus
   - Camera 1 should appear on Program output

2. **Load Song in ProPresenter:**
   - Navigate to first worship song
   - Display first lyric slide

3. **Enable DSK:**
   - Press **DSK 1 On Air** button
   - Or execute "Song - Cam 1 Wide + Lyrics" macro

4. **Verify Lyrics Appear:**
   - [ ] Lyrics overlay on camera shot
   - [ ] Text is readable and properly positioned
   - [ ] No black box around text
   - [ ] Lyrics look professional

5. **Test Disable:**
   - Press **DSK 1 Off Air** button
   - Lyrics should disappear, camera remains

6. **Advance Lyrics:**
   - Have ProPresenter operator advance to next slide
   - Verify lyrics update on Program output

**Troubleshooting:**
- If no lyrics appear: Check DSK Fill source = Input 6
- If black box around text: Adjust DSK Clip/Gain settings
- If lyrics look wrong: Check ProPresenter "Lyrics Key" output configuration

### Step 6: Start Streaming (5 min before)

**Using castr.io:**

1. **Open castr.io** web interface or software

2. **Verify ATEM Mini Connection:**
   - castr.io should detect ATEM Mini (via USB or RTMP)
   - Check video preview shows Program output

3. **Start Stream:**
   - Click **Go Live** or **Start Streaming**
   - Select destinations:
     - [ ] Facebook Live
     - [ ] YouTube Live

4. **Verify Stream Active:**
   - Check Facebook/YouTube pages for live indicator
   - Monitor viewer count (should start at 0)
   - Verify audio is present

5. **Monitor Stream Health:**
   - Watch for buffering warnings
   - Check bitrate/frame rate
   - Verify no dropped frames

**Troubleshooting:**
- If no video: Check ATEM Mini output to castr.io
- If no audio: Verify audio source connected to ATEM Mini
- If stream won't start: Check internet connection, verify castr.io account status

### Step 7: Final Checks (2 min before)

- [ ] All cameras operational and framed
- [ ] ProPresenter showing first announcement or countdown
- [ ] Sanctuary screens showing correct content (backgrounds only)
- [ ] Stream active on Facebook/YouTube
- [ ] Audio levels appropriate on stream
- [ ] DSK ready to enable (currently off for pre-service)
- [ ] Operators ready and know their cues

---

## During Service Operations

### Service Start

**When service begins:**

1. **Greeting/Announcements:**
   - Keep Program on Input 5 (ProPresenter Backgrounds) OR
   - Switch to Camera 2 (pulpit) if pastor welcomes live
   - DSK remains **Off** (no lyrics)

2. **Advance ProPresenter:**
   - Show announcement slides as scheduled
   - ProPresenter operator controls timing

### First Song Begins

**Transition to worship:**

1. **Execute Macro:** "Song - Cam 1 Wide + Lyrics"
   - Switches to Camera 1
   - Enables DSK (lyrics on)

   **OR Manual:**
   - Press **Input 1** on Program bus
   - Press **DSK 1 On Air**

2. **ProPresenter:** Advance to first song, first lyric slide

3. **Verify:**
   - Stream shows Camera 1 with lyrics
   - Sanctuary screens show backgrounds only
   - Lyrics readable on stream

### During Songs

**Switcher Operator:**

**Camera Switching:**
- Switch between cameras based on what's happening
- Use **Preview** bus to select next camera
- Press **AUTO** for smooth transitions
- Typical pattern:
  - Wide shot (Cam 1) for group singing
  - Pulpit (Cam 2) for worship leader
  - Choir/musicians (Cam 3) during instrumental
  - Detail (Cam 4) for special moments

**Switching Tips:**
- Preview before transitioning (use Preview bus)
- Time switches to music (downbeats, phrase changes)
- Hold shots 8-15 seconds minimum (avoid "switcher dizzy")
- Use wide shot during choruses (congregation singing)
- Close-ups during verses (worship leader)

**DSK Management:**
- Keep DSK **On Air** throughout song
- DSK automatically overlays on all camera inputs
- No need to touch DSK while switching cameras

**ProPresenter Operator:**
- Advance lyrics in sync with song
- Watch worship leader for timing cues
- Preview next slide before advancing

### Transition to Sermon/Speaking

**When last song ends:**

1. **Execute Macro:** "Sermon - Cam 2 No Lyrics"
   - Switches to Camera 2 (pulpit)
   - Disables DSK (lyrics off)

   **OR Manual:**
   - Press **Input 2** on Program bus
   - Press **DSK 1 Off Air**

2. **ProPresenter:** Advance to sermon notes or blank slide

3. **Verify:**
   - Stream shows pastor on Camera 2
   - No lyrics on stream
   - Sanctuary screens show sermon backgrounds (if any)

### During Sermon

**Switcher Operator:**

**Typically:**
- Stay on Camera 2 (pulpit) most of the time
- Occasional switch to Camera 1 (wide) for variety
- Switch to Camera 4 for illustrations/object lessons
- Use Camera 3 if choir/musicians perform

**If Pastor Shows Sermon Notes:**
1. Execute "Sermon - Notes to Stream + Screens" macro
2. Or manually switch Program to Input 5 (ProPresenter Backgrounds)
3. ProPresenter operator displays sermon outline slides

**If Showing Video Illustration:**
1. Execute "Video - ProPresenter Full Screen" macro
2. Or manually switch to Input 5, ensure DSK is Off
3. ProPresenter operator plays video
4. Return to Camera 2 when video ends

**ProPresenter Operator:**
- Display sermon outline slides if requested
- Play video clips on cue
- Show scripture verses if called for

### Special Events

**Baptism:**
- Use Camera 4 (detail/roving) for close-up
- Switch to Camera 1 for wide shot showing baptistry
- No lyrics (DSK off)

**Communion:**
- Camera 2 (pulpit) for explanation
- Camera 1 (wide) for elements being distributed
- ProPresenter may show communion meditation slides

**Offering:**
- Camera 2 or Camera 1
- ProPresenter may show giving information/QR codes
- DSK off (no lyrics)

**Child Dedication:**
- Camera 2 for pastor speaking
- Camera 4 for close-up of family
- DSK off

### Closing Song

**Return to worship:**

1. **Execute Macro:** "Song - Cam 1 Wide + Lyrics"
   - Switches to Camera 1
   - Enables DSK (lyrics on)

2. **ProPresenter:** Advance to closing song

3. **Switch cameras** as during opening songs

### Benediction/Closing

**After last song:**

1. **Switch to Camera 2** (pulpit) for benediction
2. **Disable DSK** (press Off Air)
3. **ProPresenter:** Show closing slide or blank

### Post-Service (stream continues)

**If streaming post-service fellowship:**
- Switch to Camera 1 (wide shot)
- DSK off
- ProPresenter shows post-service slides

**If ending stream immediately:**
- Keep Camera 2 or switch to ProPresenter slides
- Proceed to shutdown steps

---

## Post-Service Shutdown

### Step 1: Stop Streaming (immediately after service)

1. **castr.io:** Click **Stop Streaming** or **End Stream**
2. **Verify:** Stream ends on Facebook/YouTube
3. **Note:** Stream stats (viewers, watch time) for records if desired

### Step 2: Save and Close (5-10 min after)

1. **ProPresenter:**
   - Save any changes to presentations
   - Close ProPresenter (or leave running if needed soon)

2. **ATEM Software Control:**
   - If any macros were created/edited, export macros to backup file
   - Close software (or leave running for next service)

3. **castr.io:**
   - Log out or close browser/app

### Step 3: Power Down Equipment (10-15 min after)

**Power off in reverse order:**

1. **Display Outputs:**
   - Sanctuary screens (if appropriate)
   - Operator monitors

2. **Switchers:**
   - ATEM Mini
   - Blackmagic 1 M/E Switcher
   - SDI-to-HDMI converter

3. **Computers:**
   - Mac (if shutting down)

4. **Cameras:**
   - All 4 cameras
   - Camera batteries removed for charging if needed

**Equipment that can stay on:**
- If services are close together (e.g., Sunday morning and evening), can leave equipment on
- Always power off cameras when not in use (sensor longevity)

### Step 4: Clean Up (15 min after)

- [ ] Organize cables
- [ ] Cover equipment if dusty environment
- [ ] Return any moved items to storage
- [ ] Lock production booth/area if needed

---

## Quick Reference: Common Operations

### Switch to Camera with Lyrics (during song)
1. Select camera on Preview bus
2. Press AUTO button (smooth transition)
3. Ensure DSK 1 is On Air
4. OR use camera macro: "Song - Cam [1/2/3/4] + Lyrics"

### Switch to Camera without Lyrics (during sermon)
1. Select camera on Preview bus
2. Press AUTO button
3. Ensure DSK 1 is Off Air
4. OR use "Sermon - Cam 2 No Lyrics" macro

### Show ProPresenter on Stream and Screens
1. Press Input 5 on Program bus
2. Ensure DSK 1 is Off Air
3. OR use "Sermon - Notes to Stream" or "Video" macro

### Enable Lyrics Overlay
1. Press DSK 1 "On Air" button
2. Lyrics from ProPresenter will overlay on Program output

### Disable Lyrics Overlay
1. Press DSK 1 "Off Air" button
2. Lyrics disappear from Program output

### Emergency: Cut to Black
1. Press "EMERGENCY - Black Screen" macro
2. OR press Black button on Program bus + press CUT button
3. Use only for true emergencies

### Reset Switcher to Known State
1. Execute "RESET - Default State" macro
2. Returns to Camera 1, DSK off, standard transition settings

---

## Troubleshooting During Service

### Problem: Sanctuary screens show lyrics

**Immediate fix:**
- Screens will continue showing backgrounds only (Aux output is fixed)
- If this occurs, likely ProPresenter layer settings changed

**After service:**
- Check ProPresenter "Sanctuary Backgrounds" output
- Ensure text layers are disabled
- See UPGRADE-GUIDE.md troubleshooting section

### Problem: No lyrics on stream

**Check:**
1. Is DSK 1 "On Air"? Press On Air button
2. Is ProPresenter on lyric slide (not blank)?
3. ATEM Software Control: DSK Fill source = Input 6?

**Quick fix:**
- Execute "Song - Cam 1 + Lyrics" macro
- Resets camera and enables DSK

### Problem: Camera shows no image

**Check:**
1. Is camera powered on?
2. Is SDI cable connected securely?
3. Try different camera - if all fail, check 1 M/E inputs

**Workaround:**
- Use ProPresenter backgrounds (Input 5) temporarily
- Or use remaining working cameras only

### Problem: Stream went offline

**Check:**
1. Internet connection active?
2. castr.io still connected?
3. ATEM Mini powered on?

**Immediate action:**
- Restart stream in castr.io
- Service continues normally (only affects online viewers)
- Investigate after service

### Problem: Wrong content on screens

**Check:**
1. Is Aux 1 source set to Input 5? (check ATEM Software Control)
2. Is ProPresenter showing correct output on "Sanctuary Backgrounds"?

**Quick fix:**
- In ATEM Software Control: Set Aux 1 source = Input 5
- Should be automatic, but can be manually corrected

### Problem: Audio not on stream

**Check:**
1. Audio source connected to ATEM Mini?
2. Audio levels set in ATEM Mini or castr.io?
3. Muted in castr.io software?

**Note:** Audio troubleshooting beyond scope of this video guide - consult audio team

### Problem: Operator is confused

**Reset to known state:**
1. Execute "RESET - Default State" macro
2. Verify Program = Camera 1, DSK off
3. Continue from known state

**Ask for help:**
- Call technical director or experienced operator
- Worst case: Stay on one camera until resolved

---

## Service-Specific Notes

### Regular Sunday Service

**Typical flow:**
1. Pre-service: Announcements (ProPresenter or Camera)
2. Welcome: Camera 2 or ProPresenter
3. Songs 1-3: Camera switching with DSK on
4. Sermon: Camera 2, DSK off
5. Closing song: Camera switching with DSK on
6. Benediction: Camera 2, DSK off

### Special Services

**Christmas/Easter (extra cameras, special music):**
- Additional camera operators may be available
- More camera switching during special music
- Videos/presentations may be longer

**Baptism Service:**
- Camera 4 positioned near baptistry
- Use Camera 4 for close-ups during baptism
- Keep DSK off during baptisms

**Business Meetings:**
- Primarily Camera 2 (pulpit)
- ProPresenter for motions/voting information
- May show presenter slides (Input 5)

---

## Training New Operators

### Switcher Operator Training Checklist

- [ ] Understand signal flow (see OVERVIEW.md)
- [ ] Practice switching between cameras
- [ ] Practice enabling/disabling DSK
- [ ] Execute all common macros
- [ ] Perform pre-service setup supervised
- [ ] Operate during rehearsal/run-through
- [ ] Shadow experienced operator during service
- [ ] Operate service with experienced operator nearby
- [ ] Certified for solo operation

### ProPresenter Operator Training

- [ ] Load and organize presentations
- [ ] Advance slides in sync with service
- [ ] Trigger videos and media
- [ ] Understand dual-output configuration
- [ ] Troubleshoot output issues

### Camera Operator Training

- [ ] Proper framing and composition
- [ ] Focus and exposure control
- [ ] Follow shot assignments
- [ ] Anticipate when camera will be on Program
- [ ] Keep shot steady and well-framed

---

## Maintenance Schedule

### Weekly
- [ ] Verify all cameras operational before first service
- [ ] Test DSK and verify lyrics appearance
- [ ] Clean camera lenses (lens cloth only)

### Monthly
- [ ] Export ATEM macros to backup file
- [ ] Back up ProPresenter presentations to external drive
- [ ] Verify all cables secure and undamaged

### Quarterly
- [ ] Review and update service-specific procedures
- [ ] Train/refresh operators on procedures
- [ ] Test backup equipment (if available)

### Annually
- [ ] Update ATEM software and firmware
- [ ] Update ProPresenter software
- [ ] Review and update all documentation
- [ ] Verify equipment warranties/support contracts

---

## Emergency Contacts

**Technical Director:** ____________________ Phone: _______________

**Backup Switcher Operator:** ____________________ Phone: _______________

**Backup ProPresenter Operator:** ____________________ Phone: _______________

**Equipment Support:**
- Blackmagic Support: https://www.blackmagicdesign.com/support
- ProPresenter Support: support@renewedvision.com
- castr.io Support: https://castr.io/support

**Local AV Vendor:** ____________________ Phone: _______________

---

## Appendix: Keyboard Shortcuts (ATEM Software Control on Windows PC)

| Action | Shortcut |
|--------|----------|
| Cut transition | Ctrl+K |
| Auto transition | Ctrl+L |
| Toggle DSK 1 | Ctrl+1 |
| Go to black | Ctrl+B |

*Note: Shortcuts may vary by ATEM software version*

---

**Document Version:** 1.0
**Last Updated:** 2026-01-07
**Operator:** _____________
**Certification Date:** _____________

**Print and keep at operator station for quick reference.**
