---
category: general
date: 2026-08-22
description: Apprenez à générer des codes-barres postaux en C# et à contrôler la hauteur
  des barres, la dimension X et le format d'image à l'aide de la bibliothèque de génération
  de codes-barres C#.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate postal barcode
- barcode generator c#
- barcode x dimension
- barcode image format
- change barcode width
language: fr
lastmod: 2026-08-22
og_description: Générez un code-barres postal en C# avec un contrôle complet de la
  hauteur des barres, de la dimension X et du format d'image. Suivez ce tutoriel étape
  par étape pour créer des symboles postaux parfaits.
og_image_alt: Example of a generated postal barcode with custom bar height in C#
og_title: Générer un code-barres postal en C# – guide complet avec taille personnalisée
schemas:
- author: Aspose
  dateModified: '2026-08-22'
  description: Learn how to generate postal barcode in C# and control bar height,
    X dimension, and image format using the barcode generator C# library.
  headline: How to generate postal barcode in C# with custom dimensions
  type: TechArticle
tags:
- barcode
- C#
- image processing
title: Comment générer un code‑barres postal en C# avec des dimensions personnalisées
url: /fr/python-java/general/how-to-generate-postal-barcode-in-c-with-custom-dimensions/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Comment générer un code-barres postal en C# avec des dimensions personnalisées

Si vous devez générer un code-barres postal en C#, ce guide vous montre le flux de travail complet. Vous verrez comment contrôler la hauteur des barres, ajuster la dimension X du code-barres et sélectionner le format d’image de code-barres approprié.

Les codes-barres postaux sont utilisés par les services postaux du monde entier, et une implémentation fiable doit produire des dimensions cohérentes à travers différentes symbologies. Dans ce tutoriel, vous apprendrez à utiliser la classe **BarcodeGenerator**, à modifier la largeur du code-barres et à enregistrer le résultat au format PNG, JPEG ou tout autre format pris en charge.

## Prérequis

* .NET 6.0 ou version ultérieure installé  
* Une référence au package NuGet **Aspose.BarCode** (ou toute bibliothèque compatible de génération de code-barres C#)  
* Une connaissance de base de la syntaxe C# et de Visual Studio ou de votre IDE préféré  

Vous n’avez besoin d’aucun service externe ; le code s’exécute entièrement sur la machine cliente.

## Étape 1 : Configurer le projet et importer les espaces de noms

Créez une nouvelle application console et ajoutez la bibliothèque de code-barres. Les instructions `using` suivantes vous donnent accès au générateur et aux énumérations de formats d’image.

```csharp
using System;
using Aspose.BarCode.Generation;   // Provides BarcodeGenerator, EncodeTypes, etc.
using Aspose.BarCode;               // Contains BarCodeImageFormat
```

La classe `BarcodeGenerator` est le cœur de l’API C# du générateur de code-barres. Elle crée un objet qui contient tous les paramètres de rendu.

## Étape 2 : Générer un code-barres postal de base avec les dimensions par défaut

Le premier exemple crée un code-barres Planet en utilisant la hauteur de barre par défaut. Cela montre la configuration minimale requise pour générer un code-barres postal.

```csharp
// Create a Planet barcode with the default bar height
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(EncodeTypes.Planet, "123456");

// Set the module width (X dimension) to 4 pixels – this defines the narrow bar size
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 4;

// Save the image as PNG using the default bar height
barcodeGenerator.Save("PostalPlanetDefault.png", BarCodeImageFormat.Png);
```

*Pourquoi cela fonctionne* : lorsque vous omettez la propriété `BarHeight`, la bibliothèque applique la hauteur standard définie pour la symbologie sélectionnée. La `XDimension` contrôle la **dimension X du code-barres**, qui influence directement la largeur globale du symbole.

## Étape 3 : Modifier la largeur du code-barres et augmenter la hauteur des barres

Il arrive souvent que vous ayez besoin d’une barre plus haute pour répondre à des directives d’envoi spécifiques. Le code suivant définit une hauteur de barre personnalisée de 100 pixels tout en conservant la même dimension X.

```csharp
// Re‑use the generator for a custom height
barcodeGenerator = new BarcodeGenerator(EncodeTypes.Planet, "123456");
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 4;

// Increase the bar height to 100 pixels
barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 100;

// Save using the same PNG format
barcodeGenerator.Save("PostalPlanetHeight100.png", BarCodeImageFormat.Png);
```

*Pourquoi ajuster la hauteur* : la propriété `BarHeight` contrôle la taille verticale de chaque barre. Pour les services postaux qui exigent une hauteur minimale, définir cette valeur garantit la conformité sans affecter le codage.

## Étape 4 : Générer un code-barres RM4SCC avec les paramètres par défaut

RM4SCC est une autre symbologie postale courante. Le code ci‑dessous reflète l’exemple Planet mais change l’énumération `EncodeTypes`.

```csharp
// Create an RM4SCC barcode with default bar height
barcodeGenerator = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 4;

// Save as PNG; default height is applied automatically
barcodeGenerator.Save("PostalRM4SCCDefault.png", BarCodeImageFormat.Png);
```

Comme la bibliothèque sélectionne automatiquement la hauteur par défaut appropriée pour RM4SCC, vous obtenez une image conforme aux normes avec une seule ligne de code.

## Étape 5 : Modifier la hauteur des barres pour un code-barres RM4SCC

Si un système d’envoi impose une barre plus haute, vous pouvez modifier la hauteur exactement comme vous l’avez fait pour Planet.

```csharp
// RM4SCC barcode with a custom 100‑pixel bar height
barcodeGenerator = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 4;
barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 100;

// Save the result; you may also choose JPEG, BMP, or TIFF
barcodeGenerator.Save("PostalRM4SCCHeight100.png", BarCodeImageFormat.Png);
```

*Astuce* : l’énumération **barcode image format** comprend `Jpeg`, `Bmp`, `Tiff` et `Gif`. Choisissez le format qui correspond à votre pipeline de traitement en aval.

## Étape 6 : Explorer d’autres formats d’image et affiner les dimensions

Ci‑dessous se trouve un extrait compact qui montre comment changer le format de sortie et expérimenter différentes dimensions X.

```csharp
string[] formats = { "Png", "Jpeg", "Bmp", "Tiff" };
int[] xDims = { 2, 3, 4, 5 };

foreach (var fmt in formats)
{
    foreach (var x in xDims)
    {
        barcodeGenerator = new BarcodeGenerator(EncodeTypes.Planet, "123456");
        barcodeGenerator.Parameters.Barcode.XDimension.Pixels = x;
        barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 80; // consistent height

        // Dynamically choose the format enum
        BarCodeImageFormat imageFormat = (BarCodeImageFormat)Enum.Parse(
            typeof(BarCodeImageFormat), fmt, true);

        string fileName = $"Planet_X{x}_{fmt}.png";
        barcodeGenerator.Save(fileName, imageFormat);
    }
}
```

*Pourquoi itérer* : l’exécution de cette boucle produit une matrice d’images qui illustrent comment **modifier la largeur du code-barres** (via la dimension X) affecte l’apparence globale. Cela montre également que le même générateur peut produire plusieurs types de **barcode image format** sans modifications de code supplémentaires.

## Pièges courants et comment les éviter

| Problème | Raison | Solution |
|----------|--------|----------|
| Les barres apparaissent trop fines | Dimension X définie à 1 pixel ou moins | Définir `XDimension.Pixels` à au moins 2 pour la lisibilité |
| L’image est floue | Enregistrement en JPEG avec forte compression | Utiliser `BarCodeImageFormat.Png` pour une sortie sans perte |
| Taille inattendue à l’impression | DPI non pris en compte | Définir `barcodeGenerator.Parameters.ImageResolution.Dpi` si l’imprimante attend un DPI spécifique |
| Symbologie incorrecte | Utilisation de `EncodeTypes.Planet` pour des données RM4SCC | Choisir la valeur `EncodeTypes` correcte correspondant à la spécification du service postal |

## Vérifier la sortie

Après avoir exécuté le code, ouvrez l’un des fichiers PNG générés. Vous devriez voir un code-barres clair et rectangulaire avec des barres verticales uniformes. La hauteur des barres correspondra à la valeur que vous avez définie (par ex., 100 pixels), et la largeur totale reflétera la **dimension X du code-barres** que vous avez configurée.

Si vous devez intégrer l’image dans une page Web, le format PNG fonctionne nativement dans les navigateurs. Pour les rapports PDF, vous pouvez convertir le PNG en tableau d’octets et l’insérer à l’aide d’une bibliothèque PDF.

## Exemple complet – toutes les étapes dans un seul programme

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Program
{
    static void Main()
    {
        // Directory for output files
        const string outDir = @"C:\Barcodes\";

        // 1. Planet barcode – default height
        GenerateBarcode(outDir, EncodeTypes.Planet, "123456", 4, null, "PlanetDefault.png");

        // 2. Planet barcode – custom height
        GenerateBarcode(outDir, EncodeTypes.Planet, "123456", 4, 100, "PlanetHeight100.png");

        // 3. RM4SCC barcode – default height
        GenerateBarcode(outDir, EncodeTypes.RM4SCC, "123456", 4, null, "RM4SCCDefault.png");

        // 4. RM4SCC barcode – custom height
        GenerateBarcode(outDir, EncodeTypes.RM4SCC, "123456", 4, 100, "RM4SCCHeight100.png");
    }

    /// <summary>
    /// Creates a barcode image with optional custom height.
    /// </summary>
    static void GenerateBarcode(string folder, EncodeTypes type, string data,
                                int xDim, int? barHeight, string fileName)
    {
        var generator = new BarcodeGenerator(type, data);
        generator.Parameters.Barcode.XDimension.Pixels = xDim;

        if (barHeight.HasValue)
            generator.Parameters.Barcode.BarHeight.Pixels = barHeight.Value;

        generator.Save(System.IO.Path.Combine(folder, fileName), BarCodeImageFormat.Png);
    }
}
```

L’exécution de ce programme produit quatre fichiers PNG dans `C:\Barcodes\`. Chaque fichier montre une combinaison différente de **generate postal barcode**, **barcode X dimension** et **barcode image format**.

## Conclusion

Vous savez maintenant comment générer un code-barres postal en C# et contrôler entièrement la hauteur des barres, la largeur des modules et le format de sortie. En ajustant la **dimension X du code-barres** et en utilisant le **format d’image de code-barres** approprié, vous pouvez répondre à n’importe quelle spécification d’envoi et intégrer les symboles dans des applications de bureau, Web ou mobiles.

Ensuite, explorez les fonctionnalités avancées telles que l’ajout de texte lisible par l’homme, l’application de palettes de couleurs ou l’intégration du code-barres dans des documents PDF. Ces sujets impliquent les mêmes concepts **barcode generator C#** que vous venez de maîtriser, vous permettant d’étendre cette base en toute confiance.

## Que devriez‑vous apprendre ensuite ?

Les tutoriels suivants couvrent des sujets étroitement liés qui s’appuient sur les techniques démontrées dans ce guide. Chaque ressource comprend des exemples de code complets et fonctionnels avec des explications étape par étape pour vous aider à maîtriser des fonctionnalités supplémentaires de l’API et à explorer des approches d’implémentation alternatives dans vos propres projets.

- [Comment générer et ajuster la hauteur du code-barres pour Databar unidimensionnel avec Aspose.BarCode pour .NET](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-barcode-height-adjustment/)
- [Générer une image de code-barres – Code 93 avec Aspose.BarCode](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-code-93-configuration/)
- [Comment générer un code-barres Aztec avec un ratio d’aspect personnalisé en utilisant Aspose.BarCode pour .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}