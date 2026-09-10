---
category: general
date: 2026-09-10
description: Scopri come decodificare i codici a barre da un'immagine usando un esempio
  conciso di lettore di codici a barre in C# che legge i codici Macro PDF417 in poche
  righe.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- decode barcode from image
- c# barcode reader example
- read barcode C#
- barcode decoding tutorial
- Macro PDF417 C#
language: it
lastmod: 2026-09-10
og_description: Decodifica il codice a barre da un'immagine usando un breve esempio
  di lettore di codici a barre in C#. Segui la guida passo‑passo per leggere i dati
  Macro PDF417 istantaneamente.
og_image_alt: Screenshot of console output showing decoded Macro PDF417 barcode information
og_title: Decodifica il codice a barre da un'immagine con un esempio di lettore di
  codici a barre in C#
schemas:
- author: Aspose
  dateModified: '2026-09-10'
  description: Learn how to decode barcode from image using a concise C# barcode reader
    example that reads Macro PDF417 codes in just a few lines.
  headline: Decode barcode from image with a C# barcode reader example
  type: TechArticle
- description: Learn how to decode barcode from image using a concise C# barcode reader
    example that reads Macro PDF417 codes in just a few lines.
  name: Decode barcode from image with a C# barcode reader example
  steps:
  - name: '**Initialize** a `BarCodeReader` for the target image.'
    text: '**Initialize** a `BarCodeReader` for the target image.'
  - name: '**Iterate** over every detected barcode.'
    text: '**Iterate** over every detected barcode.'
  - name: '**Print** the standard and extended Macro PDF417 data.'
    text: '**Print** the standard and extended Macro PDF417 data.'
  type: HowTo
tags:
- barcode
- C#
- image processing
title: Decodifica il codice a barre da un'immagine con un esempio di lettore di codici
  a barre in C#
url: /it/net/compact-pdf417-encoding/decode-barcode-from-image-with-a-c-barcode-reader-example/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Decodifica il codice a barre da immagine con un esempio di lettore di codici a barre C#

Se hai bisogno di **decodificare un codice a barre da immagine**, questa guida ti mostra esattamente come farlo in C#. Utilizzando un **esempio compatto di lettore di codici a barre C#**, leggerai i dati Macro PDF417 con poche righe di codice.

Vedrai un programma completo e eseguibile, comprenderai perché ogni parte è importante e imparerai consigli che evitano gli errori più comuni. Non è necessaria alcuna documentazione esterna—tutto ciò che ti serve è qui.

## Cosa imparerai

- Configurare il pacchetto NuGet necessario per la decodifica dei codici a barre.  
- Scrivere un **esempio di lettore di codici a barre C#** che apre un file immagine ed estrae ogni codice a barre.  
- Accedere ai campi estesi Macro PDF417 come l'ID del file.  
- Verificare l'output e adattare il codice ad altri tipi di codici a barre.

### Prerequisiti

- SDK .NET 6.0 o successivo (il codice funziona anche con .NET Core 3.1 e .NET Framework 4.7+).  
- Familiarità di base con le applicazioni console C#.  
- Un file immagine che contiene un codice a barre Macro PDF417 (ad es., `MacroPdf417.png`).  

## Passo 1: Installa la libreria per i codici a barre

L'esempio utilizza **Aspose.BarCode for .NET**, una libreria ampiamente usata che supporta la decodifica Macro PDF417.

```bash
dotnet add package Aspose.BarCode
```

> **Perché questa libreria?**  
> Fornisce una singola classe `BarCodeReader` che gestisce molti formati, offre alta precisione e restituisce informazioni estese per i codici Macro PDF417—tutto senza configurazioni aggiuntive.

## Passo 2: Crea un esempio di lettore di codici a barre C#

Crea un nuovo progetto console e sostituisci il file `Program.cs` generato con il codice qui sotto. L'esempio segue tre azioni chiare:

1. **Inizializzare** un `BarCodeReader` per l'immagine di destinazione.  
2. **Iterare** su ogni codice a barre rilevato.  
3. **Stampare** i dati standard ed estesi Macro PDF417.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

namespace BarcodeDemo
{
    internal class Program
    {
        private static void Main()
        {
            // Path to the image that contains the Macro PDF417 barcode
            const string imagePath = "YOUR_DIRECTORY/MacroPdf417.png";

            // 1️⃣ Create a BarCodeReader configured for Macro PDF417 decoding
            using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
            {
                // 2️⃣ Read all barcodes found in the image
                foreach (BarCodeResult result in reader.ReadBarCodes())
                {
                    // 3️⃣ Display basic information
                    Console.WriteLine($"Code Type: {result.CodeTypeName}");
                    Console.WriteLine($"Code Text: {result.CodeText}");

                    // 3️⃣ Display Macro PDF417 extended fields (if available)
                    if (result.Extended?.Pdf417?.MacroPdf417FileID != null)
                    {
                        Console.WriteLine($"Macro PDF417 File ID: {result.Extended.Pdf417.MacroPdf417FileID}");
                    }

                    Console.WriteLine(new string('-', 40));
                }
            }
        }
    }
}
```

### Spiegazione di ogni sezione

- **Costruttore `BarCodeReader`** – Il primo argomento è il percorso dell'immagine; il secondo indica alla libreria di cercare specificamente i codici Macro PDF417. Questa decodifica mirata migliora le prestazioni rispetto alla scansione di tutti i formati possibili.  
- **`ReadBarCodes()`** – Restituisce un enumerabile di tutti i codici a barre rilevati nell'immagine, consentendo di gestire più codici in un unico file.  
- **`result.Extended.Pdf417.MacroPdf417FileID`** – Macro PDF417 memorizza metadati aggiuntivi (ID file, conteggio segmenti, ecc.). L'esempio verifica se è null per evitare una `NullReferenceException` quando l'immagine contiene un codice non‑Macro.

## Passo 3: Esegui il programma e verifica l'output

Compila ed esegui l'applicazione console:

```bash
dotnet run
```

Dovresti vedere un output simile a:

```
Code Type: MacroPdf417
Code Text: 1234567890ABCDEF
Macro PDF417 File ID: 42
----------------------------------------
```

Se l'immagine non contiene un codice a barre Macro PDF417, il programma elencherà comunque gli altri formati rilevati, ma il campo esteso verrà omesso.

## Suggerimento professionale: Decodifica altri tipi di codici a barre senza modificare molto il codice

Per **decodificare un codice a barre da immagine** per un formato diverso, cambia il valore dell'enumerazione `DecodeType`:

```csharp
using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.QR))
```

Puoi anche passare `DecodeType.AllSupportedTypes` per consentire alla libreria di rilevare qualsiasi codice a barre conosca.

## Problemi comuni e come evitarli

| Sintomo | Causa | Correzione |
|---------|-------|------------|
| Nessun output | Percorso immagine errato o formato file non supportato | Verifica il percorso, assicurati che il file sia un'immagine supportata (PNG, JPEG, BMP) |
| `result.Extended` è null per Macro PDF417 | Il codice a barre non è una variante Macro PDF417 | Conferma che l'immagine di origine contenga effettivamente un codice Macro PDF417 |
| Eccezione `System.IO.FileNotFoundException` | Pacchetto NuGet mancante a runtime | Esegui `dotnet restore` e assicurati che `Aspose.BarCode.dll` sia copiato nella cartella di output |

## Elenco completo del sorgente per copia‑incolla veloce

Di seguito trovi l'intero programma, pronto per essere copiato in `Program.cs`. Non sono necessari file aggiuntivi.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

namespace BarcodeDemo
{
    internal class Program
    {
        private static void Main()
        {
            const string imagePath = "YOUR_DIRECTORY/MacroPdf417.png";

            using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
            {
                foreach (BarCodeResult result in reader.ReadBarCodes())
                {
                    Console.WriteLine($"Code Type: {result.CodeTypeName}");
                    Console.WriteLine($"Code Text: {result.CodeText}");

                    if (result.Extended?.Pdf417?.MacroPdf417FileID != null)
                    {
                        Console.WriteLine($"Macro PDF417 File ID: {result.Extended.Pdf417.MacroPdf417FileID}");
                    }

                    Console.WriteLine(new string('-', 40));
                }
            }
        }
    }
}
```

## Passi successivi

- **Esplora altri campi estesi** come `MacroPdf417SegmentID` o `MacroPdf417FileSize` per creare flussi di lavoro di ricostruzione di documenti completi.  
- **Integra il lettore in una web API** affinché i client possano caricare immagini e ricevere i dati decodificati istantaneamente.  
- **Esegui benchmark delle prestazioni** decodificando grandi lotti di immagini; il `BarCodeReader` supporta l'elaborazione asincrona nelle versioni più recenti di Aspose.

---

Seguendo questo **esempio di lettore di codici a barre C#**, ora disponi di un metodo affidabile per **decodificare un codice a barre da immagine** ed estrarre informazioni ricche di Macro PDF417. Sperimenta con diversi valori `DecodeType`, combina questa logica con i monitor di file o integrala nei back‑end mobili—le tue capacità di elaborazione dei codici a barre sono pronte a scalare.

## Cosa dovresti imparare dopo?

I seguenti tutorial coprono argomenti strettamente correlati che si basano sulle tecniche dimostrate in questa guida. Ogni risorsa include esempi di codice completi e funzionanti con spiegazioni passo‑passo per aiutarti a padroneggiare funzionalità API aggiuntive ed esplorare approcci di implementazione alternativi nei tuoi progetti.

- [How to Read PDF417 in C# – Complete Barcode Reader Example](/barcode/english/net/compact-pdf417-encoding/how-to-read-pdf417-in-c-complete-barcode-reader-example/)
- [Generate barcode with text – Full PDF417 Macro Guide](/barcode/english/net/compact-pdf417-encoding/generate-barcode-with-text-full-pdf417-macro-guide/)
- [How to Create PDF417 Barcode with Aspose – Complete Step‑by‑Step Guide](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-with-aspose-complete-step-by-st/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}