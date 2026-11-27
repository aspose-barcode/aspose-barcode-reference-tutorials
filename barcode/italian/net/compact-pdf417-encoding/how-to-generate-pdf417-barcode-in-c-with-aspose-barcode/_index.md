---
category: general
date: 2026-11-27
description: Scopri come generare un codice a barre PDF417 in C# usando Aspose.BarCode.
  Regola le dimensioni, imposta il numero di colonne e salva come PNG in poche righe
  di codice.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate PDF417 barcode
- Aspose.BarCode C#
- PDF417 barcode dimensions
- barcode image PNG
- BarcodeGenerator usage
language: it
lastmod: 2026-11-27
og_description: Genera il codice a barre PDF417 in C# istantaneamente. Questo tutorial
  mostra come configurare le dimensioni, il numero di colonne e salvare il risultato
  come immagine PNG.
og_image_alt: Screenshot showing a generated PDF417 barcode saved as a PNG file
og_title: Genera codice a barre PDF417 in C# – guida rapida con Aspose.BarCode
schemas:
- author: Aspose
  dateModified: '2026-11-27'
  description: Learn how to generate PDF417 barcode in C# using Aspose.BarCode. Adjust
    dimensions, set column count, and save as PNG in a few lines of code.
  headline: How to generate PDF417 barcode in C# with Aspose.BarCode
  type: TechArticle
- description: Learn how to generate PDF417 barcode in C# using Aspose.BarCode. Adjust
    dimensions, set column count, and save as PNG in a few lines of code.
  name: How to generate PDF417 barcode in C# with Aspose.BarCode
  steps:
  - name: Why each line matters
    text: '* **BarcodeGenerator** – the core class that creates a barcode image. Passing
      `EncodeTypes.Pdf417` selects the PDF417 symbology. * **XDimension.Pixels** –
      determines the smallest bar width. Smaller values shrink the image; larger values
      improve readability on low‑resolution scanners. * **Pdf417.Colu'
  - name: Changing the encoded data
    text: 'Replace the second argument of `BarcodeGenerator` with any UTF‑8 string,
      e.g.:'
  - name: Adjusting image size without losing quality
    text: 'If you need a larger image for printing, increase `XDimension.Pixels`:'
  - name: Handling very long inputs
    text: 'PDF417 can encode up to 1 850 characters. For extremely long strings, you
      may want to increase the column count:'
  - name: Saving in other formats
    text: 'Aspose.BarCode supports BMP, JPEG, TIFF, and SVG. Change the format like
      this:'
  type: HowTo
tags:
- barcode
- PDF417
- C#
- Aspose
title: Come generare il codice a barre PDF417 in C# con Aspose.BarCode
url: /it/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-with-aspose-barcode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Come generare un codice a barre PDF417 in C# con Aspose.BarCode

Se hai bisogno di **generare un codice a barre PDF417** in un'applicazione .NET, questa guida ti mostra una soluzione concisa, end‑to‑end. Vedrai come creare il codice a barre, regolare le sue dimensioni e scrivere il risultato in un file PNG—tutto con la libreria Aspose.BarCode.

Generare un codice a barre PDF417 è comune quando devi codificare grandi quantità di dati per la scansione su dispositivi mobili, carte d'imbarco o etichette di inventario. Alla fine di questo tutorial avrai un programma console pronto all'uso che produce un'immagine PNG di alta qualità.

## Prerequisiti

Prima di iniziare, assicurati di avere:

* .NET 6.0 SDK o versioni successive installate  
* Una versione recente di **Aspose.BarCode per .NET** (il pacchetto NuGet `Aspose.BarCode`)  
* Un IDE o editor (Visual Studio, VS Code, Rider, ecc.)  

Il codice funziona su Windows, Linux e macOS perché Aspose.BarCode è cross‑platform.

## Passo 1: Creare un nuovo progetto console

Apri un terminale ed esegui:

```bash
dotnet new console -n Pdf417Demo
cd Pdf417Demo
dotnet add package Aspose.BarCode
```

Questo crea un progetto C# minimale chiamato **Pdf417Demo** e aggiunge la dipendenza `Aspose.BarCode`.

## Passo 2: Scrivere il codice di generazione del codice a barre

Apri **Program.cs** e sostituisci il contenuto con il seguente:

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace Pdf417Demo
{
    class Program
    {
        static void Main(string[] args)
        {
            // 1️⃣ Create a PDF417 barcode generator with the desired text
            // EncodeTypes.Pdf417 tells Aspose.BarCode which symbology to use.
            BarcodeGenerator generator = new BarcodeGenerator(
                EncodeTypes.Pdf417, "Sample text for PDF417 barcode");

            // 2️⃣ Adjust barcode dimensions and column count
            // XDimension controls the width of a single module (pixel size).
            // Setting it to 2 pixels yields a compact yet readable barcode.
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // Columns define how many data columns the barcode will have.
            // A value of 3 works well for short strings; increase for longer data.
            generator.Parameters.Barcode.Pdf417.Columns = 3;

            // Optional: increase error correction level for more robust scanning.
            generator.Parameters.Barcode.Pdf417.ErrorCorrectionLevel = 2;

            // 3️⃣ Save the generated barcode as a PNG file
            // The output path can be absolute or relative to the project folder.
            string outputPath = "Pdf417Basic.png";
            generator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"PDF417 barcode saved to '{outputPath}'.");
        }
    }
}
```

### Perché ogni riga è importante

* **BarcodeGenerator** – la classe principale che crea l'immagine del codice a barre. Passare `EncodeTypes.Pdf417` seleziona la simbologia PDF417.  
* **XDimension.Pixels** – determina la larghezza minima della barra. Valori più piccoli riducono l'immagine; valori più grandi migliorano la leggibilità su scanner a bassa risoluzione.  
* **Pdf417.Columns** – controlla il numero di colonne di dati. Più colonne producono un codice più corto ma più alto; meno colonne lo rendono più largo.  
* **ErrorCorrectionLevel** – livelli più alti aggiungono dati ridondanti, rendendo il codice più tollerante ai danni a scapito della dimensione.  
* **Save(..., BarCodeImageFormat.Png)** – scrive l'immagine su disco in formato PNG, un formato loss‑less ideale per ulteriori elaborazioni o per l'inserimento in documenti.

## Passo 3: Compilare ed eseguire il programma

Dal terminale, esegui:

```bash
dotnet run
```

Dovresti vedere:

```
PDF417 barcode saved to 'Pdf417Basic.png'.
```

Un file chiamato **Pdf417Basic.png** appare nella cartella del progetto. Aprirlo mostra un chiaro codice a barre PDF417 che codifica il testo *“Sample text for PDF417 barcode”*.

![Codice a barre PDF417 generato salvato come file PNG](pdf417-barcode-example.png "Codice a barre PDF417 generato in formato PNG")

*Testo alternativo dell'immagine: screenshot di un codice a barre PDF417 generato salvato come file PNG, che dimostra il risultato del tutorial su come generare un codice a barre PDF417.*

## Passo 4: Varianti comuni e casi limite

### Modificare i dati codificati

Sostituisci il secondo argomento di `BarcodeGenerator` con qualsiasi stringa UTF‑8, ad esempio:

```csharp
new BarcodeGenerator(EncodeTypes.Pdf417, "https://example.com/checkout?order=12345")
```

Il generatore suddivide automaticamente i dati tra righe e colonne.

### Regolare la dimensione dell'immagine senza perdere qualità

Se ti serve un'immagine più grande per la stampa, aumenta `XDimension.Pixels`:

```csharp
generator.Parameters.Barcode.XDimension.Pixels = 4; // double the module width
```

### Gestire input molto lunghi

PDF417 può codificare fino a 1 850 caratteri. Per stringhe estremamente lunghe, potresti voler aumentare il numero di colonne:

```csharp
generator.Parameters.Barcode.Pdf417.Columns = 5; // more columns, less height
```

Se il contenuto supera la capacità massima, Aspose.BarCode lancia un `ArgumentException`. Avvolgi il codice di generazione in un blocco try‑catch per mostrare un messaggio di errore più amichevole.

### Salvataggio in altri formati

Aspose.BarCode supporta BMP, JPEG, TIFF e SVG. Cambia il formato così:

```csharp
generator.Save("Pdf417Vector.svg", BarCodeImageFormat.Svg);
```

## Passo 5: Verificare il codice a barre

Puoi confermare che il codice a barre è valido scansionandolo con qualsiasi app lettore PDF417 (ad es., app per fotocamera smartphone che supportano la scansione di codici a barre). Il testo decodificato dovrebbe corrispondere alla stringa passata al generatore.

Se la scansione fallisce:

* Assicurati che l'immagine non sia compressa (usa PNG o SVG lossless).  
* Verifica che `ErrorCorrectionLevel` sia sufficientemente alto per l'ambiente previsto.  
* Controlla che le dimensioni del codice a barre siano appropriate per la risoluzione dello scanner.

## Conclusione

Ora sai come **generare un codice a barre PDF417** in C# usando Aspose.BarCode, personalizzare le sue dimensioni, impostare il numero di colonne e esportare il risultato come immagine PNG. Questo approccio funziona per una vasta gamma di scenari, dal ticketing mobile alla gestione dell'inventario.

Successivamente, potresti esplorare:

* **Lettura** di un codice a barre PDF417 con `BarCodeReader`.  
* Generare altre simbologie come QR Code o DataMatrix.  
* Incorporare il PNG in PDF, report o pagine web.  

Sentiti libero di sperimentare con diversi livelli di correzione errori, formati immagine e payload di dati per adattarli alle esigenze del tuo progetto. Buona programmazione!

## Cosa dovresti imparare dopo?

I tutorial seguenti trattano argomenti strettamente correlati che si basano sulle tecniche dimostrate in questa guida. Ogni risorsa include esempi di codice completi e funzionanti con spiegazioni passo‑passo per aiutarti a padroneggiare ulteriori funzionalità dell'API e a esplorare approcci di implementazione alternativi nei tuoi progetti.

- [How to generate PDF417 barcode in C# with Aspose.BarCode BarcodeGenerator](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-with-barcodegenerator/)
- [How to generate PDF417 barcode and render it as PNG](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-and-render-it-as-png/)
- [How to generate PDF417 barcode in C# and set barcode size](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-and-set-barcode-size/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}