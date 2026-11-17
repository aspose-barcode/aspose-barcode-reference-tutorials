---
category: general
date: 2026-11-17
description: Comment créer des codes‑barres PDF417 avec Aspose.BarCode – guide étape
  par étape qui montre également comment créer un code‑barres Aspose en C#.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to create pdf417
- create barcode aspose
language: fr
lastmod: 2026-11-17
og_description: Comment créer des codes-barres PDF417 avec Aspose.BarCode. Ce tutoriel
  vous guide à travers les étapes précises pour créer un code-barres Aspose, configurer
  les métadonnées Macro PDF417 et enregistrer l'image.
og_image_alt: Screenshot of a PDF417 barcode generated with Aspose.BarCode in C#
og_title: Comment créer des codes-barres PDF417 avec Aspose.BarCode – guide complet
  C#
schemas:
- author: Aspose
  dateModified: '2026-11-17'
  description: How to create PDF417 barcodes using Aspose.BarCode – step‑by‑step guide
    that also shows how to create barcode aspose in C#.
  headline: How to create PDF417 barcodes with Aspose.BarCode in C#
  type: TechArticle
- description: How to create PDF417 barcodes using Aspose.BarCode – step‑by‑step guide
    that also shows how to create barcode aspose in C#.
  name: How to create PDF417 barcodes with Aspose.BarCode in C#
  steps:
  - name: Set up the project and import Aspose.BarCode
    text: 'Create a new console project and add the Aspose.BarCode NuGet package:'
  - name: Initialise the `BarcodeGenerator` for Macro PDF417
    text: The `BarcodeGenerator` constructor takes the barcode type and the text you
      want to encode. For Macro PDF417 you use `EncodeTypes.MacroPdf417`.
  - name: Configure appearance and Macro PDF417 metadata
    text: Configure appearance and Macro PDF417 metadata
  - name: Save the barcode image
    text: '```csharp // Choose the output folder (ensure it exists) and save as PNG.
      string outputPath = "MacroPdf417.png"; generator.Save(outputPath, BarCodeImageFormat.Png);
      Console.WriteLine($"PDF417 barcode saved to {outputPath}"); } ```'
  - name: Full, runnable example
    text: 'Putting everything together, here’s the complete program you can compile
      and run immediately:'
  type: HowTo
tags:
- barcode
- pdf417
- aspose
- csharp
title: Comment créer des codes-barres PDF417 avec Aspose.BarCode en C#
url: /fr/net/compact-pdf417-encoding/how-to-create-pdf417-barcodes-with-aspose-barcode-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Comment créer des codes-barres PDF417 avec Aspose.BarCode en C#

Si vous devez **créer des codes-barres PDF417** pour l’inventaire, l’expédition ou le suivi de documents, ce guide vous montre les étapes exactes avec Aspose.BarCode. Vous verrez comment créer un code-barres Aspose, configurer les champs Macro PDF417 et exporter le résultat sous forme d’image PNG — le tout dans un seul programme C# exécutable.

Créer un code-barres PDF417 est courant lorsque vous devez encoder de grandes quantités de données dans un format compact et lisible par machine. Aspose.BarCode rend le processus simple, vous permettant d’ajuster finement les dimensions, les colonnes et l’ensemble complet des métadonnées Macro PDF417. À la fin de ce tutoriel, vous disposerez d’un exemple complet et autonome que vous pourrez intégrer à n’importe quel projet .NET.

## Prérequis

Avant de commencer, assurez‑vous d’avoir :

* .NET 6.0 SDK ou version ultérieure (le code fonctionne également avec .NET Framework 4.7+).  
* Une licence valide d’Aspose.BarCode pour .NET (l’évaluation gratuite fonctionne pour les tests).  
* Visual Studio 2022, VS Code ou tout IDE compatible C#.  
* Connaissances de base de la syntaxe C# et de l’instruction `using`.

> **Astuce :** Si vous exécutez l’exemple sans licence, Aspose ajoutera un petit filigrane à l’image générée.

## Comment créer un code-barres PDF417 avec Aspose.BarCode

Les sections suivantes découpent l’implémentation en quatre étapes claires. Chaque étape comprend un extrait de code, une explication du **pourquoi** du code, et des conseils pratiques que vous pouvez appliquer à vos propres projets.

### Étape 1 : Configurer le projet et importer Aspose.BarCode

Créez un nouveau projet console et ajoutez le package NuGet Aspose.BarCode :

```bash
dotnet new console -n Pdf417Demo
cd Pdf417Demo
dotnet add package Aspose.BarCode
```

Puis ouvrez `Program.cs` et ajoutez les espaces de noms requis :

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;
```

*Pourquoi c’est important :* L’importation de `Aspose.BarCode.Generation` vous donne accès à `BarcodeGenerator` et à l’énumération `EncodeTypes`, qui sont les classes principales pour la création de codes-barres.

### Étape 2 : Initialiser le `BarcodeGenerator` pour Macro PDF417

Le constructeur `BarcodeGenerator` prend le type de code‑barres et le texte que vous souhaitez encoder. Pour Macro PDF417, utilisez `EncodeTypes.MacroPdf417`.

```csharp
// Initialise a Macro PDF417 generator with the data you want to encode.
using (BarcodeGenerator generator = 
       new BarcodeGenerator(EncodeTypes.MacroPdf417, "Sample text for PDF417"))
{
    // The generator instance will be disposed automatically at the end of the block.
```

*Pourquoi c’est important :* L’instruction `using` garantit que les ressources non gérées (comme les handles GDI+) sont libérées rapidement, évitant les fuites de mémoire dans les services de longue durée.

### Étape 3 : Configurer l’apparence et les métadonnées Macro PDF417

#### 3.1 Ajuster les paramètres visuels

```csharp
    // Set the module (X) dimension – 2 pixels gives a reasonably dense barcode.
    generator.Parameters.Barcode.XDimension.Pixels = 2;

    // Define the number of columns; fewer columns make the barcode taller.
    generator.Parameters.Barcode.Pdf417.Columns = 5;
```

#### 3.2 Remplir les champs Macro PDF417

Macro PDF417 vous permet de diviser un gros document en plusieurs segments de code‑barres. Les champs ci‑dessous sont optionnels mais souvent requis pour les systèmes logistiques ou de gestion de documents.

```csharp
    // Unique identifier for the whole file (must be the same across all segments).
    generator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;

    // Segment index (starting at 1). Here we generate the 12th segment.
    generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;

    // Total number of segments that will be produced.
    generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;

    // Human‑readable file name, useful for audits.
    generator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";

    // CCITT‑16 checksum – helps receivers verify data integrity.
    generator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234;

    // Approximate file size in bytes; some scanners use this for validation.
    generator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400_000;

    // Timestamp of the original file creation.
    generator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = 
        new DateTime(2024, 5, 1);

    // Optional address fields that can be read by advanced scanners.
    generator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
    generator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";

    // Terminator tells the scanner that this is the last segment.
    generator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = 
        Pdf417MacroTerminator.Set;
```

*Pourquoi ces champs sont utiles :*  
* **FileID** lie tous les segments, permettant la reconstruction.  
* **SegmentID** et **SegmentsCount** indiquent au lecteur l’ordre et quand la série est complète.  
* **Checksum** et **FileSize** offrent des vérifications d’intégrité rapides sans décoder l’ensemble du payload.

> **Attention :** Le `MacroPdf417FileID` doit être unique pour chaque document logique. Réutiliser le même ID pour des fichiers non liés peut entraîner des erreurs de reconstruction.

### Étape 4 : Enregistrer l’image du code‑barres

```csharp
    // Choose the output folder (ensure it exists) and save as PNG.
    string outputPath = "MacroPdf417.png";
    generator.Save(outputPath, BarCodeImageFormat.Png);
    Console.WriteLine($"PDF417 barcode saved to {outputPath}");
}
```

*Pourquoi PNG ?* PNG préserve les données de pixels exactes sans artefacts de compression, ce qui est idéal pour les scanners de codes‑barres qui dépendent de bords nets.

### Exemple complet, exécutable

En réunissant tous les éléments, voici le programme complet que vous pouvez compiler et exécuter immédiatement :

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace Pdf417Demo
{
    class Program
    {
        static void Main()
        {
            // Step 1‑4: generate a Macro PDF417 barcode and save it as PNG
            using (BarcodeGenerator generator = 
                   new BarcodeGenerator(EncodeTypes.MacroPdf417, "Sample text for PDF417"))
            {
                // Appearance
                generator.Parameters.Barcode.XDimension.Pixels = 2;
                generator.Parameters.Barcode.Pdf417.Columns = 5;

                // Macro PDF417 metadata
                generator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
                generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;
                generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;
                generator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";
                generator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234;
                generator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400_000;
                generator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = 
                    new DateTime(2024, 5, 1);
                generator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
                generator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
                generator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = 
                    Pdf417MacroTerminator.Set;

                // Save
                string outputPath = "MacroPdf417.png";
                generator.Save(outputPath, BarCodeImageFormat.Png);
                Console.WriteLine($"PDF417 barcode saved to {outputPath}");
            }
        }
    }
}
```

**Sortie attendue :** Après l’exécution du programme, vous trouverez `MacroPdf417.png` dans le dossier du projet. L’ouverture de l’image montre un code‑barres PDF417 dense et à fort contraste qui encode « Sample text for PDF417 » ainsi que les métadonnées macro que vous avez fournies.

## Questions fréquentes et gestion des cas limites

| Question | Réponse |
|----------|--------|
| *Puis-je générer plusieurs segments dans une boucle ?* | Oui. Incrémentez `MacroPdf417SegmentID` à chaque itération, conservez `MacroPdf417FileID` constant, et mettez à jour `MacroPdf417SegmentsCount` uniquement après avoir connu le nombre total de segments. |
| *Que faire si les données dépassent un seul symbole PDF417 ?* | Macro |

## Que devriez‑vous apprendre ensuite ?

Les tutoriels suivants couvrent des sujets étroitement liés qui s’appuient sur les techniques présentées dans ce guide. Chaque ressource comprend des exemples de code complets avec des explications pas à pas pour vous aider à maîtriser d’autres fonctionnalités de l’API et explorer des approches d’implémentation alternatives dans vos propres projets.

- [Comment créer un code‑barres macro PDF417 en C# avec Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/how-to-create-macro-pdf417-barcode-in-c-using-aspose-barcode/)
- [Comment créer un code‑barres micro PDF417 en C# avec Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/how-to-create-micro-pdf417-barcode-in-c/)
- [Comment créer un code‑barres – Compact PDF417 avec Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}