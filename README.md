# expo/expo #29038 minimal reproducible example for 

## Reanimated babel error after migrating to Expo Router

1. Initialize Expo project with `bun create expo-app expo-router-babel-reanimated-crash -e with-router`
2. Install and set up `react-native-reanimated` per its quickstart: https://docs.swmansion.com/react-native-reanimated/docs/fundamentals/getting-started/
3. Install `react-native-gesture-handler` and add `import "react-native-gesture-handler"` to `app/_layout.js`
4. Run `bun start --clear --ios`

You should be met with a bundling error like the following:

```txt
iOS Bundling failed 4638ms node_modules/expo-router/entry.js (1055 modules)
error: node_modules/react-native-gesture-handler/src/handlers/gestures/hoverGesture.ts: expo-router-babel-reanimated-crash/node_modules/react-native-gesture-handler/src/handlers/gestures/hoverGesture.ts: [Reanimated] Babel plugin exception: Error: [BABEL]: You appear to be using a native ECMAScript module plugin, which is only supported when running Babel asynchronously. (While processing: expo-router-babel-reanimated-crash/node_modules/@babel/plugin-transform-shorthand-properties/lib/index.js)
```