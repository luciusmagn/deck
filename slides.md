# gjk.cat

---

<img src="/cat.png">

---

- systém na správu studijních materiálů
- založený na statickém generátoru `mdbook` a napsaný v Rustu
- vytváří hierarchi učitelů, předmětů, materiálů a tagů pomocí `gitu` a metadat v jazyce TOML

---

- [gjk.cat](https://gjk.cat/)
- [it.gjk.cat](https://it.gjk.cat/)
- [příklad předmětu](https://it.gjk.cat/subjects/unix/subject.html)
- [příklad materiálu](https://it.gjk.cat/subjects/python/datove_typy.html)
  - [zdroj](https://paste.merkoba.com/1590099286-suzase-2) 
- [karta učitele](https://it.gjk.cat/teachers.html#dawidkubis)
- [přehled tagů](https://it.gjk.cat/tags.html)

---

---

### Karta učitele

```toml
jmeno = "Lukáš Hozda"
email = "luk.hozda@gmail.com"
username = "magnusi"

bio = """
### Mauris posuere libero dui
Lorem ipsum dolor sit amet, consectetur adipiscing elit.
Sed lacinia hendrerit placerat.[1]

### Sed in tellus tincidunt, molestie libero vel,
semper mi. Praesent lacus felis, `aliquam` in tempor vel,
fringilla eget dui. Quisque *tristique* pulvinar fringilla.

[1]: <https://www.lipsum.com/feed/html>
"""
```

---

### Hlavička předmětu

```toml
nazev = "Programovací jazyk Python"
zodpovedna_osoba = "Dawid J. Kubis"
bio = "V tomto předmětu se učí Python"

+++
```

---

### Hlavička materiálu

```toml
nazev = "Datové typy"
tagy = ["python", "typy"]
+++
```

---

## Výhody

- rychlé, úsporné řešení
  - funkcionalita zdarma
- git, Markdown
- flexibilní (integrace s `mdbook` ekosystémem)
- výstupem je statický web

---

## Nevýhody

- některé části `mdbook` ekosystému jsou ještě v rané fázi vývoje
- git, Markdown
- vyžaduje základní technickou znalost

---

# Otázky k obhajobě

---

### 1. Jakým způsobem je aplikace připravena na rozšiřování o další vstupní a výstupní formáty? Je aplikace modulární a umožňuje snadnou změnu šablon?

- velmi modulární
- agnostický vůči programovacím jazykům/technologiím
- cat-prep může být pouze jedním z mnoha využitých preprocessorů
- výstupy musí respektovat markdown

---

### 2. Není náročné přispívat do obsahu pro uživatele, kteří neumí pracovat se systémem Git, či neznají Markdown?

- je to náročnější -> Github aplikace?
- cílený spíš na techničtější obory
- Markdown není až zas tak složitý a stává se stále víc "mainstreamový"

---

### 3. Jak funguje v zadání a dokumentaci popisovaný playground pro Rust? V semestrální práci se nám nepodařilo najít žádnou ukázku.

- prostřednictvím modulu `links`

---

### 4. Ve některých předmětech je často potřeba, aby bylo v zápiscích možné používat matematické formule? Jak byste aplikaci upravil, aby s matematickým zápisem dokázala pracovat?

- mdbook má podporu pro MathJax zabudovanou

---

### 5. Nepřemýšlel autor nad příspěvkem do, dle jeho slov špatně funkčních, rendererů?

- gopher
- komplexita
- semi-RFC proces

---

### Generování PDF/EPUB

- `mdbook` cílí na generování PDF pomocí tisku
- `mdbook-epub`, `mdbook-latex`
