# Kaishi 1.5k

Welcome to the public repository for **Kaishi 1.5**, a modern Anki deck made to introduce beginners to basic Japanese vocabulary. Kaishi 1.5k is highly modular and this page is dedicated to explaining various options you can use to change the deck to your liking. Here is what the deck looks like:

<div align="center">
  <img src="https://github.com/donkuri/Kaishi/blob/main/pics/front-card.png" alt="Front of a Card in Kaishi 1.5k" style="width: 70%; height: auto">
</div>
<div align="center">Front of a card.</div>

<div align="center">
  <img src="https://github.com/donkuri/Kaishi/blob/main/pics/back-card.png" alt="Back of a Card in Kaishi 1.5k" style="width: 70%; height: auto">
</div>
<div align="center">Back of a card.<br></div>

## The genesis of the deck

This deck has its origin in a discussion between Tyogin and myself in the [TMW discord server](https://learnjapanese.moe/join/). We were both lamenting the fact that the popular beginner decks at the time had annoying flaws. Beginners kept getting confused when using Core 2k and Tango due to various issues. Tango had some obscure words in it such as ナンプラー which is a Thai fish sauce and many people weren't really interested in all the basic phrases and country names taking up such a large amount of the deck. The deck's fields were formatted terribly which made it impossible to use the deck in a different way than was originally intended, which was sentence cards. Core 2k on the other hand was modular, but had multiple mistranslations, missing or unrelated pictures and some of the sentences weren't very useful, sometimes not even reflecting the meaning of the word used.

Both of these issues were annoying enough that we would get beginners asking questions about it every two weeks. Tyogin proposed we fix the issue ourselves and a small team was assembled to fix these issues. We mostly took data from Core2k, Core10k, Tango N4 and Tango N5. We then combined the data, sorted the words by frequency using various Yomichan/Yomitan frequency dictionaries and selected around 1500 words. We then fixed the translations for each word, chose the best sentence for each word and fixed the sentence if it needed fixing. We had to fix roughly 120 sentences out of the 1500 we chose. After this, we generated audio for words that were missing proper audio, and a team of two people (Karifurai and cindsa) verified the pitch accent data we got from [AJT Japanese](https://ankiweb.net/shared/info/1344485230) as well as adding pitch accent notes for words that needed it. We also generated furigana from AJT Japanese for the words and the sentences. After this, we designed a basic hint targeted sentences card CSS to be used on the default version of the deck.

Kaishi, written 開始 means "start, beginning". As we were deciding on a name, someone mentioned the word and it turned out it was exactly the 1000th in the deck. We thought this fit properly Hopefully, this deck will be a wonderful start to your Japanese learning journey.

## What options are available for the deck?

There are multiple options you can use to change your cards.

### Pitch Accent

The most important option is whether you would like to include pitch accent on your cards. Currently, whether one should learn pitch accent or not tends to spawn pretty heated arguments in the community. We decided to take a middle ground approach: the pitch accent data is there for you, you choose whether you want to use it. If you decide not to use it, you can always enable it later. The way you enable pitch accent is extremely easy. Here is a picture of the config file of the default Anki deck:

![Back Template of Kaishi 1.5k](https://github.com/donkuri/Kaishi/blob/main/pics/back-template.png)

To enable pitch accent, you simply need to take out all the `<!--` and `-->` parts which represent comments, like so: 

![Back Template of Kaishi 1.5k with Pitch Acccent enabled](https://github.com/donkuri/Kaishi/blob/main/pics/back-template-pitch.png)

### Minor options

There are a couple of minor options you can modify.

#### Bold color
By default, Kaishi 1.5k colors **bold** words. The option to change this is `b{color: }` you can see above. Simply put a hexcode or a color name like `red` to get that color. If you would like no color, simply take out the whole `b{color: }` part.

#### Furigana
If you would like to take out furigana, simply take out the `furigana:` parts of the back template.

#### Other card options

You could entirely change the type of cards you want to see. Here is the front template of Kaishi 1.5k:

![Front Template of Kaishi 1.5k](https://github.com/donkuri/Kaishi/blob/main/pics/front-template.png)

As you can see, we only have the word and the sentence. If you would like *sentence* cards, simply take out the `{{Word}}` part, or put `Sentence` inside instead and take out the rest. If you would like *word* cards, simply take out the `<div style='font-size: 20px;'>{{Sentence}}</div>` part. If instead you would like *audio* cards, take out everything and add `{{Word Audio}}`, `{{Sentence Audio}}` or both if you would like both.

#### Changing the fonts, font size or other styling options

Here is the styling template of Kaishi 1.5k:

![Styling Template of Kaishi 1.5k](https://github.com/donkuri/Kaishi/blob/main/pics/styling-template.png)

You can find the various styling options [here](https://docs.ankiweb.net/templates/styling.html). As you can see, Kaishi 1.5k uses very little options in the style tab directly. You can change the `font-family` option to get different fonts, `font-size` to change the font size and `text-align` to change the alignment of the text, for instance if you'd like the text to be left aligned. As discussed above, you can also change the bold color by changing `#5586cd` to whichever hexcode you would prefer or to a color.












