# Recite

A memorization website. Pick a passage, choose how much of it to blank out, and fill in the gaps. Each passage can have audio to listen along with. Each person enters their email, and their practice history is kept under it in their own browser.

## Put it online with GitHub Pages

1. On github.com, open the repository (it must be **public** for GitHub Pages on a free account).
2. Click **Add file → Upload files**, drag in everything from this folder (`index.html`, `library.json`, `README.md`, and the `passages` and `audio` folders), and click **Commit changes**.
3. Go to **Settings → Pages**. Under "Build and deployment", set **Source** to *Deploy from a branch*, choose the **main** branch and the **/ (root)** folder, and click **Save**.
4. After a minute or two the site is live at `https://<your-username>.github.io/<repo-name>/`.

Opening `index.html` by double-clicking it won't load the passages. Use the GitHub Pages address.

## Add a passage

1. Upload a plain text file into the `passages` folder, for example `passages/psalm-23.txt`. Line breaks are kept.
2. Edit `library.json` (click the file, then the pencil icon) and add an entry:

```json
{
  "passages": [
    {
      "id": "gettysburg",
      "title": "Gettysburg Address (example)",
      "file": "passages/gettysburg.txt",
      "audio": []
    },
    {
      "id": "psalm-23",
      "title": "Psalm 23",
      "file": "passages/psalm-23.txt",
      "audio": ["audio/psalm-23.mp3"]
    }
  ]
}
```

- `id` must be unique and should never change, because people's history is stored under it.
- Separate entries with a comma, and don't leave a comma after the last one.
- To remove the example, delete its entry and `passages/gettysburg.txt`.

## Add audio

Upload the recording into the `audio` folder, then list it in that passage's `audio` list. To show a friendlier name than the file name, use `{ "file": "audio/psalm-23.mp3", "name": "Read slowly" }`. Keep files under 25 MB (GitHub's limit for web uploads); MP3 is the safest format.

## About user history

- History is saved in each person's browser, under the email they type in. It doesn't follow them to another device or browser.
- Nothing is sent anywhere, so the site owner can't see anyone's history.
- Clearing browser data erases it.
