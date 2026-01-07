# ATEM Switcher Macro Programming Guide

## Introduction to Macros

Macros are pre-programmed sequences of commands that execute with a single button press. They automate common tasks and reduce operator errors during live production.

**Benefits:**
- One-button execution of complex operations
- Consistent results every time
- Reduced training time for new operators
- Faster transitions during service

## What Macros Can Do

- Switch between specific inputs
- Enable/disable downstream keyers (DSK)
- Trigger transitions with specific durations
- Set audio levels
- Change auxiliary output sources
- Execute multiple commands in sequence

## Accessing Macro Functions

### Method 1: ATEM Software Control (Recommended)

1. **Connect** laptop to 1 M/E switcher (Ethernet or USB)
2. **Launch** ATEM Software Control
3. **Navigate** to **Macros** panel
   - Palette menu → Macros
   - Or click "Macros" tab in interface

### Method 2: Hardware Panel (if available)

Some ATEM hardware panels have dedicated macro buttons. Consult your 1 M/E switcher manual for specific button locations.

## Programming Macros: Step-by-Step

### Basic Macro Creation Process

1. **Record** the actions you want the macro to perform
2. **Name** the macro descriptively
3. **Test** the macro execution
4. **Assign** to a button (if hardware panel available)
5. **Document** what the macro does

### Recording a Macro

**In ATEM Software Control:**

1. **Macros Panel** → Click **Create Macro** button
2. **Enter name** for the macro (e.g., "Song Start - Cam 1 + Lyrics")
3. **Click Record** button (red circle icon)
4. **Perform the actions** you want to automate:
   - Switch to desired input
   - Enable/disable DSK
   - Set transition type
   - Any other operations
5. **Click Stop** button when finished
6. **Macro is saved** automatically

**Important Tips:**
- Perform actions slowly and deliberately while recording
- Pause 1-2 seconds between actions for smoother playback
- Include all necessary steps (don't assume starting state)
- Test immediately after recording

### Editing Existing Macros

1. **Macros Panel** → Select macro from list
2. **Click Edit** button
3. **View command list** (individual steps)
4. **Add/Remove/Reorder** commands:
   - Delete unwanted steps
   - Insert pauses between commands
   - Change command parameters
5. **Save changes**

### Deleting Macros

1. **Macros Panel** → Select macro
2. **Click Delete** button
3. **Confirm deletion**

## Recommended Macros for Church Services

### Macro 1: Pre-Service Setup

**Name:** "Pre-Service - Announcements"

**Purpose:** Set up switcher for pre-service announcements

**Actions:**
1. Switch Program to Input 5 (ProPresenter Backgrounds)
2. Disable DSK 1 (no lyrics)
3. Verify Aux 1 = Input 5 (screens show backgrounds)

**Recording Steps:**
1. Start recording macro
2. Press Input 5 button on Program bus
3. Press DSK 1 "Off Air" button
4. Stop recording

**Use:** Press at start of setup, ensures clean announcement slides on both stream and screens

---

### Macro 2: Song Start (Camera 1 + Lyrics)

**Name:** "Song - Cam 1 Wide + Lyrics"

**Purpose:** Quick setup for worship song with wide camera shot

**Actions:**
1. Switch Program to Input 1 (Camera 1 - Wide)
2. Enable DSK 1 On Air (lyrics overlay)
3. Auto transition with 1-second mix

**Recording Steps:**
1. Start recording macro
2. Press Input 1 on Program bus
3. Press DSK 1 "On Air" button
4. Stop recording

**Use:** At start of each song for consistent wide shot with lyrics

---

### Macro 3: Song - Camera 2 (Pulpit/Center)

**Name:** "Song - Cam 2 Pulpit + Lyrics"

**Purpose:** Switch to pulpit camera during song (DSK remains on)

**Actions:**
1. Switch Program to Input 2 (Camera 2)
2. Auto transition with 1-second mix
3. (DSK already on from previous macro)

**Recording Steps:**
1. Start recording macro
2. Ensure DSK 1 is On Air (from previous song state)
3. Press Input 2 on Program bus
4. Press AUTO button (or set transition time first)
5. Stop recording

**Use:** During songs to show worship leader/pastor close-up

---

### Macro 4: Song - Camera 3 (Choir/Musicians)

**Name:** "Song - Cam 3 Choir + Lyrics"

**Purpose:** Show choir or musicians during song

**Actions:**
1. Switch Program to Input 3 (Camera 3)
2. Auto transition with 1-second mix

**Recording Steps:**
1. Start recording macro
2. Press Input 3 on Program bus
3. Press AUTO button
4. Stop recording

---

### Macro 5: Sermon Start (Camera Only, No Lyrics)

**Name:** "Sermon - Cam 2 No Lyrics"

**Purpose:** Transition from songs to sermon (remove lyrics overlay)

**Actions:**
1. Switch Program to Input 2 (Camera 2 - Pulpit)
2. Disable DSK 1 (remove lyrics)
3. Auto transition

**Recording Steps:**
1. Start recording macro
2. Press Input 2 on Program bus
3. Press DSK 1 "Off Air" button
4. Press AUTO button
5. Stop recording

**Use:** Beginning of sermon/speaking portions

---

### Macro 6: Sermon Notes on Screen

**Name:** "Sermon - Notes to Stream + Screens"

**Purpose:** Show ProPresenter sermon notes on both outputs

**Actions:**
1. Switch Program to Input 5 (ProPresenter Backgrounds)
2. Keep DSK 1 off (no lyrics overlay needed)
3. Auto transition

**Recording Steps:**
1. Start recording macro
2. Ensure DSK 1 is Off Air
3. Press Input 5 on Program bus
4. Press AUTO button
5. Stop recording

**Use:** When pastor wants sermon outline/notes visible on stream

---

### Macro 7: Video Playback

**Name:** "Video - ProPresenter Full Screen"

**Purpose:** Play videos from ProPresenter on stream (no lyrics)

**Actions:**
1. Switch Program to Input 5 (ProPresenter Backgrounds)
2. Disable DSK 1 (no lyrics overlay on videos)
3. Auto transition with 1-second mix

**Recording Steps:**
1. Start recording macro
2. Press Input 5 on Program bus
3. Press DSK 1 "Off Air" button
4. Press AUTO button
5. Stop recording

**Use:** Announcements videos, testimonies, sermon illustrations

---

### Macro 8: All Cameras Off (Emergency)

**Name:** "EMERGENCY - Black Screen"

**Purpose:** Cut all video immediately (emergency situations)

**Actions:**
1. Switch Program to Black (Color Bars or Black generator)
2. Disable DSK
3. Cut transition (no mix)

**Recording Steps:**
1. Start recording macro
2. Press Black or Color Bars button
3. Press DSK 1 "Off Air"
4. Press CUT button (immediate transition)
5. Stop recording

**Use:** Medical emergency, inappropriate content, technical failure

---

### Macro 9: Reset to Default (Troubleshooting)

**Name:** "RESET - Default State"

**Purpose:** Return to known good state when confused

**Actions:**
1. Program = Input 1 (Camera 1)
2. Preview = Input 2 (Camera 2)
3. DSK 1 = Off Air
4. Transition type = Mix
5. Transition duration = 1 second

**Recording Steps:**
1. Start recording macro
2. Press Input 1 on Program bus
3. Press Input 2 on Preview bus
4. Press DSK 1 "Off Air"
5. Set transition type to Mix
6. Set transition duration to 1 second
7. Stop recording

**Use:** When operator is confused or switcher state is unknown

---

## Advanced Macro Techniques

### Adding Delays/Pauses

Some macros need delays between actions (e.g., wait for transition to complete).

**How to add delays:**
1. Edit macro in ATEM Software Control
2. Right-click in command list
3. Select "Insert Pause"
4. Set duration (frames or seconds)
5. Place pause between commands

**Example:** Transition to camera, wait 2 seconds, then enable DSK

### Chaining Macros

For very complex operations, trigger one macro from another:

1. Macro A executes commands
2. Last command in Macro A = "Run Macro B"
3. Macro B executes its commands

**Use case:** Full service startup sequence

### Conditional Macros

Some ATEM models support conditional logic:
- "If Program = Input 1, then..."
- "If DSK is On, then..."

Check your 1 M/E manual for availability.

## Macro Best Practices

### Naming Conventions

**Use descriptive names:**
- Good: "Song - Cam 1 Wide + Lyrics"
- Bad: "Macro 1"

**Include key info:**
- Action (Song, Sermon, Video)
- Camera number or source
- Lyrics on/off status

### Organization

**Group macros by service section:**
1-3: Pre-service
4-8: Worship songs
9-12: Sermon
13-15: Special events
16: Emergency/reset

### Documentation

**Create macro reference sheet:**
- Macro number/name
- What it does
- When to use it
- Button assignment (if applicable)

**Print and laminate** for operator reference.

### Testing

**Test all macros before service:**
- Execute each macro
- Verify expected result
- Note any issues
- Make adjustments as needed

**Test after software updates:**
- ATEM software updates may reset macros
- Always verify macros work after updating

## Assigning Macros to Buttons

**If your 1 M/E has macro buttons:**

1. ATEM Software Control → Macros panel
2. Right-click macro
3. Select "Assign to Button"
4. Choose button number
5. Button will trigger macro when pressed

**Label physical buttons:**
- Use label maker
- Write macro name on label
- Place near button on control panel

## Exporting/Importing Macros

### Backup Your Macros

**Export all macros:**
1. ATEM Software Control → File menu
2. Select "Export Macros"
3. Choose location to save .xml file
4. Name file with date (e.g., "ATEM-Macros-2026-01-07.xml")

**Schedule:** Export monthly or after major changes

### Restore Macros

**Import macros from backup:**
1. ATEM Software Control → File menu
2. Select "Import Macros"
3. Choose .xml file
4. Macros will be loaded into switcher

**Use cases:**
- After factory reset
- Setting up backup switcher
- Sharing macros between facilities

## Troubleshooting Macros

### Macro Doesn't Execute

**Possible causes:**
- Switcher not in expected state
- Input not available/connected
- Software version mismatch

**Solutions:**
- Add "Reset to Default" macro before complex macros
- Verify all inputs are connected
- Update ATEM Software Control

### Macro Executes Incorrectly

**Possible causes:**
- Recording included unintended actions
- Commands execute too quickly
- State-dependent actions

**Solutions:**
- Re-record macro more carefully
- Add pauses between commands
- Include setup steps in macro

### Macro Disappeared

**Possible causes:**
- Switcher factory reset
- Software update cleared macros
- Accidentally deleted

**Solutions:**
- Import from backup .xml file
- Re-record macro
- Save macros regularly

## Sample Service Flow with Macros

**Pre-Service (10 minutes before):**
1. Power on all equipment
2. Execute "Pre-Service - Announcements" macro
3. Load ProPresenter playlist
4. Start castr.io stream

**Service Start:**
1. Execute "Song - Cam 1 Wide + Lyrics" macro
2. Advance ProPresenter to first song

**During Songs:**
- Switch between camera macros (Cam 1, 2, 3, 4)
- Advance ProPresenter lyrics
- Macros automatically keep DSK enabled

**Transition to Sermon:**
1. Execute "Sermon - Cam 2 No Lyrics" macro
2. Advance ProPresenter to sermon notes (if used)

**During Sermon:**
- Stay on Camera 2 (or manual switching between cameras)
- Use "Sermon - Notes to Stream" macro if displaying outlines
- Use "Video - ProPresenter Full Screen" for sermon illustrations

**Closing Song:**
1. Execute "Song - Cam 1 Wide + Lyrics" macro
2. Advance ProPresenter to closing song

**Post-Service:**
1. Execute "Pre-Service - Announcements" macro (or Camera 1 no lyrics)
2. Stop castr.io stream
3. Save any changes

## Quick Reference: Macro Commands

| Macro | Input | DSK | Use Case |
|-------|-------|-----|----------|
| Pre-Service | PP Backgrounds | Off | Announcements before service |
| Song Cam 1 | Camera 1 | On | Wide shot with lyrics |
| Song Cam 2 | Camera 2 | On | Pulpit/leader with lyrics |
| Song Cam 3 | Camera 3 | On | Choir/musicians with lyrics |
| Song Cam 4 | Camera 4 | On | Detail shots with lyrics |
| Sermon Start | Camera 2 | Off | Speaking, no lyrics |
| Sermon Notes | PP Backgrounds | Off | Show sermon outline |
| Video | PP Backgrounds | Off | Play video clips |
| Emergency Black | Black | Off | Cut to black immediately |
| Reset | Camera 1 | Off | Return to default state |

## Advanced: SuperSource Macros (if applicable)

If your 1 M/E supports SuperSource (multi-view layouts):

**Picture-in-Picture Macro:**
- Show main camera with small ProPresenter window
- Useful for displaying verses while showing speaker

**Split-Screen Macro:**
- Show 2 cameras side-by-side
- Useful for panel discussions or duets

Consult your 1 M/E manual for SuperSource programming.

## Learning Resources

**Blackmagic ATEM Training:**
- https://www.blackmagicdesign.com/products/atem/training
- Free video tutorials on macro programming
- ATEM Software Control manual (PDF)

**Community Forums:**
- https://forum.blackmagicdesign.com
- Search for "ATEM macros" for examples and tips

**YouTube Tutorials:**
- Search "ATEM macro programming"
- Many churches share their workflows

## Summary Checklist

- [ ] ATEM Software Control installed and connected
- [ ] Macros recorded for common tasks
- [ ] Macros tested and verified
- [ ] Macros documented with reference sheet
- [ ] Macros exported to backup file
- [ ] Operators trained on macro usage
- [ ] Macro buttons labeled (if applicable)
- [ ] Reference sheet printed and posted

---

**Document Version:** 1.0
**Last Updated:** 2026-01-07
**Next Review:** _____________

**Customize this guide** with your specific camera positions, service order, and preferences.
