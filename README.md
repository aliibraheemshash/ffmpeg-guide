# FFmpeg Guide

## Why We Need FFmpeg?
FFmpeg is a powerful multimedia framework that allows us to record, convert, edit, and stream audio and video files. It is widely used for processing media files due to its speed, efficiency, and compatibility with multiple formats.

## Why is FFmpeg Better than Other Editors?
- **Lightweight & Fast:** Works via command line without a heavy GUI.
- **Supports Multiple Formats:** Handles almost every media format.
- **No Quality Loss:** Processes videos without unnecessary re-encoding.
- **Automated & Scriptable:** Ideal for batch processing and automation.
- **Cross-Platform:** Runs on Windows, Linux, and macOS.

## Install FFmpeg on Windows
To install FFmpeg using Chocolatey, run the following command in PowerShell:
```powershell
choco install ffmpeg
```

## Merge Audio with Video
To add an external audio file to a video while keeping the original video unchanged:
```bash
ffmpeg -i inputVideo.mp4 -i inputAudio.mp3 -c:v copy -map 0:v:0 -map 1:a:0 -shortest output.mp4
```

## Extract a Frame from Video
To capture a frame from a specific timestamp in a video:
```bash
ffmpeg -i inputVideo.mp4 -ss 00:00:05 -vframes 1 frame.png
```

## Add Text (Name) to Video at a Specific Position
To overlay text onto a video at a given position (determined by checking coordinates in an image editor like Paint):
```bash
ffmpeg -i input.mp4 -vf "drawtext=text='Your Name':x=315:y=104:fontsize=24:fontcolor=white" -c:a copy output.mp4
```

This command places the text "Your Name" at **x=315, y=104** in the video.

