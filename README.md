# Create and Publish NPM Module

## What we're usuing
- [tsup](https://tsup.egoist.dev/)
- [TypeScrip](https://www.typescriptlang.org)
- [Vitest](https://vitest.dev/)

### Step 1: Create a new project

pnpm init

pnpm add -D typescript tsup vitest

npx tsc --init

### Step 2: Setup tsup
tsup.config.ts
```
import { defineConfig } from "tsup";

export default defineConfig({
  entry: ["src/index.ts"],
  format: ["cjs", "esm"], // Build for commonJS and ESmodules
  dts: true, // Generate declaration file (.d.ts)
  splitting: false,
  sourcemap: true,
  clean: true,
});
```

### Step 3: Update package.json
```
{
  "scripts": {
    "build": "tsup",
    "test": "vitest"
  }
}
```

### Step 3: Create some code

### Step 4: Automate updates with github actions