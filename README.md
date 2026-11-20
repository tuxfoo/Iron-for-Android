# Iron for Android 🏃‍♂️⌚

**Iron** is a modern, high-performance sports tracker for Android, designed to give your **Pebble Smartwatch** a second life as a professional-grade fitness tool.

Built with **Kotlin Multiplatform (KMP)**, Iron focuses on privacy, extensibility, and a seamless user experience—all without advertisements.

[![Get it on Google Play](https://play.google.com/intl/en_us/badges/static/images/badges/en_badge_web_generic.png)](https://play.google.com/store/apps/details?id=hag1987haaa.pebble.iron)
*(Google Play and the Google Play logo are trademarks of Google LLC.)*

---

## 🍴 About this fork

This is a fork of **[Iron](https://github.com/hag1987haaa/Iron-for-Android)** by hag1987haaa. It differs from the official app in two ways:

- **Calories are calculated from your Health Connect data.** Iron reads your latest **weight, height, body fat, resting heart rate, VO2max and BMR** from Health Connect, so the estimate keeps up as they change. If there's no resting heart rate record (for example, your watch app writes heart rate and sleep but not resting heart rate), Iron estimates it from your heart rate during sleep. The profile values you enter in Iron's settings are only used when Health Connect has no value. The official Iron only *writes* to Health Connect and uses the values you enter.
- **GPS works without Google Play Services** (e.g. GrapheneOS, or LineageOS without GApps). Iron uses Google's fused location when Play Services is available, and Android's own location service otherwise.

The calorie model itself, and the GPS fallback, have been proposed to the official app ([#8](https://github.com/hag1987haaa/Iron-for-Android/pull/8), [#7](https://github.com/hag1987haaa/Iron-for-Android/pull/7)). Reading from Health Connect is specific to this fork.

This fork isn't on Google Play: build it from source. It's signed with a different key, so it can't update the Google Play version of Iron.

---

## ✨ Key Features

- **Voice Assistant Integration**: Trigger Google Assistant or Gemini directly from your wrist by long-pressing a Pebble button. (Uses phone/headset mic).
- **Customizable "Cockpit" Display**: Choose from 12 real-time data types (Pace, HR, Cadence, Elevation Gain, Clock, etc.) to display in a large, easy-to-read format.
- **Smart Notifications**: Customizable auto-lap vibrations for distance (e.g., every 1km) and time intervals.
- **Advanced Data Export**: Support for both **GPX** and **TCX** formats. TCX includes heart rate, calories, and smoothed cadence data, perfect for Strava or Garmin Connect.
- **Rich Analytics**: Visual charts for speed, altitude, heart rate, and steps. Supports both distance-based and time-based analysis.
- **Pebble "Thin Client" Architecture**: High-speed rendering with dynamic labels generated on Android, ensuring stability and visual clarity on Pebble's screen.
- **Metric & Imperial Support**: One-tap switching between km/kg and mile/lb, including automatic weight conversion.
- **Automation Power**: Send broadcast intents on Pebble button actions or app state changes. Ideal for Tasker users.
- **Health Connect Integration**: Sync your Pebble-tracked HR and steps with Android's Health Connect.

---

## 🛠 Setup

1. Install the **Iron** app from the **[Google Play Store](https://play.google.com/store/apps/details?id=hag1987haaa.pebble.iron)**.
2. Install the **Iron for Pebble** watch app via a provider like **Cobble** or **Coreapp**.
3. Grant necessary permissions: Location (Always), Notifications, and "Display over other apps" (required for the Assistant trigger).
4. **This fork:** in Health Connect, allow Iron to read the body data you want used for calories (weight, height, body fat, resting heart rate, VO2max, BMR, plus heart rate and sleep for the resting heart rate estimate). Anything you don't allow falls back to the profile values in Iron's settings.

---

## 🤝 Heritage & Acknowledgments

The development of **Iron** stands on the shoulders of the open-source pioneers who kept the Pebble community alive. We would like to express our deepest gratitude to:

- **[RunnerUp](https://github.com/jonasoreland/runnerup)**: This incredible project proved that a Pebble could be a serious tracking companion. It was the spark that inspired the creation of Iron.
- **[OW Camera Remote](https://github.com/jamsinclair/ow-camera-remote)**: A vital reference that allowed us to finally master the implementation of **PebbleKit Android 2** (PebbleKit2). Without this example, our modern communication architecture wouldn't have been possible.

We respect and appreciate the original developers for their contribution to the Pebble ecosystem.

---

## 📄 Privacy Policy
Iron is built with a "Privacy First" mindset. No ads, no tracking.
👉 [Privacy Policy for Iron](https://hagtime.com/?page_id=364)

**This fork:** the policy above describes the official app, which doesn't read Health Connect. This fork reads the Health Connect data listed above, but only the types you allow. It uses them on your phone to calculate calories and doesn't send them anywhere.

### Contact
Developer: [hag1987haaa](https://x.com/1987haaa)

---

# Iron for Android (日本語) 🇯🇵

『Iron』は、Pebbleスマートウォッチをプロ仕様のフィットネスツールとして蘇らせる、現代的なAndroid用スポーツトラッカーです。

Kotlin Multiplatform (KMP) を採用し、広告なし、プライバシー重視、そして高度な拡張性を備えています。

**[Google Play ストアで手に入れる](https://play.google.com/store/apps/details?id=hag1987haaa.pebble.iron)**

---

## 🍴 このフォークについて

これは hag1987haaa 氏の **[Iron](https://github.com/hag1987haaa/Iron-for-Android)** のフォークです。公式版との違い:

- **消費カロリーをヘルスコネクトのデータから計算します。** 最新の体重・身長・体脂肪率・安静時心拍数・VO2max・基礎代謝をヘルスコネクトから読み取ります。安静時心拍数の記録がない場合は、睡眠中の心拍数から推定します。Iron の設定で入力した値は、ヘルスコネクトに値がない場合のみ使用されます。公式版はヘルスコネクトへの書き込みのみを行います。
- **Google Play 開発者サービスがなくても GPS が動作します**（GrapheneOS など）。

読み取ったデータはスマホ内でのカロリー計算にのみ使用され、外部には送信されません。このフォークは Google Play では配布していません。

---

## 📝 主な機能

- **ボイスアシスタント連携**: Pebbleのボタン長押しでGoogleアシスタントやGeminiを起動。（スマホまたはイヤホンのマイクを使用）
- **カスタマイズ可能な「コックピット」表示**: 12種類のデータ（ペース、心拍、ケイデンス、獲得標高、時計等）から好きな項目を選び、ウォッチ中段に特大表示可能。
- **スマート通知機能**: 距離ラップ（例：1kmごと）や時間インターバルを振動でお知らせ。
- **高度なデータ出力**: **GPX** に加え **TCX** 出力に対応. 心拍数、カロリー、平滑化されたケイデンス情報を含み、StravaやGarmin等へのアップロードに最適。
- **詳細な分析チャート**: 速度、高度、心拍数、歩数をグラフ化。距離ベースと時間ベースの切り替えに対応。
- **「Thin Client」通信設計**: ラベルや数値をスマホ側で動的に生成して送信。Pebble側での文字化けを防ぎ、視認性を最大化。
- **メートル/ヤード・ポンド法対応**: km/kg と mile/lb を一括切り替え。単位に合わせて体重設定も自動換算。
- **強力な自動化連携**: Pebbleの操作やアプリの状態変化をインテント送信。Tasker等の自動化アプリと連携可能。
- **Health Connect 完全対応**: ウォッチで記録したデータをAndroidのヘルスコネクトへシームレスに同期。

---

## 🤝 謝辞と経緯
『Iron』の開発は、Pebbleコミュニティを支え続けてきた素晴らしいオープンソースプロジェクトの存在なしには成し得ませんでした。

- **[RunnerUp](https://github.com/jonasoreland/runnerup)**: Pebbleが強力なトラッキングデバイスになり得ることを証明してくれたプロジェクトであり、Iron開発の最大のインスピレーションとなりました。
- **[OW Camera Remote](https://github.com/jamsinclair/ow-camera-remote)**: モダンな **PebbleKit Android 2** の実装方法を理解するための決定的な指針となりました。この例がなければ、現在の安定した通信環境は実現できませんでした。

先人たちの先駆的な活動と、Pebbleエコシステムへの貢献に深く感謝いたします。

---

## 📄 プライバシーポリシー
Ironは「プライバシー第一」で設計されています。広告やトラッキングコードは一切含まれていません。  
👉 [Iron プライバシーポリシー](https://hagtime.com/?page_id=364)

### お問い合わせ
開発者: [hag1987haaa](https://x.com/1987haaa)
