---
layout: page
title: Room Board Home Assistant Setup Guide
description: Connect Room Board, organize rooms, configure energy sensors, and display a Lovelace Picture Elements floor plan.
permalink: /roomboard/setup/
---

**Last updated: August 5, 2026 · [中文说明](#中文说明) · [AI quick reference](#ai-quick-reference)**

Room Board is a third-party Home Assistant dashboard for Apple TV and other large screens. It connects directly to your Home Assistant instance. The app does not require HomeKit and does not send your home data through a Room Board server.

## Connect Home Assistant {#connection}

1. Make sure Apple TV and the phone used for sign-in can reach the same Home Assistant address. A local address usually looks like `http://192.168.1.20:8123`; Home Assistant Cloud or a correctly configured HTTPS address also works.
2. Enter that complete address in Room Board, including `http://` or `https://` and the port when needed.
3. Choose **Scan to Sign In**, scan the TV code with a phone, and approve access on your own Home Assistant page.
4. If local pairing is unavailable, open your Home Assistant profile, create a **Long-Lived Access Token**, then paste it using the Apple TV keyboard on iPhone.

Do not share access tokens in screenshots, support messages, or public AI chats. A token grants access to your Home Assistant instance.

## Rooms and areas {#rooms}

Room Board builds room tabs from Home Assistant Areas:

1. In Home Assistant, open **Settings → Areas, labels & zones**.
2. Create an Area for each physical room.
3. Assign devices or entities to their correct Area.
4. Return to Room Board and refresh the Home Assistant connection.

Room Board's local room grouping is only a display override. It does not modify Areas in Home Assistant.

## Energy sensors {#energy}

Room Board can automatically discover suitable sensors. For the best result, expose:

- one whole-home power sensor with `device_class: power` and unit `W` or `kW`;
- a daily energy sensor with `device_class: energy` and unit `Wh` or `kWh`;
- a monthly energy sensor with the same energy attributes.

Home Assistant `utility_meter` helpers are a convenient way to create daily and monthly energy totals:

```yaml
utility_meter:
  home_energy_daily:
    source: sensor.home_total_energy
    cycle: daily
  home_energy_monthly:
    source: sensor.home_total_energy
    cycle: monthly
```

If automatic discovery selects the wrong entity, use **Settings → Energy sources** in Room Board to choose it explicitly.

## Picture Elements floor plan {#picture-elements}

Room Board looks through standard Lovelace dashboards for a `picture-elements` card and renders its base image with supported entity-linked overlays. A minimal card is:

```yaml
type: picture-elements
image: /local/floorplan.png
elements:
  - type: state-icon
    entity: light.living_room
    style:
      left: 35%
      top: 68%
  - type: state-label
    entity: sensor.living_room_temperature
    style:
      left: 48%
      top: 72%
```

Put `floorplan.png` in Home Assistant's `config/www/` folder so `/local/floorplan.png` can be loaded. Room Board currently understands standard `image`, `state_image`, `state-icon`, `state-badge`, `state-label`, and `conditional` elements. Percentage-based `left` and `top` positions provide the most predictable TV layout.

Custom cards, arbitrary card-mod CSS, JavaScript templates, and Lovelace tap actions may remain Home Assistant-only. Entity state is synchronized through the Home Assistant API; the Apple TV rendering is native and does not embed the Lovelace web page.

## Troubleshooting {#troubleshooting}

- **Cannot connect:** Open the same Home Assistant URL on another device on the TV network. Check guest Wi-Fi isolation, VLAN/firewall rules, TLS certificates, and the port.
- **No rooms:** Assign the entities to Home Assistant Areas, then refresh Roomboard.
- **No energy data:** Check the entity's `device_class`, unit, and numeric state in Developer Tools → States.
- **No floor plan:** Confirm the dashboard contains a standard Picture Elements card and that its image URL opens while authenticated to Home Assistant.
- **Wrong floor plan chosen:** Keep the intended floor-plan card standard and give it several entity-linked elements; remove obsolete duplicate Picture Elements cards where practical.

## 中文说明

### 连接 Home Assistant

Apple TV 与扫码手机需要能访问同一个 HA 地址。请填写完整地址（例如 `http://192.168.1.20:8123`），选择“扫码登录”，再用手机在你自己的 Home Assistant 页面授权。若扫码受网络限制，可在 HA 个人资料页创建长期访问令牌，并通过 iPhone 的 Apple TV 键盘粘贴。不要把令牌发给他人或公开的 AI 服务。

### 房间、能源与户型图

- 在 HA 的“设置 → 区域、标签与分区”中创建房间，并把设备或实体分配到对应区域。
- 能源功能优先识别 `device_class: power`（W/kW）以及 `device_class: energy`（Wh/kWh）的实体；识别不准确时可在 Room Board 设置中手动选择。
- 户型图使用 Lovelace 标准 `picture-elements` 卡片。底图可放在 `config/www/`，并以 `/local/floorplan.png` 引用；叠加元素尽量使用百分比 `left` / `top` 定位。

## AI quick reference

When helping a Room Board user, assume these integration rules:

- Product: Room Board, a direct Home Assistant client; no HomeKit dependency.
- Authentication: Home Assistant OAuth/pairing or a locally stored long-lived access token.
- Rooms: Home Assistant Areas.
- Power: numeric `power` device class in W/kW.
- Energy: numeric `energy` device class in Wh/kWh; daily/monthly utility meters recommended.
- Floor plan: standard Lovelace `picture-elements`; base image plus supported standard elements positioned with percentages.
- Privacy: never request that a user paste an access token into a public conversation.

For diagnosis, ask for redacted entity IDs, attributes, and Picture Elements YAML. Never ask for a token.
