# Hardware Upgrade Recommendation: The "Dual-Feed" ProPresenter Setup

## The Current Limitation
Currently, you likely send a single video cable from the ProPresenter Mac to the ATEM Switcher. This forces a compromise:
*   **Scenario:** You want colorful, moving backgrounds for the Sanctuary screens.
*   **The Problem:** If you overlay that same signal on the Livestream, the lyrics block the band because the background is opaque.
*   **The Band-Aid:** You use black backgrounds for lyrics. This keys nicely over the video for the stream, but looks boring/plain on the sanctuary screens.

## The Solution: Separate the Signals
We want to send **two** distinct signals from the Mac:
1.  **Audience Feed:** Full color, moving backgrounds, centered text. (For the Sanctuary Screens).
2.  **Alpha/Key Feed:** High contrast, no background, lower-third text. (For the Livestream Overlay).

## Hardware Required
To achieve this, you need an additional video output from your Mac.

### Recommended Device: Blackmagic UltraStudio Monitor 3G
*   **Cost:** Approx. $115 - $125 USD.
*   **Connection:** Thunderbolt 3 (USB-C) to SDI/HDMI.
*   **Function:** Provides a broadcast-quality video output separate from your standard HDMI port.

### Cabling Requirements
1.  **Existing Connection (HDMI):** Connects Mac HDMI -> ATEM Input 5. (Used for **Audience**).
2.  **New Connection (SDI):** Connects UltraStudio 3G (SDI Out) -> ATEM Input 6. (Used for **Key/Overlay**).

## Configuration Steps

### 1. Physical Setup
1.  Plug the UltraStudio Monitor 3G into a Thunderbolt port on the Mac.
2.  Run an SDI cable from the UltraStudio to the ATEM Switcher (e.g., Input 6).

### 2. ProPresenter Settings
1.  Go to `Screens` -> `Configure Screens`.
2.  **Audience Screen:** Set to the standard HDMI output.
3.  **Stage Screen (or New Audience Screen):** Set to the "Blackmagic UltraStudio" output.
4.  **Looks:** In the `Looks` editor, ensure the standard audience screen gets the "Presentation" theme, and the new output gets a "Lower Third" theme with no background.

### 3. ATEM Switcher Setup
1.  **Map Inputs:** Label Input 5 "ProPres Main" and Input 6 "ProPres Key".
2.  **Aux 1 (Sanctuary):** Is set to look at Input 5 ("ProPres Main").
3.  **DSK 1 (Stream Overlay):** Is set to look at Input 6 ("ProPres Key") for both Fill and Key source.

## Benefit
*   **In Room:** Beautiful, immersive motion graphics behind the lyrics.
*   **On Stream:** Clean, professional lower-thirds that do not obscure the band or speaker.
