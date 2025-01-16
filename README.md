# React Native Dimensions API Returns Incorrect Dimensions Initially

This repository demonstrates a common bug in React Native where the `Dimensions` API returns incorrect or zero dimensions when the app first launches or when the screen orientation changes. This can lead to unexpected layout issues and rendering problems.

## Problem
The `Dimensions.get('window')` method doesn't always provide accurate dimensions immediately.  Often, it returns `width: 0` and `height: 0` initially. This issue is particularly noticeable when you try to use these dimensions to style components or perform layout calculations before the dimensions have been properly measured by React Native.

## Solution
The solution is to use the `Dimensions` API in conjunction with the `Dimensions.addEventListener` to listen to changes in dimensions, and then update the state accordingly. This approach guarantees that the dimensions are correctly updated as the screen dimensions change.  Alternatively, using `useEffect` hook with the `Dimensions` API makes the logic cleaner.