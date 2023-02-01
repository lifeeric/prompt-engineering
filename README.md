
# Prompt Engineeering GPT-3
Cheat sheet of GPT-3 Prompt engineering



## text-davinci-002
Text-davinci-002 is Instruct Model which is fine-tune to follow the instruction in order to give you the result, so we'll be looking at a few examples:

1. [Summarization/Paraphrasing](#summarization/paraphrasing)
2. [Classification](#)
3. [Rewriting](#rewriting)
4. [Keyword extraction, named entity recognition, dates, etc..](#Keyword-extraction-named-entity-recognition-date)



#### 1) Summarization/Paraphrasing
let's start with the first task which is summarization or paraphrasing. we need to give an imperative verb (Command, request word), so I'll just write `summarize` at the beginning which tells what to do with the instruction, and then put the actual article. 

if you capitalize something, it is a different set of tokens which kinda tells the model like pay attention to it, it's not a normal language and not a part of the article. so we will aslo  add `ARTICLE` before the article.

and at the end just write `SUMMARY:`

***Note:*** we need to turn the temperature down to  0(zero), so zero makes the model deterministic which means we'll get the same output every time.

Syntax Example:

```
Summarize the following article:

ARTICLE
<Your article here>

SUMMARY:
```
<br />



Real Example:
```
Summarize the following article:

ARTICLE

The Irish Bee Conservation Project is a charitable organisation in Ireland that seeks to conserve all native Irish bee species. It has four "pillars of support" in its work: providing habitats, increasing biodiversity, holding education events and performing research into the decline of bee species.[1] Species of bee in Ireland include the honeybee (Apis mellifera), 21 species of bumblebee and 78 species of solitary bee.[2]

History

The Irish Bee Conservation Project (IBCP) grew out of a research project looking at honeybees and the Varroa mite and was formed in 2019 as a not for profit private company limited by guarantee. That same year it designed and installed its first honeybee "lodges" in Fota Wildlife Park, County Cork.[1]

In 2021, the Irish Bee Conservation Project registered as a charity with the Charities Regulator of Ireland.[3]

SUMMARY:

```

***OUTPUT:***
```
The Irish Bee Conservation Project is a charitable organisation that seeks to conserve all native Irish bee species. It has four "pillars of support" in its work: providing habitats, increasing biodiversity, holding education events and performing research into the decline of bee species. The organisation was formed in 2019 and registered as a charity in 2021.
```

*** sometimes the temperature no longer has the same impact. and you'll get different output each time.***


You can modify the instruction with adjectives like `very concisely` and `CONCISE`, so it will activate the different part of GPT-3 model, it says what `CONCISE` mean, make it smaller.
Syntax Example:

```
Summarize the following article very concisely:

ARTICLE
<Your article here>

CONCISE SUMMARY:
```
You'll get shorter output.


**But if you increase the temperature, you also need to remove the word `CONSICE` and `very concisely` in order to get a completely different output.**




### 3) Rewrite
rewrite an article to be more interesting for reader. 

Syntax Example:

```
Rewrite the following Wikipedia article so that it's more interesting for an online news article:

ARTICLE
<Your article here>

REWRITE TO BE INTERESTING:
```

Real Example:
```
Rewrite the following Wikipedia article so that it's more interesting for an online news article:  

ARTICLE  
The Irish Bee Conservation Project is a charitable organisation in Ireland that seeks to conserve all native Irish bee species. It has four "pillars of support" in its work: providing habitats, increasing biodiversity, holding education events and performing research into the decline of bee species.[1] Species of bee in Ireland include the honeybee (Apis mellifera), 21 species of bumblebee and 78 species of solitary bee.[2]  History  The Irish Bee Conservation Project (IBCP) grew out of a research project looking at honeybees and the Varroa mite and was formed in 2019 as a not for profit private company limited by guarantee. That same year it designed and installed its first honeybee "lodges" in Fota Wildlife Park, County Cork.[1]  In 2021, the Irish Bee Conservation Project registered as a charity with the Charities Regulator of Ireland.[3]  

REWRITE  TO BE INTERESTING:
```

***OUTPUT***
```
  
The Irish Bee Conservation Project (IBCP) is a charitable organisation in Ireland that seeks to conserve all native Irish bee species. It has four "pillars of support" in its work: providing habitats, increasing biodiversity, holding education events and performing research into the decline of bee species.  

The IBCP was formed in 2019 as a not for profit private company limited by guarantee, and registered as a charity with the Charities Regulator of Ireland in 2021. The organisation's work is based on four pillars: providing habitats, increasing biodiversity, holding education events and performing research into the decline of bee species.  

The IBCP's first project was to design and install honeybee "lodges" in Fota Wildlife Park, County Cork. The lodges provide a habitat for wild bees, and also help to increase biodiversity by providing a home for a range of bee species. The IBCP also holds education events to raise awareness of the importance of bees, and performs research into the decline of bee populations.  

The IBCP's work is important in conserving Ireland's native bee species and helping to reverse the decline of bee populations.
```

<br />

***For Children***
it will simplify the languge for the children to be understandable
```
Rewrite the following Wikipedia article so that it's more ccessible to children:

ARTICLE
<Your article here>

REWRITE FOR CHILDREN:
```
***OUTPUT***
```
The Irish Bee Conservation Project is a charity that helps bees in Ireland. It has four parts to its work: providing habitats, increasing biodiversity, holding education events and researching why bee populations are declining.  

There are three different types of bees in Ireland- the honeybee, the bumblebee and the solitary bee.  

The Irish Bee Conservation Project started in 2019 when some people decided they wanted to help bees. That same year, they designed and installed the first bee habitats in Fota Wildlife Park.  

In 2021, the Irish Bee Conservation Project became an official charity. This means that it is registered with the Charities Regulator of Ireland.
```

<br >

***You can also translate it into a different language like German, Spanish..***

```
Rewrite the following Wikipedia article in german:

ARTICLE
<Your article here>

REWRITE IN GERMAN:
```

***OUTPUT***
```
Das Irish Bee Conservation Project ist eine gemeinnützige Organisation in Irland, die sich der Erhaltung aller in Irland vorkommenden Bienenarten widmet. Es hat vier Säulen in seiner Arbeit: die Bereitstellung von Lebensräumen, die Erhöhung der Artenvielfalt, die Durchführung von Bildungsveranstaltungen und die Durchführung von Forschungen zum Rückgang der Bienenarten. [1] Arten von Bienen in Irland umfassen die Honigbiene (Apis mellifera), 21 Arten von Hummeln und 78 Arten von Einsiedlerbienen. [2]  

Geschichte  Das Irish Bee Conservation Project (IBCP) entstand aus einem Forschungsprojekt zu Honigbienen und der Varroamilbe und wurde 2019 als gemeinnützige Gesellschaft mit beschränkter Haftung
```

I have no idea what it's writing :)

**Also try for BBC pidgin**
Syntax Example:
```
Rewrite the following Wikipedia article in West African Pidgin:

ARTICLE
<Your article here>

REWRITE IN PIDGIN:
```
***OUTPUT***

```
De Irish Bee Conservation Project na im wan charity organisation wey dey Ireland wey dey try conserves all de native Irish bee species. E get four "pillars of support" for e work: Providing habitats, increasing biodiversity, holding education events and performing research into de decline of bee species.1 Species of bee wey dey Ireland na honeybee (Apis mellifera), 21 species of bumblebee and 78 species of solitary bee.2  

History  De Irish Bee Conservation Project (IBCP) grow from wan research project wey dey look into honeybees and de Varroa mite and e form in 2019 as wan not for profit private company wey dey limited by guarantee. Dat same year, e design and install e first honeybee "lodges" for Fota Wildlife Park, County Cork.1  

In 2021, de Irish Bee Conservation Project register as wan charity with de Charities Regulator of Ireland.3
```
it converts some words like `the` to `de` and so on...


### 4) Keyword extraction, named entity recognition, dates
 let's extract named entity and dates

Syntax Example:

```
Perform NER and date extraction from the following article:

ARTICLE
<Your article here>

LIST ALL NAMED ENTITIES AND DATES:
```

Real Example:

```
Perform NER and date extractio from the following article:  ARTICLE  The Irish Bee Conservation Project is a charitable organisation in Ireland that seeks to conserve all native Irish bee species. It has four "pillars of support" in its work: providing habitats, increasing biodiversity, holding education events and performing research into the decline of bee species.[1] Species of bee in Ireland include the honeybee (Apis mellifera), 21 species of bumblebee and 78 species of solitary bee.[2]  History  The Irish Bee Conservation Project (IBCP) grew out of a research project looking at honeybees and the Varroa mite and was formed in 2019 as a not for profit private company limited by guarantee. That same year it designed and installed its first honeybee "lodges" in Fota Wildlife Park, County Cork.[1]  In 2021, the Irish Bee Conservation Project registered as a charity with the Charities Regulator of Ireland.[3]  LIST ALL NAMED ENTITIES AND DATES:
```

***OUTPUT***
```
The Irish Bee Conservation Project, Ireland, Apis mellifera, Varroa mite, 2019, Fota Wildlife Park, County Cork, 2021
```
