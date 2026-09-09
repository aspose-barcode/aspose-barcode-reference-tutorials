---
category: general
date: 2026-07-15
description: Comment lire un code‑barres PDF417 en C# et lire plusieurs codes‑barres
  à partir d’une image. Apprenez à lire une image de code‑barres en C# avec du code
  détaillé et des astuces.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to read pdf417
- read multiple barcodes
- read barcode image c#
- Aspose.BarCode PDF417
- C# barcode decoding
language: fr
lastmod: 2026-07-15
og_description: Comment lire rapidement un code‑barres PDF417 en C#. Ce guide vous
  montre comment lire plusieurs codes‑barres à partir d’une seule image et décoder
  chaque propriété.
og_image_alt: Screenshot of C# console output displaying PDF417 barcode details
og_title: Comment lire le PDF417 en C# – Exemple complet de code et explication
schemas:
- author: Aspose
  dateModified: '2026-07-15'
  description: How to read PDF417 barcode in C# and read multiple barcodes from an
    image. Learn to read barcode image C# with detailed code and tips.
  headline: How to Read PDF417 in C# – Complete Step‑by‑Step Guide
  type: TechArticle
- description: How to read PDF417 barcode in C# and read multiple barcodes from an
    image. Learn to read barcode image C# with detailed code and tips.
  name: How to Read PDF417 in C# – Complete Step‑by‑Step Guide
  steps:
  - name: Why This Code Works
    text: '* **`BarCodeReader`** is the core class that streams the image, detects
      barcodes, and returns a collection of `BarCodeResult` objects. * Passing **`DecodeType.MacroPdf417`**
      tells the library to treat Macro‑PDF417 specially; it still returns plain PDF417
      symbols, which satisfies the **read multiple '
  - name: What if the image has both Macro‑PDF417 and regular PDF417 symbols?
    text: The same `BarCodeReader` call will return both. You can differentiate them
      by checking `result.CodeType` (`MacroPdf417` vs `Pdf417`). The extended properties
      will be `null` for a plain PDF417, so the `if (macro != null)` guard prevents
      a `NullReferenceException`.
  - name: My barcode is rotated or skewed—will the reader still work?
    text: Aspose.BarCode includes built‑in rotation and distortion compensation. As
      long as the barcode is at least 30 % of the image width, the decoder will usually
      succeed. For extreme cases you can enable `reader.Options.AllowInvertedBarcodes
      = true;` before calling `ReadBarCodes()`.
  - name: How do I handle large batches of images?
    text: Wrap the reading logic in a `foreach (var file in Directory.GetFiles(folder,
      "*.png"))` loop. The `using` pattern ensures each image’s native resources are
      freed before the next iteration, keeping memory usage low.
  type: HowTo
tags:
- C#
- barcode
- PDF417
- Aspose
title: Comment lire le PDF417 en C# – Guide complet étape par étape
url: /fr/net/compact-pdf417-encoding/how-to-read-pdf417-in-c-complete-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Comment lire PDF417 en C# – Guide complet étape par étape

Vous vous êtes déjà demandé **comment lire PDF417** à partir d'une image en utilisant C# ? Vous n'êtes pas le seul. La plupart des développeurs se heurtent à un mur lorsqu'ils doivent extraire les champs étendus Macro‑PDF417 d'un document numérisé. La bonne nouvelle ? En quelques lignes de code, vous pouvez décoder un PDF417, lire plusieurs codes-barres dans la même image, et récupérer chaque propriété cachée offerte par la spécification.

Dans ce tutoriel, nous parcourrons un exemple concret qui montre **comment lire PDF417**, comment **lire plusieurs codes-barres** à partir d'un seul fichier, et pourquoi le code **read barcode image C#** a cette apparence. À la fin, vous disposerez d'une application console prête à l'emploi qui affiche chaque information dont vous pourriez avoir besoin — ID de fichier, ID de segment, somme de contrôle, horodatages, etc.

## Prérequis

* .NET 6.0 SDK ou version ultérieure (le code fonctionne également avec .NET Core et .NET Framework).  
* Visual Studio 2022 (ou tout éditeur de votre choix).  
* Le package NuGet **Aspose.BarCode for .NET** – c’est la bibliothèque qui analyse réellement le PDF417.  
* Une image d'exemple contenant un code-barres Macro‑PDF417 (par exemple `ExtPDF417Meta.png`).  

Aucune configuration supplémentaire n'est requise ; la bibliothèque est fournie avec tous les décodeurs dont vous avez besoin.

## Étape 1 : Installer Aspose.BarCode

Ouvrez le dossier de votre projet dans un terminal et exécutez :

```bash
dotnet add package Aspose.BarCode
```

Cette commande récupère la dernière version stable (en juillet 2026, c’est la 23.12). Si vous préférez la console du gestionnaire de packages dans Visual Studio, utilisez :

```powershell
Install-Package Aspose.BarCode
```

> **Astuce :** verrouillez la version (`23.12.0`) dans votre `.csproj` pour éviter des changements incompatibles accidentels plus tard.

## Étape 2 : Créer la structure d’une application console

Créez un nouveau projet console si vous n’en avez pas déjà un :

```bash
dotnet new console -n Pdf417ReaderDemo
cd Pdf417ReaderDemo
```

Remplacez le `Program.cs` généré automatiquement par le code ci‑dessous. Nous expliquerons chaque bloc dans les sections suivantes.

## Étape 3 : Écrire le code complet « How to Read PDF417 »

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

namespace Pdf417ReaderDemo
{
    class Program
    {
        static void Main(string[] args)
        {
            // -----------------------------------------------------------------
            // 1️⃣  Set the path to the image that contains one or more PDF417 codes
            // -----------------------------------------------------------------
            string imagePath = @"YOUR_DIRECTORY/ExtPDF417Meta.png";

            // -----------------------------------------------------------------
            // 2️⃣  Initialise the BarCodeReader for MacroPdf417 decoding
            // -----------------------------------------------------------------
            // The DecodeType flag tells Aspose to look specifically for Macro‑PDF417,
            // but it will also pick up plain PDF417 symbols that happen to be in the
            // same image – perfect for the “read multiple barcodes” scenario.
            using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
            {
                // -----------------------------------------------------------------
                // 3️⃣  Iterate over every barcode found in the image
                // -----------------------------------------------------------------
                foreach (BarCodeResult result in reader.ReadBarCodes())
                {
                    // -------------------------------------------------------------
                    // 4️⃣  Basic barcode information – works for any barcode type
                    // -------------------------------------------------------------
                    Console.WriteLine($"Code Type : {result.CodeTypeName}");
                    Console.WriteLine($"Code Text : {result.CodeText}");

                    // -------------------------------------------------------------
                    // 5️⃣  Macro‑PDF417 extended properties (the real reason you’re here)
                    // -------------------------------------------------------------
                    var macro = result.Extended?.Pdf417?.MacroPdf417;
                    if (macro != null)
                    {
                        Console.WriteLine($"File ID          : {macro.FileID}");
                        Console.WriteLine($"Segment ID       : {macro.SegmentID}");
                        Console.WriteLine($"Segments Count   : {macro.SegmentsCount}");
                        Console.WriteLine($"File Name        : {macro.FileName}");
                        Console.WriteLine($"Checksum         : {macro.Checksum}");
                        Console.WriteLine($"File Size        : {macro.FileSize}");
                        Console.WriteLine($"Time Stamp       : {macro.TimeStamp}");
                        Console.WriteLine($"Addressee        : {macro.Addressee}");
                        Console.WriteLine($"Sender           : {macro.Sender}");
                        Console.WriteLine($"Terminator       : {macro.Terminator}");
                    }
                    else
                    {
                        Console.WriteLine("No Macro‑PDF417 extended data found for this barcode.");
                    }

                    Console.WriteLine(new string('-', 40)); // visual separator
                }
            }

            // -----------------------------------------------------------------
            // 6️⃣  Keep the console window open when running from VS
            // -----------------------------------------------------------------
            Console.WriteLine("Done. Press any key to exit...");
            Console.ReadKey();
        }
    }
}
```

### Pourquoi ce code fonctionne

* **`BarCodeReader`** est la classe principale qui charge l'image, détecte les codes‑barres et renvoie une collection d'objets `BarCodeResult`.  
* Passer **`DecodeType.MacroPdf417`** indique à la bibliothèque de traiter spécialement le Macro‑PDF417 ; elle renvoie toujours des symboles PDF417 simples, ce qui satisfait le besoin de **read multiple barcodes**.  
* L'objet **`Extended.Pdf417.MacroPdf417`** contient chaque champ optionnel défini par la norme ISO/IEC 15438 – c’est là que vous obtenez `FileID`, `SegmentID`, `Checksum`, etc.  
* Le bloc `using` garantit la libération des ressources natives, évitant les fuites de mémoire dans les services de longue durée.

## Étape 4 : Exécuter l’application et vérifier la sortie

Depuis le terminal :

```bash
dotnet run
```

Vous devriez voir quelque chose comme :

```
Code Type : MacroPdf417
Code Text : 1234567890...
File ID          : 12
Segment ID       : 1
Segments Count   : 3
File Name        : invoice2024.pdf
Checksum         : 9A3F
File Size        : 245760
Time Stamp       : 2024-11-02T14:23:00Z
Addressee        : Acme Corp
Sender           : Logistics Dept
Terminator       : 1
----------------------------------------
Done. Press any key to exit...
```

Si l'image contient plus d'un code‑barres, la boucle affichera une ligne de séparation (`----------------------------------------`) et continuera avec le résultat suivant — exactement ce à quoi ressemble **read multiple barcodes** en pratique.

## Questions fréquentes & cas particuliers

### Et si l'image contient à la fois des symboles Macro‑PDF417 et PDF417 classiques ?

Le même appel `BarCodeReader` renverra les deux. Vous pouvez les différencier en vérifiant `result.CodeType` (`MacroPdf417` vs `Pdf417`). Les propriétés étendues seront `null` pour un PDF417 simple, ainsi la condition `if (macro != null)` empêche une `NullReferenceException`.

### Mon code‑barres est tourné ou déformé — le lecteur fonctionnera‑t‑il toujours ?

Aspose.BarCode inclut une compensation intégrée de rotation et de distorsion. Tant que le code‑barres occupe au moins 30 % de la largeur de l'image, le décodeur réussira généralement. Dans les cas extrêmes, vous pouvez activer `reader.Options.AllowInvertedBarcodes = true;` avant d’appeler `ReadBarCodes()`.

### Comment gérer de gros lots d'images ?

Enveloppez la logique de lecture dans une boucle `foreach (var file in Directory.GetFiles(folder, "*.png"))`. Le modèle `using` garantit que les ressources natives de chaque image sont libérées avant l’itération suivante, maintenant ainsi une faible consommation de mémoire.

## Listing complet du code source (prêt à copier-coller)

Ci‑dessous se trouve le programme complet en un seul bloc pour un copier-coller rapide. Aucune dépendance cachée — uniquement le package NuGet Aspose.BarCode.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

namespace Pdf417ReaderDemo
{
    class Program
    {
        static void Main(string[] args)
        {
            string imagePath = @"YOUR_DIRECTORY/ExtPDF417Meta.png";

            using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
            {
                foreach (BarCodeResult result in reader.ReadBarCodes())
                {
                    Console.WriteLine($"Code Type : {result.CodeTypeName}");
                    Console.WriteLine($"Code Text : {result.CodeText}");

                    var macro = result.Extended?.Pdf417?.MacroPdf417;
                    if (macro != null)
                    {
                        Console.WriteLine($"File ID          : {macro.FileID}");
                        Console.WriteLine($"Segment ID       : {macro.SegmentID}");
                        Console.WriteLine($"Segments Count   : {macro.SegmentsCount}");
                        Console.WriteLine($"File Name        : {macro.FileName}");
                        Console.WriteLine($"Checksum         : {macro.Checksum}");
                        Console.WriteLine($"File Size        : {macro.FileSize}");
                        Console.WriteLine($"Time Stamp       : {macro.TimeStamp}");
                        Console.WriteLine($"Addressee        : {macro.Addressee}");
                        Console.WriteLine($"Sender           : {macro.Sender}");
                        Console.WriteLine($"Terminator       : {macro.Terminator}");
                    }
                    else
                    {
                        Console.WriteLine("No Macro‑PDF417 extended data found for this barcode.");
                    }

                    Console.WriteLine(new string('-', 40));
                }
            }

            Console.WriteLine("Done. Press any key to exit...");
            Console.ReadKey();
        }
    }
}
```

## Récapitulatif – Ce que nous avons couvert

* **Comment lire PDF417** avec Aspose.BarCode en C#.  
* Les étapes exactes pour **read multiple barcodes** à partir d’une seule image.  
* Comment **read barcode image C#** et extraire chaque champ Macro‑PDF417.  
* Astuces pour la rotation, le traitement par lots et la gestion des données étendues manquantes.

## Prochaines étapes & sujets associés

* **Encode PDF417** – générez vos propres codes‑barres Macro‑PDF417 avec `BarCodeBuilder`.  
* **Read other 2‑D symbologies** – QR, DataMatrix, Aztec – en utilisant la même classe `BarCodeReader`.  
* **Integrate with ASP.NET Core** – exposez un point de terminaison web qui accepte une image téléchargée et renvoie du JSON avec les champs décodés.  

N’hésitez pas à expérimenter : modifiez le chemin de l’image, déposez un PDF417 simple dans le même dossier, ou ajustez les indicateurs `DecodeType` pour voir comment la bibliothèque se comporte. Plus vous jouez, plus vous serez à l’aise avec les scénarios **read barcode image C#**.

Vous avez une image difficile qui refuse de se décoder ? Laissez un commentaire ci‑dessous ou ouvrez une issue sur le dépôt GitHub du projet d’exemple. Bon codage !

## Que devriez‑vous apprendre ensuite ?

Les tutoriels suivants couvrent des sujets étroitement liés qui s’appuient sur les techniques démontrées dans ce guide. Chaque ressource comprend des exemples de code complets et fonctionnels avec des explications étape par étape pour vous aider à maîtriser des fonctionnalités d’API supplémentaires et explorer des approches d’implémentation alternatives dans vos propres projets.

- [How to Read DataMatrix Barcodes with Aspose.BarCode for .NET](/barcode/english/net/datamatrix-barcode-reading/)
- [How to Create Barcode – Compact PDF417 with Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [Read DataMatrix barcode C# – Generate DataMatrix Mode (Auto)](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-auto/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}