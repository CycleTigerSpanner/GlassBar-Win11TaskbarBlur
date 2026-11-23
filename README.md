<p align="center">
  <img src="https://i.postimg.cc/76n7vWvV/banner.png" alt="GlassBar Taskbar Customizer — Transparent & Acrylic Blur Taskbar for Windows 11" width="100%">
</p>

<p align="center">
  <img src="https://img.shields.io/badge/Platform-Windows%2010%2F11%20x64-0078D6?style=flat-square&logo=windows" alt="Platform: Windows 10/11 x64">
  <img src="https://img.shields.io/badge/Mode-Win11%20Taskbar%20Blur-2EA44F?style=flat-square" alt="Mode">
  <img src="https://img.shields.io/badge/Release-glassbar--v1.3-5391FE?style=flat-square" alt="Release Tag">
  <img src="https://img.shields.io/badge/License-MIT-8B5CF6?style=flat-square" alt="License: MIT">
</p>

# GlassBar Taskbar Customizer — Transparent & Acrylic Blur Taskbar for Windows 11

**Tired of the thick opaque bar cutting across your clean Windows 11 wallpaper? Transform your taskbar into a fully transparent, Acrylic-blurred, or Mica glass bar that adapts dynamically when you maximize windows.**

GlassBar Taskbar Customizer applies native Windows DWM (`SetWindowCompositionAttribute`) visual states in a tiny tray utility: **supporting Clear Transparent mode on the desktop, automatic Acrylic/Opaque switching when a window is maximized, and custom tint colors without patching system DLLs**.

This project is aimed at **Windows 10 and Windows 11 (22H2 / 23H2 / 24H2 / 25H2+) users** who want a clean, aesthetic desktop without installing heavy shell-replacement suites.

## Quick Use-Case & Troubleshooting Reference

| Scenario / Issue | Cause | Solution |
| --- | --- | --- |
| Windows 11 taskbar blocks the bottom of full-screen wallpapers | Default Windows 11 theme enforces an opaque or semi-opaque shelf | Enable **Clear Transparent** mode on Desktop so your wallpaper extends edge-to-edge |
| Taskbar icons become hard to read over white browser windows | Static transparency stays clear even when an app is maximized | Set **Maximized Window State** to `Acrylic Blur` or `Solid Tint` automatically |
| Thin grey 1px top border line remains visible above the taskbar | Windows DWM draws a default separator line on desktop toolbars | Toggle **Hide Top Separator Line** for a seamless floating dock look |
| Heavy customization suites consume 300+ MB RAM in background | All-in-one theme engines load bloated web views | Run a native Win32 tray binary using under `8 MB` RAM and `0%` idle CPU |

## Download for Windows

[**Download GlassBar.zip — Latest GitHub Release (Windows x64)**](../../releases/latest/download/GlassBar.zip)  
[View All Releases & Changelog](../../releases) · [Report an Issue](../../issues)

### Why use `GlassBar.exe`? (Key features)

- Supports **Clear Transparent**, **Acrylic Blur**, **Mica**, and **Custom Color Tint** taskbar styles.
- Dynamic state rules: switch automatically between **Desktop Idle**, **Window Maximized**, and **Start Menu Open**.
- Removes the thin 1px top taskbar border line on Windows 11 for a clean edge-to-edge look.
- 100% reversible—closing GlassBar immediately restores your stock Windows taskbar.

### Sample Output

```text
[GlassBar] Windows 11 DWM Taskbar Hook Active (Memory: 6.4 MB RAM)
[OK]   Desktop State    : Clear Transparent (Border Line: Hidden)
[OK]   Maximized State  : Acrylic Blur (Tint: #101622 | Alpha: 75%)
[OK]   Multi-Monitor    : Applied across 2 connected taskbars
```

The release ZIP is named `GlassBar.zip`; the Windows executable inside is named `GlassBar.exe`.

1. Close GlassBar before updating or replacing executable files.
2. Click **Download GlassBar.zip** above.
3. Right-click the downloaded archive and choose **Extract All**.
4. Open the extracted folder and run `GlassBar.exe`.
5. Review the options and output paths before processing files.

**Requirements:** Windows 10 (1903+) or Windows 11 (64-bit).

### Verification & Windows SmartScreen Note

- **Offline & standard user permissions:** `GlassBar.exe` runs locally without uploading your personal files and does not require disabling Windows Defender.
- **Windows SmartScreen:** Because this is an independent open-source utility without a commercial EV code-signing certificate, Windows SmartScreen may show *"Windows protected your PC"* on first launch. Click **More info → Run anyway** after verifying the release checksum on the [Releases](../../releases) page.

## Problems this project solves

### Clean edge-to-edge desktop aesthetics without DLL patching

Uses official Windows DWM composition attributes rather than risky `explorer.exe` binary patches that break after Windows Updates.

### Dynamic readability when maximizing apps

Automatically adds subtle Acrylic blur behind taskbar icons whenever Chrome, VS Code, or Explorer is maximized.

### Multi-monitor taskbar synchronization

Applies consistent transparency rules across primary and secondary monitor taskbars.

### Instant restore on exit

Exiting GlassBar restores default Windows appearance with zero leftover registry changes.

## Default folders and configuration paths

GlassBar runs from any folder and stores visual presets in `%APPDATA%\GlassBar`:

```text
%APPDATA%\GlassBar\theme.json
```

Typical directory layout:

```text
System Tray -> GlassBar
├── Desktop Idle     : Clear / Blur / Acrylic / Tint
├── Window Maximized : Acrylic / Opaque / Accent Color
├── Start Menu Open  : Match System Theme
└── Autostart        : Optional Windows Login Startup
```

If you use third-party taskbar replacements (StartAllBack / ExplorerPatcher), disable conflicting transparency toggles in those tools first.

## Quick start guide

Follow these steps to get started:

1. **Extract `GlassBar.zip` to a permanent folder (e.g., `C:\Tools\GlassBar`).** Avoid running from temporary ZIP preview folders if enabling autostart.
2. **Launch `GlassBar.exe` and click its icon in the Windows system tray.** Choose **Clear Transparent** for Desktop and **Acrylic Blur** for Maximized Windows.
3. **Adjust tint opacity and toggle **Hide Taskbar Border Line** if desired.** Preview changes live across all monitors.
4. **Enable **Start with Windows** from the tray menu.** Enjoy a clean Windows 11 desktop on every boot.

### Data safety note

GlassBar never modifies `explorer.exe` or Windows system files.

## What the status summary shows

GlassBar displays **active Windows build, DWM composition mode, per-state taskbar styles, and memory usage**.

## FAQ

**Will GlassBar break after a Windows 11 cumulative update?**

No—because it uses standard Windows DWM composition calls instead of modifying `explorer.exe` system binaries.

**Does it work on dual-monitor setups?**

Yes—it styles taskbars across all connected monitors automatically.

**How do I go back to the normal Windows 11 taskbar?**

Right-click the GlassBar tray icon and click Exit.

## Useful reading

- [Microsoft Docs — Desktop Window Manager (DWM) Overview](https://learn.microsoft.com/en-us/windows/win32/dwm/dwm-overview)

## More Windows Desktop Utilities

- [LoopDesk-LiveVideoWallpaper](../LoopDesk-LiveVideoWallpaper) — Lightweight 4K MP4/WebM live desktop wallpaper engine
- [CursorPack-Win11ThemeSwitcher](../CursorPack-Win11ThemeSwitcher) — One-click Windows 11 custom cursor & folder icon switcher
- [MonitorDim-DDCBrightnessControl](../MonitorDim-DDCBrightnessControl) — Hardware DDC/CI external monitor brightness & contrast slider
- [PinTop-WindowAlwaysOnTop](../PinTop-WindowAlwaysOnTop) — Pin any window Always-on-Top & adjust transparency on Windows

*Independent open-source desktop utility for Windows. Not affiliated with Microsoft Corporation.*
