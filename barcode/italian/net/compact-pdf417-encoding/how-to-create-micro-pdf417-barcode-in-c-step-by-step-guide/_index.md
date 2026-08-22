---
category: general
date: 2026-08-22
description: Impara a creare un codice a barre micro PDF417 in C# e a generare un'immagine
  PNG del codice a barre. Include la definizione delle dimensioni del codice a barre
  e il salvataggio del file.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create micro pdf417 barcode
- how to generate barcode png
- create barcode image c#
- how to set barcode dimensions
language: it
lastmod: 2026-08-22
og_description: Crea un codice a barre micro PDF417 in C# ed esportalo come PNG. Segui
  questa guida per impostare le dimensioni del codice a barre e generare rapidamente
  un'immagine del codice a barre.
og_image_alt: Screenshot of a micro PDF417 barcode generated with C# code
og_title: Crea codice a barre micro PDF417 in C# – tutorial completo di programmazione
schemas:
- author: Aspose
  dateModified: '2026-08-22'
  description: Learn how to create micro PDF417 barcode in C# and generate a barcode
    PNG image. Includes setting barcode dimensions and saving the file.
  headline: How to create micro PDF417 barcode in C# – step‑by‑step guide
  type: TechArticle
- description: Learn how to create micro PDF417 barcode in C# and generate a barcode
    PNG image. Includes setting barcode dimensions and saving the file.
  name: How to create micro PDF417 barcode in C# – step‑by‑step guide
  steps:
  - name: 'Build the project: `dotnet build`.'
    text: 'Build the project: `dotnet build`.'
  - name: 'Execute: `dotnet run`.'
    text: 'Execute: `dotnet run`.'
  - name: Open `MicroPdf417.png` on your desktop and scan it with a mobile barcode
      scanner app.
    text: Open `MicroPdf417.png` on your desktop and scan it with a mobile barcode
      scanner app.
  type: HowTo
tags:
- barcode
- C#
- MicroPdf417
- image generation
title: Come creare un codice a barre micro PDF417 in C# – guida passo passo
url: /it/net/compact-pdf417-encoding/how-to-create-micro-pdf417-barcode-in-c-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Come creare un codice a barre micro PDF417 in C# – guida passo‑passo

Se hai bisogno di **creare un codice a barre micro PDF417** per un sistema di biglietteria, un'etichetta di inventario o una scansione mobile, questo tutorial ti mostra esattamente come fare. Vedrai il programma C# completo che genera un PNG del codice a barre, imparerai a impostare le dimensioni del codice a barre e comprenderai ogni opzione di configurazione.

Entro la fine di questa guida sarai in grado di generare un'immagine di codice a barre ad alta risoluzione, personalizzare la X‑dimension, scegliere il numero di colonne e salvare il risultato come file PNG—tutto con poche righe di codice.

## Cosa ti serve

- .NET 6.0 SDK o versioni successive (il codice funziona con .NET Core e .NET Framework)
- Visual Studio 2022 o qualsiasi IDE compatibile con C#
- Il pacchetto NuGet **Aspose.BarCode for .NET** (o qualsiasi libreria che supporti `EncodeTypes.MicroPdf417`)
- Familiarità di base con la sintassi C#

> **Consiglio professionale:** L'edizione community gratuita di Aspose.BarCode è sufficiente per lo sviluppo e i test. Per la produzione, procurati una licenza per rimuovere i watermark di valutazione.

## Passo 1: Installa la libreria di codici a barre

Apri un terminale nella cartella del tuo progetto ed esegui:

```bash
dotnet add package Aspose.BarCode
```

Questo aggiunge l'assembly `Aspose.BarCode`, che fornisce la classe `BarcodeGenerator` usata per **creare applicazioni C# per immagini di codici a barre**.

## Passo 2: Inizializza il generatore – crea un codice a barre micro PDF417

La prima riga operativa crea un'istanza di `BarcodeGenerator` configurata per la simbologia Micro PDF417 e fornisce i dati che desideri codificare.

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Program
{
    static void Main()
    {
        // Step 2: Initialize a Micro PDF417 barcode generator with the data to encode
        BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.MicroPdf417, "Sample text");
```

*Perché è importante*: L'enumerazione `EncodeTypes.MicroPdf417` indica alla libreria di utilizzare la versione compatta di PDF417, ideale per etichette piccole e schermi mobili.

## Passo 3: Come impostare le dimensioni del codice a barre in C#

Regolare finemente la larghezza del modulo (X‑dimension) controlla la densità visiva del codice a barre. Un valore più piccolo produce un'immagine più nitida, mentre un valore più grande rende il codice a barre più facile da scansionare a distanza.

```csharp
        // Step 3: Set the X‑dimension (module width) to 2 pixels for finer resolution
        generator.Parameters.Barcode.XDimension.Pixels = 2;
```

> **Perché dovresti impostare le dimensioni**: Senza regolare la X‑dimension, il valore predefinito può produrre un codice a barre che appare sfocato quando viene renderizzato a DPI elevati. Impostarla a 2 pixel è un buon compromesso per la maggior parte delle scansioni basate su schermo.

## Passo 4: Scegli il numero di colonne – controllare la larghezza del codice a barre

Micro PDF417 consente tra 1 e 4 colonne. Più colonne comprimono i dati orizzontalmente, riducendo la larghezza complessiva dell'immagine.

```csharp
        // Step 4: Define the number of columns (allowed values: 1‑4)
        generator.Parameters.Barcode.Pdf417.Columns = 4;
```

*Caso limite*: Se richiedi 5 colonne la libreria genera un'`ArgumentOutOfRangeException`. Rimani sempre entro l'intervallo documentato.

## Passo 5: Come generare un PNG del codice a barre – salvare l'immagine

Ora puoi esportare il codice a barre generato in un file PNG. PNG conserva la qualità lossless, fondamentale per una scansione affidabile.

```csharp
        // Step 5: Save the generated barcode as a PNG image
        string outputPath = Path.Combine(
            Environment.GetFolderPath(Environment.SpecialFolder.Desktop),
            "MicroPdf417.png");
        generator.Save(outputPath, BarCodeImageFormat.Png);
        Console.WriteLine($"Barcode saved to {outputPath}");
    }
}
```

Quando esegui il programma, vedrai un messaggio nella console che conferma la posizione del file. Il risultato `MicroPdf417.png` appare così:

![Screenshot che mostra un codice a barre micro PDF417 generato con C#](micro-pdf417-example.png "Codice a barre micro PDF417 generato")

*Testo alternativo dell'immagine*: **codice a barre micro PDF417 generato in C#** – dimostra l'output finale dopo aver applicato le dimensioni e le impostazioni delle colonne.

## Passo 6: Esegui e verifica l'output

1. Compila il progetto: `dotnet build`.
2. Esegui: `dotnet run`.
3. Apri `MicroPdf417.png` sul desktop e scansionalo con un'app scanner di codici a barre mobile.

Dovresti vedere il testo **“Sample text”** decodificato. Se lo scanner segnala un errore, ricontrolla la X‑dimension e il numero di colonne – valori estremi possono rendere il codice a barre troppo denso per alcuni dispositivi.

## Variazioni comuni e risoluzione dei problemi

| Situazione | Regolazione |
|-----------|------------|
| **Necessità di un codice a barre più grande per stampanti a bassa risoluzione** | Aumenta `XDimension.Pixels` a 3 o 4. |
| **Vuoi un codice a barre più alto senza cambiare la larghezza** | Imposta `generator.Parameters.Barcode.Pdf417.Rows` (intervallo righe 3‑90). |
| **Generazione di più codici a barre in un ciclo** | Riutilizza la stessa istanza di `BarcodeGenerator` e cambia solo `CodeText` prima di ogni `Save`. |
| **Salvare come JPEG invece di PNG** | Sostituisci `BarCodeImageFormat.Png` con `BarCodeImageFormat.Jpeg`. |
| **Esecuzione su .NET Framework 4.7** | Lo stesso codice funziona; basta fare riferimento al `Aspose.BarCode.dll` appropriato. |

## Elenco completo del codice sorgente (eseguibile)

```csharp
using System;
using System.IO;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace MicroPdf417Demo
{
    class Program
    {
        static void Main()
        {
            // Initialize a Micro PDF417 barcode generator with the data to encode
            BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.MicroPdf417, "Sample text");

            // Set the X‑dimension (module width) to 2 pixels for finer resolution
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // Define the number of columns (allowed values: 1‑4)
            generator.Parameters.Barcode.Pdf417.Columns = 4;

            // Save the generated barcode as a PNG image
            string outputPath = Path.Combine(
                Environment.GetFolderPath(Environment.SpecialFolder.Desktop),
                "MicroPdf417.png");
            generator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"Barcode saved to {outputPath}");
        }
    }
}
```

**Output previsto** – un file PNG di 200 × 100 pixel contenente un codice a barre Micro PDF417 nitido che decodifica “Sample text”.

## Conclusione

Ora sai come **creare un codice a barre micro PDF417** in C#, **impostare le dimensioni del codice a barre** e **generare un'immagine PNG del codice a barre**. L'esempio completo dimostra ogni passaggio necessario—dall'installazione della libreria al salvataggio del file finale—così puoi incorporare la generazione di codici a barre direttamente nelle tue applicazioni.

Successivamente, esplora argomenti correlati come **creare codici QR con Aspose.BarCode**, **personalizzare i colori**, o **incorporare codici a barre in documenti PDF**. Ognuno di questi si basa sugli stessi fondamenti di `BarcodeGenerator` trattati qui.

Sentiti libero di sperimentare con diverse stringhe di dati, numeri di colonne e valori di X‑dimension per adattarli al tuo specifico ambiente di scansione. Buon coding!

## Cosa dovresti imparare dopo?

I tutorial seguenti coprono argomenti strettamente correlati che si basano sulle tecniche dimostrate in questa guida. Ogni risorsa include esempi di codice completi e funzionanti con spiegazioni passo‑passo per aiutarti a padroneggiare funzionalità API aggiuntive ed esplorare approcci di implementazione alternativi nei tuoi progetti.

- [Come creare un codice a barre – PDF417 compatto con Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [Come generare un codice a barre PDF417 – Codifica PDF417 compatto](/barcode/english/net/compact-pdf417-encoding/)
- [Come creare un codice a barre Aztec con Aspose.BarCode per .NET](/barcode/english/net/aztec-barcode-encoding/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}