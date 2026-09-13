---
category: general
date: 2026-09-13
description: Apprenez à générer des codes‑barres en C#, à personnaliser la taille
  du code‑barres et à enregistrer l’image du code‑barres au format PNG à l’aide d’Aspose.BarCode.
  Guide complet étape par étape.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to generate barcode
- custom barcode size
- save barcode image
- Aspose.BarCode C#
- barcode image format
language: fr
lastmod: 2026-09-13
og_description: Comment générer un code‑barres en C# avec une taille de code‑barres
  personnalisée et enregistrer l’image du code‑barres au format PNG. Suivez ce guide
  complet pour Aspose.BarCode.
og_image_alt: Screenshot of a DataBar stacked omnidirectional barcode generated in
  C#
og_title: Comment générer un code‑barres, définir une taille personnalisée et enregistrer
  l’image en C#
schemas:
- author: Aspose
  dateModified: '2026-09-13'
  description: Learn how to generate barcode in C#, customize barcode size, and save
    barcode image as PNG using Aspose.BarCode. Complete step‑by‑step guide.
  headline: How to generate barcode set custom size and save image in C#
  type: TechArticle
tags:
- barcode
- C#
- Aspose
title: Comment générer un code‑barres, définir une taille personnalisée et enregistrer
  l’image en C#
url: /fr/python-java/general/how-to-generate-barcode-set-custom-size-and-save-image-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Comment générer un jeu de codes-barres de taille personnalisée et enregistrer l'image en C#

Si vous avez besoin de **comment générer un code-barres** dans une application .NET, ce tutoriel vous propose une solution complète. Vous verrez comment ajuster la **taille personnalisée du code-barres** et **enregistrer l'image du code-barres** avec seulement quelques lignes de code C#.

La génération de codes-barres est une exigence courante pour les systèmes d’inventaire, les étiquettes d’expédition et les applications de point de vente. À la fin de ce guide, vous disposerez d’un programme exécutable qui crée deux codes-barres DataBar‑Stacked‑Omnidirectional, chacun avec un rapport d’aspect différent, et les écrit dans des fichiers PNG sur le disque.

**Prérequis**

- .NET 6.0 ou version ultérieure (le code fonctionne également avec .NET Framework 4.7+)
- Visual Studio 2022 ou tout IDE C#
- Aspose.BarCode for .NET (version d’essai gratuite ou package NuGet sous licence)

---

## Comment générer un code-barres avec Aspose.BarCode

La bibliothèque Aspose.BarCode abstrait les détails de bas niveau des normes de codes-barres, vous permettant de vous concentrer sur les données à encoder et l’apparence visuelle souhaitée.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Program
{
    static void Main()
    {
        // 1️⃣ Create a DataBar stacked omnidirectional barcode generator
        var generator = new BarcodeGenerator(
            EncodeTypes.DatabarStackedOmniDirectional,
            "(01)12345678901231"); // GS1‑128 format example

        // 2️⃣ Set a basic module width – this influences the overall **custom barcode size**
        generator.Parameters.Barcode.XDimension.Pixels = 2;

        // 3️⃣ First aspect ratio (15) → save the image
        generator.Parameters.Barcode.DataBar.AspectRatio = 15;
        generator.Save("DatabarAspectRatio15.png", BarCodeImageFormat.Png);
        Console.WriteLine("Saved barcode with aspect ratio 15.");

        // 4️⃣ Change aspect ratio to 30 → **save barcode image** again
        generator.Parameters.Barcode.DataBar.AspectRatio = 30;
        generator.Save("DatabarAspectRatio30.png", BarCodeImageFormat.Png);
        Console.WriteLine("Saved barcode with aspect ratio 30.");
    }
}
```

### Pourquoi chaque ligne est importante

| Étape | Explication |
|------|-------------|
| **1️⃣ Créer un générateur** | L’énumération `EncodeTypes.DatabarStackedOmniDirectional` indique à Aspose la symbologie de code-barres à utiliser. La chaîne `"(01)12345678901231"` suit le format de données GS1‑128, où `(01)` est l’identifiant d’application pour un GTIN. |
| **2️⃣ Définir la dimension X** | `XDimension.Pixels` définit la largeur d’un seul module de code-barres (la plus petite barre). Modifier cette valeur est le moyen principal d’obtenir une **taille personnalisée du code-barres** sans altérer les données encodées. |
| **3️⃣ Définir le rapport d’aspect & enregistrer** | `DataBar.AspectRatio` contrôle le rapport hauteur/largeur des symboles DataBar. Un rapport d’aspect de 15 produit un code-barres relativement court et large, tandis que 30 le rend plus haut. `Save` écrit la représentation visuelle dans un fichier PNG, répondant à l’exigence **enregistrer l'image du code-barres**. |
| **4️⃣ Modifier le rapport d’aspect & enregistrer à nouveau** | Réutiliser la même instance du générateur vous permet de produire plusieurs images avec des caractéristiques visuelles différentes tout en conservant les mêmes données. |

---

## Ajuster la taille personnalisée du code-barres au‑delà de la dimension X

Alors que `XDimension.Pixels` fixe la largeur du module, vous pouvez également affiner les dimensions globales du code-barres en combinant deux propriétés :

1. **`BarHeight`** – hauteur explicite en pixels.  
2. **`BarWidth`** – largeur explicite en pixels (remplace la dimension X).

```csharp
// Example: make a larger, more readable barcode
generator.Parameters.Barcode.XDimension.Pixels = 4;      // wider modules
generator.Parameters.Barcode.BarHeight.Pixels = 120;    // taller bars
generator.Parameters.Barcode.DataBar.AspectRatio = 20; // balanced ratio
generator.Save("LargeCustomSize.png", BarCodeImageFormat.Png);
Console.WriteLine("Saved large custom size barcode.");
```

> **Astuce :** Lors de l’impression de codes-barres, testez toujours l’image générée à la taille d’impression finale. Une largeur de module de 2 px convient pour l’affichage à l’écran, mais les étiquettes imprimées nécessitent souvent au moins 4 px pour rester lisibles.

---

## Choisir le bon format d’image pour enregistrer le code-barres

Aspose.BarCode prend en charge PNG, JPEG, BMP, GIF et TIFF. PNG est sans perte et préserve les bords nets, ce qui en fait le choix le plus sûr pour la plupart des applications. Si vous avez besoin d’un fichier plus petit pour le web, JPEG avec un paramètre de qualité de 90 fonctionne bien, mais sachez que les artefacts de compression peuvent affecter la fiabilité du scan.

```csharp
generator.Save("DatabarAspectRatio15.jpg", BarCodeImageFormat.Jpeg, 90);
Console.WriteLine("Saved JPEG version with quality 90.");
```

---

## Exemple complet et exécutable

Voici une application console autonome que vous pouvez copier, coller et exécuter. Elle montre **comment générer un code-barres**, modifier la **taille personnalisée du code-barres**, et **enregistrer l'image du code-barres** dans deux formats différents.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // Initialize the generator with the desired symbology and data
            var generator = new BarcodeGenerator(
                EncodeTypes.DatabarStackedOmniDirectional,
                "(01)12345678901231");

            // ---- Custom size configuration ----
            generator.Parameters.Barcode.XDimension.Pixels = 2;      // module width
            generator.Parameters.Barcode.BarHeight.Pixels = 80;    // optional explicit height
            generator.Parameters.Barcode.DataBar.AspectRatio = 15; // first aspect ratio

            // Save first image as PNG
            string pngPath1 = "DatabarAspectRatio15.png";
            generator.Save(pngPath1, BarCodeImageFormat.Png);
            Console.WriteLine($"Saved {pngPath1}");

            // Change aspect ratio for a taller barcode
            generator.Parameters.Barcode.DataBar.AspectRatio = 30;
            string pngPath2 = "DatabarAspectRatio30.png";
            generator.Save(pngPath2, BarCodeImageFormat.Png);
            Console.WriteLine($"Saved {pngPath2}");

            // ---- Larger custom size example ----
            generator.Parameters.Barcode.XDimension.Pixels = 4;
            generator.Parameters.Barcode.BarHeight.Pixels = 120;
            generator.Parameters.Barcode.DataBar.AspectRatio = 20;
            string largePath = "LargeCustomSize.png";
            generator.Save(largePath, BarCodeImageFormat.Png);
            Console.WriteLine($"Saved {largePath}");

            // ---- Save as JPEG for web use ----
            string jpegPath = "DatabarAspectRatio15.jpg";
            generator.Save(jpegPath, BarCodeImageFormat.Jpeg, 90);
            Console.WriteLine($"Saved {jpegPath}");
        }
    }
}
```

**Sortie attendue dans la console**

```
Saved DatabarAspectRatio15.png
Saved DatabarAspectRatio30.png
Saved LargeCustomSize.png
Saved DatabarAspectRatio15.jpg
```

Les quatre fichiers image apparaîtront dans le programme

## Que devriez‑vous apprendre ensuite ?

Les tutoriels suivants couvrent des sujets étroitement liés qui s’appuient sur les techniques démontrées dans ce guide. Chaque ressource comprend des exemples de code complets avec des explications étape par étape pour vous aider à maîtriser d’autres fonctionnalités de l’API et explorer des approches d’implémentation alternatives dans vos propres projets.

- [How to Generate DataMatrix Barcodes Using Aspose.BarCode for .NET – Step‑by‑Step Guide](/barcode/english/net/datamatrix-barcode-configuration/)
- [How to Generate PDF417 Barcode with Aspose – Complete Guide](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-with-aspose-complete-guide/)
- [How to generate Aztec barcode with custom aspect ratio using Aspose.BarCode for .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}