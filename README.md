# Expo console object keys reproduction

Minimal Expo app reproducing an issue where `console.log()` displays JavaScript object property keys with quotes in the Expo/React Native console.

## Issue

The app logs this object:

```js
{ name: 'John Doe', age: 25 }
```

Expected/browser-style output:

```text
{ name: "John Doe", age: 25 }
```

Actual output:

```text
{ "name": "John Doe", "age": 25 }
```

## Steps to reproduce

1. Install dependencies:

   ```sh
   npm install
   ```

2. Start the Expo development server:

   ```sh
   npx expo start
   ```

3. Open the project in Expo Go or an Expo development build on Android or iOS.
4. Inspect the JavaScript/Metro console output. Reload the app if necessary.
5. Compare the logged object property keys with the expected and actual output above.

## Environment

- Expo SDK: 57.0.26
- React Native: 0.86.3
- React: 19.2.3
- Node.js: see `npx expo-env-info` output below
- Platform: Android or iOS via Expo Go/development build

The Expo SDK 57 documentation maps SDK 57 to React Native 0.86 and React 19.2.3: <https://docs.expo.dev/versions/v57.0.0/>.

### `npx expo-env-info`

```text
expo-env-info 2.1.0 environment info:
  System:
    OS: Windows 11 10.0.26200
  Binaries:
    Node: 24.16.0 - C:\nvm4w\nodejs\node.EXE
    npm: 11.13.0 - C:\nvm4w\nodejs\npm.CMD
  SDKs:
    Android SDK:
      API Levels: 34
      Build Tools: 34.0.0
  npmPackages:
    expo: ~57.0.26 => 57.0.26
    react: 19.2.3 => 19.2.3
    react-native: 0.86.3 => 0.86.3
  Expo Workflow: managed
```

### `npx expo-doctor@latest`

```text
Running 21 checks on your project...
21/21 checks passed. No issues detected!
```

## Reproduction command

```sh
npx expo start
```
