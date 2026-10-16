<div align="center">

# AttendEase

**Attendance management app for Akal University**

A Flutter application with attendance-related dashboards and supporting academic workflows.

[Features](#features) · [Screenshots](#screenshots) · [Getting Started](#getting-started) · [Build Locally](#build-locally) · [Project Structure](#project-structure)

[![Flutter](https://img.shields.io/badge/Flutter-3.32%2B-02569B?logo=flutter&logoColor=white)](https://flutter.dev/)
[![Dart](https://img.shields.io/badge/Dart-3.8%2B-0175C2?logo=dart&logoColor=white)](https://dart.dev/)
[![Backend](https://img.shields.io/badge/Backend-Supabase-3FCF8E?logo=supabase&logoColor=white)](https://supabase.com/)

</div>

---

## Overview

AttendEase is an attendance-focused application built with **Flutter** for Akal University. The repository contains student, faculty, and management-oriented screens, attendance and performance modules, communication-related components, and Supabase integration.

This repository is intended to make the source code, setup process, and project decisions easy to review. Feature availability may depend on backend configuration and the account/role used to sign in.

## Features

The current source tree includes modules for:

- **Student dashboard**
- **Faculty interface**
- **Management dashboard**
- **Attendance workflows**
- **Performance-related views**
- **Leave-related services**
- **Communication and message threads**
- **Excel report export**
- **Attachment viewing**
- **Supabase-backed application services**
- **Image selection and local notifications**

Some features require a correctly configured Supabase project. The list above describes modules present in the repository; it does not guarantee that a hosted backend or public demo account is available.

## Screenshots

Screenshots help reviewers understand the app before setting up the development environment. Add real screenshots from a running build to `docs/screenshots/` and use the relative paths below. GitHub renders repository-relative image paths in the README. See [GitHub's image and Markdown guide](https://docs.github.com/en/get-started/writing-on-github/getting-started-with-writing-and-formatting-on-github/basic-writing-and-formatting-syntax#images).

Create these files (or change the names to match your screens):

| Student dashboard | Attendance screen | Management dashboard |
|---|---|---|
| ![Student dashboard](docs/screenshots/student1.png) | ![Attendance screen](docs/screenshots/attendance.png) | ![Management dashboard](docs/screenshots/management-dashboard.png) |

**Before adding screenshots**
- Capture the real application on an emulator or device.
- Use test/demo data only; hide student names, IDs, attendance records, messages, email addresses and other personal information.
- Use descriptive filenames without spaces.
- Preview the README after committing to confirm the images render.
- If you do not yet have screenshots, leave this section as a reminder and remove the empty image table until the files exist.

## Technology stack

- **Flutter** and **Dart** for the application
- **Supabase Flutter** for backend integration
- **Excel** package for spreadsheet export
- **File Saver** for saving exported files
- **Image Picker** for selecting images
- **Flutter Local Notifications** for local notifications

See [`pubspec.yaml`](pubspec.yaml) for the authoritative dependency list and version constraints.

## Getting Started

### Prerequisites

Install the following before building:

- Flutter SDK compatible with the project's Dart SDK constraint (`^3.8.1`)
- Dart SDK supplied with Flutter
- Git
- Android Studio or Android SDK tooling for Android builds

Verify your installation:

```bash
flutter --version
flutter doctor
```

### 1. Clone the repository

```bash
git clone https://github.com/messycodechaos/attendence_app.git
cd attendence_app
```

### 2. Install dependencies

```bash
flutter pub get
```

### 3. Configure Supabase

The project contains `supabase_config.dart` and uses `supabase_flutter`. Before running the app:

1. Create or obtain access to a Supabase project you are authorized to use.
2. Review `supabase_config.dart` and the initialization code in `main.dart` to identify how the app receives the Supabase project URL and client key.
3. Configure the project URL and **publishable/anon client key** using the mechanism expected by the current code.
4. Ensure the database schema, authentication setup, and Row Level Security (RLS) policies required by the app are configured in your Supabase project.

**Security notes**
- Never put a Supabase `service_role` key, database password, private signing key, or other privileged secret in client-side Flutter code.
- A publishable/anon key is designed for client use, but it is not a substitute for correct authentication and RLS policies.
- Do not commit local secret/configuration files. If configuration is currently hard-coded, refactor it before publishing sensitive values; adding a file to `.gitignore` does not remove secrets already committed to Git history.
- Do not use production student data for local development or screenshots.

The exact database schema and required policies are application-specific and are not generated by `flutter pub get`.

### 4. Run the application

Connect an Android device or start an emulator, then run:

```bash
flutter devices
flutter run
```

The app may not be fully functional until Supabase and any required backend data are configured.

## Build Locally

You can build and run the application locally after installing the required Flutter and Android tooling.

```bash
flutter pub get
flutter run
```

To build an Android APK for your own testing:

```bash
flutter build apk --debug
```

The debug APK is normally created at `build/app/outputs/flutter-apk/app-debug.apk`.

A downloadable APK is not currently provided by this repository. This keeps the project focused on source code and documentation; reviewers can inspect the implementation or build it locally. 

## Project Structure

The repository currently includes these notable files/modules:

```text
.
├── android/                    # Android platform project
├── assets/images/              # App image assets
├── ios/                        # iOS platform project
├── lib/                        # Flutter source directory (also present in repository)
├── test/                       # Automated tests
├── main.dart                   # Application entry point (as currently listed)
├── student_dashboard.dart
├── faculity.dart               # Faculty interface (filename as currently committed)
├── attendance.dart
├── admin.dart
├── management_dashboard.dart
├── performance_page.dart
├── communication_page.dart
├── message_thread_page.dart
├── excel_export.dart
├── notification_service.dart
├── supabase_config.dart
├── pubspec.yaml                # Package metadata and dependencies
└── README.md
```

This is a high-level guide, not an exhaustive file listing. Keep this section aligned with the actual repository if files are renamed or moved.

## Quality Checks

Before submitting a change, run:

```bash
flutter pub get
flutter analyze
flutter test
```

Resolve any new analyzer errors and test failures caused by your changes. If a test suite is not yet comprehensive, mention that limitation rather than implying all behavior is covered.

## Contributing

Bug reports and improvements are welcome. Please read [`CONTRIBUTING.md`](CONTRIBUTING.md) before opening an issue or pull request.


## License

This project is intended to be open source. A license has legal implications; before publishing one, confirm that you own or are authorized to license all code, assets, and project materials in this repository. If approved, the MIT License is a simple permissive option. See [`LICENSE`](LICENSE) and replace its copyright placeholder before committing.

---

<div align="center">

Built with Flutter.

</div>
