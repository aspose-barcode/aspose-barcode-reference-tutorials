---
category: general
date: 2026-08-09
description: Crea un'immagine di codice a barre in C# con questa guida passo passo.
  Scopri come generare il codice a barre, regolare l'altezza del codice a barre in
  pixel e creare più codici a barre in modo efficiente.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode image
- how to generate barcode
- barcode generator c#
- create multiple barcodes
- barcode height pixels
language: it
lastmod: 2026-08-09
og_description: Crea rapidamente un'immagine di codice a barre in C#. Segui questo
  tutorial per imparare a generare il codice a barre, impostare l’altezza del codice
  a barre in pixel e produrre più codici a barre.
og_image_alt: Screenshot of barcode images generated with C# code showing different
  heights
og_title: Crea immagine di codice a barre in C# – guida completa per gli sviluppatori
schemas:
- author: Aspose
  dateModified: '2026-08-09'
  description: Create barcode image in C# with this step-by-step guide. Learn how
    to generate barcode, adjust barcode height pixels, and create multiple barcodes
    efficiently.
  headline: Create barcode image in C# – complete programming guide
  type: TechArticle
- description: Create barcode image in C# with this step-by-step guide. Learn how
    to generate barcode, adjust barcode height pixels, and create multiple barcodes
    efficiently.
  name: Create barcode image in C# – complete programming guide
  steps:
  - name: Define the output folder
    text: Choose a folder where the generated PNG files will be stored. Using an absolute
      path avoids permission surprises.
  - name: Instantiate the barcode generator
    text: For a DataBar Omnidirectional barcode, pass `EncodeTypes.DatabarOmniDirectional`
      and the GS1‑128 data string.
  - name: Set common barcode parameters
    text: The most common visual tweaks are the X‑dimension (module width) and the
      bar height. Both are expressed in pixels.
  - name: Save the first barcode image
    text: '```csharp // Step 4: Save the barcode image with a 30 px height string
      file30 = Path.Combine(outputFolder, "DatabarBarHeight30Pixels.png"); barcode.Save(file30,
      BarCodeImageFormat.Png); ```'
  - name: Adjust the barcode height pixels
    text: Changing the height does not require a new `BarcodeGenerator` instance—just
      modify the parameter.
  - name: Save the second barcode image
    text: '```csharp // Step 6: Save the barcode image with the new 60 px height string
      file60 = Path.Combine(outputFolder, "DatabarBarHeight60Pixels.png"); barcode.Save(file60,
      BarCodeImageFormat.Png); ```'
  - name: Expected output
    text: 'After running the full sample, the `Barcodes` folder contains:'
  type: HowTo
tags:
- barcode
- C#
- image generation
title: Crea immagine di codice a barre in C# – guida completa alla programmazione
url: /it/python-java/general/create-barcode-image-in-c-complete-programming-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Crea immagine barcode in C# – guida completa di programmazione

Se hai bisogno di **creare un'immagine barcode** in un'applicazione .NET, questa guida ti mostra esattamente **come generare un barcode** utilizzando la libreria Aspose.BarCode. Vedrai come controllare i **pixel di altezza del barcode**, salvare l'immagine e produrre **più barcode** senza duplicare il codice.

Il tutorial copre tutto, dall'installazione del pacchetto alla personalizzazione delle dimensioni, così potrai copiare‑incollare un esempio pronto all'uso nel tuo progetto oggi.

## Prerequisiti

* .NET 6.0 SDK o versioni successive installato  
* Visual Studio 2022 (o qualsiasi IDE C#)  
* Pacchetto NuGet `Aspose.BarCode` – installa con  

```bash
dotnet add package Aspose.BarCode
```

Non sono richieste dipendenze aggiuntive.

## Come generare un'immagine barcode con BarcodeGenerator C#

La classe principale per creare un'immagine barcode è `BarcodeGenerator`. Essa incapsula il tipo di codifica, la stringa di dati e tutti i parametri di rendering.

### Passo 1: Definisci la cartella di output

Scegli una cartella dove verranno salvati i file PNG generati. Utilizzare un percorso assoluto evita sorprese legate ai permessi.

```csharp
// Step 1: Define the output folder
string outputFolder = Path.Combine(Environment.CurrentDirectory, "Barcodes");
Directory.CreateDirectory(outputFolder);
```

> **Perché?** Creare la cartella programmaticamente garantisce che le successive chiamate `Save` riescano anche su una macchina nuova.

### Passo 2: Istanzia il generatore di barcode

Per un barcode DataBar Omnidirectional, passa `EncodeTypes.DatabarOmniDirectional` e la stringa di dati GS1‑128.

```csharp
// Step 2: Create a DataBar Omnidirectional barcode generator with the data to encode
var barcode = new BarcodeGenerator(
    EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");
```

> **Nota:** L'oggetto `BarcodeGenerator` è riutilizzabile; puoi modificare i suoi parametri tra i salvataggi per **creare più barcode** dagli stessi dati.

### Passo 3: Imposta i parametri comuni del barcode

Le modifiche visive più comuni sono la X‑dimension (larghezza del modulo) e l'altezza delle barre. Entrambe sono espresse in pixel.

```csharp
// Step 3: Set common barcode parameters (X‑dimension and initial height)
barcode.Parameters.Barcode.XDimension.Pixels = 2;   // thin modules for sharper output
barcode.Parameters.Barcode.BarHeight.Pixels = 30;  // initial height – 30 px
```

> **Perché impostare la X‑dimension?** Una X‑dimension più piccola produce una risoluzione più alta, importante quando l'immagine verrà stampata o visualizzata su schermi ad alta DPI.

### Passo 4: Salva la prima immagine barcode

```csharp
// Step 4: Save the barcode image with a 30 px height
string file30 = Path.Combine(outputFolder, "DatabarBarHeight30Pixels.png");
barcode.Save(file30, BarCodeImageFormat.Png);
```

Il file `DatabarBarHeight30Pixels.png` ora contiene un barcode DataBar Omnidirectional alto 30 pixel.

### Passo 5: Regola i pixel di altezza del barcode

Modificare l'altezza non richiede una nuova istanza di `BarcodeGenerator`—basta modificare il parametro.

```csharp
// Step 5: Change the bar height to 60 px for the same barcode
barcode.Parameters.Barcode.BarHeight.Pixels = 60;
```

### Passo 6: Salva la seconda immagine barcode

```csharp
// Step 6: Save the barcode image with the new 60 px height
string file60 = Path.Combine(outputFolder, "DatabarBarHeight60Pixels.png");
barcode.Save(file60, BarCodeImageFormat.Png);
```

Ora hai due file PNG con diversi **pixel di altezza del barcode**, dimostrando quanto sia semplice creare variazioni di **immagine barcode**.

## Impostare dinamicamente i pixel di altezza del barcode

Spesso è necessario una serie di barcode con altezze che corrispondono a elementi UI o etichette stampate. Il metodo di supporto seguente astrae il cambiamento di altezza:

```csharp
/// <summary>
/// Saves a barcode image with a custom height.
/// </summary>
/// <param name="generator">Configured BarcodeGenerator instance.</param>
/// <param name="heightPx">Desired bar height in pixels.</param>
/// <param name="fileName">Target file name (including path).</param>
void SaveBarcodeWithHeight(BarcodeGenerator generator, int heightPx, string fileName)
{
    generator.Parameters.Barcode.BarHeight.Pixels = heightPx;
    generator.Save(fileName, BarCodeImageFormat.Png);
}
```

Ora puoi chiamare `SaveBarcodeWithHeight(barcode, 45, "BarHeight45.png");` per **creare un'immagine barcode** con un'altezza di 45 pixel in una singola riga.

## Creare più barcode in un ciclo

Quando hai una collezione di identificatori di prodotto, un ciclo `foreach` elimina il codice ripetitivo. Questo esempio mostra come **creare più barcode** da un array di GTIN.

```csharp
string[] gtins = { "01234567890123", "09876543210987", "12345098765432" };
int[] heights = { 30, 45, 60 }; // different heights for visual variety

for (int i = 0; i < gtins.Length; i++)
{
    // Encode each GTIN as a DataBar Omnidirectional barcode
    var gen = new BarcodeGenerator(EncodeTypes.DatabarOmniDirectional,
                                   $"(01){gtins[i]}");

    // Reuse the X‑dimension setting for consistency
    gen.Parameters.Barcode.XDimension.Pixels = 2;

    // Choose a height from the heights array (or calculate dynamically)
    int height = heights[i % heights.Length];
    string filePath = Path.Combine(outputFolder,
        $"Databar_{gtins[i]}_Height{height}px.png");

    SaveBarcodeWithHeight(gen, height, filePath);
}
```

Il ciclo produce tre file PNG, ognuno con un valore distinto di **pixel di altezza del barcode**. Poiché il metodo di supporto `SaveBarcodeWithHeight` incapsula il cambiamento di altezza, il ciclo principale rimane pulito e focalizzato sui dati.

### Output previsto

Dopo aver eseguito l'esempio completo, la cartella `Barcodes` contiene:

```
DatabarBarHeight30Pixels.png
DatabarBarHeight60Pixels.png
Databar_01234567890123_Height30px.png
Databar_09876543210987_Height45px.png
Databar_12345098765432_Height60px.png
```

Aprire qualsiasi PNG mostra un barcode DataBar Omnidirectional nitido che può essere scansionato dalle app mobili standard.

## Problemi comuni e consigli professionali

| Problema | Perché succede | Come evitarlo |
|----------|----------------|---------------|
| **EncodeTypes errati** | Usare un tipo 1D per un DataBar produrrà un'immagine illeggibile. | Scegli sempre `EncodeTypes.DatabarOmniDirectional` (o un'altra variante DataBar) per payload GS1‑128. |
| **X‑dimension insufficiente** | Una X‑dimension molto bassa può far scomparire le barre sottili su monitor a bassa risoluzione. | Mantieni `XDimension.Pixels` ≥ 2 per la visualizzazione su schermo; aumentala a 3‑4 per la stampa. |
| **Errori di percorso file** | I percorsi relativi possono risolversi in directory inaspettate. | Usa `Path.Combine` e `Environment.CurrentDirectory` per costruire percorsi assoluti. |
| **Sovrascrittura delle immagini** | Riutilizzare lo stesso nome file in un ciclo sovrascrive i risultati precedenti. | Includi identificatori unici (ad es., GTIN o timestamp) nel nome del file. |
| **Pacchetto NuGet mancante** | Il codice compila ma genera `FileNotFoundException` a runtime. | Verifica che `Aspose.BarCode` sia installato e che il progetto lo riferisca. |

## Esempio completo funzionante

Di seguito trovi il programma completo che puoi copiare in un'applicazione console. Include tutti i passaggi, i metodi di supporto e la gestione degli errori.

```csharp
using System;
using System.IO;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Prepare output folder
        string outputFolder = Path.Combine(Environment.CurrentDirectory, "Barcodes");
        Directory.CreateDirectory(outputFolder);

        // ---------- Single barcode with two heights ----------
        var barcode = new BarcodeGenerator(
            EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");

        barcode.Parameters.Barcode.XDimension.Pixels = 2;
        barcode.Parameters.Barcode.BarHeight.Pixels = 30;
        barcode.Save(Path.Combine(outputFolder, "DatabarBarHeight30Pixels.png"),
                     BarCodeImageFormat.Png);

        barcode.Parameters.Barcode.BarHeight.Pixels = 60;
        barcode.Save(Path.Combine(outputFolder, "DatabarBarHeight60Pixels.png"),
                     BarCodeImageFormat.Png);

        // ---------- Helper for dynamic heights ----------
        void SaveBarcodeWithHeight(BarcodeGenerator gen, int heightPx, string fileName)
        {
            gen.Parameters.Barcode.BarHeight.Pixels = heightPx;
            gen.Save(fileName, BarCodeImageFormat.Png);
        }

        // ---------- Multiple barcodes ----------
        string[] gtins = { "01234567890123", "09876543210987", "12345098765432" };
        int[] heights = { 30, 45, 60 };

        for (int i = 0; i < gtins.Length; i++)
        {
            var gen = new BarcodeGenerator(EncodeTypes.DatabarOmniDirectional,
                                           $"(01){gtins[i]}");
            gen.Parameters.Barcode.XDimension.Pixels = 2;

            int height = heights[i % heights.Length];
            string filePath = Path.Combine(outputFolder,
                $"Databar_{gtins[i]}_Height{height}px.png");

            SaveBarcodeWithHeight(gen, height, filePath);
        }

        Console.WriteLine($"Barcode images created in: {outputFolder}");
    }
}
```

Eseguendo questo programma

## Cosa dovresti imparare dopo?

I seguenti tutorial coprono argomenti strettamente correlati che si basano sulle tecniche dimostrate in questa guida. Ogni risorsa include esempi di codice completi e funzionanti con spiegazioni passo‑passo per aiutarti a padroneggiare funzionalità API aggiuntive ed esplorare approcci di implementazione alternativi nei tuoi progetti.

- [Crea Barcode Altezza Personalizzata – Barcode Unidimensionali](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-barcode-height-adjustment/)
- [Crea immagine barcode C# – Esempio GS1 DataMatrix](/barcode/english/net/gs1-barcode-encoding/gs1-datamatrix-example/)
- [Crea immagine barcode DotCode – righe e colonne (Aspose.BarCode)](/barcode/english/net/dotcode-barcode-configuration/dotcode-rows-columns-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}