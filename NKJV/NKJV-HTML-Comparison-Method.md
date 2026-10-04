# How the NKJV HTML was compared

**Compared file:** `New King James Version (NKJV).html`  
**Comparison date:** October 4, 2026

## What it was compared with

I compared the HTML's Bible text with the NKJV text served by **Bolls.life**. The full comparison used Bolls.life's computer-readable chapter text, not a Thomas Nelson PDF or a dated publisher master file. The link pattern is `https://bolls.life/get-chapter/NKJV/{book-number}/{chapter}/`; for example, [Genesis 1](https://bolls.life/get-chapter/NKJV/1/1/). There is also a [formatted Bolls.life Genesis 1 page](https://bolls.life/NKJV/1/1/).

Bolls.life's translation list labels its entry **“New King James Version, 1982.”** The entry has an “updated” timestamp corresponding to October 25, 2021. Bolls.life's documentation describes that field as the update date for its translation record, not as a publisher's edition or revision date ([Bolls.life API documentation](https://github.com/Bolls-Bible/bain/blob/master/docs/API.md)). Other unrelated translation entries share the same timestamp. So the metadata does **not** identify which specific Thomas Nelson print edition or revision Bolls.life used. See the [Bolls.life translation list](https://bolls.life/static/bolls/app/views/languages.json).

## How I compared the text

1. I extracted the text from the HTML by its chapter headings and verse numbers.
2. I compared it with the corresponding chapter and verse from Bolls.life across **all 1,189 chapters and 31,102 verses**.
3. For the word comparison, I ignored punctuation, capitalization, and italic markup. So this checks the sequence of words, not exact punctuation, styling, page layout, or typesetting.
4. Bolls.life's data had three obvious split-word errors. Before the final check, I treated these as single words: “young est” as “youngest” (Genesis 42:20), “th e people” as “the people” (Exodus 19:17), and `<i>wa</i>s` as “was” (Revelation 21:19).

## Results

The first comparison found **325 verse-text differences**. The HTML was then rebuilt with 291 verse readings aligned to Bolls.life, and one stray next-book word, “Isaiah,” was removed from the end of Song of Solomon 8:14 while retaining its printed speaker label.

In the final check, **31,068 of 31,102 verses (99.89%)** had the same word sequence as the cleaned Bolls.life text. All chapters and verses were present; no chapter had a different verse count. The 34 remaining differences were:

- **33 Song of Solomon speaker labels**—such as “THE SHULAMITE”—that appear in the supplied PDF but not in Bolls.life's verse text. They were retained.
- The **copyright paragraph** that follows Revelation 22:21 on the supplied PDF's copyright page. It was retained.

## What this does—and does not—establish

This verifies how the HTML's verse wording compares with **Bolls.life's NKJV text**, after the three noted data repairs. It does **not** establish that Bolls.life has the latest Thomas Nelson text, or identify its exact print edition. I also did not compare the HTML's appearance or page design with a modern Thomas Nelson typeset Bible.

The supplied PDF's copyright page gives a database revision date of **March 28, 2002**. The HTML keeps that PDF's page layout and copyright page; it is not a newly typeset Thomas Nelson edition. The updated verse readings should therefore be described as aligned to Bolls.life, not certified as current Thomas Nelson wording.

## Supporting files

The saved reference text, extracted verses, correction map, and comparison results are in `/home/user/verify/`. The separate `NKJV-comparison-report.md` summarizes the updated book's results.
