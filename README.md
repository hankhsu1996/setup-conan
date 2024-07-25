# Setup Conan Environment

[![CI](https://github.com/hankhsu1996/setup-conan/actions/workflows/ci.yml/badge.svg?event=schedule)](https://github.com/hankhsu1996/setup-conan/actions/workflows/ci.yml)

This GitHub Action sets up a Python environment, installs Conan, and optionally caches the Conan home directory and pip packages for Conan.

## Inputs

- **`conan-version`**

  - _Optional_: The version of Conan to install. Default: `2.*`
  - Uses pip versioning.

- **`python-version`**

  - _Optional_: The version of Python to use. Default: `3.x`
  - Uses semantic versioning for the [setup-python](https://github.com/actions/setup-python) action.

- **`conan-home`**

  - _Optional_: The Conan home directory. Default: `~/.conan` for Conan 1 and `~/.conan2` for Conan 2. If a custom Conan home directory is provided, the action sets the `CONAN_HOME` environment variable to the specified directory.

- **`cache-dependencies`**

  - _Optional_: Whether to cache the Conan home directory. Default: `false`

- **`cache-tool`**
  - _Optional_: Whether to cache the Conan tool (pip packages). Default: `false`

## Example Usage

```yaml
uses: actions/setup-conan@v1
with:
  conan-version: "2.5.0"
  python-version: "3.12"
  conan-home: "~/.conan2"
  cache-dependencies: true
  cache-tool: true
```

## Summary of Key Steps

- **Python Environment Setup**: Automatically configures the specified Python version.
- **Conan Installation**: Installs the specified version of Conan via pip.
- **Caching Options**: Optional caching of the Conan home directory and pip packages to enhance performance.

### Notes

- Ensure that the specified `conan-home` directory aligns with your Conan version to avoid conflicts.
- Utilize caching to speed up subsequent runs by preserving the Conan environment between builds.
