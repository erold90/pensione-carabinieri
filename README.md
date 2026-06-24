# Calcolo Pensione Carabinieri

Simulatore **non ufficiale** del trattamento di quiescenza per il personale dell'Arma dei Carabinieri.
Single-file (`index.html`), nessuna dipendenza, nessun dato che lascia il browser.

## Cosa calcola
- **Pensione** col sistema misto militare: quota retributiva (art. 54 DPR 1092/1973, aliquota 2,44%) + quota contributiva (montante × coefficiente di trasformazione 2025-2026); rileva automaticamente contributivo puro / misto in base alla data di arruolamento.
- **Buonuscita (IBU)** ex-ENPAS: 1/12 dell'80% della retribuzione utile per anno.
- **Indennità di ausiliaria** (art. 992 COM): 50% della differenza pensione / pari grado in servizio.
- **Scenari a confronto**: anticipata / limite d'età / permanenza.
- **Import da file (client-side)**: Certificazione Unica PDF (legge il punto 18 «Imponibile pensionistico» via PDF.js) ed estratto conto INPS XML (anno di inizio servizio + imponibile). Nessun dato lascia il browser.

Copre tutti i ruoli (Appuntati e Carabinieri, Sovrintendenti, Ispettori, Ufficiali) con limiti d'età per grado.

> L'import della CU usa PDF.js da CDN: l'unico componente che richiede connessione (la libreria, non il file, che resta locale). I PDF-immagine/scansioni non sono leggibili. L'estratto conto INPS del comparto Difesa è spesso incompleto — il valore importato va sempre verificato.

## Riferimenti normativi
DPR 1092/1973 art. 54 · L. 335/1995 · D.Lgs. 66/2010 (COM) artt. 928, 992 · Corte dei Conti SS.RR. 2021 / Circ. INPS 107/2021 · DM 20/11/2024 (coefficienti) · L. di Bilancio 2026.

## Stato dei dati (rifinito)
1. **Coefficienti di trasformazione** — 10 valori su 15 confermati da fonti multiple (incluso il 60, limite d'età dei ruoli non-ufficiali); 5 (età 58, 59, 68, 69, 70) ricostruiti dalla tabella 2023-2024 × fattore di riduzione verificato, scostamento < 0,03% (≈ < 6 €/anno). Per precisione assoluta sostituire con i valori del DM 20/11/2024.
2. **Base pensionabile per grado** — `GRADI[]` ora usa il **parametro reale di grado × 195,50 €** (punto parametrale dal 1/1/2024, DPR 53/2025 · Allegato C Min. Difesa) come stipendio tabellare, più indennità pensionabile e assegno funzionale per la stima "a fine carriera". L'utente inserisce comunque il proprio imponibile reale dal cedolino NoiPA / mod. PA04.

## Deploy su GitHub Pages
```bash
git remote add origin https://github.com/erold90/pensione-carabinieri.git
git push -u origin main
# Settings → Pages → branch main / root  →  live su erold90.github.io/pensione-carabinieri
```
Per un dominio `.dev` custom: i TLD `.dev` sono in HSTS preload e **richiedono HTTPS** (GitHub Pages lo fornisce). Acquistare il dominio, aggiungere il record CNAME verso `erold90.github.io` e impostare il custom domain nelle Pages settings.
