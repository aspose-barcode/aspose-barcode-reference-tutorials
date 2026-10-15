---
category: general
date: 2026-10-15
description: Crea un PNG di codice a barre in C# con un esempio compatto di PDF417
  – scopri come impostare le colonne, regolare le dimensioni e generare l'immagine.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode png
- how to create barcode
- how to set columns
- c# barcode example
language: it
lastmod: 2026-10-15
og_description: Crea un PNG di codice a barre in C# con un esempio compatto di PDF417.
  Questa guida mostra come impostare le colonne, regolare le dimensioni e salvare
  l'immagine.
og_image_alt: Screenshot showing a generated barcode PNG created with C#
og_title: Crea barcode PNG in C# – tutorial completo di programmazione
schemas:
- author: Aspose
  dateModified: '2026-10-15'
  description: Create barcode PNG in C# with a compact PDF417 example – learn how
    to set columns, adjust dimensions, and generate the image.
  headline: How to create barcode PNG in C# – step‑by‑step guide
  type: TechArticle
- description: Create barcode PNG in C# with a compact PDF417 example – learn how
    to set columns, adjust dimensions, and generate the image.
  name: How to create barcode PNG in C# – step‑by‑step guide
  steps:
  - name: Initialise the barcode generator with the desired text
    text: '```csharp using Aspose.BarCode.Generation;'
  - name: Set the module (X) dimension in pixels
    text: '```csharp // Set the width of the smallest bar (module) to 2 pixels generator.Parameters.Barcode.XDimension.Pixels
      = 2; ```'
  - name: Define the number of columns for the PDF417 barcode
    text: '```csharp // Specify that the barcode should use 3 columns generator.Parameters.Barcode.Pdf417.Columns
      = 3; ```'
  - name: Enable the compact layout by truncating the barcode
    text: '```csharp // Truncate removes unnecessary empty rows, making the barcode
      shorter generator.Parameters.Barcode.Pdf417.Truncate = true; ```'
  - name: Save the barcode image as PNG
    text: '```csharp // Choose the output folder and file name string outputPath =
      Path.Combine(Environment.CurrentDirectory, "CompactPdf417.png");'
  - name: Full, runnable example
    text: 'Putting everything together, here is a self‑contained program you can copy,
      paste, and run:'
  type: HowTo
tags:
- barcode
- C#
- PDF417
- image generation
title: Come creare un PNG di codice a barre in C# – guida passo passo
url: /it/net/compact-pdf417-encoding/how-to-create-barcode-png-in-c-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Come creare barcode PNG in C# – guida passo‑passo

Se hai bisogno di **creare file barcode PNG** dal codice C#, questo tutorial ti mostra una soluzione completa in poche righe. Vedrai come impostare le colonne, regolare la dimensione del modulo e salvare un barcode PDF417 compatto come immagine PNG—tutto con un unico esempio chiaro e leggibile.

Generare barcode programmaticamente elimina il passaggio manuale di utilizzo di un editor grafico e ti consente di incorporare i barcode direttamente in fatture, ticket o etichette di inventario. Nelle sezioni successive copriremo tutto ciò che devi sapere su **come creare barcode**, perché ogni configurazione è importante e come adattare il codice a diversi casi d'uso.

## Prerequisiti

Prima di iniziare, assicurati di avere:

* .NET 6.0 o successivo (il codice funziona anche con .NET Framework 4.7+)
* Un riferimento a una libreria barcode che supporti PDF417, come **Aspose.BarCode for .NET** o **IronBarcode**. L'esempio utilizza Aspose.BarCode, che puoi installare tramite NuGet:

```bash
dotnet add package Aspose.BarCode
```

* Familiarità di base con la sintassi C# e Visual Studio (o qualsiasi IDE tu preferisca).

> **Suggerimento:** Se preferisci un'alternativa gratuita, la libreria open‑source **ZXing.Net** supporta anche PDF417, ma i nomi delle proprietà differiscono leggermente. I concetti mostrati qui rimangono gli stessi.

## Come creare barcode PNG in C# (passo principale)

Il cuore della soluzione è un oggetto `BarcodeGenerator` configurato per la codifica PDF417. Le sezioni seguenti scompongono ogni riga di codice, spiegano **come impostare le colonne** e mostrano perché le impostazioni influenzano le dimensioni finali del PNG.

### Passo 1: Inizializzare il generatore di barcode con il testo desiderato

```csharp
using Aspose.BarCode.Generation;

// The text you want to encode in the barcode
string barcodeText = "Compact example";

// Create a generator for PDF417 barcodes
using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, barcodeText))
{
    // Subsequent configuration goes here
}
```

*Perché è importante*: L'enumerazione `EncodeTypes.Pdf417` indica alla libreria di produrre un barcode bidimensionale impilato. Il costruttore accetta anche i dati da codificare, così non è necessario chiamare separatamente `SetData`.

### Passo 2: Impostare la dimensione del modulo (X) in pixel

```csharp
// Set the width of the smallest bar (module) to 2 pixels
generator.Parameters.Barcode.XDimension.Pixels = 2;
```

La **dimensione X** controlla la densità visiva del barcode. Un valore più piccolo genera un'immagine più compatta, utile quando serve un PNG ridotto per schermi mobili o spazi di stampa limitati.

### Passo 3: Definire il numero di colonne per il barcode PDF417

```csharp
// Specify that the barcode should use 3 columns
generator.Parameters.Barcode.Pdf417.Columns = 3;
```

Questa riga dimostra **come impostare le colonne**. PDF417 può scegliere automaticamente il numero ottimale di colonne, ma impostarlo esplicitamente ti garantisce una larghezza prevedibile, soprattutto quando inserisci il PNG in un layout a dimensione fissa.

### Passo 4: Abilitare il layout compatto troncando il barcode

```csharp
// Truncate removes unnecessary empty rows, making the barcode shorter
generator.Parameters.Barcode.Pdf417.Truncate = true;
```

Quando `Truncate` è true, la libreria rimuove le righe finali che non contengono dati, riducendo l'altezza complessiva dell'immagine senza perdere informazioni.

### Passo 5: Salvare l'immagine del barcode come PNG

```csharp
// Choose the output folder and file name
string outputPath = Path.Combine(Environment.CurrentDirectory, "CompactPdf417.png");

// Save the generated barcode as a PNG file
generator.Save(outputPath, BarCodeImageFormat.Png);
```

Il metodo `Save` scrive il barcode su disco nel formato specificato. PNG è loss‑less, ideale per applicazioni di scansione che richiedono un rilevamento dei bordi preciso.

### Esempio completo, eseguibile

Mettendo tutto insieme, ecco un programma autonomo che puoi copiare, incollare ed eseguire:

```csharp
using System;
using System.IO;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // 1️⃣ Initialise the generator with the data to encode
        string barcodeText = "Compact example";

        using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, barcodeText))
        {
            // 2️⃣ Set module width to 2 pixels for a tighter image
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // 3️⃣ Explicitly set the number of columns (how to set columns)
            generator.Parameters.Barcode.Pdf417.Columns = 3;

            // 4️⃣ Enable compact layout by truncating empty rows
            generator.Parameters.Barcode.Pdf417.Truncate = true;

            // 5️⃣ Define the output path and save as PNG (create barcode PNG)
            string outputPath = Path.Combine(Directory.GetCurrentDirectory(), "CompactPdf417.png");
            generator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"Barcode PNG saved to: {outputPath}");
        }
    }
}
```

**Output previsto** – Dopo aver eseguito il programma, troverai `CompactPdf417.png` nella cartella di esecuzione. L'immagine contiene un barcode PDF417 a tre colonne abbastanza compatto da stare su un'etichetta standard 2 × 2 cm, mantenendo piena leggibilità.

![Create barcode PNG example](placeholder.png){alt="Crea barcode PNG usando C#"}

## Come impostare le colonne per diverse dimensioni di dati (keyword secondaria)

Il numero di colonne influisce sia sulla larghezza sia sulla leggibilità del barcode:

| Colonne | Larghezza approssimativa (px) | Caso d'uso tipico |
|--------|-------------------------------|-------------------|
| 1‑2    | Stretta, alta                 | Piccoli tag, stampe tipo RFID |
| 3‑5    | Bilanciata                    | Etichette generiche |
| 6‑9    | Larga, corta                  | Poster grandi o confezioni |

Se la tua stringa di dati cresce, la libreria può aumentare automaticamente il conteggio delle righe per mantenere il barcode entro il limite di colonne. Tuttavia, forzare un numero di colonne troppo basso può rendere il barcode eccessivamente alto, rischiando di non stare su una stampante di ricevute. Regola il conteggio delle colonne in base ai vincoli fisici del supporto di output.

## Come creare immagini barcode in altri formati (keyword secondaria)

Mentre PNG è il formato più comune per web e mobile, potresti aver bisogno di **come creare barcode** in JPEG, BMP o SVG per flussi di lavoro specializzati:

```csharp
// Save as JPEG with 90 % quality
generator.Save("CompactPdf417.jpg", BarCodeImageFormat.Jpeg, 90);

// Save as SVG (vector, infinite scaling)
generator.Save("CompactPdf417.svg", BarCodeImageFormat.Svg);
```

Scegliere il formato giusto dipende dal consumatore finale:

* **PNG** – lossless, ideale per scanner.
* **JPEG** – dimensione file più piccola, accettabile quando sono tollerabili lievi artefatti di compressione.
* **SVG** – perfetto per stampa ad alta risoluzione o scaling UI.

## Esempio C# barcode: gestione di errori e casi limite

Un **c# barcode example** robusto dovrebbe anticipare problemi a runtime:

```csharp
try
{
    // All configuration steps as shown earlier
    generator.Save(outputPath, BarCodeImageFormat.Png);
}
catch (ArgumentException ex)
{
    Console.Error.WriteLine($"Invalid barcode parameter: {ex.Message}");
}
catch (IOException ex)
{
    Console.Error.WriteLine($"Failed to write file: {ex.Message}");
}
```

*Perché avvolgere in `try/catch`?* Caratteri non validi nel testo, dimensioni non supportate o problemi di permessi di scrittura genereranno eccezioni. Gestirle in modo appropriato impedisce al tuo applicativo di bloccarsi durante elaborazioni batch.

## Estendere l'esempio: aggiungere un logo o uno sfondo

Molti scenari reali richiedono una sovrapposizione di logo o uno sfondo colorato. L'API Aspose.BarCode ti permette di combinare il barcode con una bitmap:

```csharp
// Load a logo image
using (Bitmap logo = (Bitmap)Image.FromFile("logo.png"))
{
    generator.Parameters.Barcode.ImageFormat = BarCodeImageFormat.Png;
    generator.Parameters.Barcode.Pdf417.EnablePdf417CodewordCount = true; // optional

    // Merge the logo with the barcode (centered)
    generator.Save("BarcodeWithLogo.png", BarCodeImageFormat.Png, logo);
}
```

Questa tecnica mantiene intatto il flusso **create barcode PNG** aggiungendo al contempo un tocco di branding visivo all'immagine finale.

## Riepilogo

In questa guida abbiamo dimostrato come **creare barcode PNG** in C# usando una configurazione PDF417 compatta. Hai imparato:

* Il codice esatto per inizializzare un `BarcodeGenerator`.
* **Come impostare le colonne** e perché il conteggio è importante per dimensione e leggibilità.
* Come regolare la dimensione X e abilitare il troncamento per un PNG più stretto.
* Modi per salvare l'immagine in PNG, JPEG o SVG.
* Pattern di gestione errori per un **c# barcode example** pronto per la produzione.
* Estensioni opzionali come logo overlay e personalizzazione dello sfondo.

Ora disponi di uno snippet pronto all'uso da integrare in generatori di fatture, sistemi di ticketing o strumenti di gestione inventario. Sperimenta con valori di colonna diversi, dimensioni del modulo o tipi di barcode (es. QR, Code128) per vedere come cambia l'immagine.

## Prossimi passi

* Esplora altri tipi di codifica (`EncodeTypes.QR`, `EncodeTypes.Code128`) per coprire più casi d'uso.
* Combina la generazione di barcode con librerie di creazione PDF (es. **iTextSharp**) per incorporare il PNG direttamente nei documenti.
* Indaga sul dimensionamento dinamico: calcola il numero ottimale di colonne in base alla lunghezza della stringa di input e alle dimensioni dell'etichetta target.

Buona programmazione e goditi la semplicità di generare barcode PNG nitidi in C# in modo programmatico!

## Cosa dovresti imparare dopo?

I tutorial seguenti trattano argomenti strettamente correlati che si basano sulle tecniche dimostrate in questa guida. Ogni risorsa include esempi di codice completi con spiegazioni passo‑passo per aiutarti a padroneggiare funzionalità API aggiuntive ed esplorare approcci di implementazione alternativi nei tuoi progetti.

- [How to create PDF417 barcode and save it as PNG in C#](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-and-save-it-as-png-in-c/)
- [How to create PDF417 barcode and set its size in C#](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-and-set-its-size-in-c/)
- [How to create PDF417 barcode in C# with compact mode](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-in-c-with-compact-mode/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}