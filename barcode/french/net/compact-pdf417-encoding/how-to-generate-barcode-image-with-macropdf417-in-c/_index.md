---
category: general
date: 2026-11-23
description: Apprenez à générer une image de code‑barres en utilisant Aspose.BarCode
  pour .NET avec les métadonnées MacroPdf417 en C#. Suivez le guide complet étape
  par étape.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to generate barcode image
- MacroPdf417 barcode
- Aspose.BarCode for .NET
- set barcode metadata
- barcode image format
- C# barcode generation
language: fr
lastmod: 2026-11-23
og_description: Comment générer une image de code-barres avec Aspose.BarCode pour
  .NET. Ce tutoriel montre la configuration des métadonnées MacroPdf417 et la génération
  de code-barres en C#.
og_image_alt: Barcode image generated with MacroPdf417 using C#
og_title: Comment générer une image de code-barres avec MacroPdf417 en C#
schemas:
- author: Aspose
  dateModified: '2026-11-23'
  description: Learn how to generate barcode image using Aspose.BarCode for .NET with
    MacroPdf417 metadata in C#. Follow the complete step‑by‑step guide.
  headline: How to generate barcode image with MacroPdf417 in C#
  type: TechArticle
- description: Learn how to generate barcode image using Aspose.BarCode for .NET with
    MacroPdf417 metadata in C#. Follow the complete step‑by‑step guide.
  name: How to generate barcode image with MacroPdf417 in C#
  steps:
  - name: Open a terminal or the Package Manager Console in Visual Studio.
    text: Open a terminal or the Package Manager Console in Visual Studio.
  - name: 'Run the following command:'
    text: 'Run the following command:'
  - name: '**Visual inspection** – The barcode should display a series of stacked
      columns with a quiet zone (white margin) around it.'
    text: '**Visual inspection** – The barcode should display a series of stacked
      columns with a quiet zone (white margin) around it.'
  - name: '**Decoding test** – Use a barcode scanner app or the Aspose.BarCode `BarCodeReader`
      class to read the image back and confirm that all metadata fields are correctly
      embedded.'
    text: '**Decoding test** – Use a barcode scanner app or the Aspose.BarCode `BarCodeReader`
      class to read the image back and confirm that all metadata fields are correctly
      embedded.'
  type: HowTo
tags:
- barcode
- C#
- Aspose
- PDF417
title: Comment générer une image de code‑barres avec MacroPdf417 en C#
url: /fr/net/compact-pdf417-encoding/how-to-generate-barcode-image-with-macropdf417-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Comment générer une image de code-barres avec MacroPdf417 en C#

Si vous devez **générer une image de code-barres** dans une application .NET, ce guide vous montre exactement comment le faire avec **Aspose.BarCode for .NET**. Nous parcourrons la création d'un **code-barres MacroPdf417**, la configuration de ses métadonnées, et l'enregistrement du résultat sous forme de fichier PNG.

Ce tutoriel couvre tout, de l'installation de la bibliothèque à l'écriture d'un programme console complet et exécutable. À la fin, vous disposerez d'un exemple de code prêt à l'emploi qui produit une image de code-barres de haute qualité, et vous comprendrez comment **définir les métadonnées du code-barres**, choisir un **format d'image de code-barres**, et résoudre les problèmes courants. Aucune expérience préalable avec Aspose n'est requise—seules des connaissances de base en C# sont nécessaires.

## Installer Aspose.BarCode pour .NET

Avant de pouvoir **générer une image de code-barres**, vous avez besoin du package NuGet Aspose.BarCode.

1. Ouvrez un terminal ou la console du gestionnaire de packages dans Visual Studio.  
2. Exécutez la commande suivante :

```bash
dotnet add package Aspose.BarCode
```

Le package ajoute l'espace de noms `Aspose.BarCode.Generation`, qui contient la classe `BarcodeGenerator` utilisée pour **la génération de code-barres en C#**.

> **Astuce :** Utilisez la dernière version stable (en novembre 2026, la version actuelle est 24.11) pour bénéficier des dernières fonctionnalités et corrections de bugs.

## Créer l'instance BarcodeGenerator

La première étape de code crée un `BarcodeGenerator` configuré pour le type de **code-barres MacroPdf417** et fournit la chaîne de données que vous souhaitez encoder.

```csharp
using System;
using Aspose.BarCode.Generation;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // Step 1: Create a BarcodeGenerator for MacroPdf417 with the desired text
            using (BarcodeGenerator barcodeGenerator =
                   new BarcodeGenerator(EncodeTypes.MacroPdf417, "Åspóse.Barcóde©"))
            {
                // Subsequent configuration goes here...
```

Le bloc `using` garantit que le générateur est correctement éliminé, libérant toutes les ressources non gérées.

## Configurer l'apparence de base

Un code-barres lisible commence par des dimensions sensées. Ici, nous définissons la largeur en pixels de chaque module (`XDimension`) et le nombre de colonnes pour la matrice PDF417.

```csharp
                // Step 2: Set basic barcode appearance
                barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;   // pixel width of a module
                barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 5;    // number of columns
```

*Pourquoi ces valeurs ?*  
- **XDimension** contrôle l'épaisseur de chaque barre ; 2 pixels fonctionnent bien pour l'affichage à l'écran et la plupart des imprimantes.  
- **Columns** affecte la largeur globale ; un petit nombre de colonnes garde le code-barres compact tout en préservant la capacité de correction d'erreurs.

## Définir les métadonnées du code-barres (spécifique à MacroPdf417)

MacroPdf417 vous permet d'intégrer des informations au niveau du fichier directement dans le code-barres. C'est ici que vous **définissez les métadonnées du code-barres** telles que l'ID du fichier, l'ID du segment et les horodatages.

```csharp
                // Step 3: Configure MacroPdf417 specific metadata
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234; // CCITT‑16 example
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400000;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = new DateTime(2019, 11, 1);
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;
```

### Ce que signifie chaque propriété

| Propriété | Objectif |
|----------|----------|
| **MacroPdf417FileID** | Identifiant unique du fichier logique auquel appartient le code-barres. |
| **MacroPdf417SegmentID** | Indice du segment actuel (à partir de 0). |
| **MacroPdf417SegmentsCount** | Nombre total de segments qui composent le fichier complet. |
| **MacroPdf417FileName** | Nom lisible par l'homme du fichier source. |
| **MacroPdf417Checksum** | Somme de contrôle CCITT‑16 facultative pour la vérification de l'intégrité des données. |
| **MacroPdf417FileSize** | Taille attendue du fichier original en octets. |
| **MacroPdf417TimeStamp** | Date et heure de génération du code-barres – utile pour le suivi des versions. |
| **MacroPdf417Addressee / Sender** | Chaînes personnalisées pouvant contenir des informations d'acheminement. |
| **MacroPdf417Terminator** | Indique si ce segment est le dernier (`Set`) ou non (`Unset`). |

> **Cas limite :** Si vous prévoyez de diviser un gros document en plusieurs segments, maintenez le `SegmentsCount` cohérent sur tous les codes-barres générés. Des comptes incohérents entraîneront des échecs de décodage.

## Choisir le format d'image du code-barres et enregistrer

Aspose prend en charge de nombreux **formats d'image de code-barres** (PNG, JPEG, BMP, TIFF, etc.). PNG est sans perte et fonctionne bien pour la plupart des scénarios web et impression.

```csharp
                // Step 4: Save the generated barcode image
                string outputPath = @"YOUR_DIRECTORY/ExtPDF417Meta.png";
                barcodeGenerator.Save(outputPath, BarCodeImageFormat.Png);
                Console.WriteLine($"Barcode image saved to: {outputPath}");
            } // end using
        }
    }
}
```

Remplacez `YOUR_DIRECTORY` par un dossier absolu ou relatif où l'application possède les droits d'écriture.

Lorsque le programme s'exécute, vous devriez voir un message console confirmant l'emplacement du fichier. Ouvrez le fichier PNG avec n'importe quel visualiseur d'images — vous verrez un **code-barres MacroPdf417** net qui encode le texte fourni ainsi que les métadonnées que vous avez définies.

### Résultat attendu

```
Barcode image saved to: C:\Projects\BarcodeDemo\ExtPDF417Meta.png
```

La taille du fichier image sera d'environ 30‑40 KB, selon le `XDimension` et le nombre de colonnes choisis.

## Vérifier le code-barres et résoudre les problèmes

1. **Inspection visuelle** – Le code-barres doit afficher une série de colonnes empilées avec une zone silencieuse (marge blanche) autour.  
2. **Test de décodage** – Utilisez une application de scanner de code-barres ou la classe `BarCodeReader` d'Aspose.BarCode pour lire l'image et confirmer que tous les champs de métadonnées sont correctement intégrés.  



## Que devriez‑vous apprendre ensuite ?

Les tutoriels suivants couvrent des sujets étroitement liés qui s'appuient sur les techniques démontrées dans ce guide. Chaque ressource inclut des exemples de code complets et fonctionnels avec des explications étape par étape pour vous aider à maîtriser des fonctionnalités API supplémentaires et explorer des approches d'implémentation alternatives dans vos propres projets.

- [Générer une image de code-barres PDF417 avec Aspose.BarCode en C# – guide étape par étape](/barcode/english/net/compact-pdf417-encoding/how-to-create-barcode-image-with-pdf417-in-c-step-by-step-gu/)
- [Comment générer un code-barres avec texte personnalisé en utilisant Aspose.BarCode pour .NET](/barcode/english/net/one-dimensional-barcode-types/how-to-generate-barcode-with-custom-text-using-aspose-barcod/)
- [Comment lire des codes-barres à partir d'une image en C# avec Aspose.BarCode – guide étape par étape](/barcode/english/net/one-dimensional-barcode-types/how-to-read-barcodes-from-image-using-c-step-by-step-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}