---
category: general
date: 2026-09-22
description: Apprenez à créer un code‑barres PDF417 en C#, à définir la taille du
  code‑barres et à générer des fichiers d’image de code‑barres avec des exemples de
  code clairs, étape par étape.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create PDF417 barcode
- how to create PDF417
- set barcode size
- create barcode image c#
language: fr
lastmod: 2026-09-22
og_description: Créez un code‑barres PDF417 en C# rapidement. Ce tutoriel montre comment
  définir la taille du code‑barres, activer le mode compact et générer des images
  PNG pour tout projet .NET.
og_image_alt: Screenshot of a generated PDF417 barcode image created with C# code
og_title: Créer un code‑barres PDF417 en C# – guide étape par étape
schemas:
- author: Aspose
  dateModified: '2026-09-22'
  description: Learn how to create PDF417 barcode in C#, set barcode size, and generate
    barcode image files with clear step‑by‑step code examples.
  headline: How to create PDF417 barcode and set its size in C#
  type: TechArticle
tags:
- PDF417
- C#
- Barcode
- Imaging
title: Comment créer un code‑barres PDF417 et définir sa taille en C#
url: /fr/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-and-set-its-size-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Comment créer un code-barres PDF417 et définir sa taille en C#

Si vous devez **créer un code-barres PDF417** en C#, ce guide vous montre comment générer le code-barres, contrôler ses dimensions et enregistrer le résultat sous forme de fichier image. Que vous construisiez un système de billetterie, une étiquette logistique ou un justificatif sécurisé, maîtriser le format PDF417 vous permet d'encoder de grandes quantités de données sous une forme visuelle compacte.

Dans ce tutoriel vous apprendrez à :

* **Créer un code-barres PDF417** avec la bibliothèque Aspose.BarCode (ou toute bibliothèque compatible).  
* **Définir la taille du code-barres** en ajustant la X‑dimension et le nombre de colonnes.  
* Générer une **image de code-barres en C#** au format PNG, JPEG ou BMP.  

Cet exemple utilise l'édition communautaire gratuite d'Aspose.BarCode pour .NET, mais les mêmes concepts s'appliquent à d'autres bibliothèques exposant des propriétés similaires.

## Prérequis

Avant de commencer, assurez-vous d'avoir :

* Le SDK .NET 6.0 ou une version ultérieure installé.  
* Un IDE C# (Visual Studio, Visual Studio Code, Rider, etc.).  
* Le package NuGet `Aspose.BarCode` (`dotnet add package Aspose.BarCode`).  

Aucune configuration supplémentaire n'est requise ; la bibliothèque fonctionne sous Windows, Linux et macOS.

## Étape 1 : Créer un code-barres PDF417 de base et définir sa taille

La première étape consiste à instancier un `BarcodeGenerator` avec l'énumération `EncodeTypes.Pdf417` et à fournir le texte que vous souhaitez encoder. Ensuite, ajustez la **X‑dimension** (largeur du module) et le nombre de **colonnes** pour contrôler la taille globale.

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;

// Define the text that the barcode will represent.
string data = "Sample text for PDF417 barcode";

// Create a basic PDF417 barcode generator.
var basicPdf417 = new BarcodeGenerator(EncodeTypes.Pdf417, data);

// Set the module width to 2 pixels (controls bar thickness).
basicPdf417.Parameters.Barcode.XDimension.Pixels = 2;

// Set the column count; 3 columns yields a compact visual but still readable.
basicPdf417.Parameters.Barcode.Pdf417.Columns = 3;

// Save the barcode as a PNG image.
string basicPath = Path.Combine("YOUR_DIRECTORY", "Pdf417Basic.png");
basicPdf417.Save(basicPath, BarCodeImageFormat.Png);
```

**Pourquoi ces paramètres sont importants**

* `XDimension.Pixels` détermine la largeur de la barre la plus étroite. Des valeurs plus petites produisent un code-barres plus compact, tandis que des valeurs plus grandes augmentent la lisibilité sur les scanners basse résolution.  
* `Pdf417.Columns` influence le rapport d'aspect du code-barres. Moins de colonnes rendent le code-barres plus haut ; plus de colonnes l'aplatissent. Ajuster le nombre de colonnes est le principal moyen de **définir la taille du code-barres** sans modifier les données encodées.

Après avoir exécuté le code, vous trouverez `Pdf417Basic.png` dans le dossier spécifié. L'image ressemble à la capture d'écran ci‑dessous :

<img src="images/pdf417-basic.png" alt="create PDF417 barcode example showing basic barcode layout">

## Étape 2 : Créer un code-barres PDF417 compact (mode tronqué) avec la même taille

Parfois, vous avez besoin d'un code-barres plus court pour un espace limité. PDF417 propose un mode *truncate* (compact) qui supprime le motif d'arrêt et réduit la hauteur globale. La propriété `Truncate` active ce comportement.

```csharp
// Reuse the same data string.
var compactPdf417 = new BarcodeGenerator(EncodeTypes.Pdf417, data);

// Keep the same module width and column count for a fair size comparison.
compactPdf417.Parameters.Barcode.XDimension.Pixels = 2;
compactPdf417.Parameters.Barcode.Pdf417.Columns = 3;

// Enable compact (truncate) mode – this removes the stop pattern.
compactPdf417.Parameters.Barcode.Pdf417.Truncate = true;

// Save the compact version.
string compactPath = Path.Combine("YOUR_DIRECTORY", "CompactPdf417.png");
compactPdf417.Save(compactPath, BarCodeImageFormat.Png);
```

**Qu'est-ce qui change avec `Truncate = true` ?**

* Le code-barres devient environ 15‑20 % plus court verticalement, ce qui est utile pour les petites étiquettes ou les écrans mobiles.  
* Les données restent entièrement récupérables ; la plupart des scanners modernes comprennent automatiquement le mode tronqué.

Le fichier `CompactPdf417.png` résultant apparaît comme une version plus fine du code-barres de base.

## Étape 3 : Créer un code-barres Micro PDF417, ajuster les colonnes et l'enregistrer

Micro PDF417 est une variante plus récente, à haute densité, conçue pour des espaces très petits (par ex., les cartes d'identité). Elle ne prend en charge que 1‑4 colonnes, et la bibliothèque expose la même propriété `XDimension` pour le contrôle de la taille.

```csharp
// Create a Micro PDF417 generator.
var microPdf417 = new BarcodeGenerator(EncodeTypes.MicroPdf417, data);

// Set module width – 2 pixels works well for most printers.
microPdf417.Parameters.Barcode.XDimension.Pixels = 2;

// Micro PDF417 allows only 1 to 4 columns; choose 4 for a more square shape.
microPdf417.Parameters.Barcode.Pdf417.Columns = 4;

// Save the micro barcode.
string microPath = Path.Combine("YOUR_DIRECTORY", "MicroPdf417.png");
microPdf417.Save(microPath, BarCodeImageFormat.Png);
```

**Points clés pour Micro PDF417**

* L'énumération `EncodeTypes.MicroPdf417` sélectionne automatiquement la variante micro.  
* Parce que le symbole est plus dense, vous pouvez avoir besoin d'une imprimante à plus haute résolution DPI (300 dpi ou plus) pour que le code-barres reste lisible.  
* Ajuster le nombre de colonnes est le seul réglage de taille disponible ; la bibliothèque respecte toujours `XDimension`.

## Comment définir la taille du code-barres pour différents formats de sortie

Les exemples ci‑dessus utilisent le PNG, mais la même méthode `Save` fonctionne avec JPEG, BMP ou TIFF. Si vous avez besoin d'une dimension d'image spécifique (par ex., 300 × 150 px), combinez `XDimension` avec `ResolutionX`/`ResolutionY` :

```csharp
basicPdf417.Parameters.ImageResolution = 300; // DPI
basicPdf417.Parameters.Barcode.XDimension.Pixels = 3; // larger modules for higher DPI
basicPdf417.Save("Pdf417HighRes.jpg", BarCodeImageFormat.Jpeg);
```

Augmenter `ImageResolution` tout en ajustant `XDimension` préserve la qualité visuelle sur les impressions haute résolution.

## Pièges courants et astuces professionnelles

| Problème | Pourquoi cela se produit | Solution |
|----------|--------------------------|----------|
| Le code-barres apparaît flou à l'écran | Faible DPI combiné à une petite `XDimension` | Augmenter `ImageResolution` et/ou `XDimension.Pixels` |
| Le scanner ne peut pas lire le mode tronqué | Le firmware du scanner est trop ancien et ne le supporte pas | Utiliser le mode complet (non tronqué) pour le matériel hérité |
| Micro PDF417 illisible | Imprimé à < 300 dpi ou avec un contraste insuffisant | Imprimer sur papier mat à 300 dpi ou plus, assurer un premier plan sombre |
| Le fichier de sortie est corrompu | Permission d'écriture manquante sur le dossier cible | Vérifier que `YOUR_DIRECTORY` existe et est accessible en écriture |

**Astuce :** Générez toujours le code-barres au format PNG lorsque vous avez besoin d'une qualité sans perte pour un traitement ultérieur (par ex., l'intégration dans des PDF). Le PNG conserve les valeurs de pixels exactes, tandis que le JPEG introduit des artefacts de compression qui peuvent affecter la lisibilité du code-barres.

## Exemple complet et exécutable

Voici une application console complète qui démontre les trois types de code-barres en une seule exécution. Copiez le code dans un nouveau projet console .NET et exécutez-le.

```csharp
using System;
using System.IO;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // The text to encode – change this to whatever data you need.
        const string data = "Sample text for PDF417 barcode";

        // Directory where images will be saved.
        string outputDir = Path.Combine(Environment.CurrentDirectory, "Barcodes");
        Directory.CreateDirectory(outputDir);

        // ---------- Basic PDF417 ----------
        var basicPdf417 = new BarcodeGenerator(EncodeTypes.Pdf417, data);
        basicPdf417.Parameters.Barcode.XDimension.Pixels = 2;
        basicPdf417.Parameters.Barcode.Pdf417.Columns = 3;
        string basicPath = Path.Combine(outputDir, "Pdf417Basic.png");
        basicPdf417.Save(basicPath, BarCodeImageFormat.Png);
        Console.WriteLine($"Basic PDF417 saved to {basicPath}");

        // ---------- Compact (Truncate) PDF417 ----------
        var compactPdf417 = new BarcodeGenerator(EncodeTypes.Pdf417, data);
        compactPdf417.Parameters.Barcode.XDimension.Pixels = 2;
        compactPdf417.Parameters.Barcode.Pdf417.Columns = 3;
        compactPdf417.Parameters.Barcode.Pdf417.Truncate = true;
        string compactPath = Path.Combine(outputDir, "CompactPdf417.png");
        compactPdf417.Save(compactPath, BarCodeImageFormat.Png);
        Console.WriteLine($"Compact PDF417 saved to {compactPath}");

        // ---------- Micro PDF417 ----------
        var microPdf417 = new BarcodeGenerator(EncodeTypes.MicroPdf417, data);
        microPdf417.Parameters.Barcode.XDimension.Pixels = 2;
        microPdf417.Parameters.Barcode.Pdf417.Columns = 4; // 1‑4 allowed
        string microPath = Path.Combine(outputDir, "MicroPdf417.png");
        microPdf417.Save(microPath, BarCodeImageFormat.Png);
        Console.WriteLine($"Micro PDF417 saved to {microPath}");
    }
}
```

**Sortie attendue**

L'exécution du programme crée trois fichiers PNG dans un dossier `Barcodes` :

* `Pdf417Basic.png` – un code-barres PDF417 standard avec trois colonnes.  
* `CompactPdf417.png` – les mêmes données en mode tronqué (compact), légèrement plus court.  
* `MicroPdf417.png` – une variante Micro PDF417 à haute densité avec quatre colonnes.

Ouvrez n'importe quelle image avec un visualiseur d'images ; vous devriez voir la disposition empilée distinctive

## Que devez‑vous apprendre ensuite ?

Les tutoriels suivants couvrent des sujets étroitement liés qui s'appuient sur les techniques démontrées dans ce guide. Chaque ressource comprend des exemples de code complets et fonctionnels avec des explications étape par étape pour vous aider à maîtriser des fonctionnalités API supplémentaires et explorer des approches d'implémentation alternatives dans vos propres projets.

- [Comment créer un code-barres – PDF417 compact avec Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [Comment définir le niveau d'erreur dans le code-barres PDF417 – Guide complet](/barcode/english/net/compact-pdf417-encoding/how-to-set-error-level-in-pdf417-barcode-complete-guide/)
- [Créer les métadonnées du code-barres PDF417 en C# – Guide complet étape par étape](/barcode/english/net/compact-pdf417-encoding/create-pdf417-barcode-metadata-in-c-complete-step-by-step-gu/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}