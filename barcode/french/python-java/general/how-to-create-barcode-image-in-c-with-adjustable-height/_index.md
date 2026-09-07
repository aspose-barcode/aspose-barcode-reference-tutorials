---
category: general
date: 2026-09-07
description: Apprenez à créer une image de code‑barres en C# et à ajuster sa hauteur,
  sa largeur et son format pour générer rapidement des fichiers PNG de code‑barres.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode image
- how to set barcode
- how to adjust barcode
- generate barcode png
- change barcode height
language: fr
lastmod: 2026-09-07
og_description: Créer une image de code‑barres en C# et apprendre à définir les dimensions
  du code‑barres, à modifier sa hauteur et à générer des fichiers PNG de code‑barres
  pour toute application.
og_image_alt: C# generated barcode image saved as PNG with custom height
og_title: Créer une image de code‑barres en C# – guide étape par étape
schemas:
- author: Aspose
  dateModified: '2026-09-07'
  description: Learn how to create barcode image in C# and adjust its height, width,
    and format to generate barcode PNG files quickly.
  headline: How to create barcode image in C# with adjustable height
  type: TechArticle
- description: Learn how to create barcode image in C# and adjust its height, width,
    and format to generate barcode PNG files quickly.
  name: How to create barcode image in C# with adjustable height
  steps:
  - name: 3.1 Adjust the narrow bar width (X‑dimension)
    text: The X‑dimension controls the thickness of the thinnest bar. A value of **2
      pixels** yields a finer appearance, useful when you need a compact label.
  - name: 3.2 Change barcode height for visual balance
    text: Bar height determines how tall the barcode appears. Below we show two common
      heights—30 pixels for a small label and 60 pixels for a larger visual. This
      demonstrates **how to adjust barcode** height programmatically.
  - name: 4.1 Save the first image (30 px height)
    text: '```csharp // Save a 30‑pixel‑high barcode as PNG generator.Save("DatabarBarHeight30Pixels.png",
      BarCodeImageFormat.Png); ```'
  - name: 4.2 Increase the height and save a second image
    text: '```csharp // Increase height to 60 pixels for a larger visual generator.Parameters.Barcode.BarHeight.Pixels
      = 60;'
  type: HowTo
tags:
- barcode
- C#
- image generation
title: Comment créer une image de code‑barres en C# avec une hauteur réglable
url: /fr/python-java/general/how-to-create-barcode-image-in-c-with-adjustable-height/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Comment créer une image de code‑barres en C# avec une hauteur ajustable

Si vous devez créer une image de code‑barres en C# pour un système de point de vente ou un suivi d’inventaire, ce guide vous montre le flux complet. Vous verrez comment définir les paramètres du code‑barres, modifier la hauteur du code‑barres et générer des fichiers PNG de code‑barres qui répondent aux exigences visuelles.

Générer une image de code‑barres est une tâche courante lors de l’intégration de matériel de lecture, de l’impression d’étiquettes ou de la création de tableaux de bord de reporting. À la fin de ce tutoriel, vous disposerez d’un extrait de code réutilisable qui vous permet d’ajuster la dimension X du code‑barres, sa hauteur et le format de sortie sans quitter votre IDE.

## Prérequis

Avant de commencer, assurez‑vous d’avoir :

* .NET 6.0 (ou ultérieur) installé – le code se compile avec n’importe quel SDK .NET récent.
* Une référence à la bibliothèque **Aspose.BarCode** (disponible via NuGet `Aspose.BarCode`).
* Une connaissance de base des applications console C#.

Ces exigences garantissent que l’exemple fonctionne immédiatement sous Windows, Linux ou macOS.

## Étape 1 : Configurer le projet et importer la bibliothèque

Créez un nouveau projet console et ajoutez le package de code‑barres :

```bash
dotnet new console -n BarcodeDemo
cd BarcodeDemo
dotnet add package Aspose.BarCode
```

Ouvrez maintenant *Program.cs* et ajoutez les directives `using` nécessaires :

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode.Encoding;
using Aspose.BarCode;
```

Ces importations vous donnent accès à `BarcodeGenerator`, `EncodeTypes` et aux énumérations de formats d’image nécessaires pour **créer des fichiers image de code‑barres**.

## Étape 2 : Initialiser le générateur avec la symbologie souhaitée

La première ligne de code crée un `BarcodeGenerator` qui sait quel type de code‑barres encoder. Dans cet exemple nous utilisons la symbologie DataBar Omni‑Directional, mais vous pouvez remplacer `EncodeTypes.DatabarOmniDirectional` par tout autre type pris en charge par Aspose.BarCode.

```csharp
// Initialize a generator for a DataBar Omni‑Directional barcode
var generator = new BarcodeGenerator(
    EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");
```

La chaîne `"(01)12345678901231"` suit le format d’Identifiant d’Application GS1, requis par de nombreux détaillants. L’initialisation du générateur constitue la base de chaque opération **comment définir le code‑barres** qui suit.

## Étape 3 : Comment définir les dimensions du code‑barres – dimension X et hauteur

### 3.1 Ajuster la largeur de la barre fine (dimension X)

La dimension X contrôle l’épaisseur de la barre la plus fine. Une valeur de **2 pixels** donne un aspect plus fin, utile lorsque vous avez besoin d’une étiquette compacte.

```csharp
// Set the narrow bar width to 2 pixels
generator.Parameters.Barcode.XDimension.Pixels = 2;
```

### 3.2 Modifier la hauteur du code‑barres pour un équilibre visuel

La hauteur de la barre détermine la taille verticale du code‑barres. Ci‑dessous nous montrons deux hauteurs courantes : 30 pixels pour une petite étiquette et 60 pixels pour une plus grande. Cela illustre **comment ajuster la hauteur du code‑barres** de façon programmatique.

```csharp
// Height 30 pixels – suitable for compact labels
generator.Parameters.Barcode.BarHeight.Pixels = 30;
```

## Étape 4 : Générer des fichiers PNG de code‑barres avec différentes hauteurs

### 4.1 Enregistrer la première image (hauteur 30 px)

```csharp
// Save a 30‑pixel‑high barcode as PNG
generator.Save("DatabarBarHeight30Pixels.png", BarCodeImageFormat.Png);
```

### 4.2 Augmenter la hauteur et enregistrer une seconde image

```csharp
// Increase height to 60 pixels for a larger visual
generator.Parameters.Barcode.BarHeight.Pixels = 60;

// Save a 60‑pixel‑high barcode as PNG
generator.Save("DatabarBarHeight60Pixels.png", BarCodeImageFormat.Png);
```

Ces deux appels `Save` illustrent **générer des fichiers PNG de code‑barres** avec des dimensions distinctes tout en réutilisant la même instance du générateur. Le format d’image est explicitement défini sur PNG, ce qui préserve une qualité sans perte – idéal pour l’impression ou l’affichage à l’écran.

## Étape 5 : Exemple complet, exécutable

Assembler le tout donne une méthode `Main` unique que vous pouvez copier dans n’importe quel projet console C# :

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode.Encoding;
using Aspose.BarCode;

class Program
{
    static void Main()
    {
        // 1️⃣ Create a DataBar Omni‑Directional barcode generator
        var generator = new BarcodeGenerator(
            EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");

        // 2️⃣ Set the narrow bar width (X‑dimension) to 2 pixels
        generator.Parameters.Barcode.XDimension.Pixels = 2;

        // 3️⃣ Create a 30‑pixel‑high barcode and save it as PNG
        generator.Parameters.Barcode.BarHeight.Pixels = 30;
        generator.Save("DatabarBarHeight30Pixels.png", BarCodeImageFormat.Png);
        Console.WriteLine("Saved 30‑pixel barcode as DatabarBarHeight30Pixels.png");

        // 4️⃣ Change barcode height to 60 pixels and save again
        generator.Parameters.Barcode.BarHeight.Pixels = 60;
        generator.Save("DatabarBarHeight60Pixels.png", BarCodeImageFormat.Png);
        Console.WriteLine("Saved 60‑pixel barcode as DatabarBarHeight60Pixels.png");
    }
}
```

L’exécution de ce programme produit deux fichiers PNG dans le dossier de sortie du projet :

* `DatabarBarHeight30Pixels.png` – un code‑barres compact de 30 px.
* `DatabarBarHeight60Pixels.png` – un code‑barres plus grand de 60 px.

Les deux fichiers contiennent une **image de code‑barres créée** qui peut être intégrée dans du HTML, imprimée sur des étiquettes ou envoyée à une application mobile pour la lecture.

## Questions fréquentes et gestion des cas limites

| Question | Réponse |
|----------|--------|
| **Et si j’ai besoin d’un format d’image différent ?** | Remplacez `BarCodeImageFormat.Png` par `BarCodeImageFormat.Jpeg`, `Bmp` ou `Gif`. La bibliothèque gère automatiquement la conversion. |
| **Puis‑je changer les couleurs de premier plan/arrière‑plan ?** | Oui. Utilisez `generator.Parameters.Barcode.ForeColor` et `BackColor` pour définir des valeurs `System.Drawing.Color` avant d’appeler `Save`. |
| **Comment générer un code‑barres sans créer de fichier sur le disque ?** | Appelez `generator.GenerateBarCodeImage()` pour obtenir un objet `System.Drawing.Image`, puis diffusez‑le directement dans une réponse ou une base de données. |
| **Que se passe‑t‑il si la chaîne de données dépasse la limite de la symbologie ?** | Le générateur lève une `ArgumentException`. Validez la longueur d’entrée ou tronquez‑la selon les spécifications de la symbologie. |
| **Existe‑t‑il un moyen de traiter plusieurs codes‑barres en lot ?** | Enveloppez les étapes dans une boucle `foreach` qui met à jour `generator.CodeText` et `BarHeight` pour chaque élément, puis appelez `Save` avec un nom de fichier unique. |

Aborder ces scénarios rend la logique **comment ajuster le code‑barres** robuste pour des projets réels.

## Astuces pro pour une génération fiable de code‑barres

* **Mettez en cache le générateur** lorsque vous créez de nombreux codes‑barres du même type ; réutiliser l’objet réduit la surcharge d’allocation.
* **Définissez `Resolution`** (`generator.Parameters.ImageResolution.Dpi`) si vous avez besoin de PNG haute résolution pour l’impression.
* **Validez les données GS1** avant de les assigner à `CodeText` afin d’éviter les erreurs d’encodage pouvant entraîner des échecs de lecture.
* **Testez sur des lecteurs réels** après avoir modifié la hauteur ou la dimension X – certains appareils anciens imposent des exigences de taille minimale.

## Conclusion

Vous savez maintenant comment **créer une image de code‑barres** en C#, **comment définir les dimensions du code‑barres**, **comment ajuster la hauteur du code‑barres**, et **générer des fichiers PNG de code‑barres** pour n’importe quelle exigence visuelle. En ajustant `XDimension` et `BarHeight`, vous pouvez produire des codes‑barres compacts ou grands sans modifier les données sous‑jacentes.

Ensuite, explorez des sujets connexes tels que **modifier dynamiquement la hauteur du code‑barres** en fonction de l’entrée utilisateur, intégrer des codes‑barres dans des rapports PDF avec Aspose.PDF, ou passer à la génération de QR‑code avec `EncodeTypes.QR`. Expérimentez différentes symbologies et formats de sortie pour maîtriser pleinement la création de codes‑barres en C#.

## Que devriez‑vous apprendre ensuite ?

Les tutoriels suivants couvrent des sujets étroitement liés qui s’appuient sur les techniques démontrées dans ce guide. Chaque ressource comprend des exemples de code complets et fonctionnels avec des explications pas à pas pour vous aider à maîtriser des fonctionnalités API supplémentaires et à explorer des approches d’implémentation alternatives dans vos propres projets.

- [Create GS1 Barcode Images in C# – How to Generate Barcode C# Quickly](/barcode/english/net/gs1-barcode-encoding/create-gs1-barcode-images-in-c-how-to-generate-barcode-c-qui/)
- [How to Generate and Adjust Barcode Height for One-Dimensional Databar using Aspose.BarCode for .NET](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-barcode-height-adjustment/)
- [How to Generate Barcode Image in C# – MicroPdf417 Guide](/barcode/english/net/compact-pdf417-encoding/how-to-generate-barcode-image-in-c-micropdf417-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}