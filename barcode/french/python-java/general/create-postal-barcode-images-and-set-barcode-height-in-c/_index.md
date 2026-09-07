---
category: general
date: 2026-09-07
description: Créez des images de codes‑barres postaux en C# et apprenez à modifier
  la hauteur du code‑barres avec un exemple concis de générateur de codes‑barres –
  tutoriel C#.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create postal barcode images
- barcode generator example c#
- change barcode height
language: fr
lastmod: 2026-09-07
og_description: Créez des images de codes-barres postaux en C# et découvrez la façon
  la plus simple de modifier la hauteur du code-barres à l'aide d'un exemple clair
  de générateur de codes-barres en C#.
og_image_alt: Screenshot showing created postal barcode images with custom height
og_title: Créer des images de code‑barres postaux – définir la hauteur du code‑barres
  en C#
schemas:
- author: Aspose
  dateModified: '2026-09-07'
  description: Create postal barcode images in C# and learn how to change barcode
    height with a concise barcode generator example C# tutorial.
  headline: Create postal barcode images and set barcode height in C#
  type: TechArticle
tags:
- barcode
- C#
- Aspose.BarCode
title: Créer des images de code‑barres postal et définir la hauteur du code‑barres
  en C#
url: /fr/python-java/general/create-postal-barcode-images-and-set-barcode-height-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Créer des images de code-barres postaux et définir la hauteur du code-barres en C#

Si vous devez **créer des images de code-barres postaux** pour des applications d'envoi, ce guide vous présente une solution complète, prête à l'emploi. Vous verrez un **exemple de générateur de code-barres C#** qui produit à la fois les codes-barres Planet et RM4SCC et apprenez comment **modifier la hauteur du code-barres** sans quitter le code.

Le tutoriel couvre tout ce dont vous avez besoin pour commencer à générer des codes-barres postaux immédiatement : les packages NuGet requis, la préparation du dossier, la génération à hauteur par défaut, la personnalisation de hauteur fixe, et les pièges courants à éviter.

## Prérequis

- .NET 6.0 SDK ou version ultérieure installé  
- Visual Studio 2022 (ou tout IDE C#)  
- Le package NuGet **Aspose.BarCode** (`Install-Package Aspose.BarCode`)  

Ces composants vous donnent accès à la classe `BarcodeGenerator` utilisée tout au long des exemples.

## Étape 1 : Préparer le dossier de sortie

Le générateur écrit des fichiers PNG sur le disque, donc le dossier doit exister et être accessible en écriture.

```csharp
using System;
using System.IO;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

// Define where the barcode images will be saved
string outputFolder = Path.Combine(Environment.CurrentDirectory, "Barcodes");

// Ensure the directory exists
Directory.CreateDirectory(outputFolder);
Console.WriteLine($"Images will be saved to: {outputFolder}");
```

*Pourquoi c'est important* : essayer d'enregistrer dans un chemin inexistant lève une `DirectoryNotFoundException`. `Directory.CreateDirectory` est sûr car il ne fait rien si le dossier existe déjà.

## Étape 2 : Générer des codes-barres Planet et RM4SCC à hauteur par défaut

Lorsque vous omettez la propriété `BarHeight`, la bibliothèque choisit automatiquement une hauteur optimale (mode auto). Cela est utile pour les prototypes rapides.

```csharp
// Planet barcode – auto height
var planetAuto = new BarcodeGenerator(EncodeTypes.Planet, "123456")
{
    // Set module width (X dimension) to 4 pixels for readability
    Parameters = { Barcode = { XDimension = { Pixels = 4 } } }
};
planetAuto.Save(Path.Combine(outputFolder, "PostalPlanetBarHeightAuto.png"),
                BarCodeImageFormat.Png);

// RM4SCC barcode – auto height
var rm4sccAuto = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456")
{
    Parameters = { Barcode = { XDimension = { Pixels = 4 } } }
};
rm4sccAuto.Save(Path.Combine(outputFolder, "PostalRM4SCCBarHeightAuto.png"),
                BarCodeImageFormat.Png);
```

**Résultat** : deux fichiers PNG apparaissent dans `Barcodes/` avec la hauteur de barre choisie par la bibliothèque.

## Étape 3 : Définir une hauteur de barre explicite (100 pixels)

Parfois, les spécifications d'envoi exigent une hauteur de barre fixe. Vous pouvez la contrôler via la propriété `BarHeight.Pixels`.

```csharp
// Planet barcode – fixed 100‑pixel height
var planetFixed = new BarcodeGenerator(EncodeTypes.Planet, "123456")
{
    Parameters = {
        Barcode = {
            XDimension = { Pixels = 4 },   // module width
            BarHeight = { Pixels = 100 }   // explicit height
        }
    }
};
planetFixed.Save(Path.Combine(outputFolder, "PostalPlanetBarHeight100.png"),
                 BarCodeImageFormat.Png);

// RM4SCC barcode – fixed 100‑pixel height
var rm4sccFixed = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456")
{
    Parameters = {
        Barcode = {
            XDimension = { Pixels = 4 },
            BarHeight = { Pixels = 100 }
        }
    }
};
rm4sccFixed.Save(Path.Combine(outputFolder, "PostalRM4SCCBarHeight100.png"),
                 BarCodeImageFormat.Png);
```

**Pourquoi vous pourriez en avoir besoin** : les services postaux définissent souvent une hauteur de barre minimale pour la fiabilité du scan. Définir une hauteur fixe garantit la conformité de toutes les images générées.

## Étape 4 : Vérifier les images générées

Vous pouvez ouvrir les fichiers PNG avec n'importe quel visualiseur d'images. La différence visuelle est la longueur des barres :

- **Fichiers à hauteur auto** : la hauteur de la barre s'adapte à la longueur des données.  
- **Fichiers à hauteur fixe** : les barres mesurent exactement 100 pixels de haut, quel que soit le contenu.  

Si vous devez confirmer la hauteur de façon programmatique, vous pouvez charger l'image avec `System.Drawing` et inspecter `Bitmap.Height`.

```csharp
using System.Drawing;

void PrintBarHeight(string filePath)
{
    using var bmp = new Bitmap(filePath);
    Console.WriteLine($"{Path.GetFileName(filePath)} – Height: {bmp.Height}px");
}

PrintBarHeight(Path.Combine(outputFolder, "PostalPlanetBarHeightAuto.png"));
PrintBarHeight(Path.Combine(outputFolder, "PostalPlanetBarHeight100.png"));
```

## Astuce pro : Ajuster le DPI pour les impressions haute résolution

Lorsque le code-barres sera imprimé sur une imprimante d'étiquettes, vous pouvez souhaiter un réglage DPI plus élevé. La propriété `Resolution` vous permet de le contrôler sans modifier les dimensions en pixels.

```csharp
planetFixed.Parameters.Resolution = 300; // 300 dpi for crisp prints
planetFixed.Save(Path.Combine(outputFolder, "Planet_300dpi.png"),
                 BarCodeImageFormat.Png);
```

## Pièges courants et comment les éviter

| Problème | Cause | Solution |
|----------|-------|----------|
| **Image non créée** | Dossier de sortie manquant ou aucune permission d'écriture | Appeler `Directory.CreateDirectory` et exécuter l'application avec des privilèges suffisants |
| **Code‑barres illisible** | Dimension X trop petite (p. ex., 1 pixel) | Utiliser au moins 2 pixels ; 4 pixels fonctionnent bien pour la plupart des scanners |
| **Type de code‑barres incorrect** | Valeur `EncodeTypes` erronée | Vérifier la spécification postale (Planet vs. RM4SCC) et utiliser l'énumération correspondante |

## Code source complet (prêt à copier)

```csharp
using System;
using System.IO;
using System.Drawing;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class PostalBarcodeDemo
{
    static void Main()
    {
        // -------------------------------------------------
        // Step 1 – Prepare output folder
        // -------------------------------------------------
        string outputFolder = Path.Combine(Environment.CurrentDirectory, "Barcodes");
        Directory.CreateDirectory(outputFolder);
        Console.WriteLine($"Saving images to: {outputFolder}");

        // -------------------------------------------------
        // Step 2 – Auto‑height barcodes
        // -------------------------------------------------
        var planetAuto = new BarcodeGenerator(EncodeTypes.Planet, "123456")
        {
            Parameters = { Barcode = { XDimension = { Pixels = 4 } } }
        };
        planetAuto.Save(Path.Combine(outputFolder, "PostalPlanetBarHeightAuto.png"),
                        BarCodeImageFormat.Png);

        var rm4sccAuto = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456")
        {
            Parameters = { Barcode = { XDimension = { Pixels = 4 } } }
        };
        rm4sccAuto.Save(Path.Combine(outputFolder, "PostalRM4SCCBarHeightAuto.png"),
                        BarCodeImageFormat.Png);

        // -------------------------------------------------
        // Step 3 – Fixed 100‑pixel height barcodes
        // -------------------------------------------------
        var planetFixed = new BarcodeGenerator(EncodeTypes.Planet, "123456")
        {
            Parameters = {
                Barcode = {
                    XDimension = { Pixels = 4 },
                    BarHeight = { Pixels = 100 }
                }
            }
        };
        planetFixed.Save(Path.Combine(outputFolder, "PostalPlanetBarHeight100.png"),
                         BarCodeImageFormat.Png);

        var rm4sccFixed = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456")
        {
            Parameters = {
                Barcode = {
                    XDimension = { Pixels = 4 },
                    BarHeight = { Pixels = 100 }
                }
            }
        };
        rm4sccFixed.Save(Path.Combine(outputFolder, "PostalRM4SCCBarHeight100.png"),
                         BarCodeImageFormat.Png);

        // -------------------------------------------------
        // Step 4 – Verify heights (optional)
        // -------------------------------------------------
        PrintBarHeight(Path.Combine(outputFolder, "PostalPlanetBarHeightAuto.png"));
        PrintBarHeight(Path.Combine(outputFolder, "PostalPlanetBarHeight100.png"));
    }

    static void PrintBarHeight(string filePath)
    {
        using var bmp = new Bitmap(filePath);
        Console.WriteLine($"{Path.GetFileName(filePath)} – Height: {bmp.Height}px");
    }
}
```

L'exécution du programme crée quatre fichiers PNG :

- `PostalPlanetBarHeightAuto.png`
- `PostalRM4SCCBarHeightAuto.png`
- `PostalPlanetBarHeight100.png`
- `PostalRM4SCCBarHeight100.png`

Each

## Que devriez‑vous apprendre ensuite ?

Les tutoriels suivants couvrent des sujets étroitement liés qui s'appuient sur les techniques démontrées dans ce guide. Chaque ressource comprend des exemples de code complets et fonctionnels avec des explications étape par étape pour vous aider à maîtriser des fonctionnalités d'API supplémentaires et explorer des approches d'implémentation alternatives dans vos propres projets.

- [Créer un code‑barres postal en C# – Exemple complet de générateur](/barcode/english/python-java/general/create-postal-barcode-in-c-full-generator-example/)
- [.net barcode generator – modifier la hauteur du code‑barres](/barcode/english/python-java/general/net-barcode-generator-change-barcode-height/)
- [Créer une hauteur personnalisée de code‑barres – Codes‑barres unidimensionnels](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-barcode-height-adjustment/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}