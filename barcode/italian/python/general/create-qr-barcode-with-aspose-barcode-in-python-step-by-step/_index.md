---
category: general
date: 2026-08-09
description: Crea un codice QR in Python usando Aspose.BarCode. Scopri come generare
  un codetext esteso, regolare l'aspetto e salvare l'immagine—tutto in un unico tutorial.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create QR barcode
- Aspose.BarCode Python
- extended codetext QR
- QR code generation Python
- barcode visual customization
language: it
lastmod: 2026-08-09
og_description: Crea un codice QR in Python con Aspose.BarCode. Questa guida mostra
  come costruire un codetext esteso, impostare i parametri visivi e esportare l'immagine.
og_image_alt: Screenshot of a generated QR barcode created with Aspose.BarCode in
  Python
og_title: Crea codice QR con Aspose.BarCode in Python – esempio completo di codice
schemas:
- author: Aspose
  dateModified: '2026-08-09'
  description: Create QR barcode in Python using Aspose.BarCode. Learn how to build
    extended codetext, adjust appearance, and save the image—all in one tutorial.
  headline: Create QR barcode with Aspose.BarCode in Python – step‑by‑step guide
  type: TechArticle
- description: Create QR barcode in Python using Aspose.BarCode. Learn how to build
    extended codetext, adjust appearance, and save the image—all in one tutorial.
  name: Create QR barcode with Aspose.BarCode in Python – step‑by‑step guide
  steps:
  - name: Common variations
    text: '- **Multiple ECI segments:** Call `add_eci_codetext` multiple times to
      mix several languages. - **Different ECI identifiers:** Use `27` for ISO‑8859‑1,
      `28` for ISO‑8859‑2, etc., depending on your target encoding.'
  - name: Edge case handling
    text: '- **High‑density data:** If the encoded data is large, you may need to
      increase `x_dimension` or choose a higher error‑correction level (via `qr_generator.parameters.qr.error_correction_level`).
      - **Transparent background:** Set `qr_generator.parameters.barcode.bg_color
      = Color.Transparent` for PNGs'
  - name: Verifying the result
    text: 'Open the saved file in any image viewer. You should see a QR code that,
      when scanned, returns the combined string:'
  type: HowTo
tags:
- QR code
- Python
- Aspose
- Barcode generation
title: Crea codice a barre QR con Aspose.BarCode in Python – guida passo passo
url: /it/python/general/create-qr-barcode-with-aspose-barcode-in-python-step-by-step/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Crea un codice a barre QR con Aspose.BarCode in Python – guida passo‑passo

Se hai bisogno di **creare un codice a barre QR** in Python, questo tutorial ti guida attraverso l’intero processo usando la libreria Aspose.BarCode. Che tu stia codificando ID prodotto, testo multilingue o dati personalizzati, vedrai come costruire un codetext esteso, regolare le impostazioni visive e salvare l’immagine finale in uno script unico e eseguibile.

L’esempio mostra anche come visualizzare la versione della libreria, il che ti aiuta a verificare di stare usando una release compatibile. Alla fine di questa guida avrai un’immagine di codice a barre QR pronta all’uso e una chiara comprensione di ogni opzione di configurazione.

## Prerequisiti

Prima di iniziare, assicurati di avere:

- Python 3.8+ installato.
- Il pacchetto `aspose-barcode` (installalo con `pip install aspose-barcode`).
- Familiarità di base con la sintassi di Python.
- Permessi di scrittura nella directory di output dove verrà salvato il file PNG.

> **Consiglio pro:** Usa un ambiente virtuale per evitare conflitti di versione con altri progetti.

## Step 1: Verifica la versione della libreria Aspose.BarCode

Visualizzare la versione della libreria garantisce che tu stia usando una release che supporta il codetext esteso e la codifica QR.

```python
from asposebarcode import BuildVersionInfo

# Show the current Aspose.BarCode version
version_info = BuildVersionInfo()
print(
    f"Aspose.BarCode version: {version_info.PRODUCT} "
    f"{version_info.PRODUCT_MAJOR}.{version_info.PRODUCT_MINOR} "
    f"(released {version_info.RELEASE_DATE})"
)
```

**Perché è importante:**  
Le versioni più vecchie potrebbero non includere la classe `ExtCodetextBuilder` necessaria per segmenti misti plain e ECI. Confermare la versione previene errori di runtime più avanti nel flusso di lavoro.

## Step 2: Costruisci una stringa di codetext esteso

Un codetext esteso ti consente di combinare dati ASCII plain con segmenti Unicode (ECI), fondamentale per i QR code multilingue.

```python
from asposebarcode import ExtCodetextBuilder

# Initialize the builder
ext_builder = ExtCodetextBuilder()

# Add a plain segment – typically a product ID or numeric code
ext_builder.add_plain_codetext("ABC12345")

# Add an ECI segment – here we embed Japanese greeting "こんにちは"
# 26 is the ECI identifier for UTF‑8 encoding
ext_builder.add_eci_codetext(26, "こんにちは")

# Retrieve the full extended codetext that the QR generator will use
extended_codetext = ext_builder.get_extended_codetext()
print(f"Generated extended codetext: {extended_codetext}")
```

**Perché è importante:**  
Il metodo `add_plain_codetext` memorizza i dati come ASCII standard, mentre `add_eci_codetext` antepone a un blocco Unicode il designatore ECI appropriato. Questo approccio assicura che gli scanner QR interpretino correttamente il testo giapponese, evitando caratteri illeggibili.

### Varianti comuni

- **Segmenti ECI multipli:** Chiama `add_eci_codetext` più volte per mescolare diverse lingue.
- **Identificatori ECI diversi:** Usa `27` per ISO‑8859‑1, `28` per ISO‑8859‑2, ecc., a seconda della codifica di destinazione.

## Step 3: Genera il codice a barre QR usando il codetext esteso

Ora che abbiamo una stringa formattata correttamente, possiamo creare il QR code.

```python
from asposebarcode import BarCodeGenerator, EncodeTypes, BarCodeImageFormat

# Create the QR generator with the extended codetext
qr_generator = BarCodeGenerator(EncodeTypes.QR, extended_codetext)
```

**Perché è importante:**  
`EncodeTypes.QR` indica ad Aspose.BarCode di utilizzare la simbologia QR. Passare direttamente `extended_codetext` collega i dati misti alla matrice QR, preservando sia le parti plain sia quelle Unicode.

## Step 4: Regola l’aspetto visivo (opzionale ma consigliato)

Affinare i parametri visivi del codice a barre migliora l’affidabilità della scansione e si allinea alle linee guida del brand.

```python
# Set module (pixel) size – larger values increase overall image size
qr_generator.parameters.barcode.x_dimension = 4      # each module = 4 pixels

# Set border thickness – a thin white border helps scanners isolate the QR code
qr_generator.parameters.barcode.border_width = 2    # 2-pixel border
```

**Perché è importante:**  
- **`x_dimension`** controlla la dimensione di ogni modulo QR; valori troppo piccoli possono causare errori di lettura su dispositivi a bassa risoluzione.
- **`border_width`** aggiunge una zona silenziosa. Alcuni scanner richiedono almeno una zona silenziosa di 4 moduli; la libreria la aggiunge automaticamente, ma puoi aumentarla per maggiore sicurezza.

### Gestione dei casi limite

- **Dati ad alta densità:** Se i dati codificati sono molti, potresti dover aumentare `x_dimension` o scegliere un livello di correzione d’errore più alto (tramite `qr_generator.parameters.qr.error_correction_level`).
- **Sfondo trasparente:** Imposta `qr_generator.parameters.barcode.bg_color = Color.Transparent` per PNG con canale alfa.

## Step 5: Salva l’immagine del codice a barre QR

Infine, scrivi l’immagine su disco nel formato che preferisci.

```python
# Define output path – replace YOUR_DIRECTORY with an actual folder
output_file = "YOUR_DIRECTORY/extended_qr.png"

# Save as PNG; other formats include JPEG, BMP, GIF, TIFF
qr_generator.save(output_file, BarCodeImageFormat.PNG)
print(f"Barcode saved to {output_file}")
```

**Perché è importante:**  
Salvare come PNG mantiene una qualità lossless, ideale per i QR code che richiedono bordi nitidi. Se ti serve un formato diverso per un’app web, basta cambiare l’enumerazione `BarCodeImageFormat`.

### Verifica del risultato

Apri il file salvato con qualsiasi visualizzatore di immagini. Dovresti vedere un QR code che, una volta scansionato, restituisce la stringa combinata:

```
ABC12345
こんにちは
```

La maggior parte delle app scanner moderne mostra prima il segmento plain e poi rende correttamente il saluto giapponese.

---

## Script completo eseguibile

Copia l’intero blocco qui sotto in un file chiamato `create_qr_barcode.py` ed eseguilo con `python create_qr_barcode.py`. Modifica `YOUR_DIRECTORY` con una cartella scrivibile sul tuo computer.

```python
# create_qr_barcode.py
from asposebarcode import (
    BuildVersionInfo,
    ExtCodetextBuilder,
    BarCodeGenerator,
    EncodeTypes,
    BarCodeImageFormat,
)

# 1️⃣ Display library version
version_info = BuildVersionInfo()
print(
    f"Aspose.BarCode version: {version_info.PRODUCT} "
    f"{version_info.PRODUCT_MAJOR}.{version_info.PRODUCT_MINOR} "
    f"(released {version_info.RELEASE_DATE})"
)

# 2️⃣ Build extended codetext (plain + Japanese Unicode)
ext_builder = ExtCodetextBuilder()
ext_builder.add_plain_codetext("ABC12345")
ext_builder.add_eci_codetext(26, "こんにちは")
extended_codetext = ext_builder.get_extended_codetext()
print(f"Generated extended codetext: {extended_codetext}")

# 3️⃣ Create QR generator
qr_generator = BarCodeGenerator(EncodeTypes.QR, extended_codetext)

# 4️⃣ Optional visual tweaks
qr_generator.parameters.barcode.x_dimension = 4
qr_generator.parameters.barcode.border_width = 2

# 5️⃣ Save image
output_file = "YOUR_DIRECTORY/extended_qr.png"
qr_generator.save(output_file, BarCodeImageFormat.PNG)
print(f"Barcode saved to {output_file}")
```

L’esecuzione di questo script stampa la versione, il codetext esteso e una conferma che il file PNG è stato creato.

---

## Conclusione

Ora sai come **creare un codice a barre QR** in Python usando Aspose.BarCode. Il tutorial ha coperto:

1. Verifica della versione della libreria.
2. Costruzione del codetext esteso con segmenti plain ed ECI (Unicode).
3. Generazione del QR code.
4. Personalizzazione dei parametri visivi come dimensione del modulo e larghezza del bordo.
5. Salvataggio dell’immagine finale in formato PNG.

Da qui puoi approfondire:

- Modificare i livelli di correzione d’errore (`qr_generator.parameters.qr.error_correction_level`).
- Aggiungere un logo o un’immagine di sfondo (`qr_generator.parameters.qr.logo`).
- Esportare in altri formati come SVG per grafica web scalabile.
- Integrare il generatore in un endpoint Flask o Django per la creazione di QR al volo.

Sperimenta con payload di dati diversi e impostazioni visive per adattarle al branding e ai requisiti di scansione della tua applicazione. Buon coding!

## Cosa dovresti imparare dopo?

I tutorial seguenti trattano argomenti strettamente correlati che si basano sulle tecniche dimostrate in questa guida. Ogni risorsa include esempi di codice completi e funzionanti con spiegazioni passo‑passo per aiutarti a padroneggiare funzionalità aggiuntive dell’API e a esplorare approcci alternativi di implementazione nei tuoi progetti.

- [Come creare codetext esteso per dotcode con Aspose.BarCode per .NET](/barcode/english/net/dotcode-barcode-configuration/dotcode-extended-code-text-configuration/)
- [Creare barcode Aspose .NET – Configurazione del testo DataMatrix](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-extended-code-text-configuration/)
- [Come creare una zona silenziosa per ITF-14 usando Aspose.BarCode per .NET](/barcode/english/net/itf-14-barcode-customization/itf-14-barcode-quiet-zone-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}