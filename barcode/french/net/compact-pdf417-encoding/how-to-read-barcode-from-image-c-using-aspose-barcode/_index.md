---
category: general
date: 2026-10-02
description: Apprenez à lire les codes‑barres à partir d’une image en C# avec un exemple
  complet montrant comment décoder un code‑barres PDF417 à l’aide d’Aspose.BarCode.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- read barcode from image c#
- how to decode pdf417 barcode
language: fr
lastmod: 2026-10-02
og_description: Lire le code-barres à partir d’une image C# avec Aspose.BarCode. Ce
  tutoriel explique comment décoder le code-barres PDF417 et extraire les métadonnées
  étendues.
og_image_alt: Screenshot showing how to read barcode from image c# in Visual Studio
og_title: Lire un code‑barres à partir d’une image c# – guide étape par étape
schemas:
- author: Aspose
  dateModified: '2026-10-02'
  description: Learn how to read barcode from image c# with a complete example that
    shows how to decode PDF417 barcode using Aspose.BarCode.
  headline: How to read barcode from image c# using Aspose.BarCode
  type: TechArticle
- description: Learn how to read barcode from image c# with a complete example that
    shows how to decode PDF417 barcode using Aspose.BarCode.
  name: How to read barcode from image c# using Aspose.BarCode
  steps:
  - name: Create a `BarCodeReader` for a PDF417 image
    text: '```csharp using System; using Aspose.BarCode; using Aspose.BarCode.BarCodeRecognition;'
  - name: Iterate over all detected barcodes
    text: '```csharp // Step 2: Read every barcode found in the image foreach (BarCodeResult
      barcodeResult in barcodeReader.ReadBarCodes()) { // At this point you have successfully
      read barcode from image c#. ```'
  - name: Access the extended PDF417 macro metadata
    text: '```csharp // Step 3: Grab the macro‑PDF417 extended information var macro
      = barcodeResult.Extended.Pdf417;'
  - name: Output the barcode text and macro details
    text: '```csharp // Step 4: Print the basic barcode information Console.WriteLine($"Type:
      {barcodeResult.CodeTypeName}, Text: {barcodeResult.CodeText}");'
  - name: Handle errors and clean up resources
    text: 'The `using` statement automatically disposes the `BarCodeReader`. However,
      you should still catch exceptions that may arise from missing files or unsupported
      formats:'
  type: HowTo
tags:
- barcode
- C#
- Aspose.BarCode
title: Comment lire un code‑barres à partir d’une image C# avec Aspose.BarCode
url: /fr/net/compact-pdf417-encoding/how-to-read-barcode-from-image-c-using-aspose-barcode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Comment lire un code-barres à partir d'une image c# avec Aspose.BarCode

Si vous devez **lire un code-barres à partir d'une image c#**, ce guide vous accompagne à travers une solution complète et exécutable. Vous apprendrez à décoder un code-barres PDF417, à accéder à ses données macro étendues, et à afficher les résultats dans la console.

Lire des codes-barres à partir d'images est une exigence courante pour les systèmes d'inventaire, la validation de billets et le traitement de documents. Ce tutoriel couvre tout ce dont vous avez besoin : packages requis, explication du code, gestion des cas limites et sortie attendue. Aucune documentation externe n'est nécessaire ; l'exemple fonctionne immédiatement avec Aspose.BarCode .NET.

## Prérequis

Avant de commencer, assurez‑vous d'avoir :

* .NET 6.0 SDK ou version ultérieure installé  
* Visual Studio 2022 (ou tout IDE C#)  
* Une référence NuGet à **Aspose.BarCode** (version 23.10 ou plus récente)  
* Un fichier image contenant un code-barres PDF417 – par exemple `ExtPDF417Meta.png`

Si l'un de ces éléments manque, installez le SDK .NET, ajoutez le package NuGet avec `dotnet add package Aspose.BarCode`, et placez l'image dans un dossier que vous pouvez référencer depuis votre projet.

## Comment lire un code-barres à partir d'une image c# – étape par étape

Les sections suivantes décomposent l'implémentation en étapes logiques. Chaque étape comprend un extrait de code, une explication du **pourquoi** de l'étape, et une astuce que vous pouvez appliquer à des projets réels.

### Étape 1 : Créer un `BarCodeReader` pour une image PDF417

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

class Program
{
    static void Main()
    {
        // Step 1: Initialise the reader for a Macro PDF417 image
        const string imagePath = @"YOUR_DIRECTORY/ExtPDF417Meta.png";

        // The DecodeType enum tells the library which symbology to look for.
        // Using DecodeType.MacroPdf417 restricts the scan to PDF417 macro symbols.
        using (BarCodeReader barcodeReader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
        {
            // The reader is now ready to read barcode from image c# efficiently.
```

**Pourquoi c’est important** – Le constructeur `BarCodeReader` accepte le chemin de l'image et le type de code-barres attendu. Spécifier `MacroPdf417` restreint la recherche, ce qui améliore les performances et réduit les faux positifs lorsque l'image contient plusieurs symbologies.

**Astuce :** Si vous n'êtes pas sûr du type de code-barres, utilisez `DecodeType.AllSupportedTypes` et filtrez les résultats ultérieurement.

### Étape 2 : Parcourir tous les codes-barres détectés

```csharp
            // Step 2: Read every barcode found in the image
            foreach (BarCodeResult barcodeResult in barcodeReader.ReadBarCodes())
            {
                // At this point you have successfully read barcode from image c#.
```

**Pourquoi c’est important** – Une image macro PDF417 peut contenir plusieurs segments. La méthode `ReadBarCodes()` renvoie une collection, vous permettant de traiter chaque segment individuellement.

**Cas limite :** Si l'image ne contient aucun symbole PDF417, la collection est vide et le corps de la boucle ne s'exécute jamais. Envisagez d'ajouter une vérification après la boucle pour informer l'utilisateur.

### Étape 3 : Accéder aux métadonnées macro PDF417 étendues

```csharp
                // Step 3: Grab the macro‑PDF417 extended information
                var macro = barcodeResult.Extended.Pdf417;

                // The macro object holds file‑level data that PDF417 uses for
                // multi‑segment documents such as shipping manifests.
```

**Pourquoi c’est important** – La propriété `Extended.Pdf417` expose les champs définis par la spécification PDF417, tels que l'ID du fichier, l'ID du segment et le nom du fichier. Ces données sont essentielles lorsque vous devez reconstruire un document multipage à partir de scans de codes-barres séparés.

**Astuce :** Vérifiez toujours que `barcodeResult.Extended` n'est pas nul avant d'accéder à `Pdf417`. La bibliothèque renvoie `null` pour les symbologies qui ne supportent pas les données étendues.

### Étape 4 : Afficher le texte du code-barres et les détails macro

```csharp
                // Step 4: Print the basic barcode information
                Console.WriteLine($"Type: {barcodeResult.CodeTypeName}, Text: {barcodeResult.CodeText}");

                // Print macro‑specific fields
                Console.WriteLine($"Macro File ID: {macro.MacroPdf417FileID}, Segment ID: {macro.MacroPdf417SegmentID}");
                Console.WriteLine($"Segments Count: {macro.MacroPdf417SegmentsCount}, File Name: {macro.MacroPdf417FileName}");
            }
        }
    }
}
```

**Pourquoi c’est important** – La sortie console vous donne une visibilité immédiate à la fois sur le texte décodé et sur les métadonnées macro. Cela est utile pour le débogage et pour le traitement en aval, comme le stockage de l'information dans une base de données.

**Sortie attendue** (en supposant que l'image d'exemple contient un segment macro) :

```
Type: MacroPdf417, Text: https://example.com/document.pdf
Macro File ID: 12, Segment ID: 1
Segments Count: 3, File Name: shipment_manifest.pdf
```

Si l'image contient trois segments, la boucle affiche trois blocs, chacun avec un `Segment ID` différent.

### Étape 5 : Gérer les erreurs et nettoyer les ressources

L'instruction `using` libère automatiquement le `BarCodeReader`. Cependant, vous devez tout de même intercepter les exceptions pouvant survenir en cas de fichiers manquants ou de formats non pris en charge :

```csharp
        try
        {
            // Place the entire reader block here (Steps 1‑4)
        }
        catch (Exception ex)
        {
            Console.Error.WriteLine($"Error while trying to read barcode from image c#: {ex.Message}");
        }
```

**Pourquoi c’est important** – Les applications robustes ne plantent jamais parce qu'un fichier est absent ou que l'image est corrompue. Fournir un message d'erreur clair aide vous ou votre équipe de support à diagnostiquer rapidement le problème.

## Comment décoder un code-barres PDF417 avec Aspose.BarCode

Le mot‑clé secondaire **how to decode pdf417 barcode** apparaît naturellement dans cette section. Décoder un code-barres PDF417 suit le même schéma montré ci‑dessus, mais vous pouvez omettre le drapeau `MacroPdf417` si vous avez seulement besoin du texte brut :

```csharp
using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.Pdf417))
{
    foreach (BarCodeResult result in reader.ReadBarCodes())
    {
        Console.WriteLine($"Decoded text: {result.CodeText}");
    }
}
```

**Pourquoi vous pourriez choisir cette variante** – Lorsque le code-barres ne porte pas d'information macro, utiliser `DecodeType.Pdf417` réduit la charge de traitement et simplifie la gestion du résultat.

**Question fréquente :** *Et si le code-barres est tourné ?*  
Aspose.BarCode détecte automatiquement la rotation et la corrige, vous n'avez donc pas besoin de code de pré‑traitement d'image supplémentaire.

## Exemple complet et exécutable

Copiez le programme complet ci‑dessous dans un nouveau projet console (`dotnet new console`) et remplacez `YOUR_DIRECTORY/ExtPDF417Meta.png` par le chemin réel vers votre image.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

class Program
{
    static void Main()
    {
        const string imagePath = @"YOUR_DIRECTORY/ExtPDF417Meta.png";

        try
        {
            using (BarCodeReader barcodeReader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
            {
                foreach (BarCodeResult barcodeResult in barcodeReader.ReadBarCodes())
                {
                    var macro = barcodeResult.Extended?.Pdf417;

                    Console.WriteLine($"Type: {barcodeResult.CodeTypeName}, Text: {barcodeResult.CodeText}");

                    if (macro != null)
                    {
                        Console.WriteLine($"Macro File ID: {macro.MacroPdf417FileID}, Segment ID: {macro.MacroPdf417SegmentID}");
                        Console.WriteLine($"Segments Count: {macro.MacroPdf417SegmentsCount}, File Name: {macro.MacroPdf417FileName}");
                    }
                    else
                    {
                        Console.WriteLine("No macro PDF417 metadata available.");
                    }
                }
            }
        }
        catch (Exception ex)
        {
            Console.Error.WriteLine($"Error while trying to read barcode from image c#: {ex.Message}");
        }
    }
}
```

L'exécution du programme affiche le type de code‑barres, le texte décodé et les éventuelles métadonnées macro. Si l'image ne contient pas de macro PDF417, le programme vous en informe de manière élégante.

## Conclusion

Vous savez maintenant comment **lire un code‑barres à partir d'une image c#** avec Aspose.BarCode, comment **décoder un code‑barres PDF417**, et comment extraire les champs étendus macro‑PDF417. La solution couvre l'initialisation, l'itération, l'accès aux métadonnées, la gestion des erreurs et une variante pour le décodage PDF417 simple.

À partir d'ici, vous pouvez :

* Stocker les données extraites dans une base de données SQL pour une récupération ultérieure.  
* Combiner plusieurs segments pour reconstruire le document original.  
* Explorer d'autres symbologies prises en charge par Aspose.BarCode, such

## Que devriez‑vous apprendre ensuite ?

Les tutoriels suivants couvrent des sujets étroitement liés qui s'appuient sur les techniques démontrées dans ce guide. Chaque ressource inclut des exemples de code complets et fonctionnels avec des explications étape par étape pour vous aider à maîtriser des fonctionnalités API supplémentaires et à explorer des approches d'implémentation alternatives dans vos propres projets.

- [Comment lire le PDF417 en C# – Exemple complet de code‑barres](/barcode/english/net/compact-pdf417-encoding/how-to-read-pdf417-in-c-complete-barcode-example/)
- [Comment lire le PDF417 en C# – Exemple complet de lecteur de code‑barres](/barcode/english/net/compact-pdf417-encoding/how-to-read-pdf417-in-c-complete-barcode-reader-example/)
- [Comment générer une image de code‑barres PDF417 en C# avec Aspose](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-image-in-c-with-aspose/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}