---
category: general
date: 2026-09-22
description: Apprenez à lire les codes-barres PDF417 en C# avec un exemple complet
  de lecteur de codes-barres. Ce tutoriel vous montre comment lire rapidement et de
  manière fiable une image de code-barres en C#.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to read pdf417
- read barcode image c#
- c# barcode reader example
language: fr
lastmod: 2026-09-22
og_description: Comment lire les codes-barres PDF417 en C# à l'aide d'un exemple concis
  de lecteur de codes-barres. Suivez le guide pour décoder les images Macro PDF417
  et extraire les métadonnées.
og_image_alt: Screenshot of C# code that reads a PDF417 barcode and prints its metadata
og_title: Comment lire les codes-barres PDF417 en C# – exemple complet de lecteur
  de code-barres
schemas:
- author: Aspose
  dateModified: '2026-09-22'
  description: Learn how to read PDF417 barcodes in C# with a full barcode reader
    example. This tutorial shows you how to read barcode image C# quickly and reliably.
  headline: How to read PDF417 barcodes in C# – complete step‑by‑step guide
  type: TechArticle
- description: Learn how to read PDF417 barcodes in C# with a full barcode reader
    example. This tutorial shows you how to read barcode image C# quickly and reliably.
  name: How to read PDF417 barcodes in C# – complete step‑by‑step guide
  steps:
  - name: Why each step matters
    text: '1. **Creating the reader with `DecodeType.MacroPdf417`** – Macro PDF417
      is a special variant that can carry file‑level metadata. Specifying the decode
      type ensures the SDK parses those extra fields instead of treating the code
      as a plain PDF417. 2. **Iterating over `ReadBarCodes()`** – An image can '
  - name: Reading a non‑macro PDF417 barcode
    text: If your source images contain regular PDF417 codes (no macro metadata),
      replace `DecodeType.MacroPdf417` with `DecodeType.Pdf417`. The rest of the code
      stays identical, but the `Extended.Pdf417` block will be empty because those
      fields simply don’t exist.
  - name: Handling multi‑segment PDFs
    text: 'Macro PDF417 can split a large document across several barcode segments.
      To reassemble the original file you must:'
  - name: Dealing with corrupted images
    text: '- **Low contrast** – Increase image preprocessing (e.g., histogram equalization)
      before passing it to `BarCodeReader`. - **Rotation** – Use `barcodeReader.SetRotateAngle(90)`
      or enable auto‑rotate if the SDK supports it. - **Partial scans** – Ensure the
      image resolution is at least 300 dpi; otherwis'
  - name: Next steps
    text: '- Explore **read barcode image C#** techniques for other symbologies (QR,
      DataMatrix) using the same `BarCodeReader` API. - Integrate the barcode decoder
      into an ASP.NET Core service to process uploads on the fly. - Experiment with
      image preprocessing libraries (e.g., `OpenCvSharp`) to boost success'
  type: HowTo
tags:
- barcode
- pdf417
- c#
title: Comment lire les codes‑barres PDF417 en C# – guide complet étape par étape
url: /fr/net/compact-pdf417-encoding/how-to-read-pdf417-barcodes-in-c-complete-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Comment lire les codes-barres PDF417 en C# – guide complet étape par étape

Si vous avez besoin de **how to read pdf417** dans une application .NET, ce guide vous montre le code exact et le raisonnement nécessaires. À la fin des deux premières phrases, vous saurez comment lire une image de code-barres en C# en utilisant la classe populaire `BarCodeReader`, et vous disposerez d’un exemple prêt à l’exécution qui extrait chaque élément des métadonnées Macro PDF417.

Lire les codes-barres PDF417 est une exigence courante lors du traitement d’étiquettes d’expédition, de cartes d’embarquement ou de documents sécurisés. Ce tutoriel couvre tout, de la configuration du lecteur à la gestion des cas limites, afin que vous puissiez intégrer la lecture de codes-barres en toute confiance.

## Ce que vous allez réaliser

- Décoder un fichier image Macro PDF417.
- Afficher les informations de base du code-barres (type et texte).
- Accéder à tous les champs étendus Macro PDF417 tels que l’ID du fichier, le nombre de segments et le timestamp.
- Comprendre les pièges courants lors du travail avec des codes PDF417 multi‑segments.

**Prérequis**

- .NET 6.0 ou supérieur (le code fonctionne également avec .NET Framework 4.7+).
- Une référence au SDK de code-barres qui fournit `BarCodeReader`, `DecodeType` et `BarCodeResult` (par ex., Aspose.BarCode, Dynamsoft, ou toute bibliothèque exposant la même API).
- Un fichier image (`ExtPDF417Meta.png`) contenant un code-barres Macro PDF417.

> **Conseil pro :** Placez l'image dans un dossier relatif à la racine de votre projet et définissez sa propriété **Copy to Output Directory** sur *Copy if newer* afin que le chemin fonctionne lors du débogage.

![Comment lire le code-barres PDF417 avec C#](https://example.com/placeholder-image.png)

## Comment lire le code-barres PDF417 en C# – le code complet

Voici un programme autonome que vous pouvez coller dans une application console. Il crée un lecteur de code-barres, parcourt chaque résultat décodé et affiche à la fois les champs standards et étendus du Macro PDF417.

```csharp
using System;
using Aspose.BarCode;          // Replace with the namespace of your barcode SDK
using Aspose.BarCode.BarCodeRecognition;

class Program
{
    static void Main()
    {
        // Step 1: Create a barcode reader for a Macro PDF417 image
        // The second argument tells the SDK to look specifically for Macro PDF417 codes.
        using var barcodeReader = new BarCodeReader(
            "YOUR_DIRECTORY/ExtPDF417Meta.png",
            DecodeType.MacroPdf417);

        // Step 2: Decode all barcodes present in the image
        foreach (BarCodeResult result in barcodeReader.ReadBarCodes())
        {
            // Step 3: Display the basic barcode information
            Console.WriteLine($"CodeType: {result.CodeTypeName}");
            Console.WriteLine($"CodeText: {result.CodeText}");

            // Step 4: Output Macro PDF417 specific metadata
            // All properties are available through the Extended.Pdf417 object.
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
    }
}
```

### Pourquoi chaque étape est importante

1. **Creating the reader with `DecodeType.MacroPdf417`** – Macro PDF417 est une variante spéciale qui peut contenir des métadonnées au niveau du fichier. Spécifier le type de décodage garantit que le SDK analyse ces champs supplémentaires au lieu de traiter le code comme un simple PDF417.  
2. **Iterating over `ReadBarCodes()`** – Une image peut contenir plusieurs codes-barres (par ex., un QR code à côté d’un PDF417). La boucle assure que vous capturez chaque résultat.  
3. **Printing `CodeTypeName` and `CodeText`** – Ce sont les propriétés les plus fréquemment utilisées ; elles vous donnent le nom de la symbologie et la charge utile lisible par l’homme.  
4. **Accessing `Extended.Pdf417`** – L’objet `Extended` n’apparaît que pour les types de décodage liés au PDF417. Chaque propriété correspond directement à la spécification Macro PDF417, vous permettant de reconstruire le fichier original ou de valider l’ordre des segments.

## Variations courantes et cas limites

### Lecture d’un code-barres PDF417 non‑macro

Si vos images sources contiennent des codes PDF417 classiques (sans métadonnées macro), remplacez `DecodeType.MacroPdf417` par `DecodeType.Pdf417`. Le reste du code reste identique, mais le bloc `Extended.Pdf417` sera vide car ces champs n’existent tout simplement pas.

### Gestion des PDF multi‑segments

Macro PDF417 peut diviser un gros document en plusieurs segments de code-barres. Pour réassembler le fichier original, vous devez :

1. Collecter le `Pdf417MacroSegmentID` de chaque segment.  
2. Trier les segments par leur ID.  
3. Vérifier que `Pdf417MacroSegmentsCount` correspond au nombre de segments reçus.  
4. Concaténer le `CodeText` de chaque segment dans l’ordre.  
5. Optionnellement valider le `Pdf417MacroChecksum`.

Voici un extrait concis qui démontre la logique de réassemblage :

```csharp
var segments = new SortedDictionary<int, string>();
int expectedCount = 0;

foreach (var result in barcodeReader.ReadBarCodes())
{
    int segId = result.Extended.Pdf417.MacroPdf417SegmentID;
    int segCount = result.Extended.Pdf417.MacroPdf417SegmentsCount;
    expectedCount = segCount;               // will be the same for every segment
    segments[segId] = result.CodeText;       // store payload by segment ID
}

// Verify we have all parts
if (segments.Count == expectedCount)
{
    string fullPayload = string.Concat(segments.Values);
    Console.WriteLine("Reassembled payload:");
    Console.WriteLine(fullPayload);
}
else
{
    Console.WriteLine($"Missing segments: expected {expectedCount}, received {segments.Count}");
}
```

### Gestion des images corrompues

- **Faible contraste** – Augmentez le prétraitement de l’image (par ex., égalisation d’histogramme) avant de la transmettre à `BarCodeReader`.  
- **Rotation** – Utilisez `barcodeReader.SetRotateAngle(90)` ou activez la rotation automatique si le SDK le supporte.  
- **Scans partiels** – Assurez-vous que la résolution de l’image est d’au moins 300 dpi ; sinon le SDK peut manquer de petits segments.

## Exemple de lecteur de code-barres c# – bonnes pratiques

| Pratique | Raison |
|----------|--------|
| **Libérez le lecteur avec `using`** | Garantit que les ressources natives sont libérées rapidement, évitant les fuites de mémoire. |
| **Validez que `result.Extended` n’est pas null** | Certaines SDK renvoient `null` pour les codes non‑macro ; la vérification évite une `NullReferenceException`. |
| **Enregistrez le `Pdf417MacroFileID`** | Cet identifiant est unique par fichier et utile pour les pistes d’audit. |
| **Enveloppez le décodage dans un try/catch** | Les erreurs d’E/S (fichier manquant) ou les formats non pris en charge lèvent des exceptions qui doivent être gérées proprement. |

```csharp
try
{
    // decoding logic here
}
catch (FileNotFoundException ex)
{
    Console.Error.WriteLine($"Image not found: {ex.FileName}");
}
catch (BarCodeException ex)
{
    Console.Error.WriteLine($"Barcode decoding failed: {ex.Message}");
}
```

## Sortie attendue

L’exécution du programme complet sur un `ExtPDF417Meta.png` correctement formaté produit une sortie similaire à :

```
CodeType: MacroPdf417
CodeText: https://example.com/document.pdf
Pdf417MacroFileID: 12345
Pdf417MacroSegmentID: 1
Pdf417MacroSegmentsCount: 3
Pdf417MacroFileName: document.pdf
Pdf417MacroChecksum: 0x1A2B
Pdf417MacroFileSize: 204800
Pdf417MacroTimeStamp: 2024-08-15T14:32:00Z
Pdf417MacroAddressee: John Doe
Pdf417MacroSender: Acme Corp.
MacroPdf417Terminator: True
----------------------------------------
```

Si l’image contient plusieurs segments, la boucle affichera les métadonnées de chaque segment séquentiellement.

## Conclusion

Vous savez maintenant **how to read pdf417** les codes-barres en C# et disposez d’un **c# barcode reader example** qui extrait chaque champ Macro PDF417. La solution couvre le décodage de base, l’extraction des métadonnées, le réassemblage multi‑segments et la gestion des erreurs, vous offrant une base prête pour la production pour tout flux de traitement de documents.

### Prochaines étapes

- Explorez les techniques **read barcode image C#** pour d’autres symbologies (QR, DataMatrix) en utilisant la même API `BarCodeReader`.  
- Intégrez le décodeur de code-barres dans un service ASP.NET Core pour traiter les téléchargements à la volée.  
- Expérimentez avec des bibliothèques de prétraitement d’image (par ex., `OpenCvSharp`) pour améliorer les taux de réussite sur des scans de mauvaise qualité.

Bon codage, et n’hésitez pas à adapter l’exemple à votre cas d’utilisation spécifique !

## Que devriez‑vous apprendre ensuite ?

Les tutoriels suivants couvrent des sujets étroitement liés qui s’appuient sur les techniques démontrées dans ce guide. Chaque ressource comprend des exemples de code complets et fonctionnels avec des explications étape par étape pour vous aider à maîtriser des fonctionnalités API supplémentaires et explorer des approches d’implémentation alternatives dans vos propres projets.

- [Comment enregistrer un code-barres en C# – Générer des codes-barres PDF417](/barcode/english/net/compact-pdf417-encoding/how-to-save-barcode-in-c-generate-pdf417-barcodes/)
- [Comment lire le PDF417 en C# – Guide complet étape par étape](/barcode/english/net/compact-pdf417-encoding/how-to-read-pdf417-in-c-complete-step-by-step-guide/)
- [Comment définir le niveau d’erreur dans le code-barres PDF417 – Guide complet](/barcode/english/net/compact-pdf417-encoding/how-to-set-error-level-in-pdf417-barcode-complete-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}