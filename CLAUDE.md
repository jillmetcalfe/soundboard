# Soundboard — Project Notes

A fun workshop soundboard hosted on GitHub Pages. Opened as a pinned tab in Arc during online workshops so the host can play sound effects with a single click.

## How sounds work

- Sound files live in the `sounds/` folder as MP3s
- Each sound is defined in the `sounds` array in `index.html`
- To activate a sound once the file is uploaded, change `ready: false` to `ready: true` for that entry
- Sounds marked `loop: true` (elevator, ticking clock, lounge jazz) will repeat until stopped
- Multiple sounds can play at the same time

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
