# Kaishi 1.5k

Welcome to the public repository for **Kaishi 1.5k**, a modern Anki deck made to introduce beginners to basic Japanese vocabulary. Kaishi 1.5k is highly modular and this page is dedicated to explaining various options you can use to change the deck to your liking. Here is what the front of the deck looks like:

<img src="https://github.com/donkuri/Kaishi/blob/main/pics/front-card.png" alt="Front of a Card in Kaishi 1.5k" style="width: 100%; height: auto">

As you can see, both the word and the sentences are there but the word is highlighted in the sentence, making it easy to immediately isolate the important information. Once the word is known well, reviewing is faster because the word appears first. Here is the backside of the default deck:

<img src="https://github.com/donkuri/Kaishi/blob/main/pics/back-card.png" alt="Back of a Card in Kaishi 1.5k" style="width: 100%; height: auto">

As you can see, furigana gives the reading of the word, with the meaning right below. Audio for the word and for the sentence are then available for you. If you would like, you can also add pitch accent, see below. If there are notes related to that specifc card, they are displayed down below.

## What options are available for the deck?

There are multiple options you can use to change your cards. To modify them, select the Kaishi deck, click `Browse`, select any card from the deck, and click `Cards...` on the top right.

### Pitch Accent

The most important option is whether you would like to include pitch accent on your cards. Currently, whether one should learn pitch accent or not tends to spawn pretty heated arguments in the community. We decided to take a middle ground approach: the pitch accent data is there for you, you choose whether you want to use it. If you decide not to use it, you can always enable it later. The way you enable pitch accent is easy. Here is the card options under `Back Template` for the deck (click on the small dot above the `Search` bar.)

```CSS
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
```

To enable pitch accent, you simply need to take out all the `<!--` and `-->` parts which represent comments, like so: 

```CSS
{{furigana:Word Furigana}}

{{#Pitch Accent}}
	<br><div style='font-size: 24px'>{{Pitch Accent}}</div>
{{/Pitch Accent}} 

<div style='font-size: 25px; padding-bottom:20px'>{{Word Meaning}}</div>
<div style='font-size: 25px;'>{{furigana:Sentence Furigana}}</div>
<div style='font-size: 25px; padding-bottom:10px'>{{Sentence Meaning}}</div>

{{Word Audio}}
{{Sentence Audio}}

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
```

### Minor options

There are a couple of minor options you can modify.

#### Furigana
If you would like to take out furigana, simply take out the `furigana:` parts of the back template.

#### Other card options

You could entirely change the type of cards you want to see. Here is the `Front Template` of Kaishi 1.5k:

```CSS
{{Word}}
<div style='font-size: 20px;'>{{Sentence}}</div>
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

/* This part defines the bold coolor. */
b{color: #5586cd}
```

You can find the various styling options [here](https://docs.ankiweb.net/templates/styling.html). As you can see, Kaishi 1.5k uses very little options in the style tab directly. You can change the `font-family` option to get different fonts, `font-size` to change the font size and `text-align` to change the alignment of the text, for instance if you'd like the text to be left aligned. By default, Kaishi 1.5k colors **bold** words. The option to change this is `b{color: }` as you can see above. Simply put a hexcode or a color name like `red` to get that color instead. If you would like no color, simply take out the whole `b{color: }` part.

## The genesis of the deck

This deck has its origin in a discussion between Tyogin and myself in the [TMW discord server](https://learnjapanese.moe/join/). We were both lamenting the fact that the popular beginner decks at the time had annoying flaws. Beginners kept getting confused when using Core 2k and Tango due to various issues. Tango had some obscure words in it such as ナンプラー which is a Thai fish sauce and many people weren't really interested in all the basic phrases and country names taking up such a large amount of the deck. The deck's fields were formatted terribly which made it impossible to use the deck in a different way than was originally intended, which was sentence cards. Core 2k on the other hand was modular, but had multiple mistranslations, missing or unrelated pictures and some of the sentences weren't very useful, sometimes not even reflecting the meaning of the word used.

Both of these issues were annoying enough that we would get beginners asking questions about it every two weeks. Tyogin proposed we fix the issue ourselves and a small team was assembled to fix these issues. We mostly took data from Core2k, Core10k, Tango N4 and Tango N5. We then combined the data, sorted the words by frequency using various Yomichan/Yomitan frequency dictionaries and selected around 1500 words. We then fixed the translations for each word, chose the best sentence for each word and fixed the sentence if it needed fixing. We had to fix roughly 120 sentences out of the 1500 we chose. After this, we generated audio for words that were missing proper audio, and a team of two people (Karifurai and cindsa) verified the pitch accent data we got from [AJT Japanese](https://ankiweb.net/shared/info/1344485230) as well as adding pitch accent notes for words that needed it. We then took out silence on the cards and normalized the audio level between the various files. On top of that, we also generated furigana from AJT Japanese for the words and the sentences. After this, we designed a basic hint targeted sentences card CSS to be used on the default version of the deck. Finally, multiple people proofread the deck to make sure we had as few errors as possible.

Kaishi, written 開始 means "start, beginning". We thought this fit properly so we decided on this name. Hopefully, this deck will be a wonderful start to your Japanese learning journey.

## Credits

This deck was made with the help of these people:

[栗](https://github.com/donkuri/) - main architect, all technical aspects, translations, proofreading

Tyogin - main architect, reordered the first 200 cards, changed the sentences, proofreading

shoui - proofreading the entire deck, fixed translations

Julian - helped add notes and checked some sentence translations

karifurai - verified the pitch accent for the first 750 cards and added pitch notes

cindsa - verified the pitch accent for the last 750 cards and added pitch notes

These tools were used in the creation of the deck:

[AJT Japanese](https://github.com/Ajatt-Tools/Japanese) - pitch accent, furigana and some of the audio were generated using this add-on

[FFmpeg](https://ffmpeg.org/) - used to take out some silent parts in various audio files

[Tenacity](https://tenacityaudio.org/) - used to edit clipping sounds in various audio files

We also got various ideas from multiple members of the TMW discord server, including the name of the deck itself.




