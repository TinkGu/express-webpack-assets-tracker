# express-webpack-assets-tracker

please pre-install `assets-webpack-plugin`.

## Usage

webpack-assets.json
```
{"dashboard":{"js":"/public/scripts/dashboard-6dce253bc98e98a0d87c.js","css":"/public/styles/dashboard-6dde253bc98e98a0d87c.css"}}
```

express, app.js

```
var path = require('path');
var assets = require('express-webpack-assets-tracker');

app.use(assets(path.resolve('./webpack-assets.json')))
```

ejs, index.html
```
<link rel="stylesheet" href="<%- webpack_asset.webpack_entry_name.css %>">
<script src="<%- webpack_assets.webpack_entry_name.js %>"></script>
```

output
```
<link rel="stylesheet" href="/public/styles/dashboard-6dde253bc98e98a0d87c.css">
<script src="/public/scripts/dashboard-6dce253bc98e98a0d87c.js"></script>
```

## Note
- readFileSync
- NO TEST!
