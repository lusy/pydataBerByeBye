% Es hora de decir bye-bye
% Using python for sociolinguistic analysis
% lusy

---

# What is this talk about

* scraping webpages
* lingusitics
  * processing linguistic data
  * interpreting linguistic data

---

# Motivation

![Screenshot from Aug 13th 2017](siempre_mujer_screenshot_201708.png)

---

> Si tu amiga se la pasa poniendo memes que critican tu postura religiosa, se burlan abiértamente de los homosexuales y apoyan frases que parecen de la época de la esclavitud que te incomodan. *Es hora de decir bye-bye.*

---

## What have I done?

* scrape articles: 1419
  * possible problems: messy html structure of the magazine
  * alternative approach: systematic crawling with `scrapy`?
* strip articles from html markup

---

### cs: compilers

```
$ 'main'
 \
  \-[Someone set us up the bomb.\n\]-b--#
```

### linguistics

* "self-esteem"/"self esteem"
* "machine learning"
* "you're"

* segment article texts in tokens: non-trivial
* `nltk.word_tokenize()`

---

* download and clean openoffice spelling dictionaries
  * intersection and differences (Spanish common and Spanish regional);
* label each token according to appearance in dictionaries (EN, ES, ES_regional --> multiple labels possible; PUNCT; UNK)

---

## Problems:

* maintainer: dictionaries non-exhaustive: (seldom) words are missing
* linguistic: not every word is present in all its forms (e.g. singular, plural, m, f forms; or every tempus, modus, etc. for the verbs)
* linguistic: some words exist in both languages (e.g.: "me", "no", "hay", "sin", "soy", "sea" etc.)

---

## alternatives

* generate more complete word lists?
* `langid.py`?
* `nltk.corpus.words.words()` for English?

---

* consider all tokens marked as EN only and their surrounding context
* 3271 distinct appearances
* use NLTK `Texts.ConcordanceIndex()` for generating context

---

```
Article # 53990
[baby, ['EN']]
Displaying 4 of 4 matches:
epollo púrpura , y todos los “bebés” baby carrots , baby remolachas , baby gre
, y todos los “bebés” baby carrots , baby remolachas , baby greens , baby arúg
és” baby carrots , baby remolachas , baby greens , baby arúgula . También el n
ts , baby remolachas , baby greens , baby arúgula . También el nabo , los chal

------------------------------------------------------------

Article # 51108
[charter, ['EN']]
Displaying 1 of 1 matches:
as , tanto públicas como privadas y charter . El sitio es muy fácil de usar , y
```

---

## sorting into categories

* manually!
* alternative: automatic classification into categories
  * supervised learning
  * clustering

---

# Resulting Categories

---

## named entities

"Converse All-Star" (#57677, 52997), "iPod Shuffle" (#57677, #29888), "Daily Mail" (#64324, #64721, #66655, #42121, #69357), "American Diabetes Association" (#75801), ...

---

## tech/internet

```
"Haz clic aquí  " (#61262) ("Click here")
"se convirtió en un trending topic en las redes sociales" (#73673) (it became a trending topic in the social networks)
"por nuestros followers en las redes sociales" (#73189) (for our followers in the social networks)
"tiene capacidad de WiFi integrada" (#18762) (has an integrated wifi capacity)
"comenzó a ofrecer su servicio de streaming en Latinoamérica y el Caribe" (#26486) (started to offer streaming services in Latin America and the Caribics)
"hace compras online" (#59254) ("do shopping online")
```
---

## food/cooking

### english names in parents

```
"panceta ( bacon )" (#72354)
"la anchoa y la caballa ( mackerel )" (#75194)
"Por ejemplo: Cranberry (arandanos)" (#76140)
"con un albaricoque (apricot)" (#41196)
"col rizada (kale, en ingles)" (#65784)
"curcuma fresca (turmeric)" (#78170)
```
---

### life style

```
"prefieres alimentos gluten-free," (#65784) ("prefer gluten-free foods")
"4 tazas de espinacas tiernas (baby) limpias" (#54045) ("4 cups of clean baby spinach")
" pavo wild con salvia y ajo " (#64931) ("wild turkey with sage and garlic")
"el saludable smoothie de fresas" (#65851) ("the healthy strawberry smoothie")
"mirarán de forma extraña en tu coffeehouse favorito" (#76571) ("will look funny in your favourite coffeehouse")
```

---

## and more life style

```
"alimentos trendy" (#78170) ("trendy foods")
"cambia radicalmente de look" (#64405) ("change your look radically")
"los productos vintage originales" (#78849) ("the original vintage products")
"con pequenos toques de glamour" (#54615) ("with little glamour touches")
```

---

## sex

```
"elevar tu nivel de sex-appeal" (#61317) ("boost your sex-appeal level")
"tiene sex appeal y te llama la atencion" (#78736) ("has sex appeal and attracts your attention")
"no trata de ser sexy" (#61317) ("don't try to be sexy")
"hay tantos tipos de sexy como hay mujeres" (#61317) ("there are as many types of sexy as there are women")
"Qué es sexy ?" (#61317) ("what is sexy?")
"para tener una noche súper hot" (#73447) ("in order to have a super hot night")
```

---

## English idioms/collocations

```
"vivimos el presente a full" (#75882) ("we live the present at full")
"casarse y vivir su happily ever after" (#78457) ("get married and live their happily ever after")
"ahora esta in love con este hombre" (#78457) ("now (she) is love with this man")
"son verdaderas decision makers" (#45099) ("are the real decision makers")
"echale un vistazo al behind the scenes" (#64443) ("take a look behind the scenes")
"Mix and match , la pareja ideal" (#62615) ("Mix and match, the perfect partner")
```
---

# Excursion into (socio-)linguistics

* code switching / borrowing --> language shift
* words do not exist in the first language
* words sound similar
* words are shorter
* one of the languages is perceived as more prestigious: conscious choice
* neutral substitute

---

# Takeaways

* linguistics is awesome
* coding skills go a long way
* non-trivial problems
* "lifestyle"/"women"-magazines are evil

---

# Sources

* this presentation: [https://github.com/lusy/pydataBerByeBye](https://github.com/lusy/pydataBerByeBye)
* code: [https://github.com/lusy/hora-de-decir-bye-bye](https://github.com/lusy/hora-de-decir-bye-bye)
* Eckert, Penelope: Variation and the indexical field. In: Journal of Sociolinguistics 12 (2008), Nr. 4, S. 453–476
* Thomason, Sarah G.: Contact as a Source of Language Change. In: Joseph, Brian D. (Hrsg.) ; Janda, Richard D. (Hrsg.): The Handbook of Historical Linguistics. Oxford, UK : Blackwell Publishing Ltd, 2003, S. 687–712
* Zentella, Ana C.: Lexical Leveling in Four New York City Spanish Dialects: Linguistic and Social Factors. In: Hispania 73 (1990), Nr. 4

---

# Thank you!

This presentation is licensed under the [Creative Commons BY-SA license](https://creativecommons.org/licenses/by-sa/4.0/).

![by](Cc-by_new_white.svg)
![sa](Cc-sa_white.svg)

Shoot me an email:
