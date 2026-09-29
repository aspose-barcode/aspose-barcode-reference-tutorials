---
category: general
date: 2026-07-27
description: Comment lire rapidement un code‑barres PDF417 en C#. Apprenez à lire
  plusieurs codes‑barres, décoder des images et obtenir les métadonnées Macro PDF417
  dans un exemple complet de code‑barres C#.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to read pdf417
- read multiple barcodes
- c# barcode example
- read barcode image c#
language: fr
lastmod: 2026-07-27
og_description: Comment lire le code‑barres PDF417 en C# avec ce guide étape par étape.
  Décodez les images, gérez plusieurs codes‑barres et extrayez les métadonnées Macro
  PDF417 dans un exemple prêt à l’exécution.
og_image_alt: Screenshot showing how to read PDF417 barcode using C# code
og_title: Comment lire le PDF417 en C# – Exemple complet de code-barres
schemas:
- author: Aspose
  dateModified: '2026-07-27'
  description: How to read PDF417 barcode in C# quickly. Learn to read multiple barcodes,
    decode images, and get Macro PDF417 metadata in a full C# barcode example.
  headline: How to Read PDF417 in C# – Complete Barcode Example
  type: TechArticle
- description: How to read PDF417 barcode in C# quickly. Learn to read multiple barcodes,
    decode images, and get Macro PDF417 metadata in a full C# barcode example.
  name: How to Read PDF417 in C# – Complete Barcode Example
  steps:
  - name: Loads a barcode image from disk.
    text: Loads a barcode image from disk.
  - name: Decodes **PDF417** (including Macro PDF417) barcodes.
    text: Decodes **PDF417** (including Macro PDF417) barcodes.
  - name: Prints basic information such as code type and text.
    text: Prints basic information such as code type and text.
  - name: Outputs the full set of Macro PDF417 fields (file ID, segment ID, checksum,
      etc.).
    text: Outputs the full set of Macro PDF417 fields (file ID, segment ID, checksum,
      etc.).
  type: HowTo
tags:
- barcode
- C#
- PDF417
- image-processing
- Aspose
title: Comment lire le PDF417 en C# – Exemple complet de code-barres
url: /fr/net/compact-pdf417-encoding/how-to-read-pdf417-in-c-complete-barcode-example/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Comment lire un PDF417 en C# – Exemple complet de code‑barres

Vous vous êtes déjà demandé **comment lire un code‑barres PDF417** dans une application C# sans perdre patience ? Vous n'êtes pas le seul. Que vous construisiez un scanner logistique, un valideur de tickets, ou que vous ayez simplement besoin d'extraire des données d'une pièce d'identité encodée en PDF417, le processus peut sembler un peu mystérieux au départ.  

Dans ce tutoriel, nous allons parcourir un **exemple de code‑barres c#** qui lit une image PDF417, gère **la lecture de plusieurs codes‑barres** s'ils sont présents, et extrait toutes les métadonnées Macro PDF417 utiles dont vous pourriez avoir besoin.

## Ce que vous allez créer

À la fin de ce guide, vous disposerez d’un petit programme console qui :

1. Charge une image de code‑barres depuis le disque.  
2. Décode les codes‑barres **PDF417** (y compris Macro PDF417).  
3. Affiche des informations de base telles que le type de code et le texte.  
4. Produit l’ensemble complet des champs Macro PDF417 (ID de fichier, ID de segment, somme de contrôle, etc.).  

Aucun service externe, juste un seul package NuGet et quelques lignes de C#.

## Prérequis – Ce dont vous avez besoin avant de commencer

- **.NET 6.0** ou ultérieur (le code fonctionne également avec .NET Framework 4.6+).  
- Une version récente de la bibliothèque **Aspose.BarCode for .NET** – installez‑la via NuGet (`Install-Package Aspose.BarCode`).  
- Un fichier image contenant un code‑barres PDF417 (la démo utilise `ExtPDF417Meta.png`).  
- Une compréhension de base des applications console C# (si vous avez déjà écrit “Hello World”, vous êtes prêt).

> **Conseil pro :** Si vous n’avez pas d’exemple PDF417 sous la main, générez‑en un sur le site de démonstration Aspose ou utilisez une application smartphone capable de créer des tags PDF417.

## Étape 1 : Configurer le projet et installer la bibliothèque

Tout d’abord, créez un nouveau projet console :

```bash
dotnet new console -n Pdf417ReaderDemo
cd Pdf417ReaderDemo
dotnet add package Aspose.BarCode
```

Cela ajoute les dépendances du **exemple de code‑barres c#** dont nous avons besoin. Ouvrez `Program.cs` et remplacez le code par défaut par le squelette ci‑dessous :

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
            // We'll fill this in in the next steps.
        }
    }
}
```

## Étape 2 : Initialiser le lecteur de code‑barres pour PDF417

Le cœur de la solution est la classe `BarCodeReader`. Nous lui indiquons quel fichier scanner et quel type de code‑barres nous intéressons — dans ce cas `DecodeType.Pdf417` ou la variante macro `DecodeType.MacroPdf417`. Utiliser le type macro garantit que nous capturons les champs étendus.

```csharp
// Step 2: Create the reader, targeting Macro PDF417 barcodes
string imagePath = "YOUR_DIRECTORY/ExtPDF417Meta.png";

using (BarCodeReader reader = new BarCodeReader(
           imagePath, DecodeType.MacroPdf417))
{
    // The rest of the logic lives inside this block.
}
```

Pourquoi utiliser `MacroPdf417` au lieu de `Pdf417` simple ? Macro PDF417 transporte des métadonnées supplémentaires (ID de fichier, nombre de segments, horodatages, etc.) dont de nombreuses applications réelles dépendent — pensez aux manifestes d’expédition répartis sur plusieurs pages.

## Étape 3 : Lire tous les codes‑barres présents dans l’image

Une seule image peut contenir **la lecture de plusieurs codes‑barres** — peut‑être un QR code à côté d’un PDF417. La méthode `ReadBarCodes()` renvoie un `IEnumerable<BarCodeResult>` que nous pouvons parcourir.

```csharp
// Step 3: Iterate through every barcode detected
foreach (BarCodeResult result in reader.ReadBarCodes())
{
    // Inside we’ll output both generic and macro‑specific data.
}
```

Si l’image ne contient qu’un seul PDF417, la boucle s’exécute quand même une fois, ce qui garde le code flexible pour de futurs scénarios où vous pourriez devoir **lire plusieurs codes‑barres** à partir du même scan.

## Étape 4 : Afficher les informations de base du code‑barres

Avant de plonger dans les champs macro, il est utile d’afficher le type de code‑barres et le texte décodé. Cela vous permet de vérifier que le lecteur a bien reconnu un PDF417 et non une autre symbologie.

```csharp
Console.WriteLine($"CodeType : {result.CodeTypeName}");
Console.WriteLine($"CodeText : {result.CodeText}");
```

La propriété `CodeTypeName` affichera *MacroPdf417* (ou *Pdf417* si le drapeau macro n’est pas défini), tandis que `CodeText` contient les données brutes encodées dans le code‑barres.

## Étape 5 : Extraire les métadonnées Macro PDF417

La propriété `Extended` vous donne un aperçu détaillé de la structure spécifique au PDF417. Chaque champ que nous affichons ci‑dessous correspond directement à la spécification macro du PDF417.

```csharp
// Step 5: Macro PDF417 metadata – all optional, but very handy
Console.WriteLine($"Pdf417MacroFileID          : {result.Extended.Pdf417.MacroPdf417FileID}");
Console.WriteLine($"Pdf417MacroSegmentID       : {result.Extended.Pdf417.MacroPdf417SegmentID}");
Console.WriteLine($"Pdf417MacroSegmentsCount   : {result.Extended.Pdf417.MacroPdf417SegmentsCount}");
Console.WriteLine($"Pdf417MacroFileName        : {result.Extended.Pdf417.MacroPdf417FileName}");
Console.WriteLine($"Pdf417MacroChecksum        : {result.Extended.Pdf417.MacroPdf417Checksum}");
Console.WriteLine($"Pdf417MacroFileSize        : {result.Extended.Pdf417.MacroPdf417FileSize}");
Console.WriteLine($"Pdf417MacroTimeStamp       : {result.Extended.Pdf417.MacroPdf417TimeStamp}");
Console.WriteLine($"Pdf417MacroAddressee       : {result.Extended.Pdf417.MacroPdf417Addressee}");
Console.WriteLine($"Pdf417MacroSender          : {result.Extended.Pdf417.MacroPdf417Sender}");
Console.WriteLine($"MacroPdf417Terminator      : {result.Extended.Pdf417.MacroPdf417Terminator}");
```

Chaque ligne récupère une partie différente de la charge macro :

- **FileID** – un identifiant unique pour l’ensemble du document.  
- **SegmentID** – la partie du fichier multi‑segment que vous examinez.  
- **SegmentsCount** – nombre total de segments attendus.  
- **FileName, Checksum, FileSize** – utiles pour valider l’intégrité du fichier transféré.  
- **TimeStamp, Addressee, Sender** – champs optionnels que de nombreux systèmes logistiques intègrent.  

Si l’un de ces champs est absent dans le code‑barres source, la bibliothèque renvoie `null` ou `0`, que vous pouvez gérer selon vos besoins.

## Étape 6 : Exécuter l’exemple complet

En rassemblant le tout, voici le programme complet, prêt à être exécuté :

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
            // Path to the image containing a Macro PDF417 barcode
            string imagePath = "YOUR_DIRECTORY/ExtPDF417Meta.png";

            // Initialize the reader for Macro PDF417 (covers both standard and macro)
            using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
            {
                // Loop through every barcode detected – handles read multiple barcodes gracefully
                foreach (BarCodeResult result in reader.ReadBarCodes())
                {
                    // Basic info
                    Console.WriteLine($"CodeType : {result.CodeTypeName}");
                    Console.WriteLine($"CodeText : {result.CodeText}");

                    // Macro PDF417 specific metadata
                    Console.WriteLine($"Pdf417MacroFileID          : {result.Extended.Pdf417.MacroPdf417FileID}");
                    Console.WriteLine($"Pdf417MacroSegmentID       : {result.Extended.Pdf417.MacroPdf417SegmentID}");
                    Console.WriteLine($"Pdf417MacroSegmentsCount   : {result.Extended.Pdf417.MacroPdf417SegmentsCount}");
                    Console.WriteLine($"Pdf417MacroFileName        : {result.Extended.Pdf417.MacroPdf417FileName}");
                    Console.WriteLine($"Pdf417MacroChecksum        : {result.Extended.Pdf417.MacroPdf417Checksum}");
                    Console.WriteLine($"Pdf417MacroFileSize        : {result.Extended.Pdf417.MacroPdf417FileSize}");
                    Console.WriteLine($"Pdf417MacroTimeStamp       : {result.Extended.Pdf417.MacroPdf417TimeStamp}");
                    Console.WriteLine($"Pdf417MacroAddressee       : {result.Extended.Pdf417.MacroPdf417Addressee}");
                    Console.WriteLine($"Pdf417MacroSender          : {result.Extended.Pdf417.MacroPdf417Sender}");
                    Console.WriteLine($"MacroPdf417Terminator      : {result.Extended.Pdf417.MacroPdf417Terminator}");
                    Console.WriteLine(new string('-', 40));
                }
            }

            Console.WriteLine("Decoding complete. Press any key to exit.");
            Console.ReadKey();
        }
    }
}
```

### Résultat attendu

Lorsque vous exécutez le programme avec un `ExtPDF417Meta.png` valide, vous devriez obtenir quelque chose de similaire à :

```
CodeType : MacroPdf417
CodeText : https://example.com/track?order=12345
Pdf417MacroFileID          : 101
Pdf417MacroSegmentID       : 1
Pdf417MacroSegmentsCount   : 3
Pdf417MacroFileName        : order_manifest.pdf
Pdf417MacroChecksum        : 0x1A2B3C4D
Pdf417MacroFileSize        : 45296
Pdf417MacroTimeStamp       : 2024-03-15T10:27:00Z
Pdf417MacroAddressee       : LogisticsDept
Pdf417MacroSender          : WarehouseA
MacroPdf417Terminator      : true
----------------------------------------
Decoding complete. Press any key to exit.
```

Si l’image contient plus d’un code‑barres,

## Que devez‑vous apprendre ensuite ?

Les tutoriels suivants couvrent des sujets étroitement liés qui s’appuient sur les techniques démontrées dans ce guide. Chaque ressource inclut des exemples de code complets avec des explications pas à pas pour vous aider à maîtriser d’autres fonctionnalités de l’API et explorer des approches d’implémentation alternatives dans vos propres projets.

- [How to Generate PDF417 Barcodes – Compact PDF417 Encoding](/barcode/english/net/compact-pdf417-encoding/)
- [How to Create Barcode – Compact PDF417 with Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [How to Read DataMatrix Barcodes with Aspose.BarCode for .NET](/barcode/english/net/datamatrix-barcode-reading/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}