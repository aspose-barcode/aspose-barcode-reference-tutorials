---
category: general
date: 2026-09-10
description: Codifica caratteri non ASCII in un codice QR e salva l'immagine del codice
  QR con un semplice costruttore Python. Segui una guida passo‑passo usando ExtCodetextBuilder
  e BarcodeGenerator.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- encode non ascii characters
- save qr code image
- extended codetext builder
- eci encoding python
- barcode generation python
language: it
lastmod: 2026-09-10
og_description: Codifica caratteri non ASCII in un codice QR e salva l'immagine del
  codice QR usando Python. Questo tutorial mostra come creare un testo di codice esteso,
  generare un codice QR e salvare l'immagine.
og_image_alt: Diagram showing encode non ASCII characters in QR code and save QR code
  image workflow
og_title: Codifica caratteri non ASCII in un QR code e salva l'immagine del QR code
  – guida Python passo passo
schemas:
- author: Aspose
  dateModified: '2026-09-10'
  description: Encode non ASCII characters in a QR code and save QR code image with
    a simple Python builder. Follow a step‑by‑step guide using ExtCodetextBuilder
    and BarcodeGenerator.
  headline: Encode non ASCII characters in QR code and save QR code image
  type: TechArticle
tags:
- barcode
- QR code
- Python
title: Codifica caratteri non ASCII nel codice QR e salva l'immagine del codice QR
url: /it/python/general/encode-non-ascii-characters-in-qr-code-and-save-qr-code-imag/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Codifica caratteri non ASCII in un codice QR e salva l'immagine del codice QR

Se hai bisogno di **codificare caratteri non ASCII** in un codice QR, questa guida ti mostra esattamente come farlo e poi **salvare l'immagine del codice QR** su disco. Che tu stia gestendo dati in russo, cinese o emoji, l'ExtCodetextBuilder ti consente di mescolare testo semplice e segmenti codificati ECI senza dover manipolare manualmente i byte.

Imparerai come creare una stringa di codetext esteso, generare un codice QR che interpreta quella stringa e infine scrivere l'immagine del codice a barre su un file. Il tutorial presuppone conoscenze di base di Python e che tu abbia installato l'SDK `barcode`.

## Prerequisiti

* Python 3.8+ installato.
* Il pacchetto Python `barcode` (o l'SDK appropriato) che fornisce `ExtCodetextBuilder`, `CodetextEncodingType` e `BarcodeGenerator`.
* Permessi di scrittura nella directory in cui desideri **salvare l'immagine del codice QR**.

Puoi installare l'SDK con pip (sostituisci `barcode-sdk` con il nome reale del pacchetto):

```bash
pip install barcode-sdk
```

## Passo 1: Crea un builder di codetext esteso

Il primo passo è istanziare `ExtCodetextBuilder`. Questo oggetto raccoglie più segmenti di testo e produce una singola stringa che la simbologia del codice QR può interpretare.

```python
from barcode import ExtCodetextBuilder, CodetextEncodingType, BarcodeGenerator, Symbology

# Initialize the builder that will hold all text parts
ext_builder = ExtCodetextBuilder()
```

*Perché è importante*: i codici QR supportano **codetext esteso**, il che significa che puoi incorporare diversi modi di codifica (plain, ECI, ecc.) in un unico codice a barre. Il builder astrae la formattazione a basso livello richiesta dalla specifica QR.

## Passo 2: Aggiungi un segmento di testo semplice

Il testo semplice è la modalità predefinita e funziona per i caratteri ASCII. Aggiungerlo per primo fornisce un fallback leggibile per gli scanner che ignorano l'ECI.

```python
# Add simple ASCII text
ext_builder.add_plain_codetext("HelloWorld")
```

Se ometti questo passo, il codice QR conterrà solo il segmento ECI, che alcuni lettori più vecchi potrebbero non decodificare correttamente.

## Passo 3: Aggiungi un segmento codificato ECI per caratteri non ASCII

Per includere caratteri al di fuori dell'intervallo ASCII — come il cirillico, il cinese o le emoji — è necessario specificare una codifica ECI (Extended Channel Interpretation). Qui usiamo UTF‑8 per la parola russa “Привет”.

```python
# Add a UTF‑8 encoded segment containing non‑ASCII characters
ext_builder.add_eci_codetext(CodetextEncodingType.UTF_8, "Привет")  # Russian “Hi”
```

*Perché funziona*: la specifica QR definisce valori ECI che indicano allo scanner quale set di caratteri utilizzare. Senza il marcatore ECI, i byte grezzi verrebbero interpretati come ISO‑8859‑1, producendo un output illeggibile.

## Passo 4: Recupera la stringa di codetext esteso combinata

Dopo aver aggiunto tutti i segmenti desiderati, chiama `get_extended_codetext()` per ottenere la stringa finale che il generatore di codici a barre si aspetta.

```python
# Combine all parts into one extended codetext string
extended_codetext = ext_builder.get_extended_codetext()
print("Extended codetext:", extended_codetext)
```

Il valore stampato appare come una serie di caratteri di controllo seguiti dal testo reale, ma non è mai necessario analizzarlo manualmente.

## Passo 5: Genera un codice QR usando il codetext esteso

Ora crea un `BarcodeGenerator`, imposta la simbologia su QR (l'unica simbologia 2‑D comune che supporta il codetext esteso) e fornisci la stringa combinata.

```python
# Initialize the QR generator
qr_generator = BarcodeGenerator()
qr_generator.set_symbology(Symbology.QR)          # QR supports extended codetext
qr_generator.set_code_text(extended_codetext)
```

*Suggerimento*: se provi lo stesso processo con Code‑128 o DataMatrix, l'SDK solleverà un'eccezione perché quei formati non possono interpretare i marcatori ECI.

## Passo 6: Salva l'immagine del codice QR

Infine, scrivi il codice a barre in un file PNG. Qui è dove **salvi l'immagine del codice QR** per un uso successivo.

```python
output_path = "output/qr_extended.png"
qr_generator.save(output_path)

print(f"QR code saved to {output_path}")
```

Assicurati che la cartella `output` esista o creala con `os.makedirs('output', exist_ok=True)` prima di chiamare `save`.

### Esempio completo eseguibile

Unendo tutti i passaggi ottieni uno script autonomo che puoi eseguire immediatamente:

```python
import os
from barcode import ExtCodetextBuilder, CodetextEncodingType, BarcodeGenerator, Symbology

# Ensure the output directory exists
os.makedirs("output", exist_ok=True)

# 1️⃣ Create the builder
ext_builder = ExtCodetextBuilder()

# 2️⃣ Add plain ASCII text
ext_builder.add_plain_codetext("HelloWorld")

# 3️⃣ Add UTF‑8 encoded non‑ASCII text (Russian)
ext_builder.add_eci_codetext(CodetextEncodingType.UTF_8, "Привет")

# 4️⃣ Retrieve the combined string
extended_codetext = ext_builder.get_extended_codetext()
print("Extended codetext:", extended_codetext)

# 5️⃣ Generate QR code
qr_generator = BarcodeGenerator()
qr_generator.set_symbology(Symbology.QR)
qr_generator.set_code_text(extended_codetext)

# 6️⃣ Save the image
output_file = "output/qr_extended.png"
qr_generator.save(output_file)
print(f"QR code saved to {output_file}")
```

**Output previsto** (console):

```
Extended codetext: <binary representation showing ECI markers>
QR code saved to output/qr_extended.png
```

Aprendo `qr_extended.png` con qualsiasi scanner QR verrà visualizzato `HelloWorldПривет`. Gli scanner che comprendono l'ECI renderanno correttamente i caratteri cirillici; gli altri mostreranno solo la parte ASCII.

## Domande comuni & casi limite

| Domanda | Risposta |
|----------|--------|
| *Posso usare altre codifiche come Shift‑JIS?* | Sì. Sostituisci `CodetextEncodingType.UTF_8` con `CodetextEncodingType.SHIFT_JIS` e fornisci il testo appropriato. |
| *Cosa succede se i dati combinati superano la capacità del QR?* | I codici QR hanno limiti di versione (fino a 177 × 177 moduli). Se il builder genera un'eccezione di dimensione, aumenta il livello di correzione errori o suddividi i dati in più codici QR. |
| *Devo impostare una versione QR specifica?* | L'SDK seleziona automaticamente la versione più piccola che contiene i dati. Puoi forzare una versione con `qr_generator.set_qr_version(10)` se necessario. |
| *L'immagine sarà trasparente?* | Per impostazione predefinita l'SDK scrive un PNG con sfondo bianco. Usa `qr_generator.set_background_color(Color.Transparent)` prima di `save` se ti serve la trasparenza. |

## Conclusione

In questo tutorial hai imparato a **codificare caratteri non ASCII** in un codice QR usando `ExtCodetextBuilder` e poi **salvare l'immagine del codice QR** con `BarcodeGenerator`. Il processo prevede la costruzione di una stringa di codetext esteso, l'aggiunta di segmenti sia di testo semplice sia codificati ECI, la generazione della simbologia QR e infine la scrittura del file immagine.

Da qui puoi approfondire:

* Aggiungere più segmenti ECI (lingue diverse o emoji).
* Regolare i livelli di correzione errori del QR per una maggiore affidabilità.
* Incorporare il PNG generato in PDF o pagine web.

Buon coding e divertiti a creare codici QR multilingue!

## Cosa dovresti imparare dopo?

I tutorial seguenti trattano argomenti strettamente correlati che si basano sulle tecniche dimostrate in questa guida. Ogni risorsa include esempi di codice completi e funzionanti con spiegazioni passo passo per aiutarti a padroneggiare funzionalità API aggiuntive ed esplorare approcci di implementazione alternativi nei tuoi progetti.

- [How to Generate QR Code Image in Python with Aspose.Barcode – Full Guide](/barcode/english/python/general/how-to-generate-qr-code-image-in-python-with-aspose-barcode/)
- [Generate Code128 Barcode with Aspose.Barcode Python – Full Guide](/barcode/english/python/general/generate-code128-barcode-with-aspose-barcode-python-full-gui/)
- [display product name using Python barcode library – step‑by‑step guide](/barcode/english/python/general/display-product-name-using-python-barcode-library-step-by-st/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}