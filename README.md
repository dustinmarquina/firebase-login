# Firebase Login App (Flutter)

DEMO:


https://github.com/user-attachments/assets/92652f2b-4142-464c-8b30-fb1335078b04



Minimal Flutter app demonstrating Firebase Authentication with email/password.

What this includes
- `firebase_core` and `firebase_auth` in `pubspec.yaml`
- `lib/main.dart` initializes Firebase and uses a `StreamBuilder` on `FirebaseAuth.instance.authStateChanges()` to show login/register forms or the home screen.

Quick setup
1. Install Flutter and ensure `flutter` is on your PATH.
2. From the project root run:

```bash
flutter pub get
```

3. Configure Firebase for your platforms:

- Android: add `google-services.json` to `android/app/` and apply the Gradle config as described in Firebase docs.
- iOS: add `GoogleService-Info.plist` to `Runner/` in Xcode.

Easiest option: install the FlutterFire CLI and run `flutterfire configure` to generate `firebase_options.dart` and wire platforms automatically.

```bash
dart pub global activate flutterfire_cli
flutterfire configure
```

4. Run the app:

```bash
flutter run
```

Notes and troubleshooting
- The app's `main.dart` calls `Firebase.initializeApp()` with default options; for mobile you either need platform config files (json/plist) or a generated `firebase_options.dart` from `flutterfire configure`.
- If you see package import errors in your editor (e.g. `package:firebase_core` not found), run `flutter pub get` and ensure the Flutter SDK is correctly selected in your IDE.

**IMPORTANT: Enable Email/Password sign-in provider**
The app requires the Email/Password authentication provider to be enabled in your Firebase project:
1. Go to the [Firebase Console](https://console.firebase.google.com/)
2. Select your project (the one you selected during `flutterfire configure`)
3. Navigate to **Authentication** → **Sign-in method** tab
4. Click on **Email/Password** in the providers list
5. Toggle **Enable** to ON
6. Click **Save**

Without enabling this provider, you'll see errors like: "The given sign-in provider is disabled for this Firebase project."

What's next (suggested)
- Add `firebase_options.dart` by running `flutterfire configure` or follow the manual platform setup.
- Optionally add email verification, password reset, and nicer error handling.

Files created
- `pubspec.yaml` — dependencies
- `lib/main.dart` — app with auth UI
- `README.md` — this file

If you'd like, I can:
- Run `flutter pub get` for you (if your machine has Flutter in PATH). 
- Run the app and check the auth flow.
- Add `flutterfire configure` steps and generate `firebase_options.dart` (requires Firebase project details).
