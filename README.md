# Meditation App

A native Android application for running, scheduling and recording mindfulness and breathing sessions. It combines guided session experiences with reminders, calendar-based planning, local persistence and streak tracking.

## Features

- Timed mindfulness sessions with looping forest or ocean audio
- Configurable breathing exercises with animated inhale and exhale phases
- Immediate sessions or sessions scheduled for a future date and time
- Daily reminders and per-session notifications
- Calendar view with day-by-day session management
- Optional export of scheduled sessions to the Android calendar
- Local SQLite storage exposed through an Android `ContentProvider`
- Automatic session-status updates and completion history
- Meditation streak calculation and Android share integration
- Portrait and landscape layouts for the main workflows

## Technology

- Java 8 source compatibility
- Android SDK 33, minimum SDK 28
- Android Gradle Plugin 7.4.2 and Gradle 7.5
- Material Components and AndroidX
- SQLite, services, broadcast receivers, alarms and notifications

## Building

The easiest route is to open the repository in Android Studio and allow it to install the required SDK components.

From a configured Android development environment, the debug build can also be produced with:

```sh
./gradlew assembleDebug
```

Install it on a connected device or emulator with:

```sh
./gradlew installDebug
```

Android will request the relevant notification and calendar permissions when those integrations are used.

## Project structure

| Area | Main classes |
| --- | --- |
| Home and navigation | `MainActivity`, `FooterActivity`, `SessionTypeActivity` |
| Guided sessions | `MindfulnessSessionActivity`, `BreathingSessionActivity` |
| Planning | `ViewCalendarActivity`, `AddSessionActivity`, `ViewMeditationSessionsActivity` |
| Persistence | `DatabaseHelper`, `MeditationContentProvider`, `MeditationContract` |
| Reminders and maintenance | `AlarmReceiver`, `UpdateService` |

## Status

This is an educational Android project and is not published to an app store. It demonstrates a complete multi-screen application, but production release work such as broader device testing, accessibility review and modern Android permission/alarm handling remains outside its original scope.
