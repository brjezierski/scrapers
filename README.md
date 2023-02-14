# German Datasets / Resources

This repository contains scrapers and lists of links for various online sources of data in Leichte Sprache.

## Preprocessing

To make use of our preprocessing pipeline refer to the following steps.  
1. Create a new folder (with the name of your dataset).
2. Add folders for monolingual and/or aligned data. 
    1. For monolingual data: place another subfolder **'monolingual'** inside the first folder.
    2. For aligned data: place another subfolder **'aligned'** inside the first folder.
3. Add the text files
    1. For monolingual data: compress your raw .txt files into a zip file called **'corpus.zip'** to your and place it in your **'monolingual'** folder. Make sure the filenames in your corpus.zip meet the following criteria:
      - no spaces
      - no german "umlaut"
      - no other special characters as brackets ...  
    2. For aligned data: place your csv file (arbitrary name) in your **'aligned'** folder  
      make sure to have one column **normal_phrase** and one column **simple_phrase** in your csv.
4. If it already exists you can delete the current __clean_data__ folder.
5. Run `python3 preprocess.py` to generate preprocessed data.
6. You can now find your cleaned data in the folder __clean_data__.

If you have added new data, repeat steps 4 to 6 to update the already cleaned data again.

### Troubleshooting

- If characters are corrupted switch between text.decode() and text.decode("latin-1")

## Access to manually aligned test set

dictionary-meta.csv contains a list of urls to dictionary entries we used for compiling a sentence-wise manually aligned dataset. The election program and MDR news corpus can be provided upon request.

## Scraped monolingual data overview

| source               | # articles | # sentences | quality | type   |
|----------------------|------------|-------------|---------|---------|
| hurraki              | 3 911      | 56 785      | good    | lexicon |
| nachrichtenleicht    | 7 709      | 122 842     | good    | news    |
| klexikon             | 2 350      | 80 042      | medium  | lexicon |
| ndr                  | 1 817      | 60 749      | good    | news    |
| einfachstars         | 6 488      | 129 674     | good    | news    |
| hdasprachtechnologie | 44         | 4 210       | good    | misc.   |
| lebenshilfe          | 396        | 7 144       | good    | misc.   |
| kurier               | 4 519      | 67 827      | good    | news    |
| **total**            | **27 234** | **529 654** |         |         |

## Scraped parallel data overview

| source               | # articles | # sentences | quality | type   |
|----------------------|------------|-------------|---------|---------|
| original_kurier      | 3 476      | 77 587      | good    | news    |
| **total**            | **3 476**  | **77 587**  |         |         |

## Sentence aligned data overview

| source               | # sentences | creation method |  leichte sprache | type   |
|----------------------|-------------|-----------------|------------------|---------|
| wiki_translation     | 488 001     | scraper         | no               | lexicon |
| apa_a2               | 9 456       | lha scraper     | yes              | news    |
| apa_b1               | 10 268      | lha scraper     | yes              | news    |
| kurier               | 40 772      | vecalign scraper| yes              | news    |
| **total**            | **548 497** |                 |                  |         |


## Validation dataset
| source               | # sentences | creation method |  leichte sprache | type      |
|----------------------|-------------|-----------------|------------------|------------|
| mdr news             | 50         | manually aligned | yes             | news       |
| mdr dictionary       | 50         | manually aligned | yes             | lexicon    |
| brandeins(*)         | 106         | scraped (color coding) | yes            | various    |
| wiki_auto_test       | 147         | manually reviewed | no             | lexicon    |
| wiki_auto_dev        | 59          | manually reviewed | no             | lexicon    |
| **total**            | **412**     |                   |                |            |


## Test dataset
| source               | # sentences | creation method |  leichte sprache | type      |
|----------------------|-------------|-----------------|------------------|------------|
| wahlprogramm         | 107         | manually aligned | yes             | election program       |
| mdr news             | 50         | manually aligned | yes             | news       |
| mdr dictionary       | 50         | manually aligned | yes             | lexicon    |
| brandeins(*)         | 106         | scraped (color coding) | yes            | various    |
| **total**            | **313**     |                   |                |            |

(*) Created with the help of Daniel Berger (da.berger@tum.de)


### Creation Methods
**manually aligned**: source and target phrases/sentences are aligned by hand by a human person  
**manually reviewed**: alignment is already done (in this case english alignments are translated to german) and a human person corrects grammar and other mistakes  
**scraped (color coding)**: target and source phrases are displayed in different colors and can be automatically aligned  

## Mainly Monolingual Data

- [Geasy corpus](https://seafile.rlp.net/f/a25a64e6dfa54373b5a1/) (second sheet in file) with collection on German Easy Language data sources
- [Hurraki](https://hurraki.de/wiki/Hauptseite) kind of "Leichte Sprache" Wikipedia (approx. 40.000 phrases of different
  topics) [html]
- [Das Parlament](https://www.bundestag.de/leichte_sprache/was_macht_der_bundestag/parlament) (approx. 200 articles of
  different legal topics / sociological topics) [pdf]
- [Bundestag Website](https://www.bundestag.de/leichte_sprache/) (15 articles describing the work of the german
  parliament) [html]
- [Federal Ministry of Labour and Social Affairs](https://www.bmas.de/DE/Leichte-Sprache/Publikationen-leichte-Sprache/publikationen-leichte-sprache.html) (
  17 articles of different legal / social topics; partly with corresponding original articles in standard German) [pdf]
- [Bible texts](https://evangelium-in-leichter-sprache.de/) (approx. 180 religious texts) [html]
- [Federal Ministry of Justice](https://www.bmj.de/DE/LeichteSprache/Woerterbuch-Leichte-Sprache.html) (some word
  explanations concerning legal terms) [html]
- [Einfach Teilhaben (Federal Ministry of Labour and Social Affairs)](https://www.einfach-teilhaben.de/DE/LS/Home/leichtesprache_node.html) (>
  30 articles of different social topics) [html]
- [Deutsches Institut für Menschenrechte](https://www.institut-fuer-menschenrechte.de/leichte-sprache) (approx. 30
  articles of different legal / social topics; partly with corresponding original text in standard German) [pdf]
- [News in "Leichte Sprache" (Deutschlandfunk)](https://www.nachrichtenleicht.de/) (lexicon + about 4 new articles per
  week) [html]
- [News in "Leichte Sprache" (MDR)](https://www.mdr.de/nachrichten-leicht/rueckblick/index.html) (lexicon + about 300
  articles total from the last 3 months from states of Thüringen, Saxen, Saxen-Anhalt) [html]
- [nachrichtenleicht](https://www.nachrichtenleicht.de/)

## Parallel Data

- [KLexikon](https://github.com/dennlinger/klexikon) - article-aligned, however not in Leichte Sprache
- [hdaSprachtechnologie](https://github.com/hdaSprachtechnologie/easy-to-understand_language) - article-aligned:

| Topic             | # chars (leichte) | # chars (standard) | # sentences (leichte) | # sentences (standard) | Notes                                                                 |
|-------------------|-------------------|--------------------|-----------------------|------------------------|-----------------------------------------------------------------------|
| Election Programs | 40 406            | 782 843            | 773                   | 6 376                  | -                                                                     |
| Bible             | 32 663            | 28 044             | 806                   | 338                    | -                                                                     |
| Tales             | 104 647           | 92 335             | 2 332                 | 587                    | -                                                                     |
| BRK               | 9 263             | 26 534             | 152                   | 170                    | -                                                                     |
| News              | 6 197             | 6 305              | 102                   | 81                     | Standard German translation is sometimes mixed with "Leichte Sprache" |
| Books             | 1 863             | 2 666              | 45                    | 29                     | -                                                                     |

- [BRK (Convention on the Rights of Persons with Disabilities)](http://www.brk-allianz.de/index.php/m-brk-fassungen.html)
  1 document in different languages including standard german and "Leichte Sprache" [pdf]
- Collected parallel data sources in Geasy corpus: [online](https://seafile.rlp.net/f/a25a64e6dfa54373b5a1/)
- [GWW](https://www.gww-netz.de/de-LS/)
- [Heilpädagogische Hilfe Osnabrück](https://www.os-hho.de/)
- [Lebenshilfe Main-Taunus](https://www.lebenshilfe-main-taunus.de/)
- [OWB](https://www.owb.de/)
- [einfach teilhaben](https://www.einfach-teilhaben.de/DE/LS/Home/leichtesprache_node.html)
- [capito](www.capito.eu)

## Potential Issues

### Severely unbalanced topics

Much of the data comes from government websites or texts in a legal context

**Possible solutions**  
Use sentence embedding methods to cluster the phrases from the data.  
You may be able to recognize clusters that can be assigned to certain topics or writing styles.  
Phrases from these clusters can then be weighted differently.
