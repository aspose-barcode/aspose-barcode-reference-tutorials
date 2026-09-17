---
category: general
date: 2026-08-03
description: Lire le code‑barres PDF417 à partir d’une image en utilisant C# BarCodeReader
  – un exemple complet de lecteur de code‑barres qui montre également comment lire
  plusieurs codes‑barres.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- read PDF417 barcode
- barcode reader example
- read multiple barcodes
- read barcodes image
language: fr
lastmod: 2026-08-03
og_description: Lire rapidement le code‑barres PDF417 avec un exemple de BarCodeReader
  en C#. Suivez ce guide étape par étape pour décoder le macro PDF417 et lire plusieurs
  codes‑barres à partir d’une image.
og_image_alt: Console output of a read PDF417 barcode example in C#
og_title: Lire le code‑barres PDF417 en C# – exemple complet de lecteur de code‑barres
schemas:
- author: Aspose
  dateModified: '2026-08-03'
  description: Read PDF417 barcode from an image using C# BarCodeReader – a complete
    barcode reader example that also shows how to read multiple barcodes.
  headline: Read PDF417 barcode in C# – barcode reader example
  type: TechArticle
- description: Read PDF417 barcode from an image using C# BarCodeReader – a complete
    barcode reader example that also shows how to read multiple barcodes.
  name: Read PDF417 barcode in C# – barcode reader example
  steps:
  - name: '**Create a new console project**'
    text: '**Create a new console project**'
  - name: '**Add the barcode library**'
    text: '**Add the barcode library**'
  - name: '**Copy the barcode image**'
    text: '**Copy the barcode image**'
  type: HowTo
tags:
- barcode
- PDF417
- C#
- .NET
title: Lire le code‑barres PDF417 en C# – exemple de lecteur de code‑barres
url: /fr/net/compact-pdf417-encoding/read-pdf417-barcode-in-c-barcode-reader-example/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Lire un code‑barres PDF417 en C# – exemple de lecteur de code‑barres

Si vous devez lire les données d’un code‑barres PDF417 à partir d’une image, ce guide vous montre comment le faire avec la classe **BarCodeReader** en C#. Vous apprendrez un exemple de lecteur de code‑barres qui gère également le macro PDF417 et peut lire plusieurs code‑barres dans une même image.

Travailler avec les code‑barres implique souvent de gérer différentes sources d’images, des conditions d’éclairage variables, et parfois des données composites comme les segments macro PDF417. Ce tutoriel couvre tout ce dont vous avez besoin pour décoder un code‑barres PDF417, extraire ses champs étendus, et traiter plusieurs code‑barres à partir de la même image. À la fin, vous disposerez d’un programme console exécutable qui lit les code‑barres d’un fichier image et affiche des informations détaillées dans la console.

## Ce dont vous avez besoin

Avant de commencer, assurez‑vous d’avoir :

* le SDK .NET 6.0 ou une version ultérieure installé  
* une version récente du package NuGet **Aspose.BarCode for .NET** (ou toute bibliothèque compatible qui fournit `BarCodeReader` et `DecodeType.MacroPdf417`)  
* un fichier image contenant un code‑barres PDF417 ou macro PDF417 (l’exemple utilise `ExtPDF417Meta.png`)  
* un éditeur de code ou un IDE tel que Visual Studio 2022  

Aucun service supplémentaire ou API externe n’est requis.

## Configuration du projet pour la lecture de code‑barres

1. **Créer un nouveau projet console**  

   ```bash
   dotnet new console -n Pdf417ReaderDemo
   cd Pdf417ReaderDemo
   ```

2. **Ajouter la bibliothèque de code‑barres**  

   ```bash
   dotnet add package Aspose.BarCode --version 23.12
   ```

3. **Copier l’image du code‑barres**  

   Placez `ExtPDF417Meta.png` (ou toute image contenant un code‑barres PDF417) dans le dossier du projet.  
   Pour ce tutoriel, nous supposons que le fichier se trouve à `YOUR_DIRECTORY/ExtPDF417Meta.png`.

Le projet est maintenant prêt à être compilé et à exécuter l’exemple de lecteur de code‑barres.

## Comment lire un code‑barres PDF417 avec BarCodeReader

Le cœur de la solution est un bloc `using` qui crée une instance de `BarCodeReader`, spécifie `DecodeType.MacroPdf417`, et itère sur chaque code‑barres détecté. Le code suivant est un programme complet, autonome, que vous pouvez coller dans `Program.cs`.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

class Program
{
    static void Main()
    {
        // Path to the image that contains one or more PDF417 barcodes
        const string imagePath = "YOUR_DIRECTORY/ExtPDF417Meta.png";

        // Step 1: Create a BarCodeReader for a macro PDF417 image
        using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
        {
            // Step 2: Read all barcodes from the image
            foreach (BarCodeResult result in reader.ReadBarCodes())
            {
                // Step 3: Output basic barcode information
                Console.WriteLine($"CodeType: {result.CodeTypeName}");
                Console.WriteLine($"CodeText: {result.CodeText}");

                // Step 4: Output macro PDF417 specific fields
                Console.WriteLine($"Pdf417MacroFileID: {result.Extended.Pdf417.MacroPdf417FileID}");
                Console.WriteLine($"Pdf417MacroSegmentID: {result.Extended.Pdf417.MacroPdf417SegmentID}");
                Console.WriteLine($"Pdf417MacroSegmentsCount: {result.Extended.Pdf417.MacroPdf417SegmentsCount}");
                Console.WriteLine($"Pdf417MacroFileName: {result.Extended.Pdf417.MacroPdf417FileName}");
                Console.WriteLine($"Pdf417MacroChecksum: {result.Extended.Pdf417.MacroPdf417Checksum}");
                Console.WriteLine($"Pdf417MacroFileSize: {result.Extended.Pdf417.MacroPdf417FileSize}");
                Console.WriteLine($"Pdf417MacroTimeStamp: {result.Extended.Pdf417.MacroPdf417TimeStamp}");
                Console.WriteLine($"Pdf417MacroAddressee: {result.Extended.Pdf417.MacroPdf417Addressee}");
                Console.WriteLine($"Pdf417MacroSender: {result.Extended.Pdf417.MacroPdf417Sender}");
                Console.WriteLine($"MacroPdf417Terminator: {result.Extended.Pdf417.MacroPdf417Terminator}");
                Console.WriteLine(new string('-', 40));
            }

            // Pro tip: If no barcodes are found, ReadBarCodes() returns an empty collection.
            // You can check reader.HasBarcodes for a quick boolean test.
            if (!reader.HasBarcodes)
            {
                Console.WriteLine("No barcodes detected in the provided image.");
            }
        }
    }
}
```

**Pourquoi cela fonctionne** :  

* `DecodeType.MacroPdf417` indique au lecteur de rechercher l’extension macro du PDF417, qui transporte des métadonnées supplémentaires telles que l’ID du fichier, le nombre de segments et les horodatages.  
* L’instruction `using` garantit que les ressources non gérées (descripteurs de fichiers, tampons natifs de décodage) sont libérées rapidement.  
* La boucle `foreach` traite automatiquement **tous** les code‑barres présents dans l’image, répondant ainsi à l’exigence de *lecture de plusieurs code‑barres*.  

Lorsque vous exécutez le programme (`dotnet run`), vous devriez voir une sortie similaire à celle‑ci :

```
CodeType: MacroPdf417
CodeText: https://example.com/document.pdf
Pdf417MacroFileID: 12345
Pdf417MacroSegmentID: 1
Pdf417MacroSegmentsCount: 3
Pdf417MacroFileName: document.pdf
Pdf417MacroChecksum: 0x1A2B
Pdf417MacroFileSize: 204800
Pdf417MacroTimeStamp: 2024-07-15T10:25:00Z
Pdf417MacroAddressee: John Doe
Pdf417MacroSender: Acme Corp
MacroPdf417Terminator: True
----------------------------------------
```

Si l’image contient plus d’un code‑barres PDF417, la boucle imprime un bloc séparé pour chaque code‑barres, démontrant ainsi comment **lire plusieurs code‑barres** à partir d’une seule image.

## Lecture de plusieurs code‑barres à partir d’une image

La même instance de `BarCodeReader` peut décoder plusieurs types de code‑barres en même temps. Pour élargir le champ d’application du macro PDF417 à tout PDF417 (ou même QR, Code128, etc.), ajustez le drapeau `DecodeType` :

```csharp
using (BarCodeReader reader = new BarCodeReader(imagePath,
       DecodeType.Pdf417 | DecodeType.MacroPdf417 | DecodeType.QR | DecodeType.Code128))
{
    // The rest of the code stays unchanged.
}
```

*`DecodeType`* est un masque de bits, vous pouvez donc combiner n’importe quel nombre de formats pris en charge. Cette flexibilité fait du fragment un **exemple de lecteur de code‑barres** qui fonctionne pour une grande variété de cas d’utilisation, tels que le scan d’étiquettes produit, de billets ou de cartes d’identité.

## Accéder aux champs macro PDF417 en toute sécurité

Le macro PDF417 ajoute un ensemble riche de propriétés étendues. Cependant, tous les code‑barres ne contiennent pas chaque champ. Accéder à une propriété manquante peut déclencher une `NullReferenceException`. L’approche la plus sûre consiste à vérifier chaque propriété avant de l’afficher :

```csharp
var macro = result.Extended?.Pdf417;
if (macro != null)
{
    Console.WriteLine($"Pdf417MacroFileID: {macro.MacroPdf417FileID ?? "N/A"}");
    // Repeat for other fields...
}
```

*Pourquoi c’est important* : Dans les déploiements réels, vous pouvez recevoir des code‑barres PDF417 simples qui ne possèdent pas de données macro. La vérification défensive garantit que votre application continue de fonctionner sans plantage.

## Pièges courants et bonnes pratiques

| Problème | Pourquoi cela se produit | Solution recommandée |
|----------|--------------------------|----------------------|
| Le chemin de l’image est incorrect | `BarCodeReader` lève une exception fichier introuvable avant tout décodage | Utilisez `Path.Combine` et validez l’existence du fichier avec `File.Exists` |
| Image à basse résolution | Le décodeur ne peut pas localiser les bords du code‑barres, entraînant aucune détection | Fournissez une résolution minimale de 300 dpi pour des résultats fiables |
| Code‑barres tourné de > 45° | De nombreuses bibliothèques supposent une orientation verticale | Activez `reader.RecognitionOptions.RotateImage = true` si le |

## Que devez‑vous apprendre ensuite ?

Les tutoriels suivants couvrent des sujets étroitement liés qui s’appuient sur les techniques démontrées dans ce guide. Chaque ressource comprend des exemples de code complets avec des explications pas à pas pour vous aider à maîtriser d’autres fonctionnalités de l’API et explorer des approches d’implémentation alternatives dans vos propres projets.

- [Comment lire les codes‑barres DataMatrix avec Aspose.BarCode for .NET](/barcode/english/net/datamatrix-barcode-reading/)
- [Lire un code‑barres DataMatrix C# – Générer le mode DataMatrix (Auto)](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-auto/)
- [Lire un code‑barres depuis une image – Maîtriser l’extraction de région de code‑barres en Java avec Aspose.BarCode](/barcode/english/java/advanced-settings-and-optimization/extracting-barcode-region-information/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}