---
category: general
date: 2026-09-16
description: Apprenez à générer un code‑barres et à définir la taille du code‑barres
  en C#. Guide étape par étape utilisant Aspose.BarCode pour créer une image Micro
  PDF417.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to generate barcode
- set barcode size
language: fr
lastmod: 2026-09-16
og_description: Comment générer un code-barres en C# et définir la taille du code-barres
  avec Aspose.BarCode. Suivez ce tutoriel concis pour créer un PNG Micro PDF417.
og_image_alt: Example output showing how to generate barcode using C#
og_title: Comment générer un code‑barres en C# – guide complet d’Aspose.BarCode
schemas:
- author: Aspose
  dateModified: '2026-09-16'
  description: Learn how to generate barcode and set barcode size in C#. Step‑by‑step
    guide using Aspose.BarCode to create a Micro PDF417 image.
  headline: How to generate barcode in C# with Aspose.BarCode
  type: TechArticle
tags:
- barcode generation
- C#
- Aspose.BarCode
title: Comment générer un code‑barres en C# avec Aspose.BarCode
url: /fr/net/compact-pdf417-encoding/how-to-generate-barcode-in-c-with-aspose-barcode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Comment générer un code‑barres en C# avec Aspose.BarCode

Si vous avez besoin de savoir **comment générer un code‑barres** dans un projet .NET, ce tutoriel vous guide à travers l’ensemble du processus en utilisant la bibliothèque Aspose.BarCode. Vous apprendrez également comment **définir la taille du code‑barres** afin que l’image s’adapte à votre interface utilisateur ou à vos exigences d’impression.

Le guide couvre tout, de l’installation du package NuGet à la configuration d’un symbole Micro PDF417 et à son enregistrement au format PNG. À la fin, vous disposerez d’un exemple de code exécutable que vous pourrez intégrer à n’importe quelle application console ou web C#.

## Ce dont vous avez besoin

- .NET 6.0 ou version ultérieure (le code fonctionne également avec .NET Framework 4.6+)
- Visual Studio 2022 ou tout IDE supportant le C#
- Accès à Internet pour télécharger le package NuGet **Aspose.BarCode**  
  ```bash
  dotnet add package Aspose.BarCode
  ```
- Familiarité de base avec la syntaxe C#

## Comment générer un code‑barres avec Aspose.BarCode

La première étape consiste à créer une instance `BarcodeGenerator` qui sait quelle symbologie utiliser et quelles données encoder.

```csharp
using Aspose.BarCode.Generation;

// Step 1: Create a Micro PDF417 barcode generator with the data to encode
var barcodeGenerator = new BarcodeGenerator(EncodeTypes.MicroPdf417, "Micro data");
```

**Pourquoi c’est important :** `EncodeTypes.MicroPdf417` indique à la bibliothèque de produire une variante compacte du PDF417, idéale pour les petites étiquettes ou les empreintes similaires à un QR‑code. La chaîne `"Micro data"` devient la charge utile lisible par l’homme intégrée dans le code‑barres.

## Définir la taille et les dimensions du code‑barres

Un code‑barres lisible doit posséder la bonne dimension de module (X) et suffisamment de colonnes pour contenir les données. C’est ici que vous **définissez la taille du code‑barres**.

```csharp
// Step 2: Define the module size (X dimension) in pixels
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;

// Step 3: Set the maximum number of columns for the Micro PDF417 symbol
barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 4;
```

- **XDimension** contrôle la largeur du plus petit trait (le « module »). Une valeur de `2` pixels fonctionne bien pour l’affichage à l’écran ; augmentez‑la pour une impression haute résolution.
- **Pdf417.Columns** limite le nombre de colonnes verticales. Le format Micro PDF417 ne supporte que jusqu’à 7 colonnes ; `4` offre une taille équilibrée sans sacrifier la capacité de données.

> **Astuce :** Si l’image générée apparaît trop petite, augmentez `XDimension.Pixels` à `3` ou `4`. Inversement, pour un espace UI dense, vous pouvez la réduire à `1`, mais assurez‑vous que le scanner que vous utiliserez puisse toujours lire le symbole.

## Enregistrer l'image du code‑barres

Après avoir configuré la taille, il suffit d’indiquer au générateur d’écrire l’image sur le disque.

```csharp
// Step 4: Save the generated barcode as a PNG image
barcodeGenerator.Save("micro.png", BarCodeImageFormat.Png);
```

La méthode `Save` accepte tout format supporté par Aspose.BarCode (`Png`, `Jpeg`, `Bmp`, `Gif`, `Tiff`). PNG est sans perte, préservant les bords nets nécessaires à un scan fiable.

**Résultat attendu :** Un fichier nommé `micro.png` apparaîtra dans le répertoire de travail du projet. L’ouvrir montre un petit code‑barres Micro PDF417 à fort contraste, prêt à être testé avec n’importe quel scanner standard.

## Exemple complet

Assembler toutes les pièces donne un programme autonome que vous pouvez exécuter immédiatement.

```csharp
using System;
using Aspose.BarCode.Generation;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // Create the generator for Micro PDF417
            var generator = new BarcodeGenerator(EncodeTypes.MicroPdf417, "Micro data");

            // Set size parameters
            generator.Parameters.Barcode.XDimension.Pixels = 2;   // module width
            generator.Parameters.Barcode.Pdf417.Columns = 4;    // column count

            // Choose output path (adjust as needed)
            string outputPath = "micro.png";

            // Save as PNG
            generator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"Barcode saved to {outputPath}");
        }
    }
}
```

Exécutez le programme (`dotnet run` depuis la console) et vous verrez le message de confirmation. Le PNG généré peut être intégré dans des rapports, imprimé sur des étiquettes produit ou affiché dans une page web.

## Questions fréquentes et cas particuliers

| Question | Réponse |
|---|---|
| **Puis‑je générer d’autres types de code‑barres ?** | Oui. Remplacez `EncodeTypes.MicroPdf417` par n’importe quelle valeur de l’énumération `EncodeTypes` (par ex., `EncodeTypes.Code128`, `EncodeTypes.QR`). |
| **Et si j’ai besoin d’une image plus grande ?** | Augmentez `XDimension.Pixels` ou utilisez `generator.Parameters.Image.Width/Height` pour forcer une taille en pixels précise. |
| **La bibliothèque supporte‑t‑elle les arrière‑plans transparents ?** | Définissez `generator.Parameters.Barcode.BackColor = System.Drawing.Color.Transparent;` avant d’appeler `Save`. |
| **Comment lire le code‑barres généré ?** | Utilisez `Aspose.BarCode.BarCodeReader` sur l’image enregistrée ; il détecte automatiquement la symbologie. |
| **Le PNG est‑il sûr pour l’impression ?** | PNG est sans perte, mais pour l’impression CMYK envisagez de sauvegarder en TIFF (`BarCodeImageFormat.Tiff`). |

## Conclusion

Vous savez maintenant **comment générer un code‑barres** en C# et comment **définir la taille du code‑barres** à l’aide d’Aspose.BarCode. L’exemple complet montre la création d’un symbole Micro PDF417, l’ajustement de ses dimensions et l’exportation d’un fichier PNG. Avec cette base, vous pouvez explorer d’autres symbologies, personnaliser les couleurs ou intégrer la génération de code‑barres dans des services ASP.NET Core.

### Étapes suivantes

- Essayez de générer un QR‑code (`EncodeTypes.QR`) et comparez les tailles de module.  
- Expérimentez avec `generator.Parameters.Image` pour ajouter des marges ou modifier le DPI afin d’obtenir une sortie prête à l’impression.  
- Combinez la génération de code‑barres avec **Aspose.PDF** pour intégrer directement l’image dans un rapport PDF.

Bon codage, et profitez de la flexibilité qu’Aspose.BarCode apporte à vos projets de code‑barres .NET !

## Que devriez‑vous apprendre ensuite ?


Les tutoriels suivants couvrent des sujets étroitement liés qui s’appuient sur les techniques démontrées dans ce guide. Chaque ressource inclut des exemples de code complets avec des explications pas à pas pour vous aider à maîtriser des fonctionnalités API supplémentaires et à explorer des approches d’implémentation alternatives dans vos propres projets.

- [How to Generate PDF417 Barcode Image in C# with Aspose](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-image-in-c-with-aspose/)
- [How to Generate PDF417 Barcode with Aspose – Complete Guide](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-with-aspose-complete-guide/)
- [How to Generate Barcode in C# – Complete Aspose.BarCode Guide](/barcode/english/python-java/general/how-to-generate-barcode-in-c-complete-aspose-barcode-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}