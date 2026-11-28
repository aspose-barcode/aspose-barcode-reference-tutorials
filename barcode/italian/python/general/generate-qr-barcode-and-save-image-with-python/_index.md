---
category: general
date: 2026-11-27
description: Genera un codice QR in Python usando Aspose.Barcode e scopri come salvare
  rapidamente l'immagine del codice a barre su disco.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate QR barcode
- save barcode image
- Aspose.Barcode Python
- extended codetext QR
- barcode version information
language: it
lastmod: 2026-11-27
og_description: Genera codici QR in Python con Aspose.Barcode e salva immediatamente
  l'immagine del codice a barre. Segui l'esempio completo per creare, personalizzare
  e archiviare i codici QR.
og_image_alt: Screenshot of a generated QR barcode created with Python
og_title: Genera codice QR e salva l'immagine con Python – guida passo passo
schemas:
- author: Aspose
  dateModified: '2026-11-27'
  description: Generate QR barcode in Python using Aspose.Barcode and learn how to
    save barcode image to disk quickly.
  headline: Generate QR barcode and save image with Python
  type: TechArticle
tags:
- QR code
- Python
- Aspose
- Barcode generation
title: Genera codice QR e salva l'immagine con Python
url: /it/python/general/generate-qr-barcode-and-save-image-with-python/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Genera codice a barre QR e salva l'immagine con Python

Se devi **generare un codice a barre QR** in un'applicazione Python, questa guida ti mostra come farlo usando la libreria Aspose.Barcode. Imparerai anche il modo corretto per **salvare l'immagine del codice a barre** in una cartella locale, recuperare i dettagli della versione della libreria e gestire segmenti di codetext estesi.

La creazione di codici QR è una necessità comune per sistemi di ticketing, pagamenti mobili e tracciamento di prodotti. Alla fine di questo tutorial avrai uno script pronto all'uso che produce un file immagine di codice a barre QR e stampa le informazioni sulla versione per scopi di debug o conformità.

## Prerequisiti

Prima di iniziare, assicurati di avere:

* Python 3.8 o versioni successive installate.
* Il pacchetto `aspose-barcode`. Installalo con `pip install aspose-barcode`.
* Permessi di scrittura nella directory in cui verrà memorizzata l'immagine del codice a barre.

Non sono richiesti servizi esterni aggiuntivi; l'intero processo viene eseguito localmente.

## Passo 1: Costruisci un codetext esteso con `ExtCodetextBuilder`

Il codetext esteso ti consente di mescolare testo semplice e segmenti ECI (Extended Channel Interpretation) in un unico codice QR. Questo è utile quando devi incorporare caratteri da diversi set di caratteri, come il simbolo dell'euro.

```python
import aspose.barcode as bc
from aspose.barcode.generation import ExtCodetextBuilder, BuildVersionInfo

# Create the builder instance
ext_builder = ExtCodetextBuilder()

# Add a plain text segment
ext_builder.add_plain_codetext("ABC123")

# Add an ECI segment that uses ISO‑IEC 8859‑1 (code page 3)
ext_builder.add_eci_codetext(3, "€123")
```

**Perché questo passo è importante:**  
`ExtCodetextBuilder` assembla la stringa finale che l'encoder QR elaborerà. Senza costruire il codetext esteso, il codice a barre conterrebbe solo caratteri ASCII semplici e non potrebbe rappresentare simboli specifici della lingua locale.

## Passo 2: Recupera la stringa di codetext esteso combinata

```python
# Get the final extended codetext that will be encoded
extended_codetext = ext_builder.get_extended_codetext()
print("Extended codetext:", extended_codetext)
```

L'output appare così:

```
Extended codetext: ABC123[ECI3]€123
```

Il marcatore `[ECI3]` tra parentesi indica all'encoder QR di passare al set di caratteri specificato per i caratteri successivi.

## Passo 3: Genera il codice a barre QR usando il codetext esteso

```python
# Create a QR barcode generator with the extended codetext
barcode = bc.BarcodeGenerator(bc.EncodeTypes.QR, extended_codetext)
```

**Spiegazione:**  
`BarcodeGenerator` riceve due argomenti: il tipo di codice a barre (`QR`) e i dati da codificare (`extended_codetext`). Il generatore prepara tutte le strutture interne necessarie per il rendering.

## Passo 4: Salva l'immagine del codice a barre generato

```python
# Define the output path – adjust the folder as needed
output_path = "output/qr_extended.png"

# Save the image in PNG format
barcode.save(output_path)
print(f"Barcode image saved to {output_path}")
```

**Perché dovresti usare questo approccio:**  
Chiamare `save` scrive direttamente l'immagine su disco usando il formato inferito dall'estensione del file. Il metodo supporta PNG, JPEG, BMP e TIFF, offrendoti flessibilità per diversi consumatori downstream.

### Verifica dell'immagine salvata

Apri il file `output/qr_extended.png` con qualsiasi visualizzatore di immagini. Dovresti vedere un codice QR che, una volta scansionato, restituisce la stringa `ABC123€123`. La maggior parte degli scanner QR mobili moderni gestisce automaticamente il segmento ECI.

## Passo 5: Interroga le informazioni sulla versione di Aspose.BarCode (opzionale ma utile)

Conoscere la versione esatta della libreria Aspose.BarCode è utile quando devi segnalare bug o verificare la compatibilità.

```python
# Retrieve version details
version_info = BuildVersionInfo()
print("Aspose.BarCode version:")
print(f"  Assembly version : {version_info.ASSEMBLY_VERSION}")
print(f"  File version     : {version_info.FILE_VERSION}")
print(f"  Product          : {version_info.PRODUCT}")
print(f"  Release date     : {version_info.RELEASE_DATE}")
```

Output tipico:

```
Aspose.BarCode version:
  Assembly version : 23.9.0.0
  File version     : 23.9.0
  Product          : Aspose.BarCode for Python via .NET
  Release date     : 2023-09-15
```

## Script completo – copia, incolla ed esegui

```python
import aspose.barcode as bc
from aspose.barcode.generation import ExtCodetextBuilder, BuildVersionInfo

# 1️⃣ Build extended codetext
ext_builder = ExtCodetextBuilder()
ext_builder.add_plain_codetext("ABC123")
ext_builder.add_eci_codetext(3, "€123")
extended_codetext = ext_builder.get_extended_codetext()
print("Extended codetext:", extended_codetext)

# 2️⃣ Generate QR barcode
barcode = bc.BarcodeGenerator(bc.EncodeTypes.QR, extended_codetext)

# 3️⃣ Save barcode image
output_path = "output/qr_extended.png"
barcode.save(output_path)
print(f"Barcode image saved to {output_path}")

# 4️⃣ Display version information
version_info = BuildVersionInfo()
print("Aspose.BarCode version:")
print(f"  Assembly version : {version_info.ASSEMBLY_VERSION}")
print(f"  File version     : {version_info.FILE_VERSION}")
print(f"  Product          : {version_info.PRODUCT}")
print(f"  Release date     : {version_info.RELEASE_DATE}")
```

Eseguendo lo script si produce l'immagine del codice QR e vengono stampati sia il codetext esteso sia i dettagli della versione sulla console.

## Variazioni comuni e casi limite

| Situazione | Adeguamento consigliato |
|------------|--------------------------|
| **Set di caratteri diverso** | Cambia l'identificatore ECI passato a `add_eci_codetext`. Per UTF‑8 usa `5`. |
| **Correzione errori più alta** | Imposta `barcode.parameters.barcode.qr_error_level = bc.QRErrorLevel.H` prima di chiamare `save`. |
| **Dimensione immagine personalizzata** | Usa `barcode.parameters.image_width` e `barcode.parameters.image_height` per controllare le dimensioni in pixel. |
| **Output non PNG** | Cambia l'estensione del file in `output_path` in `.jpg` o `.bmp`. La libreria seleziona automaticamente l'encoder corretto. |

## Consigli professionali

* **Crea la cartella di output** programmaticamente se potrebbe non esistere:

  ```python
  import os
  os.makedirs(os.path.dirname(output_path), exist_ok=True)
  ```

* **Convalida il codice QR** dopo la generazione leggendo nuovamente con `aspose.barcode.BarcodeReader`. Questo garantisce che i dati codificati corrispondano alle aspettative, soprattutto quando si usano segmenti ECI.

  ```python
  reader = bc.BarcodeReader(output_path, bc.DecodeType.QR)
  for result in reader.read():
      print("Decoded text:", result.code_text)
  ```

* **Suggerimento sulle prestazioni** – riutilizza un'unica istanza di `BarcodeGenerator` se devi generare molti codici QR in un ciclo. Reimposta la proprietà `code_text` invece di creare un nuovo oggetto ad ogni iterazione.

## Conclusione

Ora sai come **generare un codice a barre QR** in Python con Aspose.Barcode, costruire un codetext esteso che mescola segmenti semplici ed ECI, e **salvare correttamente l'immagine del codice a barre** su disco. Lo script mostra anche come recuperare le informazioni sulla versione della libreria per la risoluzione dei problemi.

Passi successivi che potresti esplorare includono:

* Aggiungere un logo sovrapposto o colori personalizzati al codice QR.
* Incorporare il codice a barre QR direttamente nei PDF usando Aspose.PDF.
* Automatizzare la generazione batch per grandi set di dati.

Sentiti libero di sperimentare con payload di dati diversi, livelli di correzione errori e formati immagine. Buon coding!

## Cosa dovresti imparare dopo?

I tutorial seguenti trattano argomenti strettamente correlati che si basano sulle tecniche dimostrate in questa guida. Ogni risorsa include esempi di codice completi e funzionanti con spiegazioni passo‑passo per aiutarti a padroneggiare funzionalità API aggiuntive ed esplorare approcci di implementazione alternativi nei tuoi progetti.

- [How to Generate QR Code Image in Python with Aspose.Barcode – Full Guide](/barcode/english/python/general/how-to-generate-qr-code-image-in-python-with-aspose-barcode/)
- [How to generate Code 128 barcode and save barcode image with Aspose.BarCode](/barcode/english/python/general/how-to-generate-code-128-barcode-and-save-barcode-image-with/)
- [How to generate DataMatrix barcode in Python with Aspose.BarCode](/barcode/english/python/general/how-to-generate-datamatrix-barcode-in-python-with-aspose-bar/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}