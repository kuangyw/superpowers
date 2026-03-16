
# Installing Superpowers for Qoder

Enable superpowers skills in Qoder via native skill discovery. Just clone and symlink.

## Prerequisites

- Git

## Installation

1. **Clone the superpowers repository:**
   ```bash
   git clone https://github.com/obra/superpowers.git ~/.qoder/superpowers
   ```

2. **Create the skills symlink:**
   ```bash
   mkdir -p ~/.agents/skills
   ln -s ~/.qoder/superpowers/skills ~/.agents/skills/superpowers
   ```

   **Windows (PowerShell):**
   ```powershell
   New-Item -ItemType Directory -Force -Path "$env:USERPROFILE\.agents\skills"
   cmd /c mklink /J "$env:USERPROFILE\.agents\skills\superpowers" "$env:USERPROFILE\.qoder\superpowers\skills"
   ```

3. **Restart Qoder** (quit and relaunch the CLI) to discover the skills.

## Migrating from old bootstrap

If you installed superpowers before native skill discovery, you need to:

1. **Update the repo:**
   ```bash
   cd ~/.qoder/superpowers && git pull
   ```

2. **Create the skills symlink** (step 2 above) — this is the new discovery mechanism.

3. **Remove the old bootstrap block** from `~/.qoder/AGENTS.md` — any block referencing `superpowers-qoder bootstrap` is no longer needed.

4. **Restart Qodex.**

## Verify

```bash
ls -la ~/.agents/skills/superpowers
```

You should see a symlink (or junction on Windows) pointing to your superpowers skills directory.

## Updating

```bash
cd ~/.qoder/superpowers && git pull
```

Skills update instantly through the symlink.

## Uninstalling

```bash
rm ~/.agents/skills/superpowers
```

Optionally delete the clone: `rm -rf ~/.qoder/superpowers`.
