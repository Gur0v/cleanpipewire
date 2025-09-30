# cleanpipewire

A shell script that attempts to minimize the "cracking" and "crackling", get better performance and lower latency in PipeWire.

## What does it do?

This script automatically configures PipeWire with optimized settings by:

- Increasing audio buffer sizes to reduce crackling and stuttering
- Adjusting quantum values for smoother audio playback
- Setting up proper PulseAudio compatibility layer settings

Perfect for users experiencing audio issues or wanting better audio performance on Linux.

## Quick Install

**One-line install (automatic):**

```bash
wget -qO- https://raw.githubusercontent.com/Gur0v/cleanpipewire/main/cleanpipewire | sh -s -- -f
```

*The `-f` flag will automatically overwrite existing configuration. Intended mostly for use in the automatic install.*

**Interactive install:**

```bash
git clone https://github.com/Gur0v/cleanpipewire.git
cd cleanpipewire
chmod +x cleanpipewire
./cleanpipewire
```

The script will:
1. Check for required dependencies
2. Download fresh PipeWire configuration files
3. Apply optimized settings
4. Optionally restart PipeWire services for you

## Requirements

- PipeWire (already installed if you're using it)
- wget
- rtkit (recommended)

## What gets changed?

The script modifies your `~/.config/pipewire/` configuration files with these optimizations:

**Audio buffer settings:**
- Quantum: 1024 → 2048
- Min quantum: 32 → 64
- Max quantum: 2048 → 4096

**PulseAudio compatibility:**
- Minimum request/fragment: 128 → 1024
- Minimum quantum: 128 → 1024

## Reverting changes

Simply delete the `~/.config/pipewire/` folder and restart PipeWire to use default settings again.
