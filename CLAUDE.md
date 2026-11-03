# CLAUDE.md — Allenamento

@~/Documents/Claude/CLAUDE.md
<!-- ↑ eredita le regole personali: permessi, segreti, git, ritiro, comunicazione.
     I cassetti e il metodo: ~/Documents/Claude/Progetti.md -->

## Cos'è
Scheda di forza e corsa di Valerio (8 settimane), una pagina HTML statica pubblicata su GitHub
Pages da usare dal telefono.

## Stack e comandi
- Un solo file, `index.html`: HTML, CSS e JavaScript senza dipendenze (font da Google Fonts).
- Anteprima: si apre `index.html` nel browser.
- Online: https://valepaa.github.io/opepdxjd9o/ · repo `ValePaa/opepdxjd9o`, Pages dal ramo
  `main`. **Un push su `main` pubblica**: si fa solo quando Valerio lo chiede.

## Architettura in breve
- Quattro viste disegnate dal JavaScript (Oggi, Settimana, Ritmi, Guida), con la barra in basso.
  All'apertura si vede sempre **Oggi**: la seduta del giorno già aperta.
- `PLAN` dice quali sedute cadono in quale giorno; `SMETA` descrive le sedute di forza A, B, C.
- Il programma è nei dati in fondo allo script: `A`, `B`, `C` (sedute di forza, serie per
  settimana in `s`, ripetizioni `r1` per le settimane 1–4 e `r2` per le 5–8) e `RUN` (corse).
- I ritmi si calcolano con le formule VDOT di Daniels dal tempo sui 5 km (`VDOT_PROVV` finché
  non c'è il test).
- Il diario sta nel `localStorage` del browser (chiave `scheda-fc-2026`), con esporta/importa
  in JSON: non va mai nel repository. Le chiavi delle serie (`w1.A.bss.1.r`, `.kg`) e dei test
  (`t5k1`, `tpull1`…) non si rinominano: romperebbero i diari già salvati. Le altre chiavi:
  `.ok` (serie spuntata), `done.w1.A` (seduta fatta), `ready.AAAA-MM-GG` e `sick.…` (prontezza),
  `lastExport`.

## Vincoli specifici
- Attrezzatura di Valerio: manubri regolabili fino a 25 kg per mano, coppia fissa da 3 kg,
  bilanciere da 16 kg, panca piana, parallele, sbarra, zaino da 8,5 kg, cyclette. **I manubri
  restano a 25 + 25**: nessun esercizio richiede di cambiare i dischi.
- Ogni scelta di programmazione cita una fonte nella sezione «Le evidenze»; una fonte nuova si
  verifica prima di scriverla.
- La pagina contiene dati di salute di Valerio ed è pubblica per sua scelta: perché, in
  `docs/decisioni/0001-pubblicazione-su-github-pages-con-indirizzo.md`.

## Permessi
Claude PUÒ creare/modificare file in questa cartella.
