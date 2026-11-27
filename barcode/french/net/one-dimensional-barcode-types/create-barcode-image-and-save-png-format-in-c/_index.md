---
category: general
date: 2026-11-27
description: Créer une image de code‑barres en C# et enregistrer l’image au format
  PNG avec Aspose.BarCode – guide étape par étape.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode image
- save image PNG format
- Aspose.BarCode C#
- Macro PDF417 barcode
- barcode generation .NET
language: fr
lastmod: 2026-11-27
og_description: Créer une image de code‑barres en C# et enregistrer l’image au format
  PNG à l’aide d’Aspose.BarCode. Suivez ce tutoriel pour générer un code‑barres Macro
  PDF417 étape par étape.
og_image_alt: Screenshot of a created barcode image saved as PNG
og_title: Créer une image de code-barres et enregistrer au format PNG en C# – guide
  complet
schemas:
- author: Aspose
  dateModified: '2026-11-27'
  description: Create barcode image in C# and save image PNG format with Aspose.BarCode
    – step‑by‑step guide.
  headline: Create barcode image and save PNG format in C#
  type: TechArticle
tags:
- barcode
- C#
- Aspose
title: Créer une image de code‑barres et l’enregistrer au format PNG en C#
url: /fr/net/one-dimensional-barcode-types/create-barcode-image-and-save-png-format-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Créer une image de code‑barres et l’enregistrer au format PNG en C#

Si vous devez **créer une image de code‑barres** dans une application .NET, ce guide vous montre comment générer un code‑barres Macro PDF417 et **enregistrer l’image au format PNG** à l’aide d’Aspose.BarCode. Vous obtiendrez un exemple complet, exécutable, ainsi qu’une explication de chaque paramètre afin de pouvoir adapter le code à vos propres besoins.

Générer un code‑barres ne se résume pas à appeler une seule méthode ; il faut configurer la taille du module, les paramètres macro et le format de sortie. À la fin de ce tutoriel, vous comprendrez pourquoi chaque propriété est importante, comment gérer les cas limites courants et comment vérifier que le fichier PNG a été correctement écrit.

## Ce dont vous aurez besoin

- .NET 6.0 ou version ultérieure (le code fonctionne également avec .NET Framework 4.6+)
- Aspose.BarCode for .NET (disponible via NuGet : `Install-Package Aspose.BarCode`)
- Un IDE tel que Visual Studio 2022 ou Visual Studio Code
- Permission d’écriture sur le dossier où le fichier PNG sera enregistré

## Étape 1 : Initialiser le générateur de code‑barres

La première étape consiste à créer une instance de `BarcodeGenerator` en spécifiant la symbologie `EncodeTypes.MacroPdf417` et le texte que vous souhaitez encoder.

```csharp
using Aspose.BarCode.Generation;

// Step 1: Initialize a Macro PDF417 barcode generator with the desired text
using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.MacroPdf417, "Sample text"))
{
    // Subsequent steps go here
}
```

**Pourquoi c’est important :**  
`EncodeTypes.MacroPdf417` indique à la bibliothèque d’utiliser la variante macro du PDF417, qui prend en charge la segmentation de fichier et des métadonnées supplémentaires. Le constructeur reçoit également le texte lisible par l’homme qui sera encodé dans le code‑barres.

## Étape 2 : Définir la taille du module (dimension X)

La dimension X contrôle la largeur d’un seul module du code‑barres (l’élément noir/blanc le plus petit). Une valeur de `2` pixels convient bien pour les PNG affichés à l’écran.

```csharp
    // Step 2: Define the module size (X‑dimension) in pixels
    generator.Parameters.Barcode.XDimension.Pixels = 2;
```

**Astuce pratique :**  
Si vous prévoyez d’imprimer le code‑barres, augmentez la valeur en pixels (par ex., `4` ou `5`) afin d’éviter un rendu flou sur les imprimantes à basse résolution.

## Étape 3 : Configurer les paramètres macro PDF417

Macro PDF417 ajoute plusieurs champs optionnels qui aident à identifier le fichier source, l’ordre des segments et les contrôles d’intégrité. Vous trouverez ci‑dessous un jeu complet de paramètres typiques ; vous pouvez omettre ceux dont vous n’avez pas besoin.

```csharp
    // Step 3: Set PDF417 macro parameters
    generator.Parameters.Barcode.Pdf417.Columns = 5;                     // Number of columns per row
    generator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;    // Unique file identifier
    generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;      // Current segment number
    generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20; // Total number of segments
    generator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01"; // Logical file name
    generator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234;     // CCITT‑16 checksum
    generator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400_000;  // Approximate file size in bytes
    generator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = new DateTime(2019, 11, 1);
    generator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
    generator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
    generator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;
```

**Pourquoi ces champs sont utiles :**  

| Paramètre | Objectif |
|-----------|----------|
| `Columns` | Contrôle la largeur du code‑barres ; moins de colonnes produisent un code‑barres plus haut. |
| `MacroPdf417FileID` | Identifiant unique qui lie tous les segments ensemble. |
| `MacroPdf417SegmentID` | Position de ce segment dans le fichier complet. |
| `MacroPdf417SegmentsCount` | Nombre total de segments ; requis pour la reconstruction. |
| `MacroPdf417FileName` | Nom lisible par l’homme qui peut être affiché par les applications de lecture. |
| `MacroPdf417Checksum` | Aide les récepteurs à vérifier l’intégrité des données (CCITT‑16). |
| `MacroPdf417FileSize` | Indice de taille optionnel pour le fichier original. |
| `MacroPdf417TimeStamp` | Horodatage de la création du fichier original. |
| `MacroPdf417Addressee` / `MacroPdf417Sender` | Métadonnées pour le routage ou la propriété. |
| `MacroPdf417Terminator` | Indique si c’est le segment final (`Set`) ou un segment intermédiaire (`Unset`). |

**Cas limite :** Si vous générez un code‑barres à segment unique, définissez `MacroPdf417SegmentsCount` à `1` et `MacroPdf417Terminator` à `Unset`. La bibliothèque omettra automatiquement les champs liés aux segments qui ne sont pas applicables.

## Étape 4 : Enregistrer le code‑barres généré sous forme d’image PNG

Enfin, appelez `Save` avec un chemin de fichier et la valeur d’énumération `BarCodeImageFormat.Png`. La méthode écrit l’image sur le disque au format PNG sans perte.

```csharp
    // Step 4: Save the generated barcode as a PNG image
    string outputPath = Path.Combine(Environment.CurrentDirectory, "ExtPDF417Meta.png");
    generator.Save(outputPath, BarCodeImageFormat.Png);
}
```

**Pourquoi le PNG ?**  
Le PNG conserve les valeurs exactes des pixels, ce qui est essentiel pour les lecteurs de code‑barres qui dépendent d’un contraste net. La compression JPEG peut introduire des artefacts qui cassent le motif du code‑barres.

### Vérification de la sortie

Après l’exécution du programme, vous devriez voir un fichier nommé `ExtPDF417Meta.png` dans le dossier d’exécution. L’ouvrir avec n’importe quel visualiseur d’images affichera un code‑barres rectangulaire dense. Vous pouvez vérifier la justesse en scannant l’image avec un lecteur mobile de code‑barres qui prend en charge le PDF417 macro ; l’application affichera généralement les métadonnées intégrées (ID du fichier, numéro de segment, etc.).

## Problèmes courants et comment les éviter

| Symptôme | Cause probable | Solution |
|----------|----------------|----------|
| Le code‑barres apparaît flou | Dimension X trop basse pour le DPI choisi | Augmentez `XDimension.Pixels` ou rendez à une résolution DPI supérieure (`generator.Parameters.ImageResolution`). |
| Le scanner signale « erreur de checksum » | Valeur `MacroPdf417Checksum` incorrecte | Laissez Aspose calculer automatiquement le checksum en omettant la propriété, ou assurez‑vous que la valeur correspond à l’algorithme CCITT‑16. |
| Le fichier PNG est vide ou n’est pas créé | Chemin de sortie invalide ou permission d’écriture manquante | Utilisez `Path.Combine` avec un dossier connu et accessible en écriture (par ex., `Environment.GetFolderPath(Environment.SpecialFolder.Desktop)`). |
| Les champs macro sont ignorés | `EncodeTypes` réglé sur le `Pdf417` standard au lieu de `MacroPdf417` | Vérifiez que `EncodeTypes.MacroPdf417` est utilisé dans le constructeur. |

## Exemple complet, exécutable

Voici le programme complet que vous pouvez copier dans une application console. Il compile avec .NET 6.0 et produit le fichier PNG décrit ci‑dessus.

```csharp
using System;
using System.IO;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Initialize a Macro PDF417 barcode generator with the desired text
        using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.MacroPdf417, "Sample text"))
        {
            // Define the module size (X-dimension) in pixels
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // Set PDF417 macro parameters
            generator.Parameters.Barcode.Pdf417.Columns = 5;
            generator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
            generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;
            generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;
            generator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";
            generator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234; // CCITT‑16 checksum
            generator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400_000;
            generator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = new DateTime(2019, 11, 1);
            generator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
            generator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
            generator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;

            // Save the generated barcode as a PNG image
            string outputPath = Path.Combine(Environment.CurrentDirectory, "ExtPDF417Meta.png");
            generator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"Barcode image saved to: {outputPath}");
        }
    }
}
```

**Sortie attendue (console) :**

```
Barcode image saved to: C:\YourProject\bin\Debug\net6.0\ExtPDF417Meta.png
```

L’ouverture de `ExtPDF417Meta.png` montre un code‑barres Macro PDF417 clair, prêt à être scanné.

## Étapes suivantes

- **Modifier le format d’image** – remplacez `BarCodeImageFormat.Png` par `Jpeg` ou `Bmp` si vous avez besoin d’un autre type de fichier. Gardez à l’esprit que le JPEG introduit des artefacts de compression, ce qui peut affecter la fiabilité du scan.
- **Ajuster la résolution** – utilisez

## Que devriez‑vous apprendre ensuite ?

Les tutoriels suivants couvrent des sujets étroitement liés qui s’appuient sur les techniques démontrées dans ce guide. Chaque ressource comprend des exemples de code complets et fonctionnels avec des explications pas à pas pour vous aider à maîtriser d’autres fonctionnalités de l’API et explorer des approches d’implémentation alternatives dans vos propres projets.

- [How to create barcode image with Aspose.Barcode in C#](/barcode/english/python-java/general/how-to-create-barcode-image-with-aspose-barcode-in-c/)
- [How to create PDF417 barcode image in C# with Macro PDF417 options](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-image-in-c-with-macro-pdf417-op/)
- [How to read barcodes from image using C# with Aspose.BarCode – step‑by‑step guide](/barcode/english/net/one-dimensional-barcode-types/how-to-read-barcodes-from-image-using-c-step-by-step-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}