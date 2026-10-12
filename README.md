# Recite

**Memorize passages one gap at a time.**

Recite is a website for memorizing text. Pick a passage, choose how much of it to hide, and fill in the missing words until you know it by heart. Each passage can have audio to listen along with, and everyone's progress is tracked under their email.

🔗 **Live site:** https://engitakla.github.io/Recite/

---

## How to practice

1. **Sign in with your email.** Your scores and history are saved under it. Next time, click your email under *Used on this device*.
2. **Pick a passage** from the list on the left.
3. **Listen.** Play the recording, adjust the **Speed** (0.5×–1.5×), or turn on **Repeat**. **Read** mode shows the full text.
4. **Fill in the blanks.** Use the **Blanked out** slider (or the 25 / 50 / 60 / 75 / 100 buttons) to choose how much is hidden, then type the missing words.
   - Blanks turn green as soon as you type the right word, and the cursor jumps to the next one.
   - **Space** or **Enter** moves to the next blank.
   - **Hint** adds the next letter. **Show first letters** gives a head start on every blank.
   - **Check** marks your answers. **Reveal answers** shows the rest. **New blanks** hides a different set of words.
5. **Level up.** After a perfect score, click **Hide 10% more**. Work your way up to 100%.
6. **See your progress.** **My progress** shows your sessions, best scores, and the hardest level you've completed for each passage.

Answers aren't case sensitive, and punctuation is ignored. Verse numbers and small words (*a, the, of, and*…) always stay visible.

---

## Privacy

- Your email and history are stored **only in your own browser**. Nothing is sent to anyone, including the site owner.
- History doesn't move between devices or browsers, and clearing your browser data erases it.

---

## Managing the site

### Files

| File / folder | What it is |
|---|---|
| `index.html` | The website |
| `library.json` | The list of passages and their audio |
| `passages/` | One `.txt` file per passage |
| `audio/` | Recordings (`.mp3`) |

### Add a passage

1. Upload a `.txt` file to the `passages` folder (**Add file → Upload files**). Line breaks are kept, so one verse per line works well.
2. Open `library.json`, click the ✏️ pencil icon, and add an entry:

```json
{
  "passages": [
    {
      "id": "Part 1 Matthew 1-16",
      "title": "Part 1 Matthew 1-16",
      "file": "passages/Part 1 Matthew 1-16.txt",
      "audio": ["audio/Matthew 5 Pt1.mp3"]
    },
    {
      "id": "Matthew 6 Part 1",
      "title": "Matthew 6 Part 1",
      "file": "passages/Matthew 6 Part 1.txt",
      "audio": []
    }
  ]
}
```

3. Click **Commit changes**. The passage shows up on the site within a minute or two.

### Add audio

1. Upload the recording to the `audio` folder. MP3 works everywhere, and GitHub's website accepts files up to 25 MB.
2. Add it to the passage's `audio` list in `library.json`:

```json
"audio": ["audio/Matthew 6 Part 1.mp3"]
```

To show a friendlier label, or to add more than one recording:

```json
"audio": [
  { "file": "audio/Matthew 6 Part 1.mp3", "name": "Normal speed" },
  { "file": "audio/Matthew 6 Part 1 slow.mp3", "name": "Read slowly" }
]
```

### Rules for `library.json`

- ✅ Put a comma between entries. ❌ Don't put a comma after the last one.
- File names must match **exactly**, including capital letters, spaces, and the extension.
- Each `id` must be unique. **Never change an `id`**, because people's history is saved under it. The `title` can be changed any time.
- Passages appear in the same order as in the file.

### Troubleshooting

| Problem | Fix |
|---|---|
| "The passages could not be loaded" | There's a comma mistake in `library.json`. Paste it into [jsonlint.com](https://jsonlint.com) to find it. |
| "The text file … was not found" | The `file` name doesn't match the file in `passages/`. |
| Audio won't play | The name in `audio` doesn't match the file in `audio/`. |
| Changes don't appear | Wait a minute or two, then refresh. |
| Nothing loads when opening `index.html` from your computer | That's expected. Use the live site link. |

### First-time setup

**Settings → Pages →** set **Source** to *Deploy from a branch*, choose **main** and **/ (root)**, and click **Save**. The repository must be public.

---

## Credits

Scripture taken from the New King James Version®. Copyright © 1982 by Thomas Nelson. Used by permission. All rights reserved.
