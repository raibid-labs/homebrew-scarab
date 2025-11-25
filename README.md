# Scarab Terminal - Homebrew Tap

Official Homebrew tap for [Scarab Terminal](https://github.com/raibid-labs/scarab), a GPU-accelerated terminal emulator with a powerful plugin system.

## Installation

```bash
brew tap raibid-labs/scarab
brew install scarab
```

Or install directly:

```bash
brew install raibid-labs/scarab/scarab
```

## What Gets Installed

- **scarab-daemon** - Background server handling PTY and plugins
- **scarab-client** → **scarab** - GPU-accelerated terminal client
- **scarab-plugin-compiler** - Compile Fusabi plugins (.fsx → .fzb)

## Quick Start

```bash
# Start the daemon
brew services start scarab

# Or start manually
scarab-daemon &

# Launch terminal
scarab
```

## Configuration

Configuration file location: `~/.config/scarab/config.toml`

Example configuration:

```toml
[terminal]
shell = "/bin/zsh"
font_size = 14.0
font_family = "SF Mono"

[theme]
name = "default"

[gpu]
backend = "metal"
vsync = true

[plugins]
enabled = true
```

## Features

- 🚀 **GPU-Accelerated** - Metal/Vulkan rendering via Bevy engine
- 🔌 **Plugin System** - Fusabi (F# dialect) scripting
- 📊 **Split Architecture** - Daemon + Client for stability
- 🎨 **Customizable** - Themes, fonts, keybindings
- ⚡ **High Performance** - Zero-copy IPC, VTE caching

## Documentation

- [Main Repository](https://github.com/raibid-labs/scarab)
- [Plugin Development](https://github.com/raibid-labs/scarab/blob/main/docs/PLUGIN_LOGGING_AND_NOTIFICATIONS.md)
- [Configuration Guide](https://github.com/raibid-labs/scarab/blob/main/docs/user/installation.md)

## Troubleshooting

### Command not found after install

Ensure Homebrew's bin directory is in your PATH:

```bash
echo 'export PATH="/usr/local/bin:$PATH"' >> ~/.zshrc
# or for Apple Silicon:
echo 'export PATH="/opt/homebrew/bin:$PATH"' >> ~/.zshrc
```

### Daemon won't start

Check logs:

```bash
tail -f $(brew --prefix)/var/log/scarab-daemon.log
```

### GPU/Graphics issues

Try software rendering:

```bash
SCARAB_RENDERER=software scarab
```

## Uninstall

```bash
brew services stop scarab
brew uninstall scarab
brew untap raibid-labs/scarab
```

## Development

This tap is automatically updated with each Scarab release. The formula is maintained at:
- [Formula Source](https://github.com/raibid-labs/scarab/blob/main/packaging/homebrew/scarab.rb)

## Support

- [GitHub Issues](https://github.com/raibid-labs/scarab/issues)
- [Discussions](https://github.com/raibid-labs/scarab/discussions)

## License

Scarab Terminal is licensed under MIT OR Apache-2.0.
