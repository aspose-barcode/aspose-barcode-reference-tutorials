---
category: general
date: 2026-10-18
description: Apprenez à créer un code‑barres PDF417 en C# avec Aspose.BarCode. Ce
  tutoriel couvre la génération de PDF417 basique, compact, macro et micro avec le
  code complet.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create pdf417 barcode
- how to create pdf417
language: fr
lastmod: 2026-10-18
og_description: Créez un code‑barres PDF417 en C# avec Aspose.BarCode. Suivez ce guide
  pour générer pas à pas des codes‑barres PDF417 basiques, compacts, macro et micro.
og_image_alt: Screenshot showing a generated PDF417 barcode saved as an image file
og_title: Créer un code‑barres PDF417 en C# – tutoriel complet Aspose.BarCode
schemas:
- author: Aspose
  dateModified: '2026-10-18'
  description: Learn how to create PDF417 barcode in C# with Aspose.BarCode. This
    tutorial covers basic, compact, macro and micro PDF417 generation with full code.
  headline: Create PDF417 barcode in C# using Aspose.BarCode – step‑by‑step guide
  type: TechArticle
tags:
- barcode
- pdf417
- csharp
- aspose
title: Créer un code‑barres PDF417 en C# avec Aspose.BarCode – guide étape par étape
url: /fr/net/compact-pdf417-encoding/create-pdf417-barcode-in-c-using-aspose-barcode-step-by-step/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Créer un code‑barres PDF417 en C# avec Aspose.BarCode – guide étape par étape

Si vous devez **créer un code‑barres PDF417** dans une application .NET, ce tutoriel vous guide à travers le processus complet. Vous verrez comment générer un code‑barres de base, activer le mode compact, ajouter des métadonnées macro, et produire une variante micro — le tout avec des explications claires et du code exécutable.

La génération de codes‑barres PDF417 est courante dans la logistique, la billetterie et la gestion de documents. À la fin de ce guide, vous serez capable d’intégrer la création de codes‑barres dans n’importe quel projet C# sans outils externes.

## Prérequis

Avant de commencer, assurez‑vous d’avoir :

* .NET 6.0 ou ultérieur (le code fonctionne également avec .NET Framework 4.7+)
* Visual Studio 2022 ou tout IDE C#
* **Aspose.BarCode for .NET** package NuGet  
  ```bash
  dotnet add package Aspose.BarCode
  ```
* Permission d’écriture sur un dossier où les fichiers PNG générés seront enregistrés

Aucune configuration supplémentaire n’est requise ; la bibliothèque gère tous les détails d’encodage bas‑niveau.

## Étape 1 : Créer un code‑barres PDF417 de base

La première étape crée un code‑barres PDF417 standard avec une taille personnalisée et un nombre de colonnes défini.

```csharp
using Aspose.BarCode.Generation;

// Initialize the generator for a standard PDF417 barcode
BarcodeGenerator basicGen = new BarcodeGenerator(EncodeTypes.Pdf417, "Åspóse.Barcóde©");

// Adjust the X‑dimension (module width) to 2 pixels for higher resolution
basicGen.Parameters.Barcode.XDimension.Pixels = 2;

// Set the number of columns – three columns keep the barcode compact yet readable
basicGen.Parameters.Barcode.Pdf417.Columns = 3;

// Save the barcode as a PNG image
basicGen.Save(@"YOUR_DIRECTORY\Pdf417Basic.png", BarCodeImageFormat.Png);
```

**Pourquoi ces paramètres sont importants**

* `XDimension.Pixels` contrôle la taille physique de chaque élément du code‑barres. Une valeur de 2 produit une image nette sur la plupart des écrans et imprimantes.
* `Pdf417.Columns` détermine le nombre de colonnes de données contenues dans le code‑barres. Moins de colonnes réduisent la largeur ; plus de colonnes augmentent la capacité de données.

L’exécution du code crée `Pdf417Basic.png`, qui ressemble à un symbole PDF417 typique avec trois colonnes de données et une colonne de métadonnées complète sur le côté droit.

## Étape 2 : Activer le mode compact (truncaté)

Le mode compact supprime la colonne de métadonnées à droite, rendant le code‑barres plus étroit. Cela est utile lorsque l’espace est limité mais que les données peuvent être reconstruites à partir des lignes restantes.

```csharp
// Turn on truncated mode to omit the metadata column
basicGen.Parameters.Barcode.Pdf417.Truncate = true;

// Save the compact version
basicGen.Save(@"YOUR_DIRECTORY\CompactPdf417.png", BarCodeImageFormat.Png);
```

**Pourquoi tronquer ?**  
Lorsque `Truncate` est `true`, le générateur omet la colonne optionnelle de droite qui stocke la correction d’erreurs et les métadonnées au niveau du fichier. Le code‑barres résultant occupe moins de colonnes tout en restant lisible par la plupart des lecteurs PDF417.

## Étape 3 : Créer un code‑barres Macro PDF417 avec des métadonnées au niveau du fichier

Macro PDF417 étend le format standard avec des identifiants de segment, permettant à un gros document d’être découpé en plusieurs codes‑barres. Ceci est pratique pour encoder de longues chaînes ou des fichiers multi‑pages.

```csharp
// Initialize a generator for Macro PDF417
BarcodeGenerator macroGen = new BarcodeGenerator(EncodeTypes.MacroPdf417, "sample text");

// Set column count for better readability
macroGen.Parameters.Barcode.Pdf417.Columns = 5;

// Assign macro-specific identifiers
macroGen.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;   // Unique file identifier
macroGen.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 1;      // Current segment number
macroGen.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 10; // Total segments

// Save the macro barcode
macroGen.Save(@"YOUR_DIRECTORY\MacroPdf417.png", BarCodeImageFormat.Png);
```

**Explication des champs macro**

| Propriété | Objectif |
|-----------|----------|
| `MacroPdf417FileID` | Identifiant unique pour l’ensemble du fichier ; tous les segments partagent cette valeur. |
| `MacroPdf417SegmentID` | Index du segment actuel (commence à 1). |
| `MacroPdf417SegmentsCount` | Nombre total de segments qui composent l’ensemble complet de données. |

Un scanner qui comprend Macro PDF417 peut reconstituer les données originales en lisant tous les segments et en utilisant ces identifiants.

## Étape 4 : Créer un code‑barres Micro PDF417 pour des données courtes

Micro PDF417 est une version compacte conçue pour de petites charges utiles (jusqu’à 90 caractères). Elle limite la plage de colonnes à 1‑4, rendant le code‑barres adapté aux petites étiquettes ou aux appareils avec une zone d’affichage limitée.

```csharp
// Initialize a generator for Micro PDF417
BarcodeGenerator microGen = new BarcodeGenerator(EncodeTypes.MicroPdf417, "small data");

// Set a fine X‑dimension for crisp rendering
microGen.Parameters.Barcode.XDimension.Pixels = 2;

// Choose a column count within the allowed range (1‑4)
microGen.Parameters.Barcode.Pdf417.Columns = 4;

// Save the micro barcode
microGen.Save(@"YOUR_DIRECTORY\MicroPdf417.png", BarCodeImageFormat.Png);
```

**Quand utiliser Micro PDF417**  
Utilisez cette variante lorsque la charge de données est courte et que vous avez besoin du plus petit code‑barres possible. Elle est idéale pour les étiquettes d’inventaire, les cartes d’accès, ou tout scénario où l’espace d’affichage est précieux.

## Exemple complet fonctionnel

Ci‑dessous se trouve une application console autonome qui génère les quatre types de code‑barres en une seule exécution. Copiez le code dans un nouveau projet C#, remplacez `YOUR_DIRECTORY` par un chemin de dossier existant, puis exécutez‑le.

```csharp
using System;
using Aspose.BarCode.Generation;

namespace Pdf417Demo
{
    class Program
    {
        static void Main()
        {
            // Adjust this path to a writable folder on your machine
            string outputPath = @"C:\Barcodes";

            // ---------- Basic PDF417 ----------
            var basicGen = new BarcodeGenerator(EncodeTypes.Pdf417, "Åspóse.Barcóde©");
            basicGen.Parameters.Barcode.XDimension.Pixels = 2;
            basicGen.Parameters.Barcode.Pdf417.Columns = 3;
            basicGen.Save($"{outputPath}\\Pdf417Basic.png", BarCodeImageFormat.Png);

            // ---------- Compact PDF417 ----------
            basicGen.Parameters.Barcode.Pdf417.Truncate = true;
            basicGen.Save($"{outputPath}\\CompactPdf417.png", BarCodeImageFormat.Png);

            // ---------- Macro PDF417 ----------
            var macroGen = new BarcodeGenerator(EncodeTypes.MacroPdf417, "sample text");
            macroGen.Parameters.Barcode.Pdf417.Columns = 5;
            macroGen.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
            macroGen.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 1;
            macroGen.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 10;
            macroGen.Save($"{outputPath}\\MacroPdf417.png", BarCodeImageFormat.Png);

            // ---------- Micro PDF417 ----------
            var microGen = new BarcodeGenerator(EncodeTypes.MicroPdf417, "small data");
            microGen.Parameters.Barcode.XDimension.Pixels = 2;
            microGen.Parameters.Barcode.Pdf417.Columns = 4; // valid range: 1‑4
            microGen.Save($"{outputPath}\\MicroPdf417.png", BarCodeImageFormat.Png);

            Console.WriteLine("All PDF417 barcodes have been generated successfully.");
        }
    }
}
```

**Sortie attendue**

L’exécution du programme crée quatre fichiers PNG dans le dossier spécifié :

* `Pdf417Basic.png` – code‑barres standard avec trois colonnes
* `CompactPdf417.png` – mêmes données, colonne de droite tronquée
* `MacroPdf417.png` – code‑barres macro contenant les métadonnées de segment
* `MicroPdf417.png` – code‑barres micro compact pour des chaînes courtes

Ouvrez n’importe quelle image avec un visualiseur ; vous verrez les motifs PDF417 distincts. Les scanner avec un lecteur de code‑barres mobile (par ex., ZXing, Scandit) renvoie les chaînes de texte originales.

## Questions fréquentes et astuces

* **Et si le code‑barres apparaît flou ?**  
  Augmentez `XDimension.Pixels` à 3 ou 4. Des tailles de module plus grandes produisent des images à plus haute résolution, au prix d’un fichier plus volumineux.

* **Puis‑je générer du SVG au lieu du PNG ?**  
  Oui. Remplacez `BarCodeImageFormat.Png` par `BarCodeImageFormat.Svg` dans les appels `Save`.

* **Dois‑je définir manuellement le niveau de correction d’erreurs ?**  
  Aspose.BarCode choisit automatiquement un niveau optimal. Pour des cas d’utilisation spécialisés, vous pouvez ajuster `Pdf417.ErrorCorrectionLevel`.

* **Comment intégrer le code‑barres dans un document PDF ?**  
  Utilisez `Aspose.Pdf` pour ajouter le PNG ou le SVG généré comme élément d’image sur une page PDF.

* **La bibliothèque est‑elle thread‑safe ?**  
  Chaque instance de `BarcodeGenerator` est indépendante ; vous pouvez créer des générateurs sur plusieurs threads sans état partagé.

## Conclusion

Vous savez maintenant comment **créer un code‑barres PDF417** en C# avec Aspose.BarCode, en couvrant les variantes de base, compact, macro et micro.

## Que devriez‑vous apprendre ensuite ?

Les tutoriels suivants couvrent des sujets étroitement liés qui s’appuient sur les techniques démontrées dans ce guide. Chaque ressource comprend des exemples de code complets avec des explications étape par étape pour vous aider à maîtriser des fonctionnalités supplémentaires de l’API et explorer des approches d’implémentation alternatives dans vos propres projets.

- [Comment créer un code‑barres pdf417 en C# – guide étape par étape](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-in-c-step-by-step-guide/)
- [Comment créer un code‑barres PDF417 en C# avec le mode compact](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-in-c-with-compact-mode/)
- [Comment créer un code‑barres macro PDF417 en C# avec Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/how-to-create-macro-pdf417-barcode-in-c-using-aspose-barcode/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}