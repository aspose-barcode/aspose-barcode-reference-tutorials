---
category: general
date: 2026-10-05
description: Aspose Barcode Generator C# ti consente di aggiungere dati macro e generare
  codici a barre PDF417 senza sforzo. Scopri passo passo come aggiungere metadati
  macro e creare un'immagine PDF417.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- aspose barcode generator c#
- how to add macro
- how to generate pdf417
language: it
lastmod: 2026-10-05
og_description: Aspose Barcode Generator C# ti mostra come aggiungere metadati macro
  e generare un codice a barre PDF417 in poche righe di codice.
og_image_alt: Screenshot of a MacroPdf417 barcode created with Aspose Barcode Generator
  C#
og_title: Generatore di Codici a Barre Aspose C# – aggiungi macro e genera codice
  a barre PDF417
schemas:
- author: Aspose
  dateModified: '2026-10-05'
  description: Aspose Barcode Generator C# lets you add macro data and generate PDF417
    barcodes effortlessly. Learn step‑by‑step how to add macro metadata and create
    a PDF417 image.
  headline: How to use Aspose Barcode Generator C# for a MacroPdf417 barcode
  type: TechArticle
tags:
- barcode
- csharp
- aspose
title: Come utilizzare Aspose Barcode Generator C# per un codice a barre MacroPdf417
url: /it/net/compact-pdf417-encoding/how-to-use-aspose-barcode-generator-c-for-a-macropdf417-barc/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Come utilizzare Aspose Barcode Generator C# per un codice a barre MacroPdf417

Se hai bisogno di creare un codice a barre MacroPdf417 in C#, **Aspose Barcode Generator C#** fornisce un'API concisa che gestisce sia l'immagine del codice a barre sia i metadati macro richiesti. Questo tutorial ti mostra esattamente come aggiungere le informazioni macro e generare un'immagine di codice a barre PDF417 in pochi passaggi.

Imparerai a configurare i parametri visivi, incorporare i campi macro come l'ID file e il timestamp, e salvare il risultato come PNG. Non sono necessari strumenti esterni—solo la libreria Aspose.BarCode e un ambiente di sviluppo .NET.

## Prerequisiti

Prima di iniziare, assicurati di avere:

* .NET 6.0 o successivo installato  
* Visual Studio 2022 (o qualsiasi IDE C#)  
* Una copia con licenza o di valutazione di **Aspose.BarCode for .NET**  

Il codice funziona su Windows, Linux e macOS perché la libreria è indipendente dalla piattaforma.

## Passo 1: Installare il pacchetto NuGet Aspose.BarCode

Apri il tuo progetto in Visual Studio, quindi esegui il seguente comando nella **Package Manager Console**:

```powershell
Install-Package Aspose.BarCode
```

Questo aggiunge l'assembly `Aspose.BarCode` e le sue dipendenze al tuo progetto.

## Passo 2: Creare l'istanza del generatore di codici a barre

La prima riga crea un oggetto `BarcodeGenerator` per la simbologia **MacroPdf417** e fornisce il testo da codificare.

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode.BarCodeImageFormat;

// Step 2: Initialise the generator with MacroPdf417 and the payload text
using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.MacroPdf417, "Åspóse.Barcóde©"))
{
    // subsequent configuration goes here
}
```

*Perché è importante*: il valore `EncodeTypes.MacroPdf417` indica alla libreria di attendersi campi macro‑relativi, che imposterai nel passo successivo.

## Passo 3: Definire l'aspetto visivo

Puoi controllare la dimensione di ogni modulo (il più piccolo quadrato nero o bianco) e il numero di colonne nella matrice PDF417. Modificando `XDimension` influisce sulla risoluzione complessiva dell'immagine.

```csharp
    // Step 3: Visual settings
    generator.Parameters.Barcode.XDimension.Pixels = 2;          // width of a single module
    generator.Parameters.Barcode.Pdf417.Columns = 5;           // number of columns in the symbol
```

Aumentare `Columns` riduce l'altezza del codice a barre, mentre un `XDimension` più grande rende l'immagine più nitida su schermi ad alta DPI.

## Passo 4: Aggiungere i metadati macro (come aggiungere macro)

MacroPdf417 richiede diversi campi aggiuntivi che descrivono il file di origine e la sua segmentazione. Le proprietà seguenti corrispondono direttamente alle specifiche macro PDF417:

```csharp
    // Step 4: Macro fields – how to add macro data
    generator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;               // unique file identifier
    generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;                  // current segment number
    generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;              // total number of segments
    generator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";             // optional file name
    generator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234;                // CCITT‑16 placeholder
    generator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400_000;              // size in bytes
    generator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = 
        new DateTime(2019, 11, 1);                                                   // creation timestamp
    generator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";            // recipient identifier
    generator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";               // sender identifier
    generator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = 
        Pdf417MacroTerminator.Set;                                                   // marks the last segment
```

*Perché questi campi*:  
* `MacroPdf417FileID` collega tutti i segmenti, garantendo che uno scanner possa ricostruire il documento originale.  
* `MacroPdf417SegmentID` e `MacroPdf417SegmentsCount` informano il decoder sull'ordine e sul numero totale di parti.  
* `MacroPdf417FileSize` e `MacroPdf417Checksum` forniscono controlli di integrità, utili per trasferimenti di dati di grandi dimensioni.

## Passo 5: Salvare l'immagine del codice a barre (come generare pdf417)

Infine, scrivi il codice a barre su disco. Il metodo `Save` accetta un percorso file e un formato immagine. PNG preserva i bordi nitidi del codice a barre senza artefatti di compressione.

```csharp
    // Step 5: Save the generated barcode – how to generate pdf417 image
    generator.Save("ExtPDF417Meta.png", BarCodeImageFormat.Png);
}
```

Quando il programma viene eseguito, troverai **ExtPDF417Meta.png** nella cartella di output. Aprendo l'immagine vedrai un codice a barre MacroPdf417 pulito, pronto per la stampa o per l'inserimento in un PDF.

### Output previsto

| Nome file          | Formato | Dimensioni (circa) |
|--------------------|--------|----------------------|
| ExtPDF417Meta.png  | PNG    | 300 × 150 px (varia con `XDimension`) |

Scansionando l'immagine con un lettore compatibile PDF417 (ad esempio, ZXing, Aspose.BarCode for .NET) si ottiene il testo originale **“Åspóse.Barcóde©”** insieme a tutti i campi macro.

## Problemi comuni e come evitarli

| Problema | Perché accade | Soluzione |
|----------|----------------|----------|
| **`EncodeTypes` errato** | Usare `EncodeTypes.Pdf417` invece di `EncodeTypes.MacroPdf417` disabilita i campi macro. | Instanziare sempre il generatore con `EncodeTypes.MacroPdf417`. |
| **Campi macro mancanti** | Alcuni scanner ignorano il codice a barre se i campi macro richiesti sono omessi. | Popolare almeno `FileID`, `SegmentID`, `SegmentsCount` e `Terminator`. |
| **`XDimension` troppo piccolo** | Un valore inferiore a 1 pixel può produrre un codice a barre illeggibile su display a bassa risoluzione. | Mantenere `XDimension` ≥ 2 pixel per la maggior parte degli scenari di schermo e stampa. |
| **Errori di percorso file** | Fornire un percorso relativo che non esiste genera un'eccezione. | Usare `Path.Combine(Environment.CurrentDirectory, "ExtPDF417Meta.png")` o un percorso assoluto. |

## Codice sorgente completo

Di seguito trovi l'esempio completo e eseguibile che puoi copiare in un nuovo progetto console.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode.BarCodeImageFormat;

namespace MacroPdf417Demo
{
    class Program
    {
        static void Main()
        {
            // Initialise the generator with MacroPdf417 and the payload text
            using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.MacroPdf417, "Åspóse.Barcóde©"))
            {
                // Visual appearance
                generator.Parameters.Barcode.XDimension.Pixels = 2;          // module width
                generator.Parameters.Barcode.Pdf417.Columns = 5;           // number of columns

                // Macro fields – how to add macro
                generator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
                generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;
                generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;
                generator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";
                generator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234;
                generator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400_000;
                generator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = new DateTime(2019, 11, 1);
                generator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
                generator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
                generator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;

                // Save the barcode – how to generate pdf417
                generator.Save("ExtPDF417Meta.png", BarCodeImageFormat.Png);
            }

            Console.WriteLine("MacroPdf417 barcode generated successfully.");
        }
    }
}
```

Esegui il programma (`dotnet run`). Dopo l'esecuzione, la console stampa un messaggio di successo e il file PNG appare nella cartella di output del progetto.

## Prossimi passi

* **Codificare dati più grandi** – Incrementa `Columns` o regola `Rows` (tramite `Pdf417.Rows`) per contenere più caratteri.  
* **Incorporare in PDF** – Usa Aspose.PDF per inserire il PNG generato in un documento.  
* **Verifica della scansione** – Utilizza `Aspose.BarCode.Reader` per decodificare il codice a barre e confermare i campi macro programmaticamente.  

Esplorare questi argomenti approfondisce la tua comprensione di **come generare codici a barre PDF417** con informazioni macro ricche e ti prepara a casi d'uso reali come l'elaborazione batch di documenti o lo scambio sicuro di dati.

---

*Buon coding! Se hai trovato utile questa guida, considera di condividerla con i colleghi o di mettere una stella al repository Aspose.BarCode su GitHub.*

## Cosa dovresti imparare dopo?

I seguenti tutorial coprono argomenti strettamente correlati che si basano sulle tecniche dimostrate in questa guida. Ogni risorsa include esempi di codice completi e funzionanti con spiegazioni passo‑passo per aiutarti a padroneggiare funzionalità API aggiuntive ed esplorare approcci di implementazione alternativi nei tuoi progetti.

- [Come creare un codice a barre macro PDF417 in C# usando Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/how-to-create-macro-pdf417-barcode-in-c-using-aspose-barcode/)
- [Come generare un codice a barre PDF417 in C# con Barcode Generator](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-with-barcode-generator/)
- [Esempio Aspose barcode: generare Macro PDF417 in C#](/barcode/english/net/compact-pdf417-encoding/aspose-barcode-example-generate-macro-pdf417-in-c/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}