---
category: general
date: 2026-08-09
description: Exemple Aspose Barcode montrant comment utiliser le générateur de code-barres
  C# pour créer un Macro PDF417 avec prise en charge complète des métadonnées.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- aspose barcode example
- barcode generator c#
language: fr
lastmod: 2026-08-09
og_description: L'exemple de code‑barres Aspose montre l'utilisation d'un générateur
  de code‑barres C# pour produire un code‑barres Macro PDF417 incluant l'ID du fichier,
  les données de segment, l'horodatage et d'autres métadonnées.
og_image_alt: Screenshot of a Macro PDF417 barcode generated with Aspose.BarCode in
  C#
og_title: Exemple de code-barres Aspose – créer un Macro PDF417 avec C#
schemas:
- author: Aspose
  dateModified: '2026-08-09'
  description: Aspose barcode example showing how to use a barcode generator C# to
    create a Macro PDF417 with full metadata support.
  headline: 'Aspose barcode example: generate Macro PDF417 in C#'
  type: TechArticle
tags:
- Aspose.BarCode
- C#
- Macro PDF417
title: 'Exemple de code-barres Aspose : générer Macro PDF417 en C#'
url: /fr/net/compact-pdf417-encoding/aspose-barcode-example-generate-macro-pdf417-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Exemple Aspose Barcode : générer Macro PDF417 en C#

Si vous avez besoin d'un **exemple Aspose barcode** qui crée un code-barres Macro PDF417, ce guide vous montre comment le faire avec un **générateur de code-barres C#**. Vous verrez chaque paramètre requis, des dimensions de base à l'ensemble complet des champs de métadonnées Macro PDF417, et vous obtiendrez une image PNG prête pour le traitement en aval.

Le tutoriel couvre le flux de travail complet, explique pourquoi chaque paramètre est important et fournit un exemple de code prêt à l'exécution. Aucune référence externe n'est requise ; vous pouvez copier le code, ajuster les valeurs et l'exécuter immédiatement.

## Prérequis

- .NET 6.0 (ou version ultérieure) installé  
- Visual Studio 2022 ou tout IDE compatible C#  
- Une licence valide pour **Aspose.BarCode for .NET** (l'essai gratuit fonctionne pour cet exemple)  

Ajoutez le package NuGet Aspose.BarCode à votre projet :

```bash
dotnet add package Aspose.BarCode
```

## Étape 1 : Créer l'instance du générateur de code-barres C#  

La première étape consiste à instancier `BarcodeGenerator` avec la valeur d'énumération `EncodeTypes.MacroPdf417` et le texte que vous souhaitez encoder. Le texte peut contenir des caractères Unicode, que la bibliothèque gère automatiquement.

```csharp
using Aspose.BarCode.Generation;
using System;

using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.MacroPdf417, "Åspóse.Barcóde©"))
{
    // Subsequent steps are performed inside this using block.
```

*Pourquoi c'est important* : `EncodeTypes.MacroPdf417` indique au moteur de produire un symbole Macro PDF417, qui prend en charge les données segmentées et des métadonnées supplémentaires au niveau du fichier. L'instruction `using` garantit que les ressources non gérées sont libérées après l'enregistrement de l'image.

## Étape 2 : Définir l'apparence de base du code-barres  

Un code-barres Macro PDF417 est composé de modules carrés. Le contrôle de la taille du module et du nombre de colonnes influence à la fois la lisibilité et la taille du fichier.

```csharp
    // Pixel size of a single module (X dimension)
    generator.Parameters.Barcode.XDimension.Pixels = 2;

    // Number of columns in the symbol; fewer columns produce a taller barcode
    generator.Parameters.Barcode.Pdf417.Columns = 5;
```

*Pourquoi c'est important* : `XDimension.Pixels` détermine la densité visuelle ; une valeur de 2 pixels fonctionne bien pour l'affichage à l'écran tout en gardant l'image petite. Ajustez le nombre de colonnes pour répondre à vos contraintes de mise en page — plus de colonnes créent un code-barres plus large et plus court.

## Étape 3 : Définir les métadonnées spécifiques à Macro PDF417  

Macro PDF417 étend le format PDF417 standard avec des champs qui permettent la reconstruction de gros fichiers à partir de plusieurs segments de code-barres. Chaque champ est optionnel, mais les définir montre toutes les capacités de l'API.

```csharp
    // Unique identifier for the entire file
    generator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;

    // Identifier of the current segment (zero‑based)
    generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;

    // Total number of segments that compose the file
    generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;

    // Logical name of the source file
    generator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";

    // 16‑bit CCITT checksum for error detection
    generator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234;

    // Approximate size of the original file in bytes
    generator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400000;

    // Timestamp when the file was generated
    generator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = new DateTime(2019, 11, 1);

    // Optional address fields for routing information
    generator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
    generator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";

    // Terminator indicates that this is the last segment
    generator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;
```

*Pourquoi c'est important* :  
- `MacroPdf417FileID` lie tous les segments appartenant au même fichier logique.  
- `MacroPdf417SegmentID` et `MacroPdf417SegmentsCount` permettent au décodeur de réordonner correctement les fragments.  
- `MacroPdf417Checksum` fournit une vérification d'intégrité rapide sans décoder l'intégralité de la charge utile.  
- `MacroPdf417FileSize` et `MacroPdf417TimeStamp` permettent aux systèmes en aval de vérifier que le fichier reconstruit correspond à l'original.  
- `MacroPdf417Addressee` / `MacroPdf417Sender` sont utiles dans les scénarios logistiques ou d'échange de documents.  
- Définir `MacroPdf417Terminator` à `Set` marque ce code-barres comme le segment final, ce qui simplifie l'algorithme de reconstruction.

## Étape 4 : Enregistrer l'image du code-barres généré  

Enfin, écrivez le code-barres dans un fichier PNG. Vous pouvez choisir n'importe quel format pris en charge (`Png`, `Jpeg`, `Bmp`, `Gif`, `Tiff`).

```csharp
    // Save the barcode image to the specified path
    generator.Save("YOUR_DIRECTORY/ExtPDF417Meta.png", BarCodeImageFormat.Png);
}
```

*Pourquoi c'est important* : PNG conserve les données pixel sans perte, garantissant que les scanners lisent exactement le motif de modules que vous avez configuré. Modifier le format peut affecter la qualité visuelle et la taille du fichier.

### Résultat attendu

L'exécution du programme complet crée un fichier nommé **ExtPDF417Meta.png**. L'ouverture de l'image montre un code-barres Macro PDF417 rectangulaire avec le texte « Åspóse.Barcóde© » encodé, et la densité visuelle correspond à la dimension X de 2 pixels que vous avez définie. Scanner l'image avec un lecteur compatible PDF417 renvoie tous les champs de métadonnées définis à l'Étape 3.

## Exemple complet fonctionnel

Copiez le code ci-dessous dans un nouveau projet console (`dotnet new console`) et remplacez `YOUR_DIRECTORY` par un chemin absolu ou relatif qui existe sur votre machine.

```csharp
using Aspose.BarCode.Generation;
using System;

namespace MacroPdf417Demo
{
    class Program
    {
        static void Main()
        {
            // Step 1: Create a barcode generator for Macro PDF417 with the desired text
            using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.MacroPdf417, "Åspóse.Barcóde©"))
            {
                // Step 2: Define the basic barcode appearance
                generator.Parameters.Barcode.XDimension.Pixels = 2;          // pixel size of a single module
                generator.Parameters.Barcode.Pdf417.Columns = 5;           // number of columns in the symbol

                // Step 3: Set Macro PDF417 specific metadata
                generator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
                generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;
                generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;
                generator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";
                generator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234; // CCITT‑16 example
                generator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400000;
                generator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = new DateTime(2019, 11, 1);
                generator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
                generator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
                generator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;

                // Step 4: Save the generated barcode image
                generator.Save("YOUR_DIRECTORY/ExtPDF417Meta.png", BarCodeImageFormat.Png);
            }

            Console.WriteLine("Macro PDF417 barcode generated successfully.");
        }
    }
}
```

Exécutez le programme (`dotnet run`). Après l'exécution, vérifiez que le fichier PNG apparaît à l'emplacement que vous avez spécifié. Utilisez n'importe quelle application de lecture de code-barres qui prend en charge Macro PDF417 pour confirmer que les métadonnées sont correctement intégrées.

## Variantes courantes et cas limites

- **Différents formats d'image** : Remplacez `BarCodeImageFormat.Png` par `Jpeg`, `Bmp` ou `Tiff` si votre système en aval préfère un autre format.  
- **Modification de la taille du module** : Des valeurs plus grandes de `XDimension.Pixels` améliorent la fiabilité du scan sur des scanners basse résolution mais augmentent la taille de l'image.  
- **Segments multiples** : Pour produire un fichier multi‑segment, générez une série de code‑barres, incrémentez `MacroPdf417SegmentID` pour chaque, et conservez `MacroPdf417FileID` constant. Seul le dernier segment doit avoir `MacroPdf417Terminator` défini.  
- **Prise en charge Unicode** : Le générateur encode automatiquement les caractères Unicode ; assurez‑vous que votre chaîne source utilise l'encodage UTF‑8 si vous la lisez depuis un fichier externe.  
- **Gestion des erreurs** : Enveloppez le bloc `using` dans un try‑catch pour capturer `BarCodeException` en cas de paramètres invalides (par ex., nombre de colonnes hors plage).

## Conseils pro

- **Performance** : Réutilisez une seule instance de `BarcodeGenerator` lors de la création de nombreux code‑barres avec les mêmes paramètres ; ne changez que la propriété `CodeText` entre les enregistrements.  
- **Estimation de la taille du fichier** : Le champ `MacroPdf417FileSize` doit correspondre au nombre d'octets de la charge utile originale ; des divergences peuvent entraîner des échecs de validation en aval.  
- **Tests** : Validez les code‑barres générés avec le décodeur intégré d'Aspose (`BarCodeReader`) ainsi qu'avec un scanner tiers pour garantir l'interopérabilité.

## Conclusion

Cet **exemple Aspose barcode**

## Que devriez‑vous apprendre ensuite ?

Les tutoriels suivants couvrent des sujets étroitement liés qui s'appuient sur les techniques démontrées dans ce guide. Chaque ressource inclut des exemples de code complets et fonctionnels avec des explications étape par étape pour vous aider à maîtriser des fonctionnalités supplémentaires de l'API et explorer des approches d'implémentation alternatives dans vos propres projets.

- [How to Create Barcode – Compact PDF417 with Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [How to create barcode quiet zone for Code 16K using Aspose.BarCode for .NET](/barcode/english/net/code-16k-encoding/code-16k-quiet-zone-settings/)
- [How to Create Barcode Quiet Zone for ITF-14 Using Aspose.BarCode for .NET](/barcode/english/net/itf-14-barcode-customization/itf-14-barcode-quiet-zone-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}