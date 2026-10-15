---
category: general
date: 2026-10-15
description: Crea un codice a barre da una stringa in Python usando Aspose.BarCode,
  impara a generare un codice a barre Code 128 e a salvare il PNG del codice a barre
  in poche righe.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode from string
- generate code 128 barcode
- how to save barcode
- generate barcode png
- encode data into barcode
language: it
lastmod: 2026-10-15
og_description: Crea un codice a barre da una stringa in Python per codificare i dati
  in un codice a barre Code 128 e salvarlo come file PNG con Aspose.BarCode.
og_image_alt: Screenshot of a generated Code 128 barcode saved as a PNG image
og_title: Crea un codice a barre da una stringa in Python – guida passo passo
schemas:
- author: Aspose
  dateModified: '2026-10-15'
  description: Create barcode from string in Python using Aspose.BarCode, learn how
    to generate Code 128 barcode and save barcode PNG in just a few lines.
  headline: Create barcode from string in Python with Aspose.BarCode
  type: TechArticle
- questions:
  - answer: Replace `EncodeTypes.CODE_128` with another enum value such as `EncodeTypes.QR`,
      `EncodeTypes.EAN_13`, or `EncodeTypes.PDF_417`. The rest of the code remains
      the same.
    question: What if I need a different symbology?
  - answer: Code 128 supports the full 128‑character ASCII set. For Unicode data,
      consider using QR Code (`EncodeTypes.QR`) which handles UTF‑8 natively.
    question: Can I generate a barcode from non‑ASCII characters?
  - answer: Pass a different member of `BarCodeImageFormat` to `save`, e.g., `BarCodeImageFormat.JPEG`
      or `BarCodeImageFormat.BMP`.
    question: How do I change the image format?
  - answer: Wrap the `save` call in a try/except block and handle `PermissionError`
      gracefully, perhaps by prompting the user for an alternative path.
    question: What if the output directory is read‑only?
  type: FAQPage
tags:
- barcode
- Python
- Aspose
- Code128
title: Crea codice a barre da stringa in Python con Aspose.BarCode
url: /it/python-java/general/create-barcode-from-string-in-python-with-aspose-barcode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Crea barcode da stringa in Python con Aspose.BarCode

Se hai bisogno di **creare barcode da stringa** in Python, questa guida ti mostra i passaggi esatti con Aspose.BarCode. Imparerai come **generare un barcode Code 128**, regolare il suo aspetto e **salvare il barcode PNG** su disco. La soluzione funziona su qualsiasi piattaforma che supporta Python 3.9+ e richiede solo poche righe di codice.

Generare barcode programmaticamente elimina gli errori di inserimento manuale e ottimizza i flussi di lavoro come il tracciamento dell'inventario, la gestione dei biglietti e la stampa di etichette. Alla fine di questo tutorial sarai in grado di **codificare dati in un barcode**, personalizzare le dimensioni e memorizzare l'immagine dove ne hai bisogno.

## Prerequisiti

- Python 3.9 o versioni successive installato  
- Accesso a Internet per scaricare il pacchetto Aspose.BarCode  
- Permessi di scrittura sulla directory in cui salverai il file PNG  

Se stai usando un ambiente virtuale (altamente consigliato), attivalo ora.

## Installa il pacchetto Python Aspose.BarCode

Aspose fornisce una libreria pure‑Python che gestisce tutte le comuni simbologie di barcode, incluso Code 128. Installala con pip:

```bash
pip install aspose-barcode
```

*Consiglio pro:* Blocca la versione (ad es., `aspose-barcode==23.9`) per evitare cambiamenti inattesi in produzione.

## Crea barcode da stringa in Python

Il primo passo funzionale è importare le classi necessarie e istanziare un generatore per la simbologia desiderata. Questo esempio utilizza **Code 128**, ideale per dati alfanumerici.

```python
# Step 1: Import the Aspose.BarCode classes
from asposebarcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat

# Step 2: Create a generator for Code 128 and provide the data string
barcode_generator = BarcodeGenerator(EncodeTypes.CODE_128, "1234567890")
```

**Perché è importante:** `EncodeTypes.CODE_128` indica alla libreria quale standard di barcode applicare, mentre il secondo argomento (`"1234567890"`) è la **stringa che vuoi codificare nel barcode**. Puoi sostituirla con qualsiasi stringa ASCII fino a 80 caratteri per Code 128.

## Genera barcode Code 128

Una volta che il generatore è pronto, puoi produrre l'immagine del barcode in memoria. La libreria rende automaticamente il barcode in base ai dati forniti.

```python
# Step 3: Render the barcode to an image object (in memory)
barcode_image = barcode_generator.generate_barcode_image()
```

A questo punto `barcode_image` è un'istanza di `System.Drawing.Image` (su Windows) o un oggetto immagine compatibile su altre piattaforme. Puoi visualizzarlo direttamente in una GUI, incorporarlo in un PDF o continuare a personalizzarlo.

## Regola l'aspetto del barcode

Regolare finemente le proprietà visive garantisce che il barcode venga letto in modo affidabile nel tuo ambiente specifico. Le regolazioni comuni includono la X‑dimension (larghezza della barra più stretta) e l'altezza complessiva della barra.

```python
# Step 4: Adjust appearance – X dimension and bar height
barcode_generator.parameters.barcode.x_dimension.pixels = 2   # width of the smallest bar
barcode_generator.parameters.barcode.bar_height.pixels = 100  # height of the bars (optional)
```

*Perché regolare questi valori?*  
- **La dimensione X** influenza la densità del barcode; un valore più piccolo produce un barcode più compatto che si adatta a etichette piccole.  
- **L'altezza della barra** influisce sulla leggibilità; barre più alte sono più facili da rilevare per gli scanner da una certa distanza.

Puoi anche cambiare i colori, aggiungere margini o incorporare testo leggibile dall'uomo tramite l'oggetto `parameters`. Consulta la documentazione di Aspose.BarCode per l'elenco completo delle opzioni.

## Come salvare il barcode come PNG

Salvare l'immagine generata è l'ultimo passo nel flusso di lavoro **creare barcode da stringa**. La libreria supporta diversi formati; PNG è senza perdita e ampiamente supportato.

```python
# Step 5: Save the barcode image to a PNG file
output_path = "output/barcode.png"
barcode_generator.save(output_path, BarCodeImageFormat.PNG)
```

Il metodo `save` scrive l'immagine nel file system usando il formato specificato. Se la directory di destinazione (`output/` in questo esempio) non esiste, Python solleverà un `FileNotFoundError`. Crea la directory in anticipo o gestisci l'eccezione:

```python
import os

output_dir = os.path.dirname(output_path)
os.makedirs(output_dir, exist_ok=True)   # ensures the directory exists
barcode_generator.save(output_path, BarCodeImageFormat.PNG)
```

**Risultato atteso:** Dopo aver eseguito lo script, `output/barcode.png` contiene un chiaro barcode Code 128 che codifica `"1234567890"`. Aprendo il file in qualsiasi visualizzatore di immagini verrà mostrato un barcode nero‑su‑bianco pronto per la scansione.

## Esempio completo e eseguibile

Mettendo insieme tutti i pezzi, ecco uno script autonomo che puoi copiare, incollare e eseguire:

```python
"""
Complete example: create barcode from string, generate Code 128 barcode,
customize appearance, and save barcode PNG using Aspose.BarCode.
"""

import os
from asposebarcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat

# 1. Define input data and output location
data_to_encode = "1234567890"
output_path = "output/barcode.png"

# 2. Ensure the output directory exists
os.makedirs(os.path.dirname(output_path), exist_ok=True)

# 3. Initialise the generator for Code 128
generator = BarcodeGenerator(EncodeTypes.CODE_128, data_to_encode)

# 4. Optional: tweak visual parameters
generator.parameters.barcode.x_dimension.pixels = 2
generator.parameters.barcode.bar_height.pixels = 100

# 5. Save as PNG
generator.save(output_path, BarCodeImageFormat.PNG)

print(f"Barcode saved to {output_path}")
```

Esegui lo script con `python create_barcode.py`. Se tutto è installato correttamente, vedrai:

```
Barcode saved to output/barcode.png
```

Apri il file PNG e verifica che il barcode corrisponda alla stringa originale usando qualsiasi app scanner di barcode.

## Domande comuni e casi particolari

- **E se ho bisogno di una simbologia diversa?**  
  Sostituisci `EncodeTypes.CODE_128` con un altro valore enum, ad esempio `EncodeTypes.QR`, `EncodeTypes.EAN_13` o `EncodeTypes.PDF_417`. Il resto del codice rimane invariato.

- **Posso generare un barcode da caratteri non ASCII?**  
  Code 128 supporta l'intero set ASCII a 128 caratteri. Per dati Unicode, considera l'uso del QR Code (`EncodeTypes.QR`) che gestisce nativamente UTF‑8.

- **Come cambio il formato dell'immagine?**  
  Passa un membro diverso di `BarCodeImageFormat` al metodo `save`, ad esempio `BarCodeImageFormat.JPEG` o `BarCodeImageFormat.BMP`.

- **E se la directory di output è di sola lettura?**  
  Avvolgi la chiamata `save` in un blocco try/except e gestisci `PermissionError` in modo appropriato, magari chiedendo all'utente un percorso alternativo.

- **Suggerimento di performance:**  
  Generare migliaia di barcode in un ciclo può essere intensivo per la CPU. Riutilizza una singola istanza di `BarcodeGenerator` e aggiorna solo `generator.parameters.barcode.code_text` tra le iterazioni.

## Conclusione

Ora sai come **creare barcode da stringa** in Python usando Aspose.BarCode, **generare barcode Code 128**, personalizzare le sue dimensioni e **salvare il barcode PNG** su disco. Questa soluzione end‑to‑end ti consente di **codificare dati in un barcode** in modo rapido e affidabile, facilitando l'integrazione dei barcode nei sistemi di inventario, nelle piattaforme di biglietteria o in qualsiasi applicazione che richieda identificatori leggibili da macchine.

**Passi successivi**

- Esplora altre simbologie (alternative a `generate code 128 barcode`) come QR o DataMatrix.  
- Aggiungi logica di gestione degli errori per rendere lo script robusto per l'uso in produzione (fallimenti di `how to save barcode`).  
- Incorpora il PNG generato in PDF o report HTML (`generate barcode png` per il web).  

Buon coding e goditi la semplicità della generazione programmatica di barcode!

## Cosa dovresti imparare dopo?

I tutorial seguenti coprono argomenti strettamente correlati che si basano sulle tecniche dimostrate in questa guida. Ogni risorsa include esempi di codice completi e funzionanti con spiegazioni passo‑passo per aiutarti a padroneggiare funzionalità API aggiuntive ed esplorare approcci di implementazione alternativi nei tuoi progetti.

- [Come generare barcode Code 128 e salvare l'immagine del barcode con Aspose.BarCode](/barcode/english/python/general/how-to-generate-code-128-barcode-and-save-barcode-image-with/)
- [Come generare immagine QR Code in Python con Aspose.Barcode – Guida completa](/barcode/english/python/general/how-to-generate-qr-code-image-in-python-with-aspose-barcode/)
- [Crea barcode PNG in Python – Guida completa Aspose.Barcode](/barcode/english/python-java/general/create-barcode-png-in-python-full-aspose-barcode-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}