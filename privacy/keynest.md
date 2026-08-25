---
layout: page
title: Privacy Policy for KeyNest
permalink: /privacy/keynest/
---

# Privacy Policy for KeyNest

**Last updated: August 25, 2026**

## Introduction

KeyNest is an iOS app for storing and managing your own AI API keys. This Privacy Policy explains what data the app handles and where that data lives.

The short version: your API keys stay on your device. KeyNest has no account system and never uploads your keys. It does send anonymous product-usage statistics, described under [Data Collection](#data-collection) below.

## Information the App Handles

*   **API keys and metadata:** The API keys you add, together with names, notes, base URLs, validation status, balance snapshots, and usage records, are stored only on your device. Keys themselves are stored encrypted in the iOS Keychain; metadata is stored in the app's local storage with iOS data protection.
*   **Face ID:** KeyNest uses the system's Local Authentication framework to gate unlocking, revealing, copying, and deleting keys. Biometric data never leaves the Secure Enclave and is never visible to the app.
*   **Camera:** The camera is used only to scan KeyNest share QR codes. No images are stored or transmitted.
*   **Local network:** When you use nearby sharing, the app uses Bluetooth and the local network to transfer an end-to-end encrypted payload directly between your two devices.

## Network Requests

KeyNest contacts AI providers' official APIs (such as OpenAI, Anthropic, DeepSeek, or a custom endpoint you configure) directly from your device, and only for actions you take: validating a key, fetching model lists, or checking balances. These requests carry the relevant API key to the provider you added it for — never anywhere else. Your use of each provider remains subject to that provider's own terms and privacy policy.

Separately, the app sends the anonymous usage statistics described below to an endpoint we operate. Those requests never contain an API key or any content you entered.

## Data Collection

KeyNest records anonymous product-interaction events so we can see which features are actually used and decide what to build next.

An event consists of an event name drawn from a fixed list (for example `key_created`) plus a small set of enumerated property codes. Property values are restricted to a whitelist and truncated to 80 characters. Each event also carries the app version, build number, platform, and coarse locale (for example `en-US`).

Events carry **no device identifier, no advertising identifier, and no account identifier**. The per-event and per-purchase-flow IDs are randomly generated each time and are never reused or persisted across launches, so events cannot be linked back to you or joined into a profile. We never collect API key values, key names, base URLs, notes, balance figures, or any other content you enter.

Events are queued on device and sent in batches to an endpoint we operate. They are never shared with or sold to third parties, and are never used for advertising or cross-app tracking.

This app does not currently offer a setting to turn usage statistics off. If you enable Apple's analytics or crash sharing on your device, Apple may additionally process diagnostic data under Apple's policies.

## Sharing and Backups

Keys leave your device only when you explicitly export or share them, and always in encrypted form: QR share codes and nearby transfers use AES-GCM encryption with a time-limited key, password, or pairing code; backup files are encrypted with a password you choose. We cannot read or recover any of these — if a password is lost, the data is unrecoverable.

## In-App Purchases

KeyNest Pro is a one-time purchase processed entirely by Apple. We receive no personal or payment information from the transaction.

## Changes to This Privacy Policy

We may update this Privacy Policy from time to time by publishing the revised version on this page.

## Contact Us

If you have any questions about this Privacy Policy, please contact us at:

*   **Email:** dcyap0@icloud.com

---

# KeyNest 隐私政策

**最后更新：2026 年 8 月 25 日**

KeyNest 是一款用于保管你自己的 AI API 密钥的 iOS 应用。简单说：**你的密钥只留在你的设备上**——没有账号系统，密钥绝不上传。应用会发送匿名的功能使用统计，详见下方「数据收集」。

*   **密钥与元数据**：你添加的 API 密钥加密存储在 iOS 钥匙串中；名称、备注、验证状态、余额等元数据存储在设备本地。
*   **面容 ID**：仅用于本机解锁和敏感操作确认，生物特征数据由系统安全隔区处理，应用无法访问。
*   **相机**：仅用于扫描 KeyNest 分享二维码，不存储、不上传任何图像。
*   **网络请求**：应用只在你主动操作（验证密钥、获取模型列表、查询余额）时，从你的设备直接访问对应 AI 服务商的官方 API，密钥只会发送给它所属的服务商。此外，应用会将下方所述的匿名使用统计发送到我们运营的端点，这些请求不包含任何密钥或你输入的内容。
*   **分享与备份**：密钥只在你主动导出或分享时离开设备，且始终为加密形式（AES-GCM 加密的二维码/隔空传输，或密码保护的备份文件）。我们无法读取或找回这些数据。
*   **数据收集**：应用会记录匿名的功能使用事件，用于了解哪些功能被真正使用、决定后续开发方向。一条事件由固定清单中的事件名（如 `key_created`）和少量枚举属性代码构成，属性值经白名单限制并截断至 80 字符；同时附带应用版本、构建号、平台和粗粒度语言区域（如 `zh-Hans`）。事件**不含设备标识符、广告标识符或账号标识符**，其中的单次事件 ID 与购买流程 ID 每次随机生成、不重复使用、不跨启动保留，因此无法关联到你本人或拼接成用户画像。我们绝不收集密钥内容、密钥名称、Base URL、备注、余额数字或你输入的任何其他内容。事件在设备上排队后分批发送至我们运营的端点，绝不共享或出售给第三方，也绝不用于广告或跨应用追踪。目前应用内没有关闭使用统计的开关。
*   **内购**：KeyNest Pro 由 Apple 处理交易，我们不会获得任何个人或支付信息。

如有疑问，请联系：**dcyap0@icloud.com**
