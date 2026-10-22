---
category: general
date: 2026-10-21
description: Générez une image de code‑barres databar expanded stacked en C# à l’aide
  de BarcodeGenerator. Suivez ce guide étape par étape pour créer des images de codes‑barres,
  personnaliser les lignes et les colonnes, et exporter des fichiers PNG.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- databar expanded stacked
- generate barcode image
- barcode generator c#
- how to generate databar
- create databar barcode
language: fr
lastmod: 2026-10-21
og_description: Générez un code‑barres Databar Expanded Stacked en C# avec ce tutoriel.
  Apprenez à utiliser BarcodeGenerator, à définir les lignes et les colonnes, et à
  enregistrer des images PNG.
og_image_alt: Sample databar expanded stacked barcode image generated with C#
og_title: Générer un code‑barres Databar Expanded Stacked en C# – guide complet
schemas:
- author: Aspose
  dateModified: '2026-10-21'
  description: Generate a databar expanded stacked barcode image in C# using BarcodeGenerator.
    Follow this step‑by‑step guide to create barcode images, customize rows and columns,
    and export PNG files.
  headline: How to generate a databar expanded stacked barcode in C#
  type: TechArticle
- description: Generate a databar expanded stacked barcode image in C# using BarcodeGenerator.
    Follow this step‑by‑step guide to create barcode images, customize rows and columns,
    and export PNG files.
  name: How to generate a databar expanded stacked barcode in C#
  steps:
  - name: Basic barcode generation
    text: The simplest way to generate a **databar expanded stacked** image is to
      instantiate `BarcodeGenerator` with the desired `EncodeTypes` value and a plain
      text payload.
  - name: Customizing columns – create databar barcode with 4 columns
    text: You can control the number of columns using the `Parameters.Barcode.DataBar.Columns`
      property. The following example creates a barcode with **4 columns** while keeping
      the default row count.
  - name: Customizing rows – create databar barcode with 3 rows
    text: Similarly, you can adjust the row count via `Parameters.Barcode.DataBar.Rows`.
      The code below generates a barcode with **3 rows** and the default column count
      (4).
  - name: Exporting to other formats
    text: 'If you need a different image type (e.g., JPEG, BMP, or SVG), replace `BarCodeImageFormat.Png`
      with the appropriate enum value:'
  - name: Saving to a memory stream
    text: 'Sometimes you want to embed the barcode directly into a web response or
      a PDF without touching the file system. Use a `MemoryStream`:'
  - name: Handling invalid input
    text: 'The `BarcodeGenerator` validates the payload against the chosen symbology.
      If the data contains prohibited characters, an `ArgumentException` is thrown.
      Wrap the generation code in a try‑catch block to provide a friendly error message:'
  - name: Scaling the barcode image
    text: 'You can change the image size without altering the encoded data by setting
      `Parameters.Image.Width` and `Parameters.Image.Height`:'
  type: HowTo
tags:
- barcode
- C#
- Aspose.BarCode
title: Comment générer un code‑barres Databar Expanded Stacked en C#
url: /fr/python-java/general/how-to-generate-a-databar-expanded-stacked-barcode-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Comment générer un code‑barres databar expanded stacked en C#

Si vous devez générer un code‑barres **databar expanded stacked** en C#, ce guide vous montre comment faire. La symbologie databar expanded stacked est idéale pour encoder de grandes quantités de données sous une forme compacte, et vous pouvez créer l’image en quelques lignes de code seulement. Vous apprendrez également à **générer des fichiers d’image de code‑barres** dans différents formats et à personnaliser les lignes ou les colonnes pour s’adapter à votre environnement de numérisation.

Ce tutoriel couvre tout ce dont vous avez besoin pour commencer à produire des codes‑barres databar : installation de la bibliothèque requise, préparation du dossier de sortie, création du code‑barres avec des lignes ou colonnes personnalisées, et sauvegarde du résultat au format PNG. À la fin, vous serez capable de **créer des images de code‑barres databar** de façon programmatique et d’adapter le code à d’autres formats d’image ou scénarios d’exécution.

## Prérequis

Avant de commencer, assurez‑vous d’avoir :

* SDK .NET 6.0 ou ultérieur (le code fonctionne également avec .NET Core 3.1 et .NET Framework 4.7+)
* Un environnement de développement tel que Visual Studio 2022, Visual Studio Code ou Rider
* Un accès Internet pour installer le package NuGet **Barcode Generator C#** (Aspose.BarCode for .NET)

> **Astuce :** Si vous utilisez une pipeline CI/CD, ajoutez la référence du package NuGet à votre fichier de projet afin que les builds soient reproductibles.

## Installer la bibliothèque Barcode Generator C#

L’exemple utilise la bibliothèque Aspose.BarCode, qui fournit la classe `BarcodeGenerator` et l’énumération `EncodeTypes.DatabarExpandedStacked`.

```bash
dotnet add package Aspose.BarCode
```

La commande ajoute la dernière version stable à votre projet. Après l’installation, vous pouvez importer l’espace de noms dans vos fichiers C# :

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;
```

## Préparer le dossier de sortie

Un chemin de fichier fiable évite les erreurs d’exécution lorsque la bibliothèque tente d’écrire l’image. Le code suivant crée le répertoire s’il n’existe pas :

```csharp
using System;
using System.IO;

// Define the folder where barcode images will be saved
string outputFolder = Path.Combine(Environment.CurrentDirectory, "Barcodes");

// Ensure the folder exists
Directory.CreateDirectory(outputFolder);
```

> **Pourquoi c’est important :** Tenter d’enregistrer dans un répertoire inexistant déclenche une `IOException`. Créer le dossier à l’avance rend le code robuste tant pour le développement local que pour les environnements de production.

## Générer une image de code‑barres databar expanded stacked

### Génération de base du code‑barres

La façon la plus simple de générer une image **databar expanded stacked** consiste à instancier `BarcodeGenerator` avec la valeur `EncodeTypes` souhaitée et une charge utile en texte brut.

```csharp
// Create a barcode that encodes a long numeric string
var basicGenerator = new BarcodeGenerator(
    EncodeTypes.DatabarExpandedStacked,
    "01234567890123456789");

// Save the barcode as PNG
basicGenerator.Save(Path.Combine(outputFolder, "DatabarBasic.png"),
    BarCodeImageFormat.Png);
```

L’exécution du fragment produit `DatabarBasic.png` dans le dossier *Barcodes*. L’image contient un symbole databar expanded stacked standard avec la disposition par défaut (4 colonnes × 4 lignes).

### Personnalisation des colonnes – créer un code‑barres databar avec 4 colonnes

Vous pouvez contrôler le nombre de colonnes à l’aide de la propriété `Parameters.Barcode.DataBar.Columns`. L’exemple suivant crée un code‑barres avec **4 colonnes** tout en conservant le nombre de lignes par défaut.

```csharp
// Step 1: Define a generator with custom column count
var columnGenerator = new BarcodeGenerator(
    EncodeTypes.DatabarExpandedStacked,
    "Databar Expanded Stacked long");

// Set the column count to 4 (default rows = 4)
columnGenerator.Parameters.Barcode.DataBar.Columns = 4;

// Save the image
columnGenerator.Save(Path.Combine(outputFolder, "DatabarCols4.png"),
    BarCodeImageFormat.Png);
```

Le fichier résultant, **DatabarCols4.png**, ressemble à ceci :

![Code‑barres databar expanded stacked avec 4 colonnes](databar_cols4.png "Code‑barres databar expanded stacked avec 4 colonnes – généré avec C#")

*Texte alternatif de l’image (og_image_alt) :* **Exemple d'image de code‑barres databar expanded stacked générée avec C#** – cela satisfait l’exigence SEO pour le texte alternatif des images.

### Personnalisation des lignes – créer un code‑barres databar avec 3 lignes

De même, vous pouvez ajuster le nombre de lignes via `Parameters.Barcode.DataBar.Rows`. Le code ci‑dessous génère un code‑barres avec **3 lignes** et le nombre de colonnes par défaut (4).

```csharp
// Step 2: Define a generator with custom row count
var rowGenerator = new BarcodeGenerator(
    EncodeTypes.DatabarExpandedStacked,
    "Databar Expanded Stacked long");

// Set the row count to 3 (default columns = 4)
rowGenerator.Parameters.Barcode.DataBar.Rows = 3;

// Save the image
rowGenerator.Save(Path.Combine(outputFolder, "DatabarRows3.png"),
    BarCodeImageFormat.Png);
```

Le fichier **DatabarRows3.png** contient un symbole databar expanded stacked légèrement plus court verticalement, ce qui peut être utile pour des étiquettes à espace limité.

### Exportation vers d’autres formats

Si vous avez besoin d’un type d’image différent (par ex., JPEG, BMP ou SVG), remplacez `BarCodeImageFormat.Png` par la valeur d’énumération appropriée :

```csharp
columnGenerator.Save(Path.Combine(outputFolder, "DatabarCols4.jpg"),
    BarCodeImageFormat.Jpeg);
```

La bibliothèque prend également en charge les formats vectoriels comme SVG, idéaux pour l’impression haute résolution.

## Scénarios avancés

### Enregistrement dans un flux mémoire

Parfois, vous souhaitez intégrer le code‑barres directement dans une réponse web ou un PDF sans toucher au système de fichiers. Utilisez un `MemoryStream` :

```csharp
using System.IO;

// Generate barcode into a memory stream
using var ms = new MemoryStream();
columnGenerator.Save(ms, BarCodeImageFormat.Png);

// Reset stream position before reading
ms.Position = 0;

// Example: return the stream as a file download in ASP.NET Core
// return File(ms.ToArray(), "image/png", "databar.png");
```

### Gestion des entrées invalides

`BarcodeGenerator` valide la charge utile par rapport à la symbologie choisie. Si les données contiennent des caractères interdits, une `ArgumentException` est levée. Enveloppez le code de génération dans un bloc try‑catch pour fournir un message d’erreur convivial :

```csharp
try
{
    var gen = new BarcodeGenerator(EncodeTypes.DatabarExpandedStacked, "INVALID*DATA");
    gen.Save(Path.Combine(outputFolder, "Invalid.png"), BarCodeImageFormat.Png);
}
catch (ArgumentException ex)
{
    Console.WriteLine($"Failed to generate barcode: {ex.Message}");
}
```

### Redimensionnement de l’image du code‑barres

Vous pouvez modifier la taille de l’image sans altérer les données encodées en définissant `Parameters.Image.Width` et `Parameters.Image.Height` :

```csharp
columnGenerator.Parameters.Image.Width = 300;   // pixels
columnGenerator.Parameters.Image.Height = 150; // pixels
columnGenerator.Save(Path.Combine(outputFolder, "DatabarLarge.png"),
    BarCodeImageFormat.Png);
```

Le redimensionnement est utile lorsque le code‑barres doit répondre à une exigence DPI spécifique pour les scanners.

## Exemple complet fonctionnel

Voici une application console complète, prête à être exécutée, qui démontre toutes les étapes abordées :

```csharp
using System;
using System.IO;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace DatabarExpandedStackedDemo
{
    class Program
    {
        static void Main()
        {
            // 1️⃣ Prepare output folder
            string outputFolder = Path.Combine(
                Environment.CurrentDirectory, "Barcodes");
            Directory.CreateDirectory(outputFolder);

            // 2️⃣ Generate basic barcode
            var basic = new BarcodeGenerator(
                EncodeTypes.DatabarExpandedStacked,
                "01234567890123456789");
            basic.Save(Path.Combine(outputFolder, "DatabarBasic.png"),
                BarCodeImageFormat.Png);

            // 3️⃣ Generate barcode with 4 columns
            var colGen = new BarcodeGenerator(
                EncodeTypes.DatabarExpandedStacked,
                "Databar Expanded Stacked long");
            colGen.Parameters.Barcode.DataBar.Columns = 4;
            colGen.Save(Path.Combine(outputFolder, "DatabarCols4.png"),
                BarCodeImageFormat.Png);

            // 4️⃣ Generate barcode with 3 rows
            var rowGen = new BarcodeGenerator(
                EncodeTypes.DatabarExpandedStacked,
                "Databar Expanded Stacked long");
            rowGen.Parameters.Barcode.DataBar.Rows = 3;
            rowGen.Save(Path.Combine(outputFolder, "DatabarRows3.png"),
                BarCodeImageFormat.Png);

            // 5️⃣ Export to JPEG as an extra format
            colGen.Save(Path.Combine(outputFolder, "DatabarCols4.jpg"),
                BarCodeImageFormat.Jpeg);

            Console.WriteLine("All barcode images have been generated in:");
            Console.WriteLine(outputFolder);
        }
    }
}
```

**Sortie attendue**


## Que devriez‑vous apprendre ensuite ?


Les tutoriels suivants couvrent des sujets étroitement liés qui s’appuient sur les techniques présentées dans ce guide. Chaque ressource inclut des exemples de code complets avec des explications pas à pas pour vous aider à maîtriser d’autres fonctionnalités de l’API et explorer des approches d’implémentation alternatives dans vos propres projets.

- [Comment définir les colonnes pour un code‑barres Databar Expanded Stacked – guide complet C#](/barcode/english/python-java/general/how-to-set-columns-for-a-databar-expanded-stacked-barcode-co/)
- [Comment créer un exemple de générateur de code‑barres en C# avec DataBar Expanded Stacked](/barcode/english/python-java/general/how-to-build-a-barcode-generator-example-in-c-with-databar-e/)
- [Guide du code‑barres databar expanded stacked – comment le générer et le dimensionner en C#](/barcode/english/python-java/general/databar-expanded-stacked-barcode-guide-how-to-generate-and-s/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}