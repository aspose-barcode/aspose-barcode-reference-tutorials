---
category: general
date: 2026-08-19
description: Come generare un codice a barre con ECI usando Aspose.Barcode per Python.
  Scopri come aggiungere dati ECI, mescolare testo semplice e salvare l'immagine in
  una guida chiara.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to generate barcode
- how to add eci
- Aspose.Barcode Python
- extended codetext barcode
- ECI encoding Python
language: it
lastmod: 2026-08-19
og_description: Come generare un codice a barre con ECI usando Aspose.Barcode per
  Python. Segui questo tutorial per imparare come aggiungere dati ECI, personalizzare
  l'aspetto e salvare il risultato.
og_image_alt: Screenshot showing a barcode generated with how to generate barcode
  example
og_title: Come generare un codice a barre con ECI usando Aspose.Barcode Python – passo
  dopo passo
schemas:
- author: Aspose
  dateModified: '2026-08-19'
  description: How to generate barcode with ECI using Aspose.Barcode for Python. Learn
    how to add eci data, mix plain text, and save the image in one clear guide.
  headline: How to generate barcode with ECI using Aspose.Barcode Python
  type: TechArticle
- description: How to generate barcode with ECI using Aspose.Barcode for Python. Learn
    how to add eci data, mix plain text, and save the image in one clear guide.
  name: How to generate barcode with ECI using Aspose.Barcode Python
  steps:
  - name: Expected result
    text: When you open `extended_codetext.png`, you should see a Code 128 barcode
      that encodes the numeric string `1234567890` followed by the Chinese characters
      “特殊字符”. Scanning the barcode with a modern scanner that respects ECI will return
      the original mixed string.
  - name: What if I need a different character set?
    text: Choose the appropriate ECI value from the ISO/IEC 18004 table. For example,
      ECI 27 represents ISO‑8859‑1 (Latin‑1). Replace the numeric identifier in `add_eci_codetext`
      accordingly.
  - name: Can I embed more than one ECI block?
    text: Yes. Call `add_eci_codetext` multiple times. The builder inserts the necessary
      ECI switch codes between blocks, preserving the order you add them.
  - name: Does the generator support QR codes with ECI?
    text: Absolutely. Replace `barcode.Symbology.CODE_128` with `barcode.Symbology.QR`
      and adjust any QR‑specific parameters (e.g., error correction level) via `generator.parameters.qr`.
  - name: How to handle very long data strings?
    text: For linear barcodes like Code 128, the maximum length is about 80 characters
      when using extended codetext. If you exceed that, consider switching to a two‑dimensional
      symbology such as QR or Data Matrix, which can store thousands of characters.
  type: HowTo
tags:
- barcode
- Python
- Aspose
title: Come generare un codice a barre con ECI usando Aspose.Barcode Python
url: /it/python/general/how-to-generate-barcode-with-eci-using-aspose-barcode-python/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Come generare un barcode con ECI usando Aspose.Barcode Python

Se hai bisogno di sapere **come generare un barcode** che contenga sia caratteri semplici sia dati codificati ECI, questa guida mostra l'intero processo. Vedrai esattamente **come aggiungere eci** alle sezioni, regolare le dimensioni e scrivere l'immagine su disco con un unico script eseguibile.

Il tutorial copre:

* Recuperare la versione della libreria Aspose.Barcode (opzionale ma utile per il debug).  
* Costruire una stringa di codetext esteso che mescola caratteri semplici e codificati ECI.  
* Creare un generatore di barcode per una simbologia che supporta il codetext esteso.  
* Personalizzare le dimensioni del barcode e salvare il file PNG finale.

Non è necessaria alcuna documentazione esterna; copia il codice, eseguilo e otterrai un'immagine di barcode che include caratteri cinesi codificati con ECI 26 (UTF‑8).

## Prerequisiti

Prima di iniziare, assicurati di avere:

* Python 3.8 o versioni successive installate.  
* pacchetto `aspose-barcode` installato (`pip install aspose-barcode`).  
* Permesso di scrittura sulla cartella in cui intendi salvare il file PNG.

Se stai usando un ambiente virtuale, attivalo prima per mantenere le dipendenze isolate.

## Passo 1: Verifica la versione di Aspose.Barcode (opzionale)

Conoscere la versione esatta della libreria aiuta quando è necessario segnalare bug o confrontare le funzionalità tra versioni.

```python
import aspose.barcode as barcode
from aspose.barcode.generation import BuildVersionInfo

ver = BuildVersionInfo()
print("Assembly version :", ver.ASSEMBLY_VERSION)
print("Product version  :", f"{ver.PRODUCT_MAJOR}.{ver.PRODUCT_MINOR}")
print("Release date     :", ver.RELEASE_DATE)
```

*Perché è importante*: L'output della versione conferma che il runtime corrisponde alla documentazione che stai seguendo. Versioni diverse possono supportare valori ECI diversi, quindi è un rapido controllo di coerenza.

## Passo 2: Costruisci un codetext esteso con parti semplici ed ECI‑codificate

Aspose.Barcode fornisce `ExtCodetextBuilder` per concatenare dati semplici e segmenti codificati ECI. In questo esempio mescoliamo una stringa numerica con caratteri cinesi.

```python
from aspose.barcode.generation import ExtCodetextBuilder

builder = ExtCodetextBuilder()
builder.add_plain_codetext("1234567890")          # plain numeric data
builder.add_eci_codetext(26, "特殊字符")          # Chinese characters using ECI 26 (UTF‑8)
extended_codetext = builder.get_extended_codetext()
print("Extended codetext :", extended_codetext)
```

*Spiegazione*:  
* `add_plain_codetext` inserisce dati che la simbologia del barcode tratta come caratteri ordinari.  
* `add_eci_codetext` indica al generatore di anteporre un indicatore ECI (qui **26**, che corrisponde a UTF‑8) prima del testo fornito. Questo è esattamente **come aggiungere eci** dati a un barcode.

Puoi chiamare `add_eci_codetext` più volte per incorporare diversi blocchi linguistici. Il builder gestisce automaticamente le sequenze di escape necessarie.

## Passo 3: Scegli una simbologia che supporta il codetext esteso

Non tutti i tipi di barcode possono memorizzare segmenti ECI. Code 128, QR e Data Matrix sono scelte comuni. L'esempio utilizza Code 128 perché è ampiamente supportato e funziona bene per dati alfanumerici misti.

```python
generator = barcode.generator.BarcodeGenerator(
    barcode.Symbology.CODE_128,   # Code128 supports extended codetext
    extended_codetext
)
```

*Perché Code 128?*: Accetta l'intero intervallo ASCII e le sequenze di escape ECI prodotte dal builder, rendendolo ideale per lo scenario “come generare barcode” che mescola testo semplice e codificato.

## Passo 4: Regola l'aspetto del barcode

Puoi controllare dimensioni, altezza, margini e molti altri aspetti visivi tramite l'oggetto `parameters`.

```python
# Width of a single module (the smallest bar)
generator.parameters.barcode.x_dimension = 2   # 2 pixels per module

# Height of the bars (for linear barcodes)
generator.parameters.barcode.bar_height = 50  # 50 pixels tall

# Optional: add quiet zone (margin) if required by a scanner
generator.parameters.barcode.is_quiet_zone_visible = True
generator.parameters.barcode.quiet_zone = 10   # 10 pixels margin on each side
```

*Consiglio*: Se prevedi di stampare il barcode, aumenta `x_dimension` e `bar_height` proporzionalmente per mantenere la leggibilità al DPI target.

## Passo 5: Salva l'immagine del barcode

Infine, scrivi l'immagine generata su un file. Aspose.Barcode supporta PNG, JPEG, BMP e molti altri formati.

```python
output_path = "output/extended_codetext.png"
generator.save(output_path)
print(f"Barcode saved as {output_path}")
```

Assicurati che la cartella `output` esista o creala con `os.makedirs("output", exist_ok=True)` prima di chiamare `save`.

### Risultato atteso

Quando apri `extended_codetext.png`, dovresti vedere un barcode Code 128 che codifica la stringa numerica `1234567890` seguita dai caratteri cinesi “特殊字符”. Scansionando il barcode con uno scanner moderno che rispetta l'ECI, otterrai la stringa mista originale.

![Barcode generato con l'esempio di come generare barcode](https://example.com/images/barcode-sample.png){: .align-center alt="Barcode generato con l'esempio di come generare barcode"}

## Domande comuni e casi particolari

### E se ho bisogno di un diverso set di caratteri?

Scegli il valore ECI appropriato dalla tabella ISO/IEC 18004. Ad esempio, ECI 27 rappresenta ISO‑8859‑1 (Latin‑1). Sostituisci l'identificatore numerico in `add_eci_codetext` di conseguenza.

### Posso incorporare più di un blocco ECI?

Sì. Chiama `add_eci_codetext` più volte. Il builder inserisce i codici di commutazione ECI necessari tra i blocchi, preservando l'ordine in cui li aggiungi.

### Il generatore supporta i codici QR con ECI?

Assolutamente. Sostituisci `barcode.Symbology.CODE_128` con `barcode.Symbology.QR` e regola eventuali parametri specifici del QR (ad esempio, livello di correzione degli errori) tramite `generator.parameters.qr`.

```python
generator.parameters.qr.error_correction_level = barcode.QRErrorLevel.H
```

### Come gestire stringhe di dati molto lunghe?

Per i barcode lineari come Code 128, la lunghezza massima è di circa 80 caratteri quando si utilizza il codetext esteso. Se superi questo limite, considera di passare a una simbologia bidimensionale come QR o Data Matrix, che può memorizzare migliaia di caratteri.

## Script completo e eseguibile

Di seguito trovi il programma completo che puoi copiare‑incollare in un file chiamato `generate_extended_barcode.py` ed eseguire direttamente.

```python
import os
import aspose.barcode as barcode
from aspose.barcode.generation import ExtCodetextBuilder, BuildVersionInfo

# ------------------------------------------------------------------
# Optional: print library version – useful for troubleshooting
# ------------------------------------------------------------------
ver = BuildVersionInfo()
print("Assembly version :", ver.ASSEMBLY_VERSION)
print("Product version  :", f"{ver.PRODUCT_MAJOR}.{ver.PRODUCT_MINOR}")
print("Release date     :", ver.RELEASE_DATE)

# ------------------------------------------------------------------
# Build extended codetext: plain numbers + Chinese characters (ECI 26)
# ------------------------------------------------------------------
builder = ExtCodetextBuilder()
builder.add_plain_codetext("1234567890")          # plain numeric data
builder.add_eci_codetext(26, "特殊字符")          # Chinese characters using UTF‑8
extended_codetext = builder.get_extended_codetext()
print("Extended codetext :", extended_codetext)

# ------------------------------------------------------------------
# Create a Code128 generator – supports the extended codetext format
# ------------------------------------------------------------------
generator = barcode.generator.BarcodeGenerator(
    barcode.Symbology.CODE_128,
    extended_codetext
)

# ------------------------------------------------------------------
# Customize appearance (size, quiet zone, etc.)
# ------------------------------------------------------------------
generator.parameters.barcode.x_dimension = 2
generator.parameters.barcode.bar_height = 50
generator.parameters.barcode.is_quiet_zone_visible = True
generator.parameters.barcode.quiet_zone = 10

# ------------------------------------------------------------------
# Ensure output directory exists and save the image
# ------------------------------------------------------------------
output_dir = "output"
os.makedirs(output_dir, exist_ok=True)
output_path = os.path.join(output_dir, "extended


## Cosa dovresti imparare dopo?

I tutorial seguenti coprono argomenti strettamente correlati che si basano sulle tecniche dimostrate in questa guida. Ogni risorsa include esempi di codice completi e funzionanti con spiegazioni passo passo per aiutarti a padroneggiare funzionalità API aggiuntive ed esplorare approcci di implementazione alternativi nei tuoi progetti.

- [Come generare un'immagine di barcode con personalizzazione dello spazio supplementare usando Aspose.BarCode](/barcode/english/net/supplemental-barcode-data/supplemental-barcode-space-customization/)
- [Come generare un'immagine di barcode in Java con Aspose.BarCode](/barcode/english/java/barcode-rendering-techniques/)
- [Come generare un barcode DataMatrix con Aspose.BarCode per .NET](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-macro-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}