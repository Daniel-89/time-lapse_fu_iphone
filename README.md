Lens switching — 0.5×, 1×, 2× (detects camera labels on iPhone 15 to find the ultrawide, main, and telephoto). Lens can be switched mid-session.
Precision interval — stored as a raw parseFloat(), never rounded. A live readout shows the exact millisecond value as you type. Timing uses drift-correction (nextFrameAt += intervalMs) so long sessions stay accurate.
Exposure lock — tries exposureMode: 'manual' via applyConstraints. If the browser supports it (iOS 17+ does), the exposure, ISO and shutter are frozen when recording starts. A badge appears in the viewfinder to confirm it's active.
Maximum resolution — requests width/height: { ideal: 9999 } so iOS hands back the highest resolution it'll offer through getUserMedia.
Frame capture — each frame is drawn to a canvas and saved as a 98%-quality JPEG blob in memory.
Video export — frames are replayed into a second canvas while MediaRecorder records the canvas stream. Tries video/mp4 first (works on iOS 17+), falls back to WebM.
iOS download — on iOS, the download link opens in Safari where you can tap the share icon → Save to Photos or Save to Files.
