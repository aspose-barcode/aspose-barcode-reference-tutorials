---
category: general
date: 2026-10-18
description: Apprenez à lire les codes-barres à partir d’une image en C# avec Aspose.BarCode,
  en couvrant l’extraction des métadonnées Macro PDF417 et le code d’exemple complet.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to read barcode from image
- C# barcode reader
- Macro PDF417 metadata
- BarCodeReader class
- DecodeType.MacroPdf417
- barcode metadata extraction
language: fr
lastmod: 2026-10-18
og_description: Comment lire un code‑barres à partir d’une image en utilisant C# Aspose.BarCode.
  Suivez ce tutoriel étape par étape pour extraire les métadonnées Macro PDF417 et
  gérer les scénarios courants.
og_image_alt: Screenshot showing output of how to read barcode from image with C#
  Aspose.BarCode
og_title: Comment lire un code-barres à partir d’une image en C# – guide complet Aspose.BarCode
schemas:
- author: Aspose
  dateModified: '2026-10-18'
  description: Learn how to read barcode from image in C# with Aspose.BarCode, covering
    Macro PDF417 metadata extraction and complete sample code.
  headline: How to read barcode from image in C# using Aspose.BarCode
  type: TechArticle
- description: Learn how to read barcode from image in C# with Aspose.BarCode, covering
    Macro PDF417 metadata extraction and complete sample code.
  name: How to read barcode from image in C# using Aspose.BarCode
  steps:
  - name: Expected console output
    text: '``` CodeType: MacroPdf417 CodeText: https://example.com/document.pdf MacroFileID:
      12345 MacroSegmentID: 1 MacroSegmentsCount: 3 MacroFileName: document.pdf MacroChecksum:
      0x1A2B3C4D MacroFileSize: 204800 MacroTimeStamp: 2023-07-15T10:23:45Z MacroAddressee:
      Acme Corp MacroSender: Warehouse 7 MacroTer'
  - name: Large images
    text: 'Reading very large images can consume significant memory. Use the `BarcodeReader`
      overload that accepts `ReaderParameters` to limit the maximum image size:'
  - name: Missing or corrupted metadata
    text: If any of the Macro fields are missing, the corresponding property returns
      `null` or `0`. Log these cases and decide whether to treat the barcode as incomplete.
  - name: Multiple barcode types in one image
    text: 'If an image may contain other barcode formats, you can pass an array of
      `DecodeType` values:'
  type: HowTo
tags:
- barcode
- C#
- Aspose.BarCode
title: Comment lire un code‑barres à partir d’une image en C# avec Aspose.BarCode
url: /fr/net/one-dimensional-barcode-types/how-to-read-barcode-from-image-in-c-using-aspose-barcode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Comment lire un code‑barres à partir d’une image en C# avec Aspose.BarCode

Si vous avez besoin de **comment lire un code‑barres à partir d’une image** dans une application .NET, ce guide montre les étapes exactes avec Aspose.BarCode. Que vous traitiez des documents numérisés, des reçus ou des étiquettes d’inventaire, vous verrez comment lire le code‑barres, extraire les métadonnées Macro PDF417 et gérer les cas limites typiques.

Lire un code‑barres à partir d’une image est une tâche courante, mais extraire les champs étendus Macro PDF417 ajoute une couche de complexité. Ce tutoriel couvre le flux de travail complet, de la configuration du projet à un exemple entièrement exécutable, afin que vous puissiez copier‑coller le code et voir les résultats immédiatement.

## Ce que vous allez apprendre

- Comment configurer Aspose.BarCode pour les projets C#.  
- La bonne façon d’instancier le **lecteur de code‑barres C#** pour une image Macro PDF417.  
- Comment parcourir chaque code‑barres détecté et afficher les informations de base.  
- Comment accéder aux **métadonnées Macro PDF417** telles que l’ID de fichier, l’ID de segment et la somme de contrôle.  
- Astuces pour gérer les métadonnées manquantes, les images volumineuses et les erreurs de décodage courantes.  

**Prérequis**

- .NET 6.0 (ou version ultérieure) installé.  
- Familiarité de base avec C# et Visual Studio (tout IDE fonctionne).  
- Un fichier image contenant un code‑barres Macro PDF417 (par ex., `ExtPDF417Meta.png`).  

## Étape 1 : Installer Aspose.BarCode

Ouvrez un terminal dans le dossier de votre projet et exécutez :

```bash
dotnet add package Aspose.BarCode
```

Le package inclut la **classe BarCodeReader**, qui implémente la fonctionnalité du **lecteur de code‑barres C#** nécessaire pour ce tutoriel.

## Étape 2 : Configurer l’environnement de développement

Créez une nouvelle application console si vous n’en avez pas déjà une :

```bash
dotnet new console -n BarcodeDemo
cd BarcodeDemo
```

Ajoutez les directives `using` en haut de `Program.cs` :

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;
```

Ces espaces de noms exposent la **classe BarCodeReader** et l’énumération `DecodeType` requises pour le décodage Macro PDF417.

## Étape 3 : Initialiser le BarCodeReader pour Macro PDF417

Le cœur du **comment lire un code‑barres à partir d’une image** consiste à créer une instance `BarCodeReader` qui cible le `DecodeType` spécifique. Pour Macro PDF417, vous devez passer `DecodeType.MacroPdf417` :

```csharp
// Step 3: Create a barcode reader for a Macro PDF417 image
using (BarCodeReader reader = new BarCodeReader(
           "YOUR_DIRECTORY/ExtPDF417Meta.png", DecodeType.MacroPdf417))
{
    // The reader is now ready to scan the image.
}
```

**Pourquoi c’est important :**  
Choisir `DecodeType.MacroPdf417` indique à la bibliothèque de rechercher le format étendu Macro PDF417, qui contient des champs supplémentaires au-delà des données de base du code‑barres. Si vous utilisez le générique `DecodeType.Pdf417`, ces champs supplémentaires seraient ignorés.

## Étape 4 : Parcourir les codes‑barres détectés

Une seule image peut contenir plusieurs codes‑barres. La méthode `ReadBarCodes()` renvoie une collection énumérable d’objets `BarCodeResult`. Parcourez‑les pour afficher les informations de base de chaque code‑barres :

```csharp
foreach (BarCodeResult result in reader.ReadBarCodes())
{
    Console.WriteLine($"CodeType: {result.CodeTypeName}");
    Console.WriteLine($"CodeText: {result.CodeText}");
}
```

La propriété `CodeTypeName` indique la symbologie exacte du code‑barres (par ex., “MacroPdf417”), tandis que `CodeText` contient la chaîne décodée.

## Étape 5 : Extraire et afficher les métadonnées Macro PDF417

Lorsque le code‑barres est un Macro PDF417, la propriété `Extended.Pdf417` fournit un ensemble riche de champs de métadonnées. Accédez‑les directement comme indiqué ci‑dessous :

```csharp
Console.WriteLine($"MacroFileID: {result.Extended.Pdf417.MacroPdf417FileID}");
Console.WriteLine($"MacroSegmentID: {result.Extended.Pdf417.MacroPdf417SegmentID}");
Console.WriteLine($"MacroSegmentsCount: {result.Extended.Pdf417.MacroPdf417SegmentsCount}");
Console.WriteLine($"MacroFileName: {result.Extended.Pdf417.MacroPdf417FileName}");
Console.WriteLine($"MacroChecksum: {result.Extended.Pdf417.MacroPdf417Checksum}");
Console.WriteLine($"MacroFileSize: {result.Extended.Pdf417.MacroPdf417FileSize}");
Console.WriteLine($"MacroTimeStamp: {result.Extended.Pdf417.MacroPdf417TimeStamp}");
Console.WriteLine($"MacroAddressee: {result.Extended.Pdf417.MacroPdf417Addressee}");
Console.WriteLine($"MacroSender: {result.Extended.Pdf417.MacroPdf417Sender}");
Console.WriteLine($"MacroTerminator: {result.Extended.Pdf417.MacroPdf417Terminator}");
```

Ces champs vous donnent tout ce dont vous avez besoin pour reconstruire le fichier multi‑segment original, vérifier l’intégrité et associer le code‑barres à un document ou à un expéditeur spécifique.

### Sortie console attendue

```
CodeType: MacroPdf417
CodeText: https://example.com/document.pdf
MacroFileID: 12345
MacroSegmentID: 1
MacroSegmentsCount: 3
MacroFileName: document.pdf
MacroChecksum: 0x1A2B3C4D
MacroFileSize: 204800
MacroTimeStamp: 2023-07-15T10:23:45Z
MacroAddressee: Acme Corp
MacroSender: Warehouse 7
MacroTerminator: END
```

Si l’image ne contient pas de code‑barres Macro PDF417, l’objet `Extended.Pdf417` sera `null`. Protégez‑vous contre cela pour éviter une `NullReferenceException` :

```csharp
if (result.Extended?.Pdf417 != null)
{
    // Safe to read metadata
}
else
{
    Console.WriteLine("No Macro PDF417 metadata found.");
}
```

## Étape 6 : Gestion des erreurs courantes et des cas limites

### Images volumineuses

Lire des images très grandes peut consommer beaucoup de mémoire. Utilisez la surcharge de `BarcodeReader` qui accepte `ReaderParameters` pour limiter la taille maximale de l’image :

```csharp
ReaderParameters parameters = new ReaderParameters
{
    MaxImageSize = 4096 // pixels
};

using (BarCodeReader reader = new BarCodeReader(
           "large_image.png", DecodeType.MacroPdf417, parameters))
{
    // Process as before
}
```

### Métadonnées manquantes ou corrompues

Si l’un des champs Macro est absent, la propriété correspondante renvoie `null` ou `0`. Enregistrez ces cas et décidez si le code‑barres doit être considéré comme incomplet.

### Plusieurs types de code‑barres dans une même image

Si une image peut contenir d’autres formats de code‑barres, vous pouvez passer un tableau de valeurs `DecodeType` :

```csharp
DecodeType[] types = { DecodeType.MacroPdf417, DecodeType.QR, DecodeType.Code128 };
using (BarCodeReader reader = new BarCodeReader("mixed.png", types))
{
    // Iterate as before
}
```

Cette approche maintient la logique du **comment lire un code‑barres à partir d’une image** flexible sans sacrifier les performances.

## Étape 7 : Code source complet

Voici le programme complet, prêt à être exécuté. Remplacez `YOUR_DIRECTORY/ExtPDF417Meta.png` par le chemin vers votre propre image.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

namespace BarcodeDemo
{
    class Program
    {
        static void Main(string[] args)
        {
            // Path to the image containing a Macro PDF417 barcode
            const string imagePath = "YOUR_DIRECTORY/ExtPDF417Meta.png";

            // Initialize the C# barcode reader for Macro PDF417
            using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
            {
                // Iterate over all detected barcodes
                foreach (BarCodeResult result in reader.ReadBarCodes())
                {
                    Console.WriteLine($"CodeType: {result.CodeTypeName}");
                    Console.WriteLine($"CodeText: {result.CodeText}");

                    // Safely access Macro PDF417 metadata
                    if (result.Extended?.Pdf417 != null)
                    {
                        Console.WriteLine($"MacroFileID: {result.Extended.Pdf417.MacroPdf417FileID}");
                        Console.WriteLine($"MacroSegmentID: {result.Extended.Pdf417.MacroPdf417SegmentID}");
                        Console.WriteLine($"MacroSegmentsCount: {result.Extended.Pdf417.MacroPdf417SegmentsCount}");
                        Console.WriteLine($"MacroFileName: {result.Extended.Pdf417.MacroPdf417FileName}");
                        Console.WriteLine($"MacroChecksum: {result.Extended.Pdf417.MacroPdf417Checksum}");
                        Console.WriteLine($"MacroFileSize: {result.Extended.Pdf417.MacroPdf417FileSize}");
                        Console.WriteLine($"MacroTimeStamp: {result.Extended.Pdf417.MacroPdf417TimeStamp}");
                        Console.WriteLine($"MacroAddressee: {result.Extended.Pdf417.MacroPdf417Addressee}");
                        Console.WriteLine($"MacroSender: {result.Extended.Pdf417.MacroPdf417Sender}");
                        Console.WriteLine($"MacroTerminator: {result.Extended.Pdf417.MacroPdf417Terminator}");
                    }
                    else
                    {
                        Console.WriteLine("No Macro PDF417 metadata found for this barcode.");
                    }

                    Console.WriteLine(new string('-', 40));
                }
            }

            Console.WriteLine("Barcode processing completed.");
        }
    }
}
```

Exécutez le programme avec :

```bash
dotnet run
```

Vous devriez voir le type de code‑barres, le texte décodé et tous les champs Macro PDF417 disponibles affichés dans la console.

## Conclusion

Dans ce tutoriel, vous avez appris **comment lire un code‑barres à partir d’une image** en utilisant Aspose.BarCode pour C#. Le guide a couvert la configuration du **lecteur de code‑barres C#**,


## Que devriez‑vous apprendre ensuite ?


Les tutoriels suivants couvrent des sujets étroitement liés qui s’appuient sur les techniques démontrées dans ce guide. Chaque ressource inclut des exemples de code complets et fonctionnels avec des explications pas à pas pour vous aider à maîtriser d’autres fonctionnalités de l’API et explorer des approches d’implémentation alternatives dans vos propres projets.

- [Read barcode from image C# – complete guide with Macro PDF417](/barcode/english/net/compact-pdf417-encoding/read-barcode-from-image-c-complete-guide-with-macro-pdf417/)
- [How to create macro PDF417 barcode in C# using Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/how-to-create-macro-pdf417-barcode-in-c-using-aspose-barcode/)
- [How to read PDF417 barcode c# – complete step‑by‑step guide](/barcode/english/net/compact-pdf417-encoding/how-to-read-pdf417-in-c-complete-step-by-step-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}