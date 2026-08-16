---
category: general
date: 2026-08-15
description: Lire un code‑barres à partir d’une image en C# avec BarCodeReader. Apprenez
  à lire plusieurs codes‑barres en C#, à lire le code‑barres PDF417 et à consulter
  un exemple complet de BarCodeReader en C#.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- read barcode from image
- read multiple barcodes c#
- how to read pdf417 barcode
- c# barcodereader example
language: fr
lastmod: 2026-08-15
og_description: Lire un code‑barres à partir d’une image en C# avec un guide étape
  par étape. Découvrez comment lire plusieurs codes‑barres en C#, décoder les symboles
  PDF417 et exécuter un exemple complet de BarCodeReader en C#.
og_image_alt: Screenshot of C# code that reads barcode from image using BarCodeReader
og_title: Lire un code‑barres à partir d’une image en C# – Tutoriel BarCodeReader
schemas:
- author: Aspose
  dateModified: '2026-08-15'
  description: Read barcode from image in C# using BarCodeReader. Learn how to read
    multiple barcodes C#, read PDF417 barcode, and see a full C# BarCodeReader example.
  headline: Read barcode from image in C# – BarCodeReader tutorial
  type: TechArticle
tags:
- barcode
- C#
- .NET
- image processing
title: Lire le code‑barres à partir d’une image en C# – Tutoriel BarCodeReader
url: /fr/net/one-dimensional-barcode-types/read-barcode-from-image-in-c-barcodereader-tutorial/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Lire un code‑barres à partir d’une image en C# – Tutoriel BarCodeReader

Si vous devez **lire un code‑barres à partir d’une image** dans une application .NET, ce guide vous montre exactement comment le faire avec la classe `BarCodeReader`. Vous verrez également comment **lire plusieurs codes‑barres C#**, décoder un symbole PDF417, et obtenir un **exemple complet C# BarCodeReader** que vous pouvez copier dans votre projet.

Le tutoriel couvre chaque étape — de l’ajout du package NuGet requis à l’affichage des champs PDF417 étendus— afin que vous terminiez avec un programme console exécutable. Aucune documentation externe n’est nécessaire ; tout le code et les explications sont inclus.

## Ce dont vous aurez besoin

Avant de commencer, assurez‑vous d’avoir :

* SDK .NET 6.0 ou ultérieur (le code fonctionne avec .NET Core et .NET Framework)
* Visual Studio 2022 ou tout éditeur compatible C#
* Le package NuGet `Aspose.BarCode` (ou la bibliothèque équivalente qui fournit `BarCodeReader`)
* Un fichier image contenant un code‑barres Macro PDF417 (par ex. `ExtPDF417Meta.png`)

Disposer de ces prérequis garantit que l’exemple se compile sans configuration supplémentaire.

## Lire un code‑barres à partir d’une image avec BarCodeReader

La première étape consiste à créer une instance de `BarCodeReader` qui pointe vers le fichier image et indique à la bibliothèque quel type de code‑barres rechercher.

```csharp
using System;
using Aspose.BarCode;               // Namespace for BarCodeReader
using Aspose.BarCode.BarCodeRecognition; // DecodeType enum

class Program
{
    static void Main()
    {
        // Path to the image that holds the Macro PDF417 barcode
        const string imagePath = @"YOUR_DIRECTORY/ExtPDF417Meta.png";

        // Initialize the reader for Macro PDF417 barcodes only
        using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
        {
            // Read all barcodes present in the image
            foreach (BarCodeResult result in reader.ReadBarCodes())
            {
                // Basic barcode information
                Console.WriteLine($"Code Type : {result.CodeTypeName}");
                Console.WriteLine($"Code Text : {result.CodeText}");

                // Extended Macro PDF417 fields (available only for this type)
                Console.WriteLine($"File ID          : {result.Extended.Pdf417.MacroPdf417FileID}");
                Console.WriteLine($"Segment ID       : {result.Extended.Pdf417.MacroPdf417SegmentID}");
                Console.WriteLine($"Segments Count   : {result.Extended.Pdf417.MacroPdf417SegmentsCount}");
                Console.WriteLine($"File Name        : {result.Extended.Pdf417.MacroPdf417FileName}");
                Console.WriteLine($"Checksum         : {result.Extended.Pdf417.MacroPdf417Checksum}");
                Console.WriteLine($"File Size        : {result.Extended.Pdf417.MacroPdf417FileSize}");
                Console.WriteLine($"Time Stamp       : {result.Extended.Pdf417.MacroPdf417TimeStamp}");
                Console.WriteLine($"Addressee        : {result.Extended.Pdf417.MacroPdf417Addressee}");
                Console.WriteLine($"Sender           : {result.Extended.Pdf417.MacroPdf417Sender}");
                Console.WriteLine($"Terminator Flag  : {result.Extended.Pdf417.MacroPdf417Terminator}");
                Console.WriteLine(new string('-', 40));
            }
        }
    }
}
```

**Pourquoi cela fonctionne :**  
`BarCodeReader` ouvre l’image, scanne le `DecodeType` spécifié et renvoie une collection d’objets `BarCodeResult`. Chaque résultat contient les données génériques du code‑barres (`CodeTypeName`, `CodeText`) et, pour Macro PDF417, un objet `Extended.Pdf417` qui expose tous les champs supplémentaires définis par la norme.

## Lire plusieurs codes‑barres C# dans une même image

Parfois, une image contient plus d’un code‑barres (par ex. un QR code à côté d’un PDF417). Pour gérer ce scénario, il suffit d’omettre le `DecodeType` explicite ou de passer `DecodeType.AllSupported` et de parcourir les résultats.

```csharp
using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.AllSupported))
{
    foreach (BarCodeResult result in reader.ReadBarCodes())
    {
        Console.WriteLine($"Found {result.CodeTypeName}: {result.CodeText}");
    }
}
```

**Pourquoi vous avez besoin de cela :**  
Spécifier `AllSupported` indique au moteur d’essayer tous les formats de code‑barres qu’il connaît, ce qui garantit que vous capturez chaque symbole présent dans l’image. C’est l’approche recommandée lorsque vous ne pouvez pas prédire à l’avance les types de code‑barres.

## Comment lire un code‑barres PDF417 avec C#

Si vous ne vous intéressez qu’au format PDF417 classique (non‑macro), changez le `DecodeType` en `Pdf417`. Le reste du code reste identique, à l’exception du fait que les champs étendus ne sont pas disponibles.

```csharp
using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.Pdf417))
{
    foreach (BarCodeResult result in reader.ReadBarCodes())
    {
        Console.WriteLine($"PDF417 text: {result.CodeText}");
    }
}
```

**Pourquoi c’est important :**  
Le PDF417 classique n’expose pas les propriétés spécifiques au macro, donc le bloc `Extended.Pdf417` est inutile. Utiliser le `DecodeType` précis accélère également le scan car la bibliothèque ignore les algorithmes non pris en charge.

## Exemple complet C# BarCodeReader que vous pouvez copier

Voici le programme complet qui combine les trois scénarios en une seule application console facile à exécuter. Remplacez `YOUR_DIRECTORY/ExtPDF417Meta.png` par le chemin réel de votre image.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

class Program
{
    static void Main()
    {
        const string imagePath = @"YOUR_DIRECTORY/ExtPDF417Meta.png";

        // 1️⃣ Read Macro PDF417 and show extended fields
        Console.WriteLine("=== Macro PDF417 ===");
        ReadMacroPdf417(imagePath);

        // 2️⃣ Read any barcode type present (multiple barcodes)
        Console.WriteLine("\n=== All supported barcodes ===");
        ReadAllBarcodes(imagePath);

        // 3️⃣ Read classic PDF417 only
        Console.WriteLine("\n=== Classic PDF417 ===");
        ReadClassicPdf417(imagePath);
    }

    static void ReadMacroPdf417(string path)
    {
        using (BarCodeReader reader = new BarCodeReader(path, DecodeType.MacroPdf417))
        {
            foreach (BarCodeResult result in reader.ReadBarCodes())
            {
                Console.WriteLine($"Code Type : {result.CodeTypeName}");
                Console.WriteLine($"Code Text : {result.CodeText}");
                Console.WriteLine($"File ID   : {result.Extended.Pdf417.MacroPdf417FileID}");
                // ... other extended fields omitted for brevity
                Console.WriteLine(new string('-', 30));
            }
        }
    }

    static void ReadAllBarcodes(string path)
    {
        using (BarCodeReader reader = new BarCodeReader(path, DecodeType.AllSupported))
        {
            foreach (BarCodeResult result in reader.ReadBarCodes())
            {
                Console.WriteLine($"{result.CodeTypeName}: {result.CodeText}");
            }
        }
    }

    static void ReadClassicPdf417(string path)
    {
        using (BarCodeReader reader = new BarCodeReader(path, DecodeType.Pdf417))
        {
            foreach (BarCodeResult result in reader.ReadBarCodes())
            {
                Console.WriteLine($"PDF417 text: {result.CodeText}");
            }
        }
    }
}
```

### Résultat attendu

Lorsque l’image d’exemple contient un code‑barres Macro PDF417, la console affiche quelque chose de similaire à :

```
=== Macro PDF417 ===
Code Type : MacroPdf417
Code Text : 1234567890
File ID   : 5
Segment ID       : 2
Segments Count   : 3
File Name        : report.pdf
Checksum         : 0x1A2B
File Size        : 84212
Time Stamp       : 2024-03-15T10:22:31Z
Addressee        : John Doe
Sender           : Acme Corp
Terminator Flag  : True
------------------------------

=== All supported barcodes ===
MacroPdf417: 1234567890
QrCode: https://example.com

=== Classic PDF417 ===
PDF417 text: 0987654321
```

Si l’image ne contient qu’un PDF417 ordinaire, la section « Macro PDF417 » sera vide et la section « Classic PDF417 » affichera le texte décodé.

## Conclusion

Vous savez maintenant comment **lire un code‑barres à partir d’une image** en C# avec `BarCodeReader`, comment **lire plusieurs codes‑barres C#** dans un même fichier, et les étapes exactes pour **lire un code‑barres PDF417**—tant la variante macro que la variante classique. L’**exemple complet C# BarCodeReader** est prêt à être collé dans n’importe quel projet .NET, et vous pouvez l’étendre pour gérer d’autres formats ou l’intégrer à une chaîne de traitement d’images plus large.

**Prochaines étapes**

* Explorez les modèles de gestion des erreurs tels que `try / catch` autour du bloc lecteur.  
* Expérimentez avec l’objet `ReaderParameters` pour ajuster la vitesse et la précision de la détection.  
* Combinez la lecture de code‑barres avec des bibliothèques de prétraitement d’image (


## Que devriez‑vous apprendre ensuite ?


Les tutoriels suivants couvrent des sujets étroitement liés qui s’appuient sur les techniques démontrées dans ce guide. Chaque ressource comprend des exemples de code fonctionnels complets avec des explications pas à pas pour vous aider à maîtriser d’autres fonctionnalités de l’API et à explorer des approches d’implémentation alternatives dans vos propres projets.

- [Comment lire les codes‑barres DataMatrix avec Aspose.BarCode pour .NET](/barcode/english/net/datamatrix-barcode-reading/)
- [Lire un code‑barres DataMatrix C# – Générer le mode DataMatrix (Auto)](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-auto/)
- [Lire un code‑barres à partir d’une image – Maîtriser l’extraction de région de code‑barres en Java avec Aspose.BarCode](/barcode/english/java/advanced-settings-and-optimization/extracting-barcode-region-information/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}