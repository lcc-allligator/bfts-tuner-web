# BFTS Tuner on your Android phone

The phone version is a small web app. You put it on a free GitHub web address once, open that
address in Chrome, and install it to your home screen. After the first load it also opens with no
internet connection.

Time needed: about 10 minutes.

You will use the files in this folder:
`index.html`, `manifest.webmanifest`, `sw.js`, `icon-192.png`, `icon-512.png`.
None of them are hidden files, so the upload works normally.


## What's new

- **Bigger gauge**: the arc and needle now use the full width of the screen, about 18% larger than before.
- **Buzz Feiten open strings is now the default preset, and attack mode is on by default.**
  If you used an older version, the app keeps your A4 and offsets but switches to these two new
  defaults the first time it opens. Change them back with the buttons if you prefer.
- **New look**: a glowing analog arc gauge, an LED fine-tune bar, a large glowing note name, status
  pills for the preset, Drop D and attack state, and glowing string buttons.

---

## PART 1: Put the app on a web address

### Step 1. Create a NEW repository for the phone app
Do not reuse the plugin repository.

1. On GitHub, click the **+** at the top right, then **New repository**.
2. **Repository name:** `bfts-tuner-web`
3. Choose **Public**.
   - This is needed because GitHub's free plan only publishes web pages from public
     repositories.
   - It contains only the tuner, nothing personal. Your plugin repository can stay private.
4. Leave everything else as it is and click **Create repository**.

### Step 2. Upload the five files
1. Unzip the file you downloaded from Claude.
2. On the new repository page, click **uploading an existing file**.
3. Open the unzipped folder, select the five files (`index.html`, `manifest.webmanifest`,
   `sw.js`, `icon-192.png`, `icon-512.png`; you can also include `PHONE-GUIDE.md`) and drag
   them into the browser window.
   - Drag the **files**, not the folder around them. The files must sit at the top level of
     the repository, not inside a subfolder.
4. Click **Commit changes**.

### Step 3. Turn on GitHub Pages
1. In the repository, click **Settings** (top row of tabs).
2. In the left menu click **Pages**.
3. Under **Build and deployment**, set **Source** to **Deploy from a branch**.
4. Under **Branch**, choose **main** and the folder **/ (root)**, then click **Save**.

### Step 4. Get your address
1. Wait 1 to 3 minutes, then refresh the Pages settings page.
2. A box at the top says **Your site is live at ...**. The address will look like this:
   `https://YOUR-GITHUB-USERNAME.github.io/bfts-tuner-web/`
3. Click **Visit site** to check it. You should see the tuner with a **Start tuning** button.

If you see a "404" page, wait another minute or two and refresh. If it persists, check that the
files are at the top level of the repository (Step 2) and that Step 3 says branch **main** and
folder **/ (root)**.

---

## PART 2: Install it on your phone

### Step 5. Open it in Chrome
1. On the phone, open **Chrome** and type your address from Step 4 (you can also message the
   link to yourself and tap it).
2. Tap **Start tuning**.
3. Chrome asks to use the microphone. Tap **Allow** (choose **While using the app** if Android
   offers it).

### Step 6. Add it to the home screen
1. Tap the Chrome menu (the **three dots** at the top right).
2. Tap **Add to Home screen** (on some versions **Install app**), then **Install**.
3. A **BFTS Tuner** icon appears on your home screen. From now on, open it from there. It runs
   full screen like a normal app.

---

## PART 3: Tuning

1. At the top choose a preset:
   - **Standard**: no offsets.
   - **BFTS open**: Buzz Feiten targets for the open strings.
   - **BFTS 12th fret**: Buzz Feiten intonation check. Fret each string at the 12th fret (the
     fretted note, not the harmonic). The note names shown are an octave higher.
2. Hold the phone close to the guitar: near the soundhole on an acoustic or nylon-string guitar,
   or near the amp or the pickup area on an electric. A few centimetres to 30 cm usually works.
3. Pluck one string. The big letter shows the string it hears, and the needle shows how many
   cents you are off. The thin bar under the readout is the microphone level. If it doesn't
   move when you play, the phone isn't hearing the guitar.
4. Tune until the reading turns **green** (within 1 cent). The lower bar is a fine view of
   plus or minus 5 cents.
5. The offsets are already included in the target, so green means "tuned to the Buzz Feiten
   target". The line under the reading shows the target frequency and the offset used.
6. **Drop D** makes the 6th string target D2. In BFTS open it uses its own offset (-4 cents by
   default; that value came from you and I could not find an independent source, so check it
   against your reference).
7. **Attack mode**: notes settle flat as they ring. With this on, the tuner reads the first
   moments of each pluck (about 0.1 to 0.3 seconds in) and holds that reading, labelled
   "ATTACK reading". Re-strike the string to update it, about once a second.
8. Tap a string button to tune against that specific string only (this turns off
   auto-detect). Tap **Auto-detect** to go back.
9. **Play tone** plays the selected string through the phone speaker, including its offset, so
   you can tune by ear. Detection pauses while the tone plays.
10. **A4** sets the reference pitch (440 by default). Use the minus and plus buttons or type a
    value.
11. Tap **Offsets (cents)** at the bottom to edit the six offsets for the current preset.
    **Reset** restores the defaults. Your settings are remembered on the phone.

Offsets used by default (cents):

| String | Open (BFTS open) | 12th fret (BFTS 12th) |
|---|---|---|
| 6th E | -2 | 0 |
| 5th A | -2 | 0 |
| 4th D | -2 | +1 |
| 3rd G | -2 | +1 |
| 2nd B | +1 | 0 |
| 1st E | 0 | 0 |
| 6th, Drop D (D2) | -4 | n/a |

Use the Buzz Feiten presets only on a guitar with a Buzz Feiten nut. On any other guitar use
Standard.

---

## PART 4: Updating the app later

When Claude gives you a new version:

1. Unzip the new `BFTS-Tuner-Android-Web.zip`.
2. Open your `bfts-tuner-web` repository on GitHub and click **Add file, then Upload files**.
3. Drag in the five files again (`index.html`, `manifest.webmanifest`, `sw.js`,
   `icon-192.png`, `icon-512.png`). Files with the same name are replaced.
4. Click **Commit changes**. GitHub republishes the page within 1 to 3 minutes.
5. On the phone, **close the app completely** (swipe it away from recent apps) and open it
   again. If it still looks old, open the web address in Chrome and pull down to refresh once.

Your saved settings stay on the phone.

---

## Troubleshooting

**"Play a string..." never changes.**
- Watch the thin level bar. If it never moves, check the microphone permission: tap the padlock
  or settings icon next to the address in Chrome, then **Permissions**, then allow
  **Microphone**. If you installed the app, open Android **Settings, then Apps, then BFTS
  Tuner (or Chrome), then Permissions, then Microphone**.
- Close other apps that might be using the microphone (recorders, video calls).
- Unplug or disconnect Bluetooth headphones, which can take over the microphone.
- Move the phone closer, and pluck a bit harder. Very quiet signals are ignored.

**The reading jumps around.**
Let one string ring on its own and mute the others with your hand. Room noise or other
instruments nearby can confuse any microphone tuner.

**The reading seems off by a few cents compared with another tuner.**
Check the preset first (Standard and Buzz Feiten differ by up to 2 cents, and the 12th-fret preset
reads an octave higher) and check **A4** is what you expect.

**It stopped working after I switched apps.**
Reopen the app. Android can pause the microphone when an app is in the background.

**I changed the files on GitHub, but the phone shows the old version.**
Close the app completely and reopen it. If it still looks old, open the address in Chrome and
refresh once.

**The page says it needs https.**
Open the tuner from the `https://...github.io/...` address, not from a file saved on the phone.
The microphone only works on secure web pages.

---

## Notes

- Everything runs on the phone. No audio is recorded or sent anywhere.
- The app asks Android not to apply voice processing (noise suppression, echo cancellation and
  automatic gain), because those distort pitch. Some phones may ignore the request. If your
  readings look unstable on every string, tell Claude the phone model.
- The tuner uses the same pitch-detection method as the Windows plugin. In simulated tests it
  was accurate to within about 0.15 cents. Real-world accuracy also depends on the phone's microphone,
  the guitar and the room.
