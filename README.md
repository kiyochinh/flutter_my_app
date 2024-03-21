# 🚀 Flutter CI/CD Template

![Flutter CI/CD Workflow](assets/git_workflow.jpg)

Welcome to the Flutter CI/CD & Branching Template 🛠️, meticulously crafted to supercharge 🌟 your Flutter app development and deployment for Android 📱 and iOS 🍏 platforms. By harnessing the power of GitHub Actions, this template ensures a seamless and efficient automation process from code commit to production release.

## 🌈 Features

### 📈 Version Management
- **Auto Version Bumping:** Automagically increments app version based on PR labels (`major`, `minor`, `patch`) for merges into the `develop` branch, with shiny new tags created for each version.

### 🛠️ Testing & Deployment
- **PR Analysis & Testing:** Runs automated tests 🧪 for pull requests targeting the `develop` branch.
- **Build Number Incrementation:** Smartly increments build numbers for merges into the `staging` branch.
- **Android Deployment:** Zaps deployment to Google Play's testing track, triggered by specific PR labels.
- **iOS Deployment:** Whisks away your app to TestFlight and Firebase for thorough testing.

### 📢 Notifications & Promotions
- **Tester Notifications:** Sends alerts 🚨 to testers via Slack, Telegram, etc., upon new builds.
- **Production Promotions:** Smoothly promotes Android and iOS builds to production on merges into the `main` branch.
- **User Notifications:** Keeps users in the loop about new releases through various channels.

### 📦 Release Management
- **Automated Release Notes:** Crafts release notes based on PRs merged into the `main` branch.
- **Manual Workflows:** Flexibility with manual triggers for those special deployment and promotion tasks.

## 🚀 Getting Started

### 1. Template Usage
   - Smash that `Use this template` button at the top and select `Include all branches` for the full experience.

### 2. Secrets Configuration
   Ensure your repository secrets 🤫 are set up in the repository settings:

   #### 2.1 iOS Secrets
   - `BUILD_CERTIFICATE_BASE64`: Base64 encode your iOS build certificate using the command below and paste the clipboard contents (⌘-V) into the textbox labeled Secret.
     ```
     $ base64 -i Certificates.p12 | pbcopy
     ```
   - `P12_PASSWORD`: Copy the password you used to export your signing certificate to the clipboard and then paste it into the textbox labeled Secret.
     ```
     $ pass -c personal/apple/certs/Team_ID
     ```
   - `BUILD_PROVISION_PROFILE_BASE64`: Base64 encode your mobile provisioning profile using the command below and paste the clipboard contents (⌘-V) into the textbox labeled Secret.
     ```
     $ base64 -i My_App_Provisioning.mobileprovision | pbcopy
     ```
   - `KEYCHAIN_PASSWORD`: Copy the password you created for macOS runner’s Keychain to the clipboard and then paste it into the textbox labeled Secret.
     ```
     $ pass -c temp/temp
     ```
   - `EXPORT_OPTIONS_PLIST`: Base64 encode the `ExportOptions.plist` file using the command below and paste the clipboard contents (⌘-V) into the textbox labeled Secret.
     ```
     $ base64 -i ExportOptions.plist | pbcopy
     ```

   #### 2.2 Android Secrets
   - `PLAY_STORE_UPLOAD_KEY`: Base64 encoded Android keystore file.
   - `KEYSTORE_STORE_PASSWORD`, `KEYSTORE_KEY_PASSWORD`, `KEYSTORE_KEY_ALIAS`: Android keystore details.

   #### 2.3 General Secrets
   - `FIREBASE_APP_ID_IOS`, `FIREBASE_APP_ID_ANDROID`: Firebase App IDs for distribution.
   - `FIREBASE_TOKEN`: Token for Firebase CLI operations.
   - `SLACK_WEBHOOK_URL`, `SLACK_CHANNEL_QA`, `SLACK_CHANNEL_DEV`: Slack integration details for notifications.
   - `SLACK_MENTIONS_QA`: `<@SLACK_ID>`, `<@SLACK_ID>`
   - `SLACK_MENTIONS_DEV`: {"GITHUB_ID": "SLACK_ID", "GITHUB_ID": "SLACK_ID"}

### 3. Label Setup
   - Don't forget to create those essential labels for versioning (`major`, `minor`, `patch`) and environment tracking (`production`, `staging`, `develop`).

## 🧭 Workflow Overview

- **Build and Deployment:** Automates the building and deploying of iOS and Android apps, ensuring every merge feels like a breeze.
- **Notifications:** Keeps the whole team in sync with Slack notifications, making sure everyone's on the same beat.

## 🤝 Contributing

Got an idea or spot a bug? 🐛 We love contributions! Fork 🍴 the project, submit your blazing 🔥 pull requests, or open up an issue.

## 📜 License

Freedom awaits! Specify the license under which the template is made available.