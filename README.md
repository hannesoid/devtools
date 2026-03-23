# devtools

A collection of developer tools for macOS.

## prune-derived-data

Lists and prunes stale Xcode DerivedData directories — those whose workspace or project no longer exists on disk, or that haven't been built recently.

### Usage

```bash
# Show status of all DerivedData directories
prune-derived-data

# Include sizes (slower — runs du)
prune-derived-data --sizes

# Preview what would be deleted
prune-derived-data prune --dry

# Delete stale entries
prune-derived-data prune

# Also prune entries not built in the last 30 days
prune-derived-data prune --days 30 --dry
```

### Example output

```
Project                                                 Size     Last Build   Status
─────────────────────────────────────────────────────── ──────── ──────────── ────────────────────
MyApp                                                            2025-03-23   Active
MyApp-feature-auth/MyApp                                         2025-03-10   Stale
MyApp-old-refactor/MyApp                                         2025-02-14   Stale
Toolkit                                                          2025-03-22   Active
Toolkit/ToolkitWithDependencies                                  2025-03-22   Active
Experiments                                                      2025-01-05   Active

4 active, 2 prunable
```

## Install

```bash
brew tap hannesoid/tools
brew install prune-derived-data
```

Or run directly:

```bash
curl -sL https://raw.githubusercontent.com/hannesoid/devtools/main/prune-derived-data | bash
```
