# Expo Camera Multiple Barcode Scans

This repository demonstrates a bug in Expo's Camera component where the `onBarCodeScanned` callback function is triggered multiple times for a single barcode scan. This can lead to performance issues and unexpected behavior in your application.

## Bug Description

The `onBarCodeScanned` function, designed to be called once per successful barcode scan, is instead firing repeatedly for the same barcode.  This issue is inconsistent and appears more frequently under certain conditions like fast barcode scanning or low-light environments.

## Reproduction

1. Clone this repository.
2. Install dependencies: `npm install` or `yarn install`.
3. Run the app using Expo Go or EAS Build.
4. Scan a barcode. Observe the console logs to see the function being called multiple times.

## Solution

The solution involves debouncing the `onBarCodeScanned` callback to prevent multiple executions within a specific timeframe.  The provided solution implements a simple debounce mechanism to address the issue.

## Note

This bug's frequency and severity may vary depending on the device, Expo SDK version, and environmental factors.