# Calcolo Pensione Carabinieri

Simulatore **non ufficiale** del trattamento di quiescenza per il personale dell'Arma dei Carabinieri.
Single-file (`index.html`), nessuna dipendenza, nessun dato che lascia il browser.

## Cosa calcola
- **Pensione** col sistema misto militare: quota retributiva (art. 54 DPR 1092/1973, aliquota 2,44%) + quota contributiva (montante × coefficiente di trasformazione 2025-2026); rileva automaticamente contributivo puro / misto in base alla data di arruolamento.
- **Buonuscita (IBU)** ex-ENPAS: 1/12 dell'80% della retribuzione utile per anno.
- **Indennità di ausiliaria** (art. 992 COM): 50% della differenza pensione / pari grado in servizio.
- **Scenari a confronto**: anticipata / limite d'età / permanenza.

Copre tutti i ruoli (Appuntati e Carabinieri, Sovrintendenti, Ispettori, Ufficiali) con limiti d'età per grado.

## Riferimenti normativi
DPR 1092/1973 art. 54 · L. 335/1995 · D.Lgs. 66/2010 (COM) artt. 928, 992 · Corte dei Conti SS.RR. 2021 / Circ. INPS 107/2021 · DM 20/11/2024 (coefficienti) · L. di Bilancio 2026.

## Dati da rifinire prima della pubblicazione
1. **Coefficienti di trasformazione** — 9 valori su 15 sono confermati da fonti multiple; 6 (età 58, 59, 60, 68, 69, 70) sono ricostruiti dalla tabella 2023-2024 (scostamento < 0,03%). Sostituire con i valori esatti del DM 20/11/2024 se si vuole precisione assoluta.
2. **Base pensionabile per grado** — i valori in `GRADI[]` sono stime 2026 indicative; l'utente inserisce comunque il proprio imponibile reale dal cedolino NoiPA / mod. PA04.

## Deploy su GitHub Pages
```bash
git remote add origin https://github.com/erold90/pensione-carabinieri.git
git push -u origin main
# Settings → Pages → branch main / root  →  live su erold90.github.io/pensione-carabinieri
```
Per un dominio `.dev` custom: i TLD `.dev` sono in HSTS preload e **richiedono HTTPS** (GitHub Pages lo fornisce). Acquistare il dominio, aggiungere il record CNAME verso `erold90.github.io` e impostare il custom domain nelle Pages settings.
