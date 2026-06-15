---
layout: page
title: Privacy Policy for Wand
permalink: /privacy/wand/
---

# Privacy Policy for Wand (如意)

**Last updated: June 15, 2026**

## Introduction

Wand turns your phone into a context-aware remote: you raise your phone toward a device at home and it shows the matching remote. It works with your own **Home Assistant** instance and with **Apple Home (HomeKit)**.

The short version: **your data stays on your device.** Wand has no account system of its own, no analytics, and no developer-operated servers. All recognition is computed on-device.

## Information the App Handles

*   **Connection credentials:** If you connect to Home Assistant, the server address and your access token (or the username/password you enter, which is exchanged for a token) are stored only on your device, in the iOS Keychain. They are sent only to the Home Assistant server you specify, to authenticate and control your devices.
*   **HomeKit data:** If you connect with Apple Home, the app reads your home's accessories, rooms, and their states through Apple's HomeKit framework, on your device, to match the device you aim at and to send control commands. This data is processed locally and is never uploaded. It is used only to provide remote-control features — never for advertising, tracking, or any other purpose.
*   **Motion & orientation (location/compass, gyroscope, barometer):** To recognize which device you are pointing at, the app reads your phone's heading (compass), tilt (gyroscope), and air pressure (barometer). These readings are turned into on-device "position fingerprints" and compared locally. They never leave your phone. The app does not track your geographic location and does not run in the background.
*   **Wi‑Fi information:** The name (SSID) and access-point identifier (BSSID) of the Wi‑Fi network you are connected to are read to help tell which room you are in. This stays on your device and is used only for on-device matching.
*   **Local network:** On your local network the app discovers Home Assistant instances (via Bonjour) and sends control commands to your devices. No content is sent anywhere else.

## Network Requests

Wand communicates only with the home systems you connect to: your own Home Assistant server (on your local network or the address you provide) and Apple's HomeKit on your device. These requests happen only for actions you take — loading your devices, reading their state, or controlling them. There are no developer-operated servers and no third-party analytics or tracking SDKs.

## Data Collection

We do not collect, store, transmit, or sell any of your data. Position fingerprints, learned spots, device lists, and credentials all live on your device. If you enable Apple's analytics or crash sharing on your device, Apple may process diagnostic data under Apple's own policies.

## Data Storage and Deletion

All of your data is stored locally on your device. You can clear all learned position data at any time from the app's Advanced settings, sign out to remove connection credentials, and deleting the app removes everything it stored.

## In-App Purchases

Wand Pro is available as a one-time (lifetime) purchase or an auto-renewing subscription, processed entirely by Apple. We receive no personal or payment information from the transaction. Subscriptions renew unless cancelled at least 24 hours before the period ends; you can manage or cancel them in your Apple account settings.

## Children's Privacy

Wand is not directed at children and does not knowingly collect any information from anyone.

## Changes to This Privacy Policy

We may update this Privacy Policy from time to time by publishing the revised version on this page.

## Contact Us

If you have any questions about this Privacy Policy, please contact us at:

*   **Email:** dcyap0@icloud.com

---

# 如意 (Wand) 隐私政策

**最后更新：2026 年 6 月 15 日**

## 简介

如意(Wand)把手机变成一只"懂情境"的遥控器:举起手机对准家里的设备,它就显示对应的遥控界面。它支持你自己的 **Home Assistant** 实例以及 **Apple 家庭(HomeKit)**。

简单说:**你的数据只留在你的设备上**——没有我们的账号系统、没有数据分析、没有我们运营的服务器,所有识别都在本机完成。

## 应用处理的信息

*   **连接凭据**:连接 Home Assistant 时,服务器地址和你的访问令牌(或你输入的账号密码,会换取令牌)只保存在本机的 iOS 钥匙串中,且只发送给你指定的 Home Assistant 服务器用于认证和控制设备。
*   **HomeKit 数据**:连接 Apple 家庭时,应用通过 Apple 的 HomeKit 框架在本机读取你"家庭"中的配件、房间及其状态,用于把你对准的设备匹配成遥控器并发送控制指令。这些数据仅在本机处理、从不上传,只用于遥控功能,绝不用于广告、跟踪或任何其他用途。
*   **运动与朝向(定位/罗盘、陀螺仪、气压计)**:为识别你正对着哪台设备,应用会读取手机的朝向(罗盘)、姿态(陀螺仪)和气压(气压计),在本机生成"位置指纹"并本地比对,这些数据从不离开手机。应用不跟踪你的地理位置,也不在后台运行。
*   **Wi‑Fi 信息**:读取你已连接 Wi‑Fi 的名称(SSID)与接入点标识(BSSID),用于辅助判断你在哪个房间,仅保存在本机用于本地匹配。
*   **局域网**:在局域网内发现 Home Assistant 实例(通过 Bonjour)并向你的设备发送控制指令,不会把内容发往别处。

## 网络请求

如意 只与你连接的家居系统通信:你自己的 Home Assistant 服务器(局域网或你提供的地址)以及本机的 Apple HomeKit。这些请求只在你主动操作(加载设备、读取状态、控制设备)时发生。没有任何我们运营的服务器,也没有第三方统计或跟踪 SDK。

## 数据收集

我们不收集、不存储、不传输、不出售你的任何数据。位置指纹、已学习的位置、设备列表和凭据都只存在你的设备上。若你在设备上开启了 Apple 的分析或崩溃共享,Apple 可能依据其自身政策处理诊断数据。

## 数据存储与删除

你的全部数据均存储在本机。你可随时在应用的"高级设置"中清除全部已学习的位置数据,通过退出登录移除连接凭据;删除应用即可清除其存储的一切。

## 内购

如意 Pro 提供一次性(永久)购买或自动续期订阅,全部由 Apple 处理交易,我们不会获得任何个人或支付信息。订阅会在到期前 24 小时自动续期,除非提前取消;你可在 Apple 账户设置中管理或取消。

## 儿童隐私

如意 并非面向儿童,也不会有意收集任何人的信息。

## 政策变更

我们可能会不时更新本隐私政策,并在本页发布修订后的版本。

## 联系我们

如对本隐私政策有任何疑问,请联系:

*   **邮箱:** dcyap0@icloud.com
