# eslint-config-empoleon

## Install

```sh
yarn add --dev @eslint/js eslint eslint-plugin-jsx-a11y eslint-plugin-solid typescript-eslint eslint-config-empoleon
```

## Usage

In your `eslint.config.js`:

```tsx
import empoleon from "eslint-config-empoleon";
import { defineConfig } from "eslint/config";
import tseslint from "typescript-eslint";

// @ts-check
export default defineConfig(
  tseslint.configs.recommended,
  ...empoleon,
  { ignores: ["**/*.{mjs,cjs,js,d.ts,d.mts}"] },
  {
    files: ["**/*.story.tsx"],
    rules: { "no-console": "off" },
  },
  {
    languageOptions: {
      parserOptions: {
        tsconfigRootDir: process.cwd(),
        project: ["./tsconfig.json"],
      },
    },
  }
);
```

## License

MIT
