---
category: general
date: 2026-09-29
description: Créer un code‑barres GS1 en C# et générer des images PNG de code‑barres
  à l’aide de BarcodeGenerator. Suivez un guide étape par étape pour exporter l’image
  du code‑barres efficacement.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode gs1
- generate barcode png
- barcode generator c#
- how to generate barcode
- export barcode image
language: fr
lastmod: 2026-09-29
og_description: Créez un code‑barres GS1 en C# et générez des fichiers PNG de code‑barres
  avec BarcodeGenerator. Suivez ce guide complet pour exporter rapidement l’image
  du code‑barres.
og_image_alt: Generated GS1 MicroPDF417 barcode saved as a PNG file
og_title: Créer un code‑barres GS1 en C# – exporter en PNG en quelques minutes
schemas:
- author: Aspose
  dateModified: '2026-09-29'
  description: Create barcode GS1 in C# and generate barcode PNG images using BarcodeGenerator.
    Follow a step‑by‑step guide to export barcode image efficiently.
  headline: Create barcode GS1 in C# and export it as PNG
  type: TechArticle
tags:
- barcode
- C#
- GS1
- PNG
- Aspose
title: Créer un code‑barres GS1 en C# et l’exporter au format PNG
url: /fr/net/gs1-barcode-encoding/create-barcode-gs1-in-c-and-export-it-as-png/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Créer un code‑barcode GS1 en C# et l’exporter en PNG

Si vous devez **créer un code‑barcode GS1** dans une application .NET, ce guide vous montre exactement comment le faire. Vous verrez une solution concise qui génère une image PNG de code‑barcode et exporte l’image du code‑barcode sur le disque, le tout avec la classe `BarcodeGenerator` d’Aspose.BarCode.

Générer un code‑barcode GS1 est une exigence courante pour les systèmes d’inventaire, d’expédition et de point de vente. À la fin de ce tutoriel, vous serez capable d’écrire un petit programme C# qui crée un code‑barcode MicroPDF417 conforme à GS1 et le sauvegarde sous forme de fichier PNG de haute qualité.

## Prérequis

Avant de commencer, assurez‑vous d’avoir :

* **.NET 6** (ou toute version .NET ultérieure) installé.
* **Visual Studio 2022** ou tout IDE supportant C#.
* Le package NuGet **Aspose.BarCode for .NET** (`Aspose.BarCode`) – il fournit l’API `BarcodeGenerator` utilisée dans les exemples.
* Une connaissance de base de la syntaxe C#.

> **Astuce :** Utilisez l’édition communautaire gratuite d’Aspose.BarCode lors de vos expérimentations ; la version complète supprime tous les filigranes d’évaluation.

## Étape 1 – Créer un code‑barcode GS1 avec BarcodeGenerator

La première chose à faire est d’instancier le `BarcodeGenerator` pour le format *MicroPDF417* et de lui fournir une chaîne de données GS1. Les Identifiants d’Application GS1 (AI) sont entourés de parenthèses, par ex. `(01)` pour GTIN‑14 et `(21)` pour un numéro de série.

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;

// GS1 data: (01) – GTIN‑14, (21) – serial number
string gs1Data = "(01)12345678901234(21)ABC123";

// Initialise the generator for MicroPDF417 (GS1 compatible)
BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.MicroPdf417, gs1Data);
```

**Pourquoi c’est important :**  
`EncodeTypes.MicroPdf417` traite automatiquement l’entrée comme des données GS1 lorsque la chaîne contient des AI valides. Cela garantit que le code‑barcode généré respecte la spécification GS1 sans configuration supplémentaire.

## Étape 2 – Définir les dimensions du code‑barcode pour une taille optimale

La taille visuelle d’un code‑barcode est contrôlée par sa **X‑dimension** (la largeur d’un module unique). Ajuster `XDimension.Pixels` vous permet d’affiner la taille finale de l’image tout en préservant la lisibilité.

```csharp
// Set the module width to 2 pixels – a good balance for screen and print
generator.Parameters.Barcode.XDimension.Pixels = 2;
```

> **Comment générer un PNG de code‑barcode** – La X‑dimension n’affecte pas les données encodées ; elle ne change que les dimensions physiques de l’image générée. Si vous avez besoin d’un code‑barcode plus grand pour une impression haute résolution, augmentez cette valeur (par ex., `3` ou `4`).

## Étape 3 – Générer le PNG du code‑barcode et exporter l’image du code‑barcode

Vous pouvez maintenant rendre le code‑barcode et l’écrire dans un fichier PNG. La méthode `Save` prend le chemin cible et le format d’image souhaité.

```csharp
// Define the output folder (ensure it exists)
string outputFolder = Path.Combine(Environment.CurrentDirectory, "output");
Directory.CreateDirectory(outputFolder);

// Export the barcode image as PNG
string pngPath = Path.Combine(outputFolder, "GS1MicroPdf417.png");
generator.Save(pngPath, BarCodeImageFormat.Png);

Console.WriteLine($"Barcode image saved to: {pngPath}");
```

**Ce qui se passe en coulisses :**  
`BarcodeGenerator.Save` rasterise le code‑barcode en un bitmap, applique la X‑dimension que vous avez définie précédemment, et encode le bitmap en fichier PNG. Le fichier résultant peut être utilisé directement dans des pages web, imprimé sur des étiquettes ou intégré dans des PDF.

## Exemple complet de code source

Voici une application console complète et autonome que vous pouvez copier, coller et exécuter. Elle montre **comment générer des PNG de code‑barcode**, **exporter l’image du code‑barcode**, et inclut une gestion d’erreurs basique.

```csharp
using System;
using System.IO;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace Gs1BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            try
            {
                // 1️⃣ Initialise the barcode generator for GS1 MicroPDF417
                string gs1Data = "(01)12345678901234(21)ABC123";
                BarcodeGenerator generator = new BarcodeGenerator(
                    EncodeTypes.MicroPdf417, gs1Data);

                // 2️⃣ Adjust X‑dimension to control the visual size
                generator.Parameters.Barcode.XDimension.Pixels = 2;

                // 3️⃣ Prepare output folder
                string outputFolder = Path.Combine(
                    Environment.CurrentDirectory, "output");
                Directory.CreateDirectory(outputFolder);

                // 4️⃣ Save the barcode as PNG (export barcode image)
                string pngPath = Path.Combine(outputFolder, "GS1MicroPdf417.png");
                generator.Save(pngPath, BarCodeImageFormat.Png);

                Console.WriteLine($"✅ Barcode created and saved as PNG:");
                Console.WriteLine(pngPath);
            }
            catch (Exception ex)
            {
                Console.Error.WriteLine($"Error: {ex.Message}");
            }
        }
    }
}
```

### Résultat attendu

Lorsque vous exécutez le programme, vous devriez voir :

```
✅ Barcode created and saved as PNG:
C:\Path\To\Your\App\output\GS1MicroPdf417.png
```

L’ouverture du fichier PNG affiche un code‑barcode **GS1 MicroPDF417** clair qui encode le GTIN‑14 `12345678901234` et le numéro de série `ABC123`. Le scanner GS1‑compatible le lira et renverra la chaîne de données d’origine.

## Pièges courants et bonnes pratiques

| Problème | Pourquoi cela se produit | Comment l'éviter |
|----------|--------------------------|-------------------|
| **Mauvais format d’AI** | Parenthèses manquantes ou ordre incorrect rend le code‑barcode non‑GS1. | Entourez toujours chaque AI de parenthèses, par ex., `(01)`. |
| **X‑dimension trop petite** | Le code‑barcode devient illisible sur des appareils à faible résolution. | Gardez `XDimension.Pixels` ≥ 2 pour la plupart des imprimantes ; augmentez pour une sortie haute DPI. |
| **Le dossier de sortie n’existe pas** | `Save` lève `DirectoryNotFoundException`. | Utilisez `Directory.CreateDirectory` avant d’appeler `Save`. |
| **Mauvais EncodeType** | Certains types (ex. `Code128`) ne supportent pas les données GS1 nativement. | Choisissez `EncodeTypes.MicroPdf417` ou tout type compatible GS1. |
| **Référence NuGet manquante** | Erreurs de compilation comme `The type or namespace name 'Aspose' could not be found`. | Installez le package `Aspose.BarCode` via NuGet. |

## Étendre l'exemple

* **Formats d’image différents** – Remplacez `BarCodeImageFormat.Png` par `Jpeg`, `Gif` ou `Bmp` si vous avez besoin d’un autre format.  
* **Sortie haute résolution** – Définissez `generator.Parameters.ImageResolution.DpiX` et `DpiY` avant de sauvegarder.  
* **Intégration dans un PDF** – Utilisez `Aspose.Pdf` pour placer le PNG dans une facture ou une étiquette PDF.  

## Conclusion

Vous savez maintenant comment **créer un code‑barcode GS1** en C# avec `BarcodeGenerator` d’Aspose.BarCode, **générer un PNG de code‑barcode**, et **exporter l’image du code‑barcode** sur le système de fichiers. Le guide a couvert chaque étape — de l’initialisation du générateur avec les données GS1, le réglage de la X‑dimension, jusqu’à l’enregistrement du fichier PNG final — tout en abordant les erreurs courantes et en proposant des idées d’extension.

N’hésitez pas à expérimenter avec d’autres Identifiants d’Application GS1, différentes symbologies de code‑barcode ou des images à plus haute résolution. Une fois ces bases maîtrisées, la génération de codes‑barcode conformes pour l’inventaire, l’expédition ou le commerce de détail devient une tâche routinière de votre boîte à outils .NET.

## Que devriez‑vous apprendre ensuite ?

Les tutoriels suivants couvrent des sujets étroitement liés qui s’appuient sur les techniques démontrées dans ce guide. Chaque ressource inclut des exemples de code complets avec des explications pas à pas pour vous aider à maîtriser des fonctionnalités API supplémentaires et explorer des approches d’implémentation alternatives dans vos propres projets.

- [Créer des images de code‑barcode GS1 en C# – Comment générer rapidement un code‑barcode C#](/barcode/english/net/gs1-barcode-encoding/create-gs1-barcode-images-in-c-how-to-generate-barcode-c-qui/)
- [Créer un PNG de code‑barcode en C# – guide pas à pas](/barcode/english/python-java/general/create-barcode-png-in-c-step-by-step-guide/)
- [Créer une image de code‑barcode en C# – guide complet de programmation](/barcode/english/python-java/general/create-barcode-image-in-c-complete-programming-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}