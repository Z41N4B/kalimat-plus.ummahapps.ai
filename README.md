# Kalimat Plus كَلِمَات

A free Fusha (Modern Standard Arabic) vocabulary trainer for deeper topics. Live at https://kalimat-plus.ummahapps.ai/

Discussion phrases (opinions, agreeing, contrast, cause and effect, linking words) have moved to Takallum, https://takallum.ummahapps.ai/, where each one has its own speaking drill.

**Words:** 277 words and phrases with full harakat in four topics: religion and worship, tarbiyyah and upbringing (including modern parenting: screens, social media, peer pressure, bullying), relationships and character, and the environment.

## Features
- Tap any word to hear it at slow, normal or natural speed (uses the device's Arabic text-to-speech voice)
- An example sentence with English translation for every entry
- Verbs with present tense and verbal noun; nouns with sound or broken plurals
- Notes on 52 words: which preposition a verb takes, tricky plurals and endings, and words often confused
- Games: read it, say it from memory, say the verb forms, say the plural
- Mark words as learned; 5 right in a row in the game moves a word to Known well
- Spaced memory checks bring Known well words back now and then; forgotten ones return to the game
- Add your own words
- Up to 3 learners on one device, each with their own progress, shared with Takallum Kids, Kalimat and Takallum. Learner p1 keeps the original `kpp-` storage keys.
- Words known from the other apps: a note on the Words tab offers to mark them as learned

## Shared with the other apps
Takallum Kids, Kalimat, Kalimat Plus and Takallum share two things on the same device through `ummah.js`, which is copied into each app's folder (keep the four copies identical):
- **Learners:** name, boy or girl (man or woman), and animal, in the `ua_l` cookie on `.ummahapps.ai`. A learner added in one app appears in the others; a learner still called "Learner 1" stays in its own app until renamed.
- **Known words:** words learned in Takallum Kids and Known well words in Kalimat and Kalimat Plus go into a per-learner `ua_w_<id>` cookie as short hashes of the bare Arabic. Kalimat and Kalimat Plus offer to add words known from the other apps.

Each page also ends with the same four-app family strip. On localhost, `ummah.js` points the strip's links at the local servers (Kids 8771, Kalimat 8766, Kalimat Plus 8772, Takallum 8770).

## SEO and GEO
`index.html` has meta tags, Open Graph and JSON-LD (WebApplication + FAQPage). `robots.txt`, `sitemap.xml` and `llms.txt` sit at the root.

## Running locally
```
node serve.js
```
Then open http://localhost:8765
