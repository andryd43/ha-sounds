# SmartHome Sound Files

Audio files for Home Assistant Echo device announcements.

## Format Requirements (Amazon SSML)
- MP3, 24kHz, 48kbps CBR, mono
- HTTPS direct link (no redirects, no auth)
- Max 240 seconds

## Convert with ffmpeg
```bash
ffmpeg -i input.mp3 -ar 24000 -b:a 48k -ac 1 -codec:a libmp3lame output.mp3
```

## Usage in HA
```yaml
service: notify.alexa_media
data:
  message: "<audio src='https://raw.githubusercontent.com/USERNAME/ha-sounds/main/general/day-is-never-finished.mp3'/>"
  data:
    type: tts
  target: media_player.alex
```

## Folders
- `general/` — misc sounds
- `chores/` — chore reminders and completion chimes
- `notifications/` — alerts and announcements
- `bedtime/` — bedtime routine sounds
