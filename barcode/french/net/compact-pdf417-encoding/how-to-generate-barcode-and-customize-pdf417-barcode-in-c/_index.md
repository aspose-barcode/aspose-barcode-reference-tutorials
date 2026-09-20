---
category: general
date: 2026-09-19
description: Comment générer un code‑barres en C# avec un guide étape par étape. Apprenez
  à personnaliser les paramètres du code‑barres PDF417 et à créer une image de code‑barres
  que les développeurs C# peuvent utiliser immédiatement.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to generate barcode
- customize pdf417 barcode
- create barcode image c#
language: fr
lastmod: 2026-09-19
og_description: Comment générer un code‑barres en C# avec des instructions détaillées.
  Personnalisez les paramètres du code‑barres PDF417 et créez une image de code‑barres
  que les projets C# peuvent utiliser dès aujourd’hui.
og_image_alt: Screenshot of a generated MicroPDF417 barcode image created with C#
  code
og_title: Comment générer un code-barres et personnaliser le code-barres PDF417 en
  C#
schemas:
- author: Aspose
  dateModified: '2026-09-19'
  description: How to generate barcode in C# with a step‑by‑step guide. Learn to customize
    PDF417 barcode settings and create a barcode image C# developers can use instantly.
  headline: How to generate barcode and customize PDF417 barcode in C#
  type: TechArticle
- description: How to generate barcode in C# with a step‑by‑step guide. Learn to customize
    PDF417 barcode settings and create a barcode image C# developers can use instantly.
  name: How to generate barcode and customize PDF417 barcode in C#
  steps:
  - name: Check that the X‑dimension is not set below 1 pixel (some scanners cannot
      resolve sub‑pixel modules).
    text: Check that the X‑dimension is not set below 1 pixel (some scanners cannot
      resolve sub‑pixel modules).
  - name: Ensure the output file is not corrupted—re‑run the program and compare file
      sizes.
    text: Ensure the output file is not corrupted—re‑run the program and compare file
      sizes.
  - name: Increase `ErrorLevel` to improve tolerance.
    text: Increase `ErrorLevel` to improve tolerance.
  type: HowTo
tags:
- barcode
- C#
- pdf417
title: Comment générer un code‑barres et personnaliser le code‑barres PDF417 en C#
url: /fr/net/compact-pdf417-encoding/how-to-generate-barcode-and-customize-pdf417-barcode-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Comment générer un code-barres et personnaliser le code-barres PDF417 en C#

Si vous avez besoin de **how to generate barcode** dans une application .NET, ce tutoriel vous montre une solution complète, prête à l’emploi. Vous apprendrez comment personnaliser les dimensions du code-barres PDF417, choisir le nombre de colonnes, et enfin **create barcode image C#** que les projets peuvent intégrer directement.

Générer un code-barres ne nécessite pas de pipeline de construction complexe. À la fin de ce guide, vous disposerez d’un fichier PNG contenant un code-barres MicroPDF417 qui correspond exactement à la taille et à la résolution dont vous avez besoin.

## Prérequis

Vous devez avoir installé les éléments suivants avant de commencer :

* .NET 6.0 SDK ou ultérieur (le code fonctionne également avec .NET Framework 4.6+)
* Visual Studio 2022 (ou tout éditeur C# de votre choix)
* Package NuGet Aspose.BarCode pour .NET – installer avec  
  `dotnet add package Aspose.BarCode`

Aucun outil externe supplémentaire n’est requis.

## Étape 1 : Configurer le projet et importer les espaces de noms

Créez un nouveau projet console et ajoutez la référence Aspose.BarCode.

```bash
dotnet new console -n BarcodeDemo
cd BarcodeDemo
dotnet add package Aspose.BarCode
```

Ouvrez `Program.cs` et ajoutez les directives `using` requises :

```csharp
using System;
using Aspose.BarCode.Generation;   // Provides BarcodeGenerator and EncodeTypes
using Aspose.BarCode;               // Contains BarCodeImageFormat enum
```

Ces espaces de noms exposent les classes qui vous permettent de **how to generate barcode** et de contrôler les options spécifiques à PDF417.

## Étape 2 : Initialiser le générateur MicroPDF417 avec le texte souhaité

La première ligne crée une instance `BarcodeGenerator` configurée pour la symbologie MicroPDF417. Le constructeur prend le type d’encodage et la chaîne de données que vous souhaitez encoder.

```csharp
// Step 2: Create a MicroPDF417 barcode generator with the desired text
BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.MicroPdf417, "Sample");
```

**Pourquoi c’est important :** MicroPDF417 est une variante compacte du standard PDF417 complet, idéale pour les petites étiquettes ou les écrans mobiles. Initialiser le générateur avec le bon `EncodeTypes` garantit que la bibliothèque utilise le bon algorithme d’encodage.

## Étape 3 : Personnaliser la X‑dimension (largeur du module) pour une résolution plus fine

La X‑dimension contrôle la largeur d’un seul module du code-barres (la plus petite barre noire ou blanche). La définir à une faible valeur en pixels produit une image à plus haute résolution.

```csharp
// Step 3: Set the X‑dimension (module width) in pixels for finer resolution
generator.Parameters.Barcode.XDimension.Pixels = 2;
```

**Pourquoi c’est important :** Une X‑dimension plus grande rend le code-barres plus facile à lire pour les scanners à basse résolution, tandis qu’une valeur plus petite permet de placer plus de données dans un espace limité. Ajustez cette valeur en fonction de l’environnement de numérisation.

## Étape 4 : Définir le nombre de colonnes pour contrôler la taille du code-barres

MicroPDF417 autorise 1 à 4 colonnes. Plus de colonnes produisent un code-barres plus court et plus large ; moins de colonnes créent un code-barres plus haut et plus étroit.

```csharp
// Step 4: Define the number of columns (1‑4 are allowed) to control barcode size
generator.Parameters.Barcode.Pdf417.Columns = 4;
```

**Pourquoi c’est important :** Choisir le bon nombre de colonnes vous permet d’adapter le code-barres à un élément d’interface utilisateur ou à une étiquette imprimée spécifique sans mise à l’échelle manuelle.

## Étape 5 : Enregistrer le code-barres en tant qu’image PNG

Enfin, écrivez le code-barres généré sur le disque. PNG conserve une qualité sans perte, ce qui est important pour une numérisation nette.

```csharp
// Step 5: Save the generated barcode as a PNG image
string outputPath = @"C:\Barcodes\MicroPdf417.png";
generator.Save(outputPath, BarCodeImageFormat.Png);
Console.WriteLine($"Barcode saved to {outputPath}");
```

Si le répertoire cible n’existe pas, la méthode `Save` lève une `ArgumentException`. Vous pouvez vous en prémunir avec une vérification simple :

```csharp
if (!System.IO.Directory.Exists(@"C:\Barcodes"))
{
    System.IO.Directory.CreateDirectory(@"C:\Barcodes");
}
```

### Code source complet

En assemblant les éléments, voici le programme complet et exécutable :

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
            // 1️⃣ Create a MicroPDF417 barcode generator with the desired text
            BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.MicroPdf417, "Sample");

            // 2️⃣ Set the X‑dimension (module width) in pixels for finer resolution
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // 3️⃣ Define the number of columns (1‑4 are allowed) to control barcode size
            generator.Parameters.Barcode.Pdf417.Columns = 4;

            // Ensure the output folder exists
            string folder = @"C:\Barcodes";
            if (!System.IO.Directory.Exists(folder))
                System.IO.Directory.CreateDirectory(folder);

            // 4️⃣ Save the generated barcode as a PNG image
            string outputPath = System.IO.Path.Combine(folder, "MicroPdf417.png");
            generator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"Barcode saved to {outputPath}");
        }
    }
}
```

L’exécution de ce programme produit un fichier nommé **MicroPdf417.png** qui ressemble à la capture d’écran ci‑dessous (image omise pour plus de concision). Le code-barres encode le texte *Sample* et respecte les paramètres de X‑dimension et de colonnes que vous avez définis.

## Personnalisation d’autres options PDF417

Bien que ce guide se concentre sur les paramètres **customize pdf417 barcode** qui affectent la taille, Aspose.BarCode propose de nombreux paramètres supplémentaires dont vous pourriez avoir besoin :

| Property | Objectif | Valeurs typiques |
|----------|----------|------------------|
| `generator.Parameters.Barcode.Pdf417.Rows` | Contrôle le nombre de lignes (hauteur) | 3‑30 |
| `generator.Parameters.Barcode.Pdf417.ErrorLevel` | Définit le niveau de correction d’erreurs (plus élevé = plus tolérant) | 0‑8 |
| `generator.Parameters.Barcode.Pdf417.Truncated` | Génère un code-barres tronqué (pas de motif d’arrêt) | `true`/`false` |
| `generator.Parameters.Barcode.Pdf417.CompactionMode` | Choisit la compaction numérique, texte ou octet | `CompactionModes.Numeric`, etc. |

**Astuce :** Lorsque vous avez besoin d’un code-barres qui s’adapte à une largeur fixe, commencez par augmenter `Columns` et diminuer `XDimension`. Si le scanner signale des symboles manquants, augmentez le `ErrorLevel` pour améliorer la redondance.

## Gestion des cas limites

* **Texte trop long pour MicroPDF417 :** La variante Micro prend en charge jusqu’à 1 KB de données. Si votre chaîne dépasse cette limite, passez à la symbologie complète `Pdf417` en changeant `EncodeTypes.MicroPdf417` en `EncodeTypes.Pdf417`.
* **Format d’image non pris en charge :** `BarCodeImageFormat` prend également en charge `Jpeg`, `Bmp` et `Gif`. Choisissez un format qui correspond à votre chaîne de traitement en aval.
* **Chemins multiplateformes :** Utilisez `Path.Combine` au lieu de barres obliques inverses codées en dur lorsque vous ciblez Linux ou macOS.

## Vérification du code-barres

Vous pouvez vérifier l’image générée avec n’importe quelle application de lecture de code-barres standard (mobile ou de bureau). Le scanner doit renvoyer le texte original **Sample**. En cas d’échec :

1. Vérifiez que la X‑dimension n’est pas réglée en dessous de 1 pixel (certains scanners ne peuvent pas résoudre les modules sous‑pixel).
2. Assurez‑vous que le fichier de sortie n’est pas corrompu — relancez le programme et comparez les tailles de fichier.
3. Augmentez le `ErrorLevel` pour améliorer la tolérance.

## Conclusion

Vous savez maintenant **how to generate barcode** en C# avec Aspose.BarCode, comment **customize pdf417 barcode** les dimensions et le nombre de colonnes, et comment **create barcode image C#** que les projets peuvent intégrer directement. L’exemple complet démontre un flux de travail pratique, de la configuration du projet à la sortie PNG finale.

Ensuite, explorez d’autres symbologies telles que QR, Code128 ou DataMatrix en changeant la valeur de l’énumération `EncodeTypes`. Ajuster des paramètres supplémentaires comme `Resolution` ou `Margin` vous permet d’affiner chaque code-barres pour votre application spécifique.

Bon codage, et laissez vos codes-barres dynamiser votre prochain projet d’automatisation !

## Que devriez‑vous apprendre ensuite ?

Les tutoriels suivants couvrent des sujets étroitement liés qui s’appuient sur les techniques démontrées dans ce guide. Chaque ressource comprend des exemples de code complets et fonctionnels avec des explications étape par étape pour vous aider à maîtriser des fonctionnalités API supplémentaires et explorer des approches d’implémentation alternatives dans vos propres projets.

- [Comment générer une image de code-barres PDF417 en C# avec Aspose](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-image-in-c-with-aspose/)
- [Comment créer un code-barres PDF417 avec Aspose – Guide complet étape par étape](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-with-aspose-complete-step-by-st/)
- [Comment enregistrer un code-barres en C# – Générer des codes-barres PDF417](/barcode/english/net/compact-pdf417-encoding/how-to-save-barcode-in-c-generate-pdf417-barcodes/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}