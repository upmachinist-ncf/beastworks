# Beastworks — putting it on your phone

Upload these files to free web hosting, open the link on your phone, install it.
About 15 minutes.

```
index.html              the game
manifest.webmanifest    the app's name and icon
sw.js                   makes it work with no internet
icon-192.png            icon
icon-512.png            icon
icon-512-maskable.png   icon
```

Keep all six **in the same folder**. Don't rename any of them.

---

## Step 1 — put the files online

Pick one. Both are free, neither needs a credit card.

### Option A: GitHub Pages

1. Make a free account at **github.com**
2. Click **+** (top right) then **New repository**
3. Name it `beastworks`, choose **Public**, click **Create repository**
4. Click **uploading an existing file**
5. Drag the six files in, then **Commit changes**
6. Go to **Settings** (top of the repo) then **Pages** (left sidebar)
7. Under *Branch*, pick **main** and **/ (root)**, then **Save**
8. Wait about a minute and refresh. Your link is at the top:
   `https://YOURNAME.github.io/beastworks/`

### Option B: Cloudflare Pages

1. Make a free account at **dash.cloudflare.com**
2. Sidebar: **Workers & Pages** then **Create** then **Pages**
3. Choose **Upload assets**
4. Name it `beastworks`, drag the folder in, click **Deploy site**
5. Your link appears when it finishes: `https://beastworks.pages.dev`

---

## Step 2 — install it on your phone

Open your new link in your phone's browser, then:

**iPhone — must be Safari**
Tap **Share** (the square with the arrow up) at the bottom, scroll down,
tap **Add to Home Screen**, tap **Add**.

**Android — Chrome**
Tap the **three dots** top right, tap **Install app**
(or **Add to Home screen**), tap **Install**.

You get a Beastworks icon on your home screen. It opens full screen with no
address bar, and once you've opened it once it works with **no internet at all**.

---

## Moving your creature over

Your creature lives in whichever browser you played in, so it doesn't follow
you by itself.

**From the Claude version to the app:**

1. In the Claude version, open **Save code** and tap **Make a save code**
2. Write down the short code (something like `munoskunks1181`)
3. Open the app, scroll to **Save code**, tap **Use a code**, type it in

**Between two copies of the installed app:**

Short codes need the Claude version, so use the long one instead.
Open **Save code**, expand **Backup code**, tap **Copy backup code**, send it
to yourself, then paste it into **Use a code** on the other device.

Either way you get everything: creature, house, tokens, unlocks and high scores.

---

## Changing the game later

Upload a new `index.html` the same way. **One extra step:** open `sw.js` and
change this line near the top:

```js
const CACHE = 'beastworks-v1';
```

to `beastworks-v2`, then `v3` next time, and so on. Upload that too.

Skip this and phones keep showing the old version out of their cache, and your
changes never appear. This catches a lot of people out.

---

## Sharing it

Send anyone the link. They install it the same way. They don't need a Claude
account, a GitHub account, or anything else.

---

## What this is and isn't

This is a **Progressive Web App**. For almost everything it behaves like a real
app — own icon, full screen, works offline.

It can't go in the Apple App Store or Google Play. That needs a different kind
of build, a paid developer account ($99/year Apple, $25 once Google), and a
review process. The web version is free, instant, and works on both.
