# EA Sports CBB: Dynasty Logic Prototype (v0.9.xx)

Current Build: Vertical Slice / Mechanics Test
Tech: Vanilla JS, HTML5

[Launch the Prototype](https://lakseru.github.io/ea-cbb-dynastyLogic/)
(Runs in browser, no install needed)

---

### The Idea
I've been messing around with the recruiting logic in College Football 25. I like it, but it obviously doesn't fit basketball. Football is about collecting assets; basketball is about managing egos and chemistry.

I wanted to prototype a system where fit matters more than ratings. I spent time scripting a "Triad" system that penalizes you for signing high-rated players who don't actually fit your coaching scheme.

This repo is just a proof-of-concept for that logic.

### Systems

**1. The "Triad" Fit System**
Instead of a binary "Match/No Match" system, I wrote a weighted logic check that runs every time you scout a player:
* Catalyst (50%): Does the player have the primary stat for the scheme? (e.g., 3PT rating for 'Analytics' offense).
* Enabler (30%): Do they have the secondary IQ stat?
* Inhibitor (Pass/Fail): This is the main mechanic. I added "Deal Breaker" traits. If a player has the "Ball Stopper" trait, they will fail a "Motion Offense" check instantly, even if they are a 5-star recruit.

**2. Fog of War & Ranges**
I didn't want exact numbers showing up immediately like in older games. In this build:
* All stats are hidden ranges by default.
* You have to spend "Scouting Points" to decrypt the array and get the real integer.
* The "Fit Grade" is fuzzy until you scout, so you have to gamble a bit.

**3. Rarity Buckets**
I set up a weighted RNG system for player generation:
* 90%: Standard Archetypes (hard caps on stats).
* 8%: Generational Talents (higher caps).
* 2%: "Aliens." I hardcoded a break in the logic to allow 7'4" players with Guard skills (Wembanyama builds). They're rare, but possible.

---

### To-Do
* Dual Archetypes: Currently, players are locked to one archetype. Need to add hybrid logic (e.g., Two-Way Playmaker).
* UI Polish: The reveal animation is too basic right now.
* Save State: Resets on refresh. Need to add local storage support as well as locking in players to create a team.

### Documentation
I wrote up a full feature spec explaining how this fits into a larger Dynasty Mode loop.
[Read the Design Doc (PDF)](./Project_College_Basketball_Dynasty_Logic_Overhaul.pdf)

---
Built by Xavier Seron.
