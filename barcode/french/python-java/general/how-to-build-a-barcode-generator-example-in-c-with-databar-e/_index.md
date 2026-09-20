---
category: general
date: 2026-09-19
description: Exemple de générateur de code‑barres en C# montrant comment générer un
  code‑barres en C# à l’aide d’Aspose.BarCode pour les dispositions en colonnes et
  en lignes.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- barcode generator example
- generate barcode c#
language: fr
lastmod: 2026-09-19
og_description: L'exemple de générateur de code-barres montre comment générer des
  codes-barres en C# avec des dispositions en colonnes et en lignes en utilisant Aspose.BarCode.
og_image_alt: C# barcode generator example output showing a DataBar Expanded Stacked
  barcode with 4 columns
og_title: exemple de générateur de code-barres – créer des codes-barres DataBar Expanded
  Stacked en C#
schemas:
- author: Aspose
  dateModified: '2026-09-19'
  description: barcode generator example in C# showing how to generate barcode C#
    using Aspose.BarCode for column and row layouts
  headline: How to build a barcode generator example in C# with DataBar Expanded Stacked
  type: TechArticle
tags:
- barcode
- C#
- Aspose.BarCode
title: Comment créer un exemple de générateur de code‑barres en C# avec DataBar Expanded
  Stacked
url: /fr/python-java/general/how-to-build-a-barcode-generator-example-in-c-with-databar-e/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# barcode generator example – create DataBar Expanded Stacked barcodes in C#

Si vous avez besoin d’un **exemple de générateur de code-barres** fonctionnant dans un projet .NET, ce guide vous montre exactement comment générer des codes-barres C# en utilisant la bibliothèque Aspose.BarCode. Vous verrez comment configurer un code‑barres DataBar Expanded Stacked pour une disposition en colonnes et une disposition en lignes, et vous obtiendrez du code prêt à l’emploi qui produit des images PNG.

Le tutoriel couvre tout, de l’installation du package NuGet à l’enregistrement des images finales, afin que vous puissiez copier le code dans votre propre solution sans recherche supplémentaire.

## What you’ll learn

* Comment installer et référencer Aspose.BarCode dans un projet C#.  
* Comment créer un **exemple de générateur de code‑barres** qui encode une longue chaîne de données.  
* Comment définir une disposition à 4 colonnes et une disposition à 3 lignes sur le même type de code‑barres.  
* Comment enregistrer les images générées au format PNG.  

À la fin de cet article, vous disposerez de deux fichiers PNG prêts à l’emploi : `ExpandedStackedCols4.png` (quatre colonnes) et `ExpandedStackedRows3.png` (trois lignes).

## Prerequisites

* SDK .NET 6.0 ou ultérieur (le code fonctionne également avec .NET Framework 4.7.2).  
* Visual Studio 2022, VS Code ou tout IDE C# de votre choix.  
* Accès Internet pour télécharger le package NuGet **Aspose.BarCode**.  

Aucun service externe supplémentaire n’est requis.

## Step 1: Install the Aspose.BarCode NuGet package

Ouvrez un terminal dans le dossier de votre projet et exécutez :

```bash
dotnet add package Aspose.BarCode
```

La commande ajoute la dernière version stable d’Aspose.BarCode à votre fichier projet. Après la restauration du package, vous pouvez référencer ses espaces de noms dans vos fichiers source C#.

## Step 2: Add the required using directives

Créez une nouvelle application console C# (ou ajoutez le code à un projet existant) et incluez les instructions `using` suivantes en haut du fichier :

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;
```

Ces directives vous donnent accès à la classe `BarcodeGenerator` et à l’énumération `EncodeTypes` utilisées dans le **exemple de générateur de code‑barres**.

## Step 3: Create a barcode generator example with a 4‑column layout

La première partie de l’exemple construit un code‑barres DataBar Expanded Stacked qui utilise une disposition à quatre colonnes. Le code ci‑dessous suit exactement les étapes montrées dans l’extrait original, mais ajoute des commentaires expliquant pourquoi chaque ligne est nécessaire.

```csharp
// Step 3.1: Initialise the generator with the desired barcode type and data
BarcodeGenerator generator = new BarcodeGenerator(
    EncodeTypes.DatabarExpandedStacked,   // DataBar Expanded Stacked type
    "Long data string");                  // The data you want to encode

// Step 3.2: Configure the barcode to use a 4‑column layout
generator.Parameters.Barcode.DataBar.Columns = 4;

// Step 3.3: Save the image as a PNG file
generator.Save("ExpandedStackedCols4.png", BarCodeImageFormat.Png);
```

**Why this works**

* `EncodeTypes.DatabarExpandedStacked` indique à Aspose.BarCode de générer un symbole DataBar Expanded Stacked, adapté aux applications de vente au détail.  
* Définir `DataBar.Columns` à `4` force le générateur à diviser le symbole en quatre sections verticales, améliorant la lisibilité sur des étiquettes étroites.  
* `Save` écrit le code‑barres sur le disque ; l’argument `BarCodeImageFormat.Png` garantit une qualité d’image sans perte.

L’exécution de ce bloc crée `ExpandedStackedCols4.png` dans le répertoire de travail de l’application. Le fichier contient un code‑barres haute résolution qui peut être scanné par n’importe quel lecteur DataBar standard.

## Step 4: Re‑initialize the generator for a different layout

Pour démontrer une disposition basée sur les lignes, vous avez besoin d’une nouvelle instance `BarcodeGenerator`. Ré‑initialiser garantit que le paramètre de colonne précédent n’affecte pas la nouvelle configuration.

```csharp
// Step 4.1: Create a new generator with the same data string
generator = new BarcodeGenerator(
    EncodeTypes.DatabarExpandedStacked,
    "Long data string");
```

## Step 5: Configure the barcode to use a 3‑row layout

L’API DataBar prend également en charge une disposition en lignes. Définir la propriété `Rows` indique combien de tranches horizontales le symbole contiendra.

```csharp
// Step 5.1: Apply a 3‑row layout
generator.Parameters.Barcode.DataBar.Rows = 3;

// Step 5.2: Save the row‑oriented barcode
generator.Save("ExpandedStackedRows3.png", BarCodeImageFormat.Png);
```

**Why you might choose rows over columns**

Les lignes sont utiles lorsque la hauteur de l’étiquette est limitée mais que la largeur est suffisante. Une disposition à trois lignes compresse le code‑barres verticalement tout en conservant la quantité de données requise.

## Complete source file

Voici un fichier complet et autonome `Program.cs` que vous pouvez compiler et exécuter directement. Il inclut les exemples de colonne et de ligne, de sorte que vous obtenez deux fichiers PNG en une seule exécution.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

namespace BarcodeGeneratorExample
{
    class Program
    {
        static void Main(string[] args)
        {
            // Data to encode – replace with your own value if needed
            const string data = "Long data string";

            // ---------- Column layout (4 columns) ----------
            var columnGenerator = new BarcodeGenerator(
                EncodeTypes.DatabarExpandedStacked,
                data);

            // Set 4‑column layout
            columnGenerator.Parameters.Barcode.DataBar.Columns = 4;

            // Save the column image
            columnGenerator.Save("ExpandedStackedCols4.png", BarCodeImageFormat.Png);
            Console.WriteLine("Saved ExpandedStackedCols4.png (4‑column layout)");

            // ---------- Row layout (3 rows) ----------
            var rowGenerator = new BarcodeGenerator(
                EncodeTypes.DatabarExpandedStacked,
                data);

            // Set 3‑row layout
            rowGenerator.Parameters.Barcode.DataBar.Rows = 3;

            // Save the row image
            rowGenerator.Save("ExpandedStackedRows3.png", BarCodeImageFormat.Png);
            Console.WriteLine("Saved ExpandedStackedRows3.png (3‑row layout)");
        }
    }
}
```

### Expected output

Après l’exécution du programme, vous verrez deux messages dans la console confirmant la création des fichiers :

```
Saved ExpandedStackedCols4.png (4‑column layout)
Saved ExpandedStackedRows3.png (3‑row layout)
```

Les deux fichiers PNG afficheront un code‑barres DataBar Expanded Stacked qui encode la chaîne `"Long data string"`. Scanner l’une ou l’autre image avec un lecteur de code‑barres standard renvoie les données d’origine.

## Common questions and edge cases

| Question | Answer |
|----------|--------|
| **Can I change the image format?** | Yes. Replace `BarCodeImageFormat.Png` with `Jpeg`, `Bmp`, or `Tiff` depending on your requirements. |
| **What if the data string is shorter?** | The DataBar format automatically adjusts the symbol size; you do not need to modify the layout settings. |
| **How do I set the barcode size (width/height)?** | Use `generator.Parameters.Image.Width` and `generator.Parameters.Image.Height` before calling `Save`. |
| **Is it possible to add a human‑readable caption?** | Set `generator.Parameters.Barcode.CodeText` and enable `generator.Parameters.Barcode.CodeLocation = CodeLocation.Above`. |
| **What .NET versions are supported?** | Aspose.BarCode supports .NET Standard 2.0, .NET 5/6, and .NET Framework 4.6.1+. |

Addressing these variations makes the **exemple de générateur de code‑barres** robust enough for production use.

## Pro tips

* **Reuse the generator object only when the layout stays the same.** Creating a new instance for each layout, as shown in Steps 4‑5, prevents accidental property carry‑over.  
* **Validate the generated barcode** with `generator.Validate()` if you need to ensure compliance with ISO/GS1 standards.  
* **Batch processing:** Wrap the column and row logic inside a loop that iterates over a list of layout configurations. This reduces code duplication when you need many variations.

## Conclusion

This **exemple de générateur de code‑barres** demonstrates how to **generate barcode C#** code that produces both a 4‑column and a 3‑row DataBar Expanded Stacked barcode. You now have a complete, runnable program, an understanding of the key properties (`Columns`, `Rows`), and practical tips for extending the solution.

Next, explore related topics such as **customizing barcode colors**, **embedding barcodes in PDF documents**, or **generating QR codes with Aspose.BarCode**. Each of those subjects builds on the same API principles covered here.

Feel free to experiment with different data strings, image formats, and layout combinations. Happy coding!

## What Should You Learn Next?

The following tutorials cover closely related topics that build on the techniques demonstrated in this guide. Each resource includes complete working code examples with step-by-step explanations to help you master additional API features and explore alternative implementation approaches in your own projects.

- [Barcode Generator Example in C# – Set Columns, Rows & Export Image](/barcode/english/python-java/general/barcode-generator-example-in-c-set-columns-rows-export-image/)
- [Generate Aspose.BarCode Databar barcode using .NET API – Row & Column Configuration](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-row-column-configuration/)
- [Barcode generator example in C# – set width and height](/barcode/english/python-java/general/barcode-generator-example-in-c-set-width-and-height/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}