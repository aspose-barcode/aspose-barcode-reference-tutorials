---
category: general
date: 2026-11-23
description: Apprenez à utiliser BarCodeReader en C# pour lire les codes‑barres à
  partir d’une image, y compris le décodage Macro PDF417, avec un exemple de code
  complet et des explications claires.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to use barcodereader
- read barcodes from image c#
language: fr
lastmod: 2026-11-23
og_description: Comment utiliser BarCodeReader en C# pour lire les codes-barres à
  partir d’une image. Suivez ce guide étape par étape pour décoder le Macro PDF417
  et d’autres formats avec du code prêt à l’emploi.
og_image_alt: Screenshot of BarCodeReader console output showing decoded Macro PDF417
  data
og_title: Comment utiliser BarCodeReader en C# – lire rapidement les codes-barres
  à partir d'images
schemas:
- author: Aspose
  dateModified: '2026-11-23'
  description: Learn how to use BarCodeReader in C# to read barcodes from an image,
    including Macro PDF417 decoding, with a complete code example and clear explanations.
  headline: How to use BarCodeReader in C# to read barcodes from images
  type: TechArticle
- description: Learn how to use BarCodeReader in C# to read barcodes from an image,
    including Macro PDF417 decoding, with a complete code example and clear explanations.
  name: How to use BarCodeReader in C# to read barcodes from images
  steps:
  - name: 1. Decoding multiple barcode formats
    text: 'If you need to detect more than one format, pass a combined `DecodeType`
      flag:'
  - name: 2. Managing large images
    text: 'Large images can cause high memory usage. Downscale the image before passing
      it to the reader:'
  - name: 3. Error handling
    text: 'Wrap the reading logic in a try‑catch block to surface decoding failures:'
  type: HowTo
tags:
- barcode
- C#
- image-processing
title: Comment utiliser BarCodeReader en C# pour lire les codes-barres à partir d'images
url: /fr/net/compact-pdf417-encoding/how-to-use-barcodereader-in-c-to-read-barcodes-from-images/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Comment utiliser BarCodeReader en C# pour lire les codes-barres à partir d'images

Si vous avez besoin de **comment utiliser BarCodeReader** pour un scan rapide de code-barres, ce guide vous montre exactement cela. Que vous construisiez un système de point de vente ou que vous automatisiez la saisie de documents, vous apprendrez à lire les codes-barres à partir d'images dans des projets C# avec seulement quelques lignes de code.

Dans ce tutoriel, vous verrez un exemple complet et exécutable qui décode un code-barres Macro PDF417, extrait ses propriétés étendues et affiche des informations utiles dans la console. Aucune documentation externe n’est requise – tout ce dont vous avez besoin se trouve ici.

## Prérequis

Avant de commencer, assurez‑vous d’avoir :

* .NET 6.0 (ou version ultérieure) installé – le code cible la dernière version LTS.  
* Une référence au package NuGet **Aspose.BarCode** (ou tout autre compatible) qui fournit `BarCodeReader`.  
* Un fichier image contenant un code-barres Macro PDF417 (l’exemple utilise `ExtPDF417Meta.png`).

> **Astuce :** Si vous utilisez Visual Studio, ajoutez le package via `dotnet add package Aspose.BarCode` ou l’interface NuGet Package Manager.

## Étape 1 : Créer une instance de BarCodeReader

La première chose à faire avec une bibliothèque de codes‑barres est d’instancier un lecteur qui pointe vers l’image source et indique à l’API quels types de codes‑barres rechercher.

```csharp
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

// Step 1: Initialise BarCodeReader for a Macro PDF417 image
using (BarCodeReader barcodeReader = new BarCodeReader(
           "YOUR_DIRECTORY/ExtPDF417Meta.png",
           DecodeType.MacroPdf417))
{
    // The using block guarantees proper disposal of native resources.
```

*Pourquoi cette étape est importante :*  
`BarCodeReader` ouvre l’image, alloue la mémoire native et prépare les algorithmes de décodage pour le `DecodeType` spécifié. En limitant le type à `MacroPdf417`, vous réduisez la charge CPU et améliorez la précision de détection.

## Étape 2 : Lire tous les codes‑barres trouvés dans l’image

Une seule image peut contenir plusieurs codes‑barres, surtout lorsqu’il s’agit de données macro‑encodées. La méthode `ReadBarCodes` renvoie une collection de `BarCodeResult`, chaque objet représentant un code détecté.

```csharp
    // Step 2: Iterate over every barcode found
    foreach (BarCodeResult barcodeResult in barcodeReader.ReadBarCodes())
    {
```

*Pourquoi cette étape est importante :*  
Parcourir la collection garantit que vous capturez chaque occurrence, ce qui est essentiel pour les scénarios de traitement par lots ou lorsqu’un document intègre plusieurs codes.

## Étape 3 : Accéder aux propriétés étendues du Macro PDF417

Macro PDF417 stocke des métadonnées supplémentaires telles que les identifiants de fichier, les numéros de segment et le nombre total de segments. Ces valeurs sont exposées via la propriété `Extended.Pdf417` de `BarCodeResult`.

```csharp
        // Step 3: Pull extended Macro PDF417 information
        var macroInfo = barcodeResult.Extended.Pdf417;
```

*Pourquoi cette étape est importante :*  
Les champs étendus vous permettent de reconstruire des documents multi‑segments ou de valider que toutes les parties proviennent de la même source. Ignorer cette étape ne vous donnerait que le texte brut, perdant ainsi un contexte précieux.

## Étape 4 : Afficher les informations les plus utiles

Enfin, écrivez les données dans la console (ou tout autre journal) afin de vérifier l’opération de lecture. L’exemple affiche le type de code, le texte décodé et plusieurs champs macro.

```csharp
        // Step 4: Display key details
        Console.WriteLine($"Code Type: {barcodeResult.CodeTypeName}");
        Console.WriteLine($"Code Text: {barcodeResult.CodeText}");
        Console.WriteLine($"Macro PDF417 File ID: {macroInfo.MacroPdf417FileID}");
        // Additional macro fields are available:
        // macroInfo.MacroPdf417SegmentID
        // macroInfo.MacroPdf417SegmentsCount
    }
}
```

**Sortie console attendue**

```
Code Type: MacroPdf417
Code Text: 1234567890
Macro PDF417 File ID: 42
```

> **Remarque :** Si l’image ne contient pas de code‑barres Macro PDF417, `ReadBarCodes()` renvoie une collection vide et le corps de la boucle ne s’exécute jamais. Vérifiez toujours qu’il y a un résultat avant de poursuivre en production.

## Lire des codes‑barres à partir d’une image en C# – gestion des scénarios courants

### 1. Décodage de plusieurs formats de codes‑barres

Si vous devez détecter plus d’un format, passez un drapeau `DecodeType` combiné :

```csharp
using (BarCodeReader reader = new BarCodeReader(
           "sample.png",
           DecodeType.Pdf417 | DecodeType.QR | DecodeType.DataMatrix))
{
    // Same iteration logic as before
}
```

### 2. Gestion des images volumineuses

Les images de grande taille peuvent entraîner une forte consommation de mémoire. Redimensionnez l’image avant de la transmettre au lecteur :

```csharp
using (Bitmap original = new Bitmap("large.png"))
using (Bitmap resized = new Bitmap(original, new Size(1024, 768)))
{
    // Save resized image to a temporary stream and feed it to BarCodeReader
}
```

### 3. Gestion des erreurs

Enveloppez la logique de lecture dans un bloc try‑catch pour remonter les échecs de décodage :

```csharp
try
{
    // reading code from previous steps
}
catch (BarCodeException ex)
{
    Console.Error.WriteLine($"Barcode decoding failed: {ex.Message}");
}
```

## Exemple complet fonctionnel

Voici le programme complet que vous pouvez copier, coller et exécuter. Il inclut toutes les étapes, les directives `using` nécessaires et une structure simple de gestion des erreurs.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

class Program
{
    static void Main()
    {
        const string imagePath = "YOUR_DIRECTORY/ExtPDF417Meta.png";

        try
        {
            using (BarCodeReader barcodeReader = new BarCodeReader(
                       imagePath,
                       DecodeType.MacroPdf417))
            {
                bool anyFound = false;

                foreach (BarCodeResult barcodeResult in barcodeReader.ReadBarCodes())
                {
                    anyFound = true;
                    var macroInfo = barcodeResult.Extended.Pdf417;

                    Console.WriteLine($"Code Type: {barcodeResult.CodeTypeName}");
                    Console.WriteLine($"Code Text: {barcodeResult.CodeText}");
                    Console.WriteLine($"Macro PDF417 File ID: {macroInfo.MacroPdf417FileID}");
                    Console.WriteLine($"Segment ID: {macroInfo.MacroPdf417SegmentID}");
                    Console.WriteLine($"Segments Count: {macroInfo.MacroPdf417SegmentsCount}");
                    Console.WriteLine(new string('-', 40));
                }

                if (!anyFound)
                {
                    Console.WriteLine("No barcodes were detected in the image.");
                }
            }
        }
        catch (BarCodeException ex)
        {
            Console.Error.WriteLine($"Error reading barcode: {ex.Message}");
        }
    }
}
```

**Exécuter le programme** affiche chaque code‑barres Macro PDF417 détecté et ses champs étendus, ou vous informe qu’aucun code‑barres n’a été trouvé.

## Conclusion

Vous savez maintenant **comment utiliser BarCodeReader** pour lire des codes‑barres à partir d’applications C# basées sur des images, y compris l’extraction des métadonnées Macro PDF417. La solution couvre l’initialisation, l’itération, l’accès aux propriétés étendues et des conseils pratiques pour gérer plusieurs formats, des images volumineuses et les erreurs.

Ensuite, vous pourriez explorer :

* **Lecture de QR codes** – remplacez `DecodeType.MacroPdf417` par `DecodeType.QR`.  
* **Enregistrement des données décodées** dans une base de données ou un fichier JSON pour le traitement en aval.  
* **Intégration avec ASP.NET Core** pour accepter des images téléchargées via une API web.

N’hésitez pas à expérimenter avec différents types de codes‑barres et sources d’images. Bon codage !

## Que devriez‑vous apprendre ensuite ?

Les tutoriels suivants couvrent des sujets étroitement liés qui s’appuient sur les techniques démontrées dans ce guide. Chaque ressource inclut des exemples de code complets avec des explications pas à pas pour vous aider à maîtriser des fonctionnalités supplémentaires de l’API et explorer des approches d’implémentation alternatives dans vos propres projets.

- [tutoriel lecteur de code‑barres c# – lire les codes‑barres Macro PDF417 étape par étape avec GroupDocs.Barcode](/barcode/english/net/compact-pdf417-encoding/c-barcode-reader-tutorial-read-macro-pdf417-barcodes-step-by/)
- [Comment utiliser un générateur de code‑barres C# pour Macro PDF417](/barcode/english/net/compact-pdf417-encoding/how-to-use-a-barcode-generator-c-for-macro-pdf417/)
- [Lire un code‑barres à partir d’une image C# – guide complet avec Macro PDF417](/barcode/english/net/compact-pdf417-encoding/read-barcode-from-image-c-complete-guide-with-macro-pdf417/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}