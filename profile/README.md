# MPClipboard

1. **M**ulti
2. **P**latform
3. **Clipboard**

This project implements a set of libraries and self-hosted apps (both desktop and mobile) to implement a shared clipboard buffer across multiple devices running on multiple platforms.

It requires a WebSocket server for communication (can be local if you only need it for devices that run in the same local network).

Key components:

1. [Server](https://github.com/mpclipboard/server) - self-hosted WebSocket server (a single binary, 2.3MB of RAM).
2. [Generic client](https://github.com/mpclipboard/generic-client) - a library that is the heart of all desktop/mobile apps, handles talking over WebSocket and implements a dead simple communication protocol.
    1. [Linux client](https://github.com/mpclipboard/linux) - integrates with Wayland clipboard, shows history in tray menu.
    2. [macOS client](https://github.com/mpclipboard/macos) - integrates with macOS clipboard, shows history in tray menu, displays system notification when there's a new text received from the server.
3. [Android library](https://github.com/mpclipboard/mpclipboard-android) - a generic library for Android
    1. [Patched FlorisBoard app](https://github.com/mpclipboard/android-florisboard) - a patched version of a popular open-source custom IME app for Android.

And potentially any other client can be implemented as well (iOS, Windows, etc).

![diagram.png](/assets/diagram.png)
