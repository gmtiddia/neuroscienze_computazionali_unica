# Sito del gruppo Neuroscienze Computazionali UniCA
 
Sito web del gruppo di ricerca in neuroscienze computazionali (Università di Cagliari, Dipartimento di Fisica).
 
**Indirizzo del sito:** https://gmtiddia.github.io/neuroscienze_computazionali_unica
 
Il sito è costruito con [Jekyll](https://jekyllrb.com/) a partire dal template [Academic Pages](https://github.com/academicpages/academicpages.github.io) e pubblicato con GitHub Pages tramite GitHub Actions. Questo file spiega a chi modera la repo come aggiornare i contenuti.
 
## Come funziona in breve
 
- I contenuti sono file di testo (Markdown e YAML) in questa repo.
- Ogni commit sul branch `main` avvia automaticamente la pubblicazione. Dopo uno o due minuti la modifica è online.
- Lo stato della pubblicazione si controlla nella scheda **Actions**: una spunta verde significa che il sito è aggiornato, una croce rossa che c'è un errore (vedi la sezione "Risoluzione dei problemi").
## Come modificare un file
 
**Dal browser (il metodo più semplice):**
 
1. Apri il file su GitHub e clicca sull'icona a matita (*Edit this file*).
2. Modifica il testo.
3. Clicca *Commit changes*. Per modifiche rilevanti scegli *Create a new branch and start a pull request* e fai approvare la modifica da un altro moderatore.
**Da computer, con anteprima locale (facoltativa):**
 
```bash
git clone https://github.com/gmtiddia/neuroscienze_computazionali_unica.git
cd neuroscienze_computazionali_unica
bundle install
bundle exec jekyll serve
```
 
Il sito locale è su `http://localhost:4000/neuroscienze_computazionali_unica/`. Servono Ruby e Bundler installati. Le modifiche a `_config.yml` richiedono il riavvio di `jekyll serve`.
 
## Dove si trova cosa
 
| Cosa vuoi modificare | File o cartella |
|---|---|
| Home page | `_pages/about.md` |
| Linee di ricerca | `_pages/research.md` |
| Software (NEST GPU e altri) | `_pages/software.md` |
| Contatti | `_pages/contacts.md` |
| Membri | `_data/members.yml` (la pagina è `_pages/team.md`) |
| News | `_posts/` |
| Pubblicazioni | `_publications/` |
| Voci del menu | `_data/navigation.yml` |
| Titolo, descrizione, logo, link del gruppo | `_config.yml` |
| Immagini | `images/` |
| PDF e altri file scaricabili | `files/` |
 
Non c'è bisogno di toccare `_layouts/`, `_includes/`, `_sass/` e `assets/`: contengono la grafica del template.
 
## Aggiungere una news
 
Crea un file in `_posts/` con nome `AAAA-MM-GG-titolo-breve.md`, per esempio `2026-12-01-articolo-accettato.md`:
 
```markdown
---
title: "Titolo della news"
date: 2026-12-01
---
 
Testo della news in Markdown. Link, elenchi e immagini funzionano come in un normale file Markdown.
```
 
Attenzione alla data: con `future: false` in `_config.yml`, le news con data futura non vengono mostrate finché quel giorno non arriva.
 
## Aggiungere o modificare un membro
 
Apri `_data/members.yml` e aggiungi una voce copiando la struttura di quelle esistenti. I campi sono:
 
```yaml
- name: "Nome Cognome"
  role: "Dottorando"
  photo: "/images/team/nome-cognome.jpg"
  bio: "Breve descrizione (una o due righe)."
  orcid: "0000-0000-0000-0000"
  alumni: false
```
 
- Per spostare una persona tra gli ex membri basta mettere `alumni: true`.
- Carica la foto in `images/team/` (circa 400 px di larghezza, formato JPG, peso contenuto).
- Prima di pubblicare foto e dati personali, assicurati di avere il consenso della persona.
- Il rientro a capo e gli apici contano: se una stringa contiene due punti o virgolette, mettila tra virgolette doppie.
## Aggiungere una pubblicazione
 
Ogni pubblicazione è un file in `_publications/`, con nome `AAAA-MM-GG-titolo-breve.md`:
 
```markdown
---
title: "Titolo dell'articolo"
collection: publications
category: manuscripts
permalink: /publication/2026-12-01-titolo-breve
date: 2026-12-01
venue: "Nome della rivista"
paperurl: "https://doi.org/..."
citation: "Cognome N., Cognome N., Titolo, Rivista, anno."
---
```
 
Il campo `category` deve essere **esattamente** uno di questi, altrimenti la pubblicazione non compare nella pagina:
 
| Valore | Sezione |
|---|---|
| `books` | Libri |
| `manuscripts` | Articoli su rivista |
| `conferences` | Atti di convegno |
 
Le chiavi si definiscono in `_config.yml` alla voce `publication_category`; si possono tradurre i titoli (`title:`), ma non le chiavi.
 
**Importare molte pubblicazioni da BibTeX:** nella cartella `markdown_generator/` ci sono gli script per generare i file di `_publications/` da un file `.bib`. Le istruzioni sono in `markdown_generator/README.md`. Dopo l'esecuzione controlla sempre i file generati prima di fare commit.
 
## Aggiungere immagini e file
 
- Immagini in `images/`, ridimensionate prima del caricamento (le foto delle persone a circa 400 px).
- Inseriscile in una pagina con il testo alternativo:
```markdown
![Descrizione dell'immagine]({{ '/images/nome.png' | relative_url }})
```
 
- File scaricabili (PDF, dataset piccoli) in `files/`, con link `{{ '/files/nome.pdf' | relative_url }}`.
- Per dati e software di grandi dimensioni usa repository dedicate o Zenodo e inserisci il link.
## Modificare il menu
 
Le voci sono in `_data/navigation.yml`. Ogni voce ha un `title` e un `url`; l'`url` deve coincidere con il `permalink` indicato nell'intestazione (front matter) della pagina corrispondente in `_pages/`.
 
| Voce | Permalink |
|---|---|
| Ricerca | `/research/` |
| Pubblicazioni | `/publications/` |
| Membri | `/team/` |
| News | `/year-archive/` |
| Software | `/software/` |
| Contatti | `/contact/` |
 
## Aggiungere una nuova pagina
 
1. Crea un file in `_pages/`, per esempio `opportunita.md`:
```markdown
---
permalink: /opportunita/
title: "Opportunità"
author_profile: false
---
 
Contenuto della pagina.
```
 
2. Aggiungi la voce in `_data/navigation.yml`:
```yaml
- title: "Opportunità"
  url: /opportunita/
```
 
## Modifiche che richiedono più attenzione
 
- **`_config.yml`**: influisce su tutto il sito. In particolare non modificare `url` e `baseurl`, a meno che il sito non venga spostato (per esempio in un'organizzazione GitHub o su un dominio personalizzato).
- **`.github/workflows/jekyll.yml`**: contiene la procedura di pubblicazione. Se ti serve modificarlo da terminale, il token di accesso personale deve avere lo scope `workflow`; in alternativa modifica il file dal browser.
- **Impostazioni di Pages**: in *Settings → Pages* la sorgente deve restare **GitHub Actions**.
## Risoluzione dei problemi
 
**La pubblicazione fallisce (croce rossa in Actions).** Apri l'esecuzione e leggi le ultime righe del log dello step di build. Gli errori più frequenti sono un front matter scritto male (`YAML Exception`), virgolette non chiuse in un file `.yml` o un file che ne richiama un altro che è stato eliminato.
 
**Una pubblicazione o una news non compare.**
 
- Controlla che `category` sia uno tra `books`, `manuscripts`, `conferences`.
- Controlla che la `date` non sia nel futuro.
- Controlla che il file sia nella cartella giusta e che l'intestazione inizi e finisca con `---`.
**Stile o immagini non si caricano.** Verifica che `baseurl` in `_config.yml` sia `"/neuroscienze_computazionali_unica"` e che i link a immagini e file usino `relative_url`.
 
**Una voce del menu porta a una pagina 404.** L'`url` in `_data/navigation.yml` non coincide con il `permalink` della pagina.
 
## Buone pratiche per chi modera
 
- Fai commit piccoli e con un messaggio chiaro (per esempio "Aggiunge news convegno novembre 2026").
- Per modifiche strutturali usa un branch e una pull request, così un altro moderatore può controllare l'anteprima e il risultato in Actions.
- Prima di pubblicare dati personali (foto, email, ORCID) di una persona, verifica che abbia dato il consenso.
- Usa sempre il testo alternativo per le immagini.
- Se un membro lascia il gruppo, passa la sua voce in `alumni: true` invece di cancellarla.
## Contatti
 
Per problemi con il sito apri una *issue* in questa repo.
 
## Crediti e licenza
 
Il sito usa il template [Academic Pages](https://github.com/academicpages/academicpages.github.io), derivato da [Minimal Mistakes](https://github.com/mmistakes/minimal-mistakes). Per le licenze dei template fai riferimento al file `LICENSE`.
