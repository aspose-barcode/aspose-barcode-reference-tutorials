---
category: general
date: 2026-09-26
description: Apprenez à décoder le PDF417 en C# avec un exemple de lecteur de code‑barres
  pas à pas. Ce guide vous montre comment lire une image de code‑barres en C# à l’aide
  d’Aspose.BarCode.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to decode pdf417
- read barcode image c#
- c# barcode reader example
language: fr
lastmod: 2026-09-26
og_description: Comment décoder rapidement le PDF417 en C#. Suivez cet exemple de
  lecteur de code‑barres pour lire une image de code‑barres en C# avec Aspose.BarCode
  et extraire les détails macro.
og_image_alt: Screenshot showing how to decode PDF417 in C# using Aspose.BarCode
og_title: Comment décoder le PDF417 en C# – guide complet du lecteur de codes‑barres
schemas:
- author: Aspose
  dateModified: '2026-09-26'
  description: Learn how to decode PDF417 in C# with a step‑by‑step barcode reader
    example. This guide shows you how to read barcode image C# using Aspose.BarCode.
  headline: How to decode PDF417 in C# – barcode reader example
  type: TechArticle
tags:
- barcode
- pdf417
- csharp
title: Comment décoder le PDF417 en C# – exemple de lecteur de code‑barres
url: /fr/net/compact-pdf417-encoding/how-to-decode-pdf417-in-c-barcode-reader-example/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Comment décoder le PDF417 en C# – exemple de lecteur de code-barres

Si vous avez besoin de **how to decode PDF417** dans une application .NET, ce tutoriel fournit une solution complète, prête à l’emploi. Vous verrez comment lire une image de code-barres en C# à l’aide de la bibliothèque Aspose.BarCode, récupérer les informations macro étendues du PDF417 et afficher chaque champ pertinent.

Le décodage du PDF417 ne se limite pas au texte brut ; le format peut contenir des données de segmentation de fichier, des horodatages et des sommes de contrôle. Ce guide vous accompagne à chaque étape, explique pourquoi le code est structuré ainsi, et met en évidence les pièges courants que vous pourriez rencontrer lors de la mise en œuvre d’un exemple de lecteur de code-barres C#.

## Prérequis

* .NET 6.0 (ou version ultérieure) SDK installé  
* Visual Studio 2022 (ou tout IDE compatible C#)  
* **Aspose.BarCode for .NET** package NuGet (`Aspose.BarCode`)  
* Une image d’exemple Macro PDF417 (p. ex., `ExtPDF417Meta.png`)

Ces exigences garantissent que le code se compile et s’exécute sans configuration supplémentaire.

## Étape 1 : Installer le package NuGet Aspose.BarCode

La première étape dans tout projet **read barcode image C#** consiste à ajouter la bibliothèque de codes-barres. Ouvrez le terminal dans le dossier de votre solution et exécutez :

```bash
dotnet add package Aspose.BarCode
```

Le package fournit `BarCodeReader`, `DecodeType` et la propriété `Extended` utilisée pour accéder aux données macro. L’installer une fois rend les classes disponibles dans tout votre projet.

## Étape 2 : Créer un lecteur de code-barres pour une image Macro PDF417

Vous pouvez maintenant instancier `BarCodeReader` avec le chemin de l’image et spécifier `DecodeType.MacroPdf417`. Cela indique à la bibliothèque de rechercher le format PDF417 étendu contenant les informations macro.

```csharp
using Aspose.BarCode.BarCodeRecognition;

// Path to the Macro PDF417 image
string imagePath = @"YOUR_DIRECTORY/ExtPDF417Meta.png";

// Initialize the reader for Macro PDF417 decoding
using (BarCodeReader barcodeReader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
{
    // The reader is ready – next we will extract barcodes.
}
```

**Pourquoi c’est important :**  
`DecodeType.MacroPdf417` active l’analyseur spécifique aux macros. Si vous l’omettez, le lecteur ne renvoie que la charge utile en texte brut et ignore les champs macro dont vous avez probablement besoin pour la reconstruction du fichier.

## Étape 3 : Lire tous les codes-barres trouvés dans l’image

Une seule image peut contenir plusieurs symboles PDF417, surtout lorsque les données sont réparties sur plusieurs segments. Parcourir `ReadBarCodes()` garantit que vous capturez chaque segment.

```csharp
// Step 3: Iterate over each detected barcode
foreach (BarCodeResult barcodeResult in barcodeReader.ReadBarCodes())
{
    // Inside the loop we will access both basic and macro data.
}
```

**Pourquoi boucler :**  
Les données macro PDF417 apparaissent souvent en plusieurs segments. Traiter chaque `BarCodeResult` vous assure de collecter l’ensemble complet des champs macro, tels que `MacroPdf417FileID` et `MacroPdf417SegmentsCount`.

## Étape 4 : Récupérer et afficher les données de base du code-barres

L’objet `BarCodeResult` contient le type et le texte décodé. Afficher ces valeurs aide à vérifier que le lecteur a correctement identifié le symbole avant de plonger dans les détails macro.

```csharp
Console.WriteLine($"CodeType: {barcodeResult.CodeTypeName}");
Console.WriteLine($"CodeText: {barcodeResult.CodeText}");
```

**Astuce :** Si `CodeText` est vide, l’image peut être corrompue ou le mode de décodage est incorrect. Vérifiez à nouveau le `DecodeType` utilisé lors de l’initialisation.

## Étape 5 : Extraire les informations macro PDF417 étendues

Les données macro se trouvent sous `barcodeResult.Extended.Pdf417`. Chaque propriété correspond à un champ défini dans la spécification PDF417.

```csharp
// Step 5: Access macro-specific fields
var macroInfo = barcodeResult.Extended.Pdf417;

Console.WriteLine($"Pdf417MacroFileID: {macroInfo.MacroPdf417FileID}");
Console.WriteLine($"Pdf417MacroSegmentID: {macroInfo.MacroPdf417SegmentID}");
Console.WriteLine($"Pdf417MacroSegmentsCount: {macroInfo.MacroPdf417SegmentsCount}");
Console.WriteLine($"Pdf417MacroFileName: {macroInfo.MacroPdf417FileName}");
Console.WriteLine($"Pdf417MacroChecksum: {macroInfo.MacroPdf417Checksum}");
Console.WriteLine($"Pdf417MacroFileSize: {macroInfo.MacroPdf417FileSize}");
Console.WriteLine($"Pdf417MacroTimeStamp: {macroInfo.MacroPdf417TimeStamp}");
Console.WriteLine($"Pdf417MacroAddressee: {macroInfo.MacroPdf417Addressee}");
Console.WriteLine($"Pdf417MacroSender: {macroInfo.MacroPdf417Sender}");
Console.WriteLine($"MacroPdf417Terminator: {macroInfo.MacroPdf417Terminator}");
```

**Ce que signifie chaque champ**

| Propriété | Description |
|-----------|-------------|
| `MacroPdf417FileID` | Identifiant qui regroupe tous les segments appartenant au même fichier logique. |
| `MacroPdf417SegmentID` | Indice du segment actuel (commençant à 1). |
| `MacroPdf417SegmentsCount` | Nombre total de segments nécessaires pour reconstruire le fichier original. |
| `MacroPdf417FileName` | Nom de fichier optionnel intégré dans la macro. |
| `MacroPdf417Checksum` | Somme de contrôle CRC‑16 pour la vérification d’intégrité. |
| `MacroPdf417FileSize` | Taille attendue du fichier reconstruit (en octets). |
| `MacroPdf417TimeStamp` | Date‑heure de génération de la macro. |
| `MacroPdf417Addressee` | Identifiant du destinataire optionnel. |
| `MacroPdf417Sender` | Identifiant de l’expéditeur optionnel. |
| `MacroPdf417Terminator` | Indicateur de terminaison ; doit être `true` sur le dernier segment. |

Comprendre ces champs vous permet de reconstruire le fichier original, de valider l’intégrité des données et de mettre en œuvre une logique métier personnalisée (p. ex., rejeter les documents périmés).

## Étape 6 : Gérer plusieurs segments et reconstruire le fichier original (avancé)

Lorsque `MacroPdf417SegmentsCount` est supérieur à 1, vous devez collecter chaque segment, les trier par `MacroPdf417SegmentID` et concaténer les valeurs `CodeText`. Voici une implémentation concise :

```csharp
// Collect segments in a dictionary keyed by SegmentID
var segments = new SortedDictionary<int, string>();

foreach (BarCodeResult result in barcodeReader.ReadBarCodes())
{
    var macro = result.Extended.Pdf417;
    segments[macro.MacroPdf417SegmentID] = result.CodeText;
}

// Verify that we received all expected segments
int expectedCount = segments.First().Value != null
    ? barcodeReader.ReadBarCodes().First().Extended.Pdf417.MacroPdf417SegmentsCount
    : 0;

if (segments.Count == expectedCount)
{
    // Reconstruct the full payload
    string fullPayload = string.Concat(segments.Values);
    Console.WriteLine($"Reconstructed payload ({fullPayload.Length} chars):");
    Console.WriteLine(fullPayload);
}
else
{
    Console.WriteLine($"Warning: Expected {expectedCount} segments but received {segments.Count}.");
}
```

**Pourquoi c’est important :**  
Sans tri et concaténation, les données décodées seraient incomplètes ou corrompues. L’extrait montre également une programmation défensive en vérifiant le nombre de segments.

## Étape 7 : Conclure avec la gestion des erreurs et les bonnes pratiques

Un **c# barcode reader example** prêt pour la production doit anticiper les erreurs d’E/S, les formats non pris en charge et les images corrompues.

```csharp
try
{
    // Existing barcode reading code goes here
}
catch (FileNotFoundException ex)
{
    Console.Error.WriteLine($"Image file not found: {ex.Message}");
}
catch (BarCodeException ex)
{
    Console.Error.WriteLine($"Barcode processing error: {ex.Message}");
}
catch (Exception ex)
{
    Console.Error.WriteLine($"Unexpected error: {ex.Message}");
}
```

**Checklist des meilleures pratiques**

* Validez le chemin de l’image avant de créer `BarCodeReader`.  
* Utilisez les instructions `using` pour garantir la libération des ressources non gérées.  
* Enregistrez les champs macro pour les pistes d’audit—en particulier `MacroPdf417Checksum` et `MacroPdf417TimeStamp`.  
* Lors du traitement de gros fichiers, envisagez de diffuser le payload concaténé vers le disque plutôt que de le conserver entièrement en mémoire.

## Sortie attendue

L’exécution du programme complet avec un `ExtPDF417Meta.png` valide produit une sortie similaire à :

```
CodeType: MacroPdf417
CodeText: <base64‑encoded segment data>
Pdf417MacroFileID: 42
Pdf417MacroSegmentID: 1
Pdf417MacroSegmentsCount: 3
Pdf417MacroFileName: document.pdf
Pdf417MacroChecksum: 0x1A2B
Pdf417MacroFileSize: 254312
Pdf417MacroTimeStamp: 2024-03-15T10:23:45Z
Pdf417MacroAddressee: Acme Corp
Pdf417MacroSender: Warehouse 7
MacroPdf417Terminator: False
...
```

Si les trois segments sont présents, le bloc de reconstruction affiche le payload complet après le message de vérification.

## Conclusion

Vous savez maintenant **how to decode PDF417** en C# en utilisant un exemple de lecteur de code-barres robuste. Le tutoriel a couvert l’installation d’Aspose.BarCode, l’initialisation d’un `BarCodeReader` pour Macro PDF417, l’itération sur plusieurs codes-barres, l’extraction des champs macro, la reconstruction des données segmentées et la mise en œuvre de la gestion des erreurs.  

À partir d’ici, vous pouvez :

* Intégrer le lecteur dans une API web qui accepte les images téléchargées.  
* Stocker les métadonnées macro dans une base de données à des fins d’audit.  
* Étendre la solution à d’autres symbologies 2‑D en changeant `DecodeType` (p.

## Que devriez‑vous apprendre ensuite ?

Les tutoriels suivants couvrent des sujets étroitement liés qui s’appuient sur les techniques démontrées dans ce guide. Chaque ressource comprend des exemples de code complets et fonctionnels avec des explications étape par étape pour vous aider à maîtriser des fonctionnalités API supplémentaires et explorer des approches d’implémentation alternatives dans vos propres projets.

- [How to Read PDF417 in C# – Complete Barcode Reader Example](/barcode/english/net/compact-pdf417-encoding/how-to-read-pdf417-in-c-complete-barcode-reader-example/)
- [How to Create PDF417 Barcode with Aspose – Complete Step‑by‑Step Guide](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-with-aspose-complete-step-by-st/)
- [Read PDF417 barcode in C# – barcode reader example](/barcode/english/net/compact-pdf417-encoding/read-pdf417-barcode-in-c-barcode-reader-example/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}