# Driftwater

A message-in-a-bottle sea, in the spirit of QQ's drift bottles. One HTML file, no build step.

**Live:** https://claude.ai/code/artifact/845314bd-efd4-48a8-a557-2795c08a6b0d

## How it plays

- **Fish.** Cast a line. About 70% of casts bring up a bottle from another player; the rest bring up a crab, fish, or piece of flotsam for your tide pool (19 species across four rarity tiers).
- **Matching.** Which bottle bites is weighted by a compatibility score between you and the sender: shared interests, waking hours (timezone gap), writing pace, temperament, first language, mood pairing, and age band. The score becomes a *tide forecast* of expected exchanges, and the sampler favours high scores with a softmax-style weight.
- **Answer to keep fishing.** Bottles you catch sit in a net that holds three. You must write back or throw a bottle back before you can cast again.
- **Choose what you fish for.** Filter by kind: romance, life lessons, confessions, questions, stories, encouragement, jokes. Your own bottles are tagged with a kind too.
- **Opening.** Tap the bottle: the cork pops, the paper slides out of the neck, the scroll unrolls, and the message writes itself in.
- **Letters.** Replies become a live two-way conversation. The sender sees it appear as soon as someone answers.

## Where the data lives

When opened inside claude.ai the page uses the artifact's shared database (`bottles`, `threads`, `players` collections), so bottles thrown by one person are caught by another. Opened anywhere else, it falls back to an offline harbour of practice bottles stored in the browser.

Player identity is a random id in `localStorage`; no accounts.

## Seeding

`seed/make-seeds.js` writes `seed/bottles.json` (24 starter bottles from fictional castaways with varied profiles so matching works on day one) and injects the same array into `index.html` for the offline harbour. The same file was written to the shared database at launch.
