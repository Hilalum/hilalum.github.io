---
layout: page
title: Privacy Policy for KeyNest
permalink: /privacy/keynest/
---

# Privacy Policy for KeyNest

**Last updated: June 12, 2026**

## Introduction

KeyNest is an iOS app for storing and managing your own AI API keys. This Privacy Policy explains what data the app handles and where that data lives.

The short version: your data stays on your device. KeyNest has no account system, no analytics, and no servers of its own.

## Information the App Handles

*   **API keys and metadata:** The API keys you add, together with names, notes, base URLs, validation status, balance snapshots, and usage records, are stored only on your device. Keys themselves are stored encrypted in the iOS Keychain; metadata is stored in the app's local storage with iOS data protection.
*   **Face ID:** KeyNest uses the system's Local Authentication framework to gate unlocking, revealing, copying, and deleting keys. Biometric data never leaves the Secure Enclave and is never visible to the app.
*   **Camera:** The camera is used only to scan KeyNest share QR codes. No images are stored or transmitted.
*   **Local network:** When you use nearby sharing, the app uses Bluetooth and the local network to transfer an end-to-end encrypted payload directly between your two devices.

## Network Requests

KeyNest contacts AI providers' official APIs (such as OpenAI, Anthropic, DeepSeek, or a custom endpoint you configure) directly from your device, and only for actions you take: validating a key, fetching model lists, or checking balances. These requests carry the relevant API key to the provider you added it for — never anywhere else. Your use of each provider remains subject to that provider's own terms and privacy policy.

## Data Collection

We do not collect, store, transmit, or sell any of your data. There are no analytics SDKs, no tracking, and no developer-operated servers. If you enable Apple's analytics or crash sharing on your device, Apple may process diagnostic data under Apple's policies.

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

**最后更新：2026 年 6 月 12 日**

KeyNest 是一款用于保管你自己的 AI API 密钥的 iOS 应用。简单说：**你的数据只留在你的设备上**——没有账号系统、没有数据分析、没有我们运营的服务器。

*   **密钥与元数据**：你添加的 API 密钥加密存储在 iOS 钥匙串中；名称、备注、验证状态、余额等元数据存储在设备本地。
*   **面容 ID**：仅用于本机解锁和敏感操作确认，生物特征数据由系统安全隔区处理，应用无法访问。
*   **相机**：仅用于扫描 KeyNest 分享二维码，不存储、不上传任何图像。
*   **网络请求**：应用只在你主动操作（验证密钥、获取模型列表、查询余额）时，从你的设备直接访问对应 AI 服务商的官方 API，密钥只会发送给它所属的服务商。
*   **分享与备份**：密钥只在你主动导出或分享时离开设备，且始终为加密形式（AES-GCM 加密的二维码/隔空传输，或密码保护的备份文件）。我们无法读取或找回这些数据。
*   **数据收集**：我们不收集、不存储、不传输、不出售你的任何数据，无任何统计或跟踪 SDK。
*   **内购**：KeyNest Pro 由 Apple 处理交易，我们不会获得任何个人或支付信息。

如有疑问，请联系：**dcyap0@icloud.com**
