# Translation Cleaner

`translation-cleaner` is a tool designed to help developers manage and clean up unused translation keys in their localization files. This utility ensures that your translation files remain clean and free from unused keys, making your localization process more efficient.

## Features

- Analyzes source files to identify used and unused translation keys.
- Supports multiple scoped translation functions.
- Can display or remove unused translation keys.
- Configurable through a JSON, JS, or TS config file.

## Installation

You can install `translation-cleaner` via npm:

```sh
npm install -g translation-cleaner
```

Or pnpm

```sh
pnpm install -g translation-cleaner
```

## Configuration

Create a translation-cleaner.config.json, translation-cleaner.config.js, or translation-cleaner.config.ts file in the root of your project. Here's an example configuration:

```json
{
  "paths": [
    {
      "srcPath": ["src/pages/products"],
      "localPath": "src/pages/products/locales"
    }
  ],
  "localesExtensions": "js",
  "localesNames": "en",
  "scopedNames": ["scopedT", "scopedTOne"],
  "ignorePaths": ["src/pages/products/ignoreThisFolder"],
  "excludeKey": ["someKey"]
}
```

## Usage

### Using with Config File

To use translation-cleaner with your config file, simply run:

```sh
npx translation-cleaner
```

### Using with Command Line Options

You can also specify the source and local paths directly in the command line:

##### Display Unused Translations

```sh
npx translation-cleaner display --srcPath="src/folders/bla" --localPath="src/folders/bla/locales"
```

##### Remove Unused Translations

```sh
npx translation-cleaner remove --srcPath="src/folders/bla" --localPath="src/folders/bla/locales"
```

## API

`processTranslations(paths, action)`
Processes translations based on the specified paths and action.

- paths: Array of objects containing srcPath and localPath.
- action: Action to perform, either 'display' or 'remove'.

## Development

### Building the Project

To build the project, run:

```sh
npm run build
```

#### Running Tests

To run the tests, use:

```sh
npm run test
```

## License

This project is licensed under the MIT License - see the LICENSE file for details.

## Contributing

Contributions are welcome! Please open an issue or submit a pull request if you have any improvements or suggestions.

Acknowledgements

- [Rollup](https://rollupjs.org/) - Module bundler used in this project.
- [TypeScript](https://www.typescriptlang.org/) - Typed JavaScript used in this project.
- [Vitest](https://vitest.dev/guide/cli) - Testing framework used in this project.
