# Expo Linking.getInitialURL() Inconsistent Behavior on Android

This repository demonstrates a bug in Expo's `Linking.getInitialURL()` API on Android.  The function sometimes returns `null` even when the app is opened via a deep link, leading to unexpected behavior in apps that rely on deep linking for initial state handling.

## Problem

The `Linking.getInitialURL()` method is unreliable on Android.  It often correctly returns the deep link URL. However, in some instances, it returns `null`, even when the app has been launched directly from a deep link.  This inconsistency creates difficulty in reliably handling initial deep links.

## Reproduction Steps

1. Clone this repository.
2. Run the project on an Android device or emulator.
3. Open a deep link to the app. 
4. Observe that `Linking.getInitialURL()` sometimes returns null, despite being launched from the deep link.

## Solution

A potential workaround is provided in `bugSolution.js`. Although a definitive fix requires changes within the Expo Linking API itself, this workaround can improve reliability in many cases.