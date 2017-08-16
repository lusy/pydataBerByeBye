% Es hora de decir bye-bye
% Using python for sociolinguistic analysis
% lusy

---

# Motivation

![](siempre_mujer_screenshot_201708.png)

---

8 señales de una amiga tóxica en las redes sociales

> Maquinita de criticar: Si tu amiga se la pasa poniendo memes que critican tu postura religiosa, se burlan abiértamente de los homosexuales y apoyan frases que parecen de la época de la esclavitud que te incomodan. *Es hora de decir bye-bye.*

---

# What is this talk about

* scraping webpages
* lingusitics
  * processing linguistic data
  * interpreting linguistic data

---

## What have I done?

* quick and dirty
* procedural, one task at time (Unix approach^^)
* python 2.7 (2013)

---

* scrape articles (pattern, request)
  * possible problems: irregular html structure of the magazine
* also note which category each article was in on the website (fashion, lifestyle, love, beauty, fitness, etc..)
* clean articles from html markup
* segment article texts in tokens
  * nltk.word_tokenize()

---

* download and clean libre office spelling dictionaries
  * intersection and differences (Spanish common and Spanish regional);
* label each token according to appearance in dictionaries (EN, ES, ES_regional --> multiple labels possible; PUNCT; UNK)
  Problems:
    * dictionaries non-exhaustive: seldom words are missing
    * not every word is present in all its forms (e.g. singular, plural, m, f forms; or every tempus, modus, .. for the verbs) --> it is possible to generate flexions forms and add them to dicts, but it makes the process a whole lot more complicated
  * some words exist in both languages (e.g.: "me", "no", "hay", "sin", "soy", "sea" etc.)

---

* consider all words marked as EN only and their surrounding context
  * use NLTK Texts.ConcordanceIndex() for generating context

Article # 72933
[love, ['EN']]
Displaying 1 of 1 matches:
ersando con Trilce Ortiz , sexpert y love adviser de Ellaysusexo .com , quien

[adviser, ['EN']]
Displaying 1 of 1 matches:
o con Trilce Ortiz , sexpert y love adviser de Ellaysusexo .com , quien nos dio

[one, ['EN']]
Displaying 1 of 1 matches:
erlo . Yo creo que así se trate de un one night stand o del amor de tu vida , l

[night, ['EN']]
Displaying 1 of 1 matches:
. Yo creo que así se trate de un one night stand o del amor de tu vida , lo más

---

# Excursion into (socio-)linguistics

* code switching
* borrowing
* language shift
* socio indexicality
 ** first-order index
 ** secondary index
* indexical field/style

---

# Resulting Categories

---

## named entities

"Converse All-Star" (#57677, 52997), "iPod Shuffle" (#57677, #29888), "Daily Mail" (#64324, #64721, #66655, #42121, #69357), "American Diabetes Association" (#75801), ...

---

## tech/internet

  * clic: " Haz clic en Send y eso es todo " (#23166)
  * clic: " Haz clic aquí  " (#61262)
  * clic: "haz clic en “donate”" (#46929)
  * hashtag: "donde el hashtag “ # RIP # GabrielGarcíaMarquez” se ha posicio" (#69261)
  * trending topic: "A través de las redes sociales la convirtieron en hashtag y ha llegado a ser trending topic" (#75913)
  * trending topic: "no ha tardado en colocarse como “trending topic” en las redes sociales" (#69261)
  * trending topic: "se convirtió en un trending topic en las redes sociales" (#73673)
  * follower: "por nuestros followers en las redes sociales" (#73189) (or open social media cathegory)
  * tweet: " mandarle un tweet para que sepa que lo piensas " (#73189) (or open social media cathegory)
  * wifi: "con frecuencia a través de WiFi" (#33890)
  * wifi: "tiene capacidad de WiFi integrada" (#18762)

---

## food/cooking

life-style shit
   * gluten free: "prefieres alimentos gluten-free," (#65784)
   * baby: "4 tazas de espinacas tiernas (baby) limpias" (#54045)
   * wild: " pavo wild con salvia y ajo " (#64931)
   * smoothie: "el saludable smoothie de fresas" (#65851)
   * coffeehouse: "mirarán de forma extraña en tu coffeehouse favorito" (#76571)
(+ more stuff: vintage, look,..)
english names in parents
   * bacon: "panceta ( bacon )" (#72354)
   * "la anchoa y la caballa ( mackerel )" (#75194),
   * cranberry: "Por ejemplo: Cranberry (arandanos)" (#76140)
   * apricot: "con un albaricoque (apricot)" (#41196) --> English translation in parents.
   * kale: "col rizada (kale, en ingles)" (#65784)
   * turmeric: "curcuma fresca (turmeric)" (#78170)

---

## sex

   * sex appeal: "elevar tu nivel de sex-appeal" (#61317)
   * sex appeal: "tiene sex appeal y te llama la atencion" (#78736)
   * sexy: "no trata de ser sexy" (#61317)
   * sexy: "hay tantos tipos de sexy como hay mujeres" (#61317)
   * sexy: "Qué es sexy ?" (#61317)
   * hot: "para tener una noche súper hot" (#73447)
---

## English idioms/collocations

    * full: "vivimos el presente a full" (#75882)
    * off: "la voz en off" (#71538)
    * footsie: "jugar footsie" ("to play footsie with sb" -- mit jmd füßeln) (#78122)
    * happily ever after: "casarse y vivir su happily ever after" (#78457)
    * in love: "ahora esta in love con este hombre" (#78457)
12a. English Idiomatic expressions / collocations
    * decision makers: "son verdaderas decision makers" (#45099)
    * behind the scenes: "echale un vistazo al behind the scenes" (#64443)
12b. Whole phrases in English, not necessarily idiomatic
    * "Happy party!" (#76085) (whole phrases?)
    * "Mix and match , la pareja ideal" (#62615)
    * "Wait , what !" (#76337)

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

Earlier Intents on Explanation
------------------------------
* Movies, Book names are not translated;
  audience living in the USA much more likely to know the stuff under their English names
* the rest of the named entities: even less expected to be translated?
* multiple clinics, hospitals and universities among the organizations (but that does not look that exciting)

Warum passieren beide?: "powerful socioeconomic and cultural forces", die Borrowings in Kontaktsi-
tuationen zwischen zwei Kulturen fördern(vgl. Zentella, 1990).
* Begriffe, die kulturelle Phänomene beschreiben, die in der Muttersprache und der dazugehörigen Kultur in der Form nicht existieren. Beispiele hierfür wären [kei/keike/keiki] “cake”, [yins/blu yines] “(blue)jeans” (vgl. Zentella, 1990) oder “la boila” (boiler).
* Ähnlichkeit in der phonologischen oder morphologischen Struktur eines Wortes. Deshalb wird das spanische Wort “libreria” (Buchladen) auf einmal im Spanischen auch für Bibliothek (auf Englisch “library”, auf Spanisch “biblioteca”) benutzt.
* einer der universellen Prinzipien des Sprachwandels – Sparsamkeit: das entlehnteWort ist kürzer. Deshalb wird zum Beispiel “florero” durch “vase” ersetzt (vgl. Zentella, 1990).
* Prestige: die Sprache oder Varietät, aus der entlehnt wird, wird als prestigeträchtiger angesehen.
* im konkreten Fall “Entlehnungen zwischen dem Spanischen und dem Englischen in den USA” können Anglizismen als neutralisierende Begriffe zwischen den ver-
schiedenen Varietäten des Spanischen dienen.
---

# Future work / What would I do differently today

* pattern is not ported for python3
    ** 3 years old work; pattern seemed a better choice at the time, today it is still not ported for python3
* non-exhaustive scrape because of irregular html; scrapy? it would have been an option back then as well, I just did not do my research properly
* generate more complete word lists
* better approach to language recognition?
  * `langid.py` detects language for whole snippet with certain probability
  * nltk.corpus.words.words() for English only
* automatic classification into categories
  * supervised learning
  * clustering

---

# Takeaways

* linguistics is awesome
* coding skills go a long way
* non-trivial problems

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
