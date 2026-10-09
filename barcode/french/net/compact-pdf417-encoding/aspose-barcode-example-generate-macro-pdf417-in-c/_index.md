---
category: general
date: 2026-10-09
description: Apprenez comment créer un code-barres PDF417 en C# en utilisant Aspose.BarCode
  – générez un Macro PDF417 avec une prise en charge complète des métadonnées.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create pdf417 barcode c#
- macro pdf417 c#
- aspose barcode c#
- barcode generator c#
lastmod: 2026-10-09
og_description: Apprenez comment créer un code-barres PDF417 en C# en utilisant Aspose.BarCode
  – générez un Macro PDF417 avec une prise en charge complète des métadonnées, y compris
  l'ID du fichier, les données de segment, l'horodatage et plus encore.
og_image_alt: Screenshot of a Macro PDF417 barcode generated with Aspose.BarCode in
  C#
og_title: Comment créer un code-barres PDF417 en C# avec Aspose.BarCode
schemas:
- author: Aspose
  dateModified: '2026-10-09'
  description: Aspose barcode example showing how to use a barcode generator C# to
    create a Macro PDF417 with full metadata support.
  headline: 'Aspose barcode example: generate Macro PDF417 in C#'
  type: TechArticle
tags:
- aspose barcode
- pdf417 barcode
- c# barcode generation
- macro pdf417
title: Comment créer un code-barres PDF417 en C# avec Aspose.BarCode
url: /fr/net/compact-pdf417-encoding/aspose-barcode-example-generate-macro-pdf417-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Comment créer un code-barres PDF417 en C# avec Aspose.BarCode

Si vous devez **créer un code-barres PDF417 C#** rapidement et de manière fiable, ce tutoriel vous guide à travers le processus complet en utilisant Aspose.BarCode. Vous verrez chaque paramètre requis, des dimensions de base à l'ensemble complet des champs de métadonnées Macro PDF417, et vous terminerez avec une image PNG prête pour le traitement en aval.

## Réponses rapides
- **Quelle bibliothèque génère les codes-barres PDF417 ?** Aspose.BarCode for .NET.
- **Quel format l'exemple produit‑il ?** Une image PNG sans perte.
- **Ai‑je besoin d'une licence ?** Un essai gratuit fonctionne pour l'exemple ; une licence commerciale est requise pour la production.
- **Quelle version de .NET est prise en charge ?** .NET 6.0 ou ultérieure.
- **Puis‑je ajouter des métadonnées au code‑barres ?** Oui – Macro PDF417 prend en charge l'ID de fichier, le nombre de segments, les horodatages, et plus encore.

## Qu'est‑ce qu'un code-barres PDF417 ?
Un code‑barres PDF417 est une symbologie linéaire empilée qui peut encoder jusqu'à environ 1 KB de données par symbole et prend en charge des métadonnées macro optionnelles pour les fichiers multi‑segments. Il se compose de plusieurs rangées de motifs linéaires empilés, offrant une grande capacité de données tout en restant lisible par les scanners 2‑D standards. Le format inclut également des niveaux de correction d'erreurs pour améliorer la fiabilité, et la fonction macro optionnelle permet de diviser de gros fichiers en plusieurs codes‑barres avec des métadonnées qui aident à les réassembler.

## Pourquoi utiliser Aspose.BarCode pour le PDF417 ?
Aspose.BarCode prend en charge **plus de 50 symbologies de codes‑barres** et peut générer des codes‑barres Macro PDF417 avec jusqu'à **2 000 colonnes**, gérant des fichiers de plus de **10 Mo** sans charger l'intégralité de la charge utile en mémoire. Cette capacité quantifiée garantit le bon fonctionnement des scénarios d'entreprise à haut débit, et elle offre de nombreuses options de personnalisation.

## Prérequis

Avant de commencer, assurez‑vous d'avoir :

- .NET 6.0 (ou ultérieur) installé  
- Visual Studio 2022 ou tout IDE compatible C#  
- Une licence valide pour **Aspose.BarCode for .NET** (l'essai gratuit fonctionne pour cet exemple)  

Ajoutez le package NuGet Aspose.BarCode à votre projet :

```bash
dotnet add package Aspose.BarCode
```

## Comment créer un code-barres PDF417 en C# ?

`BarcodeGenerator` est la classe principale pour créer des images de code‑barres.  
`EncodeTypes.MacroPdf417` sélectionne la symbologie Macro PDF417 pour la génération du code‑barres.  
`Save` écrit le code‑barres généré dans un fichier image.

Chargez le `BarcodeGenerator` avec l'énumération `EncodeTypes.MacroPdf417` et le texte cible, puis appelez `Save` – c’est le flux complet de création en trois lignes. Le générateur gère Unicode automatiquement, et l'instruction `using` garantit que les ressources non gérées sont libérées après l'enregistrement de l'image.

### Étape 1 : créer l'instance du générateur de code‑barres C#

La classe `BarcodeGenerator` crée et configure les images de code‑barres.

Instanciez `BarcodeGenerator` avec la valeur d'énumération `EncodeTypes.MacroPdf417` et le texte que vous souhaitez encoder. Le texte peut contenir des caractères Unicode, que la bibliothèque gère automatiquement.

```csharp
using Aspose.BarCode.Generation;
using System;

using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.MacroPdf417, "Åspóse.Barcóde©"))
{
    // Subsequent steps are performed inside this using block.
```

*Pourquoi c'est important* : `EncodeTypes.MacroPdf417` indique au moteur de produire un symbole Macro PDF417, qui prend en charge les données segmentées et des métadonnées supplémentaires au niveau du fichier. L'instruction `using` garantit que les ressources non gérées sont libérées après l'enregistrement de l'image.

### Étape 2 : définir l'apparence de base du code‑barres

`XDimension.Pixels` définit la taille de chaque module du code‑barres en pixels.

Un code‑barres Macro PDF417 est composé de modules carrés. Le contrôle de la taille du module et du nombre de colonnes influence à la fois la lisibilité et la taille du fichier.

```csharp
    // Pixel size of a single module (X dimension)
    generator.Parameters.Barcode.XDimension.Pixels = 2;

    // Number of columns in the symbol; fewer columns produce a taller barcode
    generator.Parameters.Barcode.Pdf417.Columns = 5;
```

*Pourquoi c'est important* : `XDimension.Pixels` détermine la densité visuelle ; une valeur de 2 pixels fonctionne bien pour l'affichage à l'écran tout en gardant l'image petite. Ajustez le nombre de colonnes pour répondre à vos contraintes de mise en page — plus de colonnes créent un code‑barres plus large et plus court.

### Étape 3 : définir les métadonnées spécifiques à Macro PDF417

`MacroPdf417FileID` identifie le fichier auquel tous les segments du code‑barres appartiennent.

Macro PDF417 étend le format PDF417 standard avec des champs qui permettent la reconstruction de gros fichiers à partir de plusieurs segments de code‑barres. Chaque champ est optionnel, mais les définir montre l’ensemble des capacités de l'API.

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
- `MacroPdf417FileID` relie tous les segments appartenant au même fichier logique.  
- `MacroPdf417SegmentID` et `MacroPdf417SegmentsCount` permettent au décodeur de réordonner correctement les fragments.  
- `MacroPdf417Checksum` fournit une vérification rapide d'intégrité sans décoder l'intégralité de la charge utile.  
- `MacroPdf417FileSize` et `MacroPdf417TimeStamp` permettent aux systèmes en aval de vérifier que le fichier reconstruit correspond à l'original.  
- `MacroPdf417Addressee` / `MacroPdf417Sender` sont utiles dans les scénarios logistiques ou d'échange de documents.  
- Définir `MacroPdf417Terminator` à `Set` marque ce code‑barres comme le segment final, ce qui simplifie l'algorithme de reconstruction.

### Étape 4 : enregistrer l'image du code‑barres généré

`Save` écrit l'image du code‑barres vers le chemin de fichier spécifié.

Enfin, enregistrez le code‑barres dans un fichier PNG. Vous pouvez choisir n'importe quel format pris en charge (`Png`, `Jpeg`, `Bmp`, `Gif`, `Tiff`).

```csharp
    // Save the barcode image to the specified path
    generator.Save("YOUR_DIRECTORY/ExtPDF417Meta.png", BarCodeImageFormat.Png);
}
```

*Pourquoi c'est important* : PNG conserve les données de pixels sans perte, garantissant que les scanners lisent le motif de modules exact que vous avez configuré. Modifier le format peut affecter la qualité visuelle et la taille du fichier.

#### Résultat attendu

L'exécution du programme complet crée un fichier nommé **ExtPDF417Meta.png**. L'ouverture de l'image montre un code‑barres Macro PDF417 rectangulaire avec le texte « Åspóse.Barcóde© » encodé, et la densité visuelle correspond à la dimension X de 2 pixels que vous avez définie. Scanner l'image avec un lecteur compatible PDF417 renvoie tous les champs de métadonnées définis à l'Étape 3.

## Exemple complet fonctionnel

Copiez le code ci‑dessous dans un nouveau projet console (`dotnet new console`) et remplacez `YOUR_DIRECTORY` par un chemin absolu ou relatif qui existe sur votre machine.

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

Exécutez le programme (`dotnet run`). Après l'exécution, vérifiez que le fichier PNG apparaît à l'emplacement que vous avez spécifié. Utilisez n'importe quelle application de lecture de code‑barres qui prend en charge Macro PDF417 pour confirmer que les métadonnées sont correctement intégrées.

## Variantes courantes et cas limites

- **Formats d'image différents** : Remplacez `BarCodeImageFormat.Png` par `Jpeg`, `Bmp` ou `Tiff` si votre système en aval préfère un autre format.  
- **Modification de la taille du module** : Des valeurs plus grandes de `XDimension.Pixels` améliorent la fiabilité du scan sur les scanners à basse résolution mais augmentent la taille de l'image.  
- **Segments multiples** : Pour produire un fichier multi‑segment, générez une série de codes‑barres, incrémentez `MacroPdf417SegmentID` pour chacun, et maintenez `MacroPdf417FileID` constant. Seul le dernier segment doit avoir `MacroPdf417Terminator` défini.  
- **Prise en charge Unicode** : Le générateur encode automatiquement les caractères Unicode ; assurez‑vous que votre chaîne source utilise l'encodage UTF‑8 si vous la lisez depuis un fichier externe.  
- **Gestion des erreurs** : Enveloppez le bloc `using` dans un try‑catch pour capturer `BarCodeException` en cas de paramètres invalides (par ex., nombre de colonnes hors limites).

## Astuces professionnelles

- **Performance** : Réutilisez une seule instance de `BarcodeGenerator` lors de la création de nombreux codes‑barres avec les mêmes paramètres ; ne modifiez que la propriété `CodeText` entre les enregistrements.  
- **Estimation de la taille du fichier** : Le champ `MacroPdf417FileSize` doit correspondre au nombre d'octets de la charge utile originale ; des divergences peuvent entraîner des échecs de validation en aval.  
- **Tests** : Validez les codes‑barres générés avec le décodeur intégré d'Aspose (`BarCodeReader`) ainsi qu'avec un scanner tiers pour garantir l'interopérabilité.

## Conclusion

Cet exemple **Aspose.BarCode** vous montre comment **créer un code‑barres PDF417 C#** avec un support complet des métadonnées Macro, vous offrant une base solide pour construire des pipelines d'échange de données basés sur les codes‑barres.

## Que devriez‑vous apprendre ensuite ?

Les tutoriels suivants couvrent des sujets étroitement liés qui s'appuient sur les techniques démontrées dans ce guide. Chaque ressource comprend des exemples de code complets et fonctionnels avec des explications étape par étape pour vous aider à maîtriser des fonctionnalités supplémentaires de l'API et à explorer des approches d'implémentation alternatives dans vos propres projets.

- [Comment créer un code‑barres – PDF417 compact avec Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [Comment créer la zone silencieuse d'un code‑barres pour Code 16K avec Aspose.BarCode pour .NET](/barcode/english/net/code-16k-encoding/code-16k-quiet-zone-settings/)
- [Comment créer la zone silencieuse d'un code‑barres pour ITF-14 avec Aspose.BarCode pour .NET](/barcode/english/net/itf-14-barcode-customization/itf-14-barcode-quiet-zone-configuration/)

---

**Dernière mise à jour:** 2026-10-09  
**Testé avec:** Aspose.BarCode 24.11 for .NET  
**Auteur:** Aspose

## Tutoriels associés

- [Comment générer une image de code‑barres Pdf417 en C avec Aspose](/barcode/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-image-in-c-with-aspose/)
- [Comment créer un code‑barres – PDF417 compact avec Aspose.BarCode](/barcode/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [Tutoriel du générateur de code‑barres – Comment générer un code‑barres Pdf417 dans](/barcode/net/compact-pdf417-encoding/barcode-generator-tutorial-how-to-generate-pdf417-barcode-in/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}