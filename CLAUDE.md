# CLAUDE.md — Allenamento

@~/Documents/Claude/CLAUDE.md
<!-- ↑ eredita le regole personali: permessi, segreti, git, ritiro, comunicazione.
     I cassetti e il metodo: ~/Documents/Claude/Progetti.md -->

## Cos'è
Scheda di forza e corsa di Valerio, sempre la stessa ogni settimana, con la progressione
calcolata dal diario. Una pagina HTML statica pubblicata su GitHub Pages da usare dal telefono.

## Stack e comandi
- Un solo file, `index.html`: HTML, CSS e JavaScript senza dipendenze (font di sistema).
- Anteprima: si apre `index.html` nel browser.
- Online: https://valepaa.github.io/opepdxjd9o/ · repo `ValePaa/opepdxjd9o`, Pages dal ramo
  `main`. **Un push su `main` pubblica**: si fa solo quando Valerio lo chiede.

## Architettura in breve
- Quattro viste disegnate dal JavaScript (Oggi, Settimana, Progressi, Guida), con la barra in
  basso. All'apertura si vede sempre **Oggi**: la seduta del giorno già aperta.
- La scheda è fissa: `PLAN` dice quale seduta cade in quale giorno, `SESS` descrive le sedute di
  forza A, B, C (esercizi in coppie, e `PLATES` dove si cambiano i dischi), `EX` gli esercizi
  (serie, range `lo`–`hi`, attrezzo `eq`, varianti `lv`).
- `prescribe()` calcola l'obiettivo di una settimana dalle settimane prima nel diario: +1
  ripetizione, conferma, +5 kg, bottiglie nello zaino, variante più difficile, settimana leggera
  o passo indietro. Le corse con `qPlan()` (ripetute 4 → 6, poi test) e `lPlan()` (lungo +5 min,
  tetto in km a +10% sulla corsa più lunga dei 30 giorni). La regola: decisione 0002.
- I ritmi si calcolano con le formule VDOT di Daniels dal tempo sui 5 km (`VDOT_PROVV` finché
  non c'è il test).
- Il diario sta nel `localStorage` del browser (chiave `scheda-fc-2026`), con esporta/importa
  in JSON: non va mai nel repository. Le settimane si contano dal 2 novembre 2026. Le chiavi
  delle serie (`w1.A.gsq.1.r`, `.kg`), gli id degli esercizi e i test (`t5k1`…) non si
  rinominano: romperebbero i diari già salvati e la progressione. Per esercizio e settimana:
  `.lv` (variante usata), `.rir` (margine), `.dl` (settimana leggera). Corse: `w3.q.n`, `.reps`,
  `.test`, `.t5k`, `w3.l.pres`, `.min`, `.km`. I tempi (`.min`, `.t5k`) si scrivono
  `mm:ss` e si leggono con `parseDur()`. Le altre: `.ok` (serie spuntata), `done.w1.A` (seduta
  fatta), `lastExport`, `vdot`.

## Vincoli specifici
- Attrezzatura di Valerio: manubri regolabili fino a 25 kg per mano, coppia fissa da 3 kg,
  bilanciere da 16 kg con dischi aggiungibili, dischi 8 × 5 kg e 4 × 2,5 kg, panca piana,
  parallele, sbarra, rotella, zaino da 8,5 kg più bottiglie da 1,5 L, cyclette. I dischi si
  cambiano il meno possibile: martedì e mercoledì mai, sabato una volta sola, togliendo e basta.
  Un esercizio con i manubri si fa in coppia con uno che non li usa.
- Esercizi che Valerio non vuole: salti (jump squat, salto su una gamba), hip thrust su panca,
  leg curl con asciugamano, push-up con i piedi sulla panca, rollout con il bilanciere.
- Ogni scelta di programmazione cita una fonte nella sezione «Le evidenze»; una fonte nuova si
  verifica prima di scriverla.
- La pagina contiene dati di salute di Valerio ed è pubblica per sua scelta: perché, in
  `docs/decisioni/0001-pubblicazione-su-github-pages-con-indirizzo.md`.

## Permessi
Claude PUÒ creare/modificare file in questa cartella.
