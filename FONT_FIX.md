# Selectric Font Fix - macOS Big Sur Compatibility

## Issue
When installing the original `SelectricRoman.otf` on macOS Big Sur (11+), users got an error because the font contained deprecated FontForge-specific tables.

## Solution
Regenerated OTF fonts using `fontTools` to remove problematic tables.

### Changes Made
- Removed FontForge-specific tables: `FFTM`, `feat`, `morx`
- Cleaned font tables for better macOS compatibility

## Test Results

### System
- macOS: 26.3 (Sequoia 26 Developer Beta)
- FontForge: 20251009

### Fonts Installed
| Font | Glyphs | Status |
|------|--------|--------|
| SelectricRoman.otf | 194 | ✅ OK |
| SelectricMono.otf | 186 | ✅ OK |

### Font Tables
- `head`, `hhea`, `maxp`, `OS/2`, `name`, `cmap`, `post`, `CFF`, `hmtx`, `kern`

## Installation
```bash
# Clone the fixed version
git clone https://github.com/cluster2600/selectric.git
cd selectric/OTF

# Install on macOS
cp *.otf ~/Library/Fonts/
```

## References
- Original issue: https://github.com/atelierBek/selectric/issues/2
- PR: https://github.com/atelierBek/selectric/pull/3
