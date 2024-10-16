# VanillaJS-Vite-LibraryMode

Viteを利用してVanilla JSでライブラリをバンドル

---

# 手順

```powershell
volta install node@latest
volta install npm@latest
```

```powershell
npm create vite@latest my_app -- --template vanilla
```

```
Need to install the following packages:
create-vite@5.5.3
Ok to proceed? (y)


> npx
> create-vite my_app --template vanilla


Scaffolding project in path\to\my_app...

Done. Now run:

  cd my_app
  npm install
  npm run dev

```

```powershell
cd my_app
# rm counter.js javascript.svg public\vite.svg style.css
nano main.js
nano app.css
nano index.html
npm install
npm i maplibre-gl # https://maplibre.org/maplibre-gl-js/docs/
```

```powershell
# Viteのライブラリモードを利用するための設定ファイルを作成
touch vite.config.js
nano vite.config.js
```

```js
import { resolve } from 'path';
import { defineConfig } from 'vite';

export default defineConfig({
  build: {
    lib: {
      entry: resolve(__dirname, 'main.js'), // エントリポイント
      fileName: 'bundle',
      formats: ['es']
    }
  },
});

```

```powershell
npm run dev
```

```
  VITE v5.4.8  ready in 213 ms

  ➜  Local:   http://localhost:5173/
  ➜  Network: use --host to expose
  ➜  press h + enter to show help

```

```powershell
npm run build
npm run preview
```

---

Copyright (c) 2024 YA-androidapp(https://github.com/yzkn) All rights reserved.
