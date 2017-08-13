% Es hora de decir bye-bye
% Using python for sociolinguistic analysis
% lusy (lusy@spline.de)

---

This repository contains a talk on the collection and explanation of the English occurrences in a corpus of articles from the US Spanish language journal "Siempre mujer".
We will have a look at the python modules for scraping and natural language processing used for the project (pattern, request and nltk),
try to evaluate their suitability for the task and discuss alternative approaches.
As an added bonus we will also briefly touch on some theories from the sociolinguistics in an attempt to understand why English was used in the particular cases.

---

* What will people learn?
* Activation questions

---

# Structure

* problem: hausarbeit; scrape articles; identify English occurrances; analyse them
* approach: use python!
  * scrape articles (pattern, request) -> possible problems (irregular html structure of the magazine)
  * clean articles from html markup -> result we use for next step: plain text
  * segment article texts in tokens (use ' ' as delimiter)
  * was hab ich nochma mit nltk gemacht?
  * identify English occurrences in the Spanish texts (download and apply the libre office Spanish and English language dicts); label each token according to appearance in dictionaries (EN, ES or both)
    * problems: some words exist in both languages (e.g.: "me", "no", "hay", etc.)
    * dictionaries non-exhaustive: seldom words are missing
    * not every word is present in all its forms (e.g. singular, plural, m, f forms; or every tempus, modus, .. for the verbs) --> it is possible to generate flexions forms and add them to dicts, but it makes the process a whole lot more complicated
  * consider all words marked as EN only and their surrounding context
* brief overview over resulting cathegories
* discuss alternative approaches on each step (or on the whole)
  * e.g. for scraping you can also use BeautifulSoup

---

# Motivation

* problem: hausarbeit; scrape articles; identify English occurrances; analyse them
Example: http://siempremujer.com/estilo/8-senales-amiga-toxica-en-redes-sociales/72941/
8 señales de una amiga tóxica en las redes sociales

> Maquinita de criticar: Si tu amiga se la pasa poniendo memes que critican tu postura religiosa, se burlan abiértamente de los homosexuales y apoyan frases que parecen de la época de la esclavitud que te incomodan. *Es hora de decir bye-bye.*

---

# Excursion into (socio-)linguistics

* code switching
Der Begriff Code-Switching beschreibt die alternierende Benutzung von zwei oder meh-
reren Codes (Sprachen, Varietäten, Dialekten) innerhalb einer und der selben Äußerung.
* borrowing
Borrowing oder Entlehnung ist die Benutzung der Elemente einer Sprache in einer an-
deren Sprache. Meistens meinen wir damit Entlehnungen auf der Lexikon-Ebene, jedoch
können auch Elemente anderer Systeme entlehnt werden (was durchaus seltener pas-
siert) (vgl. Thomason, 2003). Wichtig dabei ist, dass Borrowings in einer Sprache A
durch Muttersprachlerinnen dieser Sprache inkorporiert werden (vgl. Thomason, 2003).
Wenn die Personen, die die Elemente aus Sprache B in Sprache A übertragen, Mutter-
sprachlerinnen der Sprache B sind, die die Sprache A gerade erlernen, reden wir von
einer “shift-induced interference” (vgl. Thomason, 2003).

Laut Sarah Thomason ist Code-Switching vermutlich der häufigste Weg, auf dem Ent-
lehnungen Teil einer Sprache werden (vgl. Thomason, 2003).
Schwierig scharf von einander abzugrenzen; Unterschied: quantitativer Natur

Warum passieren beide? "powerful socioeconomic and cultural forces", die Borrowings in Kontaktsi-
tuationen zwischen zwei Kulturen fördern(vgl. Zentella, 1990).

* socio indexicality

---

# Linguistic interpretation

Kategorien:
* Named Entities
* Kochrezepte/Essen
* “look”
4.2 Interpretation
* English is the more prestigious language;
* the dominant (both in numbers and power) group of people in the USA speaks English
* serves to avoid misunderstandings/clarify (zb cooking recipes)
* es wird ein bestimmter Lebensstil kreiert/bedient

---

# Sources

* this presentation: [https://github.com/lusy/pydataBerByeBye](https://github.com/lusy/pydataBerByeBye)
* code: [https://github.com/lusy/hora-de-decir-bye-bye](https://github.com/lusy/hora-de-decir-bye-bye)

---

# Thank you!

This presentation is licensed under the [Creative Commons BY-SA license](https://creativecommons.org/licenses/by-sa/4.0/).

![by](Cc-by_new_white.svg)
![sa](Cc-sa_white.svg)

