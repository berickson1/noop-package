# noop-package
Noop NPM Package

## Description
This package is useful when you want to remove a transitive dependency from npm/yarn.

For example. Module A depends sets Module B as a dependency but doens't use it and you want to remove it from your node_modules. You can use [selective dependency resolution](https://yarnpkg.com/en/docs/selective-version-resolutions/) to override a module in `package.json`

```json
{
  "dependencies": {
    "moduleA": "1.0.0",
    "moduleB": "npm:noop-package@1.0.0"
  },
  "resolution": {
    "moduleB": "npm:noop-package@1.0.0"
  }
}
```

## Warnings
If you override a package using selective dependency resolution, the original package *will be replaced* in node_modules and may cause undefined behaviour. 

## License
This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details
