# Capacitor Firebase Remote Config Plugin

Capacitory community plugin for firebase remote config.

## Maintainers

| Maintainer | GitHub | Social | Sponsoring Company |
| -----------| -------| -------| -------------------|
| Priyank Patel | [priyankpat](https://github.com/priyankpat) | [@priyankpat_](https://twitter.com/priyankpat_) | Ionic |

Mainteinance Status: Actively Maintained

## Installation

To use npm

```bash
npm install @capacitor/firebase-remote-config
```

To use yarn

```bash
yarn add @capacitor/firebase-remote-config
```

Sync native files

```bash
npx cap sync
```

On iOS, no further steps are needed.

On Android, register the plugin in your main activity:

```java
import com.getcapacitor.community.firebaserc.FirebaseRemoteConfig;

public class MainActivity extends BridgeActivity {
  @Override
  public void onCreate(Bundle savedInstanceState) {
    super.onCreate(savedInstanceState);

    // Initializes the Bridge
    this.init(savedInstanceState, new ArrayList<Class<? extends Plugin>>() {{
      // Additional plugins you've installed go here
      // Ex: add(TotallyAwesomePlugin.class);
      add(FirebaseRemoteConfig.class);
    }});
  }
}
```

## Configuration

No configuration required for this plugin.

## Supported methods

| Name  | Android | iOS | Web
| :---- | :--- | :--- | :--- |
| initialize | ✅ | ✅ | ❌ 
| fetch | ✅ | ✅ | ❌ 
| activate | ✅ | ✅ | ❌ 
| fetchAndActivate | ✅ | ✅ | ❌ 
| getBoolean | ✅ | ✅ | ❌ 
| getByteArray | ✅ | ✅ | ❌ 
| getNumber | ✅ | ✅ | ❌ 
| getString | ✅ | ✅ | ❌ 

## Usage

```typescript
// Must import the package once to make sure the web support initializes
import '@capacitor-community/http';

import { Plugins } from '@capacitor/core';

const { FirebaseRemoteConfig } = Plugins;

/**
 * This method will configure remote config object instance and set the minimum fetch interval to allow for frequest refreshes.
 * @param minimumFetchIntervalInSeconds - interval in seconds (default: 3600)
 * @returns void
 */
FirebaseRemoteConfig.initialize();

/**
 * This method will execute fetch task to retrieve config
 * @param none
 * @returns void
 */
FirebaseRemoteConfig.fetch();

/**
 * This method will activate the fetched values making it available for your app
 * @param none
 * @returns void
 */
FirebaseRemoteConfig.activate();

/**
 * This method will fetch and activate the values making it available for your app
 * @param none
 * @returns void
 */
FirebaseRemoteConfig.fetchAndActivate();

/**
 * This method will return the parameter value for a given key in boolean
 * @param key - key to obtain boolean value
 * @returns key - key used to obtain value
 *          value - boolean value for a given key
 *          source - Indicates that the source of value retrieved (default, remote, static)
 */
FirebaseRemoteConfig.getBoolean({
  key: 'bool key',
});

/**
 * This method will return the parameter value for a given key in byte array
 * @param key - key to obtain byte array value
 * @returns key - key used to obtain value
 *          value - byte array value for a given key
 *          source - Indicates that the source of value retrieved (default, remote, static)
 */
FirebaseRemoteConfig.getByteArray({
  key: 'array key',
});

/**
 * This method will return the parameter value for a given key in double
 * @param key - key to obtain double value
 * @returns key - key used to obtain value
 *          value - double value for a given key
 *          source - Indicates that the source of value retrieved (default, remote, static)
 */
FirebaseRemoteConfig.getNumber({
  key: 'number key',
});

/**
 * This method will return the parameter value for a given key in string
 * @param key - key to obtain string value
 * @returns key - key used to obtain value
 *          value - string value for a given key
 *          source - Indicates that the source of value retrieved (default, remote, static)
 */
FirebaseRemoteConfig.getString({
  key: 'string key',
});
```