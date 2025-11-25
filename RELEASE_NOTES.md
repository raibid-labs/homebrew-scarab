# Release Notes

## Homebrew Tap Setup - Not Yet Published

This Homebrew tap has been configured but is **NOT YET PUBLISHED**.

### Current Status

- ✅ Repository structure created
- ✅ Formula added (v0.1.0-alpha.7)
- ✅ Documentation complete
- ⏸️ **SHA256 checksums need to be added** (PLACEHOLDER values currently)
- ⏸️ **Not pushed to GitHub yet**

### Before Publishing

1. **Update checksums** after v0.1.0-alpha.7 release:
   ```bash
   cd ~/raibid-labs/scarab
   ./scripts/update-homebrew-formula.sh v0.1.0-alpha.7
   cp packaging/homebrew/scarab.rb ~/raibid-labs/homebrew-scarab/Formula/scarab.rb
   ```

2. **Test formula locally**:
   ```bash
   brew audit --strict Formula/scarab.rb
   brew install --build-from-source ./Formula/scarab.rb
   scarab --version
   brew uninstall scarab
   ```

3. **Commit and push**:
   ```bash
   cd ~/raibid-labs/homebrew-scarab
   git add -A
   git commit -m "feat: Add Scarab Terminal formula v0.1.0-alpha.7"
   git push origin main
   ```

4. **Test installation from tap**:
   ```bash
   brew tap raibid-labs/scarab
   brew install scarab
   ```

### For Each New Release

1. Create release tag in main repo
2. Wait for GitHub Actions to build binaries
3. Run update script:
   ```bash
   ./scripts/update-homebrew-formula.sh vX.Y.Z
   ```
4. Copy updated formula to tap
5. Commit and push tap repository

### Notes

- Formula expects pre-built binaries in GitHub releases
- Archive names must match: `scarab-vX.Y.Z-{arch}-apple-darwin.tar.gz`
- Archives must contain: `scarab-daemon`, `scarab-client`, `scarab-plugin-compiler`

---

**Last Updated**: 2025-11-24
**Formula Version**: v0.1.0-alpha.7
**Status**: Configured, awaiting SHA256 checksums and publication
