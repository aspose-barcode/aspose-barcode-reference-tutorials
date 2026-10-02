---
category: general
date: 2026-08-12
description: Configura rapidamente il layout del codice a barre Databar in Python.
  Impara a impostare colonne, righe e a salvare le immagini con la libreria generatore
  di codici a barre.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- configure databar barcode layout
- Databar Expanded Stacked
- barcode generator Python
- set barcode columns
- set barcode rows
language: it
lastmod: 2026-08-12
og_description: Configura il layout del codice a barre Databar in Python per controllare
  colonne, righe e output dell'immagine. Segui questa guida per una soluzione pronta
  all'uso.
og_image_alt: Screenshot of a Databar Expanded Stacked barcode with custom column
  layout
og_title: Configura il layout del codice a barre Databar in Python – tutorial completo
schemas:
- author: Aspose
  dateModified: '2026-08-12'
  description: Configure Databar barcode layout in Python quickly. Learn to set columns,
    rows, and save images with the barcode generator library.
  headline: Configure Databar barcode layout in Python – step‑by‑step guide
  type: TechArticle
- description: Configure Databar barcode layout in Python quickly. Learn to set columns,
    rows, and save images with the barcode generator library.
  name: Configure Databar barcode layout in Python – step‑by‑step guide
  steps:
  - name: Import the required classes
    text: '```python from aspose.barcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat
      ```'
  - name: Create a barcode generator for Databar Expanded Stacked
    text: '```python # Initialize the generator with the desired symbology and value
      barcode_generator = BarcodeGenerator( EncodeTypes.DatabarExpandedStacked, "Databar
      Expanded Stacked long" ) ```'
  - name: Set the number of columns (horizontal layout)
    text: '```python # Configure the layout to use 4 columns barcode_generator.parameters.barcode.data_bar.columns
      = 4 ```'
  - name: Save the barcode image with the column layout
    text: '```python # Save the image as a PNG file barcode_generator.save("output/ExpandedCols4.png",
      BarCodeImageFormat.Png) ```'
  - name: Create a second generator for the same barcode type (row layout)
    text: If you prefer a vertical stack, you work with rows instead of columns. The
      code below re‑uses the same value but creates a fresh `BarcodeGenerator` instance
      to avoid mixing column and row settings.
  - name: Set the number of rows (vertical layout)
    text: '```python # Configure the layout to use 3 rows barcode_generator.parameters.barcode.data_bar.rows
      = 3 ```'
  - name: Save the barcode image with the row layout
    text: '```python # Save the vertically stacked barcode barcode_generator.save("output/ExpandedRows3.png",
      BarCodeImageFormat.Png) ```'
  type: HowTo
tags:
- barcode
- Python
- Databar
- image generation
title: Configura il layout del codice a barre Databar in Python – guida passo passo
url: /it/python-java/general/configure-databar-barcode-layout-in-python-step-by-step-guid/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Configurare il layout del codice a barre Databar in Python – guida passo‑passo

Se devi **configurare il layout del codice a barre Databar in Python**, questa guida ti accompagna attraverso l’intero processo. Vedrai come impostare il numero di colonne o righe per un codice a barre Databar Expanded Stacked e come salvare l’immagine risultante con una singola chiamata alla libreria generatore di codici a barre.

Controllare il layout è essenziale quando inserisci i codici a barre su confezioni strette, ricevute o schermi mobili. Nelle sezioni seguenti copriremo le importazioni necessarie, le due opzioni di layout (colonne e righe) e le migliori pratiche per salvare un’immagine PNG pulita.

## Cosa ti serve

Prima di iniziare, assicurati di avere:

* Python 3.8 o superiore
* `aspose.barcode` (o qualsiasi pacchetto compatibile per la generazione di codici a barre) installato  
  ```bash
  pip install aspose-barcode
  ```
* Permessi di scrittura su una cartella dove verranno salvati i file PNG

Non sono necessari strumenti esterni aggiuntivi: la libreria gestisce il rendering, il ridimensionamento e la codifica dell’immagine internamente.

## Come configurare il layout del codice a barre Databar in Python

Il cuore della soluzione è la classe `BarcodeGenerator`. Accetta un enum `EncodeTypes` che identifica la simbologia del codice a barre—in questo caso `EncodeTypes.DatabarExpandedStacked`. Dopo aver creato il generatore puoi regolare il layout impostando le proprietà `columns` o `rows` sull’oggetto parametro `data_bar`.

### Passo 1: Importare le classi necessarie

```python
from aspose.barcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat
```

Queste importazioni ti danno accesso al generatore, all’enumerazione per i tipi Databar e alla costante del formato immagine PNG.

### Passo 2: Creare un generatore di codici a barre per Databar Expanded Stacked

```python
# Initialize the generator with the desired symbology and value
barcode_generator = BarcodeGenerator(
    EncodeTypes.DatabarExpandedStacked,
    "Databar Expanded Stacked long"
)
```

*Perché questo passo?*  
`EncodeTypes.DatabarExpandedStacked` indica alla libreria di produrre la simbologia **Databar Expanded Stacked**, che supporta stringhe numeriche più lunghe mantenendo un ingombro compatto. Il secondo argomento è il dato da codificare; può essere qualsiasi stringa conforme alla specifica Databar.

### Passo 3: Impostare il numero di colonne (layout orizzontale)

```python
# Configure the layout to use 4 columns
barcode_generator.parameters.barcode.data_bar.columns = 4
```

**set barcode columns** è la frase chiave per questa operazione. Quando aumenti il conteggio delle colonne, il codice a barre si espande orizzontalmente, utile per etichette larghe. La libreria ricalcola automaticamente la larghezza del modulo per mantenere le dimensioni complessive coerenti.

#### Consiglio professionale
Il numero massimo di colonne per Databar Expanded Stacked è 8. Impostare un valore superiore al limite lo ridurrà al massimo consentito, ma è meglio convalidare l’input in anticipo.

### Passo 4: Salvare l’immagine del codice a barre con il layout a colonne

```python
# Save the image as a PNG file
barcode_generator.save("output/ExpandedCols4.png", BarCodeImageFormat.Png)
```

**save barcode image** è l’azione che scrive il codice a barre renderizzato su disco. PNG è lossless, quindi preserva i bordi netti necessari per una scansione affidabile.

### Passo 5: Creare un secondo generatore per lo stesso tipo di codice a barre (layout a righe)

Se preferisci una pila verticale, lavori con le righe invece delle colonne. Il codice qui sotto riutilizza lo stesso valore ma crea una nuova istanza di `BarcodeGenerator` per evitare di mescolare le impostazioni di colonne e righe.

```python
# New generator instance for row configuration
barcode_generator = BarcodeGenerator(
    EncodeTypes.DatabarExpandedStacked,
    "Databar Expanded Stacked long"
)
```

### Passo 6: Impostare il numero di righe (layout verticale)

```python
# Configure the layout to use 3 rows
barcode_generator.parameters.barcode.data_bar.rows = 3
```

**set barcode rows** dispone i moduli del codice a barre verticalmente. Un layout a tre righe riduce l’altezza di ogni singola pila, rendendo il codice a barre adatto a ricevute strette o schermi mobili.

#### Caso limite
Se imposti `rows` a 1, la libreria genera un Databar a singola riga (equivalente a un Databar standard). Valori inferiori a 1 vengono ignorati e ripristinati al valore predefinito (1 riga).

### Passo 7: Salvare l’immagine del codice a barre con il layout a righe

```python
# Save the vertically stacked barcode
barcode_generator.save("output/ExpandedRows3.png", BarCodeImageFormat.Png)
```

Ancora una volta, **save barcode image** utilizza PNG per mantenere l’output nitido.

## Esempio completo eseguibile

Mettere insieme tutti i pezzi ti fornisce uno script autonomo che puoi inserire in qualsiasi progetto Python.

```python
# ------------------------------------------------------------
# configure_databar_layout.py
# Demonstrates how to configure Databar barcode layout in Python
# ------------------------------------------------------------

from aspose.barcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat
import os

# Ensure the output directory exists
output_dir = "output"
os.makedirs(output_dir, exist_ok=True)

# -----------------------------------------------------------------
# 1️⃣ Column layout – 4 columns
# -----------------------------------------------------------------
col_generator = BarcodeGenerator(
    EncodeTypes.DatabarExpandedStacked,
    "Databar Expanded Stacked long"
)
col_generator.parameters.barcode.data_bar.columns = 4   # set barcode columns
col_path = os.path.join(output_dir, "ExpandedCols4.png")
col_generator.save(col_path, BarCodeImageFormat.Png)   # save barcode image
print(f"Column layout saved to {col_path}")

# -----------------------------------------------------------------
# 2️⃣ Row layout – 3 rows
# -----------------------------------------------------------------
row_generator = BarcodeGenerator(
    EncodeTypes.DatabarExpandedStacked,
    "Databar Expanded Stacked long"
)
row_generator.parameters.barcode.data_bar.rows = 3      # set barcode rows
row_path = os.path.join(output_dir, "ExpandedRows3.png")
row_generator.save(row_path, BarCodeImageFormat.Png)   # save barcode image
print(f"Row layout saved to {row_path}")
```

**Output previsto**

L’esecuzione dello script crea due file PNG:

* `output/ExpandedCols4.png` – un codice a barre esteso su quattro colonne
* `output/ExpandedRows3.png` – un codice a barre compresso in tre righe

Entrambe le immagini possono essere aperte con qualsiasi visualizzatore di immagini o importate direttamente in fatture PDF, modelli di etichette o pagine web.

## Domande frequenti e risoluzione dei problemi

| Domanda | Risposta |
|----------|--------|
| *E se il codice a barre appare sfocato?* | Aumenta la risoluzione dell’immagine impostando `barcode_generator.parameters.image_width` e `image_height` prima di chiamare `save`. |
| *Posso usare altri formati immagine?* | Sì. Sostituisci `BarCodeImageFormat.Png` con `Jpeg`, `Bmp` o `Gif` secondo necessità. |
| *Esiste un limite alla lunghezza dei dati?* | Databar Expanded Stacked supporta fino a 74 caratteri numerici. Superare il limite genera una `ArgumentException`. |
| *Come cambio il colore del primo piano?* | Usa `barcode_generator.parameters.barcode.color = Color.Blue` (importa `System.Drawing.Color`). |
| *Posso combinare colonne e righe?* | No. L’API tratta colonne e righe come modalità di layout mutualmente esclusive. Scegli una sola per istanza di codice a barre. |

## Prossimi passi

Ora che sai **configurare il layout del codice a barre Databar**, considera di approfondire questi argomenti correlati:

* **Aggiungere didascalie di testo** – usa `barcode_generator.parameters.barcode.code_text` per visualizzare il valore codificato sotto l’immagine.
* **Incorporare il codice a barre in un PDF** – combina il PNG generato con `aspose.pdf` per creare documenti stampabili.
* **Dimensionamento dinamico** – calcola il numero ottimale di colonne o righe in base alle dimensioni dell’etichetta a runtime.
* **Elaborazione batch** – itera su un CSV di codici prodotto per generare automaticamente una libreria di immagini di codici a barre.

Sperimenta con valori diversi di colonne e righe per vedere come influenzano l’affidabilità della scansione sui tuoi dispositivi target. Più test esegui, più comprenderai i compromessi tra dimensione del codice a barre, leggibilità e vincoli di spazio.

---

*Buon coding! Se questo tutorial ti è stato utile, condividilo con i colleghi o lascia un commento sulle sfide di layout che hai incontrato.*

## Cosa dovresti imparare dopo?


I tutorial seguenti coprono argomenti strettamente correlati che si basano sulle tecniche dimostrate in questa guida. Ogni risorsa include esempi di codice completi e funzionanti con spiegazioni passo‑passo per aiutarti a padroneggiare ulteriori funzionalità dell’API ed esplorare approcci di implementazione alternativi nei tuoi progetti.

- [Create DotCode barcode image – rows & columns (Aspose.BarCode)](/barcode/english/net/dotcode-barcode-configuration/dotcode-rows-columns-configuration/)
- [Create barcode image c# – Configure Codablock F Rows & Columns](/barcode/english/net/codablock-f-encoding/codablock-f-row-column-configuration/)
- [One-Dimensional Databar Barcode Height Adjustment](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-barcode-height-adjustment/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}