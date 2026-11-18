---
layout: page
title: Privacy Policy for SignalMap
permalink: /privacy/signalmap/
---

**Last Updated: November 18, 2026**

## Introduction

Thank you for using **SignalMap** ("the App"). SignalMap uses your iPhone's LiDAR (where available) or camera to scan your home's floor plan and maps the Wi‑Fi signal quality in each area as you walk around.

All scanning and measurement happen on your device. The App additionally sends privacy-minimized product interaction events to a developer-operated analytics service so we can tell whether onboarding, scanning, and the purchase flow work as intended. Apart from that, the App's network activity is limited to your own local network, Apple's App Store, and, only if you turn on the optional scan-place feature described below, Apple's place-name lookup service.

## Data Collection and Use

1.  **On-device processing**: All scanning and analysis happen entirely on your device. The floor plan generated from LiDAR or the camera and the resulting signal heatmap are processed locally and are **never uploaded** to us or anyone else.
2.  **Network measurements**: To estimate Wi‑Fi quality, the App measures the connection (latency, jitter, packet loss) between your device and your own router/gateway on the local network. These measurements are performed on your device and stay on your device. The App does **not** capture or transmit the contents of your network traffic.
3.  **Wi‑Fi network name (SSID/BSSID)**: With your permission, the App reads the name and identifier of the Wi‑Fi network you are currently connected to, solely to label nodes on the heatmap. This information is used locally and is **never** transmitted, including in analytics events.
4.  **Local storage**: Your scan history is saved only in your device's local storage so you can review past results. You can delete any record at any time within the App.
5.  **Scan place (optional, off by default)**: If you turn on "Save scan location" in the App's Settings, the App reads a location fix while a scan runs and saves it **only on your device**, together with that scan. The saved data is the coordinates, an altitude and floor level where iOS provides them, and the fix's accuracy. It is used to tell different homes and different floors apart, so that scans of the same Wi‑Fi network in different places are not compared with each other. To show a readable place name (for example a district and street), the App sends the saved coordinates once to **Apple's system place-name lookup service** (Apple's reverse geocoding); this request goes to Apple, not to us, and is subject to [Apple's Privacy Policy](https://www.apple.com/legal/privacy/). If the lookup is unavailable, the coordinates are shown instead. We never receive your location, and it is **never** included in analytics events. Turning the setting off stops saving new locations; deleting a scan record removes its saved location.
6.  **Limited-time offer timer**: To show the limited-time lifetime offer honestly, the App stores the time at which the offer window began in your device's Keychain. It contains no personal information and is not sent to us. Because the Keychain can survive deleting and reinstalling the App, the offer cannot be restarted by reinstalling.
7.  **Product analytics**: SignalMap sends privacy-minimized product interaction events to a developer-operated ("first-party") analytics service. These events help us understand whether the introduction, the walk-and-scan flow, the results screen, and the Pro purchase flow work as intended.

    An event may include:

    *   a random identifier generated for that single event;
    *   the event name and the time it occurred;
    *   a short-lived flow identifier used to connect the steps of one paywall journey, discarded when that journey ends. It is not a user, device, or installation identifier and cannot be used to recognise you later or across sessions;
    *   the app version, build number, platform, and system locale/region;
    *   a small set of allowlisted, fixed-vocabulary attributes describing the product flow and commercial decision — for example which screen or entry point was used, which onboarding step was seen, which plan or offer was selected, and whether a purchase succeeded, was cancelled, was pending, or failed. For scans, they also include the scan mode (LiDAR or camera), coarse buckets such as how many sample points were collected or how long the first point took, and a stable reason category when a scan ends early (for example no Wi‑Fi connection or router not reachable). Failures are reported only as a stable category such as `network` or `storekit`, never as an error message.

    We do **not** send: your Wi‑Fi network name (SSID) or identifier (BSSID), IP addresses, GPS or any location data, floor plans, wall geometry, scan coordinates, signal strength or any network measurement results, scan history, names, email addresses, account identifiers, advertising identifiers, persistent device or installation identifiers, screenshots, or any free-form text you enter. Analytics events are not linked to your identity and are not used to track you across apps or websites. The App sends no analytics events at all when your App Store country or region is mainland China.

8.  **No third-party trackers or advertising**: The App contains no advertising SDKs and no third-party analytics or tracking SDKs. The analytics service described above is operated by the developer, not by an advertising or data broker network.

## Permissions

The App requests the following permissions, each used only for the stated purpose:

*   **Camera** — required by Apple's RoomPlan/ARKit to scan rooms with LiDAR or, on devices without LiDAR, with the camera, and to build the floor plan.
*   **Local Network** — to measure connection quality to your router/gateway.
*   **Location (While Using the App)** — required by iOS in order to read the name (SSID) of the Wi‑Fi network you are connected to, used to label the heatmap. By default the App does not store or transmit your location. Only if you turn on the optional "Save scan location" setting does the App keep a location fix **on your device** with each scan, as described under "Scan place" above; the saved location is never sent to us and is not included in analytics events. You can leave location permission off or choose approximate location; the App then cannot tell nearby homes or floors apart, but still works.

## Purchases

Optional "Pro" features are offered through in-app purchases processed by **Apple** via the App Store: a one-time 7-day pass that does not renew, a one-time lifetime unlock (sometimes offered at a limited-time price), and, for existing subscribers, legacy subscriptions that are no longer sold. Payments are handled entirely by Apple under its own terms and privacy policy; we do not receive or store your payment information. Purchase and subscription status is verified through Apple's StoreKit. Analytics records only that a purchase step occurred and its outcome — never payment details, transaction identifiers, or prices tied to you.

## Third-Party Services

*   **Hilalum Analytics** — the developer-operated analytics service that receives the privacy-minimized product interaction events described above. It is operated by the developer of this App and is not shared with advertisers or data brokers. It does not receive account, device, location, floor-plan, or network-measurement data. Request IP addresses and User-Agent strings are discarded and never stored.
*   **Apple App Store** — in-app purchases are processed by Apple. See [Apple's Privacy Policy](https://www.apple.com/legal/privacy/).
*   **Apple place-name lookup (only if you turn on "Save scan location")** — Apple's system reverse-geocoding service turns a saved scan location into a readable place name. The request is made from your device directly to Apple; we do not receive it or its result. See [Apple's Privacy Policy](https://www.apple.com/legal/privacy/).

## Data Retention and Deletion

*   Individual analytics events are retained for **30 days**, after which they are deleted automatically.
*   Aggregated daily counts (for example, "how many scans completed on a given day") are retained longer for trend comparison. These aggregates contain no identifiers and cannot be traced back to any person or device.
*   Because analytics events contain no user, device, or installation identifier, we have no way to single out one person's events. If you would like your data removed, email us and we can delete the events for a given time window; you can also stop all future collection at any time by deleting the App.
*   Your scans, floor plans, history, and any saved scan locations live only on your device. Deleting a record in the App, or deleting the App, removes them permanently. The offer-timer value kept in the Keychain (see above) may remain after the App is deleted.

## Children's Privacy

The App is not directed at children and does not knowingly collect personal information from anyone.

## Changes to This Privacy Policy

We will update this privacy policy if the App's functionality changes significantly. Any changes will be posted on this page with an updated "Last Updated" date.

## Contact Us

If you have any questions about this privacy policy or concerns about the security of the App, please contact us at:

*   Email: [dcyap0@icloud.com](mailto:dcyap0@icloud.com)
