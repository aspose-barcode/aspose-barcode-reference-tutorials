---
category: general
date: 2026-08-22
description: Impara a generare codici a barre DataMatrix in Python e a codificare
  testo russo usando Aspose.BarCode – guida passo passo.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate DataMatrix barcode
- encode Russian text
language: it
lastmod: 2026-08-22
og_description: Genera un codice a barre DataMatrix in Python e codifica testo russo
  con Aspose.BarCode. Segui l'esempio completo ed eseguilo subito.
og_image_alt: Python script that generate DataMatrix barcode with encoded Russian
  text
og_title: Genera codice a barre DataMatrix in Python – tutorial completo di Aspose.BarCode
schemas:
- author: Aspose
  dateModified: '2026-08-22'
  description: Learn to generate DataMatrix barcode in Python and encode Russian text
    using Aspose.BarCode – step‑by‑step guide.
  headline: How to generate DataMatrix barcode in Python with Aspose.BarCode
  type: TechArticle
- description: Learn to generate DataMatrix barcode in Python and encode Russian text
    using Aspose.BarCode – step‑by‑step guide.
  name: How to generate DataMatrix barcode in Python with Aspose.BarCode
  steps:
  - name: '**ABC123** – the plain identifier.'
    text: '**ABC123** – the plain identifier.'
  - name: '**Привет** – the Russian greeting, correctly decoded as UTF‑8.'
    text: '**Привет** – the Russian greeting, correctly decoded as UTF‑8.'
  - name: Open the PNG file in an image viewer.
    text: Open the PNG file in an image viewer.
  - name: Use any DataMatrix scanning app (many mobile apps support it) or a hardware
      scanner.
    text: Use any DataMatrix scanning app (many mobile apps support it) or a hardware
      scanner.
  - name: The decoded string should display `ABC123Привет` (or the two parts separated
      depending on the scanner UI).
    text: The decoded string should display `ABC123Привет` (or the two parts separated
      depending on the scanner UI).
  type: HowTo
tags:
- Aspose.BarCode
- Python
- barcode generation
title: Come generare il codice a barre DataMatrix in Python con Aspose.BarCode
url: /it/python/general/how-to-generate-datamatrix-barcode-in-python-with-aspose-bar/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Come generare un codice a barre DataMatrix in Python con Aspose.BarCode

Se hai bisogno di **generare un codice a barre DataMatrix** in Python mentre **codifichi testo russo**, questa guida ti mostra i passaggi esatti. Vedrai un esempio completo, eseguibile, che costruisce un codetext esteso, configura il codice a barre e salva l’immagine in un unico script.

Creare codici a barre che contengono caratteri non‑ASCII solleva spesso domande su set di caratteri e codifica dei dati. Utilizzando `ExtCodetextBuilder` di Aspose.BarCode, puoi incorporare in modo sicuro testo UTF‑8, come i caratteri cirillici, all’interno di un simbolo DataMatrix. Il risultato funziona con qualsiasi scanner che supporti lo standard DataMatrix.

In questo tutorial imparerai a:

* Installare il pacchetto Aspose.BarCode necessario.
* Costruire un codetext esteso che mescoli dati semplici e testo russo.
* **Generare un codice a barre DataMatrix** con la stringa estesa.
* Regolare parametri del codice a barre come la dimensione del modulo.
* Salvare il codice a barre come file PNG.

Non sono richiesti servizi esterni; tutto viene eseguito localmente sulla tua macchina.

## Prerequisiti

Prima di iniziare, assicurati di avere:

* Python 3.8 o versioni successive installate.
* Una licenza attiva di Aspose.BarCode per Python (una versione di prova gratuita è sufficiente per lo sviluppo).
* Familiarità di base con la programmazione in Python.

Puoi installare la libreria Aspose.BarCode tramite pip:

```bash
pip install aspose-barcode
```

## Passo 1: Costruire una stringa di codetext esteso

Il primo compito è creare una singola stringa che contenga sia l’identificatore di prodotto semplice sia la frase in russo. `ExtCodetextBuilder` ti consente di concatenare diverse parti di codetext preservando le informazioni di codifica.

```python
# Import required Aspose.BarCode classes
import aspose.barcode as barcode
from aspose.barcode.generation import ExtCodetextBuilder, BarcodeGenerator, EncodeTypes

# Initialize the extended codetext builder
builder = ExtCodetextBuilder()

# Add a plain ASCII identifier – this could be a SKU, part number, etc.
builder.add_plain_codetext("ABC123")

# Add Russian text using ECI (Extended Channel Interpretation) encoding.
# The eci_encoding value 3 corresponds to UTF‑8.
builder.add_eci_codetext(eci_encoding=3, codetext="Привет")

# Retrieve the combined string that Aspose.BarCode will use.
extended_text = builder.get_extended_codetext()
print("Generated extended codetext:", extended_text)
```

**Perché questo passaggio è importante** – I simboli DataMatrix memorizzano byte grezzi. Quando devi mescolare alfabeti, devi indicare all’encoder quale set di caratteri si applica a ciascun segmento. Il metodo `add_eci_codetext` inserisce un indicatore ECI prima del testo russo, garantendo che gli scanner interpretino i byte come UTF‑8. Senza ECI, i caratteri cirillici apparirebbero come dati corrotti.

## Passo 2: Creare un generatore di codice a barre DataMatrix

Con il codetext esteso pronto, istanzia un `BarcodeGenerator` specificando il tipo `EncodeTypes.DATA_MATRIX`.

```python
# Create a DataMatrix barcode generator using the extended codetext
generator = BarcodeGenerator(EncodeTypes.DATA_MATRIX, extended_text)
```

**Perché DataMatrix?** – DataMatrix è un codice a barre bidimensionale che può contenere fino a 2.335 caratteri alfanumerici o 1.556 byte. È ideale per piccoli oggetti, parti industriali e situazioni in cui è necessario incorporare testo multilingue.

## Passo 3: (Opzionale) Configurare i parametri del codice a barre

Aspose.BarCode espone molti parametri. Per la maggior parte dei casi d’uso, le impostazioni predefinite producono un simbolo leggibile. Tuttavia, potresti voler controllare la dimensione di ogni modulo (il quadrato più piccolo nella matrice) per adattarla ai requisiti di stampa.

```python
# Set the module (pixel) size to 2.5 points – adjust as needed for your printer DPI
generator.parameters.barcode.x_dimension = 2.5
```

Altri parametri utili includono il livello di correzione errori, il margine e il colore di sfondo. Modificali solo se l’ambiente di scansione di destinazione richiede tolleranze specifiche.

## Passo 4: Salvare l’immagine del codice a barre

Infine, scrivi il codice a barre su un file. Il metodo `save` supporta PNG, JPEG, BMP e diversi formati vettoriali.

```python
# Save the barcode image to the desired folder
output_path = "YOUR_DIRECTORY/extended_codetext.png"
generator.save(output_path)
print(f"Barcode saved as {output_path}")
```

Quando apri `extended_codetext.png`, vedrai un simbolo DataMatrix nitido. Scansionandolo con un lettore DataMatrix standard otterrai le due parti:

1. **ABC123** – l’identificatore semplice.
2. **Привет** – il saluto russo, correttamente decodificato come UTF‑8.

## Esempio completo, eseguibile

Di seguito trovi lo script completo che puoi copiare‑incollare in un file chiamato `generate_datamatrix.py`. Sostituisci `YOUR_DIRECTORY` con una cartella esistente sul tuo sistema.

```python
# generate_datamatrix.py
# -------------------------------------------------
# Complete example: generate DataMatrix barcode and encode Russian text
# -------------------------------------------------

import aspose.barcode as barcode
from aspose.barcode.generation import ExtCodetextBuilder, BarcodeGenerator, EncodeTypes

def main():
    # Step 1: Build extended codetext
    builder = ExtCodetextBuilder()
    builder.add_plain_codetext("ABC123")
    builder.add_eci_codetext(eci_encoding=3, codetext="Привет")
    extended_text = builder.get_extended_codetext()
    print("Generated extended codetext:", extended_text)

    # Step 2: Create DataMatrix generator
    generator = BarcodeGenerator(EncodeTypes.DATA_MATRIX, extended_text)

    # Step 3: Optional parameters (adjust module size if needed)
    generator.parameters.barcode.x_dimension = 2.5

    # Step 4: Save the image
    output_path = "YOUR_DIRECTORY/extended_codetext.png"
    generator.save(output_path)
    print(f"Barcode saved as {output_path}")

if __name__ == "__main__":
    main()
```

Esegui lo script dalla riga di comando:

```bash
python generate_datamatrix.py
```

Dovresti vedere un output sulla console simile a:

```
Generated extended codetext: (ECI:3)ПриветABC123
Barcode saved as YOUR_DIRECTORY/extended_codetext.png
```

## Verifica del risultato

Per confermare che il codice a barre codifichi correttamente la frase russa:

1. Apri il file PNG in un visualizzatore di immagini.
2. Usa qualsiasi app di scansione DataMatrix (molte app mobili lo supportano) o uno scanner hardware.
3. La stringa decodificata dovrebbe mostrare `ABC123Привет` (o le due parti separate a seconda dell’interfaccia dello scanner).

Se i caratteri russi appaiono come spazzatura, ricontrolla che lo scanner supporti ECI UTF‑8. La maggior parte dei lettori moderni lo fa, ma i dispositivi legacy potrebbero richiedere una configurazione esplicita.

## Problemi comuni e come evitarli

| Problema | Causa | Soluzione |
|----------|-------|-----------|
| Output cirillico corrotto | Indicatore ECI mancante | Usa `add_eci_codetext` con `eci_encoding=3`. |
| Codice a barre troppo piccolo per la stampante | Dimensione modulo predefinita troppo fine per bassa DPI | Aumenta `x_dimension` (es. `3.0` o `4.0`). |
| File non salvato | Percorso della directory non valido | Verifica che `YOUR_DIRECTORY` esista e sia scrivibile. |
| Lo scanner non legge | Densità dati eccessiva | Riduci la quantità di dati codificati o aumenta il livello di correzione errori (`generator.parameters.barcode.error_correction_level`). |

## Estendere l’esempio

Puoi adattare questo schema ad altre lingue o tipi di dati:

* **Codificare testo giapponese o arabo** – cambia `eci_encoding` al valore appropriato (es. 5 per ISO‑8859‑5, 6 per ISO‑8859‑7).  
* **Aggiungere più segmenti ECI** – chiama `add_eci_codetext` più volte, ciascuna con la propria codifica.  
* **Creare un QR code invece** – sostituisci `EncodeTypes.DATA_MATRIX` con `EncodeTypes.QR`.  

Tutti gli altri passaggi rimangono identici perché `ExtCodetextBuilder` astrae la gestione a basso livello dei byte.

## Conclusione

Ora sai come **generare un codice a barre DataMatrix** in Python e **codificare testo russo** usando la funzionalità di codetext esteso di Aspose.BarCode. Lo script completo gestisce la negoziazione del set di caratteri, la creazione del codice a barre e l’output dell’immagine con poche righe di codice.

Successivamente, esplora altre simbologie di codici a barre (PDF417, Aztec) o integra il generatore in un servizio web che restituisce immagini PNG su richiesta. Gli stessi principi—costruire un codetext esteso e selezionare il `EncodeTypes` appropriato—si applicano all’intera suite Aspose.BarCode.

Buon coding e goditi la potenza della generazione multilingue di codici a barre!

## Cosa dovresti imparare dopo?

I tutorial seguenti trattano argomenti strettamente correlati che si basano sulle tecniche dimostrate in questa guida. Ogni risorsa include esempi di codice completi e funzionanti con spiegazioni passo‑passo per aiutarti a padroneggiare ulteriori funzionalità dell’API e a esplorare approcci di implementazione alternativi nei tuoi progetti.

- [How to Generate DataMatrix Barcodes Using Aspose.BarCode for .NET – Step‑by‑Step Guide](/barcode/english/net/datamatrix-barcode-configuration/)
- [Generate a DataMatrix barcode in ASCII mode with Aspose.BarCode for .NET (C#)](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-ascii/)
- [How to Generate DataMatrix Barcodes (ECC 200) with Aspose.BarCode for .NET](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-ecc-200-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}