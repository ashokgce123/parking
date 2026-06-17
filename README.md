# ParkingPay - Android App

A minimal Android app that opens Google Pay with a UPI payment request and closes automatically.

## Features

- **Single Activity Design**: Lightweight with only MainActivity
- **No UI Layout**: No XML layouts required
- **Direct Payment Intent**: Launches Google Pay with pre-filled UPI payment details
- **Auto-Close**: App closes after launching Google Pay
- **Production Clean**: Minimal and optimized code

## Payment Details

- **Payee**: gpay-12196767649@okbizaxis
- **Payee Name**: Parking
- **Amount**: ₹15 INR
- **Payment Method**: UPI via Google Pay

## Package Structure

```
com.example.parkingpay
├── MainActivity.java       (Single Activity)
└── AndroidManifest.xml     (Configuration)
```

## How It Works

1. User taps the app icon
2. MainActivity launches in onCreate()
3. UPI deep link is constructed with payment details
4. Intent is created to open Google Pay (com.google.android.apps.nbu.paisa.user)
5. Google Pay opens with ₹15 pre-filled
6. ParkingPay app closes automatically via finish()

## Prerequisites

- Android SDK 21 or higher
- Google Pay app installed on device

## Building

```bash
./gradlew build
./gradlew installDebug
```

## Permissions

No special permissions required beyond standard Internet access (for payment processing).

## Notes

- The app forces Google Pay specifically to avoid app chooser dialogs
- If Google Pay is not installed, the exception is caught gracefully
- The app closes immediately after launching the payment intent
- UPI link format: `upi://pay?pa=...&pn=...&am=...&cu=...`
