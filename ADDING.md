# Adding a new feet pic

## Steps

1. Put the image in the `images/` folder.
   - Name it after the character, e.g. `vaelia.jpg`
   - Filename case matters on GitHub Pages. If the file is `vaelia.JPG`, the path in `index.html` must be `images/vaelia.JPG`.

2. Open `index.html` and add a line at the **top** of the `characters` array (newest on top):

   ```javascript
   { name: "charactername", image: "images/charactername.jpg" },
   ```

   Do not copy `index.html` over `404.html`. That file is the URL redirect and should stay as-is.

3. Commit and push:

   ```powershell
   git add images/charactername.jpg index.html
   git commit -m "add charactername"
   git push
   ```

4. Wait 1–2 minutes for GitHub Pages to rebuild, then check:
   - https://warcraftfeet.com
   - https://warcraftfeet.com/charactername
   - Hard refresh with `Ctrl+F5` if you don't see it yet.
