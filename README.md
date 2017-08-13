# Es hora de decir bye-bye. Using python for sociolinguistic analysis.

This repository contains a talk on the collection and explanation of the English occurrences in a corpus of articles from the US Spanish language journal "Siempre mujer".
We will have a look at the python modules for scraping and natural language processing used for the project (pattern, request and nltk),
try to evaluate their suitability for the task and discuss alternative approaches.
As an added bonus we'll also briefly touch on some theories from the sociolinguistics in an attempt to understand why English was used in the particular cases.

The talk is in English language and prepared for the pydata meetup Berlin August 2017.

## paper

I'm also writing a [paper](https://github.com/lusy/hausarbeiten/tree/master/spanishNYC/hausarbeit) on the topic.

## code

You can also view the [code](https://github.com/lusy/hora-de-decir-bye-bye) I've written as part of this analysis.

## to view the presentation

* checkout this repo
* checkout [revealjs](https://github.com/hakimel/reveal.js) in the same directory under the name `reveal.js`
* open the `slides.html` file in your browser

## to build the slides

* checkout this repo
* checkout [revealjs](https://github.com/hakimel/reveal.js) in the same directory under the name `reveal.js`
* edit the source of the slides: the `slides.md` file

* install [pandoc](https://github.com/jgm/pandoc/releases/)

### html slides

use `pandoc -s --mathjax -i -t revealjs slides.md -o slides.html` to convert the slides to a html presentation

### latex slides

use `pandoc -t beamer slides.md -o slides.pdf` to convert the slides to a latex beamer presentation


## license

This talk is licensed under the Creative Commons Attribution-ShareAlike 4.0 (CC BY-SA 4.0) License. For more detailed information, visit [https://creativecommons.org/licenses/by-sa/4.0/](https://creativecommons.org/licenses/by-sa/4.0/)

