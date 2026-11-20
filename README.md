# MedGuide

A static PWA made with HTML, CSS and vanilla JavaScript. No backend, Node.js, framework or external medicine API is used. The 651-entry generic-name catalogue is bundled locally in `medicines.js`.

## Clinical safety and catalogue limitations
This is an educational index, not a validated clinical decision-support tool or complete medicine monograph. For practical reasons, many safety fields use conservative class-level summaries rather than verified, medicine-specific details. Do not use this app to prescribe, calculate doses or make patient-specific decisions. Verify each medicine against current Philippine FDA product information, the actual product insert and an authoritative current reference. Brand availability varies by country and product. The references listed are sources to consult, not citations confirming every statement in each entry.

## Publish on GitHub Pages
1. Create/sign in to a GitHub account at https://github.com/.
2. Click **New repository**, name it `medguide`, choose **Public**, and create it.
3. In the repository choose **Add file → Upload files**.
4. Extract the downloaded ZIP on your computer. Open the extracted `MedGuide` folder and upload its contents: all seven root files and the `icons` folder. Keep the folder and filenames unchanged.
5. Click **Commit changes**.
6. Open **Settings → Pages**.
7. Under **Build and deployment**, choose **Deploy from a branch**.
8. Select branch **main** and folder **/(root)**, then **Save**.
9. Wait for publication. Your URL will look like `https://YOUR-USERNAME.github.io/medguide/`. Copy the exact URL shown by GitHub Pages.
10. Open the HTTPS URL on your phone. Keep it online until it has loaded fully, then refresh once.

## Install
- **Android Chrome:** open the HTTPS site; use the Install app button/browser prompt or browser menu → Install app / Add to Home screen.
- **iPhone/iPad:** open the URL in Safari → Share → Add to Home Screen. iOS may not show Android's install prompt.
- **Desktop Chrome/Edge:** use the install icon in the address bar or browser menu → Install MedGuide.
- You can also use it as an ordinary website without installing.

## Offline test
After a successful online visit and refresh, turn on airplane mode and reload. Search medicines, select a result, browse categories and use Back. The service worker caches `medicines.js` with the app shell, so the catalogue is available offline after it has been cached. A first visit cannot work offline.

## NFC tag
Publish first and copy the final public HTTPS URL. With an NFC-writing app, create one NDEF URL/URI record containing only that URL (for example `https://YOUR-USERNAME.github.io/medguide/`). Write it to the NFC tag and test it with a phone. The tag contains the URL only; an initial online visit is still required to cache the app.

## Add a medicine later
1. Open `medicines.js` in a plain-text editor.
2. Copy one complete medicine object between `{` and `}`.
3. Give it a new unique `id` and unique `genericName`.
4. Update every field using verified information. Keep the exact field names. `brandNames`, `keywords` and `references` are arrays.
5. Ensure there is a comma between adjacent objects. Save the file.
6. Upload the changed `medicines.js` to GitHub and commit the change.

Do not invent product brands, indications, routes, adverse effects or contraindications. Search reads generic name, brand names, class, category, uses and keywords.

## Update the offline cache
Whenever you change project files, open `service-worker.js` and change `medguide-v1` to `medguide-v2`. Commit both changes. On the next online visit the new cache is installed and the old `medguide-*` cache is removed. Users must reconnect to receive updates.

## Files
`index.html`, `style.css`, `app.js`, `medicines.js`, `manifest.json`, `service-worker.js`, `README.md`, `icons/icon-192.png`, `icons/icon-512.png`.
