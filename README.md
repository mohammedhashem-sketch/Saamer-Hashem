# 🌱 Sprout Tycoon

A browser-based garden growing game. Buy seeds, plant them, watch them grow in
real time, and harvest crops for coins to buy rarer seeds.

## Play

Open **`index.html`** in any web browser. That's it — no install, no build step.
Your progress saves automatically in the browser.

## How to play

1. **Buy seeds** from the shop on the right.
2. **Select** a seed in your inventory, then **click an empty plot** to plant it.
3. Wait for it to grow (a progress bar fills up), then **click the ripe plot** to
   harvest it for coins — or use **Harvest All**.
4. Spend your coins on rarer, more valuable seeds.

## The stock mechanic

The shop **restocks every 45 seconds** and re-rolls its entire inventory. Each
seed has its own chance to appear in stock — the rarer the seed, the lower the
chance:

| Rarity | Example | Stock chance |
| --- | --- | --- |
| Common | 🥕 Carrot, 🌾 Wheat | ~100% |
| Rare | 🍓 Strawberry, 🌽 Corn | 25–35% |
| Epic | 🍉 Watermelon, 🎃 Pumpkin | ~10% |
| Legendary | 🍏 Golden Apple, 🐉 Dragon Fruit | **1%** |
| Mythic | 🌹 Celestial Rose, 🔥 Phoenix Bloom | **0.1%** |

So a mythic seed shows up in the shop only about 1 in 1000 restocks — keep
checking back, or pay 5 coins to force an early restock and roll the dice. Rarer
seeds cost more and take longer to grow, but sell for far more.

Editing which seeds exist, their rarities, costs, grow times, and stock chances
is easy — they all live in the `SEEDS` array at the top of the `<script>` in
`index.html`.
