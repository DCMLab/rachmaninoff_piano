![Version](https://img.shields.io/github/v/release/DCMLab/rachmaninoff_piano?display_name=tag)
[![DOI](https://zenodo.org/badge/520217150.svg)](https://doi.org/10.5281/zenodo.14984155)
![GitHub repo size](https://img.shields.io/github/repo-size/DCMLab/rachmaninoff_piano)
![License](https://img.shields.io/badge/license-CC%20BY--NC--SA%204.0-9cf)


This is a README file for a data repository originating from the [DCML corpus initiative](https://github.com/DCMLab/dcml_corpora)
and serves as welcome page for both 

* the GitHub repo [https://github.com/DCMLab/rachmaninoff_piano](https://github.com/DCMLab/rachmaninoff_piano) and the corresponding
* documentation page [https://dcmlab.github.io/rachmaninoff_piano](https://dcmlab.github.io/rachmaninoff_piano)

For information on how to obtain and use the dataset, please refer to [this documentation page](https://dcmlab.github.io/rachmaninoff_piano/introduction).

# Sergei Rachmaninoff – Variations on a Theme of Corelli, Op. 42 (A corpus of annotated scores)

This corpus of annotated [MuseScore](https://musescore.org) files has been created within
the [DCML corpus initiative](https://github.com/DCMLab/dcml_corpora) and employs
the [DCML harmony annotation standard](https://github.com/DCMLab/standards).
It represents Sergei Rachmaninoff's virtuosic op. 42 Variations (1931). This work, written on Lake Lucerne in
Switzerland, reflects the style of the composer's reticent late period. The title is something of a misnomer, as the
theme is in fact the traditional La Folia, used widely by composers of the 17th and 18th centuries including Vivaldi,
Händel, and indeed Corelli. Rachmaninoff tears this venerable theme to shreds with pianistic pyrotechnics so difficult
that the composer himself, champion of the instrument that he was, found them unplayable. Our annotations reveal the
tonal substance out of which this cycle's impressive digressions and interpolations are forged, and comparing the
outputs of each of these variations should provide fertile ground for quantitative study of variational technique.

## Getting the data

* download repository as a [ZIP file](https://github.com/DCMLab/rachmaninoff_piano/archive/main.zip)
* download a [Frictionless Datapackage](https://specs.frictionlessdata.io/data-package/) that includes concatenations
  of the TSV files in the four folders (`measures`, `notes`, `chords`, and `harmonies`) and a JSON descriptor:
  * [rachmaninoff_piano.zip](https://github.com/DCMLab/rachmaninoff_piano/releases/latest/download/rachmaninoff_piano.zip)
  * [rachmaninoff_piano.datapackage.json](https://github.com/DCMLab/rachmaninoff_piano/releases/latest/download/rachmaninoff_piano.datapackage.json)
* clone the repo: `git clone https://github.com/DCMLab/rachmaninoff_piano.git` 


## Data Formats

Each piece in this corpus is represented by five files with identical name prefixes, each in its own folder. 
For example, the variation theme has the following files:

* `MS3/op42_01a.mscx`: Uncompressed MuseScore 3.6.2 file including the music and annotation labels.
* `notes/op42_01a.notes.tsv`: A table of all note heads contained in the score and their relevant features (not each of them represents an onset, some are tied together)
* `measures/op42_01a.measures.tsv`: A table with relevant information about the measures in the score.
* `chords/op42_01a.chords.tsv`: A table containing layer-wise unique onset positions with the musical markup (such as dynamics, articulation, lyrics, figured bass, etc.).
* `harmonies/op42_01a.harmonies.tsv`: A table of the included harmony labels (including cadences and phrases) with their positions in the score.

Each TSV file comes with its own JSON descriptor that describes the meanings and datatypes of the columns ("fields") it contains,
follows the [Frictionless specification](https://specs.frictionlessdata.io/tabular-data-resource/),
and can be used to validate and correctly load the described file. 

### Opening Scores

After navigating to your local copy, you can open the scores in the folder `MS3` with the free and open source score
editor [MuseScore](https://musescore.org). Please note that the scores have been edited, annotated and tested with
[MuseScore 3.6.2](https://github.com/musescore/MuseScore/releases/tag/v3.6.2). 
MuseScore 4 has since been released which renders them correctly but cannot store them back in the same format.

### Opening TSV files in a spreadsheet

Tab-separated value (TSV) files are like Comma-separated value (CSV) files and can be opened with most modern text
editors. However, for correctly displaying the columns, you might want to use a spreadsheet or an addon for your
favourite text editor. When you use a spreadsheet such as Excel, it might annoy you by interpreting fractions as
dates. This can be circumvented by using `Data --> From Text/CSV` or the free alternative
[LibreOffice Calc](https://www.libreoffice.org/download/download/). Other than that, TSV data can be loaded with
every modern programming language.

### Loading TSV files in Python

Since the TSV files contain null values, lists, fractions, and numbers that are to be treated as strings, you may want
to use this code to load any TSV files related to this repository (provided you're doing it in Python). After a quick
`pip install -U ms3` (requires Python 3.10 or later) you'll be able to load any TSV like this:

```python
import ms3

labels = ms3.load_tsv("harmonies/op42_01a.harmonies.tsv")
notes = ms3.load_tsv("notes/op42_01a.notes.tsv")
```


## Version history

See the [GitHub releases](https://github.com/DCMLab/rachmaninoff_piano/releases).

## Questions, Suggestions, Corrections, Bug Reports

Please [create an issue](https://github.com/DCMLab/rachmaninoff_piano/issues) and/or feel free to fork and submit pull requests.

## Cite as

> Johannes Hentschel, Yannis Rammos, Markus Neuwirth, & Martin Rohrmeier. (2025). Sergei Rachmaninoff – Variations on a Theme of Corelli, Op. 42 (A corpus of annotated scores) [Data set]. Zenodo. https://doi.org/10.5281/zenodo.14984155

## License

Creative Commons Attribution-NonCommercial-ShareAlike 4.0 International License ([CC BY-NC-SA 4.0](https://creativecommons.org/licenses/by-nc-sa/4.0/)).

![cc-by-nc-sa-image](https://licensebuttons.net/l/by-nc-sa/4.0/88x31.png)

## Scores

These scores were specially typeset for this project by Matthias Schabow following the reissued 1931 first edition, which is itself available via the IMSLP MIT Archive Project.

## File naming convention

```regex
op42_(?<movement>\d{2}[ab]?)
```

## Overview
|file_name|measures|labels|standard|    annotators     |     reviewers     |
|---------|-------:|-----:|--------|-------------------|-------------------|
|op42_05  |      16|    17|2.3.0   |0000-0002-6329-7492|0000-0002-6588-2257|
|op42_06  |      16|    82|2.3.0   |0000-0002-6329-7492|0000-0002-6588-2257|
|op42_07  |      18|    51|2.3.0   |0000-0002-6329-7492|0000-0002-6588-2257|
|op42_08  |      15|    45|2.3.0   |0000-0002-6329-7492|0000-0002-6588-2257|
|op42_09  |      19|    52|2.3.0   |0000-0002-6329-7492|0000-0002-2105-525X|
|op42_10  |      25|    45|2.3.0   |0000-0002-6329-7492|0000-0002-2105-525X|
|op42_01a |      16|    28|2.3.0   |0000-0002-6329-7492|0000-0002-6588-2257|
|op42_01b |      16|    35|2.3.0   |0000-0002-6329-7492|0000-0002-6588-2257|
|op42_02  |      16|    24|2.3.0   |0000-0002-6329-7492|0000-0002-6588-2257|
|op42_03  |      16|    52|2.3.0   |0000-0002-6329-7492|0000-0002-6588-2257|
|op42_04  |      16|    22|2.3.0   |0000-0002-6329-7492|0000-0002-6588-2257|
|op42_11  |      16|    54|2.3.0   |0000-0002-6329-7492|0000-0002-6588-2257|
|op42_12  |      23|    69|2.3.0   |0000-0002-6329-7492|0000-0002-6588-2257|
|op42_13a |      17|    69|2.3.0   |0000-0002-6329-7492|0000-0002-6588-2257|
|op42_13b |      13|    47|2.3.0   |0000-0002-6329-7492|0000-0002-6588-2257|
|op42_14  |      16|    35|2.3.0   |0000-0002-6329-7492|0000-0002-6588-2257|
|op42_15  |      26|    66|2.3.0   |0000-0002-6329-7492|0000-0002-6588-2257|
|op42_16  |      15|    58|2.3.0   |0000-0002-6329-7492|0000-0002-6588-2257|
|op42_17  |      23|    40|2.3.0   |0000-0002-6329-7492|0000-0002-6588-2257|
|op42_18  |      16|    50|2.3.0   |0000-0002-6329-7492|VZ                 |
|op42_19  |      17|    99|2.3.0   |0000-0002-6329-7492|VZ                 |
|op42_20  |      44|   101|2.3.0   |0000-0002-6329-7492|VZ                 |


*Overview table automatically updated using [ms3](https://ms3.readthedocs.io/).*
