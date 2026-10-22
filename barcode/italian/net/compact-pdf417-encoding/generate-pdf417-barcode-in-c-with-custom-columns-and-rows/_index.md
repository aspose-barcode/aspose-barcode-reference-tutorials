---
category: general
date: 2026-10-21
description: Genera rapidamente codici a barre PDF417 in C#. Scopri come generare
  codici a barre PDF417 con layout personalizzato, colonne, righe e output PNG.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate pdf417 barcode
- how to generate pdf417 barcode
- pdf417 barcode layout
- barcode generator C#
- save barcode as PNG
language: it
lastmod: 2026-10-21
og_description: Genera codice a barre pdf417 in C#. Segui questo tutorial per imparare
  a generare un codice a barre pdf417 con colonne e righe personalizzate e output
  PNG.
og_image_alt: Screenshot showing a generated PDF417 barcode saved as a PNG file
og_title: Genera codice a barre PDF417 in C# – guida completa passo passo
schemas:
- author: Aspose
  dateModified: '2026-10-21'
  description: Generate pdf417 barcode quickly in C#. Learn how to generate pdf417
    barcode with custom layout, columns, rows, and PNG output.
  headline: Generate pdf417 barcode in C# with custom columns and rows
  type: TechArticle
- description: Generate pdf417 barcode quickly in C#. Learn how to generate pdf417
    barcode with custom layout, columns, rows, and PNG output.
  name: Generate pdf417 barcode in C# with custom columns and rows
  steps:
  - name: Open the PNG file in any image viewer.
    text: Open the PNG file in any image viewer.
  - name: Use a free PDF417 scanner app (e.g., ZXing, PDF417 Decoder) to scan the
      image.
    text: Use a free PDF417 scanner app (e.g., ZXing, PDF417 Decoder) to scan the
      image.
  - name: Confirm that the decoded text matches the original input.
    text: Confirm that the decoded text matches the original input.
  type: HowTo
tags:
- barcode
- pdf417
- C#
- image generation
title: Genera codice a barre pdf417 in C# con colonne e righe personalizzate
url: /it/net/compact-pdf417-encoding/generate-pdf417-barcode-in-c-with-custom-columns-and-rows/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Generare codice a barre pdf417 in C# – guida completa di programmazione

Se hai bisogno di **generare codice a barre pdf417** in un'applicazione .NET, questa guida ti mostra come farlo con poche righe di codice. Vedrai un esempio pratico che configura il numero di colonne e righe, quindi salva il risultato come immagine PNG. Lo stesso approccio funziona per qualsiasi testo che desideri codificare, così puoi adattarlo a fatture, biglietti o tessere d'identità.

Generare un **codice a barre pdf417** spesso sembra un compito separato dal resto del tuo codice. Alla fine di questo tutorial comprenderai perché i parametri di layout sono importanti, come controllare la qualità dell'immagine e quali chiamate di libreria sono necessarie per **generare codice a barre pdf417** in modo affidabile.

## Cosa ti serve

* .NET 6.0 SDK o versioni successive installato  
* Un IDE compatibile con C# (Visual Studio, VS Code, Rider, ecc.)  
* Il pacchetto NuGet **Aspose.BarCode for .NET** (o qualsiasi libreria di codici a barre compatibile)  

Puoi aggiungere la libreria con il seguente comando:

```bash
dotnet add package Aspose.BarCode
```

La libreria fornisce la classe `BarcodeGenerator` utilizzata in tutto questo tutorial.

## Passo 1: Creare un'istanza del generatore di codici a barre

La prima riga crea un oggetto che sa come **generare codice a barre pdf417**. Devi specificare il tipo di codifica (`EncodeTypes.Pdf417`) e il testo che desideri codificare.

```csharp
using Aspose.BarCode.Generation;

BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Sample Text");
```

*Perché questo passo è importante* – Il `BarcodeGenerator` incapsula tutte le impostazioni per il codice a barre. Istanziarlo con il corretto `EncodeTypes` indica al motore di utilizzare la simbologia PDF417 invece di QR, Code128 o altri formati.

## Passo 2: Configurare il layout PDF417

PDF417 ti permette di controllare il numero di colonne e righe, influenzando direttamente le dimensioni e la densità del codice a barre. Regolare questi valori è il fulcro di **come generare codice a barre pdf417** con un layout personalizzato.

```csharp
// Set the number of data columns (valid range: 2‑30)
generator.Parameters.Barcode.Pdf417.Columns = 4;

// Set the number of rows (up to 90 rows)
generator.Parameters.Barcode.Pdf417.Rows = 9;
```

*Perché potresti modificare questi valori* – Più colonne riducono l'altezza del codice a barre, mentre più righe aumentano la larghezza. Scegli valori che si adattino al dispositivo di scansione target e all'area di stampa disponibile.

> **Consiglio professionale:** Se ometti le righe, la libreria calcola automaticamente il conteggio ottimale in base alla lunghezza dei dati. Impostare esplicitamente le righe è utile quando hai bisogno di una dimensione immagine fissa per i layout UI.

## Passo 3: Scegliere un formato immagine e salvare il file

Dopo aver configurato il layout, puoi renderizzare il codice a barre in un'immagine. L'esempio qui sotto salva il codice a barre come file PNG, ma puoi anche selezionare JPEG, BMP o TIFF.

```csharp
using Aspose.BarCode;
using System.IO;

// Define the output path – replace with your actual directory
string outputPath = Path.Combine("C:\\Barcodes", "CustomLayout.png");

// Save the barcode image as PNG
generator.Save(outputPath, BarCodeImageFormat.Png);
```

Quando il codice viene eseguito, `CustomLayout.png` conterrà un chiaro **codice a barre pdf417** che corrisponde alle impostazioni di colonna/riga fornite.

### Output previsto

Aprendo `CustomLayout.png` si vede un codice a barre rettangolare con quattro colonne di dati e nove righe. Scansionando l'immagine con qualsiasi lettore PDF417 si ottiene il testo originale **“Sample Text”**.

![Esempio di codice a barre PDF417 generato](generated-pdf417.png){: .center-image alt="Codice a barre PDF417 generato salvato come file PNG"}

## Passo 4: Esempio completo e eseguibile

Di seguito trovi un'applicazione console autonoma che mette insieme tutti i componenti. Copia il codice in un nuovo progetto `.csproj` e eseguilo—non sono necessari file aggiuntivi.

```csharp
using System;
using System.IO;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace Pdf417Demo
{
    class Program
    {
        static void Main()
        {
            // 1️⃣ Create the generator with the desired text
            BarcodeGenerator generator = new BarcodeGenerator(
                EncodeTypes.Pdf417,
                "Sample Text for PDF417 barcode");

            // 2️⃣ Configure layout – custom columns and rows
            generator.Parameters.Barcode.Pdf417.Columns = 4; // 2‑30
            generator.Parameters.Barcode.Pdf417.Rows = 9;    // up to 90

            // Optional: increase image resolution for sharper output
            generator.Parameters.ImageResolution = 300; // DPI

            // 3️⃣ Define the output location
            string folder = Path.Combine(Environment.CurrentDirectory, "output");
            Directory.CreateDirectory(folder);
            string filePath = Path.Combine(folder, "CustomLayout.png");

            // 4️⃣ Save as PNG
            generator.Save(filePath, BarCodeImageFormat.Png);

            Console.WriteLine($"PDF417 barcode generated at: {filePath}");
        }
    }
}
```

L'esecuzione del programma stampa una riga di conferma e crea il file PNG nella sottocartella `output`. L'immagine può essere incorporata nei report, stampata su etichette o inviata a un dispositivo mobile per la scansione.

## Varianti comuni e casi limite

| Scenario | Cosa cambiare | Perché è importante |
|----------|----------------|----------------|
| **Codificare una stringa lunga** | Aumenta `Rows` o lascia che la libreria calcoli automaticamente omettendo l'assegnazione di `Rows` | PDF417 può contenere fino a 1.850 caratteri; un numero insufficiente di righe provoca troncamento |
| **Qualità visiva più alta** | Imposta `generator.Parameters.ImageResolution` a 600 DPI | Utile per la stampa su stampanti ad alta risoluzione |
| **Formato immagine diverso** | Sostituisci `BarCodeImageFormat.Png` con `Jpeg` o `Tiff` | JPEG riduce la dimensione del file; TIFF conserva i dati senza perdita per l'archiviazione |
| **Aggiungere una zona silenziosa** | `generator.Parameters.Barcode.XDimension = 2;` (o regola `Margins`) | Le zone silenziose migliorano l'affidabilità dello scanner in ambienti rumorosi |
| **Testo dinamico da input utente** | Sostituisci la stringa hard‑coded con `Console.ReadLine()` | Consente la generazione a runtime basata sui dati dell'utente |

### Come generare codice a barre pdf417 in una Web API

Se hai bisogno di esporre la generazione di codici a barre tramite un endpoint ASP.NET Core, restituisci l'immagine come array di byte:

```csharp
[HttpGet("api/barcode/pdf417")]
public IActionResult GetPdf417([FromQuery] string data)
{
    var generator = new BarcodeGenerator(EncodeTypes.Pdf417, data);
    generator.Parameters.Barcode.Pdf417.Columns = 5;
    generator.Parameters.Barcode.Pdf417.Rows = 10;

    using var ms = new MemoryStream();
    generator.Save(ms, BarCodeImageFormat.Png);
    return File(ms.ToArray(), "image/png");
}
```

Questo frammento risponde a **come generare codice a barre pdf417** al volo senza scrivere su disco, il che è ideale per microservizi o backend mobili.

## Testare il codice a barre generato

Per verificare che il codice a barre sia stato creato correttamente:

1. Apri il file PNG in qualsiasi visualizzatore di immagini.  
2. Usa un'app scanner PDF417 gratuita (ad es., ZXing, PDF417 Decoder) per scansionare l'immagine.  
3. Conferma che il testo decodificato corrisponda all'input originale.  

Se lo scanner segnala errori, ricontrolla i valori di colonna/riga e assicurati che la risoluzione dell'immagine sia sufficientemente alta per il tuo dispositivo.

## Conclusione

Ora sai come **generare codice a barre pdf417** in C# con pieno controllo su colonne, righe e formato di output. L'esempio completo dimostra l'intero flusso di lavoro—dalla creazione del `BarcodeGenerator` al salvataggio di un file PNG—così puoi integrare la creazione di codici a barre in qualsiasi progetto .NET.

Successivamente, esplora argomenti correlati come l'ottimizzazione del **layout del codice a barre pdf417**, l'incorporamento di codici a barre nei report PDF o la decodifica di codici a barre su dispositivi mobili. Regolare i livelli di correzione degli errori e sperimentare diverse risoluzioni delle immagini ti aiuterà a perfezionare la soluzione per il tuo caso d'uso specifico. Buona programmazione!

## Cosa dovresti imparare dopo?

I seguenti tutorial coprono argomenti strettamente correlati che si basano sulle tecniche dimostrate in questa guida. Ogni risorsa include esempi di codice completi e funzionanti con spiegazioni passo‑passo per aiutarti a padroneggiare funzionalità API aggiuntive ed esplorare approcci di implementazione alternativi nei tuoi progetti.

- [Come generare codice a barre PDF417 in C# – guida passo‑passo](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-step-by-step-guide/)
- [Come salvare il codice a barre in C# – Generare codici a barre PDF417](/barcode/english/net/compact-pdf417-encoding/how-to-save-barcode-in-c-generate-pdf417-barcodes/)
- [Come generare codice a barre PDF417 – Guida completa di programmazione](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-complete-programming-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}