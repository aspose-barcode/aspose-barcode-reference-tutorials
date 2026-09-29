---
category: general
date: 2026-08-15
description: Immagine del codice a barre PNG in C# – impara a generare codici a barre
  postali, creare un codice Planet e modificare l'altezza del codice a barre con un
  semplice generatore.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- barcode image png
- barcode generator c#
- generate postal barcode
- create planet barcode
- change barcode height
language: it
lastmod: 2026-08-15
og_description: Il tutorial Barcode image PNG in C# mostra come generare codici a
  barre postali, creare un codice a barre Planet e modificare l'altezza del codice
  a barre utilizzando l'API BarcodeGenerator.
og_image_alt: Screenshot of generated PNG barcode with custom height using C# BarcodeGenerator
og_title: Immagine del codice a barre PNG in C# – genera e regola i codici a barre
schemas:
- author: Aspose
  dateModified: '2026-08-15'
  description: Barcode image PNG in C# – learn how to generate postal barcodes, create
    a Planet barcode, and change barcode height with a simple generator.
  headline: Barcode image PNG in C# generate barcodes, change height
  type: TechArticle
tags:
- barcode
- C#
- PNG
- postal
- generator
title: Immagine barcode PNG in C# genera codici a barre, modifica l'altezza
url: /it/python-java/general/barcode-image-png-in-c-generate-barcodes-change-height/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Immagine barcode PNG in C# – genera barcode, cambia altezza

Se hai bisogno di una **barcode image PNG** in C#, questa guida ti accompagna passo passo nel processo completo. Imparerai a generare barcode postali, a creare un barcode Planet e a modificare l'altezza del barcode senza lasciare l'IDE.

Generare barcode PNG affidabili è una necessità comune per etichette di spedizione, sistemi di inventario e soluzioni di mailing automatizzate. Alla fine di questo tutorial avrai a disposizione uno snippet di codice riutilizzabile che produce file PNG di alta qualità sia per i formati Planet che RM4SCC, e comprenderai come regolare l'altezza delle barre per soddisfare le specifiche postali.

## Cosa ti servirà

- .NET 6+ o .NET Framework 4.7.2 (l'API BarcodeGenerator funziona con qualsiasi runtime .NET recente)  
- Un riferimento al pacchetto NuGet **Aspose.BarCode for .NET** (o a qualsiasi libreria compatibile che fornisca `BarcodeGenerator`, `EncodeTypes` e `BarCodeImageFormat`)  
- Familiarità di base con la sintassi C# e con I/O di file  

Non sono richiesti strumenti aggiuntivi; il codice funziona in Visual Studio, Rider o con la CLI `dotnet`.

## Immagine barcode PNG – generazione di base

Il primo passo è creare una **barcode image PNG** con dimensioni predefinite. Questo stabilisce il file di base che potrai personalizzare in seguito.

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;

// Define the output folder (replace with your own path)
string outputFolder = @"C:\Barcodes";

// Ensure the folder exists
Directory.CreateDirectory(outputFolder);

// 1️⃣ Create a Planet barcode generator with default height
BarcodeGenerator planetGenerator = new BarcodeGenerator(EncodeTypes.Planet, "123456");

// Set the module width (X‑dimension) to 4 pixels – this defines the thin bar size
planetGenerator.Parameters.Barcode.XDimension.Pixels = 4;

// Save the image as PNG; this is the first **barcode image PNG** you’ll produce
planetGenerator.Save(Path.Combine(outputFolder, "PlanetBarHeightDefault.png"),
                     BarCodeImageFormat.Png);
```

**Perché funziona:**  
- `EncodeTypes.Planet` indica al generatore di utilizzare la simbologia Planet, necessaria per molti servizi postali.  
- `XDimension.Pixels` controlla la larghezza della barra più piccola; un valore di 4 px produce un barcode leggibile nelle dimensioni tipiche delle etichette.  
- Il metodo `Save` scrive un file **barcode image PNG** su disco, preservando tutte le informazioni vettoriali come pixel raster.

## Cambia altezza barcode – personalizzazione del peso visivo

Le linee guida postali spesso richiedono un'altezza specifica delle barre. Il frammento seguente dimostra come impostare un'altezza personalizzata di 100 pixel per lo stesso barcode Planet.

```csharp
// 2️⃣ Apply a custom 100‑pixel bar height
planetGenerator.Parameters.Barcode.BarHeight.Pixels = 100;

// Overwrite or save as a new file to keep both versions
planetGenerator.Save(Path.Combine(outputFolder, "PlanetBarHeight100.png"),
                     BarCodeImageFormat.Png);
```

**Perché cambiare l'altezza:**  
Una barra più alta migliora l'affidabilità della scansione su stampanti a bassa risoluzione, mentre una barra più corta riduce lo spazio occupato sull'etichetta. La proprietà `BarHeight.Pixels` ti consente di regolare finemente questo attributo senza influire sulla dimensione X.

## Genera barcode postale – esempio RM4SCC

Il formato RM4SCC è un altro barcode postale comune utilizzato nel Regno Unito. I passaggi di generazione rispecchiano l'esempio Planet, rafforzando il modello **barcode generator c#**.

```csharp
// 3️⃣ Create an RM4SCC barcode generator with default height
BarcodeGenerator rm4sccGenerator = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");

// Keep the same module width for consistency
rm4sccGenerator.Parameters.Barcode.XDimension.Pixels = 4;

// Save the default‑height PNG
rm4sccGenerator.Save(Path.Combine(outputFolder, "RM4SCCBarHeightDefault.png"),
                     BarCodeImageFormat.Png);
```

## Cambia altezza barcode – variazione RM4SCC

Proprio come per il barcode Planet, puoi regolare l'altezza delle barre RM4SCC. Il codice qui sotto imposta l'altezza a 100 px, producendo un secondo **barcode image PNG** per la stessa stringa di dati.

```csharp
// 4️⃣ Set a custom 100‑pixel bar height for RM4SCC
rm4sccGenerator.Parameters.Barcode.BarHeight.Pixels = 100;

// Save the customized PNG
rm4sccGenerator.Save(Path.Combine(outputFolder, "RM4SCCBarHeight100.png"),
                     BarCodeImageFormat.Png);
```

## Esempio completo, eseguibile

Unendo tutti i passaggi ottieni un unico programma autonomo che crea quattro file PNG:

```csharp
using System;
using System.IO;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Program
{
    static void Main()
    {
        string outputFolder = @"C:\Barcodes";
        Directory.CreateDirectory(outputFolder);

        // Planet barcode – default height
        var planet = new BarcodeGenerator(EncodeTypes.Planet, "123456");
        planet.Parameters.Barcode.XDimension.Pixels = 4;
        planet.Save(Path.Combine(outputFolder, "PlanetBarHeightDefault.png"),
                    BarCodeImageFormat.Png);

        // Planet barcode – custom 100‑pixel height
        planet.Parameters.Barcode.BarHeight.Pixels = 100;
        planet.Save(Path.Combine(outputFolder, "PlanetBarHeight100.png"),
                    BarCodeImageFormat.Png);

        // RM4SCC barcode – default height
        var rm4scc = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");
        rm4scc.Parameters.Barcode.XDimension.Pixels = 4;
        rm4scc.Save(Path.Combine(outputFolder, "RM4SCCBarHeightDefault.png"),
                    BarCodeImageFormat.Png);

        // RM4SCC barcode – custom 100‑pixel height
        rm4scc.Parameters.Barcode.BarHeight.Pixels = 100;
        rm4scc.Save(Path.Combine(outputFolder, "RM4SCCBarHeight100.png"),
                    BarCodeImageFormat.Png);

        Console.WriteLine("All barcode PNG files have been generated in " +


## Cosa dovresti imparare dopo?

I tutorial seguenti coprono argomenti strettamente correlati che si basano sulle tecniche dimostrate in questa guida. Ogni risorsa include esempi di codice completi e funzionanti con spiegazioni passo‑passo per aiutarti a padroneggiare funzionalità aggiuntive dell'API ed esplorare approcci di implementazione alternativi nei tuoi progetti.

- [Crea Barcode Altezza Personalizzata – Codici a Barre Unidimensionali](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-barcode-height-adjustment/)
- [Crea Barcode PNG – Rapporto d'Aspetto DataMatrix – Aspose.BarCode](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-aspect-ratio-customization/)
- [Crea immagine barcode C# – Esempio GS1 DataMatrix](/barcode/english/net/gs1-barcode-encoding/gs1-datamatrix-example/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}