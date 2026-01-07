# Directory Overview
This directory contains the technical documentation, operational guides, and system architecture for the Church's Video Production System. The system utilizes Blackmagic Design hardware (ATEM 1 M/E, ATEM Mini) and ProPresenter software to manage separate feeds for the in-house Sanctuary screens and the Online Livestream.

## Key Files & Directories

### `church_video_docs/`
This folder holds the core documentation generated to restructure the video workflow.

*   **`01_System_Overview.md`**
    *   **Purpose:** Explains the fundamental change in signal routing.
    *   **Key Concept:** Swaps the previous setup. Now, **Program Out** feeds the Livestream (for switching + overlays), and **Aux Out** feeds the Sanctuary (for switching between Lyrics-only and Live Camera IMAG).

*   **`02_Upgrade_Recommendation.md`**
    *   **Purpose:** Proposes a hardware improvement using a Blackmagic UltraStudio Monitor 3G.
    *   **Goal:** To allow ProPresenter to send two separate signals: a full-graphics feed for the in-house screens and a clean "Key/Alpha" feed for the livestream overlays.

*   **`03_Macro_Setup_Guide.md`**
    *   **Purpose:** Technical instructions for configuring the ATEM Software Control.
    *   **Content:** Steps to record "Worship Mode" and "Preach Mode" macros to automate signal routing changes during a service.

*   **`04_Operations_Guide.md`**
    *   **Purpose:** A day-to-day checklist for volunteers.
    *   **Content:** Covers power-up procedures, what to do during worship vs. preaching, and troubleshooting tips.

## Usage
This project is a **Knowledge Base** for the AV team.
*   **System Architects/Tech Leads:** Use `01` and `02` to understand the physical cabling and logic.
*   **Volunteers/Operators:** Use `03` to set up the software once, and `04` to run the system every Sunday.
