# Use an iPhone as a second Mac display

Two Xcode apps. MacScreenExtender captures a display with ScreenCaptureKit, encodes H.264 at 1920x1080, 60 fps, 5 Mbps, and serves it on WebSocket port 8080. iPhoneScreenExtender connects to `ws://<mac-ip>:8080` and draws the frames with Metal.

The repo name says monitor. The code extends the Mac screen onto the phone.

## Run both apps

1. Open `MacScreenExtender/MacScreenExtender.xcodeproj` and run it on the Mac. Allow screen recording when macOS asks. The process logs `WebSocket server on port 8080`.
2. Open `iPhoneScreenExtender/iPhoneScreenExtender.xcodeproj` and run it on the phone.
3. Type the Mac's LAN IP into "Enter Mac's IP address" and connect. Streaming starts when the phone connects, and stops when it disconnects.

Both devices have to be on a network that can reach port 8080.

## License

[MIT](LICENSE)
