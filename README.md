# Kalimat Plus كَلِمَات

A free Fusha (Modern Standard Arabic) vocabulary trainer for deeper topics. Live at https://kalimat-plus.ummahapps.ai/

Discussion phrases (opinions, agreeing, contrast, cause and effect, linking words) have moved to Takallum, https://takallum.ummahapps.ai/, where each one has its own speaking drill.

**Words:** 522 words and phrases with full harakat. 277 are in four topics: religion and worship, tarbiyyah and upbringing (including modern parenting: screens, social media, peer pressure, bullying), relationships and character, and the environment.

**Feelings and sayings:** 47 more are expressive words such as flame, dignity, longing, imagination, to smile, to give up hope and to feel at ease. They were picked from the words used in well-loved Arabic sayings, and their example sentences are written for the app. They are in `DATA.lit`.

**GCSE Arabic:** 198 more are for GCSE Arabic (Pearson Edexcel), in a group for each of the 13 topics of the five GCSE themes: Identity and culture (Who am I?, Daily life, Cultural life); Local area, holiday and travel (Holidays, Travel and tourist transactions, Town, region and country); School (What school is like, School activities); Future aspirations, study and work (Using languages beyond the classroom, Ambitions, Work); International and global dimension (Bringing the world together, Environmental issues). They are in `GCSE` in `index.html`. Each GCSE group in `CATS` has its theme as a third item, and the group lists show a heading where the theme changes. The Learn tab has a GCSE only button; until a learner chooses, it starts with the four topics that are not GCSE. Takallum has speaking phrases for the same topics.

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
Takallum Kids, Kalimat, Kalimat Plus and Takallum share four things on the same device through `ummah.js`, which is copied into each app's folder (keep the four copies identical):
- **Learners:** name, boy or girl (man or woman), and animal, in the `ua_l` cookie on `.ummahapps.ai`. A learner added in one app appears in the others; a learner still called "Learner 1" stays in its own app until renamed. Removing a learner asks first, then removes them from all four apps: each app deletes their progress the next time it opens.
- **Known words:** words learned in Takallum Kids and Known well words in Kalimat and Kalimat Plus go into a per-learner `ua_w_<id>` cookie as short hashes of the bare Arabic. A cookie holds 600 words, so the rest go on in `ua_w_<id>_1` to `ua_w_<id>_4`, up to 3000 words a learner. Kalimat and Kalimat Plus offer to add words known from the other apps.
- **Settings:** voice speed (slow, normal, natural), playing the Arabic straight away and vowel marks go with each learner in a `ua_s_<id>` cookie (`ua_s_d` for a learner with no name yet), and the voice help goes with the device in `ua_d`. The Settings panel that changes them is drawn by `ummah.js`, so it is the same in all four apps; each app opens it from its learner row or settings sheet and turns the speed into its own voice rate. The first time an app loads the shared settings, what was set in that app before fills in for the learners already on the device; new learners start from the defaults.
- **Today’s practice:** a card at the top of each app, drawn by `ummah.js`, with three steps like the Hifdh Helper’s day: revise old work (Known well checks in Kalimat, memory checks in Kalimat Plus, solid sentences that are due in Takallum, the warm-up in Takallum Kids), strengthen recent work (up to 10 Learning words or sentences not yet solid), and something new (3, 5 or 10 a day). Each app saves its own counts for the learner in a `ua_p_<id>` cookie (old work due today and each of the next 6 days, recent work, and today’s tallies) and the card adds up the apps chosen in Settings. Revising 20 counts as enough for one day. A day with any practice in any app counts towards the days in a row. The app chips on the card link to the other apps with `#ua-start=old|recent|new`, which starts that step there.

Each page starts with the four apps’ icons as quick links, top right in line with the page, with a gold ring on the app you are in, and ends with the same four-app family strip. On localhost, `ummah.js` points the strip's links at the local servers (Kids 8771, Kalimat 8766, Kalimat Plus 8772, Takallum 8770).

## SEO and GEO
`index.html` has meta tags, Open Graph and JSON-LD (WebApplication + FAQPage). `robots.txt`, `sitemap.xml` and `llms.txt` sit at the root.

## Running locally
```
node serve.js
```
Then open http://localhost:8765

## Already learnt
Above the word cards, Mark all shown as Known well marks every word in the group, level or search on screen as Known well after a warning. They skip the Learning stage, and their first checks are spread over the next month.

## Learn and the game goal
The Learn tab (the first tab) gives the learner their next words instead of asking them to choose. They tick any number of groups and how many words at a time (5, 10 or 15), then tap Give me new words: the next words taken in turn from each ticked group, skipping words already learned, known or swapped out. Before starting they can Swap a word or say I know it (it goes to Known well, first memory check 7 to 30 days away). The words are then met one by one like flashcards, with sound, plural or present tense and the example sentence, followed by a quick check (pick the meaning; a miss comes back once), and become learned. Add all marks every word in the ticked groups as learned at once and shows them as flashcards. Go through them one by one runs the learned words as flashcards with the meaning hidden until tapped. The choices are kept per learner in `kpp-path`.

The Game tab starts with Today’s goal: the Memory check when words are due, then Read it, Say it from memory, and Say the verb forms (or Say the plural), 10 answers each. The step to do next has a Play button, and finishing a step moves the game on to the next one. Counts are kept per learner per day in `kpp-goal`.
