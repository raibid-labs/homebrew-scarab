# Contributing to homebrew-scarab

Thank you for your interest in contributing to the Scarab Homebrew tap!

## Reporting Issues

If you encounter issues with the Homebrew formula:

1. **Check existing issues**: [Issues](https://github.com/raibid-labs/homebrew-scarab/issues)
2. **Provide details**:
   - macOS version
   - Homebrew version (`brew --version`)
   - Installation method
   - Error messages
   - Output of `brew doctor`

## Formula Updates

The formula is automatically maintained and synced from the main Scarab repository. If you notice the formula is out of date:

1. Check the [latest Scarab release](https://github.com/raibid-labs/scarab/releases)
2. Open an issue requesting an update
3. Maintainers will run the update script

## Testing Changes

Before submitting changes:

```bash
# Audit the formula
brew audit --strict Formula/scarab.rb

# Test installation
brew install --verbose --debug Formula/scarab.rb

# Test the application
scarab --version
scarab-daemon --version

# Test uninstallation
brew uninstall scarab
```

## Pull Request Guidelines

1. **Formula changes**:
   - Update only necessary fields
   - Test thoroughly on both Intel and Apple Silicon
   - Include version bump reasoning

2. **Documentation changes**:
   - Update README.md for user-facing changes
   - Ensure markdown formatting is correct
   - Check all links work

3. **Commit messages**:
   - Use conventional commits format
   - Examples:
     - `feat: add support for feature X`
     - `fix: correct SHA256 checksum`
     - `docs: update installation instructions`

## Automated Updates

This tap is updated automatically when new Scarab versions are released. The process:

1. New tag is created in main Scarab repo
2. GitHub Actions builds release binaries
3. Update script calculates SHA256 checksums
4. Formula is updated and committed

Manual intervention is only needed for:
- Formula structure changes
- Dependency updates
- Service configuration changes

## Questions?

- [Scarab Discussions](https://github.com/raibid-labs/scarab/discussions)
- [Main Repository Issues](https://github.com/raibid-labs/scarab/issues)

## Code of Conduct

This project follows the same Code of Conduct as the main Scarab repository. Please be respectful and constructive.
