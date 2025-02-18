# rnfe

react native snippet download

# prettier 설정

[참조](https://www.jetbrains.com/help/webstorm/prettier.html#ws_prettier_configuration_automatic)

# nativewind css 설정

[참조](https://www.nativewind.dev/getting-started/installation)

# metro.config.js | tailwind.config.js 경로 설정

```javascript
// metro.config.js
const {getDefaultConfig} = require("expo/metro-config");
const {withNativeWind} = require('nativewind/metro');

const config = getDefaultConfig(__dirname)

module.exports = withNativeWind(config, {input: './app/global.css'}) //이 부분 설정 해주기
```

```javascript
// tailwind.config.js
/** @type {import('tailwindcss').Config} */
module.exports = {
    // NOTE: Update this to include the paths to all of your component files.
    content: ["./app/**/*.{js,jsx,ts,tsx}", "./components/**/*.{js,jsx,ts,tsx}"], // 이 부분 설정
    presets: [require("nativewind/preset")],
    theme: {
        extend: {},
    },
    plugins: [],
}
```

# font, splash 설정

```json
{
  "expo": {
    "icon": "./assets/images/icon.png",
    "scheme": "restate",
    "userInterfaceStyle": "automatic",
    "newArchEnabled": true,
    "plugins": [
      "expo-router",
      [
        "expo-splash-screen",
        {
          "image": "./assets/images/splash-icon.png",
          "imageWidth": 200,
          "resizeMode": "cover",
          "backgroundColor": "#ffffff",
          "enableFullScreenImage_legacy": true
        }
      ],
      [
        "expo-font",
        {
          "fonts": [
            "./assets/fonts/Rubik-Bold.ttf",
            "./assets/fonts/Rubik-ExtraBold.ttf",
            "./assets/fonts/Rubik-Medium.ttf",
            "./assets/fonts/Rubik-Light.ttf",
            "./assets/fonts/Rubik-Regular.ttf",
            "./assets/fonts/Rubik-SemiBold.ttf"
          ]
        }
      ]
    ],
    "experiments": {
      "typedRoutes": true
    }
  }
}
```

# type 정의 파일

[참조](https://www.codeit.kr/tutorials/90/%ED%83%80%EC%9E%85%20%EC%A0%95%EC%9D%98(d.ts)%20%ED%8C%8C%EC%9D%BC%EC%9D%B4%20%EB%AD%94%EA%B0%80%EC%9A%94%3F)
