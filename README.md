# Santral-C Desktop Releases

Official Windows desktop releases and installation packages for Santral-C.

English | [Türkçe](README.tr.md)

## Downloads

| Package | Type | Description |
| :--- | :--- | :--- |
| [Santral-C Mini Widget Setup 1.0.0.exe](https://github.com/toprakgureli/santral-desktop-releases/releases/download/v1.0.0/Santral-C-Mini-Widget-Setup-1.0.0.exe) | NSIS Installer | Windows installer with background auto-update support. |
| [Santral-C-Widget-Portable.exe](https://github.com/toprakgureli/santral-desktop-releases/releases/download/v1.0.0/Santral-C-Widget-Portable.exe) | Portable Binary | Standalone executable. Runs directly without installation. |

Update metadata: [`latest.yml`](https://github.com/toprakgureli/santral-desktop-releases/releases/download/v1.0.0/latest.yml)

## Technical Summary

Santral-C Desktop bundles the full management panel and a lightweight floating softphone widget into an Electron runtime for Windows.

- **Direct WebRTC Integration:** SIP signaling, registration, and RTP media are managed inside the desktop runtime. External browser extensions are not required.
- **Window Management:** The softphone widget stays on top of other applications and does not create a secondary taskbar entry. Window close and minimize behaviors are handled through the notification area.
- **Update Delivery:** Builds packaged with the installer check this repository for newer releases and prompt for background download and replacement.
- **Theme Synchronization:** Detects the active Windows theme (dark/light) to eliminate frame flash on launch, and updates window chrome when the application palette changes (`dark`, `midnight`, `forest`, `matte`, `sand`, `crimson`, `light`).

## System Requirements

- Operating System: Windows 10 (version 1809 or higher), Windows 11
- Architecture: x64
- Hardware: Working audio input (microphone) and output devices
- Connectivity: Outbound HTTPS and WebSocket access to the panel and SIP endpoints

## Configuration

Default panel endpoints are built into the binary. To direct the client to an alternative host, modify `%AppData%\santralc-desktop-widget\widget-config.json`:

```json
{
  "panelUrl": "https://cm.toprakgureli.com"
}
```

The endpoint can also be specified via the `SANTRAL_PANEL_URL` environment variable.
