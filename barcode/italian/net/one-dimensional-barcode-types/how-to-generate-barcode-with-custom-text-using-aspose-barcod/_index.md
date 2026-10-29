---
category: general
date: 2026-10-28
description: Come generare un codice a barre con testo personalizzato usando Aspose.BarCode
  – guida passo‑passo per gli sviluppatori .NET per creare immagini di codici a barre
  Aspose.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to generate barcode
- generate barcode custom text
- create barcode aspose
language: it
lastmod: 2026-10-28
og_description: Come generare un codice a barre con testo personalizzato in .NET usando
  Aspose.BarCode. Segui questa guida completa per creare e salvare un codice a barre
  Macro PDF417.
og_image_alt: how to generate barcode example PNG image showing a Macro PDF417 barcode
og_title: Come generare un codice a barre con testo personalizzato – tutorial Aspose.BarCode
schemas:
- author: Aspose
  dateModified: '2026-10-28'
  description: How to generate barcode with custom text using Aspose.BarCode – step‑by‑step
    guide for .NET developers to create barcode Aspose images.
  headline: How to generate barcode with custom text using Aspose.BarCode for .NET
  type: TechArticle
- description: How to generate barcode with custom text using Aspose.BarCode – step‑by‑step
    guide for .NET developers to create barcode Aspose images.
  name: How to generate barcode with custom text using Aspose.BarCode for .NET
  steps:
  - name: Why each line matters
    text: '* **EncodeTypes.MacroPdf417** – selects the Macro PDF417 symbology, which
      supports segmented data and metadata. * **XDimension.Pixels** – controls the
      size of each module; a value of 2 pixels yields a clear, scannable image. *
      **Pdf417.Columns** – reduces the overall width, making the barcode more c'
  - name: Using a different barcode type
    text: If you need to **generate barcode custom text** for a QR code instead of
      Macro PDF417, replace `EncodeTypes.MacroPdf417` with `EncodeTypes.QR`. The rest
      of the parameter structure stays the same, but QR codes do not support Macro
      metadata fields.
  - name: Handling Unicode characters
    text: The example already includes Unicode characters (`Å`, `ó`, `©`). Aspose.BarCode
      handles UTF‑8 input out of the box, but you should ensure the source file is
      saved with UTF‑8 encoding to avoid compile‑time warnings.
  - name: Saving to other image formats
    text: 'Aspose.BarCode supports BMP, JPEG, TIFF, and SVG in addition to PNG. Change
      the `BarCodeImageFormat` enum value accordingly:'
  - name: Large data sets
    text: Macro PDF417 can split data across multiple segments. When the text exceeds
      the capacity of a single segment, increment `MacroPdf417SegmentID` and keep
      `MacroPdf417SegmentsCount` consistent across all generated parts. This approach
      is essential for **create barcode aspose** scenarios where the paylo
  - name: Error handling
    text: 'Wrap the generation logic in a try‑catch block to surface runtime issues
      such as invalid file paths or unsupported characters:'
  type: HowTo
tags:
- barcode
- Aspose.BarCode
- .NET
title: Come generare un codice a barre con testo personalizzato usando Aspose.BarCode
  per .NET
url: /it/net/one-dimensional-barcode-types/how-to-generate-barcode-with-custom-text-using-aspose-barcod/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Come generare un codice a barre con testo personalizzato usando Aspose.BarCode per .NET

Generare un codice a barre con testo personalizzato è una necessità frequente quando è necessario incorporare identificatori, timestamp o altri metadati direttamente in un codice visivo. Questo tutorial mostra come generare un codice a barre Macro PDF417 che contiene testo personalizzato e un set completo di metadati, utilizzando la libreria **Aspose.BarCode** per .NET.

Imparerai a configurare il generatore, applicare testo personalizzato, impostare i campi specifici di Macro PDF417 e salvare il risultato come immagine PNG. Non sono richiesti strumenti esterni: basta il pacchetto NuGet Aspose.BarCode e un ambiente di sviluppo .NET.

## Prerequisiti

Prima di iniziare, assicurati di avere:

* .NET 6.0 SDK o versioni successive installate  
* Visual Studio 2022 (o qualsiasi IDE che supporti .NET)  
* **Aspose.BarCode for .NET** pacchetto NuGet (`Install-Package Aspose.BarCode`)  

Questi prerequisiti garantiscono che il codice venga compilato ed eseguito senza configurazioni aggiuntive.

## Passo 1: Installa il pacchetto Aspose.BarCode

Apri un terminale nella cartella del tuo progetto ed esegui:

```bash
dotnet add package Aspose.BarCode
```

Il comando aggiunge l'ultima versione stabile di Aspose.BarCode al tuo progetto, fornendoti l'accesso alla classe `BarcodeGenerator` e a tutti i parametri correlati.

## Passo 2: Crea una nuova applicazione console

Crea una semplice app console che ospiterà la logica di generazione del codice a barre:

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

namespace BarcodeDemo
{
    internal class Program
    {
        private static void Main()
        {
            // The full barcode generation flow is encapsulated in a separate method
            GenerateMacroPdf417Barcode();
        }

        /// <summary>
        /// Generates a Macro PDF417 barcode with custom text and metadata, then saves it as PNG.
        /// </summary>
        private static void GenerateMacroPdf417Barcode()
        {
            // Step 1: Instantiate the generator with the desired encode type and data
            using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.MacroPdf417, "Åspóse.Barcóde©"))
            {
                // Step 2: Define the visual appearance of the barcode
                generator.Parameters.Barcode.XDimension.Pixels = 2;          // Size of a single module
                generator.Parameters.Barcode.Pdf417.Columns = 5;            // Number of columns in the symbol

                // Step 3: Populate Macro PDF417 specific metadata fields
                generator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
                generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;
                generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;
                generator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";
                generator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234; // CCITT‑16 example value
                generator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400_000;
                generator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = new DateTime(2019, 11, 1);
                generator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
                generator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
                generator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;

                // Step 4: Save the barcode image to disk
                string outputPath = @"ExtPDF417Meta.png";
                generator.Save(outputPath, BarCodeImageFormat.Png);
                Console.WriteLine($"Barcode saved to {outputPath}");
            }
        }
    }
}
```

### Perché ogni riga è importante

* **EncodeTypes.MacroPdf417** – seleziona la simbologia Macro PDF417, che supporta dati segmentati e metadati.  
* **XDimension.Pixels** – controlla la dimensione di ogni modulo; un valore di 2 pixel produce un’immagine chiara e leggibile.  
* **Pdf417.Columns** – riduce la larghezza complessiva, rendendo il codice a barre più compatto per le etichette stampate.  
* **MacroPdf417* properties** – incorporano informazioni a livello di file (ID, conteggio segmenti, timestamp, ecc.) direttamente nel codice a barre. Questa capacità è unica a Macro PDF417 ed è spesso usata in logistica o sistemi di gestione documentale.  
* **Save(..., BarCodeImageFormat.Png)** – scrive un file PNG lossless, preservando i bordi nitidi del codice a barre per una scansione affidabile.

## Passo 3: Esegui il programma e verifica l'output

Compila ed esegui l’app console:

```bash
dotnet run
```

Il programma crea `ExtPDF417Meta.png` nella directory di lavoro del progetto. Aprendo il file si visualizza un codice a barre Macro PDF417 che codifica il testo **“Åspóse.Barcóde©”** insieme ai metadati forniti.

**Output previsto** – un’immagine PNG simile a quella mostrata di seguito:

![esempio di output di generazione di codice a barre PNG che mostra un codice a barre Macro PDF417](ExtPDF417Meta.png)

*Il testo alternativo dell’immagine (“esempio di output di generazione di codice a barre PNG che mostra un codice a barre Macro PDF417”) rinforza la parola chiave principale per l’accessibilità e la SEO.*

## Varianti comuni e casi limite

### Utilizzare un tipo di codice a barre diverso

Se devi **generare codice a barre con testo personalizzato** per un QR code invece di Macro PDF417, sostituisci `EncodeTypes.MacroPdf417` con `EncodeTypes.QR`. La struttura dei parametri rimane la stessa, ma i QR code non supportano i campi di metadati Macro.

### Gestione dei caratteri Unicode

L’esempio include già caratteri Unicode (`Å`, `ó`, `©`). Aspose.BarCode gestisce l'input UTF‑8 nativamente, ma è necessario assicurarsi che il file sorgente sia salvato con codifica UTF‑8 per evitare avvisi di compilazione.

### Salvataggio in altri formati immagine

Aspose.BarCode supporta BMP, JPEG, TIFF e SVG oltre a PNG. Modifica il valore dell’enumerazione `BarCodeImageFormat` di conseguenza:

```csharp
generator.Save("barcode.svg", BarCodeImageFormat.Svg);
```

### Set di dati di grandi dimensioni

Macro PDF417 può suddividere i dati in più segmenti. Quando il testo supera la capacità di un singolo segmento, incrementa `MacroPdf417SegmentID` e mantieni coerente `MacroPdf417SegmentsCount` in tutte le parti generate. Questo approccio è essenziale per scenari **create barcode aspose** in cui il payload è più grande di quanto un singolo codice a barre possa contenere.

### Gestione degli errori

Avvolgi la logica di generazione in un blocco try‑catch per rilevare problemi a runtime, come percorsi file non validi o caratteri non supportati:

```csharp
try
{
    GenerateMacroPdf417Barcode();
}
catch (Exception ex)
{
    Console.Error.WriteLine($"Barcode generation failed: {ex.Message}");
}
```

## Pro tip per una generazione di codici a barre affidabile

* **Convalida il codice a barre** dopo la creazione usando `BarCodeReader`. Questo passaggio aggiuntivo conferma che i dati codificati corrispondano alle tue aspettative.

  ```csharp
  using (BarCodeReader reader = new BarCodeReader("ExtPDF417Meta.png", DecodeType.MacroPdf417))
  {
      if (reader.Read())
          Console.WriteLine($"Decoded text: {reader.GetCodeText()}");
  }
  ```

* **Mantieni la X‑dimension** tra 2 – 4 pixel per la maggior parte degli scanner. Valori più piccoli possono produrre immagini illeggibili su dispositivi a bassa risoluzione.

* **Evita nomi file molto lunghi** in `MacroPdf417FileName`. La specifica limita il campo a 32 caratteri.

* **Usa timestamp coerenti** (UTC) quando generi più segmenti per semplificare l’elaborazione successiva.

## Conclusione

Ora sai **come generare un codice a barre** con testo personalizzato usando Aspose.BarCode per .NET, come configurare i metadati Macro PDF417 e come salvare il risultato come immagine PNG. L’esempio completo e funzionante dimostra ogni passaggio necessario—from l’installazione del pacchetto NuGet alla gestione dei caratteri Unicode e al salvataggio dell’output.

Da qui puoi:

* **Generare codice a barre con testo personalizzato** per altre simbologie (QR, DataMatrix, ecc.)  
* **Creare workflow Aspose per codici a barre** che elaborano migliaia di immagini in batch  
* Integrare il codice di generazione del codice a barre in servizi ASP.NET Core, servizi Windows o Azure Functions  

Sperimenta con parametri diversi, esplora campi di metadati aggiuntivi e incorpora il codice a barre nei tuoi flussi di automazione documentale. Buon coding!

## Cosa dovresti imparare dopo?

I tutorial seguenti coprono argomenti strettamente correlati che si basano sulle tecniche dimostrate in questa guida. Ogni risorsa include esempi di codice completi e funzionanti con spiegazioni passo‑passo per aiutarti a padroneggiare funzionalità API aggiuntive ed esplorare approcci di implementazione alternativi nei tuoi progetti.

- [How to Create PDF417 Barcode with Aspose – Complete Step‑by‑Step Guide](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-with-aspose-complete-step-by-st/)
- [Generate barcode from text using Aspose.BarCode – C# Guide](/barcode/english/net/one-dimensional-barcode-types/generate-barcode-from-text-using-aspose-barcode-c-guide/)
- [How to use Aspose.BarCode to create DataMatrix code text in .NET](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-extended-code-text-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}