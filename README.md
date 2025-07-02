### Issue

glob pattern does not work when run through scripts

#### `package.json` scripts
```json
"scripts": {
    "lint:0:ok": "oxlint",
    "lint:1:ok": "oxlint ./src/index.ts",
    "lint:2:ok": "find ./src -name '*.ts' | xargs oxlint",
    "lint:3:ok": "oxlint $(ls ./src/**/*.ts)",
    "lint:4:nok": "oxlint ./src/**/*.ts",
    "lint:5:nok": "oxlint './src/**/*.ts'",
    "lint:6:nok": "oxlint $(echo './src/**/*.ts')",
    "lint:7:nok": "oxlint \"./src/**/*.ts\"",
    "lint:8:nok": "oxlint ./src/\\*\\*.ts",
    "lint:9:nok": "oxlint ./src/\\*\\*/\\*.ts"
  }
```
