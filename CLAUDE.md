# Soundboard — Project Notes

A fun workshop soundboard hosted on GitHub Pages. Opened as a pinned tab in Arc during online workshops so the host can play sound effects with a single click.

## How sounds work

- Sound files live in the `sounds/` folder as MP3s
- Each sound is defined in the `sounds` array in `index.html` (around line 214)
- Buttons with no audio file yet show as dimmed with a "Soon" label (`ready: false`)
- Sounds marked `loop: true` (elevator, ticking clock, lounge jazz) will repeat until stopped
- Multiple sounds can play at the same time

## How to add a new sound file

1. Find your MP3 and name it to match the `file` field in `index.html` (e.g. `tada.mp3`)
2. Drop the file into the `sounds/` folder in the soundboard project directory
3. Open `index.html` in a text editor, find the `sounds` array (around line 214)
4. Find the entry for that sound and change `ready: false` to `ready: true`
5. Save the file and push to GitHub (commit + push) — the live page will update automatically

To add a **brand new sound** that isn't already listed, add a new line to the `sounds` array in the same format:
```
{ emoji: '🎵', label: 'My Sound', file: 'mysound.mp3', loop: false, color: '#FF6B35', ready: true },
```
Pick any emoji, label, hex colour, set `loop: true` if it should repeat, and make sure the filename matches what's in `sounds/`.

## File naming

| Sound | Filename |
|---|---|
| Elevator Music | elevator.mp3 |
| Applause | applause.mp3 |
| Sad Trombone | sadtrombone.mp3 |
| Ta-da! | tada.mp3 |
| Ticking Clock | ticking.mp3 |
| Drumroll | drumroll.mp3 |
| Laugh Track | laugh.mp3 |
| Ding! | ding.mp3 |
| Countdown | countdown.mp3 |
| Lounge Jazz | lounge.mp3 |

## Hosting

Hosted on GitHub Pages. To update the soundboard, edit `index.html` and push to the `main` branch.

---

## Making sounds audible in Google Meet recordings

By default, sounds played from the browser only come out of your speakers — Google Meet's recording only captures the microphone (Blue Yeti), so the sounds are silent on recordings.

**The fix:** Use BlackHole 2ch (already installed) to pipe system audio into Google Meet alongside your voice.

### One-time setup in Audio MIDI Setup

Open **Audio MIDI Setup** (find it via Spotlight: Cmd+Space, type "Audio MIDI Setup").

**Step 1 — Create a Multi-Output Device** (so you still hear the sounds yourself):
1. Click the **+** button at the bottom left → **Create Multi-Output Device**
2. Tick both **BlackHole 2ch** and your normal listening device (headphones or built-in speakers — whichever you use during workshops)
3. Right-click the new device → Rename it to something like **Soundboard Output**
4. Make sure **BlackHole 2ch is the Master Device** (there's a radio button — select it)

**Step 2 — Create an Aggregate Device** (so Google Meet gets your voice + system audio together):
1. Click **+** → **Create Aggregate Device**
2. Tick **Blue Yeti** and **BlackHole 2ch**
3. Rename it to something like **Meet Microphone**

### Before each workshop

1. Connect your **AirPods** (macOS will switch output to them automatically)
2. **Hold Option and click the speaker icon** in the menu bar → select **Soundboard Output**
   - This routes audio to both your AirPods and BlackHole simultaneously
3. **In Google Meet** settings → Audio:
   - Set **Microphone** to **Meet Microphone**
   - Set **Speakers** to your AirPods (not Soundboard Output — that would cause an echo loop)
   - Leave **Camera** as your Logitech HD webcam (unchanged)
4. Open the soundboard tab and test a sound — you should hear it through your AirPods, and it will appear in the recording.

### After the workshop

Hold **Option + click the speaker icon** → switch back to **AirPods** or **MacBook Air Speakers**.

### Note on AirPods

Soundboard Output is configured with AirPods + BlackHole 2ch. If you ever use different headphones, you'd need to open Audio MIDI Setup and swap them in.
