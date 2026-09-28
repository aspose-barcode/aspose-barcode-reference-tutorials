---
category: general
date: 2026-09-28
description: Lisez le barcode PDF417 c# rapidement avec Aspose.BarCode. Décodez plusieurs
  barcodes à partir d’une image, extrayez les champs Macro‑PDF417 et gérez la rotation
  ou le traitement par lots.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- read pdf417 barcode c#
- read multiple barcodes
- pdf417 c# decoding
- Aspose.BarCode PDF417
- barcode image c#
lastmod: 2026-09-28
og_description: Lisez le barcode PDF417 c# rapidement avec Aspose.BarCode. Ce guide
  montre comment décoder plusieurs barcodes à partir d’une seule image, extraire toutes
  les propriétés Macro‑PDF417 et gérer les images tournées ou en lot.
og_image_alt: Screenshot of C# console output displaying PDF417 barcode details
og_title: Lire le barcode PDF417 c# – exemple complet de code & guide
schemas:
- author: Aspose
  dateModified: '2026-09-28'
  description: Read PDF417 barcode c# and read multiple barcodes from an image. Learn
    to read barcode image C# with detailed code and tips.
  headline: Read PDF417 barcode c# – complete step‑by‑step guide
  type: TechArticle
- description: Read PDF417 barcode c# and read multiple barcodes from an image. Learn
    to read barcode image C# with detailed code and tips.
  name: Read PDF417 barcode c# – complete step‑by‑step guide
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
title: Comment lire le barcode PDF417 c# – guide complet étape par étape
url: /fr/net/compact-pdf417-encoding/how-to-read-pdf417-in-c-complete-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Comment lire le code‑barres PDF417 c# – guide complet étape par étape

Vous vous êtes déjà demandé **comment lire le PDF417** à partir d'une image en utilisant C# ? Vous n'êtes pas le seul. La plupart des développeurs se heurtent à un mur lorsqu'ils doivent extraire les champs étendus Macro‑PDF417 d'un document numérisé. La bonne nouvelle ? En quelques lignes de code, vous pouvez **read PDF417 barcode c#**, décoder plusieurs codes‑barres dans la même image, et récupérer chaque propriété cachée offerte par la spécification.

## Réponses rapides
- **Aspose.BarCode peut‑il décoder Macro‑PDF417 ?** Oui – il suffit d'activer `DecodeType.MacroPdf417` et la bibliothèque renvoie tous les champs étendus.  
- **Combien de codes‑barres peuvent être lus à partir d'une image ?** Illimité ; l'API renvoie une collection d'objets `BarCodeResult`.  
- **Ai‑je besoin d'une licence pour la production ?** Une licence commerciale est requise pour une utilisation en production ; un essai gratuit suffit pour l'évaluation.  
- **Les codes‑barres tournés seront‑ils détectés ?** La compensation de rotation intégrée fonctionne pour les codes‑barres couvrant au moins 30 % de la largeur de l'image.  
- **Le traitement par lots est‑il pris en charge ?** Absolument – encapsulez le lecteur dans une boucle `foreach` et libérez chaque instance avec `using`.

## Qu'est‑ce que read PDF417 barcode c# ?
`read pdf417 barcode c#` désigne le processus d'utilisation d'une bibliothèque .NET pour décoder les symboles PDF417 (y compris Macro‑PDF417) à partir de fichiers image directement en code C#. Le SDK Aspose.BarCode fournit une API à appel unique qui gère le chargement d'image, la détection de code‑barres et l'extraction de tous les champs définis par l'ISO.

## Pourquoi utiliser Aspose.BarCode pour le décodage PDF417 ?
Aspose.BarCode prend en charge **plus de 30 symbologies de codes‑barres** et peut traiter des images jusqu'à **5000 × 5000 px** en moins de **0,1 s** sur du matériel serveur typique. Il offre également une gestion intégrée de la rotation, de la distorsion et des codes‑barres inversés, éliminant le besoin de prétraitement d'image personnalisé. De plus, la bibliothèque inclut une prise en charge native de la lecture des champs étendus Macro‑PDF417, ce qui en fait une solution tout‑en‑un pour les scénarios de numérisation complexes.

## Prérequis

Avant de plonger, assurez‑vous d'avoir :

* .NET 6.0 SDK ou version ultérieure (le code fonctionne également avec .NET Core et .NET Framework).  
* Visual Studio 2022 (ou tout éditeur de votre choix).  
* Le package NuGet **Aspose.BarCode for .NET** – c’est la bibliothèque qui analyse réellement le PDF417.  
* Une image d'exemple contenant un code‑barres Macro‑PDF417 (par exemple `ExtPDF417Meta.png`).  

Aucune configuration supplémentaire n'est requise ; la bibliothèque est fournie avec tous les décodeurs dont vous avez besoin.

## Comment lire le code‑barres PDF417 c# ?

Chargez l'image avec `BarCodeReader`, spécifiez `DecodeType.MacroPdf417`, et parcourez la collection `BarCodeResult` retournée – c’est la solution complète en moins de dix lignes de code. Le lecteur extrait automatiquement les symboles PDF417 simples ainsi que les données étendues Macro‑PDF417, vous obtenez ainsi les identifiants de fichier, numéros de segment, horodatages et sommes de contrôle sans analyse supplémentaire.

### Étape 1 : installer Aspose.BarCode

Ouvrez le dossier de votre projet dans un terminal et exécutez :

```bash
dotnet add package Aspose.BarCode
```

Cette commande récupère la dernière version stable (en juillet 2026, c’est la 23.12). Si vous préférez la console du Gestionnaire de packages dans Visual Studio, utilisez :

```powershell
Install-Package Aspose.BarCode
```

> **Astuce :** verrouillez la version (`23.12.0`) dans votre `.csproj` pour éviter des changements incompatibles accidentels plus tard.

### Étape 2 : créer une structure d'application console

Créez un nouveau projet console si vous n’en avez pas déjà un :

```bash
dotnet new console -n Pdf417ReaderDemo
cd Pdf417ReaderDemo
```

Remplacez le `Program.cs` généré automatiquement par le code ci‑dessous. Nous expliquerons chaque bloc dans les sections suivantes.

### Étape 3 : écrire le code complet « comment lire le PDF417 »

`BarCodeReader` est la classe principale qui lit le flux d'image, détecte les codes‑barres et renvoie une collection d'objets `BarCodeResult`.

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

* `BarCodeReader` — la classe principale responsable de la lecture et du décodage des codes‑barres à partir d'images.  
* `DecodeType.MacroPdf417` — un drapeau indiquant au SDK de traiter spécialement le Macro‑PDF417 tout en renvoyant les symboles PDF417 simples.  
* `Extended.Pdf417.MacroPdf417` — l'objet qui contient chaque champ optionnel défini par ISO/IEC 15438, tel que `FileID`, `SegmentID` et `Checksum`.

Le bloc `using` garantit que les ressources natives sont libérées, évitant les fuites de mémoire dans les services de longue durée.

### Étape 4 : exécuter l'application et vérifier la sortie

Depuis le terminal :

```bash
dotnet run
```

Vous devriez voir quelque chose comme :

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

Si l'image contient plus d'un code‑barres, la boucle imprime une ligne de séparation (`----------------------------------------`) et continue avec le résultat suivant — exactement ce à quoi ressemble **read multiple barcodes** en pratique.

## Questions fréquentes & cas limites

### Que se passe‑t‑il si l'image contient à la fois des symboles Macro‑PDF417 et PDF417 ordinaires ?
Le même appel `BarCodeReader` renverra les deux. Vous pouvez les différencier en vérifiant `result.CodeType` (`MacroPdf417` vs `Pdf417`). Les propriétés étendues seront `null` pour un PDF417 simple, ainsi la garde `if (macro != null)` empêche une `NullReferenceException`.

### Mon code‑barres est tourné ou incliné—le lecteur fonctionnera‑t‑il toujours ?
Aspose.BarCode inclut une compensation intégrée de la rotation et de la distorsion. Tant que le code‑barres occupe au moins 30 % de la largeur de l'image, le décodeur réussira généralement. Pour les cas extrêmes, vous pouvez activer `reader.Options.AllowInvertedBarcodes = true;` avant d’appeler `ReadBarCodes()`.

### Comment gérer de gros lots d'images ?
Encapsulez la logique de lecture dans une boucle `foreach (var file in Directory.GetFiles(folder, "*.png"))`. Le modèle `using` garantit que les ressources natives de chaque image sont libérées avant l’itération suivante, maintenant ainsi une faible consommation de mémoire.

## Listing complet du code source (prêt à copier‑coller)

Ci‑dessous se trouve le programme entier en un seul bloc pour un copier‑coller rapide. Aucun dépendance cachée — uniquement le package NuGet Aspose.BarCode.

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

## Récapitulatif – ce que nous avons couvert

* **Comment lire le code‑barres PDF417 c#** avec Aspose.BarCode.  
* Les étapes exactes pour **read multiple barcodes** à partir d'une seule image.  
* Comment **read barcode image c#** et extraire chaque champ Macro‑PDF417.  
* Conseils pour la rotation, le traitement par lots et la gestion des données étendues manquantes.

## Prochaines étapes & sujets associés

* **Encode PDF417** – générez vos propres codes‑barres Macro‑PDF417 avec `BarCodeBuilder`.  
* **Read other 2‑D symbologies** – QR, DataMatrix, Aztec – en utilisant la même classe `BarCodeReader`.  
* **Integrate with ASP.NET Core** – exposez un point de terminaison web qui accepte une image téléchargée et renvoie du JSON avec les champs décodés.  

### Liens utiles supplémentaires
- [Comment lire les codes‑barres DataMatrix avec Aspose.BarCode pour .NET](/barcode/english/net/datamatrix-barcode-reading/)  
- [Comment créer un code‑barres – Compact PDF417 avec Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)  
- [Lire le code‑barres DataMatrix C# – Générer le mode DataMatrix (Auto)](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-auto/)

N’hésitez pas à expérimenter : modifiez le chemin de l'image, déposez un PDF417 simple dans le même dossier, ou ajustez les drapeaux `DecodeType` pour voir comment la bibliothèque se comporte. Plus vous jouez, plus vous serez à l’aise avec les scénarios **read barcode image c#**.

Vous avez une image récalcitrante qui refuse de décoder ? Laissez un commentaire ci‑dessous ou ouvrez une issue sur le dépôt GitHub du projet d’exemple. Bon codage !

## Questions fréquemment posées

**Q : Puis‑je utiliser cela dans une application commerciale ?**  
R : Oui, vous pouvez utiliser Aspose.BarCode dans des projets commerciaux tant que vous disposez d’une licence valide ; un essai gratuit est disponible pour l’évaluation.

**Q : Le lecteur prend‑il en charge les images protégées par mot de passe ?**  
R : Le SDK fonctionne avec tout format d’image standard ; la protection par mot de passe ne s’applique pas aux images raster, seulement aux PDF, qui sont gérés par un composant séparé Aspose.PDF.

**Q : Quelles versions de .NET sont prises en charge ?**  
R : .NET Framework 4.5+, .NET Core 3.1+, .NET 5+ et .NET 6+ sont tous pleinement pris en charge par la version actuelle d’Aspose.BarCode.

**Q : Comment améliorer les performances pour de très gros lots d’images ?**  
R : Activez `reader.Options.Quality = QualityMode.HighPerformance` et traitez les images en parallèle avec `Parallel.ForEach` tout en encapsulant chaque `BarCodeReader` dans un bloc `using`.

**Q : Existe‑t‑il un moyen d’obtenir uniquement les champs Macro‑PDF417 sans parcourir tous les résultats ?**  
R : Oui – après avoir appelé `ReadBarCodes()`, filtrez la collection avec `result => result.CodeType == DecodeType.MacroPdf417` puis accédez à la propriété `Extended.Pdf417.MacroPdf417`.

---

**Dernière mise à jour :** 2026-09-28  
**Testé avec :** Aspose.BarCode 23.12 for .NET  
**Auteur :** Aspose

## Tutoriels associés

- [Comment générer une image de code‑barres Pdf417 en C avec Aspose](/barcode/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-image-in-c-with-aspose/)
- [Créer un code‑barres Pdf417 avec Aspose Barcode – Guide étape par étape](/barcode/net/compact-pdf417-encoding/create-pdf417-barcode-with-aspose-barcode-step-by-step-guide/)
- [Lire plusieurs codes‑barres C – Guide complet avec Pdf417](/barcode/net/compact-pdf417-encoding/read-multiple-barcodes-c-complete-guide-with-pdf417/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}