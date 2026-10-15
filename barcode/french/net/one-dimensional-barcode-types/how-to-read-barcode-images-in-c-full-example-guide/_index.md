---
category: general
date: 2026-10-15
description: Comment lire rapidement des images de codes-barres en C# avec BarCodeReader.
  Apprenez à lire plusieurs codes-barres et découvrez un exemple de lecteur de codes-barres
  C# qui fonctionne avec Macro‑PDF417.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to read barcode
- read multiple barcodes
- c# barcode reader example
- Macro‑PDF417 decoding
- barcode metadata extraction
language: fr
lastmod: 2026-10-15
og_description: Comment lire un code‑barres en C# avec BarCodeReader. Ce tutoriel
  montre un exemple complet de lecteur de code‑barres en C# qui gère plusieurs codes‑barres
  et extrait les métadonnées Macro‑PDF417.
og_image_alt: Screenshot showing how to read barcode with C# BarCodeReader
og_title: Comment lire un code-barres en C# – exemple pas à pas
schemas:
- author: Aspose
  dateModified: '2026-10-15'
  description: How to read barcode images in C# quickly using BarCodeReader. Learn
    to read multiple barcodes and see a c# barcode reader example that works with
    Macro‑PDF417.
  headline: How to read barcode images in C# – full example guide
  type: TechArticle
- description: How to read barcode images in C# quickly using BarCodeReader. Learn
    to read multiple barcodes and see a c# barcode reader example that works with
    Macro‑PDF417.
  name: How to read barcode images in C# – full example guide
  steps:
  - name: Initialise the `BarCodeReader`
    text: '```csharp using Aspose.BarCode; using Aspose.BarCode.BarCodeRecognition;'
  - name: Read all barcodes present in the image
    text: '```csharp // Step 2: Read all barcodes in the image BarCodeResult[] results
      = reader.ReadBarCodes(); ```'
  - name: Display basic barcode details
    text: '```csharp foreach (BarCodeResult result in results) { Console.WriteLine($"CodeType:
      {result.CodeTypeName}"); Console.WriteLine($"CodeText: {result.CodeText}");
      ```'
  - name: Retrieve and show Macro‑PDF417 specific metadata
    text: '```csharp // Macro‑PDF417 extended data Console.WriteLine($"FileID: {result.Extended.Pdf417.MacroPdf417FileID}");
      Console.WriteLine($"Segment: {result.Extended.Pdf417.MacroPdf417SegmentID}");
      Console.WriteLine($"Count: {result.Extended.Pdf417.MacroPdf417SegmentsCount}");
      Console.WriteLine($"FileName'
  - name: Full runnable program
    text: Below is a self‑contained console application that puts all four steps together.
      Copy the code into a new `.cs` file, adjust the `imagePath`, and run `dotnet
      run`.
  type: HowTo
tags:
- barcode
- C#
- Aspose.BarCode
title: Comment lire des images de codes-barres en C# – guide complet avec exemple
url: /fr/net/one-dimensional-barcode-types/how-to-read-barcode-images-in-c-full-example-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Comment lire des images de code-barres en C# – guide complet avec exemple

Si vous devez **comment lire un code-barres** à partir d'une image dans une application .NET, ce guide vous fournit une solution prête à l'emploi. Vous verrez un **exemple complet de lecteur de code-barres en c#** qui fonctionne avec les symboles Macro‑PDF417 et peut **lire plusieurs codes-barres** à partir d'une seule image.

Lire les codes-barres est une exigence courante pour les systèmes d'inventaire, la validation de tickets et le traitement de documents. À la fin de ce tutoriel, vous serez capable de :

* Initialiser le `BarCodeReader` pour tout format pris en charge.  
* Extraire les informations de base telles que le type de code et le texte décodé.  
* Récupérer les métadonnées spécifiques à Macro‑PDF417 (ID de fichier, segment, somme de contrôle, …).  
* Gérer les images contenant plusieurs codes-barres sans code supplémentaire.

## Prérequis

Avant de commencer, assurez‑vous d’avoir :

* .NET 6.0 SDK ou version ultérieure installé.  
* Un environnement de développement (Visual Studio 2022, VS Code ou Rider).  
* Le package NuGet **Aspose.BarCode for .NET** (`Aspose.BarCode`) – il fournit la classe `BarCodeReader` utilisée dans l'exemple.  
* Un fichier image contenant un code-barres Macro‑PDF417 (par ex., `MacroPdf417.png`).  

Vous pouvez installer le package NuGet avec la commande suivante :

```bash
dotnet add package Aspose.BarCode
```

## Comment lire un code-barres avec BarCodeReader en C#

Le cœur de la solution se compose de quatre étapes concises. Chaque étape est encapsulée dans un bloc `using` afin de garantir que les ressources non gérées sont libérées rapidement.

### Étape 1 : Initialiser le `BarCodeReader`

```csharp
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

// Path to the image that contains the Macro‑PDF417 barcode(s)
string imagePath = @"YOUR_DIRECTORY\MacroPdf417.png";

// Initialise the reader for the specific DecodeType
using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
{
    // The remaining steps are inside this block
}
```

**Pourquoi c'est important :**  
`BarCodeReader` accepte un chemin de fichier et un `DecodeType`. Spécifier `DecodeType.MacroPdf417` indique à la bibliothèque de ne rechercher que les symboles Macro‑PDF417, ce qui améliore la vitesse de détection et réduit les faux positifs.

### Étape 2 : Lire tous les codes-barres présents dans l'image

```csharp
    // Step 2: Read all barcodes in the image
    BarCodeResult[] results = reader.ReadBarCodes();
```

**Pourquoi c'est important :**  
La méthode `ReadBarCodes()` renvoie un tableau pouvant contenir un ou plusieurs objets `BarCodeResult`. C'est à ce moment que la capacité de **read multiple barcodes** se démarque – vous n'avez pas besoin d'une boucle séparée pour chaque code-barres possible.

### Étape 3 : Afficher les détails de base du code-barres

```csharp
    foreach (BarCodeResult result in results)
    {
        Console.WriteLine($"CodeType: {result.CodeTypeName}");
        Console.WriteLine($"CodeText: {result.CodeText}");
```

**Pourquoi c'est important :**  
`CodeTypeName` indique quelle symbologie a été détectée (par ex., “MacroPDF417”), tandis que `CodeText` contient la charge décodée. Ces deux champs sont les plus fréquemment utilisés dans la logique en aval.

### Étape 4 : Récupérer et afficher les métadonnées spécifiques à Macro‑PDF417

```csharp
        // Macro‑PDF417 extended data
        Console.WriteLine($"FileID:    {result.Extended.Pdf417.MacroPdf417FileID}");
        Console.WriteLine($"Segment:   {result.Extended.Pdf417.MacroPdf417SegmentID}");
        Console.WriteLine($"Count:     {result.Extended.Pdf417.MacroPdf417SegmentsCount}");
        Console.WriteLine($"FileName:  {result.Extended.Pdf417.MacroPdf417FileName}");
        Console.WriteLine($"Checksum:  {result.Extended.Pdf417.MacroPdf417Checksum}");
        Console.WriteLine($"FileSize:  {result.Extended.Pdf417.MacroPdf417FileSize}");
        Console.WriteLine($"Time:      {result.Extended.Pdf417.MacroPdf417TimeStamp}");
        Console.WriteLine($"Addressee: {result.Extended.Pdf417.MacroPdf417Addressee}");
        Console.WriteLine($"Sender:    {result.Extended.Pdf417.MacroPdf417Sender}");
        Console.WriteLine($"Terminator:{result.Extended.Pdf417.MacroPdf417Terminator}");
        Console.WriteLine(new string('-', 40));
    }
}
```

**Pourquoi c'est important :**  
Macro‑PDF417 étend le format PDF417 standard avec des métadonnées au niveau du document. Accéder à la propriété `Extended.Pdf417` vous fournit tout ce dont vous avez besoin pour reconstruire le fichier original, valider son intégrité ou acheminer les données vers le destinataire approprié.

### Programme complet exécutable

Ci-dessous se trouve une application console autonome qui regroupe les quatre étapes. Copiez le code dans un nouveau fichier `.cs`, ajustez le `imagePath`, puis exécutez `dotnet run`.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // ------------------------------------------------------------
            // 1️⃣ Initialise the BarCodeReader for Macro‑PDF417 images
            // ------------------------------------------------------------
            string imagePath = @"YOUR_DIRECTORY\MacroPdf417.png";

            using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
            {
                // ------------------------------------------------------------
                // 2️⃣ Read all barcodes present in the image
                // ------------------------------------------------------------
                BarCodeResult[] results = reader.ReadBarCodes();

                if (results.Length == 0)
                {
                    Console.WriteLine("No barcodes were detected.");
                    return;
                }

                // ------------------------------------------------------------
                // 3️⃣ Iterate over each result – this is where we **read multiple barcodes**
                // ------------------------------------------------------------
                foreach (BarCodeResult result in results)
                {
                    Console.WriteLine($"CodeType: {result.CodeTypeName}");
                    Console.WriteLine($"CodeText: {result.CodeText}");

                    // ------------------------------------------------------------
                    // 4️⃣ Extract Macro‑PDF417 metadata (c# barcode reader example)
                    // ------------------------------------------------------------
                    Console.WriteLine($"FileID:    {result.Extended.Pdf417.MacroPdf417FileID}");
                    Console.WriteLine($"Segment:   {result.Extended.Pdf417.MacroPdf417SegmentID}");
                    Console.WriteLine($"Count:     {result.Extended.Pdf417.MacroPdf417SegmentsCount}");
                    Console.WriteLine($"FileName:  {result.Extended.Pdf417.MacroPdf417FileName}");
                    Console.WriteLine($"Checksum:  {result.Extended.Pdf417.MacroPdf417Checksum}");
                    Console.WriteLine($"FileSize:  {result.Extended.Pdf417.MacroPdf417FileSize}");
                    Console.WriteLine($"Time:      {result.Extended.Pdf417.MacroPdf417TimeStamp}");
                    Console.WriteLine($"Addressee: {result.Extended.Pdf417.MacroPdf417Addressee}");
                    Console.WriteLine($"Sender:    {result.Extended.Pdf417.MacroPdf417Sender}");
                    Console.WriteLine($"Terminator:{result.Extended.Pdf417.MacroPdf417Terminator}");
                    Console.WriteLine(new string('-', 40));
                }
            }
        }
    }
}
```

#### Sortie console attendue

```
CodeType: MacroPDF417
CodeText: https://example.com/document
FileID:    12
Segment:   3
Count:     5
FileName:  report.pdf
Checksum:  0x1A2B3C4D
FileSize:  1048576
Time:      2024-08-15T14:23:00Z
Addressee: John Doe
Sender:    Acme Corp.
Terminator:END
----------------------------------------
```

Si l'image contient plus d'un symbole Macro‑PDF417, le programme affiche un bloc distinct pour chaque code-barres, démontrant la capacité de **read multiple barcodes** sans aucun code supplémentaire.

## Gestion des cas limites courants

| Situation | Action à entreprendre | Raison |
|-----------|-----------------------|--------|
| **Fichier non trouvé** | Enveloppez la construction du `BarCodeReader` dans un bloc `try/catch (FileNotFoundException)` et affichez un message convivial. | Empêche l'application de planter et informe l'utilisateur de l'absence de la ressource. |
| **Aucun code-barres détecté** | Vérifiez `results.Length == 0` (comme montré dans le programme complet) et gérez-le de manière élégante. | Fournit un retour clair lorsque l'image ne contient aucune symbologie prise en charge. |
| **Type de code-barres différent** | Changez `DecodeType.MacroPdf417` en `DecodeType.AllSupportedTypes` ou une autre valeur d'énumération spécifique. | Permet au même code de fonctionner avec QR, Code128, DataMatrix, etc., tout en continuant à supporter **read multiple barcodes**. |
| **Images volumineuses** | Définissez `reader.AutoSize = true` ou réduisez la taille de l'image avant de la transmettre au lecteur. | Améliore les performances et réduit la pression mémoire sur le CLR. |
| **Utilisation thread‑safe** | Créez une instance distincte de `BarCodeReader` par thread ; la classe n'est pas thread‑safe. | Évite les conditions de concurrence dans les scanners multi‑threads ou les services web. |

## Astuces pro pour le code de production

* **Libérez tôt :** L'instruction `using` garantit que les ressources natives (par ex., les tampons d'image) sont libérées rapidement. Dans les services de longue durée, libérez le lecteur dès que vous avez fini de traiter chaque image.  
* **Traitement par lots**

## Que devriez‑vous apprendre ensuite ?

Les tutoriels suivants couvrent des sujets étroitement liés qui s'appuient sur les techniques présentées dans ce guide. Chaque ressource comprend des exemples de code complets et fonctionnels avec des explications étape par étape pour vous aider à maîtriser des fonctionnalités supplémentaires de l'API et explorer des approches d'implémentation alternatives dans vos propres projets.

- [Lire un code-barres à partir d'une image C# – guide complet avec Macro PDF417](/barcode/english/net/compact-pdf417-encoding/read-barcode-from-image-c-complete-guide-with-macro-pdf417/)
- [Comment créer un code-barres macro PDF417 en C# avec Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/how-to-create-macro-pdf417-barcode-in-c-using-aspose-barcode/)
- [Comment lire le PDF417 en C# – Exemple complet de lecteur de code-barres](/barcode/english/net/compact-pdf417-encoding/how-to-read-pdf417-in-c-complete-barcode-reader-example/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}