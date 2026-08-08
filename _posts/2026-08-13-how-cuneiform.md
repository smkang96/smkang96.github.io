---
layout: post
title: "How Cuneiform?"
date: 2026-08-08 18:00:00+0800
description: "An account of how the decipherment of cuneiform started"
categories: hobby fun
giscus_comments: true
related_posts: true
---

How did people learn to read this stuff?

![a close-up image of a cuneiform inscription](/assets/images/2026-07-24-21-45-34.png){: width="600" .center}

I don't know why, but I've been thinking about this for a few months now, and decided to get to the bottom of it. 

My usual go-to is Wikipedia for these matters, and there is indeed a relevant article titled [Decipherment of Cuneiform](https://en.wikipedia.org/wiki/Decipherment_of_cuneiform). I was not satisfied by the amount of detail it provided, however. For example, it says: "Della Valle understood that the writing had to be read from left to right". What? How?? I also looked up one or two of the linked books in Wikipedia and searched for YouTube videos, which were similarly unsatisfactory.

So how, specifically, did people learn to read cuneiform?

One thing I learned in the process is that there are many different types of cuneiform. This post only deals with Old Persian cuneiform, the first to be deciphered.

Necessary caveats: I am (obviously) not an expert. While I wrote the post in its entirety, I also relied on Claude Opus for discussion and translation of original sources in Latin, German, and French.

## Awareness

Travelers visiting ancient Persian lands regularly encountered sculptures accompanied by mysterious 'decorations':

![dense cuneiform with sculpted figurines to the left, right, and bottom.](/assets/images/2026-07-24-23-30-31.png){: width="600" .center}

Many thought this was text, and tried to decipher it, without making much (known) progress. Nonetheless, there were some early guesses which turned out to be correct. For example, the Italian traveler Pietro Della Valle, who had been in the region between 1616-1621, saw the glyph

> <span style="font-size: 50px">𐎠</span>

and observed (translation by Claude):

> What gives me an indication that it may be written from left to right in our manner is the character, which is composed of four similar pyramidal figures — three upright with the point downward, and one lying on its side above them. For of the pyramidal figures, the head of this writing, as one sees in all the characters, is the broad part, which always stands uppermost when they are upright. Now in that pyramidal figure lying above the three that stand on end, since its head — that is, the broad part — is on the left, and its tail — that is, the point — on the right, it shows that the beginning of the writing is from the left side toward the right. Still, I do not affirm it for certain.

Simply put, because the lower three 'triangles' of the example glyph get narrower as they go down, and the upper 'triangle' gets narrower as it goes from left to right, the text might be read left to right. But he's not sure. 

(This is all Della Valle had to say, if you were wondering if I left something out. Not strong reasoning IMO, but it is what it is.)

Not everyone agreed that the 'decorations' were actually text, however. Thomas Hyde, who coined the term _cuneiform_[^1], apparently believed that the signs were meant to serve as ornaments. (Charitably, perhaps he saw inscriptions with just a few lines? I cannot imagine seeing literal walls of text like the one photographed above and concluding "Ah, decoration.")

Such was the state by the 1760s - controversy on whether cuneiform even represented writing proper. This changed with Carsten Niebuhr.

## Details Emerging

Carsten Niebuhr, a German mathematician and cartographer, excelled in his studies, and was thus recommended to be part of the Danish Arabia expedition at the age of 27. You can see his journey route below:

![map of the danish expedition to yemen](/assets/images/2026-07-25-00-40-35.png){: width="600" .center}

_Image from [deSyracuse](https://twitter.com/deSyracuse/status/1171377770598977536)._

This was a dangerous journey: Niebuhr was the only one of the six members to survive. That he survived is fortunate for us, because Niebuhr visited Persepolis, an ancient Persian city with many cuneiform inscriptions, and made a number of critical contributions, getting the decipherment ball rolling.

First, Niebuhr left highly accurate copies of the inscriptions at Persepolis, and published them in 1778, in a series of tables labeled from A to L. This allowed anyone with access to his book to contribute, not just people (like him) who were fortunate enough to see the inscriptions in person.

Second, Niebuhr noticed that there was not just one but three types of script. See an image of how he classified them below (on the right, tables B, C, and D):

![Niebuhr's table of script types](/assets/images/2026-07-25-14-25-10.png){: width="600" .center}

Not having seen the inscriptions myself, it is difficult to know how easy it is to tell in person, but once they are organized like this it is relatively easy to see the differences. In type B, for example, the wedges only appear vertically or horizontally, _except_ when the wedge is used alone. In type C, various forms of diagonally oriented wedges appear. Type D is somewhat similar to type B, but there are generally more wedges. Probably there was some physical separation between the blocks, making it easier for Niebuhr to tell that they were meant to be distinct.

Finally, Niebuhr noticed that one of the three scripts he identified was the simplest, making it the prime target for decipherment. Regarding type B above, Niebuhr says (translated):

> The number of letters is therefore by no means as large as one might perhaps have supposed from the copies of my predecessors. I have collected the various letters of one alphabet, the one that occurs most often, and have found no more than 42 of them.

Niebuhr has, by this point, provided accurate records and established key basic facts about the script, including different script types and which would be easiest to decipher (the type in Table B, which we will alternatively call "Old Persian Cuneiform"). But he has not yet deciphered the meaning of the text.

## Breakthrough

As Niebuhr's records spread, Oluf Gerhard Tychsen guessed that the diagonal wedge (𐏐) was likely a word separator. It is unique, as discussed above, in that it is the only diagonal wedge to appear in the glyphs. Furthermore, separating by the wedge yields roughly word-sized chunks. 

This observation in turn made it easy to realize that there is a common recurring sequence in the text. See if you can find it yourself (here, I quote part of the [DNa inscription](https://en.wikipedia.org/wiki/DNa_inscription)):

> 𐏐 𐎠𐎭𐎶 𐏐 𐎭𐎠𐎼𐎹𐎺𐎢𐏁 𐏐 𐎧𐏁𐎠𐎹𐎰𐎡𐎹 𐏐 𐎺/𐏀𐎼𐎣
> 
> 𐏐 𐎧𐏁𐎠𐎹𐎰𐎡𐎹 𐏐 𐎧𐏁𐎠𐎹𐎰𐎡𐎹𐎠𐎴𐎠𐎶
> 
> 𐏐 𐎧𐏁𐎠𐎹𐎰𐎡𐎹 𐏐 𐎭𐏃𐎹𐎢𐎴𐎠𐎶 𐏐 𐎻𐎡𐎿𐎱𐏀𐎴𐎠/𐎴𐎠𐎶
> 
> 𐏐 𐎧𐏁𐎠𐎹𐎰𐎡𐎹 𐏐 𐎠𐏃𐎹𐎠𐎹𐎠 𐏐 𐎲𐎢𐎷𐎡/𐎹𐎠

This is parsed favorably, so you should be able to make it out: "𐎧𐏁𐎠𐎹𐎰𐎡𐎹" is a frequently recurring pattern. What might it be, though? A name? A title? An article like "the"? Tychsen made some guesses as to how to read the script, but it was not the most accurate.

It is at this point where [Georg Grotefend](https://en.wikipedia.org/wiki/Georg_Friedrich_Grotefend), a 27-year-old scholar, made a series of bold informed guesses that led to significant progress.

In his 1802 submission to the Göttingen Society, Grotefend suggested the following:

### The script is alphabetic

If we accept 𐏐 is a separator, the glyphs in Niebuhr's Table B cannot represent individual words. Not only are there too few observable glyphs for that, it is implausible that there would be repetitions of exact phrases over and over. Thus, the script is likely alphabetic.

### The language it describes is likely Old Persian

If the script is alphabetic, certain glyphs are likely vowels. We can identify which of them are vowels, by looking at glyph frequency, since vowels can be expected to occur more often. Indeed, three glyphs are notably more frequent: 𐎠, 𐎶[^2], and 𐎡.

Grotefend argued the usage of these glyphs closely fits vowel usage in the [Avestan](https://en.wikipedia.org/wiki/Avestan) language (the language used by the Persian peoples in 1500-400 BCE). Therefore, we can deduce that the language the glyphs are recording is similar in nature. This makes sense because the glyphs were found in Persian lands, and Avestan is a Persian language.[^3]

### The script is read left-to-right

Grotefend provides a stronger reason why the script is read left-to-right: namely, that patterns are better preserved when read in such a manner.

Here, Grotefend did not give a specific example, but it's fairly easy to find one. Consider the often-recurring pattern "𐎧𐏁𐎠𐎹𐎰𐎡𐎹", and how it is recorded in Niebuhr's original table. We can see an instance of the _left_ part of it appearing on the right side of second line and the _right_ part at the left side of the third line. This provides reasonably strong indication that the glyphs are read left-to-right, top-to-bottom, just like the Latin alphabet usually is.

![linebreak of common cuneiform word](/assets/images/2026-07-25-16-22-04.png){: width="600" .center}

### The pattern "𐎧𐏁𐎠𐎹𐎰𐎡𐎹" likely means "king", with the king's name appearing to its left

With the reading order in mind, Grotefend observes that Niebuhr's Table B and G start as:

> Table B: &nbsp;&nbsp;𐎭𐎠𐎼𐎹𐎺𐎢𐏁𐏐𐎧𐏁𐎠𐎹𐎰𐎡𐎹
> 
> Table G: 𐎧𐏁𐎹𐎠𐎼𐏁𐎠𐏐𐎧𐏁𐎠𐎹𐎰𐎡𐎹

From this, he conjectures that "𐎧𐏁𐎠𐎹𐎰𐎡𐎹" is a title, most likely "king", and that the sequence preceding "𐎧𐏁𐎠𐎹𐎰𐎡𐎹" is the king's name. This makes sense as there are also inscriptions where the "king" sequence appears in succession: "<span style="color:goldenrod">𐎧𐏁𐎠𐎹𐎰𐎡𐎹</span>𐏐<span style="color:goldenrod">𐎧𐏁𐎠𐎹𐎰𐎡𐎹</span>𐎠𐎴𐎠𐎶", which would mean "king of kings".

### Identification of the kings in the inscriptions: Darius and Xerxes

Tables B and G are in fact almost identical in structure:

> Table B: 
> 
> <span style="color:green">𐎭𐎠𐎼𐎹𐎺𐎢𐏁</span>𐏐<span style="color:goldenrod">𐎧𐏁𐎠𐎹𐎰𐎡𐎹</span>𐏐<span style="color:purple">𐎺𐏀𐎼𐎣</span>𐏐  // [name1] king [word1]
> 
> <span style="color:goldenrod">𐎧𐏁𐎠𐎹𐎰𐎡𐎹</span>𐏐<span style="color:goldenrod">𐎧𐏁𐎠𐎹𐎰𐎡𐎹</span>𐎠𐎴𐎠𐎶𐏐 // king of kings
> 
> <span style="color:goldenrod">𐎧𐏁𐎠𐎹𐎰𐎡𐎹</span>𐏐𐎭𐏃𐎹𐎢𐎴𐎠𐎶𐏐 // king [word2] 
>
> 𐎻𐎡𐏁𐎫𐎠𐎿𐎱<span style="color:red">𐏃</span>𐎹𐎠𐏐 // [word3 with 𐏃 modifier]
>
> <span style="color:skyblue">𐎱𐎢𐏂𐏐𐏃𐎧𐎠𐎶𐎴𐎡𐏁𐎡𐎹𐏐</span> // [word4] [word5]
>
> ...

> Table G:
> 
> 𐎧𐏁𐎹𐎠𐎼𐏁𐎠𐏐<span style="color:goldenrod">𐎧𐏁𐎠𐎹𐎰𐎡𐎹</span>𐏐<span style="color:purple">𐎺𐏀𐎼𐎣</span>𐏐 // [name2] king [word1]
>
> <span style="color:goldenrod">𐎧𐏁𐎠𐎹𐎰𐎡𐎹</span>𐏐<span style="color:goldenrod">𐎧𐏁𐎠𐎹𐎰𐎡𐎹</span>𐎠𐎴𐎠𐎶𐏐 // king of kings
>
> <span style="color:green">𐎭𐎠𐎼𐎹𐎺<span style="color:red">𐏃</span>𐎢𐏁</span>𐏐<span style="color:goldenrod">𐎧𐏁𐎠𐎹𐎰𐎡𐎹<span style="color:red">𐏃</span></span>𐎹𐎠𐏐 // [name1 with 𐏃 modifier] king
>
> <span style="color:skyblue">𐎱𐎢𐏂𐏐𐏃𐎧𐎠𐎶𐎴𐎡𐏁𐎡𐎹𐏐</span> // [word4] [word5]

There is a clear pattern between the two; what can we do with this? Here, there is a difference between the interesting story on Wikipedia, and what I could find in Grotefend's original text.

#### Wikipedia's Story

Note that [name1] is mentioned in Table G. The story goes that it was already known that Persian kings described themselves in this formula. For example, here goes the translated description of a Persian king in the 200s ([Shapur I](https://sites.uci.edu/sasanika/sapur-is-inscription-naqs-e-rajab-snrb/)):

> ... lord Shapur,
> king of kings of the Iranians and non Iranians...
> son of ... lord Ardashir, king of kings of the Iranians...

Then the recurrence of [name1] in Table G likely means that [name2] was a _son_ of [name1], with the <span style="color:red">𐏃</span> modifier perhaps doing a grammatical job related to the "son of" meaning. With this in mind, we can make an interesting observation about Table B: there, [word3] does _not_ have the king title following it, unlike Shapur's description and Table G, which explicitly note the father is a king. Thus, we need to find a Persian king whose father was not a king, but whose son was.

Two Achaemenid kings fit that pattern: Cyrus II and Darius I.[^4] A distinguishing factor is that for Cyrus II, the name of his father and son were the same (Cambyses). However, [name2] and [word3] are clearly different. So [name1] must be Darius! From here, we can deduce the sound values of the cuneiform, since we earlier suspected it to be alphabetic, and eventually decipher it all.

#### Grotefend's Description

Unfortunately, the tidy story is not what I could find in Grotefend's 1802 submission.

Instead, Grotefend noted that [name1] appears in both Niebuhr's tables B and G, and thus deduced that the kings first mentioned in B and G were father and son:

> ... from which I gathered that the kings praised in these inscriptions were father and son. Since therefore the name of Darius — which the sacred codex calls Darjavesch — seemed to square with that word which Tychsen read Malkéusch (Dârhéusch), and the name of Xerxes with that which Tychsen read Osch patscha (Khschhêrschê): what the royal title was could not long escape me.

Thus, Darius and Xerxes are Grotefend's guesstimates of the names based on the father-son relationship and the reconstructed sounds of Tychsen, not from a genealogy search.

Be it genealogy or guesstimate, Grotefend has concluded that [name1] is Darius and [name2] is Xerxes. Having established that the glyphs are alphabetic in nature, we can start deducing what _sounds_ the glyphs would represent.

### Phonetic Deduction

Once a name is known, mapping it back to sounds might not seem _too_ hard. But consider: would the ancient Persians have pronounced Darius the same way as we English speakers do? Probably not: "Darius" is in fact a Latin form of the Greek term for the King, so it is twice removed from the name in its native language. Thus, for accurate decipherment, one must try to reconstruct how the ancient Persians might have called their king.

Grotefend reconstructed Darius's name from the Bible, where Darius is called "Darjavesch". Without describing why, he slightly modified this to "Dárheúsch",[^5] which was then used to identify the glyph sounds:

| 𐎭  | 𐎠 |  𐎼 | 𐎹  | 𐎺  | 𐎢| 𐏁 |
|---|---|---|---|---|---|---|
| D  | a  |  r | h | e  | u | sch |

Conveniently, [name2] (Xerxes) shares all glyphs with Darius except its first. Guessting the first letter to be _kh_ based on Xerxes's name, we get

|𐎧|𐏁|𐎹|𐎠|𐎼|𐏁|𐎠|
|---|---|---|---|---|---|---|
| kh | sch | h | a[^6] | r | sch | a |

The "kh" read is also corroborated by our key word "king", "𐎧𐏁𐎠𐎹𐎰𐎡𐎹", which starts with the same glyph as Xerxes; Grotefend says that an earlier scholar reconstructed the Old Persian term for king to be "Khscheio".[^7]

Grotefend, not being an expert in ancient Persian himself, used a dictionary of Old Persian words to reconstruct even more. For example, <span style="color:purple">𐎺𐏀𐎼𐎣</span> would read as "e?r?" based on what we have deduced. Grotefend thinks this word is an adjective (as it appears after "king"), and finds from the dictionary the word "eghré", meaning "strong" or "great". Thus he further connected "𐏀" with "gh" and "𐎣" with "é". Through such a process, he constructed the following table and provided the meaning of the shorter inscriptions from Niebuhr:

![grotefend's table of old persian cuneiform decipherment](/assets/images/2026-07-26-18-24-36.png){: width="600" .center}

Well, then, this looks good, are we done now?

Not quite. When compared with a modern reconstruction, Grotefend's phonetic reconstruction wasn't even half correct. As mentioned, Grotefend relied on a dictionary of Old Persian words. However, later scholars pointed out that the dictionary he relied on had many problems itself, leading to incorrect deductions. That <span style="color:purple">𐎺𐏀𐎼𐎣</span> word earlier? Modern scholars would read it as "vazraka", not "eghré", so it was quite far off. 

Without an accurate phonetic reconstruction, it was thus impossible to read text that did _not_ follow patterns already established. This contributed to skepticism amongst the academic experts in the area; to them, using Grotefend's table to decipher unknown text probably led to sounds that seemed meaningless or even impossible in the ancient Persian language.

Grotefend's semantic reading was validated when _hieroglyphs_ were deciphered. In 1823, an Egyptian vase was found to have both the cuneiform "𐎧𐏁𐎹𐎠𐎼𐏁𐎠𐏐" and hieroglyphs spelling out "Xerxes". This further supported Grotefend's guess that [name2] was in fact Xerxes. Nonetheless, this did not rescue the ultimately incorrect phonetics.

## Expert At The Rescue

Enter Eugène Burnouf. Born to a scholarly family, Burnouf was an expert in ancient Iranian and Indian languages. He had deciphered Avestan (an ancient Persian language) script, and thus had a deep knowledge of the language, precisely what Grotefend lacked.

Here, the popular story seems to be that "Burnouf discovered that the first of the inscriptions published by Niebuhr contained a list of the satrapies of Darius", which is... another interesting but inaccurate story.[^8] 

Having written this, though, I sympathize with simplifying, as it's impossible to fully communicate what Burnouf did. From this point on, decipherment becomes less about exciting ideas and more about the diligent application of language-specific knowledge, making it difficult to distill into a single compelling observation. Nonetheless, here is my hopefully more instructive summary of Burnouf's methodology based on my reading of [Burnouf's book](https://archive.org/details/mmoiresurdeuxin01burngoog/page/n196/mode/2up). 

The key method for him was to note that there were some words that were close but not exact matches to known geographies and gods. I built the following table to simulate the knowledge that he had in his mind and show the technique: try to match the Grotefend reading to the closest known word, knowing that the Grotefend reading is partially accurate.

|Known cuneiform word|Grotefend reading|Known words and geographies (randomized order)|
|---|---|---|
| 𐎠𐎢𐎼𐎶𐏀𐎭𐎠 | auroghda | -anam (common suffix) |
| 𐎲𐎠𐎧𐎫𐎼𐎡𐏁 | bakhmrosch | Achaemenid (demonym) |
| 𐎠𐎴𐎠𐎶 | atschao | Ahura Mazda (supreme god of Zoroastrianism) |
| 𐎠𐎿𐎶𐎠𐎴𐎶 | asoatscho | ashmanem (the sky) |
| 𐏃𐎧𐎠𐎶𐎴𐎡𐏁𐎡𐎹 | akhaotschoschoh | Bactria (region name) |

If you tried matching the words, hopefully it wasn't too hard to match "auroghda" with Ahura Mazda, as both start with the "au" vowels and end with "da". If we accept this match, we can identify that the "m" sound we would expect from Ahura Mazda is completely missing from Grotefend's reading. Thus, we can correct Grotefend's reading of "𐎶" from "o" to "m".

We can be surer of this reading, because it makes other readings closer to our matches. Consider the reading "asoatscho", which was probably one of the harder to match. Its reading would now be "asmatschm", close to "ashmanem". This is again almost accurate, while suggesting that "𐎴" should be read as "n" instead of "tsch".

To complete the matching process: reading "𐎴" as "n" completely reconstructs "-anam", so we can again be more confident. "akhaotschoschoh" becomes "akhamnoschoh", which matches "Achaemenid" sans the suffixes. Probably the easiest match was "bakhmrosch" matching Bactria, again sans suffixes. Again, this is a simplification of what Burnouf did - he had many more Persian words and cuneiform words to match consistently - but it illustrates the rough process through which he corrected Grotefend's reconstruction.

Contrary to the popular narrative, it is only after this series of corrections was made that Burnouf recognized there was a list of satrapies in one of Niebuhr's inscriptions - he did not _start_ with the recognition that the list of satrapies was in the inscriptions.

Burnouf's phonetic reconstruction was _still_ not completely correct, but it was substantially closer than Grotefend's. Over the years, later scholars could further refine the phonetic reconstruction, eventually leading to its modern form:

![Wikipedia's phonetic table of Old Persian cuneiform](/assets/images/2026-08-08-17-51-56.png){: width="600" .center}

## Epilogue: The Behistun Inscription

We have told the story of how the cuneiform type in Niebuhr's Table B, which he identified as the easiest to decipher, was gradually understood. But what about the types in Tables C and D?

Here, the British officer Henry Rawlinson played a role similar to Niebuhr. During his time in Persia, Rawlinson provided an accurate depiction of the [Behistun Inscription](https://en.wikipedia.org/wiki/Behistun_inscription), which has inscriptions in all cuneiform types, but which are much longer. This seems to have been enough source material for the decipherment of the other types. Just look at how much is inscribed: all the "lines" you see on the left, on the right, and on the bottom of the photograph are all in fact cuneiform from what I can see.

![A photograph of the Behistun inscription](/assets/images/2026-08-08-17-59-53.png){: width="600" .center}

But that's a story for another day, and I've satisfied my itch for a while. When (if?) we come back to this topic, we'll describe what ideas were used in deciphering the other, substantially more complex cuneiform types.

----

### Footnotes
[^1]: wedge-form, cunei- is from the Latin [cuneus](https://en.wiktionary.org/wiki/cuneus)
[^2]: To be clear, this is from the original 1802 text of Grotefend, but further research has revealed it is not a vowel.
[^3]: Grotefend and the later Burnouf actually call the language "Zend", but Avestan seems to be the modern term for the language, so I used Avestan for consistency.
[^4]: Looking up the family tree of the Achaemenid dynasty, I was further confused by this explanation, as Cyrus II's father was also a king. Claude suggested that Herodotus, a Greek historian, did not consider Cyrus II's father a king. I looked at the Herodotus passage that Claude cited for that (1.107), but it was not clear to me. In any case Grotefend doesn't appear to have considered Cyrus as a candidate, so it doesn't matter.
[^5]: While reviewing the manuscript, I realized that this change actually introduced more problems in the phonetic reconstruction: using the biblical "Darjavesch" would have potentially allowed the accurate reading of "𐎹" as "ya" and "𐎺" as "v". This was probably difficult to see by Grotefend because he thought cuneiform to be alphabetic, but much later research showed the Old Persian cuneiform to be partially syllabary (representing both consonant and vowel, as in "ya"). If one assumes alphabetic representation, the cuneiform does not have enough glyphs for Darjavesch.
[^6]: Here, 𐎠 poses a bit of a problem: Xerxes is nowadays read with an "e" sound, which is different from an "a" sound, so why would they be represented with the same glyph? Grotefend notes this and justifies that in non-cuneiform representations of the old language, the same character could be read as multiple sounds. (This is an instance where he was wrong - it seems like modern reconstructions of Old Persian do not have the "eh" sound at all, and that a consistent "a" was the right reconstruction.)
[^7]: This also fits well with e.g. kshatriya, which is of the same origin. I was initially confused by the _Decipherment of Cuneiform_ Wikipedia article which claimed the correct modern reading of 𐎧 is "wsa", but this seems wrong and "𐎧" as "kh" seems right.
[^8]: Wikipedia can't exactly be faulted, because it is another error from _The Archaeology of the Cuneiform Inscriptions_, p.14, published in 1908. A small problem not worth noting in the main text: Niebuhr published inscriptions in Tables A-L, and Burnouf noted that _`Table I`_ (i.e. the 9th table, counted in alphabetic order) of the inscriptions contains the list of tributaries, not the "first".