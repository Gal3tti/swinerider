# 🐗 Swine Rider — 3D Print Catalogue

Sito vetrina statico per il catalogo di stampe 3D, pubblicato tramite **GitHub Pages**.  
Nessun backend, nessun database: tutto si basa su un file CSV e una cartella di immagini.

---

## Struttura della repository

```
swine-rider/
│
├── index.html            → Il sito (non modificare)
├── catalogue.csv         → Il catalogo delle miniature
├── build_catalogue.py    → Script per generare/aggiornare il CSV automaticamente
├── README.md             → Questo file
│
└── images/
    ├── ABR_Aboleth_40_003.jpg
    ├── ABR_Aboleth_50_005.jpg
    ├── ABR_Balhannoth_40_001.jpg
    └── ...
```

---

## Formato del nome file immagine

Ogni immagine deve seguire questo schema:

```
PREFISSO_NomeCreatura_BaseMM_Variante.jpg
```

| Parte | Descrizione | Esempio |
|---|---|---|
| `PREFISSO` | Categoria (lettere maiuscole) | `ABR` |
| `NomeCreatura` | Nome della miniatura | `Aboleth` |
| `BaseMM` | Diametro della base in mm | `40` |
| `Variante` | Numero scultura/variante | `003` |

**Esempio completo:** `ABR_Aboleth_40_003.jpg`

> Sono supportati i formati `.jpg`, `.jpeg`, `.png`, `.webp`

---

## Formato del CSV

Il file `catalogue.csv` contiene una riga per ogni miniatura:

```
code,name,base_mm,variant,file
ABR_Aboleth_40_003,Aboleth,40,003,ABR_Aboleth_40_003.jpg
ABR_Aboleth_50_005,Aboleth,50,005,ABR_Aboleth_50_005.jpg
ABR_Balhannoth_40_001,Balhannoth,40,001,ABR_Balhannoth_40_001.jpg
ABR_Beholder_40_002,Beholder,40,002,ABR_Beholder_40_002.jpg
```

| Colonna | Descrizione |
|---|---|
| `code` | Codice pezzo univoco (= nome file senza estensione) |
| `name` | Nome della creatura |
| `base_mm` | Diametro base in mm |
| `variant` | Numero variante |
| `file` | Nome file immagine con estensione |

---

## Aggiornare il catalogo

### Step 1 — Aggiungi le nuove immagini

Copia i nuovi file JPG nella cartella `images/` rispettando il formato del nome.

### Step 2 — Aggiorna il CSV

Aggiorna il .csv con i nuovi codici rispettando le regole definite all'inizio


### Step 3 — Carica su GitHub

**Con Git (consigliato per molte immagini):**

```bash
git add images/ catalogue.csv
git commit -m "Aggiunto nuovo lotto miniature"
git push
```

**Da browser GitHub:**

1. Vai nella repository
2. Clicca **"Add file" → "Upload files"**
3. Carica le nuove immagini nella cartella `images/`
4. Torna alla root e carica il `catalogue.csv` aggiornato
5. Clicca **"Commit changes"**

### Step 4 — Verifica il sito

Dopo 1–3 minuti il sito si aggiorna automaticamente.  
Se vedi ancora la versione precedente, forza il refresh con:

- **Windows/Linux:** `Ctrl + Shift + R`
- **Mac:** `Cmd + Shift + R`

---

## Limiti GitHub Pages (piano gratuito)

| Voce | Limite |
|---|---|
| Dimensione repository | 1 GB consigliato |
| Banda mensile | 100 GB |
| Singolo file | max 100 MB |

Con immagini da ~300 KB si possono gestire comodamente **2.000+ miniature** senza ottimizzazioni.

---

## Link utili

- 🌐 **Sito live:** `https://gal3tti.github.io/swinerider/`
- 📁 **Repository:** `https://github.com/Gal3tti/swinerider`
- 📖 **GitHub Pages docs:** https://docs.github.com/pages
