# Adding a new feet pic

## Steps

1. Put the image in the `images/` folder.
   - Name it after the character, e.g. `zoe.jpg`
   - Filename case matters on GitHub Pages. If the file is `zoe.JPG`, the path in `index.html` must be `images/zoe.JPG`.

2. Open `index.html` and add a line at the **top** of the `characters` array (newest on top):

   ```javascript
   { name: "charactername", image: "images/charactername.jpg" },
   ```

3. Copy `index.html` over `404.html` (needed for `/charactername` URLs on GitHub Pages):

   ```powershell
   Copy-Item index.html 404.html -Force
   ```

4. Commit and push:

   ```powershell
   git add images/charactername.jpg index.html 404.html
   git commit -m "add charactername"
   git push
   ```

5. Wait 1–2 minutes for GitHub Pages to rebuild, then check:
   - https://warcraftfeet.com
   - https://warcraftfeet.com/charactername
   - Hard refresh with `Ctrl+F5` if you don't see it yet.
