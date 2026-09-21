---
category: general
date: 2026-08-09
description: Come leggere PDF417 in C# usando BarCodeReader. Impara a leggere file
  PNG di codici a barre, gestire più codici a barre ed estrarre metadati estesi.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to read pdf417
- c# barcode reader
- read multiple barcodes
- read barcode png
- read barcode extended
language: it
lastmod: 2026-08-09
og_description: Come leggere PDF417 in C# con Aspose.BarCode. Questo tutorial ti mostra
  come leggere file PNG di codici a barre, elaborare più codici a barre in un'unica
  immagine e recuperare i metadati estesi di PDF417.
og_image_alt: Screenshot of C# BarCodeReader console output displaying PDF417 metadata
og_title: Come leggere PDF417 in C# – tutorial sul lettore di codici a barre
schemas:
- author: Aspose
  dateModified: '2026-08-09'
  description: How to read PDF417 in C# using the BarCodeReader. Learn to read barcode
    PNG files, handle multiple barcodes, and extract extended metadata.
  headline: How to read PDF417 in C# – complete barcode reader guide
  type: TechArticle
- description: How to read PDF417 in C# using the BarCodeReader. Learn to read barcode
    PNG files, handle multiple barcodes, and extract extended metadata.
  name: How to read PDF417 in C# – complete barcode reader guide
  steps:
  - name: Verify the file exists before creating the reader.
    text: Verify the file exists before creating the reader.
  - name: Use `Image.FromFile` only when you need to pre‑process (rotate, crop). The
      `BarCodeReader` can open the file directly, which avoids extra memory allocation.
    text: Use `Image.FromFile` only when you need to pre‑process (rotate, crop). The
      `BarCodeReader` can open the file directly, which avoids extra memory allocation.
  - name: If the PNG contains transparency, the reader still works because the barcode
      is rendered on opaque pixels.
    text: If the PNG contains transparency, the reader still works because the barcode
      is rendered on opaque pixels.
  type: HowTo
tags:
- barcode
- C#
- PDF417
title: Come leggere PDF417 in C# – guida completa al lettore di codici a barre
url: /it/net/compact-pdf417-encoding/how-to-read-pdf417-in-c-complete-barcode-reader-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Come leggere PDF417 in C# – guida completa al lettore di codici a barre

Se hai bisogno di **come leggere PDF417** in un'applicazione .NET, questa guida ti fornisce una soluzione pronta all'uso. Vedrai come leggere un PNG di codice a barre, elaborare più codici a barre nella stessa immagine e recuperare i campi estesi PDF417 che molti scanner nascondono.

La lettura dei codici a barre PDF417 è comune nella logistica, nella gestione dei biglietti e nella gestione dei documenti. Alla fine di questo tutorial potrai decodificare un'immagine Macro PDF417, visualizzare ogni risultato e utilizzare le informazioni aggiuntive (ID file, conteggio segmenti, timestamp, ecc.) nella tua logica di business.

## Prerequisiti

- .NET 6.0 o versioni successive (il codice funziona anche con .NET Framework 4.7+)
- Visual Studio 2022 o qualsiasi IDE C#
- **Aspose.BarCode for .NET** (versione di prova gratuita o pacchetto NuGet con licenza)
- Un'immagine PNG che contiene un codice a barre Macro PDF417 (il file di esempio si chiama `ExtPDF417Meta.png`)

> **Consiglio professionale:** Installa la libreria con la console NuGet:  
> `dotnet add package Aspose.BarCode`

## Come leggere PDF417 con BarCodeReader in C#

Il nucleo della soluzione è la classe `BarCodeReader`. Accetta un percorso immagine e un enum `DecodeType` che indica al motore quale simbologia cercare.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.ReadEngine;

class Pdf417Demo
{
    static void Main()
    {
        // Step 1: Create a BarCodeReader for a Macro PDF417 image
        using (BarCodeReader reader = new BarCodeReader(
            "YOUR_DIRECTORY/ExtPDF417Meta.png",
            DecodeType.MacroPdf417))
        {
            // Step 2: Read all barcodes from the image
            foreach (BarCodeResult result in reader.ReadBarCodes())
            {
                // Step 3: Output basic barcode information
                Console.WriteLine($"CodeType: {result.CodeTypeName}");
                Console.WriteLine($"CodeText: {result.CodeText}");

                // Step 4: Display Macro PDF417 extended metadata
                Console.WriteLine($"Pdf417MacroFileID: {result.Extended.Pdf417.MacroPdf417FileID}");
                Console.WriteLine($"Pdf417MacroSegmentID: {result.Extended.Pdf417.MacroPdf417SegmentID}");
                Console.WriteLine($"Pdf417MacroSegmentsCount: {result.Extended.Pdf417.MacroPdf417SegmentsCount}");
                Console.WriteLine($"Pdf417MacroFileName: {result.Extended.Pdf417.MacroPdf417FileName}");
                Console.WriteLine($"Pdf417MacroChecksum: {result.Extended.Pdf417.MacroPdf417Checksum}");
                Console.WriteLine($"Pdf417MacroFileSize: {result.Extended.Pdf417.MacroPdf417FileSize}");
                Console.WriteLine($"Pdf417MacroTimeStamp: {result.Extended.Pdf417.MacroPdf417TimeStamp}");
                Console.WriteLine($"Pdf417MacroAddressee: {result.Extended.Pdf417.MacroPdf417Addressee}");
                Console.WriteLine($"Pdf417MacroSender: {result.Extended.Pdf417.MacroPdf417Sender}");
                Console.WriteLine($"MacroPdf417Terminator: {result.Extended.Pdf417.MacroPdf417Terminator}");
                Console.WriteLine(new string('-', 40));
            }
        }
    }
}
```

### Perché funziona

- `DecodeType.MacroPdf417` indica al lettore di cercare la variante Macro PDF417, che memorizza i campi aggiuntivi visti al passo 4.
- Il blocco `using` elimina automaticamente il lettore, rilasciando i handle dei file.
- `ReadBarCodes()` restituisce **tutti** i codici a barre che corrispondono al tipo richiesto, soddisfacendo il requisito *leggere più codici a barre* anche se l'immagine contiene solo uno.

L'esecuzione del programma stampa un output simile a:

```
CodeType: MacroPdf417
CodeText: 1234567890
Pdf417MacroFileID: 1
Pdf417MacroSegmentID: 0
Pdf417MacroSegmentsCount: 3
Pdf417MacroFileName: invoice_2023.pdf
Pdf417MacroChecksum: 0x1A2B
Pdf417MacroFileSize: 254321
Pdf417MacroTimeStamp: 2023-03-15T10:45:00Z
Pdf417MacroAddressee: ACME Corp.
Pdf417MacroSender: Warehouse 7
MacroPdf417Terminator: True
----------------------------------------
```

## Utilizzare il lettore di codici a barre C# per leggere più codici a barre

Se un'immagine contiene diversi simboli Macro PDF417 (ad esempio, una pagina scannerizzata con un lotto di biglietti), lo stesso ciclo `foreach` elabora ciascuno di essi. Non è necessario alcun codice aggiuntivo; il lettore aggrega i risultati internamente.

```csharp
// Example: processing a batch image
using (BarCodeReader batchReader = new BarCodeReader(
    "batch.png", DecodeType.MacroPdf417))
{
    int index = 0;
    foreach (BarCodeResult item in batchReader.ReadBarCodes())
    {
        Console.WriteLine($"--- Barcode #{++index} ---");
        Console.WriteLine($"Text: {item.CodeText}");
        // extended fields are accessed the same way
    }
}
```

### Problemi comuni

- **Formato immagine:** Il lettore supporta PNG, JPEG, BMP e TIFF. Se provi un formato che non può decodificare, otterrai una collezione vuota. Ecco perché il tutorial evidenzia *leggere codice a barre PNG*.
- **Risoluzione:** Immagini a bassa risoluzione (< 300 dpi) possono causare segmenti mancati. Aumenta la scala o richiedi una scansione di qualità superiore quando possibile.
- **Flag macro:** Dimenticare `DecodeType.MacroPdf417` limita il motore al PDF417 semplice e scarta i dati estesi. Specifica sempre il tipo macro quando hai bisogno dei campi *leggere codice a barre esteso*.

## Lettura di file PNG di codici a barre – migliori pratiche

Lavorare con file PNG è semplice perché il formato conserva i dati pixel senza perdita. Ecco una rapida checklist:

1. Verifica che il file esista prima di creare il lettore.  
   ```csharp
   if (!File.Exists(path))
       throw new FileNotFoundException($"File not found: {path}");
   ```
2. Usa `Image.FromFile` solo quando è necessario pre‑processare (ruotare, ritagliare). Il `BarCodeReader` può aprire il file direttamente, evitando un'allocazione di memoria aggiuntiva.
3. Se il PNG contiene trasparenza, il lettore funziona comunque perché il codice a barre è renderizzato su pixel opachi.

## Accesso ai metadati PDF417 estesi

L'oggetto `Extended.Pdf417` espone ogni campo opzionale definito dalla specifica PDF417. Puoi mappare questi campi a un modello di dominio, memorizzarli in un database o usarli per la validazione.

```csharp
public class Pdf417Metadata
{
    public int FileID { get; set; }
    public int SegmentID { get; set; }
    public int SegmentsCount { get; set; }
    public string FileName { get; set; }
    public string Checksum { get; set; }
    public long FileSize { get; set; }
    public DateTime TimeStamp { get; set; }
    public string Addressee { get; set; }
    public string Sender { get; set; }
    public bool Terminator { get; set; }
}
```

Populate the model:



## Cosa dovresti imparare dopo?

I seguenti tutorial coprono argomenti strettamente correlati che si basano sulle tecniche dimostrate in questa guida. Ogni risorsa include esempi di codice completi e funzionanti con spiegazioni passo passo per aiutarti a padroneggiare funzionalità API aggiuntive ed esplorare approcci di implementazione alternativi nei tuoi progetti.

- [Come leggere i codici a barre DataMatrix con Aspose.BarCode per .NET](/barcode/english/net/datamatrix-barcode-reading/)
- [Come creare un codice a barre – Compact PDF417 con Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [Leggi il codice a barre DataMatrix C# – Genera modalità DataMatrix (Auto)](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-auto/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}