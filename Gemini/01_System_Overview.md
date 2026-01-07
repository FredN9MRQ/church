# Church Video System Overview

## The Core Concept
We are restructuring the video system to provide a professional experience for both the congregation in the sanctuary and the online audience.

**The Main Change:**
We are swapping the output assignments.
*   **Previously:** Program Out -> Sanctuary | Aux Out -> Stream
*   **New Setup:** Aux Out -> Sanctuary | Program Out -> Stream

## Why this works
1.  **Sanctuary Screens (Aux Out):** The screens in the room have specific needs. During worship, they need clean lyrics and backgrounds (no camera shots). During the sermon, they need the live camera feed (IMAG) so people can see the speaker. The **Auxiliary Output** on the switcher allows us to change *only* this destination without affecting the recording.
2.  **Livestream (Program Out):** The livestream needs to see everything that happens: the camera switching, the transitions, and the lower-third lyric overlays. By sending the **Program Output** to the stream, the online audience gets the fully produced "TV show" experience.

## Signal Flow Diagram

### Inputs (Sources)
*   **Cameras 1-4:** Connected via SDI to ATEM 1 M/E Inputs 1-4.
*   **ProPresenter (Mac):** Connected via HDMI/SDI to ATEM 1 M/E Input 5 (Example).

### Processing (ATEM 1 M/E)
*   **Switcher Control:** Manages the mix, keys (overlays), and Aux routing.

### Outputs (Destinations)
*   **Output 1: "Program Out" (SDI)**
    *   Path: `ATEM Program SDI` -> `SDI-to-HDMI Converter` -> `ATEM Mini` -> `Castr.io`
    *   *Content:* The main switched feed with camera cuts and lyric overlays.
    
*   **Output 2: "Aux 1 Out" (SDI)**
    *   Path: `ATEM Aux 1 SDI` -> `Sanctuary Projectors/Screens`
    *   *Content:* Variable.
        *   *Worship:* Shows direct ProPresenter feed.
        *   *Sermon:* Shows "Program" (Cameras).

## Key Definitions
*   **Program:** The main "Line Cut" that is being recorded/streamed.
*   **Aux (Auxiliary):** A secondary output that can "mirror" any input or output, independent of what is live on Program.
*   **DSK (Downstream Keyer):** The tool used to stamp graphics (lyrics) on top of the video before it leaves the switcher.
*   **IMAG (Image Magnification):** Showing the live camera shot of a speaker on the big screens in the same room.
