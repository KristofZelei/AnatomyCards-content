# AnatomyCards content

The text shown on the cards of the AnatomyCards iOS app: Latin names, origin,
insertion, innervation and action, in English (`en`) and Hungarian (`hu`).

The app downloads `card_texts.json` from this repository in the background when it
starts, and uses the new text **from the next launch**.

## Fixing a card

1. Open `card_texts.json` and find the card by its id (e.g. `gluteus_maximus`) or by searching for the wrong text.
2. Edit the text. Each card looks like this:

   ```json
   "abductor_digiti_minimi_of_hand": {
     "latinName": "Musculus abductor digiti minimi manus",
     "en": { "origin": "…", "insertion": "…", "innervation": "…", "action": "…" },
     "hu": { "name": "…", "origin": "…", "insertion": "…", "innervation": "…", "action": "…" }
   }
   ```

3. **Raise `version` at the top of the file by one.** The app only takes a file whose
   version is higher than the one it already has.
4. Commit to `main`.

Notes:
- Keep the file valid JSON (quotes, commas). An invalid file is ignored by the app.
- A missing or empty field falls back to English, then to the text built into the app.
- Card ids, images and regions come from the app itself; new cards cannot be added here.
- GitHub may serve the old file for a few minutes after a commit.
- Before an app release, copy this file to `AnatomyCards/Data/card_texts.json` in the app
  repository so new installs start with the latest text.
