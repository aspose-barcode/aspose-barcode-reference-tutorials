---
category: general
date: 2026-10-12
description: Apprenez à créer un exemple de code‑barres Aspose en C# qui génère un
  code‑barres MacroPdf417 avec toutes les métadonnées et le lit à nouveau à l’aide
  de BarCodeReader.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- aspose barcode example
- macroPdf417 barcode
- barcode metadata
- c# barcode generation
- BarCodeReader
language: fr
lastmod: 2026-10-12
og_description: Exemple de code-barres Aspose en C# montrant comment générer un code-barres
  MacroPdf417 avec des métadonnées intégrées et le lire à nouveau à l'aide de BarCodeReader.
og_image_alt: Screenshot of an Aspose barcode example displaying a MacroPdf417 barcode
  with metadata
og_title: Créer un exemple de code‑barres Aspose avec MacroPdf417 en C#
schemas:
- author: Aspose
  dateModified: '2026-10-12'
  description: Learn how to create an Aspose barcode example in C# that generates
    a MacroPdf417 barcode with full metadata and reads it back using BarCodeReader.
  headline: How to build an Aspose barcode example with MacroPdf417 in C#
  type: TechArticle
tags:
- Aspose.BarCode
- C#
- Barcode
title: Comment créer un exemple de code‑barres Aspose avec MacroPdf417 en C#
url: /fr/net/compact-pdf417-encoding/how-to-build-an-aspose-barcode-example-with-macropdf417-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Comment créer un exemple de code‑barres Aspose avec MacroPdf417 en C#

Si vous avez besoin d'un **aspose barcode example** qui crée un code‑barres MacroPdf417 et lit ses métadonnées intégrées, ce guide vous montre le flux de travail complet. Vous verrez comment configurer le générateur, intégrer des informations au niveau du fichier, enregistrer l'image, puis décoder les mêmes données avec `BarCodeReader`.

Le tutoriel couvre tout ce que vous devez savoir pour la **C# barcode generation** avec Aspose.BarCode, y compris les pièges courants et les conseils pour gérer les grands ID de fichiers ou les horodatages personnalisés.

## Ce dont vous avez besoin

* .NET 6.0 SDK ou version ultérieure (le code fonctionne avec .NET Core et .NET Framework)
* Visual Studio 2022 ou tout IDE qui prend en charge C#
* Une licence active Aspose.BarCode (l'essai gratuit fonctionne pour le développement)
* Le package NuGet `Aspose.BarCode` installé dans votre projet

Ces prérequis garantissent que l'exemple s'exécute sans configuration supplémentaire.

## Étape 1 : Configurer le projet d'exemple de code‑barres Aspose

Créez une nouvelle application console et ajoutez la bibliothèque Aspose.BarCode :

```bash
dotnet new console -n AsposeMacroPdf417Demo
cd AsposeMacroPdf417Demo
dotnet add package Aspose.BarCode
```

Le package `Aspose.BarCode` fournit `BarcodeGenerator`, `BarCodeReader` et tous les types nécessaires à la gestion de MacroPdf417.

### Pourquoi cette étape est importante
L'ajout du package NuGet résout les énumérations `EncodeTypes`, `DecodeType` et `BarCodeImageFormat` utilisées plus tard. Sans le package, le compilateur ne reconnaîtrait pas ces symboles et l'exemple échouerait lors de la compilation.

## Étape 2 : Créer le générateur de code‑barres MacroPdf417

Ouvrez **Program.cs** et remplacez le code modèle par le bloc suivant. Ce bloc crée un `BarcodeGenerator` configuré pour la symbologie MacroPdf417 et définit les paramètres d'apparence de base.

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Enums;
using System;

class Program
{
    static void Main()
    {
        // Step 2.1: Initialize the generator with source text.
        using (BarcodeGenerator barcodeGenerator =
               new BarcodeGenerator(EncodeTypes.MacroPdf417, "Sample data"))
        {
            // Adjust the module size – 2 pixels per X‑dimension.
            barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;

            // Reduce the number of columns to keep the barcode compact.
            barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 5;

            // Step 2.2: Embed MacroPdf417 metadata.
            // ---------------------------------------------------------
            // The following properties are optional but illustrate
            // how a full‑featured barcode can carry file‑level data.
            // ---------------------------------------------------------
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234; // CCITT‑16
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400_000;
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp =
                new DateTime(2024, 9, 1);
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Terminator =
                Pdf417MacroTerminator.Set;

            // Step 2.3: Save the barcode image.
            const string outPath = "ExtPDF417Meta.png";
            barcodeGenerator.Save(outPath, BarCodeImageFormat.Png);
            Console.WriteLine($"Barcode saved to {outPath}");
        }
```

#### Explication des propriétés clés

| Propriété | Objectif | Plage typique / notes |
|----------|----------|-----------------------|
| `MacroPdf417FileID` | Identifiant unique pour l'ensemble du fichier | Doit être ≤ 2³¹‑1 |
| `MacroPdf417SegmentID` | Index du segment actuel | Commence à 0 |
| `MacroPdf417SegmentsCount` | Nombre total de segments dans le fichier | Doit être ≥ SegmentID |
| `MacroPdf417FileName` | Nom lisible par l'homme pour le fichier | Jusqu'à 255 caractères |
| `MacroPdf417Checksum` | Somme de contrôle CCITT‑16 du fichier original | Calculée par un outil externe si nécessaire |
| `MacroPdf417FileSize` | Taille du fichier original en octets | Utile pour la validation |
| `MacroPdf417TimeStamp` | Date/heure de création du fichier | Utilisez UTC pour la cohérence |
| `MacroPdf417Addressee` / `MacroPdf417Sender` | Informations de routage optionnelles | Toute chaîne jusqu'à 255 caractères |
| `MacroPdf417Terminator` | Marque le segment final | Utilisez `Set` pour le dernier segment |

Ces champs constituent les **barcode metadata** que le lecteur peut extraire ultérieurement.

## Étape 3 : Décoder le code‑barres et afficher les métadonnées

Après avoir enregistré l'image, le même programme continue en ouvrant le fichier avec `BarCodeReader`. Ajoutez le code suivant à l'intérieur de la méthode `Main`, après le bloc `using` précédent :

```csharp
        // Step 3: Open the saved image with a MacroPdf417 reader.
        using (BarCodeReader barcodeReader =
               new BarCodeReader("ExtPDF417Meta.png", DecodeType.MacroPdf417))
        {
            // Step 3.1: Iterate through all decoded results.
            foreach (BarCodeResult result in barcodeReader.ReadBarCodes())
            {
                // The Extended property holds the MacroPdf417 specific fields.
                var meta = result.Extended.Pdf417;
                Console.WriteLine($"FileID: {meta.MacroPdf417FileID}");
                Console.WriteLine($"SegmentID: {meta.MacroPdf417SegmentID}");
                Console.WriteLine($"SegmentsCount: {meta.MacroPdf417SegmentsCount}");
                Console.WriteLine($"FileName: {meta.MacroPdf417FileName}");
                Console.WriteLine($"Checksum: {meta.MacroPdf417Checksum}");
                Console.WriteLine($"FileSize: {meta.MacroPdf417FileSize}");
                Console.WriteLine($"Timestamp: {meta.MacroPdf417TimeStamp}");
                Console.WriteLine($"Addressee: {meta.MacroPdf417Addressee}");
                Console.WriteLine($"Sender: {meta.MacroPdf417Sender}");
                Console.WriteLine($"Terminator: {meta.MacroPdf417Terminator}");
            }
        }
    }
}
```

### Pourquoi la lecture inverse est importante
Le `BarCodeReader` valide que les métadonnées que vous avez intégrées sont correctement encodées. Si une propriété est manquante ou hors plage, le lecteur renvoie `null` pour ce champ, vous permettant de gérer les erreurs de manière élégante.

## Étape 4 : Exécuter et vérifier la sortie

Exécutez le programme :

```bash
dotnet run
```

Vous devriez voir une sortie console similaire à :

```
Barcode saved to ExtPDF417Meta.png
FileID: 12345678
SegmentID: 12
SegmentsCount: 20
FileName: file01
Checksum: 1234
FileSize: 400000
Timestamp: 9/1/2024 12:00:00 AM
Addressee: street
Sender: aspose
Terminator: Set
```

Si les valeurs correspondent à celles que vous avez définies à l'étape 2, le **aspose barcode example** fonctionne comme prévu.

## Cas limites et conseils de bonnes pratiques

| Situation | À surveiller | Gestion recommandée |
|-----------|--------------|---------------------|
| **FileID dépasse la plage 32 bits** | Aspose lève `ArgumentOutOfRangeException`. | Conservez l'ID ≤ 2 147 483 647 ou divisez le fichier en plusieurs blocs MacroPdf417. |
| **Horodatage en heure locale** | Les lecteurs dans un autre fuseau horaire peuvent mal interpréter la valeur. | Enregistrez les horodatages en UTC (`DateTime.UtcNow`) et convertissez-les lors de l'affichage si nécessaire. |
| **Grande taille de fichier** | `MacroPdf417FileSize` est un `int` ; les valeurs > 2 Go débordent. | Utilisez un champ personnalisé ou divisez le fichier en segments plus petits. |
| **Segment manquant** | Si `SegmentID` n'est pas séquentiel, la reconstruction échoue. | Validez l'ordre des segments avant l'encodage ou utilisez les paramètres de correction d'erreurs. |
| **Format d'image non pris en charge** | Enregistrer en BMP peut augmenter la taille de façon spectaculaire. | PNG est une bonne valeur par défaut ; JPEG peut être utilisé si vous acceptez la compression avec perte. |

**Astuce :** Lorsque vous générez de nombreux codes‑barres en lot, réutilisez une seule instance de `BarcodeGenerator` et ne modifiez que les `EncodeTypes` et le texte source. Cela réduit les allocations mémoire et accélère le traitement.

## Sujets connexes que vous pourriez explorer ensuite

* **Other macro symbologies** – Aspose prend également en charge MacroPdf417 avec des niveaux de correction d'erreurs.
* **Embedding barcodes in PDFs** – Combinez `Aspose.PDF` avec le générateur de code‑barres pour produire des documents imprimables.
* **ASP.NET Core integration** – Servez les codes‑barres générés directement depuis une API web.
* **Scanning via mobile devices** – Utilisez le SDK `Aspose.BarCode.Cloud` pour le décodage multiplateforme.

Ces sujets complémentaires prolongent naturellement le **aspose barcode example** et approfondissent votre expertise en **C# barcode generation**.

## Conclusion

Vous disposez maintenant d'un **aspose barcode example** entièrement fonctionnel qui crée un code‑barres MacroPdf417, intègre des **barcode metadata** riches, enregistre l'image et lit les données avec `BarCodeReader`. En suivant les étapes ci‑dessus, vous pouvez adapter le code à différents ID de fichiers, horodatages ou même à d'autres types de code‑barres pris en charge par Aspose.

N'hésitez pas à expérimenter avec des champs de métadonnées supplémentaires, à changer le format d'image ou à intégrer le générateur dans une application plus grande. Bon codage !

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}