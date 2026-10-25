---
category: general
date: 2026-10-24
description: Apprenez à lire le code‑barres PDF417 en C# avec Aspose.BarCode. Ce tutoriel
  couvre la lecture d’une image de code‑barres, l’extraction des champs Macro PDF417
  et la gestion des scénarios courants.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to read pdf417 barcode
- read barcode image c#
- read barcode with aspose
language: fr
lastmod: 2026-10-24
og_description: Comment lire le code‑barres PDF417 en C# avec Aspose.BarCode. Suivez
  ce tutoriel complet pour décoder les images, récupérer les métadonnées Macro PDF417
  et éviter les pièges courants.
og_image_alt: Screenshot showing how to read PDF417 barcode results in a C# console
  application
og_title: Comment lire le code‑barres PDF417 en C# avec Aspose – guide complet
schemas:
- author: Aspose
  dateModified: '2026-10-24'
  description: Learn how to read PDF417 barcode in C# using Aspose.BarCode. This tutorial
    covers reading a barcode image, extracting Macro PDF417 fields, and handling common
    scenarios.
  headline: How to read PDF417 barcode in C# with Aspose – step‑by‑step guide
  type: TechArticle
- description: Learn how to read PDF417 barcode in C# using Aspose.BarCode. This tutorial
    covers reading a barcode image, extracting Macro PDF417 fields, and handling common
    scenarios.
  name: How to read PDF417 barcode in C# with Aspose – step‑by‑step guide
  steps:
  - name: Why use `DecodeType.MacroPdf417`?
    text: '* **Macro PDF417** stores additional fields (file ID, segment count, timestamps,
      etc.) that are not present in standard PDF417. * The `Extended` property of
      `BarCodeResult` is populated only when you request the macro type, saving you
      a separate parsing step.'
  - name: What each property means
    text: '| Property | Description | |----------|-------------| | **MacroPdf417FileID**
      | Unique identifier for the whole multi‑segment document. | | **MacroPdf417SegmentID**
      | Index of the current segment (starting at 0). | | **MacroPdf417SegmentsCount**
      | Total number of segments that belong to the file. | '
  - name: Missing macro fields
    text: 'Sometimes a PDF417 barcode is generated without the optional macro fields.
      Accessing a missing property returns `null` or `0`. Guard against this if you
      plan to store the values:'
  - name: Corrupted or low‑quality images
    text: 'If the image is blurry, you can improve detection by enabling the `BarCodeReader`
      quality options:'
  - name: Multiple barcode formats in one image
    text: 'If you suspect other barcode types might be present, use `DecodeType.AllSupported`
      and filter results:'
  type: HowTo
- questions:
  - answer: Yes. Change `DecodeType.MacroPdf417` to `DecodeType.Pdf417`. The `Extended`
      property will be empty, but `CodeText` and `CodeTypeName` remain available.
    question: Can I read a standard PDF417 (non‑macro) with the same code?
  - answer: Absolutely. Use the overload `new BarCodeReader(Stream, DecodeType)` and
      pass a `FileStream` or `MemoryStream`. This is useful when the image comes from
      a web API.
    question: Does Aspose.BarCode support reading from a stream instead of a file
      path?
  - answer: 'The `MacroPdf417Checksum` field contains the raw CRC‑16 value. You can
      recompute the checksum on the reconstructed file and compare it to ensure data
      integrity. ## Next steps and related topics * **Write PDF417 barcodes** – explore
      `BarCodeGenerator` to create macro barcodes for testing. * **Combine'
    question: How do I validate the checksum?
  type: FAQPage
tags:
- barcode
- Aspose.BarCode
- C#
title: Comment lire le code‑barres PDF417 en C# avec Aspose – guide étape par étape
url: /fr/net/compact-pdf417-encoding/how-to-read-pdf417-barcode-in-c-with-aspose-step-by-step-gui/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Comment lire le code‑barres PDF417 en C# avec Aspose – guide étape par étape

Si vous avez besoin de **comment lire un code‑barres PDF417** dans une application .NET, ce guide vous montre exactement comment lire le code‑barres PDF417 en C# en utilisant la bibliothèque Aspose.BarCode. Que vous traitiez des documents numérisés, des captures mobiles ou des images importées par lots, le code ci‑dessous décode le code‑barres et extrait chaque propriété Macro PDF417 dont vous pourriez avoir besoin.

Lire une image de code‑barres en C# peut sembler intimidant, surtout lorsque le code‑barres contient des métadonnées étendues. Ce tutoriel élimine les approximations en fournissant un exemple complet et exécutable, en expliquant chaque ligne et en couvrant les cas limites tels que les segments macro manquants ou les images corrompues. À la fin, vous pourrez intégrer le décodage PDF417 dans n’importe quel projet C# en toute confiance.

## Prérequis

Avant de commencer, assurez‑vous d’avoir :

* .NET 6.0 SDK ou version ultérieure installé  
* Visual Studio 2022 (ou tout IDE supportant .NET)  
* Une licence ou une évaluation gratuite d’**Aspose.BarCode for .NET** – vous pouvez obtenir une clé temporaire depuis le site web d’Aspose  
* Un fichier image contenant un code‑barres Macro PDF417 (par ex., `ExtPDF417Meta.png`)

> **Conseil pro :** Si vous avez seulement besoin d’expérimenter, Aspose propose un essai de 30 jours incluant toutes les fonctionnalités de lecture de code‑barres.

## Étape 1 : Installer le package NuGet Aspose.BarCode

Ouvrez le dossier de votre projet dans un terminal et exécutez :

```bash
dotnet add package Aspose.BarCode
```

Le package ajoute l’espace de noms `Aspose.BarCode.ReadRecognition`, qui contient la classe `BarCodeReader` utilisée pour décoder les images.

## Étape 2 : Créer un BarCodeReader pour une image PDF417

Le constructeur `BarCodeReader` prend deux arguments : le chemin du fichier image et le `DecodeType` que vous souhaitez cibler. Spécifier `DecodeType.MacroPdf417` indique à Aspose de rechercher les symboles Macro PDF417 et de remplir automatiquement les propriétés étendues.

```csharp
using Aspose.BarCode.ReadRecognition;

// Replace with the actual path to your barcode image
string imagePath = @"C:\Barcodes\ExtPDF417Meta.png";

using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
{
    // The reader is now ready to scan the image
```

### Pourquoi utiliser `DecodeType.MacroPdf417` ?

* **Macro PDF417** stocke des champs supplémentaires (ID de fichier, nombre de segments, horodatages, etc.) qui ne sont pas présents dans le PDF417 standard.  
* La propriété `Extended` de `BarCodeResult` est remplie uniquement lorsque vous demandez le type macro, vous évitant ainsi une étape de parsing séparée.

## Étape 3 : Parcourir tous les codes‑barres détectés

Une seule image peut contenir plusieurs symboles PDF417 (par exemple, lorsqu’un document est réparti sur plusieurs pages). La méthode `ReadBarCodes()` renvoie un `IEnumerable<BarCodeResult>` que vous pouvez parcourir.

```csharp
    foreach (BarCodeResult result in reader.ReadBarCodes())
    {
        // Basic information
        Console.WriteLine($"CodeType: {result.CodeTypeName}");
        Console.WriteLine($"CodeText: {result.CodeText}");
```

Si l’image ne contient aucun code‑barres, la boucle ne s’exécute tout simplement jamais, et le programme se termine proprement. Ce comportement rend le code sûr pour le traitement par lots où certains fichiers peuvent être dépourvus de code‑barres.

## Étape 4 : Afficher les propriétés étendues Macro PDF417

La propriété `Extended.Pdf417` regroupe tous les champs spécifiques au macro. Chaque champ correspond directement à la spécification PDF417, vous pouvez donc les stocker dans une base de données, les consigner ou les utiliser pour une validation supplémentaire.

```csharp
        // Macro PDF417 extended properties
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
    }
}
```

### Signification de chaque propriété

| Propriété | Description |
|----------|-------------|
| **MacroPdf417FileID** | Identifiant unique pour l’ensemble du document multi‑segment. |
| **MacroPdf417SegmentID** | Indice du segment actuel (commençant à 0). |
| **MacroPdf417SegmentsCount** | Nombre total de segments appartenant au fichier. |
| **MacroPdf417FileName** | Nom de fichier optionnel intégré dans le code‑barres. |
| **MacroPdf417Checksum** | Somme de contrôle CRC‑16 pour le bloc de données macro. |
| **MacroPdf417FileSize** | Taille originale du fichier en octets. |
| **MacroPdf417TimeStamp** | Horodatage de la génération du code‑barres macro. |
| **MacroPdf417Addressee** | Destinataire prévu du document. |
| **MacroPdf417Sender** | Émetteur du document. |
| **MacroPdf417Terminator** | Indicateur de terminaison signalant la fin de la séquence macro. |

Ces champs sont particulièrement utiles lorsque vous reconstituez un gros PDF ou une image qui a été découpé en plusieurs symboles PDF417 pour l’impression sur un support à basse résolution.

## Étape 5 : Gérer les cas limites courants

### Champs macro manquants

Parfois, un code‑barres PDF417 est généré sans les champs macro optionnels. Accéder à une propriété manquante renvoie `null` ou `0`. Protégez‑vous contre cela si vous prévoyez de stocker les valeurs :

```csharp
string fileName = result.Extended.Pdf417.MacroPdf417FileName ?? "Unnamed";
long fileSize = result.Extended.Pdf417.MacroPdf417FileSize;
```

### Images corrompues ou de mauvaise qualité

Si l’image est floue, vous pouvez améliorer la détection en activant les options de qualité du `BarCodeReader` :

```csharp
reader.BarcodeSettings.ImageQuality = 90; // value between 0‑100
reader.BarcodeSettings.PureBarcode = false; // allow detection in noisy backgrounds
```

Ces paramètres sont optionnels mais peuvent augmenter considérablement le taux de réussite pour les documents numérisés.

### Plusieurs formats de code‑barres dans une même image

Si vous pensez que d’autres types de code‑barres peuvent être présents, utilisez `DecodeType.AllSupported` et filtrez les résultats :

```csharp
using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.AllSupported))
{
    foreach (BarCodeResult result in reader.ReadBarCodes())
    {
        if (result.CodeType == DecodeType.MacroPdf417)
        {
            // Process macro PDF417 as shown above
        }
    }
}
```

## Exemple complet exécutable

Copiez le programme suivant dans un nouveau projet console (`dotnet new console`) et exécutez‑le. Remplacez la variable `imagePath` par le chemin de votre propre image Macro PDF417.

```csharp
using System;
using Aspose.BarCode.ReadRecognition;

class Program
{
    static void Main()
    {
        // Path to the barcode image
        string imagePath = @"C:\Barcodes\ExtPDF417Meta.png";

        // Initialize the reader for Macro PDF417
        using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
        {
            // Optional: improve detection on low‑quality scans
            reader.BarcodeSettings.ImageQuality = 90;
            reader.BarcodeSettings.PureBarcode = false;

            // Iterate through every barcode found in the image
            foreach (BarCodeResult result in reader.ReadBarCodes())
            {
                Console.WriteLine($"CodeType: {result.CodeTypeName}");
                Console.WriteLine($"CodeText: {result.CodeText}");

                // Output extended Macro PDF417 fields
                Console.WriteLine($"Pdf417MacroFileID: {result.Extended.Pdf417.MacroPdf417FileID}");
                Console.WriteLine($"Pdf417MacroSegmentID: {result.Extended.Pdf417.MacroPdf417SegmentID}");
                Console.WriteLine($"Pdf417MacroSegmentsCount: {result.Extended.Pdf417.MacroPdf417SegmentsCount}");
                Console.WriteLine($"Pdf417MacroFileName: {result.Extended.Pdf417.MacroPdf417FileName ?? \"N/A\"}");
                Console.WriteLine($"Pdf417MacroChecksum: {result.Extended.Pdf417.MacroPdf417Checksum}");
                Console.WriteLine($"Pdf417MacroFileSize: {result.Extended.Pdf417.MacroPdf417FileSize}");
                Console.WriteLine($"Pdf417MacroTimeStamp: {result.Extended.Pdf417.MacroPdf417TimeStamp}");
                Console.WriteLine($"Pdf417MacroAddressee: {result.Extended.Pdf417.MacroPdf417Addressee ?? \"N/A\"}");
                Console.WriteLine($"Pdf417MacroSender: {result.Extended.Pdf417.MacroPdf417Sender ?? \"N/A\"}");
                Console.WriteLine($"MacroPdf417Terminator: {result.Extended.Pdf417.MacroPdf417Terminator}");
                Console.WriteLine(new string('-', 40));
            }
        }
    }
}
```

**Sortie attendue** (les valeurs différeront selon votre image) :

```
CodeType: MacroPdf417
CodeText: 1234567890ABCDEFGHIJ
Pdf417MacroFileID: 42
Pdf417MacroSegmentID: 0
Pdf417MacroSegmentsCount: 3
Pdf417MacroFileName: Invoice_2026_10.pdf
Pdf417MacroChecksum: 32768
Pdf417MacroFileSize: 245760
Pdf417MacroTimeStamp: 2026-10-24T14:32:10Z
Pdf417MacroAddressee: AccountingDept
Pdf417MacroSender: SalesTeam
MacroPdf417Terminator: True
----------------------------------------
```

Si l’image ne contient aucun symbole Macro PDF417, le programme n’écrit rien et se termine silencieusement—parfait pour les travaux par lots qui traitent de nombreux fichiers.

## Questions fréquemment posées

**Q : Puis‑je lire un PDF417 standard (non‑macro) avec le même code ?**  
R : Oui. Remplacez `DecodeType.MacroPdf417` par `DecodeType.Pdf417`. La propriété `Extended` sera vide, mais `CodeText` et `CodeTypeName` restent disponibles.

**Q : Aspose.BarCode prend‑il en charge la lecture depuis un flux au lieu d’un chemin de fichier ?**  
R : Absolument. Utilisez la surcharge `new BarCodeReader(Stream, DecodeType)` et passez un `FileStream` ou un `MemoryStream`. Cela est utile lorsque l’image provient d’une API web.

**Q : Comment valider la somme de contrôle ?**  
R : Le champ `MacroPdf417Checksum` contient la valeur brute du CRC‑16. Vous pouvez recalculer la somme de contrôle sur le fichier reconstruit et la comparer pour garantir l’intégrité des données.

## Prochaines étapes et sujets associés

* **Écrire des codes‑barres PDF417** – explorez `BarCodeGenerator` pour créer des codes‑barres macro à des fins de test.  
* **Combiner plusieurs segments** – après avoir lu tous les segments, triez‑les par `MacroPdf417SegmentID` et concaténez `CodeText` pour reconstituer la charge utile originale.  
* **Optimisation des performances** – pour les scénarios à haut débit, réutilisez une seule instance de `BarCodeReader` sur de nombreuses images et

## Que devriez‑vous apprendre ensuite ?

Les tutoriels suivants couvrent des sujets étroitement liés qui s’appuient sur les techniques démontrées dans ce guide. Chaque ressource comprend des exemples de code complets et fonctionnels avec des explications étape par étape pour vous aider à maîtriser des fonctionnalités API supplémentaires et à explorer des approches d’implémentation alternatives dans vos propres projets.

- [Comment lire le PDF417 en C# – Exemple complet de code‑barres](/barcode/english/net/compact-pdf417-encoding/how-to-read-pdf417-in-c-complete-barcode-example/)
- [Comment créer un code‑barres macro PDF417 en C# avec Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/how-to-create-macro-pdf417-barcode-in-c-using-aspose-barcode/)
- [Lire un code‑barres depuis une image C# – guide complet avec Macro PDF417](/barcode/english/net/compact-pdf417-encoding/read-barcode-from-image-c-complete-guide-with-macro-pdf417/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}