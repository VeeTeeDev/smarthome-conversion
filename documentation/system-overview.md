## System Overview

### Distribution Board (DIN-Rail Components)

*   **Cabinet / Multifunction Actuator:** Zennio ALLinBOX 1612 v3 (ZPR1612V3)
    *   *Note:* This unit provides a compact all-in-one solution, including an integrated KNX Power Supply (640 mA) and an IP Interface.
*   **Dimming Actuator:** MDT AKD-0401.02 (4-channel)
    *   *Requirement:* Only **4 dimming channels** are needed, chosen for smooth, flicker-free dimming of LED lights.
    *   *Note:* The overall system has 13 light points (2 outside), but only 4 are currently designated as dimmable via this specific actuator. This implies other light points are switched or dimmed by other means not yet defined.
    *   *Compatibility:* Verify with lamp types (LED, halogen, CFL) for smooth dimming.
*   **KNX Power Supply:** Integrated 640 mA KNX PS (part of Zennio ALLinBOX 1612 v3)
    *   *Adequacy:* Generally sufficient for small-to-medium installations; confirm total bus current draw with ~20–30% headroom after all devices are finalized.
*   **IP Interface / Router:** Integrated IP interface (part of Zennio ALLinBOX 1612 v3)
    *   *Functionality:* Supports ETS programming over IP and remote access/router functionality.
    *   *Security Note:* For remote access outside LAN, consider secure VPN or KNX/IP Secure.

### KNX Dimming Explained

In a KNX system, dimming is handled by the **dimming actuator** (e.g., your MDT AKD-0401.02) located in the electrical cabinet. Your wall switches (MDT Push Button Lite) send digital commands to this actuator, not direct power. This allows for flexible and powerful control.

**How Dimming Works with Your KNX Push Buttons:**

1.  **With a 2-Button Rocker (e.g., Top/Bottom or Left/Right):**
    *   **Short Press (e.g., Top):** Switches the light ON to its last dimming value, or to a pre-set value.
    *   **Short Press (e.g., Bottom):** Switches the light OFF.
    *   **Long Press (e.g., Top):** Dims the light UP (brighter) as long as held.
    *   **Long Press (e.g., Bottom):** Dims the light DOWN (darker) as long as held.

2.  **With a Single Button (One-Button Dimming):**
    *   This is used when only one physical button or rocker position is assigned to a light.
    *   **Short Press:** Toggles the light ON/OFF. (If OFF, turns ON; if ON, turns OFF).
    *   **Long Press:** Dims the light UP or DOWN cyclically. The direction alternates with each long press.
        *   First long press after switching ON: Dims UP.
        *   Next long press: Dims DOWN.
        *   And so on.

This approach provides a clean aesthetic with uniform switches throughout your home and offers high flexibility in programming.

### Installation Note: Replacing Niko with Gira/MDT

*   **Wall Box Compatibility:** The existing side-by-side wall boxes (as seen in the image below) are installed with the standard 71mm center-to-center spacing, which is the universal European standard (DIN 49073).
    <img src="../images/double-poweroutlet.jpeg" alt="Existing Double Power Outlet" width="300"/>
*   **Niko "Hooks":** The specific "dovetail" hooks on your current Niko inserts are brand-specific for interlocking Niko mounting frames. These are *not* required or used by Gira inserts or MDT frames.
*   **Gira/MDT Integration:**
    *   The **Gira inserts** (power, data, mechanical push button) come with their own standard metal mounting frames which screw directly into the existing wall box screw points.
    *   **All frames used (1-gang, 2-gang, 3-gang) will be Gira frames.** These Gira frames are rigid and are designed to hold both the **MDT inserts (for buttons)** and the **Gira inserts (for power/data, etc.)** in perfect alignment over the standard 71mm spacing.
*   **Conclusion:** You can confidently replace your existing Niko setup with Gira inserts and MDT frames. The physical mounting and alignment will be fully compatible.

### KNX Cable Identification

*   **Standard Color:** The universally recognized and standard color for KNX bus cable is **green**.
*   **Cable Type:** It is typically a shielded twisted-pair cable (often specified as J-Y(St)Y 2x2x0.8mm). Inside, you'll usually find two pairs of wires:
    *   **Red/Black:** The primary pair for KNX bus data and power.
    *   **Yellow/White:** An auxiliary pair, often unused for bus communication.
*   **Identification:** A green, shielded twisted-pair cable is a strong indicator of KNX. Look for markings on the cable sheath (e.g., "KNX", "EIB", or "J-Y(St)Y") for definitive confirmation.
*   **VERIFICATION (Your Apartment):**
    *   **Visual Evidence of Cabling:** Locations identified as having bus cable:

| | |
|:---:|:---:|
| <img src="../images/cable1.jpeg" alt="Cable Location 1" width="200"/> | <img src="../images/cable2.jpeg" alt="Cable Location 2" width="200"/> |
| <img src="../images/cable3.jpeg" alt="Cable Location 3" width="200"/> | <img src="../images/cable4.jpeg" alt="Cable Location 4" width="200"/> |

    *   **Confirmed Marking:** Photographic evidence clearly shows the cable sheath marked **`J-Y(St)Y`**.

| |
|:---:|
| <img src="../images/cable5.jpeg" alt="Cable Marking J-Y(St)Y" width="300"/> |

    *   **Good News:** This is the standard specification for KNX bus cable. Even though it was used for Nikobus, **it is fully compatible with your new KNX system.**
    *   **Action:** You can reuse the existing cabling without modification. Simply replace the Nikobus components with your new KNX devices.

### Installation Note: Cabinet Space Confirmed

*   **Available Width:** Analysis of the electrical cabinet image (as seen below) confirms an available DIN rail width of approximately **32.5 cm (325 mm)** on at least one row in your distribution board.

| |
|:---:|
| <img src="../images/electrical-cabinet-size.jpeg" alt="Electrical Cabinet Size Measurement" width="400"/> |

*   **KNX Equipment Width:** Your selected KNX central components (Zennio ALLinBOX: 12 TE + MDT AKD-0401.02: 6 TE) require a total of **18 TE**.
*   **Conversion:** 18 TE equates to 18 * 17.5 mm = **315 mm**.
*   **Conclusion:** The available space of 325 mm is sufficient for the 315 mm (18 TE) required, leaving a small buffer for ease of installation.
*   **Action:** The existing Nikobus modules on this rail will need to be removed to free up the 18 TE for the new KNX components.

### Cabinet Requirements (Physical Space)

*   **Total Space Needed:** **18 TE** (DIN rail units)
    *   **Zennio ALLinBOX 1612 v3:** 12 TE
    *   **MDT AKD-0401.02:** 6 TE
*   **Capacity Check:**
    *   **Dimming:** 4 channels (MDT) cover the 4 dimmable circuits.
    *   **Switching:** The Zennio unit has **16 relay outputs**.
        *   **Required:** 9 channels (13 total lights - 4 dimmed).
        *   **Spare:** 7 channels remaining (available for blinds, screens, or switched outlets).
    *   *Conclusion:* The current hardware selection is sufficient for all 13 light points with room for expansion.

### Visualization / App Control

*   **Zennio Hardware:** The Zennio ALLinBOX 1612 v3 allows control via IP but **does not** host a mobile app server itself. To use the official **Zennio Remote** app, a Zennio Touch Panel with a license is typically required.
*   **Server-Based (Best Experience):**
    *   **Home Assistant / OpenHAB:** Free, open-source. Requires a small server (e.g., Raspberry Pi). Connects to the Zennio IP Interface to provide a rich mobile UI, automation, and Apple/Google integration.
*   **Direct Connection / Serverless (For minimalists):**
    *   **EasyKNX (Android):** Connects directly to the IP interface without a server. "Lite" version is free/basic.
    *   **TouchControl (iOS):** Connects directly. Paid app, but no server hardware needed.

### Wiring & Channel Mapping (High Level)

*   The **MDT 4-channel dimmer (AKD-0401.02)** provides the **4 dimming channels** required.
*   The remaining **9 light points** will be switched via the **Zennio ALLinBOX 1612 v3** relays.
*   There are a total of **13 light points (including 2 outside)**. All are covered by the current hardware.
*   **Switch-to-channel assignment:** Detailed per-room mapping to be defined.