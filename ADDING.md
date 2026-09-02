# Adding a new feet pic

## Steps

1. Put the image in the `images/` folder.
   - Name it after the character, e.g. `zoe.jpg`
   - Filename case matters on GitHub Pages. If the file is `zoe.JPG`, the path in `feet/index.html` must be `images/zoe.JPG`.

2. Open `feet/index.html` and add a line at the **top** of the `characters` array (newest on top):

   ```javascript
   { name: "charactername", image: "images/charactername.jpg" },
   ```

3. Copy `feet/index.html` over `404.html` (needed for `/feet/charactername` URLs on GitHub Pages):

   ```powershell
   Copy-Item feet/index.html 404.html -Force
   ```

4. Commit and push:

   ```powershell
   git add images/charactername.jpg feet/index.html 404.html
   git commit -m "add charactername"
   git push
   ```

5. Wait 1–2 minutes for GitHub Pages to rebuild, then check:
   - https://warcraftfeet.com/feet/
   - https://warcraftfeet.com/feet/charactername
   - Hard refresh with `Ctrl+F5` if you don't see it yet.

# Adding a rage whisper

Folder: `rage_whispers_images/<character>/`
- `1-a` = the gank (combat log / kill). Smaller, shown first.
- `1-b` = the rage whisper. This is the main image.
- Next incident for the same character is `2-a` and `2-b`. Filename case matters.

Open `rage-whispers/index.html` and add at the **top** of the `whispers` array:

```javascript
{
    name: "superbull",
    names: ["superbull", "zagan"],
    killedBy: ["xfraz", "pee"],
    items: [
        { gank: "rage_whispers_images/superbull/1-a.JPG", whisper: "rage_whispers_images/superbull/1-b.png" }
    ]
},
```

- `name` is the URL slug: `/rage-whispers/superbull`
- `names` is who got killed. Shown on the card.
- `killedBy` is who did it. Shown as `Killed by: ...`
- Search matches both lists.
- Extra `1-a`/`1-b` pairs go in `items` (then `2-a`/`2-b`, etc). Each pair is its own box.

Commit the folder, the images, and `rage-whispers/index.html`. You do not copy this page over `404.html`.

Do not drop the `rage-whispers` redirect at the top of `feet/index.html` when you copy that file over `404.html`.
