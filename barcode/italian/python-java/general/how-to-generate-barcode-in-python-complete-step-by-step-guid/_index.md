---
category: general
date: 2026-08-12
description: Come generare rapidamente un codice a barre usando Python. Impara a creare
  un codice a barre dai dati ed esportare l'immagine del codice a barre con una singola
  libreria.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to generate barcode
- create barcode from data
- export barcode image
- Python barcode generation
- Aspose.BarCode tutorial
language: it
lastmod: 2026-08-12
og_description: Come generare un codice a barre in Python con Aspose.BarCode. Segui
  questa guida per creare un codice a barre dai dati ed esportare l'immagine del codice
  a barre in formato PNG.
og_image_alt: Screenshot showing how to generate barcode with Python code
og_title: Come generare un codice a barre in Python – guida veloce e affidabile
schemas:
- author: Aspose
  dateModified: '2026-08-12'
  description: How to generate barcode quickly using Python. Learn to create barcode
    from data and export barcode image with a single library.
  headline: How to generate barcode in Python – complete step‑by‑step guide
  type: TechArticle
- description: How to generate barcode quickly using Python. Learn to create barcode
    from data and export barcode image with a single library.
  name: How to generate barcode in Python – complete step‑by‑step guide
  steps:
  - name: 1. Import the required classes
    text: '```python from aspose.barcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat
      ```'
  - name: 2. Create barcode from data
    text: The first step is to **create barcode from data**. The `BarcodeGenerator`
      constructor takes the symbology and the raw string you want to encode.
  - name: 3. Adjust the X‑dimension (module width)
    text: The X‑dimension controls the width of each barcode module (the thin bar).
      Setting it to 4 pixels gives a clear, readable image without making the file
      too large.
  - name: 4. Export barcode image (filled style)
    text: Now you can **export barcode image** using the `save` method. The example
      saves a PNG file, but you can choose JPEG, BMP, or TIFF by changing the `BarCodeImageFormat`
      enum.
  - name: 5. Create a second generator for an outline‑only barcode
    text: If you need an outline version (empty bars), you must create a new generator
      because the `filled_bars` flag cannot be toggled after the image is saved.
  - name: 6. Apply the same X‑dimension setting
    text: When you create a second generator, you must repeat any visual settings
      you want to keep consistent.
  - name: 7. Disable filled bars for an outline barcode
    text: Setting `filled_bars` to `False` tells the renderer to draw only the outlines
      of each module, producing a lighter image that can be useful for design purposes.
  - name: 8. Export the outline barcode image
    text: Finally, **export barcode image** again, this time storing the outline version.
  - name: Next steps
    text: '* Explore other symbologies such as QR, Code‑128, or DataMatrix by swapping
      `EncodeTypes.Planet` with the desired value. * Integrate the generated PNG files
      into PDF reports using libraries like `ReportLab` or `PyPDF2`. * Experiment
      with dynamic X‑dimension values to adapt barcode size based on scre'
  type: HowTo
tags:
- barcode
- Python
- image export
title: Come generare un codice a barre in Python – guida completa passo passo
url: /it/python-java/general/how-to-generate-barcode-in-python-complete-step-by-step-guid/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Come generare un codice a barre in Python – guida completa passo‑passo

Se hai bisogno di **come generare un codice a barre** in un'applicazione Python, questo tutorial ti mostra il codice esatto di cui hai bisogno. Imparerai a **creare un codice a barre dai dati**, a regolare il suo aspetto e a **esportare l'immagine del codice a barre** come file PNG—tutto in meno di dieci righe di codice.

Generare un codice a barre può sembrare una preoccupazione separata rispetto al resto della tua logica di business, ma con una singola libreria puoi mantenere il processo in linea con il tuo codice esistente. Nelle sezioni seguenti vedrai un esempio completo e eseguibile, comprenderai perché ogni riga è importante e scoprirai variazioni comuni come la modifica della larghezza del modulo o la creazione di un codice a barre solo con contorno.

## Come generare un codice a barre con la libreria Aspose.BarCode

La libreria Aspose.BarCode per Python (via .NET) fornisce un'API semplice per molte simbologie, incluso il codice a barre Planet usato in questa guida. Prima di iniziare, assicurati di avere il pacchetto installato:

```bash
pip install aspose-barcode
```

> **Consiglio:** Usa un ambiente virtuale per evitare conflitti di versione con altri progetti.

### 1. Importa le classi necessarie

```python
from aspose.barcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat
```

Queste importazioni ti danno accesso alla classe generatore, all'enumerazione dei tipi di codice a barre e all'enumerazione del formato immagine usata quando salvi il risultato.

### 2. Crea un codice a barre dai dati

Il primo passo è **creare un codice a barre dai dati**. Il costruttore `BarcodeGenerator` accetta la simbologia e la stringa grezza che vuoi codificare.

```python
# Step 1: Create a barcode generator for the Planet symbology with data "123456"
barcode_filled = BarcodeGenerator(EncodeTypes.Planet, "123456")
```

Il valore `EncodeTypes.Planet` seleziona il codice a barre Planet, mentre `"123456"` è il payload che apparirà nell'immagine finale.

### 3. Regola la dimensione X (larghezza del modulo)

La dimensione X controlla la larghezza di ogni modulo del codice a barre (la barra sottile). Impostandola a 4 pixel ottieni un'immagine chiara e leggibile senza rendere il file troppo grande.

```python
# Step 2: Set the X‑dimension (module width) to 4 pixels
barcode_filled.parameters.barcode.x_dimension.pixels = 4
```

> **Perché è importante:** Una dimensione X più grande migliora l'affidabilità della scansione su stampanti a bassa risoluzione, mentre un valore più piccolo riduce le dimensioni del file per l'uso web.

### 4. Esporta l'immagine del codice a barre (stile pieno)

Ora puoi **esportare l'immagine del codice a barre** usando il metodo `save`. L'esempio salva un file PNG, ma puoi scegliere JPEG, BMP o TIFF modificando l'enumerazione `BarCodeImageFormat`.

```python
# Step 3: Save the barcode using the default filled‑bars style
barcode_filled.save("YOUR_DIRECTORY/PlanetFilled.png", BarCodeImageFormat.Png)
```

Il file `PlanetFilled.png` contiene un codice a barre Planet completamente pieno, pronto per la stampa o per l'inserimento in un PDF.

### 5. Crea un secondo generatore per un codice a barre solo contorno

Se ti serve una versione a contorno (barre vuote), devi creare un nuovo generatore perché il flag `filled_bars` non può essere modificato dopo che l'immagine è stata salvata.

```python
# Step 4: Create a second generator for the same data to illustrate empty bars
barcode_empty = BarcodeGenerator(EncodeTypes.Planet, "123456")
```

### 6. Applica la stessa impostazione della dimensione X

Quando crei un secondo generatore, devi ripetere tutte le impostazioni visive che vuoi mantenere coerenti.

```python
# Step 5: Apply the same X‑dimension setting
barcode_empty.parameters.barcode.x_dimension.pixels = 4
```

### 7. Disabilita le barre piene per un codice a barre a contorno

Impostare `filled_bars` a `False` indica al renderer di disegnare solo i contorni di ogni modulo, producendo un'immagine più leggera che può essere utile per scopi di design.

```python
# Step 6: Disable filled bars to produce an outline‑only barcode
barcode_empty.parameters.barcode.filled_bars = False
```

### 8. Esporta l'immagine del codice a barre a contorno

Infine, **esporta l'immagine del codice a barre** di nuovo, questa volta salvando la versione a contorno.

```python
# Step 7: Save the outline barcode
barcode_empty.save("YOUR_DIRECTORY/PlanetEmpty.png", BarCodeImageFormat.Png)
```

Ora hai due file PNG: uno con barre solide (`PlanetFilled.png`) e uno con solo i contorni (`PlanetEmpty.png`).

## Esporta l'immagine del codice a barre in altri formati (opzionale)

Il metodo `save` supporta diversi formati. Per esportare come JPEG con qualità al 90 %:

```python
barcode_filled.save(
    "YOUR_DIRECTORY/PlanetFilled.jpg",
    BarCodeImageFormat.Jpeg,
    quality=90
)
```

Se ti serve uno sfondo trasparente per il web, scegli PNG con canale alfa:

```python
barcode_filled.parameters.background_color = None  # disables background fill
barcode_filled.save("YOUR_DIRECTORY/PlanetTransparent.png", BarCodeImageFormat.Png)
```

## Variazioni comuni e casi limite

| Scenario | Modifica necessaria | Snippet di codice |
|----------|---------------------|-------------------|
| **Simbologia diversa** (es. QR) | Usa un valore `EncodeTypes` diverso | `BarcodeGenerator(EncodeTypes.QR, "https://example.com")` |
| **Colore di primo piano personalizzato** | Imposta `fore_color` | `barcode_filled.parameters.barcode.fore_color = Color.Blue` |
| **Risoluzione più alta** | Aumenta DPI tramite `image_width` e `image_height` | `barcode_filled.parameters.image_width = 300; barcode_filled.parameters.image_height = 150` |
| **Stringhe di dati lunghe** | Assicurati che la lunghezza dei dati rientri nelle specifiche della simbologia | Valida la lunghezza prima di creare il generatore |

> **Attenzione:** Fornire dati che superano la lunghezza massima per la simbologia scelta genera un'eccezione a runtime. Convalida sempre la lunghezza della stringa o gestisci `ArgumentException`.

## Esempio completo, eseguibile

Di seguito trovi lo script completo che puoi copiare‑incollare in un file chiamato `generate_planet_barcode.py`. Modifica `YOUR_DIRECTORY` con una cartella che esiste sul tuo computer.

```python
# generate_planet_barcode.py
from aspose.barcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat

def generate_barcodes(output_dir: str):
    # Filled‑bars barcode
    filled = BarcodeGenerator(EncodeTypes.Planet, "123456")
    filled.parameters.barcode.x_dimension.pixels = 4
    filled.save(f"{output_dir}/PlanetFilled.png", BarCodeImageFormat.Png)

    # Outline‑only barcode
    empty = BarcodeGenerator(EncodeTypes.Planet, "123456")
    empty.parameters.barcode.x_dimension.pixels = 4
    empty.parameters.barcode.filled_bars = False
    empty.save(f"{output_dir}/PlanetEmpty.png", BarCodeImageFormat.Png)

if __name__ == "__main__":
    import os
    output_path = "YOUR_DIRECTORY"
    os.makedirs(output_path, exist_ok=True)
    generate_barcodes(output_path)
    print("Barcodes generated successfully.")
```

Eseguendo questo script otterrai due file PNG nella directory specificata. Verifica l'output aprendo le immagini con qualsiasi visualizzatore; entrambe dovrebbero mostrare un codice a barre Planet che codifica la stringa `123456`.

## Conclusione

Ora sai **come generare un codice a barre** in Python usando Aspose.BarCode, come **creare un codice a barre dai dati** e come **esportare l'immagine del codice a barre** sia in stile pieno che a contorno. Lo stesso schema si applica ad altre simbologie, formati immagine e personalizzazioni visive, offrendoti una base flessibile per qualsiasi funzionalità legata ai codici a barre nella tua applicazione.

### Prossimi passi

* Esplora altre simbologie come QR, Code‑128 o DataMatrix sostituendo `EncodeTypes.Planet` con il valore desiderato.  
* Integra i file PNG generati nei report PDF usando librerie come `ReportLab` o `PyPDF2`.  
* Sperimenta valori dinamici della dimensione X per adattare la dimensione del codice a barre in base alla risoluzione dello schermo o al DPI della stampante.

Buon coding, e sentiti libero di adattare l'esempio alle esigenze del tuo progetto!

## Cosa dovresti imparare dopo?

I tutorial seguenti trattano argomenti strettamente correlati che si basano sulle tecniche dimostrate in questa guida. Ogni risorsa include esempi di codice completi e funzionanti con spiegazioni passo‑passo per aiutarti a padroneggiare ulteriori funzionalità dell'API e a esplorare approcci di implementazione alternativi nei tuoi progetti.

- [Come generare un'immagine di codice a barre in Java con Aspose.BarCode](/barcode/english/java/barcode-rendering-techniques/)
- [Come generare un codice a barre Java – Guida completa alla configurazione](/barcode/english/java/barcode-configuration/)
- [Come creare immagini di codice a barre code128 in Java con Aspose.BarCode](/barcode/english/java/advanced-settings-and-optimization/saving-barcode-images-different-formats/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}