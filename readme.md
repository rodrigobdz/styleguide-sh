# [rodrigobdz](https://github.com/rodrigobdz)'s Shell Style Guide

Opinionated guide on how to organize scripts and which rules to follow while writing them.

[Motivation](https://github.com/github/scripts-to-rule-them-all#the-idea)

## Usage

### File Naming Convention

We follow a modified version of [github/scripts-to-rule-them-all](https://github.com/github/scripts-to-rule-them-all):

- [`utils.sh`](./utils.sh) - shared functions and variables
- [`script/bootstrap`](./script/bootstrap) - installs all dependencies
- `script/setup` - sets up a project to be used for the first time
- `script/update` - updates a project to run at its current version
- `script/build` - builds package
- `script/up` - starts app
- `script/test` - runs tests
- `script/console` - opens a console for your application.
- `script/cibuild` - invoked by continuous integration servers to run tests

If script targets a specific OS version, add it to the filename after a hyphen. We like hyphens.

Example: `script/bootstrap-mac` or `script/bootstrap-centos`

#### File Extensions

> Executables should have **no extension**.
>
> Libraries **must have** a .sh **extension** and should not be executable.

Source: [Google's Shell Style Guide](https://google.github.io/styleguide/shell.xml#File_Extensions)

### Code Style

- [Google Shell Style Guide](https://google.github.io/styleguide/shell.xml) - Set of best practices, additional to linter use.

  Only modifications are:

  - [Shebang](https://google.github.io/styleguide/shell.xml?showone=Which_Shell_to_Use#Which_Shell_to_Use): `#!/usr/bin/env bash`
  - Shell Options:

    ```sh
    set -o errexit # Abort script at first error
    set -o pipefail # Return last non-zero status in pipeline
    set -o nounset # Exit if any variable is undefined
    # Optional
    set -o verbose # Print commands before executing them
    ```

  - Source Filenames: We prefer **hyphens** instead of underscores.

- [ShellCheck](https://github.com/koalaman/shellcheck) - Linter

#### Example

```sh
#!/usr/bin/env bash
#
# Install all project dependencies.

set -o errexit
set -o pipefail
set -o nounset
```

## License

[MIT](license) © [rodrigobdz](https://github.com/rodrigobdz)
