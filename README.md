# izbank Mobile Banking App

izbank is a native Android mobile banking application built in Java. It includes user registration and login, account and card management, money transfer flows, bill payments, credit requests, profile settings, and a crypto finance screen that fetches market data from an external API.

The repository also includes Figma design files, gallery screenshots, a demo video, and a prebuilt debug APK.

## Screenshots

| Sign In | Sign Up | Home | Log Out |
| --- | --- | --- | --- |
| ![Sign In](Gallery/Sign%20In%20Page.jpg) | ![Sign Up](Gallery/Sign%20Up%20Page.jpg) | ![Home](Gallery/Home%20Page.jpg) | ![Log Out](Gallery/Log%20Out%20Page.jpg) |

## Features

- User sign up and sign in with Parse/Back4App authentication
- Personal profile with editable name, phone number, address, password, profession, and profile image
- Bank account and credit card listing
- Add bank accounts and credit cards
- Send and request money between users
- Transaction history
- Bill payment support for electric, gas, internet, phone, and water bills
- Credit request flow based on profession-specific limits, installment counts, and interest rates
- Crypto market listing, search, purchase flow, and owned crypto view
- Admin panel flow for the special admin user

## Tech Stack

- Java
- Android SDK
- AndroidX
- Material Components
- RecyclerView
- Retrofit and Gson
- RxJava/RxAndroid
- Parse Android SDK / Back4App
- Picasso
- AndroidSvgLoader
- Gradle Android Plugin 4.1.3

## Project Structure

```text
.
├── APK File/                     # Prebuilt debug APK
├── Figma Designs/                # Source design files and exported assets
├── Gallery/                      # README/gallery screenshots
├── Mobile Banking App/           # Android Studio project
│   ├── app/
│   │   └── src/main/
│   │       ├── java/com/bank/izbank/
│   │       │   ├── Adapters/     # RecyclerView adapters
│   │       │   ├── Bill/         # Bill domain models
│   │       │   ├── Credit/       # Credit domain models/events
│   │       │   ├── Job/          # Profession-based credit rules
│   │       │   ├── MainScreen/   # Main app fragments and activities
│   │       │   ├── Sign/         # Sign in and sign up flows
│   │       │   ├── UserInfo/     # User, account, card, address, history models
│   │       │   ├── database/     # Parse initialization
│   │       │   └── service/      # Retrofit API interfaces
│   │       └── res/              # Layouts, drawables, menus, and values
│   └── build.gradle
└── PROJECT VIDEO/                # Demo video
```

## Requirements

- Android Studio
- JDK 8 or compatible Java toolchain
- Android SDK Platform 30
- Android SDK Build Tools 30.0.3
- An Android emulator or physical Android device

## Getting Started

1. Clone the repository.

   ```bash
   git clone <repository-url>
   cd bankapp-master
   ```

2. Open the Android project in Android Studio.

   Select the `Mobile Banking App` directory as the project root.

3. Let Gradle sync the project.

4. Run the app from Android Studio on an emulator or connected Android device.

The launcher activity is `com.bank.izbank.Sign.SignIn`.

## Command Line Build

From the Android project directory:

```bash
cd "Mobile Banking App"
./gradlew assembleDebug
```

The generated APK will be created under:

```text
Mobile Banking App/app/build/outputs/apk/debug/
```

A prebuilt debug APK is also included at:

```text
APK File/app-debug.apk
```

## Backend and API Notes

The app initializes Parse in `Mobile Banking App/app/src/main/java/com/bank/izbank/database/ParseStarterClass.java` and uses Back4App as the Parse server.

Crypto data is loaded through Retrofit in `Mobile Banking App/app/src/main/java/com/bank/izbank/service/ICryptoAPI.java`.

This project currently contains API keys in source code. For production or public distribution, move those values into local Gradle properties, environment-specific configuration, or a secure backend so secrets are not committed to version control.

## Tests

The project includes the default Android unit and instrumentation test stubs:

```bash
cd "Mobile Banking App"
./gradlew test
./gradlew connectedAndroidTest
```

`connectedAndroidTest` requires an emulator or connected device.

## Design Assets

- Figma source: `Figma Designs/Mobile Banking App.fig`
- Design PDF: `Figma Designs/Mobile Banking App.pdf`
- Additional exported design screens: `Figma Designs/Extras/`
- Demo video: `PROJECT VIDEO/PROJECT_ZIP.MP4`

## Package

```text
com.bank.izbank
```

## License

No license file is currently included in this repository. Add a license before distributing or reusing the project publicly.
# izmobilebanking
