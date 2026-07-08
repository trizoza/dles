# assets.DLES.gg

Collection of free assets for daily game makers: words, sounds and images.

I collect daily games at [dles.gg](https://dles.gg) and I see a lot of games created every single week. At the time of writing, there's 852 active games in the collection. That's incredible and I want to support the movement a bit.

When I made my first game [Rotaboxes](https://rotaboxes.com) I had no idea where to start and how to do it. I had a rough idea of a gameplay, I knew HTML, CSS and Javascript but I needed a picture. I just googled "free images" and stumbled on [Unsplash](https://unsplash.com). I ended up downloading one cute picture of a dog and with that I developed my game. Without a service like Unsplash, my game wouldn't exist.

The goal of this repo is to create a collection of free assets for daily games, maintain and conserve them for future use.

So far I see 3 main categories that I'd like to cover: Words, Images and Sounds.

## Words

Even though you can technically find all words used in Wordle in their [source code](https://www.nytimes.com/games-assets/v2/wordle.2cb2da2d44b27be37f0df877458485d700fe8c1e.js), it is explicitly against their terms and conditions and you might get in trouble if you do so. Therefore I've taken the words from ENABLE (Enhanced North American Benchmark LExicon) wordlist which is in public domain and split it into chunks based on letter length to simplify your life, so it's up to you if you create a game based on 5-letter long words, or 3 or who knows 21, totally up to you.

- [2 letter words](assets/words/enable/2-letter-words.txt) - 96 words
- [3 letter words](assets/words/enable/3-letter-words.txt) - 972 words
- [4 letter words](assets/words/enable/4-letter-words.txt) - 3903 words
- [5 letter words](assets/words/enable/5-letter-words.txt) - 8636 words
- [6 letter words](assets/words/enable/6-letter-words.txt) - 15232 words
- [7 letter words](assets/words/enable/7-letter-words.txt) - 23109 words
- [8 letter words](assets/words/enable/8-letter-words.txt) - 28420 words
- [9 letter words](assets/words/enable/9-letter-words.txt) - 24873 words
- [10 letter words](assets/words/enable/10-letter-words.txt) - 20300 words
- [11 letter words](assets/words/enable/11-letter-words.txt) - 15504 words
- [12 letter words](assets/words/enable/12-letter-words.txt) - 11357 words
- [13 letter words](assets/words/enable/13-letter-words.txt) - 7827 words
- [14 letter words](assets/words/enable/14-letter-words.txt) - 5127 words
- [15 letter words](assets/words/enable/15-letter-words.txt) - 3192 words
- [16 letter words](assets/words/enable/16-letter-words.txt) - 1943 words
- [17 letter words](assets/words/enable/17-letter-words.txt) - 1127 words
- [18 letter words](assets/words/enable/18-letter-words.txt) - 594 words
- [19 letter words](assets/words/enable/19-letter-words.txt) - 329 words
- [20 letter words](assets/words/enable/20-letter-words.txt) - 160 words
- [21 letter words](assets/words/enable/21-letter-words.txt) - 62 words
- [22 letter words](assets/words/enable/22-letter-words.txt) - 30 words
- [23 letter words](assets/words/enable/23-letter-words.txt) - 13 words
- [24 letter words](assets/words/enable/24-letter-words.txt) - 9 words
- [25 letter words](assets/words/enable/25-letter-words.txt) - 2 words
- [27 letter words](assets/words/enable/27-letter-words.txt) - 2 words
- [28 letter words](assets/words/enable/28-letter-words.txt) - 1 word
- [All words](assets/words/enable/all-words.txt) - 172820 words - the complete ENABLE list

### Most popular words

The magic of Wordle was partly accomplished thanks to the effort of Josh Wardle's partner who filtered a list of 12 thousand 5-letter words manually to approximately 2.5 thousand words, based on one judgement, do I know this word or not? The full ENABLE list above includes a lot of rare, archaic and technical words that most players would never recognise (e.g. `aalii`). So I decided to filter them too. Below are curated subsets that keep only the everyday ones: every ENABLE word is ranked by how often it actually appears in real-world text, the frequent ones are kept, and proper nouns, brand names, foreign words, crude or offensive terms and the obscure long tail are removed. The result is a "common folk" vocabulary that's a better fit for answers in guessing games, while the lists above are great for allowed guesses. I used two different frequency filter techniques, pick whichever you find better.

#### Norvig filtered

The **`norvig-*`** lists are ranked with Peter Norvig's [word-frequency data](https://www.norvig.com/ngrams/) — the [count_1w.txt](https://www.norvig.com/ngrams/count_1w.txt) list of the ⅓-million most frequent words, derived from the Google Web Trillion Word Corpus and released under the MIT license. A script ranked every ENABLE word of each letter length by its frequency and produced an ordered list and I kept top 30% of each list. Then Claude Fable individually judged: proper nouns/brands/vulgar/foreign and common-but-lower-frequency words at the fuzzy zone deciding to keep vs cut.

- [4 letter popular words (Norvig)](assets/words/enable/norvig-most-popular-4-letter-words.txt) - 2067 words
- [5 letter popular words (Norvig)](assets/words/enable/norvig-most-popular-5-letter-words.txt) - 3743 words
- [6 letter popular words (Norvig)](assets/words/enable/norvig-most-popular-6-letter-words.txt) - 5283 words

#### Wordfreq filtered

The **`wordfreq-*`** lists are generated automatically with the open-source [wordfreq](https://pypi.org/project/wordfreq/) library, so they're fully reproducible from open data. **The Zipf cutoff.** wordfreq scores each word on the _Zipf scale_ — a base-10 logarithmic frequency running from about 0 to 8, where every whole step means the word is 10× more common (`the` ≈ 7.7, `house` ≈ 5.7, `gecko` ≈ 3.0, and the obscure `aalii` ≈ 0). Every ENABLE word is scored, and those at **Zipf ≥ 3.0** are kept — roughly "used at least once per million words", the level below which words start to feel obscure to a general audience. Because raw frequency still ranks proper nouns and profanity highly, offensive terms and obvious names/places are then filtered out. The 3.0 bar is deliberately strict so the lists favour genuinely everyday words; a lower threshold would keep more but rarer words.

- [4 letter popular words (wordfreq)](assets/words/enable/wordfreq-most-popular-4-letter-words.txt) - 1751 words
- [5 letter popular words (wordfreq)](assets/words/enable/wordfreq-most-popular-5-letter-words.txt) - 2648 words
- [6 letter popular words (wordfreq)](assets/words/enable/wordfreq-most-popular-6-letter-words.txt) - 3380 words
- [7 letter popular words (wordfreq)](assets/words/enable/wordfreq-most-popular-7-letter-words.txt) - 3634 words
- [8 letter popular words (wordfreq)](assets/words/enable/wordfreq-most-popular-8-letter-words.txt) - 3315 words
- [9 letter popular words (wordfreq)](assets/words/enable/wordfreq-most-popular-9-letter-words.txt) - 2698 words
- [10 letter popular words (wordfreq)](assets/words/enable/wordfreq-most-popular-10-letter-words.txt) - 1950 words
- [11 letter popular words (wordfreq)](assets/words/enable/wordfreq-most-popular-11-letter-words.txt) - 1159 words
- [12 letter popular words (wordfreq)](assets/words/enable/wordfreq-most-popular-12-letter-words.txt) - 660 words
- [13 letter popular words (wordfreq)](assets/words/enable/wordfreq-most-popular-13-letter-words.txt) - 357 words

## Images

- [Unsplash](https://unsplash.com/) - free photos
- [Pixabay](https://pixabay.com) - free photos, illustrations, vectors

## Sounds

- [ElevenLabs](https://elevenlabs.io/sound-effects) - generate sound effect with AI
- [Pixabay](https://pixabay.com/) - free sounds, music

## 3D Assets

- [Kenney](https://kenney.nl/) - free 3D models, textures, audio and UI packs
- [Sketchfab](https://sketchfab.com/features/free-3d-models) - free 3D models

## DLES

I decided to open source the entire collection of DLES I collect at [dles.gg](https://dles.gg). I will be updating this list at the end of each week. If you're in search for the latest games, please head to [dles.gg/games/newest](https://dles.gg/games/newest) instead, otherwise use this mirror if you need to download the entire games list at once.

- [DLES](assets/daily-games/dles.json) - 874 daily games listed on [dles.gg](https://dles.gg) with names, URLs and descriptions, sorted by a date added to the collection

## Contribute

This is an open source project and contributions are welcome. If you know of a word list, dictionary, or useful asset that should be here, you can help in two ways:

- [Open an issue](https://github.com/trizoza/assets.dles.gg/issues/new) - Suggest a new resource, report a bug or a broken link. No coding required — just describe what you'd like to see added.
- [Submit a pull request](https://github.com/trizoza/assets.dles.gg/pulls) - Fork the repo, add your resource to the `assets/` directory, update this `README.md` with the new resource, and open a PR. We'll review and merge it.
