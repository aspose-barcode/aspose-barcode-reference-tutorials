---
category: general
date: 2026-09-07
description: Apprenez à décoder les codes‑barres PDF417 en C# avec BarCodeReader.
  Ce guide étape par étape explique également comment lire les données PDF417 efficacement.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to decode pdf417
- how to read pdf417
- PDF417 barcode decoding C#
- MacroPdf417 extraction C#
- barcode reader BarCodeReader
- GroupDocs.Barcode tutorial
language: fr
lastmod: 2026-09-07
og_description: Comment décoder les codes-barres PDF417 en C# avec BarCodeReader.
  Suivez ce tutoriel pour apprendre à lire les données PDF417 et extraire les champs
  MacroPdf417.
og_image_alt: Screenshot of C# code reading PDF417 barcode fields in the console
og_title: Comment décoder les codes-barres PDF417 en C# – guide complet
schemas:
- author: GroupDocs
  dateModified: '2026-09-07'
  description: Learn how to decode PDF417 barcodes in C# using BarCodeReader. This
    step‑by‑step guide also explains how to read PDF417 data efficiently.
  headline: How to decode PDF417 barcodes in C# with BarCodeReader
  type: TechArticle
- description: Learn how to decode PDF417 barcodes in C# using BarCodeReader. This
    step‑by‑step guide also explains how to read PDF417 data efficiently.
  name: How to decode PDF417 barcodes in C# with BarCodeReader
  steps:
  - name: Prepare the project and import namespaces
    text: '```csharp using System; using GroupDocs.Barcode; using GroupDocs.Barcode.Common;
      ```'
  - name: Define the image path
    text: '```csharp // Replace with the absolute or relative path to your barcode
      image string imagePath = "YOUR_DIRECTORY/ExtPDF417Meta.png"; ```'
  - name: Initialize the barcode reader for MacroPdf417 decoding
    text: '```csharp using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
      { // Step 4 runs inside this block } ```'
  - name: Read every barcode found in the image
    text: '```csharp foreach (BarCodeResult result in reader.ReadBarCodes()) { //
      Step 5 extracts the MacroPdf417 fields } ```'
  - name: Retrieve and display Macro PDF417 specific data
    text: '```csharp Console.WriteLine($"Pdf417MacroFileID: {result.Extended.Pdf417.MacroPdf417FileID}");
      Console.WriteLine($"Pdf417MacroSegmentID: {result.Extended.Pdf417.MacroPdf417SegmentID}");
      Console.WriteLine($"Pdf417MacroSegmentCount: {result.Extended.Pdf417.MacroPdf417SegmentCount}");
      Console.WriteLine'
  - name: Full runnable example
    text: 'Combine the snippets above into a single `Program.cs` file:'
  type: HowTo
tags:
- PDF417
- C#
- barcode decoding
title: Comment décoder les codes-barres PDF417 en C# avec BarCodeReader
url: /fr/net/compact-pdf417-encoding/how-to-decode-pdf417-barcodes-in-c-with-barcodereader/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Comment décoder les codes-barres PDF417 en C# avec BarCodeReader

Si vous avez besoin de **comment décoder les PDF417** dans une application .NET, ce guide vous accompagne tout au long du processus. Vous découvrirez également **comment lire les PDF417** telles que les identifiants de fichier et de segment MacroPdf417, le tout en quelques lignes de C#.

Le décodage du PDF417 est courant lors du traitement de tickets de transport, de permis de conduire ou d'étiquettes d'expédition. À la fin de ce tutoriel, vous disposerez d'un programme console exécutable qui affiche chaque champ MacroPdf417 exposé par le SDK GroupDocs.Barcode.

## Prérequis

* .NET 6.0 SDK ou ultérieur (le code se compile avec .NET Core et .NET Framework)
* Visual Studio 2022 ou tout IDE supportant C#
* Le package NuGet **GroupDocs.Barcode** (`GroupDocs.Barcode` ≥ 23.3)
* Un fichier image contenant un code-barres Macro PDF417 (par ex., `ExtPDF417Meta.png`)

> **Astuce :** Installez le package via la CLI :  
> `dotnet add package GroupDocs.Barcode --version 23.3`

## Comment décoder les codes-barres PDF417 en C#

Les sections suivantes décomposent la solution en étapes logiques. Chaque étape comprend le code exact dont vous avez besoin ainsi qu'une brève explication de son importance.

### Étape 1 : Préparer le projet et importer les espaces de noms

```csharp
using System;
using GroupDocs.Barcode;
using GroupDocs.Barcode.Common;
```

*Pourquoi ?*  
`GroupDocs.Barcode` fournit la classe `BarCodeReader`, tandis que `GroupDocs.Barcode.Common` contient l'énumération `DecodeType` nécessaire au décodage du PDF417.

### Étape 2 : Définir le chemin de l'image

```csharp
// Replace with the absolute or relative path to your barcode image
string imagePath = "YOUR_DIRECTORY/ExtPDF417Meta.png";
```

*Pourquoi ?*  
Le lecteur fonctionne avec n'importe quel format d'image pris en charge par .NET (`.png`, `.jpg`, `.bmp`). Fournir le chemin correct garantit que le SDK peut localiser le fichier.

### Étape 3 : Initialiser le lecteur de code-barres pour le décodage MacroPdf417

```csharp
using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
{
    // Step 4 runs inside this block
}
```

*Pourquoi ?*  
`DecodeType.MacroPdf417` indique au SDK de rechercher le format étendu Macro PDF417, qui transporte des métadonnées supplémentaires telles que les identifiants de fichier et de segment. L'utilisation de l'instruction `using` garantit que les ressources non gérées sont libérées rapidement.

### Étape 4 : Lire chaque code-barres trouvé dans l'image

```csharp
foreach (BarCodeResult result in reader.ReadBarCodes())
{
    // Step 5 extracts the MacroPdf417 fields
}
```

*Pourquoi ?*  
Une image peut contenir plusieurs codes-barres. La méthode `ReadBarCodes()` renvoie une collection, vous permettant de traiter chaque élément individuellement.

### Étape 5 : Récupérer et afficher les données spécifiques au Macro PDF417

```csharp
Console.WriteLine($"Pdf417MacroFileID: {result.Extended.Pdf417.MacroPdf417FileID}");
Console.WriteLine($"Pdf417MacroSegmentID: {result.Extended.Pdf417.MacroPdf417SegmentID}");
Console.WriteLine($"Pdf417MacroSegmentCount: {result.Extended.Pdf417.MacroPdf417SegmentCount}");
Console.WriteLine($"Pdf417MacroFileName: {result.Extended.Pdf417.MacroPdf417FileName}");
Console.WriteLine($"Pdf417MacroTimestamp: {result.Extended.Pdf417.MacroPdf417Timestamp}");
```

*Pourquoi ?*  
L'objet `Extended.Pdf417` expose tous les champs Macro PDF417 définis par la spécification. Les afficher vous permet de vérifier que l'opération de décodage a réussi et vous fournit les données nécessaires au traitement en aval.

### Exemple complet exécutable

Combinez les extraits ci‑dessus dans un seul fichier `Program.cs` :

```csharp
using System;
using GroupDocs.Barcode;
using GroupDocs.Barcode.Common;

class Program
{
    static void Main()
    {
        // 1️⃣ Path to the image that contains the Macro PDF417 barcode
        string imagePath = "YOUR_DIRECTORY/ExtPDF417Meta.png";

        // 2️⃣ Create a reader configured for MacroPdf417 decoding
        using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
        {
            // 3️⃣ Iterate over all detected barcodes
            foreach (BarCodeResult result in reader.ReadBarCodes())
            {
                // 4️⃣ Output Macro PDF417 metadata
                Console.WriteLine($"Pdf417MacroFileID: {result.Extended.Pdf417.MacroPdf417FileID}");
                Console.WriteLine($"Pdf417MacroSegmentID: {result.Extended.Pdf417.MacroPdf417SegmentID}");
                Console.WriteLine($"Pdf417MacroSegmentCount: {result.Extended.Pdf417.MacroPdf417SegmentCount}");
                Console.WriteLine($"Pdf417MacroFileName: {result.Extended.Pdf417.MacroPdf417FileName}");
                Console.WriteLine($"Pdf417MacroTimestamp: {result.Extended.Pdf417.MacroPdf417Timestamp}");
                Console.WriteLine(); // Blank line for readability
            }
        }
    }
}
```

**Sortie console attendue** (les valeurs varieront selon le contenu du code-barres) :

```
Pdf417MacroFileID: 12345
Pdf417MacroSegmentID: 1
Pdf417MacroSegmentCount: 3
Pdf417MacroFileName: shipment_data
Pdf417MacroTimestamp: 2024-07-15T10:23:45Z
```

Si l'image ne contient pas de code-barres Macro PDF417, la collection `ReadBarCodes()` sera vide et rien ne sera affiché.

## Variations courantes et cas limites

| Situation | Comment adapter le code |
|-----------|--------------------------|
| **Standard (non‑macro) PDF417** | Remplacez `DecodeType.MacroPdf417` par `DecodeType.Pdf417`. L'objet `Extended.Pdf417` sera `null`, donc prévoyez une vérification des références nulles. |
| **Multiple images** | Enveloppez l'initialisation du lecteur dans une boucle `foreach (var path in imagePaths)`. |
| **Large images** | Définissez `reader.Options.ImageProcessingOptions.MaxImageDimension = 2000;` pour limiter l'utilisation de la mémoire. |
| **Performance‑critical batch** | Réutilisez une seule instance de `BarCodeReader` avec `reader.SetImage(path)` au lieu de créer un nouvel objet pour chaque fichier. |

## Liste de vérification de dépannage

* **Pas de sortie :** Vérifiez que `imagePath` pointe vers un fichier valide et que l'image contient réellement un code-barres PDF417. |
* **`Extended.Pdf417` nul :** Vous avez probablement utilisé `DecodeType.Pdf417` au lieu de `MacroPdf417`. |
* **Exception `FileNotFoundException` :** Assurez‑vous que le répertoire de travail correspond au chemin ou utilisez un chemin absolu. |
* **Score de confiance faible :** Augmentez la qualité de l'image ou ajustez les paramètres `reader.Options.Quality`. |

## Conclusion

Vous savez maintenant **comment décoder les PDF417** en C# et **comment lire les métadonnées PDF417** telles que les identifiants de fichier Macro, les identifiants de segment et les horodatages. L'exemple complet montre comment initialiser `BarCodeReader`, sélectionner le bon type de décodage, itérer sur les résultats et extraire chaque champ MacroPdf417 disponible.

Vous pouvez maintenant :

* Intégrer les données extraites dans un système logistique ou de validation de tickets.
* Étendre l'application console pour écrire les résultats dans une base de données ou un fichier JSON.
* Explorer d'autres formats de codes-barres pris en charge par GroupDocs.Barcode (QR, DataMatrix, Code128, etc.) en changeant l'énumération `DecodeType`.

Bon codage, et n'hésitez pas à expérimenter avec différentes images et paramètres de code-barres pour maîtriser le décodage PDF417 dans vos projets .NET !

## Que devriez‑vous apprendre ensuite ?

Les tutoriels suivants couvrent des sujets étroitement liés qui s'appuient sur les techniques démontrées dans ce guide. Chaque ressource comprend des exemples de code complets et fonctionnels avec des explications étape par étape pour vous aider à maîtriser des fonctionnalités API supplémentaires et explorer des approches d'implémentation alternatives dans vos propres projets.

- [Comment lire le PDF417 en C# – Guide complet étape par étape](/barcode/english/net/compact-pdf417-encoding/how-to-read-pdf417-in-c-complete-step-by-step-guide/)
- [Comment lire le PDF417 en C# – Exemple complet de lecteur de code-barres](/barcode/english/net/compact-pdf417-encoding/how-to-read-pdf417-in-c-complete-barcode-reader-example/)
- [Comment générer un code-barres PDF417 – Guide complet de programmation](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-complete-programming-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}