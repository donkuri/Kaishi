# Kaishi 1.5k

Welcome to the public repository for **Kaishi 1.5k**, a modern Anki deck made to introduce beginners to basic Japanese vocabulary. Kaishi 1.5k is highly modular and this page is dedicated to explaining various options you can use to change the deck to your liking. Here is what the front of the deck looks like:

<img src="https://github.com/donkuri/Kaishi/blob/main/pics/kaishi-front.png" alt="Front of a Card in Kaishi 1.5k" style="width: 100%; height: auto">

As you can see, both the word and the sentences are there but the word is highlighted in the sentence, making it easy to immediately isolate the important information. Once the word is known well, reviewing is faster because the word appears first. Here is the backside of the default deck:

<img src="https://github.com/donkuri/Kaishi/blob/main/pics/kaishi-back.png" alt="Back of a Card in Kaishi 1.5k" style="width: 100%; height: auto">

Contrary to most other Core-type decks, here furigana gives the reading of the word, with the meaning right below. Audio for the word and for the sentence are then available for you. If you would like, you can also add pitch accent, see below. If there are notes related to that specifc card, they are displayed down below.

[If you are new to Japanese or immersion, please read the guide first.](https://donkuri.github.io/learn-japanese/guide/)

### Table of contents

- [Where do I get the deck?](#where-do-i-get-the-deck)
- [How do I use this deck?](#how-do-i-use-this-deck)
- [Other related decks](#other-related-decks)
- [What options are available for the deck?](#what-options-are-available-for-the-deck)
- [I don't like the images!](#i-dont-like-the-images)
- [How to import Kaishi on top of another deck](#how-to-import-kaishi-on-top-of-another-deck)
- [The genesis of the deck](#the-genesis-of-the-deck)
- [Translation of the deck](#translation-of-the-deck)
- [What do I do after this deck?](#what-do-i-do-after-this-deck)
- [Credits](#credits)

## Where do I get the deck?

You can either get the deck on the [releases](https://github.com/donkuri/Kaishi/releases/) page of this GitHub or on [AnkiWeb](https://ankiweb.net/shared/info/1196762551), provided the deck is not undergoing review. **The deck is supported on Anki 2.1.50+.**

## How do I use this deck?

For an explanation on how Kaishi fits in with learning Japanese more generally, see the [guide](https://donkuri.github.io/learn-japanese/guide/).

## Other related decks

ねむい made a radicals deck based on Kaishi 1.5k, linking every kanji radical found in it with the first word in Kaishi that features this radical. It also covers a few more radicals that aren't in Kaishi proper. You can **use this deck in parallel with Kaishi if you struggle with kanji**, because it introduces kanji radicals as you go, helping you break them down more efficiently. You can find the deck [here on AnkiWeb](https://ankiweb.net/shared/info/1722008986). Thank you ねむい!

## What options are available for the deck?

There are multiple options you can use to change your cards. To modify them, select the Kaishi deck, click `Browse`, select any card from the deck, and click `Cards...` on the top right.

### Pitch Accent

The most important option is whether you would like to include pitch accent on your cards. Currently, whether one should learn pitch accent or not tends to spawn pretty heated arguments in the community. We decided to take a middle ground approach: the pitch accent data is there for you, you choose whether you want to use it. If you decide not to use it, you can always enable it later. The way you enable pitch accent is easy. Here is the card options under `Back Template` for the deck (click on the small dot above the `Search` bar.)

```CSS
<div lang="ja">
{{furigana:Word Furigana}}

<!-- This part enables pitch accent.

{{#Pitch Accent}}
	<br><div style='font-size: 24px'>{{Pitch Accent}}</div>
{{/Pitch Accent}} 

-->

<div style='font-size: 25px; padding-bottom:20px'>{{Word Meaning}}</div>
<div style='font-size: 25px;'>{{furigana:Sentence Furigana}}</div>
<div style='font-size: 25px; padding-bottom:10px'>{{Sentence Meaning}}</div>

{{Word Audio}}
{{Sentence Audio}}
<br>
{{Picture}}

{{#Notes}}
	<br>
	<div style="font-size: 20px; padding-top:12px">Note: {{Notes}}</div>
{{/Notes}}

<!-- This part enables pitch accent notes.

{{#Pitch Accent Notes}}
<div style="font-size: 20px; width: fit-content; max-width:40vw; margin: auto">
	<details><summary>Pitch Accent Notes</summary>
		<br>{{Pitch Accent Notes}}
	</details>
</div>
{{/Pitch Accent Notes}}

-->

</div>
```

To enable pitch accent, you simply need to take out all the `<!--` and `-->` parts which represent comments, like so: 

```CSS
<div lang="ja">
{{furigana:Word Furigana}}

{{#Pitch Accent}}
	<br><div style='font-size: 24px'>{{Pitch Accent}}</div>
{{/Pitch Accent}} 

<div style='font-size: 25px; padding-bottom:20px'>{{Word Meaning}}</div>
<div style='font-size: 25px;'>{{furigana:Sentence Furigana}}</div>
<div style='font-size: 25px; padding-bottom:10px'>{{Sentence Meaning}}</div>

{{Word Audio}}
{{Sentence Audio}}
<br>
{{Picture}}

{{#Notes}}
	<br>
	<div style="font-size: 20px; padding-top:12px">Note: {{Notes}}</div>
{{/Notes}}

{{#Pitch Accent Notes}}
<div style="font-size: 20px; width: fit-content; max-width:40vw; margin: auto">
	<details><summary>Pitch Accent Notes</summary>
		<br>{{Pitch Accent Notes}}
	</details>
</div>
{{/Pitch Accent Notes}}

</div>
```

### Minor options

There are a couple of minor options you can modify.

#### Furigana
If you would like to take out furigana, simply take out the `furigana:` parts of the back template.

#### Other card options

You could entirely change the type of cards you want to see. Here is the `Front Template` of Kaishi 1.5k:

```CSS
<div lang="ja">
{{Word}}
<div style='font-size: 20px;'>{{Sentence}}</div>
</div>
```

As you can see, we only have the word and the sentence. If you would like *sentence* cards, simply take out the `{{Word}}` part, or put `Sentence` inside instead and take out the rest. If you would like *word* cards, simply take out the `<div style='font-size: 20px;'>{{Sentence}}</div>` part. If instead you would like *audio* cards, take out everything and add `{{Word Audio}}`, `{{Sentence Audio}}` or both if you would like both.

#### Changing the fonts, font size or other styling options

Here is the `Styling` template of Kaishi 1.5k:

```CSS
.card {
 font-family: "ヒラギノ角ゴ Pro W3", "Hiragino Kaku Gothic Pro", "Noto Sans JP", Osaka, "メイリオ", Meiryo, "ＭＳ Ｐゴシック", "MS PGothic", "MS UI Gothic", sans-serif;
 font-size: 44px;
 text-align: center;
}

img {
max-width: 300px;
max-height: 250px;
}

.mobile img {
max-width: 50vw;
}

/* This part defines the bold color. */
b{color: #5586cd}
```

You can find the various styling options [here](https://docs.ankiweb.net/templates/styling.html). As you can see, Kaishi 1.5k uses very little options in the style tab directly. You can change the `font-family` option to get different fonts, `font-size` to change the font size and `text-align` to change the alignment of the text, for instance if you'd like the text to be left aligned. By default, Kaishi 1.5k colors **bold** words. The option to change this is `b{color: }` as you can see above. Simply put a hexcode or a color name like `red` to get that color instead. If you would like no color, simply take out the whole `b{color: }` part.

## How to import Kaishi on top of another deck

If you already started Core2k or Tango N4-N5 (or some other similar deck) and you would like to switch to Kaishi 1.5k, you can follow these steps written by [Kuuube](https://github.com/Kuuuube).

1. Import Kaishi normally with the .apkg file.
2. Go to `File > Export...` and export the Kaishi deck using `Notes in Plain Text (.txt)`. Leave all other settings default.
3. Delete the Kaishi deck.
4. Select the deck you want to import Kaishi on top of, select `Browse`, click any card, press `ctrl + a`, and select `Notes > Change Note Type...` on the top left menu. Make sure all notes you selected are of the same note type or else `Notes > Change Note Type...` may not show up.
5. Change to the `Kaishi 1.5k` note type. Make sure the `Word` field in the `New` column shows the field your deck uses for the word next to it.
    If you don't intend to delete any cards from your current deck that are not in Kaishi, make sure your other fields are lined up to the correct places too. Otherwise you can use the defaults and click `Save`.
6. Import the Kaishi .txt file exported in step 2.
7. When importing, make sure the Notetype is set to `Kaishi 1.5k` and the Deck is set to the deck you want to import on top of. 
  If you intend on deleting cards not in Kaishi, add the tag `Kaishi` in the `Tag all notes` option.
8. Click `Import`.
9. To delete cards not in Kaishi, select your deck, click `Browse`, select your deck in left menu, append ` -tag:Kaishi` to the search bar, select any card, press `ctrl + a`, on the top left menu and go to `Notes > Delete`.

**If you're importing on top of Core 2.3k, please see [this](https://github.com/Manhhao/anki.transfer-review-history).**

## I don't like the images!

That's fair. Finding 1500 consistent and free pictures to use for the deck was a tremendous challenge (thank you again for this [liarbeast](https://github.com/liarbeast)!). As a result, a bunch of pictures do not align perfectly with the sentence or the word. That's valid criticism, and if you would like to take the picture out, here's what you should do. Open up Cards...` after clicking on a Kaishi card in the browser. Look for the `Back` template. In it, you will find `{{Picture}}`. Simply take it out. Alternatively, just replace everything with the following:

```html
<div lang="ja">
{{furigana:Word Furigana}}

<!-- This part enables pitch accent.

{{#Pitch Accent}}
	<br><div style='font-size: 24px'>{{Pitch Accent}}</div>
{{/Pitch Accent}} 

-->

<div style='font-size: 25px; padding-bottom:20px'>{{Word Meaning}}</div>
<div style='font-size: 25px;'>{{furigana:Sentence Furigana}}</div>
<div style='font-size: 25px; padding-bottom:10px'>{{Sentence Meaning}}</div>

{{Word Audio}}
{{Sentence Audio}}
<br>

{{#Notes}}
	<br>
	<div style="font-size: 20px; padding-top:12px">Note: {{Notes}}</div>
{{/Notes}}

<!-- This part enables pitch accent notes.

{{#Pitch Accent Notes}}
<div style="font-size: 20px; width: fit-content; max-width:40vw; margin: auto">
	<details><summary>Pitch Accent Notes</summary>
		<br>{{Pitch Accent Notes}}
	</details>
</div>
{{/Pitch Accent Notes}}

-->

</div>
```

## The genesis of the deck

This deck has its origin in a discussion between Tyogin and myself in the [TMW discord server](https://learnjapanese.moe/join/). We were both lamenting the fact that the popular beginner decks at the time had annoying flaws. Beginners kept getting confused when using Core 2k and Tango due to various issues. Tango had some obscure words in it such as ナンプラー which is a Thai fish sauce and many people weren't really interested in all the basic phrases and country names taking up such a large amount of the deck. The deck's fields were formatted terribly which made it impossible to use the deck in a different way than was originally intended, which was sentence cards. Core 2k on the other hand was modular, but had multiple mistranslations, missing or unrelated pictures and some of the sentences weren't very useful, sometimes not even reflecting the meaning of the word used.

Both of these issues were annoying enough that we would get beginners asking questions about it every two weeks. Tyogin proposed we fix the issue ourselves and a small team was assembled to fix these issues. We mostly took data from Core2k, Core10k, Tango N4 and Tango N5. We then combined the data, sorted the words by frequency using various Yomichan/Yomitan frequency dictionaries and selected around 1500 words. We then fixed the translations for each word, chose the best sentence for each word and fixed the sentence if it needed fixing. We had to fix roughly 120 sentences out of the 1500 we chose. After this, we generated audio for words that were missing proper audio, and a team of two people (Karifurai and cindsa) verified the pitch accent data we got from [AJT Japanese](https://ankiweb.net/shared/info/1344485230) as well as adding pitch accent notes for words that needed it. We then took out silence on the cards and normalized the audio level between the various files. On top of that, we also generated furigana from AJT Japanese for the words and the sentences. After this, we designed a basic hint targeted sentences card CSS to be used on the default version of the deck. Finally, multiple people proofread the deck to make sure we had as few errors as possible.

Kaishi, written 開始 means "start, beginning". We thought this fit properly so we decided on this name. Hopefully, this deck will be a wonderful start to your Japanese learning journey.

## What do I do after this deck?

[Start mining](https://donkuri.github.io/learn-japanese/guide/#consuming-native-content) if you haven't already. See [this](https://github.com/donkuri/japanese-resources/?tab=readme-ov-file#mining) for a list of mining notetypes.

## Translation of the deck

If you are interested in translating the deck in your native language, please make an issue on [the GitHub tracker](https://github.com/donkuri/Kaishi/issues). The deck has already been translated in **[Russian](https://github.com/NeonGooRoo/KaishiRu)**, **[Indonesian](https://ankiweb.net/shared/info/1512066033)**, **[Vietnamese](https://github.com/duy103zxc/kaishi-vi/releases)**, **[Ukrainian](https://github.com/maksiksq/KaishiUa)**, **[Brazilian Portuguese](https://github.com/nonsolvent/Kaishi-pt-BR)** and **[Spanish](https://github.com/Dogi5/Kaishi-ESP)**.

## Credits

This deck was made with the help of these people:

[栗](https://github.com/donkuri/) - main architect, all technical aspects, translations, proofreading

Tyogin - main architect, reordered the first 200 cards, changed the sentences, proofreading

shoui - proofreading the entire deck, fixed translations

Julian - helped add notes and checked some sentence translations

karifurai - verified the pitch accent for the first 750 cards and added pitch notes

cindsa - verified the pitch accent for the last 750 cards and added pitch notes

[Kuuube](https://github.com/Kuuuube) - suggested the use of FFmpeg, wrote the transferring cards to Kaishi 1.5k section above

[stephenmk](https://github.com/stephenmk) - ran the Jmdict Furigana tool on Kaishi 1.5k to fix furigana, see v1.3.0

[Kaanium](https://github.com/kaanium) - helped make a script to convert the deck to the writing version

These tools were used in the creation of the deck:

[AJT Japanese](https://github.com/Ajatt-Tools/Japanese) - pitch accent, furigana and some of the audio were generated using this add-on

[FFmpeg](https://ffmpeg.org/) - used to take out some silent parts in various audio files

[Tenacity](https://tenacityaudio.org/) - used to edit clipping sounds in various audio files

We also got various ideas from multiple members of the TMW discord server, including the name of the deck itself. The sentences themselves come from various Core decks found on Ankiweb.




