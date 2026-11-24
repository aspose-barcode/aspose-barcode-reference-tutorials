---
category: general
date: 2026-11-23
description: Come generare immagini di codici a barre in Python con Aspose.BarCode.
  Impara a creare un codice a barre Planet, regolare la dimensione X e generare un
  PNG con barre vuote.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to generate barcode
- Python barcode generation
- Aspose.BarCode library
- Planet barcode symbology
- empty bars barcode
- barcode image PNG
language: it
lastmod: 2026-11-23
og_description: Come generare un codice a barre in Python usando Aspose.BarCode. Questo
  tutorial ti guida nella creazione di un codice a barre Planet con barre vuote e
  nel salvataggio come PNG.
og_image_alt: Screenshot of Python code that generates a Planet barcode with empty
  bars saved as a PNG file
og_title: Come generare un codice a barre in Python – guida completa
schemas:
- author: Aspose
  dateModified: '2026-11-23'
  description: How to generate barcode images in Python with Aspose.BarCode. Learn
    to create a Planet barcode, adjust X‑dimension, and output an empty‑bars PNG.
  headline: How to generate barcode images in Python using Aspose.BarCode
  type: TechArticle
- description: How to generate barcode images in Python with Aspose.BarCode. Learn
    to create a Planet barcode, adjust X‑dimension, and output an empty‑bars PNG.
  name: How to generate barcode images in Python using Aspose.BarCode
  steps:
  - name: Switching to a different symbology
    text: 'If you need a QR code, Code 128, or any other format, replace `EncodeTypes.Planet`
      with the appropriate enum value:'
  - name: Changing the image format
    text: 'Aspose.BarCode supports PNG, JPEG, BMP, and TIFF. To generate a JPEG instead:'
  - name: Adjusting image size without losing quality
    text: 'You can control the overall image dimensions via the `resolution` property
      or by scaling the X‑dimension and Y‑dimension together. For high‑resolution
      prints, set a higher DPI:'
  - name: Handling long data strings
    text: 'The Planet symbology has a limited data capacity (up to 8 characters).
      If you try to encode a longer string, the generator raises an exception. Validate
      the length before creating the barcode:'
  type: HowTo
tags:
- barcode
- Python
- Aspose
title: Come generare immagini di codici a barre in Python usando Aspose.BarCode
url: /it/python-java/general/how-to-generate-barcode-images-in-python-using-aspose-barcod/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Come generare immagini di codici a barre in Python usando Aspose.BarCode

Generare immagini di codici a barre in Python è semplice con la libreria Aspose.BarCode. Questa guida ti mostra passo‑passo come generare un codice a barre usando la simbologia Planet, personalizzare la dimensione X e produrre un file PNG in stile “empty‑bars”.

Vedrai uno script completo e eseguibile che potrai copiare nel tuo progetto. Il tutorial copre anche variazioni comuni — come passare a un’altra simbologia o a un formato di output diverso — così potrai adattare la soluzione alle tue esigenze.

## Prerequisiti

Prima di iniziare, assicurati di avere:

* Python 3.8 o versioni successive installate.  
* Accesso a un terminale o prompt dei comandi.  
* Una licenza attiva di Aspose.BarCode per Python (la valutazione gratuita è sufficiente per i test).  
* Familiarità di base con la gestione dei pacchetti Python (`pip`).

## Passo 1: Installa il pacchetto Aspose.BarCode

Aspose distribuisce la sua API Python tramite PyPI. Installala con il gestore di pacchetti standard:

```bash
pip install asposebarcode
```

> **Consiglio:** Usa un ambiente virtuale (`python -m venv venv`) per mantenere le dipendenze isolate dagli altri progetti.

## Passo 2: Importa le classi Aspose.BarCode necessarie

L'istruzione di importazione porta il generatore, l'enumerazione delle simbologie e l'enumerazione dei formati immagine.

```python
from asposebarcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat
```

* `BarcodeGenerator` crea l'oggetto codice a barre.  
* `EncodeTypes` elenca tutte le simbologie supportate — qui useremo `Planet`.  
* `BarCodeImageFormat` definisce il tipo di file di output (PNG, JPEG, ecc.).

## Passo 3: Crea un generatore di codice a barre per la simbologia Planet

Istanzia il generatore con la simbologia desiderata e i dati da codificare.

```python
# Create a generator for the Planet symbology with the value "123456"
barcode = BarcodeGenerator(EncodeTypes.Planet, "123456")
```

La simbologia `Planet` produce un motivo circolare ideale per scopi decorativi o di branding.

## Passo 4: Regola la dimensione X (larghezza del modulo)

La dimensione X controlla la larghezza della barra più piccola (modulo). Impostarla a 4 pixel produce un’immagine chiara e ad alta risoluzione.

```python
# Set the module width to 4 pixels
barcode.parameters.barcode.x_dimension.pixels = 4
```

Modificare la dimensione X è utile quando serve un codice a barre che si scala bene per la stampa o la visualizzazione su schermo.

## Passo 5: Disabilita le barre piene per uno stile “empty‑bars”

Un codice a barre “empty‑bars” mostra solo i contorni delle barre, utile per applicazioni con forte componente di design.

```python
# Produce an empty‑bars barcode by disabling filled bars
barcode.parameters.barcode.filled_bars = False
```

Quando `filled_bars` è `False`, il generatore disegna forme vuote anziché solide.

## Passo 6: Salva l’immagine del codice a barre come file PNG

Infine, scrivi il codice a barre su disco. PNG è senza perdita e ampiamente supportato.

```python
# Save the barcode as a PNG image
barcode.save("output/PlanetEmptyBars.png", BarCodeImageFormat.Png)
```

Il metodo `save` crea automaticamente la directory di destinazione se non esiste.

## Esempio completo – uno script completo e eseguibile

Unendo tutti i pezzi ottieni un programma autonomo che puoi eseguire subito:

```python
# -*- coding: utf-8 -*-
"""
Generate a Planet barcode with empty bars and save it as PNG.
Requires: asposebarcode (pip install asposebarcode)
"""

from asposebarcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat
import os

# Ensure the output directory exists
output_dir = "output"
os.makedirs(output_dir, exist_ok=True)

# Step 1: Create the generator
barcode = BarcodeGenerator(EncodeTypes.Planet, "123456")

# Step 2: Configure appearance
barcode.parameters.barcode.x_dimension.pixels = 4   # X‑dimension = 4 px
barcode.parameters.barcode.filled_bars = False    # empty‑bars style

# Step 3: Save as PNG
output_path = os.path.join(output_dir, "PlanetEmptyBars.png")
barcode.save(output_path, BarCodeImageFormat.Png)

print(f"Barcode saved to: {output_path}")
```

**Output previsto:** Dopo aver eseguito lo script, `output/PlanetEmptyBars.png` contiene un’immagine di 200 × 200 pixel di un codice a barre Planet con barre vuote. Aprendo il file in qualsiasi visualizzatore di immagini vedrai il motivo circolare con il valore numerico codificato al suo interno.

## Variazioni comuni e casi particolari

### Passare a un’altra simbologia

Se ti serve un QR code, Code 128 o qualsiasi altro formato, sostituisci `EncodeTypes.Planet` con il valore enum appropriato:

```python
barcode = BarcodeGenerator(EncodeTypes.QR, "https://example.com")
```

### Cambiare il formato immagine

Aspose.BarCode supporta PNG, JPEG, BMP e TIFF. Per generare un JPEG invece:

```python
barcode.save("output/PlanetEmptyBars.jpg", BarCodeImageFormat.Jpeg)
```

### Regolare le dimensioni dell’immagine senza perdere qualità

Puoi controllare le dimensioni complessive dell’immagine tramite la proprietà `resolution` o scalando insieme le dimensioni X e Y. Per stampe ad alta risoluzione, imposta un DPI più alto:

```python
barcode.parameters.image.resolution = 300  # 300 dpi for print quality
```

### Gestire stringhe di dati lunghe

La simbologia Planet ha una capacità dati limitata (fino a 8 caratteri). Se provi a codificare una stringa più lunga, il generatore solleverà un’eccezione. Convalida la lunghezza prima di creare il codice a barre:

```python
data = "123456"
if len(data) > 8:
    raise ValueError("Planet barcode supports a maximum of 8 characters.")
```

## Consigli e insidie

* **Attivazione della licenza:** Per l’uso in produzione, applica il file di licenza all’inizio dello script con `asposebarcode.License().set_license("Aspose.Total.lic")`. Saltare questo passaggio inserirà una filigrana nell’immagine di output.  
* **Sicurezza nei thread:** Le istanze di `BarcodeGenerator` non sono thread‑safe. Crea un’istanza separata per ogni thread se generi codici a barre in parallelo.  
* **Prestazioni:** Riutilizzare un generatore per più valori (impostando `barcode.value = "new data"`) è più veloce che costruire un nuovo oggetto ogni volta.  
* **Percorsi file:** Usa `os.path.join` per costruire percorsi indipendenti dalla piattaforma, soprattutto quando distribuisci su Linux o macOS.

## Conclusione

Ora sai come generare immagini di codici a barre in Python con Aspose.BarCode, personalizzare la dimensione X, produrre uno stile “empty‑bars” e salvare il risultato come PNG. L’esempio completo può essere adattato ad altre simbologie, formati di output e stili visivi, fornendoti una base flessibile per qualsiasi funzionalità legata ai codici a barre nelle tue applicazioni.

**Passi successivi:** Esplora parole chiave secondarie come *Python barcode generation* provando diverse codifiche, sperimenta le impostazioni di compressione *barcode image PNG* o integra le immagini generate in un servizio web usando Flask o FastAPI. Buon coding!

## Cosa dovresti imparare dopo?

I tutorial seguenti trattano argomenti strettamente correlati che si basano sulle tecniche dimostrate in questa guida. Ogni risorsa include esempi di codice completi e funzionanti con spiegazioni passo‑passo per aiutarti a padroneggiare funzionalità aggiuntive dell’API ed esplorare approcci di implementazione alternativi nei tuoi progetti.

- [How to create planet barcode PNG with Python](/barcode/english/python-java/general/how-to-create-planet-barcode-png-with-python/)
- [How to create barcode image in Python with Aspose.BarCode](/barcode/english/python-java/general/how-to-create-barcode-image-in-python-with-aspose-barcode/)
- [How to Generate QR Code Image in Python with Aspose.Barcode – Full Guide](/barcode/english/python/general/how-to-generate-qr-code-image-in-python-with-aspose-barcode/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}