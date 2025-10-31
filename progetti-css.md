# Laboratorio di Tecnologie Web (CSS III)

Queste specifiche definiscono i requisiti comuni e quelli specifici per tre mini‑progetti da sviluppare nella giornata di laboratorio. 

## Requisiti comuni per tutti i progetti

I siti web dovranno essere belli ed originali

### Layout

Per il layout è necessario usare o `flex` o le utility dai framework seguenti (tramite CDN)

* [Bootstrap](https://getbootstrap.com/)
* [Tailwind](https://tailwindcss.com/docs/installation/play-cdn)

Utilizzare i tag HTML e.g., `<header>`, `<nav>`, `<main>`, `<footer>`, `<sidebar>`

### Variabili e calcoli: 

definire in :root un set di CSS Custom Properties (es. --space-1, --radius, --maxw, --brand, --text, --bg) e usare calc() per larghezze, spaziature, aspect‑ratio.

### Responsive
Creare un design mobile‑first, con almeno 3 breakpoints (es. 480px, 768px, 1024px). Usare unità relative (rem, %, vw, ch). [MDN documentation](https://developer.mozilla.org/en-US/docs/Learn_web_development/Core/CSS_layout/Responsive_Design)

### Animazioni
almeno 2 animazioni (e.g., @keyframes su hero/banner, reveal on hover, indicatori attivi in nav, transizioni su card). Includere media query @media (prefers-reduced-motion: reduce) per offrire una versione senza animazioni. [MDN documentation](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_animations/Using_CSS_animations)

### Tipografia & colori
scala tipografica con variabili e usa una Palette con almeno 3 livelli (primario, neutri, stato). Prevedere dark mode con @media (prefers-color-scheme: dark).

Per qualche spunto, guarda su [Coolors.co](https://coolors.co/)

### accessibilità a11y: 

HTML semantico (landmarks: header, nav, main, aside, footer), focus visibile, testo alternativo alle immagini, skip link all’inizio della pagina. [MDN documentation](https://developer.mozilla.org/en-US/docs/Web/Accessibility)

## Struttura repo:
```
-progetto
  -assets/
    -css/     # dividere file con variabili e file con stili
    -imgs/    # Se ci sono delle immaigni
    -fonts/   # Se scaricati salvarli qui oppure usare Google Fonts
  -index.html # Pagina principale
  ...
```

## Qualità del codice
HTML valido, nessun inline style, non usare `!important` classi coerenti, commenti di sezione.

## Consegna
Solo il progetto C è da consegnare per poter arrivare ad avere **fino** ad un punto in più durante la discussione del progetto. Il migliore verrà scelto come template per il sito web delle esercitazioni dei prossimi anni.

Se scegliete di fare i progetti A e B potete comunque consegnarli, se fatti bene ne terremo conto durante la discussione del progetto.

**Consega valida fino alle 23:59 del giorno 3 Novembre 2025**. 

Zip della cartella, README.md con: struttura, scelte di design, librerie usate, crediti immagini/licenze, checklist di conformità da consegnare a `gianmarco.spinaci2 [at] unibo.it`

### Checklist di accettazione

* Nessun JavaScript
* Layout con Flex/Bootstrap (preferiti) o Tailwind
* Variabili CSS + calc() usati
* almeno 2 animazioni
* 3 breakpoint mobile‑first
* A11y: semantica, alt, contrasto, focus, skip link

# Progetto A — Sito personale multi‑pagina

**Obiettivo:** creare un sito personale con almeno 3 sezioni.

* `/index.html` (home con hero e call to action + navigazione alle 3 sezioni tramite navbar)

* `/bio.html` file contenente la biografia 
  * foto profilo (anche placeholder va bene)
  * bio testuale
  * timeline delle esperienze/studi
* `/interessi.html` pagina dei propri interessi 
  * usare categorie/tag
  * descrizione
  * aggiungere link esterni
* `/progetti.html` pagina dei Lavori/Progetti 
  * griglia di card con immagini, titolo, descrizione breve, e link esterni se presenti
  * card responsive (Flex o utility).

## Altri componenti obbligatori:
* Navbar coerente su tutte le pagine 
* Footer con contatti/crediti (link social con icone solo via font/svg inline, niente JS).

### Animazioni suggerite
* Keyframe “fade‑in + slide” per hero
* Hover su card (elevazione/ombra + trasformazione lieve)

### Contenuti minimi
* Bio: ≥ 120 parole, 1 foto (non personale, non è richiesta)
* Interessi: ≥ 3 interessi, ognuno con 1 link
* Progetti: ≥ 6 card

# Progetto B — Blog personale (o ecommerce)

**Obiettivo:** creare un piccolo blog statico.

* `/index.html` pagina contenente:
  - la lista di post con anteprime, date, tag
  - le categorie

* `/posts/<slug>.html` una pagina per ogni blog post con:
  - titolo
  - categorie
  - contenuto
  - call to action
  - immagini
  - etc

* `/about.html`

## Altri componenti obbligatori
- Indice con filtri solo CSS (checkbox/radio) per tag/categorie: mostra/nasconde card post con selettori :checked + ….

- Breadcrumb nei singoli post.

- Sezione “Post correlati” (scelta manuale con link interni).

- Paginazione a link statici (es. /page/2/ anche se mock).

### Animazioni suggerite
- Transizione sui link (colore/underline animata)

- Evidenziazione del tag attivo con keyframe pulsante leggero

- Card “in evidenza” con badge animato via @keyframes.


### Contenuti minimi
5 post (≥ 300 parole ciascuno), ciascuno con: titolo, data, tag, immagini (anche placeholder)

# Progetto C — Sito delle esercitazioni di TW
**Obiettivo:** progettare il sito che ospita le esercitazioni di Tecnologie Web. Deve unire la struttura di due siti di riferimento [[1](https://site212248.tw.cs.unibo.it/), [2](https://gspinaci.dev/esercizi_tw/)] mantenendo:

- Livello 1: macro‑temi (HTML, CSS, JAVASCRIPT)

- Livello 2: lista esercitazioni per tema (titolo, difficoltà, prerequisiti, durata stimata)

- Livello 3: pagina esercitazione con traccia, materiali e soluzione


`/index.html` panoramica con griglia dei macro‑temi (card)

`/tema/<slug>.html` — elenco esercizi del tema (tabella/card)

`/es/<slug>.html` — singolo esercizio

`/risorse.html` — link utili, linee guida, template

`/about.html` — scopi del corso, crediti

`/chat.html` - l'interfaccia di una chat e.g., ChatGPT (non dovrà essere interattiva, è necessario solo il design)

### Componenti obbligatori
- Sidebar sticky (o breadcrumb) per navigazione tra Livello 1–3.

- tag con caption e scope per le liste esercizi.

- Badge difficoltà (es. base, medio, avanzato) con colori da variabili.

- Box “Materiali”: link a PDF/immagini/zip (mock).

- Callout info/warning/success via classi utility.

- Aggiungere il proprio nome tra i crediti del footer

### Animazioni suggerite
- Evidenziazione della card al focus/hover

- Micro‑animazione del badge attivo nella sidebar


# Idee aggiuntive opzionali
- Licenze & crediti: sezione dedicata nel footer.

- Component library: piccola pagina con componenti riutilizzabili (bottoni, card, callout) documentati.

- Modalità “alto contrasto” (toggle CSS‑only via checkbox hack).

- Layout stampabile del CV nel Progetto A (pagina dedicata cv.html).

- Glossario nel Progetto C con definizioni (lista alfabetica, ancore locali).

- Pagina 404 statica personalizzata.

- Schede “progress” con puro CSS (stati completato/in corso/non iniziato) per le esercitazioni.
