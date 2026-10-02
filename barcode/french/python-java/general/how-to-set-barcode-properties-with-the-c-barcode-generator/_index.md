---
category: general
date: 2026-09-10
description: Comment définir un code‑barres en C# à l'aide d'un générateur de code‑barres.
  Ajustez la largeur du module du code‑barres, générez des images de code‑barres et
  apprenez comment enregistrer les fichiers de code‑barres.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to set barcode
- c# barcode generator
- barcode module width
- how to generate barcode
- how to save barcode
language: fr
lastmod: 2026-09-10
og_description: Comment configurer un code‑barres en C# avec un générateur de code‑barres.
  Apprenez à ajuster la largeur du module, générer un code‑barres et enregistrer l’image
  du code‑barres efficacement.
og_image_alt: Screenshot showing a Planet barcode with filled and empty bars generated
  by C# code
og_title: Comment définir les propriétés du code‑barres avec le générateur de code‑barres
  C#
schemas:
- author: Aspose
  dateModified: '2026-09-10'
  description: How to set barcode in C# using a Barcode Generator. Adjust barcode
    module width, generate barcode images, and learn how to save barcode files.
  headline: How to set barcode properties with the C# Barcode Generator
  type: TechArticle
tags:
- barcode
- c#
- image generation
title: Comment définir les propriétés du code-barres avec le générateur de codes-barres
  C#
url: /fr/python-java/general/how-to-set-barcode-properties-with-the-c-barcode-generator/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Comment définir les propriétés du code-barres avec le générateur de code-barres C#

Définir les propriétés d'un code-barres est essentiel lorsque vous avez besoin d'un contrôle précis sur le style visuel d'un code-barres. Ce guide vous montre comment générer un code-barres Planet, ajuster la largeur du module du code-barres et enregistrer l'image du code-barres à l'aide du générateur de code-barres C#.

Vous verrez un exemple complet et exécutable qui couvre chaque étape, de la création de l'objet code-barres à l'écriture des fichiers PNG sur le disque. Aucune documentation externe n'est requise — uniquement le code ci‑dessous et la bibliothèque Aspose.BarCode (ou tout SDK de code-barres compatible). À la fin du tutoriel, vous pourrez répondre à des questions telles que « comment générer un code-barres avec des dimensions personnalisées ? » et « comment enregistrer un code-barres dans différents formats ? ».

## Prérequis

Avant de commencer, assurez‑vous d'avoir :

* .NET 6.0 ou version ultérieure installé  
* Visual Studio 2022 (ou tout IDE C#)  
* Le package NuGet **Aspose.BarCode** (ou une autre bibliothèque qui fournit `BarcodeGenerator`)  

Vous pouvez ajouter le package avec la commande suivante :

```bash
dotnet add package Aspose.BarCode
```

## Comment définir la largeur du module du code-barres

La *largeur du module* (également appelée X‑dimension) détermine la taille en pixels de chaque barre étroite du code-barres. Définir cette valeur vous permet de contrôler la taille globale et la lisibilité de l'image.

```csharp
// Create a barcode generator for the Planet symbology
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(EncodeTypes.Planet, "123456");

// Set the module width to 4 pixels
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 4;
```

*Pourquoi c'est important* : une X‑dimension plus grande produit un code-barres plus gros, plus facile à lire pour les scanners à distance, tandis qu'une valeur plus petite réduit la taille du fichier pour le rendu à l'écran.

## Génération d'un code-barres avec des barres pleines

Le style par défaut du code-barres Planet utilise des **barres pleines** (barres noires solides). Le code suivant crée l'image et l'enregistre au format PNG.

```csharp
// Save the barcode with filled bars
barcodeGenerator.Save("YOUR_DIRECTORY/PostalPlanetFilledBars.png", BarCodeImageFormat.Png);
```

> **Résultat** : `PostalPlanetFilledBars.png` contient un code-barres Planet standard où chaque barre est remplie.

## Création d'un code-barres à barres vides

Parfois, vous avez besoin d'un code-barres qui n'affiche que les contours des barres (barres vides). Pour ce faire, vous dupliquez le générateur, conservez la même largeur de module et désactivez le drapeau `FilledBars`.

```csharp
// Duplicate the generator for an empty‑bar version
BarcodeGenerator emptyBarGenerator = new BarcodeGenerator(EncodeTypes.Planet, "123456");

// Apply the same X‑dimension
emptyBarGenerator.Parameters.Barcode.XDimension.Pixels = 4;

// Disable filled bars so only the outlines are drawn
emptyBarGenerator.Parameters.Barcode.FilledBars = false;

// Save the empty‑bar barcode
emptyBarGenerator.Save("YOUR_DIRECTORY/PostalPlanetEmptyBars.png", BarCodeImageFormat.Png);
```

> **Résultat** : `PostalPlanetEmptyBars.png` affiche les mêmes données mais avec des barres non remplies, utile pour les documents très graphiques où vous souhaitez que le code-barres se fonde dans le fond.

## Comment enregistrer le code-barres dans différents formats

La méthode `Save` accepte tout format pris en charge par le SDK, tel que **Jpeg**, **Bmp**, **Gif** ou **Svg**. Modifier le format ne nécessite que de remplacer la valeur de l'énumération `BarCodeImageFormat`.

```csharp
// Example: save as SVG for lossless scaling
barcodeGenerator.Save("YOUR_DIRECTORY/PostalPlanet.svg", BarCodeImageFormat.Svg);
```

*Astuce* : utilisez le SVG lorsque vous avez besoin d'un graphique vectoriel qui s'adapte sans pixellisation, notamment pour les PDF prêts à l'impression.

## Exemple complet et exécutable

Assembler toutes les pièces vous donne un programme autonome que vous pouvez coller dans une application console.

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // 1. Create a filled‑bar Planet barcode
        BarcodeGenerator filledGenerator = new BarcodeGenerator(EncodeTypes.Planet, "123456");
        filledGenerator.Parameters.Barcode.XDimension.Pixels = 4; // barcode module width
        filledGenerator.Save("PostalPlanetFilledBars.png", BarCodeImageFormat.Png);

        // 2. Create an empty‑bar version of the same barcode
        BarcodeGenerator emptyGenerator = new BarcodeGenerator(EncodeTypes.Planet, "123456");
        emptyGenerator.Parameters.Barcode.XDimension.Pixels = 4; // same module width
        emptyGenerator.Parameters.Barcode.FilledBars = false;   // how to set barcode to empty bars
        emptyGenerator.Save("PostalPlanetEmptyBars.png", BarCodeImageFormat.Png);

        // 3. Optional: save as SVG for scalable use
        filledGenerator.Save("PostalPlanet.svg", BarCodeImageFormat.Svg);
    }
}
```

**Sortie attendue**

| Nom du fichier                | Description                              |
|-------------------------------|------------------------------------------|
| `PostalPlanetFilledBars.png`  | Code-barres Planet avec des barres noires solides |
| `PostalPlanetEmptyBars.png`   | Même donnée, barres affichées sous forme de contours |
| `PostalPlanet.svg`            | Version vectorielle pour un redimensionnement sans perte |

Exécutez le programme, ouvrez les fichiers générés et vérifiez que les codes-barres correspondent à la chaîne numérique « 123456 ».

## Variations courantes et cas limites

| Situation                               | Ajustement                                                                 |
|----------------------------------------|---------------------------------------------------------------------------|
| Besoin d'un code-barres plus épais                 | Augmenter `XDimension.Pixels` (par ex., `8`)                                   |
| Souhait d'une taille de fichier plus petite               | Utiliser `BarCodeImageFormat.Jpeg` ou diminuer la X‑dimension                    |
| Générer d'autres symbologies           | Remplacer `EncodeTypes.Planet` par `EncodeTypes.Code128`, `QR`, etc.       |
| Impression sur des imprimantes haute résolution   | Enregistrer sous `BarCodeImageFormat.Tiff` pour une sortie raster sans perte              |
| Exécution sur un serveur sans interface graphique           | Aucun code UI requis ; le générateur fonctionne dans un contexte console ou service  |

**Astuce pro** : Validez toujours le code-barres généré avec un scanner ou un outil de vérification avant de le déployer en production. Une largeur de module ou un format incorrect peut entraîner des échecs de lecture.

## Conclusion

Vous savez maintenant comment définir les propriétés d'un code-barres à l'aide du générateur de code-barres C#, comment contrôler la largeur du module du code-barres, comment générer à la fois des styles de barres pleines et vides, et comment enregistrer le code-barres aux formats PNG ou SVG. Ces étapes vous offrent une base solide pour ajouter la création de code-barres à toute application .NET.

Ensuite, explorez des sujets connexes tels que **c# barcode generator performance tuning**, **embedding barcodes in PDF documents**, et **creating QR codes with custom colors**. Expérimentez avec différents `EncodeTypes` et formats d'image pour trouver la meilleure solution pour votre projet.

## Que devriez‑vous apprendre ensuite ?

Les tutoriels suivants couvrent des sujets étroitement liés qui s'appuient sur les techniques démontrées dans ce guide. Chaque ressource comprend des exemples de code complets et fonctionnels avec des explications étape par étape pour vous aider à maîtriser des fonctionnalités supplémentaires de l'API et explorer des approches d'implémentation alternatives dans vos propres projets.

- [Comment enregistrer un code-barres en C# – Générer des codes-barres PDF417](/barcode/english/net/compact-pdf417-encoding/how-to-save-barcode-in-c-generate-pdf417-barcodes/)
- [Tutoriel du générateur de code-barres : comment générer un code-barres PDF417 en C#](/barcode/english/net/compact-pdf417-encoding/barcode-generator-tutorial-how-to-generate-pdf417-barcode-in/)
- [Comment définir le niveau d’erreur dans le code-barres PDF417 – Guide complet](/barcode/english/net/compact-pdf417-encoding/how-to-set-error-level-in-pdf417-barcode-complete-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}