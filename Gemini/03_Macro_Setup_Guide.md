# How to Create Automation Macros
Switching the routing manually during a service can be stressful. We will create two buttons to automate the configuration changes between "Worship" and "Preaching".

## Preparation
1.  Open **ATEM Software Control** on your computer.
2.  Go to the top menu bar: `Macros` -> `Macros`.
3.  A window will appear listing numbered slots.

## Creating Macro 1: "Worship Mode"
*This mode sets the screens to show lyrics and ensures lyrics are ready to be overlaid on the stream.*

1.  Click on an empty slot (e.g., Slot 1).
2.  Click **Create** (Record icon). Name it "Worship Mode".
3.  **Perform these actions on the switcher software:**
    *   Go to the **Auxiliary** tab (top bar). Set `Aux 1` source to your **ProPresenter Input**.
    *   Go to the **Palettes** tab (right side). Under `Downstream Key 1`, ensure the `Key` button is **ON** (or `On Air` is active).
    *   *(Optional)* Switch the **Program** bus to a wide shot of the stage.
4.  Click the **Stop Record** button in the Macros window.

## Creating Macro 2: "Preach Mode"
*This mode sets the screens to show the Live Camera (IMAG) and turns off the lyric overlay.*

1.  Click on the next empty slot (e.g., Slot 2).
2.  Click **Create** (Record icon). Name it "Preach Mode".
3.  **Perform these actions on the switcher software:**
    *   Go to the **Auxiliary** tab. Set `Aux 1` source to **Program**.
    *   Go to the **Palettes** tab. Under `Downstream Key 1`, press the `On Air` button to turn it **OFF** (light goes out).
4.  Click the **Stop Record** button in the Macros window.

## How to Use Them
1.  During the service, keep the **Macros** window open (or use a Stream Deck if integrated).
2.  When the band starts: Click **Run** on "Worship Mode".
3.  When the pastor walks up: Click **Run** on "Preach Mode".

*Note: If you make a mistake while recording, just delete the macro and start over. It records every click you make!*
