# 🌱 Sprout Tycoon

A standalone, walk-around garden game that runs in any web browser — on iPhone,
iPad, Android, Windows, Mac, or Linux. No app store, no accounts, no internet
required after the first load. Everything lives in one self-contained
`index.html`, upgraded to an installable **PWA** (Progressive Web App).

## You do NOT need Claude to play it

The Claude link is only convenient hosting. The game is a plain web app you fully
own. Here are the ways to run it, from simplest to best — pick one.

### Option 1 — Just open the file (zero setup)
`index.html` is completely self-contained. Put it on any device and open it in a
browser:
- **Computer:** double-click `index.html`.
- **iPhone/iPad/Android:** save the file (Files app, email, Drive, etc.) and tap
  it to open in the browser.

It runs fully offline and saves your progress in that browser. (This method
can't add an app icon to your home screen — for that, use Option 2.)

### Option 2 — Install it like a real app (recommended best practice)
Host the files once on **GitHub Pages** (free, already set up in this repo), then
install to your home screen. This gives you a fullscreen, offline, icon-on-the-
homescreen app on every platform — the modern way to ship a game without an app
store.

**One-time hosting setup:**
1. Merge this branch to `main` (or push these files to `main`).
2. In GitHub: **Settings → Pages → Build and deployment → Source: “GitHub
   Actions.”**
3. The included workflow (`.github/workflows/pages.yml`) publishes the game to
   `https://<your-username>.github.io/<repo>/` and redeploys on every push.

**Install to home screen from that URL:**
- **iPhone/iPad (Safari):** Share → **Add to Home Screen**.
- **Android (Chrome):** ⋮ menu → **Install app** / **Add to Home Screen**.
- **Desktop (Chrome/Edge):** the **Install** icon in the address bar.

Once installed it launches fullscreen and works with no connection.

### Option 3 — Any other static host
Because it's just static files, you can drop the whole folder onto Netlify,
Vercel, Cloudflare Pages, itch.io, or any web server and it works the same way.

## Bonus: Gun Forge 🔫

`gun-game.html` is a second self-contained game in the same repo. It has two
parts:

**🔧 Workshop — craft weapons.** Start with realistically-drawn guns, blades and a
bomb. **Select any number of weapons — mixing guns, blades and bombs freely — and
Fuse them** into one hybrid: its stats blend and its traits (explosive, homing,
pierce, scatter, burst, incendiary, ricochet…) combine, and cross-type fusions
graft on extra abilities (a gun that also swings a **+Blade** and lobs a **+Boom**).
Bolt a **🔇 silencer** or a **💥 boom-launcher** onto any gun for combos like
*Silenced Rifle +Boom*. Base weapons include lots of **guns** (plus an **RPG**
that fires explosive rockets), **knives & swords** (Knife, Dagger, Machete,
Cleaver, Rapier, Katana, Greatsword) and **throwable bombs** (Frag, Sticky,
Cluster, Molotov, Dynamite, MegaNuke).

**⚔️ Arena — a true 3D first-person team battle** in an outdoor field: **blue sky,
clouds, a sun, grassy ground and stone walls**, rendered with inline WebGL (no
external libraries — still one offline file). Press **＋ Spawn** to drop fighters
onto colored teams — **type in exactly how many you want** (up to 40 per spawn) —
and hand them any weapon. Spawned fighters **mill about peacefully and won't hurt
anyone until you press the ⚔️ Fight button**, so you can set up a battle first.
The fighters are **detailed humanoid soldiers** (helmets, vests, backpacks,
articulated arms/legs, boots, walk cycle, aiming pose and recoil) that walk, aim,
shoot, launch rockets, throw bombs and swing blades. Every team attacks every
other team — **including you** — and the **last team standing wins** (no friendly
fire). Hit **⚔️ Auto-brawl** to pit Red vs Green and watch them fight to a winner.
Your held weapon is drawn in first person **with your hands holding it** — a real
rifle, an RPG tube, or an actual knife/blade — and traits play out in 3D. A
**forge machine** sits in the arena, and the 🔧 Forge button jumps to the
Workshop.

- **Desktop:** click the arena to capture the mouse, **WASD** move, **mouse**
  look/aim, **click/Space** fire, **R** reload, **G** bomb, **V** melee, **Esc**
  release.
- **Touch:** left stick moves, drag to look, **FIRE** shoots, plus 🔪 melee and
  💣 bomb buttons.

Your arsenal saves in the browser. Reach it from the same host at
`.../gun-game.html`.

## What's in the repo

| File | Purpose |
| --- | --- |
| `index.html` | The entire game (HTML + CSS + JS inlined). Runs by itself. |
| `gun-game.html` | Gun Forge — the build-fuse-test gun sandbox. Also self-contained. |
| `manifest.webmanifest` | PWA metadata (name, icons, colors, standalone display). |
| `service-worker.js` | Offline caching so the app loads with no connection. |
| `icon-192.png`, `icon-512.png` | Home-screen / install icons. |
| `.github/workflows/pages.yml` | Auto-deploys to GitHub Pages. |

> The extra files only power the “install like an app” experience. Opening
> `index.html` on its own still works — the service worker simply stays dormant
> until the game is served over http(s).

## How to play

- **Move:** WASD / arrow keys, or the on-screen D-pad on touch devices.
- **Interact:** press **E** / the on-screen button at shop doors and plots.
- Buy seeds at the 🌱 **Seed Shop**, plant them, and harvest fruit one at a time.
- Plants are **permanent** and regrow each picked fruit every 5 minutes.
- Sell your crops at the 🏪 **Market**.
- 📜 **History** logs everything; the shop restocks every 4 minutes with a pop-up.
- 🍃 **Leaf Shop** is a *demo* premium store (no real money is charged) with a
  country-currency picker.

## Rarities, grow times & regrow capacity

| Rarity | Matures in | Fruit held (regrows 5m each) | Stock chance |
| --- | --- | --- | --- |
| Common | seconds | 3 | ~100% |
| Rare | 10 min | 5 | 25–35% |
| Epic | 30 min | 8 | ~10% |
| Legendary | 1 hour | 4 | 1% |
| Mythic | 2 hours | 🌹 1 · 🔥 2 | 0.1% |
| Exclusive | 5 min | 6 | Leaf Shop only |

All seed stats live in the `SEEDS` array at the top of the `<script>` in
`index.html` — easy to tweak.
