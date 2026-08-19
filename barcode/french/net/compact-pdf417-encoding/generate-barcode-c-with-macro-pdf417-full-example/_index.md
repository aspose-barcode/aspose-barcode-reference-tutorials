---
category: general
date: 2026-08-19
description: Générer un code‑barres C# avec Aspose.BarCode pour créer un Macro PDF417
  avec du texte personnalisé et l’enregistrer sous forme de fichier image.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate barcode C#
- how to generate pdf417
- create barcode custom text
- generate barcode image file
language: fr
lastmod: 2026-08-19
og_description: Générez un code-barres C# avec Aspose.BarCode, apprenez à créer du
  PDF417, ajoutez du texte personnalisé et enregistrez le fichier image du code-barres.
og_image_alt: Screenshot of a Macro PDF417 barcode generated with C#
og_title: Générer un code-barres C# – Guide Macro PDF417
schemas:
- author: Aspose
  dateModified: '2026-08-19'
  description: Generate barcode C# using Aspose.BarCode to create a Macro PDF417 with
    custom text and save as an image file.
  headline: Generate barcode C# with Macro PDF417 – full example
  type: TechArticle
- questions:
  - answer: Yes. Replace `BarCodeImageFormat.Png` with `Jpeg`, `Bmp`, or `Gif` as
      needed.
    question: Can I generate a different image format?
  - answer: Macro PDF417 is designed for segmentation. Adjust `MacroPdf417SegmentsCount`
      and `MacroPdf417SegmentID` for each part, then concatenate the scanned results.
    question: What if my data exceeds a single barcode?
  - answer: Aspose.BarCode fully supports Unicode. Ensure your source file is saved
      with UTF‑8 encoding to avoid character corruption.
    question: Is Unicode support guaranteed?
  - answer: A licensed version removes the evaluation watermark and provides full
      functionality. The trial works for testing and learning.
    question: Do I need a license for production?
  type: FAQPage
tags:
- barcode
- C#
- Aspose
title: Générer un code-barres C# avec Macro PDF417 – exemple complet
url: /fr/net/compact-pdf417-encoding/generate-barcode-c-with-macro-pdf417-full-example/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Générer un code-barres C# avec Macro PDF417 – exemple complet

Si vous devez **générer un code-barres C#** au format Macro PDF417, ce guide vous présente une solution prête à l’emploi. Vous verrez comment **générer pdf417**, intégrer du texte personnalisé et **générer un fichier d’image de code-barres** dans un programme autonome.

Le tutoriel couvre tout, de l’installation de la bibliothèque Aspose.BarCode à la configuration des métadonnées Macro PDF417, afin que vous puissiez copier le code directement dans votre projet et voir le résultat immédiatement.

## Prérequis

- .NET 6.0 SDK ou version ultérieure (le code fonctionne également avec .NET Framework 4.7+)
- Visual Studio 2022 (ou tout IDE supportant C#)
- Une licence Aspose.BarCode pour .NET (l’essai gratuit fonctionne pour l’évaluation)
- Familiarité de base avec la syntaxe C#

> **Conseil pro :** Installez le package NuGet via la CLI pour éviter les incompatibilités de version :  
> `dotnet add package Aspose.BarCode`

## Étape 1 : Configurer le projet et importer la bibliothèque

Créez une nouvelle application console et ajoutez les directives `using` requises.

```csharp
using Aspose.BarCode.Generation;
using System;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // The full barcode generation logic starts in the next step.
        }
    }
}
```

**Pourquoi cette étape est importante :**  
L’espace de noms `Aspose.BarCode.Generation` fournit la classe `BarcodeGenerator`, qui est le point d’entrée pour créer tout type de code-barres, y compris Macro PDF417. L’importation de `System` vous donne accès à `DateTime` pour les métadonnées de timestamp.

## Étape 2 : Créer un générateur Macro PDF417 avec texte personnalisé

Remplacez le commentaire d’espace réservé par l’initialisation du générateur. Cela montre comment **créer du texte personnalisé pour le code-barres** tout en sélectionnant le type d’encodage correct.

```csharp
// Step 2: Initialize a barcode generator for Macro PDF417 with custom text.
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.MacroPdf417,          // Choose Macro PDF417 as the symbology
    "Åspóse.Barcóde©");               // Custom text can contain Unicode characters
```

**Explication :**  
- `EncodeTypes.MacroPdf417` indique à Aspose de produire un code-barres PDF417 qui prend en charge les fonctionnalités macro (segmentation de fichier, somme de contrôle, etc.).  
- Le texte `"Åspóse.Barcóde©"` montre que les caractères Unicode sont entièrement pris en charge, ce qui est souvent requis pour les applications internationales.

## Étape 3 : Configurer l’apparence et les métadonnées Macro PDF417

Ajustez finement les dimensions du code-barres et définissez les champs spécifiques à la macro requis pour la gestion de fichiers segmentés.

```csharp
// Appearance: set the narrow bar width to 2 pixels.
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;

// PDF417 specific settings
barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 5;                     // Number of columns per row
barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;    // Unique file identifier
barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;       // Current segment number
barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;  // Total number of segments
barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01"; // Logical file name
barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234;     // CCITT‑16 CRC checksum
barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400_000;   // Approximate file size in bytes
barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = new DateTime(2019, 11, 1);
barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;
```

**Pourquoi ces paramètres sont importants :**

| Paramètre | Objectif |
|-----------|----------|
| `XDimension.Pixels` | Contrôle la densité visuelle ; 2 px donnent une image claire et lisible. |
| `Columns` | Détermine le nombre de colonnes de données par ligne, affectant la taille du code-barres. |
| `MacroPdf417FileID` | Identifie de façon unique le fichier logique à travers tous les segments. |
| `MacroPdf417SegmentID` / `SegmentsCount` | Permet la reconstruction du fichier original à partir de plusieurs codes-barres. |
| `MacroPdf417FileName` | Nom lisible par l’homme stocké dans le code-barres pour le traitement en aval. |
| `MacroPdf417Checksum` | Fournit la détection d’erreurs en utilisant l’algorithme CRC CCITT‑16. |
| `MacroPdf417FileSize` | Aide le décodeur à savoir quand le fichier complet a été reçu. |
| `MacroPdf417TimeStamp` | Enregistre le moment où le code-barres a été généré, utile pour les pistes d’audit. |
| `MacroPdf417Addressee` / `MacroPdf417Sender` | Champs optionnels pouvant être utilisés dans les flux de travail métier. |
| `MacroPdf417Terminator` | Indique que ce segment est le dernier (`Set`). |

## Étape 4 : Enregistrer le code-barres sous forme de fichier image

Enfin, écrivez le code-barres dans un fichier PNG afin de pouvoir le visualiser ou l’intégrer ailleurs.

```csharp
// Step 4: Save the generated barcode image to a file.
string outputPath = @"C:\Barcodes\ExtPDF417Meta.png";   // Adjust the folder as needed
barcodeGenerator.Save(outputPath, BarCodeImageFormat.Png);

Console.WriteLine($"Barcode saved to {outputPath}");
```

**Ce que vous verrez :**  
Une image PNG nommée `ExtPDF417Meta.png` contenant un code-barres Macro PDF417 qui encode le texte personnalisé et tous les champs de métadonnées que vous avez définis ci‑dessus. L’image peut être ouverte avec n’importe quel visualiseur standard ou insérée dans des PDF, rapports ou pages web.

## Code source complet (prêt à copier‑coller)

```csharp
using Aspose.BarCode.Generation;
using System;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // Initialize generator with custom Unicode text.
            BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
                EncodeTypes.MacroPdf417,
                "Åspóse.Barcóde©");

            // Appearance settings.
            barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
            barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 5;

            // Macro PDF417 metadata.
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234;
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400_000;
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = new DateTime(2019, 11, 1);
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;

            // Save the barcode image.
            string outputPath = @"C:\Barcodes\ExtPDF417Meta.png";
            barcodeGenerator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"Barcode saved to {outputPath}");
        }
    }
}
```

### Résultat attendu

L’exécution du programme affiche :

```
Barcode saved to C:\Barcodes\ExtPDF417Meta.png
```

Ouvrir `ExtPDF417Meta.png` montre un code-barres Macro PDF417 propre qui se lit correctement avec n’importe quel lecteur PDF417, en conservant le texte personnalisé `"Åspóse.Barcóde©"` et les métadonnées macro que vous avez définies.

## Questions fréquentes et cas particuliers

- **Puis-je générer un format d’image différent ?**  
  Oui. Remplacez `BarCodeImageFormat.Png` par `Jpeg`, `Bmp` ou `Gif` selon vos besoins.

- **Que faire si mes données dépassent un seul code-barres ?**  
  Macro PDF417 est conçu pour la segmentation. Ajustez `MacroPdf417SegmentsCount` et `MacroPdf417SegmentID` pour chaque partie, puis concaténez les résultats scannés.

- **Le support Unicode est‑il garanti ?**  
  Aspose.BarCode prend pleinement en charge Unicode. Assurez‑vous que votre fichier source est enregistré avec l’encodage UTF‑8 pour éviter la corruption des caractères.

- **Ai‑je besoin d’une licence pour la production ?**  
  Une version sous licence supprime le filigrane d’évaluation et offre toutes les fonctionnalités. L’essai fonctionne pour les tests et l’apprentissage.

## Conclusion

Vous savez maintenant comment **générer un code-barres C#** pour un Macro PDF417, **générer pdf417** avec des métadonnées riches, **créer du texte personnalisé pour le code-barres**, et **générer un fichier d’image de code-barres** en utilisant Aspose.BarCode. L’exemple complet et exécutable montre chaque étape requise — de la configuration du projet à l’enregistrement de l’image PNG finale.

### Prochaines étapes

- Expérimentez d’autres paramètres PDF417 tels que `ErrorCorrectionLevel` et `CompactPdf417` pour des symboles plus petits.  
- Intégrez le code-barres généré dans un rapport PDF à l’aide d’Aspose.PDF.  
- Explorez la génération en lot : parcourez une collection de fichiers et produisez une série de codes-barres Macro PDF417 segmentés.

N’hésitez pas à adapter le code à votre propre flux de travail, et laissez la génération de codes-barres devenir une partie fluide de vos applications C#. Bon codage !

## Que devriez‑vous apprendre ensuite ?

Les tutoriels suivants couvrent des sujets étroitement liés qui s’appuient sur les techniques démontrées dans ce guide. Chaque ressource comprend des exemples de code complets et fonctionnels avec des explications étape par étape pour vous aider à maîtriser des fonctionnalités API supplémentaires et explorer des approches d’implémentation alternatives dans vos propres projets.

- [Comment générer un code-barres Aztec avec un ratio d’aspect personnalisé en utilisant Aspose.BarCode pour .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)
- [Générer une image de code-barres – Code 93 avec Aspose.BarCode](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-code-93-configuration/)
- [Comment générer et ajuster la hauteur du code-barres pour One-Dimensional Databar en utilisant Aspose.BarCode pour .NET](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-barcode-height-adjustment/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}