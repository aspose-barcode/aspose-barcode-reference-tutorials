---
category: general
date: 2026-10-28
description: Comment décoder rapidement les codes-barres PDF417 en C#. Apprenez à
  lire une image de code-barres en C# avec Aspose.BarCode grâce à un exemple complet
  et exécutable.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to decode pdf417
- read barcode image c#
- PDF417 decoding C#
- barcode reader C#
- Aspose.BarCode example
language: fr
lastmod: 2026-10-28
og_description: Comment décoder les codes-barres PDF417 en C# avec Aspose.BarCode.
  Ce guide vous montre comment lire une image de code-barres en C# étape par étape,
  avec le code complet.
og_image_alt: Screenshot of C# code that decodes a PDF417 barcode from an image
og_title: Comment décoder les codes-barres PDF417 en C# – tutoriel C# pour lire une
  image de code-barres
schemas:
- author: Aspose
  dateModified: '2026-10-28'
  description: How to decode PDF417 barcodes in C# quickly. Learn to read barcode
    image C# using Aspose.BarCode with a complete, runnable example.
  headline: How to decode PDF417 barcodes in C# and read barcode image C#
  type: TechArticle
- description: How to decode PDF417 barcodes in C# quickly. Learn to read barcode
    image C# using Aspose.BarCode with a complete, runnable example.
  name: How to decode PDF417 barcodes in C# and read barcode image C#
  steps:
  - name: What each line does
    text: '| Line | Explanation | |------|-------------| | `result.CodeTypeName` |
      Human‑readable name of the detected barcode type (e.g., “MacroPdf417”). | |
      `result.CodeText` | The raw data encoded in the barcode. | | `result.Extended.Pdf417.MacroPdf417FileID`
      | Identifier that ties all segments of a macro P'
  - name: Handling common edge cases
    text: '| Situation | Recommended handling | |-----------|----------------------|
      | **No barcode found** | Check `reader.ReadBarCodes().Any()` before the loop
      and display a friendly message. | | **Corrupted image** | Wrap the `BarCodeReader`
      creation in a `try/catch` block for `BarCodeException`. | | **Mult'
  - name: Next steps
    text: '* Explore other barcode formats by changing `DecodeType` (e.g., `DecodeType.QR`,
      `DecodeType.Code128`). * Combine multiple decoded segments to reconstruct the
      original document. * Use the `BarCodeGenerator` class to create test PDF417
      barcodes on the fly.'
  type: HowTo
tags:
- barcode
- pdf417
- csharp
title: Comment décoder les codes-barres PDF417 en C# et lire l'image du code-barres
  en C#
url: /fr/net/compact-pdf417-encoding/how-to-decode-pdf417-barcodes-in-c-and-read-barcode-image-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Comment décoder les codes-barres PDF417 en C# et lire une image de code-barres C#

Si vous avez besoin de **how to decode pdf417** dans une application .NET, ce guide vous fournit une solution prête à l'emploi. Vous verrez exactement comment **read barcode image c#** en utilisant la bibliothèque Aspose.BarCode, extraire les champs macro‑PDF417 et les afficher dans la console.

Le décodage des codes-barres PDF417 apparaît souvent dans les systèmes de logistique, de billetterie et de vérification d'identité. À la fin de ce tutoriel, vous serez capable de charger n'importe quelle image contenant un code-barres Macro PDF417, de le décoder et d'accéder aux valeurs d'ID de fichier, d'ID de segment et de nombre de segments qui sont essentielles pour assembler des documents multi‑segments.

## Prérequis

* SDK .NET 6.0 ou version ultérieure installé  
* Visual Studio 2022 (ou tout IDE C#)  
* Un package NuGet Aspose.BarCode pour .NET (`Aspose.BarCode`)  
* Un fichier image contenant un code-barres Macro PDF417 (l'exemple utilise `ExtPDF417Meta.png`)

Vous pouvez ajouter le package NuGet avec la commande suivante :

```bash
dotnet add package Aspose.BarCode
```

## Étape 1 : Configurer le projet et importer les espaces de noms

Créez un nouveau projet console et importez les espaces de noms requis. Les directives `using` vous donnent accès à `BarCodeReader`, `DecodeType` et aux objets d'extension de résultat.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;
```

> **Pourquoi cette étape est importante** – Importer les espaces de noms corrects évite les erreurs de compilation et rend l'API disponible pour la logique de décodage suivante.

## Étape 2 : Spécifier le chemin de l'image

Définissez le chemin complet ou relatif vers l'image du code-barres. Conserver le chemin dans une variable rend le code réutilisable pour différentes images.

```csharp
// Step 2: Specify the path to the image that contains a Macro PDF417 barcode
string imagePath = "YOUR_DIRECTORY/ExtPDF417Meta.png";
```

> **Astuce :** Utilisez `Path.Combine` si vous construisez le chemin à partir de plusieurs parties ; il gère les séparateurs de répertoires selon les systèmes d'exploitation.

## Étape 3 : Créer un `BarCodeReader` configuré pour le décodage Macro PDF417

Instanciez `BarCodeReader` avec le chemin de l'image et le drapeau `DecodeType.MacroPdf417`. Cela indique à la bibliothèque de rechercher spécifiquement les symboles Macro PDF417.

```csharp
// Step 3: Create a BarCodeReader configured for MacroPdf417 decoding
using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
{
    // The reader is now ready to scan the image.
```

> **Pourquoi cette étape est importante** – Sélectionner le `DecodeType` approprié améliore les performances car le moteur ignore les formats de code-barres non pertinents.

## Étape 4 : Lire tous les codes-barres et afficher les informations macro

Parcourez chaque `BarCodeResult` renvoyé par `reader.ReadBarCodes()`. L'objet résultat contient à la fois des champs génériques (`CodeTypeName`, `CodeText`) et des extensions spécifiques à Macro PDF417 (`MacroPdf417FileID`, `MacroPdf417SegmentID`, `MacroPdf417SegmentsCount`).

```csharp
    // Step 4: Read all barcodes in the image and display the most relevant macro information
    foreach (BarCodeResult result in reader.ReadBarCodes())
    {
        Console.WriteLine($"Code Type : {result.CodeTypeName}");
        Console.WriteLine($"Code Text : {result.CodeText}");

        // Macro PDF417 specific fields
        Console.WriteLine($"File ID   : {result.Extended.Pdf417.MacroPdf417FileID}");
        Console.WriteLine($"Segment ID: {result.Extended.Pdf417.MacroPdf417SegmentID}");
        Console.WriteLine($"Segments  : {result.Extended.Pdf417.MacroPdf417SegmentsCount}");
    }
}
```

### Ce que chaque ligne fait

| Ligne | Explication |
|------|-------------|
| `result.CodeTypeName` | Nom lisible par l'homme du type de code-barres détecté (par ex., “MacroPdf417”). |
| `result.CodeText` | Les données brutes encodées dans le code-barres. |
| `result.Extended.Pdf417.MacroPdf417FileID` | Identifiant qui relie tous les segments d'un document macro PDF417. |
| `result.Extended.Pdf417.MacroPdf417SegmentID` | Indice du segment actuel dans le document complet. |
| `result.Extended.Pdf417.MacroPdf417SegmentsCount` | Nombre total de segments attendus pour le document. |

> **Conseil pro :** Stockez les champs macro dans une base de données si vous devez réassembler le document complet plus tard. Le `File ID` vous permet de regrouper les segments appartenant à la même source.

## Étape 5 : Exécuter le programme et vérifier la sortie

Compilez et exécutez l'application console :

```bash
dotnet run
```

Un exemple de sortie console typique ressemble à ceci :

```
Code Type : MacroPdf417
Code Text : 0123456789ABCD
File ID   : 101
Segment ID: 1
Segments  : 3
```

Si l'image contient plusieurs symboles Macro PDF417, la boucle les imprime chacun séquentiellement.

### Gestion des cas limites courants

| Situation | Gestion recommandée |
|-----------|----------------------|
| **Aucun code-barres trouvé** | Vérifiez `reader.ReadBarCodes().Any()` avant la boucle et affichez un message convivial. |
| **Image corrompue** | Enveloppez la création de `BarCodeReader` dans un bloc `try/catch` pour `BarCodeException`. |
| **Formats de code-barres multiples** | Utilisez `DecodeType.AllSupported` et filtrez les résultats avec `result.CodeTypeName == "MacroPdf417"`. |
| **Images volumineuses** | Redimensionnez l'image avant le décodage pour améliorer les performances ; la bibliothèque accepte un objet `Bitmap`. |

## Code source complet

Ci-dessous le programme complet et autonome. Copiez‑le dans `Program.cs` d'un nouveau projet console et remplacez `YOUR_DIRECTORY/ExtPDF417Meta.png` par le chemin réel vers votre image.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

namespace Pdf417Decoder
{
    class Program
    {
        static void Main(string[] args)
        {
            // Step 2: Specify the path to the image that contains a Macro PDF417 barcode
            string imagePath = "YOUR_DIRECTORY/ExtPDF417Meta.png";

            // Step 3: Create a BarCodeReader configured for MacroPdf417 decoding
            using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
            {
                // Step 4: Read all barcodes in the image and display the most relevant macro information
                foreach (BarCodeResult result in reader.ReadBarCodes())
                {
                    Console.WriteLine($"Code Type : {result.CodeTypeName}");
                    Console.WriteLine($"Code Text : {result.CodeText}");

                    // Macro PDF417 specific fields
                    Console.WriteLine($"File ID   : {result.Extended.Pdf417.MacroPdf417FileID}");
                    Console.WriteLine($"Segment ID: {result.Extended.Pdf417.MacroPdf417SegmentID}");
                    Console.WriteLine($"Segments  : {result.Extended.Pdf417.MacroPdf417SegmentsCount}");
                }
            }
        }
    }
}
```

## Conclusion

Vous savez maintenant **how to decode pdf417** les codes-barres en C# et comment **read barcode image c#** en utilisant Aspose.BarCode. Le tutoriel vous a guidé à travers la configuration du projet, le chargement de l'image, la configuration du lecteur, l'extraction des résultats et la gestion des cas limites. Avec cette base, vous pouvez intégrer le décodage PDF417 dans des systèmes d'inventaire, des validateurs de tickets ou tout flux de travail reposant sur des données macro‑encodées.

### Prochaines étapes

* Explorez d'autres formats de code-barres en modifiant `DecodeType` (par ex., `DecodeType.QR`, `DecodeType.Code128`).  
* Combinez plusieurs segments décodés pour reconstruire le document original.  
* Utilisez la classe `BarCodeGenerator` pour créer des codes-barres PDF417 de test à la volée.  

N'hésitez pas à expérimenter avec différentes sources d'images, à ajuster la sortie console, ou à intégrer la logique de décodage dans une API web pour un traitement en temps réel. Bon codage !

## Que devriez‑vous apprendre ensuite ?

Les tutoriels suivants couvrent des sujets étroitement liés qui s'appuient sur les techniques démontrées dans ce guide. Chaque ressource comprend des exemples de code fonctionnels complets avec des explications étape par étape pour vous aider à maîtriser des fonctionnalités API supplémentaires et explorer des approches d'implémentation alternatives dans vos propres projets.

- [Comment décoder PDF417 en C# avec un exemple de lecteur de code-barres](/barcode/english/net/compact-pdf417-encoding/how-to-decode-pdf417-in-c-with-a-barcode-reader-example/)
- [Comment générer des codes-barres PDF417 en C# avec Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcodes-in-c-with-aspose-barcode/)
- [Comment lire un code-barres depuis une image c# en utilisant Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/how-to-read-barcode-from-image-c-using-aspose-barcode/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}