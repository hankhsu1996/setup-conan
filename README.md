# Setup Conan with Python

This action sets up Conan with Python, and optionally caches the Conan home directory and the Conan tool itself.

## Inputs

### `conan-version`

**Optional** The version of Conan to install. Default is the latest version.

### `python-version`

**Optional** The version of Python to use. Default is Python 3 latest version.

### `conan-home`

**Optional** The Conan home directory. Default is `~/.conan` for Conan 1 and `~/.conan2` for Conan 2. If custom Conan home directory is provided, the action will set the `CONAN_HOME` environment variable to the provided directory.

### `cache-dependencies`

**Optional** Whether to cache the Conan home directory in which dependencies are stored. Default is `false`.

### `cache-tool`

**Optional** Whether to cache the Conan tool itself. This means caching pip packages. Default is `false`.

## Example usage

```yaml
uses: actions/setup-conan@v1
with:
  conan-version: "2.5.0"
  python-version: "3.12"
  conan-home: "~/.conan2"
  cache-dependencies: true
  cache-tool: true
```
