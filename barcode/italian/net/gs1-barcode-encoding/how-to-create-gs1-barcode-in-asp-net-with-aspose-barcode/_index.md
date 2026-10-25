---
category: general
date: 2026-10-24
description: Scopri come creare un codice a barre GS1 in ASP.NET usando Aspose.BarCode.
  Guida passo‑passo per generare il codice a barre da una stringa e renderizzarlo
  in PNG.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to create GS1 barcode
- generate barcode from string
- barcode generator asp.net
- create barcode with aspose
language: it
lastmod: 2026-10-24
og_description: Come creare un codice a barre GS1 in ASP.NET usando Aspose.BarCode.
  Segui questo tutorial per generare il codice a barre da una stringa, configurare
  le impostazioni visive e salvare i file PNG.
og_image_alt: Screenshot of a generated GS1 Micro PDF417 barcode saved as PNG
og_title: Come creare un codice a barre GS1 in ASP.NET – guida completa di Aspose
schemas:
- author: Aspose
  dateModified: '2026-10-24'
  description: Learn how to create GS1 barcode in ASP.NET using Aspose.BarCode. Step‑by‑step
    guide to generate barcode from string and render PNG.
  headline: How to create GS1 barcode in ASP.NET with Aspose.BarCode
  type: TechArticle
- description: Learn how to create GS1 barcode in ASP.NET using Aspose.BarCode. Step‑by‑step
    guide to generate barcode from string and render PNG.
  name: How to create GS1 barcode in ASP.NET with Aspose.BarCode
  steps:
  - name: 4.1 Prepare the GS1 data string
    text: 'GS1 data must be wrapped in parentheses with the AI code. For a product
      identifier (01) and a batch number (10) the string looks like:'
  - name: 4.2 Build the GS1 Micro PDF417 generator
    text: '```csharp public static byte[] GenerateGs1MicroPdf417(string gs1Data, string
      outputFolder) { // Step 4.2.1: Create a generator for Micro PDF417 using the
      GS1 data. BarcodeGenerator gs1Generator = new BarcodeGenerator(EncodeTypes.MicroPdf417,
      gs1Data);'
  - name: 4.3 Expose the generator through an ASP.NET endpoint
    text: '```csharp app.MapGet("/gs1barcode", (HttpContext context) => { string outputFolder
      = Path.Combine(Directory.GetCurrentDirectory(), "wwwroot", "barcodes"); Directory.CreateDirectory(outputFolder);
      // Ensure the folder exists'
  type: HowTo
tags:
- Aspose.BarCode
- GS1
- ASP.NET
- C#
title: Come creare un codice a barre GS1 in ASP.NET con Aspose.BarCode
url: /it/net/gs1-barcode-encoding/how-to-create-gs1-barcode-in-asp-net-with-aspose-barcode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Come creare un codice a barre GS1 in ASP.NET con Aspose.BarCode

Se hai bisogno di **come creare un codice a barre GS1** in un'applicazione ASP.NET, questa guida ti mostra i passaggi esatti. Vedrai come generare un codice a barre da una stringa, configurare l'aspetto visivo e salvare il risultato come immagine PNG.

La creazione di codici a barre GS1 non richiede una logica di codifica personalizzata. Utilizzando Aspose.BarCode ottieni una soluzione affidabile e conforme agli standard che funziona su .NET 6+ e versioni precedenti. Questo tutorial copre tutto, dall'impostazione del progetto alla verifica dell'output, così puoi copiare il codice direttamente nel tuo progetto web.

## Prerequisiti

* Visual Studio 2022 (o qualsiasi IDE che supporti .NET)
* .NET 6 SDK (o .NET Framework 4.7.2 e versioni successive)
* Conoscenze di base di ASP.NET Core o ASP.NET Framework
* Una licenza Aspose.BarCode (la valutazione gratuita funziona per i test)

Non sono necessarie librerie di terze parti aggiuntive perché Aspose.BarCode gestisce internamente tutta la codifica e il rendering.

## Passo 1: Creare un nuovo progetto ASP.NET

Apri Visual Studio e crea una **ASP.NET Core Web App** (scegli il modello *Empty*). Per un progetto Web Forms classico, lo stesso codice funziona all'interno di un file code‑behind.

```csharp
// Program.cs (ASP.NET Core minimal API example)
using Microsoft.AspNetCore.Builder;
using Microsoft.Extensions.Hosting;

var builder = WebApplication.CreateBuilder(args);
var app = builder.Build();

app.MapGet("/", () => "GS1 barcode generator is ready.");
app.Run();
```

Eseguendo il progetto dovrebbe comparire *GS1 barcode generator is ready.* nel browser. Questo conferma che l'host web è operativo.

## Passo 2: Installare Aspose.BarCode tramite NuGet

Apri la **Package Manager Console** ed esegui:

```powershell
Install-Package Aspose.BarCode
```

Il pacchetto aggiunge lo spazio dei nomi `Aspose.BarCode.Generation`, che contiene la classe `BarcodeGenerator` che utilizzerai per **generate barcode from string**. Il comando NuGet aggiorna anche il file di progetto con il riferimento necessario.

## Passo 3: Generare un semplice codice a barre da una stringa

Per illustrare l'uso di base, crea un metodo helper che restituisce un array di byte PNG. Questo metodo può essere chiamato da un controller, da una pagina Razor o da qualsiasi endpoint.

```csharp
using Aspose.BarCode.Generation;
using System.IO;

/// <summary>
/// Generates a barcode image from the supplied text.
/// </summary>
/// <param name="text">The data to encode.</param>
/// <param name="encodeType">The barcode symbology.</param>
/// <returns>PNG image bytes.</returns>
public static byte[] GenerateBarcode(string text, EncodeTypes encodeType)
{
    // Step 3.1: Initialize the generator with the desired symbology and data.
    BarcodeGenerator generator = new BarcodeGenerator(encodeType, text);

    // Step 3.2: Set a modest module width – 2 pixels gives a clear image.
    generator.Parameters.Barcode.XDimension.Pixels = 2;

    // Step 3.3: Render the barcode to a memory stream in PNG format.
    using MemoryStream ms = new MemoryStream();
    generator.Save(ms, BarCodeImageFormat.Png);
    return ms.ToArray();
}
```

Ora puoi chiamare `GenerateBarcode("HelloWorld", EncodeTypes.Code128)` da qualsiasi endpoint e scrivere i byte risultanti nella risposta HTTP. Questo dimostra il pattern **barcode generator asp.net** per stringhe arbitrarie.

## Passo 4: Come creare un codice a barre GS1 – esempio Micro PDF417

I codici a barre GS1 incorporano application‑identifiers (AI) che trasmettono informazioni sul prodotto. Aspose.BarCode supporta la variante compatibile GS1 di Micro PDF417, ideale per una rappresentazione compatta dei dati.

### 4.1 Preparare la stringa dati GS1

I dati GS1 devono essere racchiusi tra parentesi con il codice AI. Per un identificatore di prodotto (01) e un numero di lotto (10) la stringa appare così:

```csharp
string gs1Data = "(01)12345678901234(10)ABCD";
```

Le parentesi fanno parte dello standard; Aspose.BarCode le analizza automaticamente.

### 4.2 Costruire il generatore GS1 Micro PDF417

```csharp
public static byte[] GenerateGs1MicroPdf417(string gs1Data, string outputFolder)
{
    // Step 4.2.1: Create a generator for Micro PDF417 using the GS1 data.
    BarcodeGenerator gs1Generator = new BarcodeGenerator(EncodeTypes.MicroPdf417, gs1Data);

    // Step 4.2.2: Apply the same visual settings used for other barcodes.
    gs1Generator.Parameters.Barcode.XDimension.Pixels = 2;

    // Step 4.2.3: Micro PDF417 allows 1‑4 columns; 4 gives a more square shape.
    gs1Generator.Parameters.Barcode.Pdf417.Columns = 4;

    // Step 4.2.4: Save the image to the specified folder.
    string filePath = Path.Combine(outputFolder, "GS1MicroPdf417.png");
    gs1Generator.Save(filePath, BarCodeImageFormat.Png);

    // Return the file bytes for immediate HTTP response if needed.
    return File.ReadAllBytes(filePath);
}
```

### 4.3 Esporre il generatore tramite un endpoint ASP.NET

```csharp
app.MapGet("/gs1barcode", (HttpContext context) =>
{
    string outputFolder = Path.Combine(Directory.GetCurrentDirectory(), "wwwroot", "barcodes");
    Directory.CreateDirectory(outputFolder); // Ensure the folder exists

    byte[] pngBytes = GenerateGs1MicroPdf417("(01)12345678901234(10)ABCD", outputFolder);

    context.Response.ContentType = "image/png";
    return context.Response.Body.WriteAsync(pngBytes, 0, pngBytes.Length);
});
```

Visitando `https://localhost:5001/gs1barcode` ora viene trasmessa in streaming il PNG generato. L'immagine corrisponde alla specifica GS1 e il file viene anche salvato su disco per un uso successivo.

## Passo 5: Rendering di tipi di codice a barre aggiuntivi

Lo stesso approccio **create barcode with aspose** funziona per altre simbologie. Di seguito un rapido esempio che crea un QR code da un URL:

```csharp
byte[] qrBytes = GenerateBarcode("https://example.com", EncodeTypes.QR);
File.WriteAllBytes(Path.Combine(outputFolder, "ExampleQR.png"), qrBytes);
```

Puoi sostituire `EncodeTypes.QR` con `EncodeTypes.Code128`, `EncodeTypes.DataMatrix` o qualsiasi altro tipo supportato. I parametri visivi (`XDimension`, `Resolution`, `Color`) sono configurabili tramite l'oggetto `Parameters`.

## Passo 6: Problemi comuni e consigli di best‑practice

| Issue | Why it happens | How to avoid it |
|-------|----------------|-----------------|
| **Formattazione AI errata** | Mancano le parentesi o la lunghezza dell'AI è errata, causando errori di codifica. | Costruisci sempre la stringa GS1 esattamente come specificato dallo standard. Usa un metodo helper per concatenare gli AI. |
| **Troppi colonne** | Micro PDF417 supporta solo 1‑4 colonne; impostare 5 genera un'eccezione. | Convalida il valore delle colonne prima di assegnarlo: `if (columns < 1 || columns > 4) throw …` |
| **Bassa risoluzione dell'immagine** | Valori piccoli di `XDimension` possono rendere il codice a barre illeggibile sulle stampanti. | Per codici a barre pronti per la stampa, aumenta `Resolution` (ad esempio, `generator.Parameters.Image.Resolution = 300`). |
| **Problemi di percorso file su Linux** | Backslash codificati staticamente rompono su host non Windows. | Usa `Path.Combine` per costruire i percorsi dei file; gestisce i separatori specifici del sistema operativo. |
| **Licenza non applicata** | La valutazione gratuita aggiunge una filigrana dopo 30 giorni. | Applica la licenza subito: `new License().SetLicense("Aspose.BarCode.lic");` |

## Passo 7: Verificare il codice a barre generato

Dopo aver eseguito l'endpoint, apri il PNG in qualsiasi visualizzatore di immagini. Per confermare che i dati GS1 siano codificati correttamente, puoi utilizzare uno scanner mobile gratuito che supporta GS1 Micro PDF417 (molte app di scansione elencano questa simbologia). Scansiona l'immagine; l'app dovrebbe restituire:

```
(01)12345678901234
(10)ABCD
```

Se lo scanner segnala un errore, ricontrolla la formattazione degli AI e il numero di colonne.

## Conclusione

Ora sai **how to create GS1 barcode** in un ambiente ASP.NET usando Aspose.BarCode. Il tutorial ha coperto:

* Impostare un progetto ASP.NET e installare il pacchetto NuGet Aspose.BarCode.  
* Utilizzare **generate barcode from string** per codici a barre generici.  
* Implementare **create barcode with aspose** per produrre un'immagine Micro PDF417 compatibile GS1.  
* Salvare l'immagine su disco e trasmetterla in streaming tramite un endpoint HTTP.  

Da qui puoi esplorare altre simbologie GS1 (ad esempio, GS1 DataMatrix) o integrare il generatore in un flusso di lavoro di elaborazione ordini più ampio. Sperimenta con diversi valori di `XDimension`, colori e livelli di correzione degli errori per adattarli al tuo brand e all'ambiente di scansione.

Buon coding, e lascia che le tue applicazioni parlino il linguaggio universale dei codici a barre!

## Cosa dovresti imparare dopo?

I seguenti tutorial coprono argomenti strettamente correlati che si basano sulle tecniche dimostrate in questa guida. Ogni risorsa include esempi di codice completi e funzionanti con spiegazioni passo‑passo per aiutarti a padroneggiare funzionalità API aggiuntive ed esplorare approcci di implementazione alternativi nei tuoi progetti.

- [Come creare un codice a barre code 128 con GS1 usando Aspose.BarCode](/barcode/english/net/gs1-barcode-encoding/gs1-code-128-example/)
- [Come creare la zona silenziosa del codice a barre per ITF-14 usando Aspose.BarCode per .NET](/barcode/english/net/itf-14-barcode-customization/itf-14-barcode-quiet-zone-configuration/)
- [Come creare un codice a barre ITF-14 .NET – Tutorial completi di Aspose.BarCode](/barcode/english/net/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}