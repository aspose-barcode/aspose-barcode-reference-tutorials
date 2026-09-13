---
category: general
date: 2026-09-13
description: Scopri come creare un'immagine di codice a barre PDF417 in C# usando
  BarcodeGenerator e le opzioni Macro PDF417. Codice passo‑passo, consigli e esempio
  completo.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create PDF417 barcode image
- macro PDF417 options
- BarcodeGenerator class
- C# barcode generation
- barcode image format
language: it
lastmod: 2026-09-13
og_description: Crea un'immagine di codice a barre PDF417 in C# con BarcodeGenerator.
  Segui questo tutorial dettagliato per configurare le opzioni Macro PDF417 e salvare
  un codice a barre PNG.
og_image_alt: Screenshot of a generated PDF417 barcode image created with C# code
og_title: Crea immagine di codice a barre PDF417 in C# – guida completa
schemas:
- author: Aspose
  dateModified: '2026-09-13'
  description: Learn how to create PDF417 barcode image in C# using BarcodeGenerator
    and Macro PDF417 options. Step‑by‑step code, tips, and full example.
  headline: How to create PDF417 barcode image in C# with Macro PDF417 options
  type: TechArticle
- description: Learn how to create PDF417 barcode image in C# using BarcodeGenerator
    and Macro PDF417 options. Step‑by‑step code, tips, and full example.
  name: How to create PDF417 barcode image in C# with Macro PDF417 options
  steps:
  - name: '**Create the generator** – instantiate `BarcodeGenerator` with `EncodeTypes.MacroPdf417`
      and the data you want to encode.'
    text: '**Create the generator** – instantiate `BarcodeGenerator` with `EncodeTypes.MacroPdf417`
      and the data you want to encode.'
  - name: '**Define the module size** – set `XDimension.Pixels` to control the physical
      width of each barcode element.'
    text: '**Define the module size** – set `XDimension.Pixels` to control the physical
      width of each barcode element.'
  - name: '**Configure Macro PDF417 options** – specify columns, file identifiers,
      segment numbers, and optional checksum.'
    text: '**Configure Macro PDF417 options** – specify columns, file identifiers,
      segment numbers, and optional checksum.'
  - name: '**Save the barcode** – write the generated image to disk using a supported
      **barcode image format** such as PNG.'
    text: '**Save the barcode** – write the generated image to disk using a supported
      **barcode image format** such as PNG.'
  - name: Create a new .NET 6 (or later) console project.
    text: Create a new .NET 6 (or later) console project.
  - name: Add the Aspose.BarCode NuGet package (`dotnet add package Aspose.BarCode`).
    text: Add the Aspose.BarCode NuGet package (`dotnet add package Aspose.BarCode`).
  - name: Replace the generated `Program.cs` with the code above.
    text: Replace the generated `Program.cs` with the code above.
  - name: Adjust `outputPath` to a folder you have write access to.
    text: Adjust `outputPath` to a folder you have write access to.
  - name: Build and run – the console will confirm the image location.
    text: Build and run – the console will confirm the image location.
  type: HowTo
tags:
- PDF417
- C#
- Barcode
title: Come creare un'immagine di codice a barre PDF417 in C# con opzioni Macro PDF417
url: /it/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-image-in-c-with-macro-pdf417-op/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Come creare un'immagine di codice a barre PDF417 in C# con le opzioni Macro PDF417

Se hai bisogno di **creare un'immagine di codice a barre PDF417** in C#, questa guida ti mostra esattamente come farlo usando la **classe BarcodeGenerator**. Che tu stia costruendo un sistema di tracciamento dei documenti o codificando file di grandi dimensioni, le istruzioni passo‑passo qui sotto coprono tutto, dalla configurazione delle opzioni Macro PDF417 al salvataggio del PNG finale.

Generare un codice a barre è semplice una volta compresi i parametri chiave. In questo tutorial imparerai a:

* Inizializzare un `BarcodeGenerator` per **Macro PDF417**.  
* Regolare la dimensione del modulo del codice a barre (`XDimension`).  
* Configurare le impostazioni specifiche del segmento come ID file, ID segmento e checksum.  
* Salvare il risultato in un **formato immagine del codice a barre** (PNG) che può essere visualizzato in qualsiasi interfaccia utente.

L'unico prerequisito è un ambiente di sviluppo .NET (Visual Studio 2022 o successivo) e il pacchetto NuGet Aspose.BarCode per .NET, che fornisce l'API `BarcodeGenerator` utilizzata negli esempi.

---

## Come creare un'immagine di codice a barre PDF417 in C# – panoramica

Creare un'immagine di codice a barre PDF417 consiste in quattro passaggi logici:

1. **Crea il generatore** – istanzia `BarcodeGenerator` con `EncodeTypes.MacroPdf417` e i dati che desideri codificare.  
2. **Definisci la dimensione del modulo** – imposta `XDimension.Pixels` per controllare la larghezza fisica di ogni elemento del codice a barre.  
3. **Configura le opzioni Macro PDF417** – specifica colonne, identificatori di file, numeri di segmento e checksum opzionale.  
4. **Salva il codice a barre** – scrivi l'immagine generata su disco usando un **formato immagine del codice a barre** supportato, come PNG.

Ogni passaggio è spiegato in dettaglio di seguito, con codice C# completo e eseguibile.

---

## Passo 1: Inizializzare il BarcodeGenerator per Macro PDF417

La prima riga crea un oggetto `BarcodeGenerator` che sa di dover produrre un codice a barre **Macro PDF417**. Il costruttore accetta due argomenti: il tipo di codifica e la stringa di dati grezzi.

```csharp
using Aspose.BarCode.Generation;   // NuGet: Aspose.BarCode
using System.Drawing.Imaging;      // For ImageFormat if you prefer System.Drawing

// Step 1 – create a barcode generator for Macro PDF417
using (var barcodeGenerator = new BarcodeGenerator(EncodeTypes.MacroPdf417, "Sample data"))
{
    // Subsequent configuration goes here
}
```

**Perché è importante:**  
`EncodeTypes.MacroPdf417` indica alla libreria di trattare il codice a barre come un contenitore multi‑segmento, fondamentale quando è necessario suddividere un file grande in più simboli. L'istanza `BarcodeGenerator` è disposable, quindi il blocco `using` garantisce che tutte le risorse non gestite vengano rilasciate dopo il salvataggio dell'immagine.

---

## Passo 2: Impostare la dimensione del modulo del codice a barre (XDimension)

`XDimension` controlla la larghezza in pixel di un singolo modulo del codice a barre (la barra nera o bianca più piccola). Un valore di **2 pixel** produce un'immagine compatta ma leggibile.

```csharp
    // Step 2 – define the size of each barcode module (pixel width)
    barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

**Consiglio pratico:**  
Se la stampante di destinazione ha una bassa risoluzione DPI, aumenta il conteggio dei pixel (ad es., `3` o `4`) per evitare sbavature. Al contrario, per la visualizzazione su schermo puoi mantenerlo basso per ridurre le dimensioni del file.

---

## Passo 3: Configurare le opzioni specifiche di Macro PDF417

Macro PDF417 aggiunge metadati che consentono a uno scanner di ricostruire il file originale da più segmenti di codice a barre. Le opzioni più comuni sono:

| Proprietà | Significato |
|----------|------------|
| `Columns` | Numero di colonne in ogni simbolo (influisce sulla larghezza). |
| `MacroPdf417FileID` | Identificatore unico per l'intero file. |
| `MacroPdf417SegmentID` | Indice del segmento corrente (parte da 1). |
| `MacroPdf417SegmentsCount` | Numero totale di segmenti che compongono il file. |
| `MacroPdf417FileName` | Nome originale del file (opzionale, per visualizzazione). |
| `MacroPdf417Checksum` | Checksum opzionale a 16 bit per la verifica dell'integrità. |

```csharp
    // Step 3 – configure Macro PDF417 specific options
    barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 5;                     // Number of columns in the symbol
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;    // Unique file identifier
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 1;       // Current segment number
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 10; // Total number of segments
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "report.pdf"; // Original file name
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 0x1A2B;    // Optional checksum
```

**Perché queste impostazioni sono importanti:**  
- **Columns** influisce sulla leggibilità e sulle dimensioni complessive dell'immagine.  
- **FileID** deve essere lo stesso in tutti i segmenti affinché il decoder sappia che appartengono insieme.  
- **SegmentID** e **SegmentsCount** consentono allo scanner di ordinare correttamente i pezzi.  
- **FileName** e **Checksum** sono opzionali ma migliorano l'esperienza utente e l'integrità dei dati.

**Caso limite:** Se generi più di 999 segmenti, il campo `SegmentID` trabocca; in tal caso suddividi i dati in più file.

---

## Passo 4: Salvare il codice a barre generato come immagine PNG

L'ultimo passaggio scrive il codice a barre su disco. `BarCodeImageFormat.Png` produce un'immagine loss‑less che funziona su piattaforme web, desktop e mobile.

```csharp
    // Step 4 – save the generated barcode as a PNG image
    barcodeGenerator.Save("YOUR_DIRECTORY/MacroPdf417.png", BarCodeImageFormat.Png);
}
```

**Formati alternativi:**  
Puoi sostituire `BarCodeImageFormat.Png` con `Jpeg`, `Bmp` o `Gif` se il tuo sistema a valle richiede un formato specifico. Tieni presente che JPEG introduce artefatti di compressione che possono ridurre l'affidabilità della scansione.

**Output previsto:**  
Il file `MacroPdf417.png` conterrà un codice a barre PDF417 multi‑segmento ad alto contrasto. Quando aperto, dovrebbe apparire simile all'illustrazione qui sotto.

![Esempio di creazione immagine di codice a barre PDF417](image.png){: .align-center alt="Esempio di creazione immagine di codice a barre PDF417 generato dal codice C#"}

---

## Codice sorgente completo – pronto da copiare ed eseguire

Di seguito trovi il programma completo e autonomo. Include le direttive `using` necessarie, il metodo `Main` e commenti che spiegano ogni riga non ovvia.

```csharp
using System;
using Aspose.BarCode.Generation;   // Install-Package Aspose.BarCode
// No other external dependencies are required.

namespace Pdf417BarcodeDemo
{
    class Program
    {
        static void Main(string[] args)
        {
            // Data to encode – can be any UTF‑8 string up to 1,800 characters.
            const string dataToEncode = "Sample data";

            // Output directory – change this to a valid path on your machine.
            const string outputPath = @"C:\Barcodes\MacroPdf417.png";

            // Create a BarcodeGenerator for Macro PDF417.
            using (var barcodeGenerator = new BarcodeGenerator(EncodeTypes.MacroPdf417, dataToEncode))
            {
                // 1️⃣ Define module size (pixel width of each bar).
                barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;

                // 2️⃣ Configure Macro PDF417 options.
                barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 5;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 1;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 10;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "report.pdf";
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 0x1A2B;

                // 3️⃣ Save the barcode as a PNG image.
                barcodeGenerator.Save(outputPath, BarCodeImageFormat.Png);
            }

            Console.WriteLine($"PDF417 barcode image created at: {outputPath}");
        }
    }
}
```

**Esecuzione del programma:**  

1. Crea un nuovo progetto console .NET 6 (o successivo).  
2. Aggiungi il pacchetto NuGet Aspose.BarCode (`dotnet add package Aspose.BarCode`).  
3. Sostituisci il file `Program.cs` generato con il codice sopra.  
4. Modifica `outputPath` puntando a una cartella in cui hai i permessi di scrittura.  
5. Compila ed esegui – la console confermerà la posizione dell'immagine.

---

## Domande frequenti e risoluzione dei problemi

| Domanda | Risposta |
|----------|--------|
| *E se il codice a barre è troppo largo per la mia etichetta?* | Riduci `Columns` o aumenta `XDimension.Pixels` per bilanciare larghezza e leggibilità. |
| *Devo impostare un checksum?* | Il checksum è opzionale |

## Cosa dovresti imparare dopo?

I tutorial seguenti coprono argomenti strettamente correlati che si basano sulle tecniche dimostrate in questa guida. Ogni risorsa include esempi di codice completi e funzionanti con spiegazioni passo‑passo per aiutarti a padroneggiare funzionalità API aggiuntive ed esplorare approcci di implementazione alternativi nei tuoi progetti.

- [Crea codice a barre PDF417 in C# – Guida completa passo‑passo](/barcode/english/net/compact-pdf417-encoding/create-pdf417-barcode-in-c-complete-step-by-step-guide/)
- [Crea metadati del codice a barre PDF417 in C# – Guida completa passo‑passo](/barcode/english/net/compact-pdf417-encoding/create-pdf417-barcode-metadata-in-c-complete-step-by-step-gu/)
- [Genera codice a barre con testo – Guida completa PDF417 Macro](/barcode/english/net/compact-pdf417-encoding/generate-barcode-with-text-full-pdf417-macro-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}