# asdf-java-debug

[Microsoft Java Debug Server](https://github.com/microsoft/java-debug) plugin for asdf version manager (and mise)


## README.md

```markdown
# asdf-java-debug

[![Build](https://github.com/yourusername/asdf-java-debug/actions/workflows/build.yml/badge.svg)](https://github.com/yourusername/asdf-java-debug/actions/workflows/build.yml)

[Microsoft Java Debug Server](https://github.com/microsoft/java-debug) plugin for the [asdf version manager](https://asdf-vm.com) and [mise](https://github.com/jdx/mise).

## Dependencies

- Java JDK (8 or newer)
- Maven (if Maven wrapper is not available in the source)
- `bash`, `curl`, `git`, `tar`

## Install

### asdf

```bash
asdf plugin add java-debug https://github.com/yourusername/asdf-java-debug.git
```

### mise

```bash
mise plugin install java-debug https://github.com/yourusername/asdf-java-debug.git
# Or in .mise.toml
# [plugins.java-debug]
# plugin_url = "https://github.com/yourusername/asdf-java-debug.git"
```

### Install using an old JDTLS version

If you need to use an older JDTLS version, add the following env var:
```
export JDTLS_VERSION=1.43.0 
```

## Usage

### asdf

```bash
# Install latest version
asdf install java-debug latest

# Set global version
asdf global java-debug latest

# Get the path to the plugin JAR
java-debug --path
```

### mise

```bash
# Install latest version 
mise install java-debug@latest

# Set global version
mise global java-debug@latest

# Get the path to the plugin JAR
java-debug --path
```

## Integration with JDT.LS

To use with [Eclipse JDT.LS](https://github.com/eclipse/eclipse.jdt.ls), add the plugin JAR to the initialization options:

```json
{
  "initializationOptions": {
    "bundles": [
      "/path/to/com.microsoft.java.debug.plugin-x.y.z.jar"
    ]
  }
}
```

You can get the path to the JAR with:

```bash
java-debug --path
```

## Structure

```
.
├── bin
│   ├── download
│   ├── install
│   ├── list-all
│   └── java-debug (wrapper script)
└── lib
    └── utils.bash
```

## License

See [LICENSE](LICENSE) © [Your Name](https://github.com/yourusername/)
```
