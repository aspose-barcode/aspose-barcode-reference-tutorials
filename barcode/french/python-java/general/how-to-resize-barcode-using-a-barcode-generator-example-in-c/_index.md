---
category: general
date: 2026-10-08
description: Apprenez à redimensionner les images de codes‑barres avec un exemple
  de générateur de codes‑barres en C#, en ajustant la hauteur des barres de 30 px
  à 60 px en quelques lignes de code.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to resize barcode
- barcode generator example c#
language: fr
lastmod: 2026-10-08
og_description: Comment redimensionner rapidement un code‑barres avec un exemple de
  générateur de code‑barres C#. Ajustez la hauteur des barres, enregistrez des fichiers
  PNG et évitez les pièges courants.
og_image_alt: Screenshot showing a resized barcode generated with C# code
og_title: Comment redimensionner un code‑barres en C# – exemple de générateur étape
  par étape
schemas:
- author: Aspose
  dateModified: '2026-10-08'
  description: Learn how to resize barcode images with a C# barcode generator example,
    adjusting bar height from 30 px to 60 px in just a few lines of code.
  headline: How to resize barcode using a barcode generator example in C#
  type: TechArticle
- description: Learn how to resize barcode images with a C# barcode generator example,
    adjusting bar height from 30 px to 60 px in just a few lines of code.
  name: How to resize barcode using a barcode generator example in C#
  steps:
  - name: Open each PNG in an image viewer and verify the pixel dimensions (e.g.,
      150 × 30 px vs. 150 × 60 px).
    text: Open each PNG in an image viewer and verify the pixel dimensions (e.g.,
      150 × 30 px vs. 150 × 60 px).
  - name: Print the images at 100 % scale.
    text: Print the images at 100 % scale.
  - name: Scan with a handheld barcode scanner or a mobile app. The decoded data should
      be
    text: Scan with a handheld barcode scanner or a mobile app. The decoded data should
      be
  type: HowTo
tags:
- barcode
- C#
- image processing
title: Comment redimensionner un code‑barres à l’aide d’un exemple de générateur de
  code‑barres en C#
url: /fr/python-java/general/how-to-resize-barcode-using-a-barcode-generator-example-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Comment redimensionner un code‑barres à l'aide d'un exemple de générateur de code‑barres en C#

Si vous devez **redimensionner un code‑barres** dans un projet .NET, ce guide montre la solution complète. Vous verrez un **exemple de générateur de code‑barres C#** concis qui modifie la hauteur des barres de 30 px à 60 px et enregistre chaque version sous forme de fichier PNG.

Le redimensionnement d’un code‑barres est souvent nécessaire lorsque les mêmes données doivent apparaître sur des tickets, des étiquettes ou des pages produit à des échelles visuelles différentes. Plutôt que de modifier l’image raster avec un éditeur externe, vous pouvez ajuster les dimensions du code‑barres de façon programmatique, tout en conservant l’intégrité des données.

Dans ce tutoriel, vous allez :

* Configurer un générateur de code‑barres DataBar Omni‑Directional.  
* Modifier les paramètres X‑dimension et hauteur des barres.  
* Enregistrer deux images avec des hauteurs distinctes.  
* Comprendre pourquoi la modification de la hauteur des barres fonctionne et quels cas limites surveiller.

> **Prérequis** – Vous disposez d’un environnement de développement .NET (Visual Studio 2022 ou version ultérieure) et de la bibliothèque de code‑barres qui fournit `BarcodeGenerator`, `EncodeTypes` et `BarCodeImageFormat`. Le code fonctionne avec la dernière version de la bibliothèque en date d’octobre 2026.

## Prérequis pour l’exemple de générateur de code‑barres C#

Avant de commencer, assurez‑vous d’avoir :

| Élément | Raison |
|------|--------|
| .NET 6.0 SDK ou version plus récente | Fournit le runtime et les fonctionnalités du langage utilisées dans l’exemple. |
| Bibliothèque de code‑barres (par ex., Aspose.BarCode, Dynamsoft, ou toute bibliothèque exposant `BarcodeGenerator`) | Fournit l’énumération `EncodeTypes.DatabarOmniDirectional` et les méthodes d’exportation d’image. |
| Un dossier dans lequel vous pouvez écrire (par ex., `C:\Temp\Barcodes\`) | L’exemple enregistre les fichiers PNG à cet emplacement. |
| Connaissances de base en C# | Le tutoriel suppose une familiarité avec les classes, propriétés et l’interpolation de chaînes. |

Installez la bibliothèque via NuGet si ce n’est pas déjà fait :

```bash
dotnet add package Aspose.BarCode
```

Remplacez le nom du package par celui que vous utilisez réellement ; l’interface API présentée ci‑dessous est commune à la plupart des SDK de code‑barres.

## Comment redimensionner un code‑barres – étape 1 : créer le générateur

La première étape consiste à instancier un `BarcodeGenerator` avec la symbologie souhaitée et les données à encoder. Dans cet exemple nous générons un code‑barres **DataBar Omni‑Directional** qui encode une valeur GTIN‑14.

```csharp
using Aspose.BarCode.Generation;

// Step 1: Create a DataBar Omni‑Directional barcode generator with the desired data
BarcodeGenerator generator = new BarcodeGenerator(
    EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");
```

**Pourquoi c’est important :** L’énumération `EncodeTypes.DatabarOmniDirectional` indique à la bibliothèque quel standard de code‑barres utiliser. La chaîne de données suit l’identifiant d’application GS1 `(01)` pour un GTIN à 14 chiffres, garantissant la conformité du code‑barres aux normes commerciales mondiales.

## Comment redimensionner un code‑barres – étape 2 : définir la largeur du module et la hauteur initiale des barres

La taille visuelle d’un code‑barres dépend de deux paramètres :

* **X‑dimension** – la largeur du plus petit module (barre). Mesurée en pixels ou millimètres.  
* **Bar height** – la longueur verticale des barres.

Définir ces valeurs avant l’enregistrement garantit que l’image rendue correspond aux dimensions requises.

```csharp
// Step 2: Define the X‑dimension (module width) and set the bar height to 30 px
generator.Parameters.Barcode.XDimension.Pixels = 2;   // 2 px per module
generator.Parameters.Barcode.BarHeight.Pixels = 30; // 30 px tall bars
```

**Explication :** Une X‑dimension de 2 px donne un code‑barres compact qui reste lisible. La hauteur de 30 px est une valeur par défaut courante pour les petites étiquettes. Vous pouvez ajuster la X‑dimension indépendamment de la hauteur si vous avez besoin d’un motif plus dense ou plus espacé.

## Comment redimensionner un code‑barres – étape 3 : enregistrer la première image (hauteur 30 px)

Exportez maintenant le code‑barres vers un fichier PNG. La méthode `Save` accepte un chemin de fichier et une énumération de format d’image.

```csharp
// Step 3: Save the barcode image with a 30 px height
string outputPath = @"C:\Temp\Barcodes\";
generator.Save($"{outputPath}DatabarBarHeight30Pixels.png", BarCodeImageFormat.Png);
```

**Résultat :** `DatabarBarHeight30Pixels.png` contient un code‑barres de 30 px de hauteur. Vous pouvez ouvrir le fichier avec n’importe quel visualiseur d’image pour vérifier les dimensions.

## Comment redimensionner un code‑barres – étape 4 : changer la hauteur des barres à 60 px

Pour créer une version plus grande, il suffit de modifier la propriété `BarHeight`. Le générateur réutilise les mêmes données et la même X‑dimension, de sorte que le motif du code‑barres reste identique — seule la taille visuelle change.

```csharp
// Step 4: Change the bar height to 60 px for a larger barcode
generator.Parameters.Barcode.BarHeight.Pixels = 60;
```

**Pourquoi cela fonctionne :** Le moteur de rendu calcule la géométrie de chaque barre à la volée. Mettre à jour la propriété de hauteur avant le prochain appel à `Save` déclenche une nouvelle rasterisation avec les nouvelles dimensions.

## Comment redimensionner un code‑barres – étape 5 : enregistrer la deuxième image (hauteur 60 px)

```csharp
// Step 5: Save the barcode image with a 60 px height
generator.Save($"{outputPath}DatabarBarHeight60Pixels.png", BarCodeImageFormat.Png);
```

Vous disposez maintenant de deux fichiers PNG, l’un petit (30 px) et l’autre plus grand (60 px), prêts à être utilisés sur des étiquettes de tailles différentes.

## Code complet pour l’exemple de générateur de code‑barres C#

Voici le programme complet, exécutable immédiatement. Copiez‑le dans un nouveau projet console pour le tester.

```csharp
using System;
using Aspose.BarCode.Generation;

namespace BarcodeResizeDemo
{
    class Program
    {
        static void Main()
        {
            // 1️⃣ Create the generator with DataBar Omni‑Directional symbology
            BarcodeGenerator generator = new BarcodeGenerator(
                EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");

            // 2️⃣ Set X‑dimension and initial bar height (30 px)
            generator.Parameters.Barcode.XDimension.Pixels = 2;
            generator.Parameters.Barcode.BarHeight.Pixels = 30;

            // 3️⃣ Define output folder (ensure it exists)
            string outputPath = @"C:\Temp\Barcodes\";
            System.IO.Directory.CreateDirectory(outputPath);

            // 4️⃣ Save the 30 px version
            generator.Save($"{outputPath}DatabarBarHeight30Pixels.png", BarCodeImageFormat.Png);
            Console.WriteLine("Saved 30 px barcode.");

            // 5️⃣ Increase bar height to 60 px
            generator.Parameters.Barcode.BarHeight.Pixels = 60;

            // 6️⃣ Save the 60 px version
            generator.Save($"{outputPath}DatabarBarHeight60Pixels.png", BarCodeImageFormat.Png);
            Console.WriteLine("Saved 60 px barcode.");
        }
    }
}
```

**Sortie attendue dans la console :**

```
Saved 30 px barcode.
Saved 60 px barcode.
```

Après exécution, ouvrez les deux fichiers PNG pour observer la différence visuelle. Les deux codes‑barres encodent la même valeur GTIN‑14 et seront lus de façon identique, quelle que soit la hauteur.

## Pourquoi ajuster la hauteur des barres est sûr pour la lecture

Les lecteurs de code‑barres analysent le motif de modules clairs et sombres, pas le nombre absolu de pixels. Tant que la **X‑dimension** reste dans la tolérance du lecteur (généralement entre 0,5 mm et 2 mm en unités physiques), modifier la hauteur n’affecte pas la lisibilité. La bibliothèque met automatiquement à l’échelle les modules, en préservant les zones calmes et les motifs d’alignement requis.

## Pièges courants et comment les éviter

| Problème | Comment corriger |
|----------|------------------|
| **Le dossier de sortie n’existe pas** | Appelez `Directory.CreateDirectory(outputPath)` avant d’enregistrer. |
| **X‑dimension incorrecte entraînant des scans flous** | Gardez `XDimension.Pixels` entre 1 px et 4 px pour la plupart des imprimantes ; testez avec un scanner physique. |
| **Utilisation d’un format raster pour des codes‑barres très grands** | Passez à `BarCodeImageFormat.Svg` pour une évolutivité infinie sans pixellisation. |
| **Oublier de réinitialiser `BarHeight` avant le deuxième enregistrement** | Assurez‑vous d’attribuer la nouvelle hauteur **avant** d’appeler à nouveau `Save`. |

## Astuce pro : générer plusieurs tailles dans une boucle

Si vous avez besoin d’une gamme de hauteurs (par ex., 30 px, 45 px, 60 px), une simple boucle `foreach` évite la duplication :

```csharp
int[] heights = { 30, 45, 60 };
foreach (int h in heights)
{
    generator.Parameters.Barcode.BarHeight.Pixels = h;
    generator.Save($"{outputPath}DatabarBarHeight{h}Pixels.png", BarCodeImageFormat.Png);
    Console.WriteLine($"Saved {h} px barcode.");
}
```

Ce modèle s’adapte bien au traitement par lots de catalogues produits.

## Cas limites : formats d’image différents et réglages DPI

* **Sortie SVG** – Utilisez `BarCodeImageFormat.Svg` pour produire un fichier vectoriel redimensionnable sans perte de qualité.  
* **PNG haute résolution** – Réglez `generator.Parameters.Image.DpiX` et `DpiY` à 300 ou 600 pour des images prêtes à l’impression ; la hauteur des barres restera mesurée en pixels, il faut donc l’augmenter proportionnellement.  
* **Symbologies non standard** – Certaines types (par ex., QR Code) possèdent une propriété `Size` distincte au lieu de `BarHeight`. Consultez la documentation de la bibliothèque pour ces cas.

## Tester le code‑barres redimensionné

1. Ouvrez chaque PNG dans un visualiseur d’image et vérifiez les dimensions en pixels (par ex., 150 × 30 px vs. 150 × 60 px).  
2. Imprimez les images à 100 % d’échelle.  
3. Scannez avec un lecteur de code‑barres portable ou une application mobile. Les données décodées doivent être identiques.

## Que devez‑vous apprendre ensuite ?

Les tutoriels suivants abordent des sujets étroitement liés qui prolongent les techniques présentées dans ce guide. Chaque ressource comprend des exemples de code complets avec des explications pas à pas pour vous aider à maîtriser d’autres fonctionnalités de l’API et à explorer des approches d’implémentation alternatives dans vos propres projets.

- [Exemple de générateur de code‑barres en C# – définir la largeur et la hauteur](/barcode/english/python-java/general/barcode-generator-example-in-c-set-width-and-height/)
- [Comment redimensionner un code‑barres en C# avec Aspose.BarCode – guide pas à pas](/barcode/english/python-java/general/how-to-resize-barcode-in-c-with-aspose-barcode-step-by-step/)
- [Comment enregistrer des images de code‑barres avec Barcode Generator C# – guide pas à pas](/barcode/english/python-java/general/how-to-save-barcode-images-with-barcode-generator-c-step-by/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}