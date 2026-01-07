# Sunday Morning Operations Guide

## 1. Power Up Checklist
*   [ ] Turn on Cameras 1-4.
*   [ ] Turn on ATEM Switchers (1 M/E and Mini).
*   [ ] Turn on Mac (ProPresenter).
*   [ ] Open **ATEM Software Control** on the PC.
*   [ ] **Verify Stream:** Check that the ATEM Mini is receiving signal (Green light/HDMI visible).

## 2. Pre-Service Setup
1.  **Check Aux Output:** Look at the "Auxiliary" tab in ATEM Software. Ensure `Aux 1` is set to **ProPresenter**.
    *   *Check:* The Sanctuary screens should show the "Welcome" slide.
2.  **Check Stream Overlay:**
    *   Ask ProPresenter operator to fire a "Test Lyric".
    *   In ATEM Software, press `DSK 1 On Air`.
    *   *Check:* Does the text appear over the camera shot?
    *   Turn `DSK 1 Off Air` when done.

## 3. During Worship (Music Set)
**Standard Operation:**
*   **Sanctuary Screens:** Automatically show lyrics (because Aux 1 is set to ProPresenter).
*   **Stream:** You cut between cameras on the **Program Bus**.
*   **Overlay:** Keep `DSK 1 On Air` active so the stream sees lyrics.

**Transitions:**
*   Switch cameras to the beat of the music.
*   If the song ends and someone speaks, you might temporarily turn `DSK 1 Off` if the lyrics are blocking their face, but usually, ProPresenter will just "Clear Slide".

## 4. The Transition (Worship -> Sermon)
*Wait for the Pastor to take the stage.*

**EXECUTE "PREACH MODE"** (or Manual Steps):
1.  **Change Aux 1:** Set Source to **Program**.
    *   *Result:* The screens now show the camera you have selected.
2.  **Turn Off Overlay:** Turn `DSK 1 On Air` to **OFF**.
    *   *Result:* No stray lyrics will accidentally pop up over the pastor's face on the stream.

## 5. The Sermon
**Standard Operation:**
*   You are now switching for **BOTH** the Room and the Stream.
*   **Keep it simple:** Stay mostly on the Close-Up camera of the speaker.
*   **Wide Shots:** Use sparingly (e.g., when they move or gesture broadly).
*   *Note:* Do not cut to empty cameras. The room is watching!

## 6. Post-Service / Closing
1.  **EXECUTE "WORSHIP MODE"** (if the band comes back up).
    *   Aux 1 -> ProPresenter.
    *   DSK 1 -> On Air.
2.  **End of Stream:** Fade to Black on the main Program bus.

## Troubleshooting
*   **"The Screens are Black!"** -> Check `Aux 1`. Is it set to "Black"? Change it to ProPresenter or Program.
*   **"Lyrics are blocking the Pastor's face on stream!"** -> Turn off `DSK 1 On Air`.
*   **"I can't see the lyrics on the stream!"** -> Turn on `DSK 1 On Air`.
