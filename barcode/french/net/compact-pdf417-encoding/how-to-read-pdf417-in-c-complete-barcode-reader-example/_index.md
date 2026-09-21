---
category: general
date: 2026-07-21
description: Comment lire un code‑barres PDF417 en C# à l’aide d’un exemple concis
  de lecteur de code‑barres. Apprenez rapidement à lire un code‑barres à partir d’une
  image avec un code étape par étape.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to read pdf417
- read barcode from image
- c# barcode reader example
language: fr
lastmod: 2026-07-21
og_description: Comment lire le code‑barres PDF417 en C# avec un exemple pratique.
  Découvrez comment lire le code‑barres à partir d’une image et intégrer immédiatement
  l’exemple de lecteur de code‑barres C#.
og_image_alt: Screenshot of a C# console app printing PDF417 barcode details
og_title: Comment lire le PDF417 en C# – Guide complet du lecteur de codes-barres
schemas:
- author: Aspose
  dateModified: '2026-07-21'
  description: How to read PDF417 barcode in C# using a concise barcode reader example.
    Quickly learn how to read barcode from image with step‑by‑step code.
  headline: How to Read PDF417 in C# – Complete Barcode Reader Example
  type: TechArticle
- description: How to read PDF417 barcode in C# using a concise barcode reader example.
    Quickly learn how to read barcode from image with step‑by‑step code.
  name: How to Read PDF417 in C# – Complete Barcode Reader Example
  steps:
  - name: Why This Works
    text: '- **`DecodeType.MacroPdf417`** tells the reader to expect the extended
      Macro PDF417 format, which carries extra metadata (file ID, segment count, timestamps,
      etc.). - The **`Extended.Pdf417`** object is only populated for Macro PDF417
      barcodes, so accessing those properties is safe after the `ReadBa'
  - name: Multiple Barcodes in One Image
    text: Sometimes a single scan contains more than one PDF417 segment (think of
      a multi‑page document encoded across several symbols). The `foreach` loop already
      enumerates *all* detected barcodes, so you don’t need extra logic—just collect
      the segments and reassemble them later if required.
  - name: Missing Extended Data
    text: 'Not every PDF417 carries macro information. In that scenario `result.Extended.Pdf417`
      will be instantiated but its fields will be default values (zero, empty string,
      or `false`). You can guard against it like this:'
  - name: Performance Tips
    text: '- **Batch processing:** If you have a folder of images, wrap the `BarCodeReader`
      creation inside a loop that reuses the same instance with `barcodeReader.SetImage(imagePath)`.
      This reduces allocation overhead. - **Parallelism:** For large workloads, consider
      `Parallel.ForEach` on the file list, but '
  type: HowTo
tags:
- barcode
- pdf417
- csharp
title: Comment lire le PDF417 en C# – Exemple complet de lecteur de code‑barres
url: /fr/net/compact-pdf417-encoding/how-to-read-pdf417-in-c-complete-barcode-reader-example/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Comment lire le PDF417 en C# – Exemple complet de lecteur de code-barres

Vous vous êtes déjà demandé **comment lire le PDF417** dans un projet .NET sans fouiller dans d'innombrables documents ? Vous n'êtes pas le seul. Que vous scanniez des permis de conduire, des cartes d'embarquement ou des étiquettes d'inventaire personnalisées, extraire ces données de manière fiable est un besoin réel.

Dans ce guide, nous parcourrons un **exemple de lecteur de code-barres c#** qui extrait chaque morceau de métadonnées Macro PDF417 d'un fichier image unique. À la fin, vous disposerez d'une application console prête à l'emploi qui **lit le code-barres depuis une image** et affiche tous les champs étendus dont vous pourriez avoir besoin.

## Ce dont vous avez besoin

- .NET 6.0 SDK ou version ultérieure (vous pouvez également cibler .NET Framework 4.7+ – le code fonctionne de la même façon)
- Visual Studio 2022, VS Code, ou tout éditeur C# de votre choix
- Le package NuGet **Aspose.BarCode for .NET** (la classe `BarCodeReader` provient de cette bibliothèque)
- Un fichier image contenant un code-barres Macro PDF417 (pour la démo, nous utiliserons `ExtPDF417Meta.png`)

> **Astuce :** Si vous n’avez pas d’exemple PDF417 sous la main, Aspose fournit quelques images de test dans leur dépôt GitHub – téléchargez‑en simplement une et placez‑la dans le dossier de votre projet.

## Étape 1 : Installer la bibliothèque de codes‑barres

Ouvrez un terminal dans le dossier de votre projet et exécutez :

```bash
dotnet add package Aspose.BarCode
```

Le package ajoute les classes `BarCodeReader`, `DecodeType` et la propriété `Extended` dont nous aurons besoin plus tard. Aucune configuration supplémentaire n’est requise ; la bibliothèque fonctionne immédiatement pour la plupart des formats d’image (PNG, JPEG, BMP, etc.).

## Étape 2 : Créer une application console minimale

Créez un nouveau projet console si ce n’est pas déjà fait :

```bash
dotnet new console -n Pdf417ReaderDemo
cd Pdf417ReaderDemo
```

Remplacez le `Program.cs` généré par le code ci‑dessous. Notez comment chaque section est commentée afin que vous puissiez suivre la logique même si vous débutez dans le traitement des codes‑barres.

```csharp
using System;
using Aspose.BarCode;               // Core barcode classes
using Aspose.BarCode.BarCodeRecognition; // DecodeType enum

class Program
{
    static void Main()
    {
        // 👉 1️⃣  Point the reader at the image that holds the Macro PDF417 barcode.
        //    Replace the path with your own image location if needed.
        string imagePath = "YOUR_DIRECTORY/ExtPDF417Meta.png";

        // The BarCodeReader is disposable – using a using‑statement guarantees resources are freed.
        using (BarCodeReader barcodeReader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
        {
            // 👉 2️⃣  Iterate over every barcode that the reader finds.
            //    Macro PDF417 can embed multiple segments, so we handle them all.
            foreach (BarCodeResult result in barcodeReader.ReadBarCodes())
            {
                // Basic barcode info – always handy for logging.
                Console.WriteLine($"CodeType: {result.CodeTypeName}");
                Console.WriteLine($"CodeText: {result.CodeText}");

                // 👉 3️⃣  Pull out the extended Macro PDF417 fields.
                //    These properties live under result.Extended.Pdf417.
                var macro = result.Extended.Pdf417;

                Console.WriteLine($"Pdf417MacroFileID: {macro.MacroPdf417FileID}");
                Console.WriteLine($"Pdf417MacroSegmentID: {macro.MacroPdf417SegmentID}");
                Console.WriteLine($"Pdf417MacroSegmentsCount: {macro.MacroPdf417SegmentsCount}");
                Console.WriteLine($"Pdf417MacroFileName: {macro.MacroPdf417FileName}");
                Console.WriteLine($"Pdf417MacroChecksum: {macro.MacroPdf417Checksum}");
                Console.WriteLine($"Pdf417MacroFileSize: {macro.MacroPdf417FileSize}");
                Console.WriteLine($"Pdf417MacroTimeStamp: {macro.MacroPdf417TimeStamp}");
                Console.WriteLine($"Pdf417MacroAddressee: {macro.MacroPdf417Addressee}");
                Console.WriteLine($"Pdf417MacroSender: {macro.MacroPdf417Sender}");
                Console.WriteLine($"MacroPdf417Terminator: {macro.MacroPdf417Terminator}");
                Console.WriteLine(new string('-', 40)); // visual separator
            }
        }

        // Keep the console window open when debugging.
        Console.WriteLine("Done. Press any key to exit...");
        Console.ReadKey();
    }
}
```

### Pourquoi cela fonctionne

- **`DecodeType.MacroPdf417`** indique au lecteur d’attendre le format Macro PDF417 étendu, qui transporte des métadonnées supplémentaires (ID de fichier, nombre de segments, horodatages, etc.).
- L’objet **`Extended.Pdf417`** n’est rempli que pour les codes‑barres Macro PDF417, ainsi l’accès à ces propriétés est sûr après l’appel `ReadBarCodes()`.
- L’utilisation d’un bloc **`using`** garantit que les handles de fichiers sont libérés, évitant les problèmes de verrouillage de fichier sous Windows.

## Étape 3 : Exécuter l’application

Compilez et exécutez :

```bash
dotnet run
```

Si l’image contient un code‑barres Macro PDF417 valide, vous devriez voir une sortie similaire à :

```
CodeType: MacroPdf417
CodeText: 1234567890
Pdf417MacroFileID: 1
Pdf417MacroSegmentID: 0
Pdf417MacroSegmentsCount: 3
Pdf417MacroFileName: SampleDocument.pdf
Pdf417MacroChecksum: 0xABCD
Pdf417MacroFileSize: 102400
Pdf417MacroTimeStamp: 2024-03-15T10:23:45Z
Pdf417MacroAddressee: John Doe
Pdf417MacroSender: Acme Corp
MacroPdf417Terminator: True
----------------------------------------
Done. Press any key to exit...
```

Si rien n’est affiché, vérifiez que le chemin de l’image est correct et que le code‑barres est bien une variante Macro PDF417. Un PDF417 standard (sans l’extension macro) sera tout de même décodé, mais les propriétés `Extended` seront vides.

## Gestion des cas limites

### Plusieurs codes‑barres dans une même image

Parfois, une seule numérisation contient plus d’un segment PDF417 (pensez à un document multi‑pages encodé sur plusieurs symboles). La boucle `foreach` énumère déjà *tous* les codes‑barres détectés, vous n’avez donc pas besoin de logique supplémentaire — il suffit de collecter les segments et de les réassembler plus tard si nécessaire.

### Données étendues manquantes

Tous les PDF417 ne contiennent pas d’informations macro. Dans ce cas, `result.Extended.Pdf417` sera instancié mais ses champs auront des valeurs par défaut (zéro, chaîne vide ou `false`). Vous pouvez vous en prémunir ainsi :

```csharp
if (macro.MacroPdf417FileID != 0)
{
    // Process macro data
}
else
{
    Console.WriteLine("No macro information present in this barcode.");
}
```

### Conseils de performance

- **Traitement par lots :** Si vous avez un dossier d’images, encapsulez la création du `BarCodeReader` dans une boucle qui réutilise la même instance avec `barcodeReader.SetImage(imagePath)`. Cela réduit la surcharge d’allocation.
- **Parallélisme :** Pour de gros volumes, envisagez `Parallel.ForEach` sur la liste de fichiers, mais gardez à l’esprit que le lecteur Aspose n’est thread‑safe que lorsque chaque thread utilise sa propre instance de `BarCodeReader`.

## Listing complet du code source (prêt à copier‑coller)

Voici à nouveau le programme complet, prêt à être placé dans `Program.cs`. Aucun fichier supplémentaire n’est nécessaire en dehors de l’image.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

class Program
{
    static void Main()
    {
        string imagePath = "YOUR_DIRECTORY/ExtPDF417Meta.png";

        using (BarCodeReader barcodeReader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
        {
            foreach (BarCodeResult result in barcodeReader.ReadBarCodes())
            {
                Console.WriteLine($"CodeType: {result.CodeTypeName}");
                Console.WriteLine($"CodeText: {result.CodeText}");

                var macro = result.Extended.Pdf417;

                Console.WriteLine($"Pdf417MacroFileID: {macro.MacroPdf417FileID}");
                Console.WriteLine($"Pdf417MacroSegmentID: {macro.MacroPdf417SegmentID}");
                Console.WriteLine($"Pdf417MacroSegmentsCount: {macro.MacroPdf417SegmentsCount}");
                Console.WriteLine($"Pdf417MacroFileName: {macro.MacroPdf417FileName}");
                Console.WriteLine($"Pdf417MacroChecksum: {macro.MacroPdf417Checksum}");
                Console.WriteLine($"Pdf417MacroFileSize: {macro.MacroPdf417FileSize}");
                Console.WriteLine($"Pdf417MacroTimeStamp: {macro.MacroPdf417TimeStamp}");
                Console.WriteLine($"Pdf417MacroAddressee: {macro.MacroPdf417Addressee}");
                Console.WriteLine($"Pdf417MacroSender: {macro.MacroPdf417Sender}");
                Console.WriteLine($"MacroPdf417Terminator: {macro.MacroPdf417Terminator}");
                Console.WriteLine(new string('-', 40));
            }
        }

        Console.WriteLine("Done. Press any key to exit...");
        Console.ReadKey();
    }
}
```

## Récapitulatif : Comment lire le PDF417 en C# rapidement

- Installez **Aspose.BarCode** via NuGet.
- Pointez un `BarCodeReader` sur votre image avec `DecodeType.MacroPdf417`.
- Parcourez `ReadBarCodes()` et récupérez les champs de base ainsi que les champs étendus.
- Gérez les données macro manquantes avec élégance et envisagez des ajustements de performance pour les analyses en masse.

## Prochaines étapes et sujets associés

- **Lire un code‑barres depuis une image** en utilisant d’autres formats (QR, DataMatrix) – il suffit de changer l’énumération `DecodeType`.
- **Encoder du PDF417** avec `BarCodeGenerator` si vous devez créer des codes‑barres programmatiquement.
- Explorez les **niveaux de correction d’erreur** et leur impact sur la fiabilité du scan.
- Intégrez cette logique dans une API ASP.NET Core pour exposer la lecture de codes‑barres en tant que service web.

N’hésitez pas à expérimenter : changez l’image, jouez avec le drapeau `DecodeType`, ou alimentez les données macro dans une base de données. Le modèle de base reste le même, et vous disposez désormais d’un solide **exemple de lecteur de code‑barres c#** dans votre boîte à outils.

Bon codage, et que vos scans soient toujours impeccables !

## Que devriez‑vous apprendre ensuite ?

Les tutoriels suivants couvrent des sujets étroitement liés qui s’appuient sur les techniques démontrées dans ce guide. Chaque ressource comprend des exemples de code complets et fonctionnels avec des explications étape par étape pour vous aider à maîtriser des fonctionnalités supplémentaires de l’API et explorer des approches d’implémentation alternatives dans vos propres projets.

- [Comment lire les codes‑barres DataMatrix avec Aspose.BarCode pour .NET](/barcode/english/net/datamatrix-barcode-reading/)
- [Comment créer un code‑barres – PDF417 compact avec Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [Comment créer une zone silencieuse de code‑barres pour Code 16K en utilisant Aspose.BarCode pour .NET](/barcode/english/net/code-16k-encoding/code-16k-quiet-zone-settings/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}