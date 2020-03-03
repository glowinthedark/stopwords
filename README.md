
# stopwords: the R package

[![CRAN
Version](https://www.r-pkg.org/badges/version/stopwords)](https://CRAN.R-project.org/package=stopwords)
[![Travis-CI Build
Status](https://travis-ci.org/quanteda/stopwords.svg?branch=master)](https://travis-ci.org/quanteda/stopwords)
[![Coverage
status](https://codecov.io/gh/davnn/stopwords/branch/master/graph/badge.svg)](https://codecov.io/github/davnn/stopwords?branch=master)
[![Downloads](https://cranlogs.r-pkg.org/badges/stopwords)](https://CRAN.R-project.org/package=stopwords)
[![Total
Downloads](https://cranlogs.r-pkg.org/badges/grand-total/stopwords?color=orange)](https://CRAN.R-project.org/package=stopwords)

R package providing “one-stop shopping” (or should that be “one-shop
stopping”?) for stopword lists in R, for multiple languages and sources.
No longer should text analysis or NLP packages bake in their own
stopword lists or functions, since this package can accommodate them
all, and is easily extended.

Created by [David Muhr](https://github.com/davnn), and extended in
cooperation with [Kenneth Benoit](https://github.com/kbenoit) and [Kohei
Watanabe](https://github.com/koheiw).

## Installation

``` r
# from CRAN
install.packages("stopwords")

# Or get the development version from GitHub:
# install.packages("devtools")
devtools::install_github("quanteda/stopwords")
```

## Usage

``` r
head(stopwords::stopwords("de", source = "snowball"), 20)
##  [1] "aber"    "alle"    "allem"   "allen"   "aller"   "alles"   "als"    
##  [8] "also"    "am"      "an"      "ander"   "andere"  "anderem" "anderen"
## [15] "anderer" "anderes" "anderm"  "andern"  "anderr"  "anders"

head(stopwords::stopwords("de", source = "stopwords-iso"), 20)
##  [1] "a"           "ab"          "aber"        "ach"         "acht"       
##  [6] "achte"       "achten"      "achter"      "achtes"      "ag"         
## [11] "alle"        "allein"      "allem"       "allen"       "aller"      
## [16] "allerdings"  "alles"       "allgemeinen" "als"         "also"
```

For compatibility with the former `quanteda::stopwords()`:

``` r
head(stopwords::stopwords("german"), 20)
##  [1] "aber"    "alle"    "allem"   "allen"   "aller"   "alles"   "als"    
##  [8] "also"    "am"      "an"      "ander"   "andere"  "anderem" "anderen"
## [15] "anderer" "anderes" "anderm"  "andern"  "anderr"  "anders"
```

Explore sources and languages:

``` r
# list all sources
stopwords::stopwords_getsources()
## [1] "snowball"      "stopwords-iso" "misc"          "smart"

# list languages for a specific source
stopwords::stopwords_getlanguages("snowball")
##  [1] "da" "de" "en" "es" "fi" "fr" "hu" "ir" "it" "nl" "no" "pt" "ro" "ru" "sv"
```

## Languages available

The following coverage of languages is currently available, by source.
Note that the inclusiveness of the stopword lists will vary by source,
and the number of languages covered by a stopword list does not
necessarily mean that the source is better than one with more limited
coverage. (There may be many reasons to prefer the default “snowball”
source over the “stopwords-iso” source, for instance.)

The following languages are currently
available:

| Language       | [ISO-639-1 Code](https://en.wikipedia.org/wiki/List_of_ISO_639-1_codes) | `stopwords-iso` | `snowball` | `SMART` | `misc` |
| :------------- | :---------------------------------------------------------------------: | :-------------: | :--------: | :-----: | :----: |
| Afrikaans      |                                   af                                    |        ✔        |            |         |        |
| Arabic         |                                   ar                                    |        ✔        |            |         |   ✔    |
| Armenian       |                                   hy                                    |        ✔        |            |         |        |
| Basque         |                                   eu                                    |        ✔        |            |         |        |
| Bengali        |                                   bn                                    |        ✔        |            |         |        |
| Breton         |                                   br                                    |        ✔        |            |         |        |
| Bulgarian      |                                   bg                                    |        ✔        |            |         |        |
| Catalan        |                                   ca                                    |        ✔        |            |         |   ✔    |
| Chinese        |                                   zh                                    |        ✔        |            |         |   ✔    |
| Croatian       |                                   hr                                    |        ✔        |            |         |        |
| Czech          |                                   cs                                    |        ✔        |            |         |        |
| Danish         |                                   da                                    |        ✔        |     ✔      |         |        |
| Dutch          |                                   nl                                    |        ✔        |     ✔      |         |        |
| English        |                                   en                                    |        ✔        |     ✔      |    ✔    |        |
| Esperanto      |                                   eo                                    |        ✔        |            |         |        |
| Estonian       |                                   et                                    |        ✔        |            |         |        |
| Finnish        |                                   fi                                    |        ✔        |     ✔      |         |        |
| French         |                                   fr                                    |        ✔        |     ✔      |         |        |
| Galician       |                                   gl                                    |        ✔        |            |         |        |
| German         |                                   de                                    |        ✔        |     ✔      |         |        |
| Greek          |                                   el                                    |        ✔        |            |         |   ✔    |
| Gujarati       |                                   gu                                    |                 |            |         |   ✔    |
| Hausa          |                                   ha                                    |        ✔        |            |         |        |
| Hebrew         |                                   he                                    |        ✔        |            |         |        |
| Hindi          |                                   hi                                    |        ✔        |            |         |        |
| Hungarian      |                                   hu                                    |        ✔        |     ✔      |         |        |
| Indonesian     |                                   id                                    |        ✔        |            |         |        |
| Irish          |                                   ga                                    |        ✔        |            |         |        |
| Italian        |                                   it                                    |        ✔        |     ✔      |         |        |
| Japanese       |                                   ja                                    |        ✔        |            |         |        |
| Korean         |                                   ko                                    |        ✔        |            |         |        |
| Kurdish        |                                   ku                                    |        ✔        |            |         |        |
| Latin          |                                   la                                    |        ✔        |            |         |        |
| Lithuanian     |                                   lt                                    |        ✔        |            |         |        |
| Latvian        |                                   lv                                    |        ✔        |            |         |        |
| Malay          |                                   ms                                    |        ✔        |            |         |        |
| Marathi        |                                   mr                                    |        ✔        |            |         |        |
| Norwegian      |                                   no                                    |        ✔        |     ✔      |         |        |
| Persian        |                                   fa                                    |        ✔        |            |         |        |
| Polish         |                                   pl                                    |        ✔        |            |         |        |
| Portuguese     |                                   pt                                    |        ✔        |     ✔      |         |        |
| Romanian       |                                   ro                                    |        ✔        |     ✔      |         |        |
| Russian        |                                   ru                                    |        ✔        |     ✔      |         |        |
| Slovak         |                                   sk                                    |        ✔        |            |         |        |
| Slovenian      |                                   sl                                    |        ✔        |            |         |        |
| Somali         |                                   so                                    |        ✔        |            |         |        |
| Southern Sotho |                                   st                                    |        ✔        |            |         |        |
| Spanish        |                                   es                                    |        ✔        |     ✔      |         |        |
| Swahili        |                                   sw                                    |        ✔        |            |         |        |
| Swedish        |                                   sv                                    |        ✔        |     ✔      |         |        |
| Thai           |                                   th                                    |        ✔        |            |         |        |
| Tagalog        |                                   tl                                    |        ✔        |            |         |        |
| Turkish        |                                   tr                                    |        ✔        |            |         |        |
| Ukrainian      |                                   uk                                    |        ✔        |            |         |        |
| Urdu           |                                   ur                                    |        ✔        |            |         |        |
| Vietnamese     |                                   vi                                    |        ✔        |            |         |        |
| Yoruba         |                                   yo                                    |        ✔        |            |         |        |
| Zulu           |                                   zu                                    |        ✔        |            |         |        |

## Adding stopwords to your own package

As of version 1.1, we’ve made it a one-step process to add `stopwords()`
to your package through a re-export. Simply call `use_stopwords()` like
this:

``` r
> stopwords::use_stopwords()
✔ Setting active project to '/Users/me/GitHub/mypackage'
✔ Adding 'stopwords' to Imports field in DESCRIPTION
✔ Writing 'R/use-stopwords.R'
● Run `devtools::document()` to update 'NAMESPACE'

> devtools::document()
Updating mypackage documentation
Updating collate directive in  /Users/me/GitHub/mypackage/DESCRIPTION 
Writing NAMESPACE
Loading mypackage
Writing NAMESPACE
Writing stopwords.Rd
```

## Contributing

Additional sources can be defined and contributed by adding new data
objects, as follows:

1.  **Data object**. Create a named list of characters, in UTF-8 format,
    consisting of the stopwords for each language. The
    [ISO-639-1](https://en.wikipedia.org/wiki/List_of_ISO_639-1_codes)
    language code will form the name of the list element, and the values
    of each element will be the character vector of stopwords for
    literal matches. The data object should follow the package naming
    convention, and be called `data_stopwords_newsource`, where
    `newsource` is replaced by the name of the new source.

2.  **Documentation**. The new source should be clearly documented,
    especially the source from which was taken.

## License

This package as well as the source repositories are licensed under MIT.
