---
category: general
date: 2026-08-09
description: Comment lire le PDF417 en C# avec le BarCodeReader. Apprenez à lire les
  fichiers PNG de codes-barres, à gérer plusieurs codes-barres et à extraire les métadonnées
  étendues.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to read pdf417
- c# barcode reader
- read multiple barcodes
- read barcode png
- read barcode extended
language: fr
lastmod: 2026-08-09
og_description: Comment lire le PDF417 en C# avec Aspose.BarCode. Ce tutoriel vous
  montre comment lire des fichiers PNG de codes-barres, traiter plusieurs codes-barres
  dans une même image et récupérer les métadonnées étendues du PDF417.
og_image_alt: Screenshot of C# BarCodeReader console output displaying PDF417 metadata
og_title: Comment lire le PDF417 en C# – tutoriel de lecteur de code-barres
schemas:
- author: Aspose
  dateModified: '2026-08-09'
  description: How to read PDF417 in C# using the BarCodeReader. Learn to read barcode
    PNG files, handle multiple barcodes, and extract extended metadata.
  headline: How to read PDF417 in C# – complete barcode reader guide
  type: TechArticle
- description: How to read PDF417 in C# using the BarCodeReader. Learn to read barcode
    PNG files, handle multiple barcodes, and extract extended metadata.
  name: How to read PDF417 in C# – complete barcode reader guide
  steps:
  - name: Verify the file exists before creating the reader.
    text: Verify the file exists before creating the reader.
  - name: Use `Image.FromFile` only when you need to pre‑process (rotate, crop). The
      `BarCodeReader` can open the file directly, which avoids extra memory allocation.
    text: Use `Image.FromFile` only when you need to pre‑process (rotate, crop). The
      `BarCodeReader` can open the file directly, which avoids extra memory allocation.
  - name: If the PNG contains transparency, the reader still works because the barcode
      is rendered on opaque pixels.
    text: If the PNG contains transparency, the reader still works because the barcode
      is rendered on opaque pixels.
  type: HowTo
tags:
- barcode
- C#
- PDF417
title: Comment lire le PDF417 en C# – guide complet du lecteur de codes-barres
url: /fr/net/compact-pdf417-encoding/how-to-read-pdf417-in-c-complete-barcode-reader-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Comment lire PDF417 en C# – guide complet du lecteur de codes-barres

Si vous avez besoin de **comment lire PDF417** dans une application .NET, ce guide vous fournit une solution prête à l’emploi. Vous verrez comment lire un PNG de code-barres, traiter plusieurs codes-barres dans la même image, et extraire les champs PDF417 étendus que de nombreux scanners masquent.

La lecture des codes-barres PDF417 est courante dans la logistique, la billetterie et la gestion de documents. À la fin de ce tutoriel, vous pourrez décoder une image Macro PDF417, afficher chaque résultat, et utiliser les informations supplémentaires (ID de fichier, nombre de segments, horodatages, etc.) dans votre propre logique métier.

## Prérequis

- .NET 6.0 ou version ultérieure (le code fonctionne également avec .NET Framework 4.7+)
- Visual Studio 2022 ou tout IDE C#
- **Aspose.BarCode for .NET** (version d’essai gratuite ou package NuGet sous licence)
- Une image PNG contenant un code-barres Macro PDF417 (le fichier d’exemple s’appelle `ExtPDF417Meta.png`)

> **Astuce pro** : Installez la bibliothèque avec la console NuGet :  
> `dotnet add package Aspose.BarCode`

## Comment lire PDF417 avec BarCodeReader en C#

Le cœur de la solution est la classe `BarCodeReader`. Elle accepte un chemin d’image et une énumération `DecodeType` qui indique au moteur quelle symbologie rechercher.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.ReadEngine;

class Pdf417Demo
{
    static void Main()
    {
        // Step 1: Create a BarCodeReader for a Macro PDF417 image
        using (BarCodeReader reader = new BarCodeReader(
            "YOUR_DIRECTORY/ExtPDF417Meta.png",
            DecodeType.MacroPdf417))
        {
            // Step 2: Read all barcodes from the image
            foreach (BarCodeResult result in reader.ReadBarCodes())
            {
                // Step 3: Output basic barcode information
                Console.WriteLine($"CodeType: {result.CodeTypeName}");
                Console.WriteLine($"CodeText: {result.CodeText}");

                // Step 4: Display Macro PDF417 extended metadata
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
}
```

### Pourquoi cela fonctionne

- **`DecodeType.MacroPdf417`** indique au lecteur de rechercher la variante Macro PDF417, qui stocke les champs supplémentaires que vous voyez à l’étape 4.
- Le bloc `using` libère automatiquement le lecteur, en fermant les descripteurs de fichiers.
- `ReadBarCodes()` renvoie **tous** les codes-barres correspondant au type demandé, ce qui satisfait le besoin de *lire plusieurs codes-barres* même si l’image ne contient qu’un seul.

L’exécution du programme affiche une sortie similaire à :

```
CodeType: MacroPdf417
CodeText: 1234567890
Pdf417MacroFileID: 1
Pdf417MacroSegmentID: 0
Pdf417MacroSegmentsCount: 3
Pdf417MacroFileName: invoice_2023.pdf
Pdf417MacroChecksum: 0x1A2B
Pdf417MacroFileSize: 254321
Pdf417MacroTimeStamp: 2023-03-15T10:45:00Z
Pdf417MacroAddressee: ACME Corp.
Pdf417MacroSender: Warehouse 7
MacroPdf417Terminator: True
----------------------------------------
```

## Utiliser le lecteur de codes-barres C# pour lire plusieurs codes-barres

Si une image contient plusieurs symboles Macro PDF417 (par exemple, une page numérisée avec un lot de billets), la même boucle `foreach` traite chacun d’eux. Aucun code supplémentaire n’est nécessaire ; le lecteur agrège les résultats en interne.

```csharp
// Example: processing a batch image
using (BarCodeReader batchReader = new BarCodeReader(
    "batch.png", DecodeType.MacroPdf417))
{
    int index = 0;
    foreach (BarCodeResult item in batchReader.ReadBarCodes())
    {
        Console.WriteLine($"--- Barcode #{++index} ---");
        Console.WriteLine($"Text: {item.CodeText}");
        // extended fields are accessed the same way
    }
}
```

### Pièges courants

- **Format d’image :** Le lecteur prend en charge PNG, JPEG, BMP et TIFF. Si vous essayez un format qu’il ne peut pas décoder, vous obtiendrez une collection vide. C’est pourquoi le tutoriel met en avant *lire le code-barres PNG*.
- **Résolution :** Les images à basse résolution (< 300 dpi) peuvent entraîner des segments manquants. Agrandissez ou demandez un scan de meilleure qualité lorsque c’est possible.
- **Drapeau Macro :** Oublier `DecodeType.MacroPdf417` limite le moteur au PDF417 simple et supprime les données étendues. Spécifiez toujours le type macro lorsque vous avez besoin des champs *lire le code-barres étendu*.

## Lecture de fichiers PNG de codes-barres – bonnes pratiques

Travailler avec des fichiers PNG est simple car le format préserve les données de pixels sans perte. Voici une checklist rapide :

1. Vérifiez que le fichier existe avant de créer le lecteur.  
   ```csharp
   if (!File.Exists(path))
       throw new FileNotFoundException($"File not found: {path}");
   ```
2. Utilisez `Image.FromFile` uniquement si vous devez pré‑traiter (rotation, recadrage). Le `BarCodeReader` peut ouvrir le fichier directement, ce qui évite une allocation mémoire supplémentaire.
3. Si le PNG contient de la transparence, le lecteur fonctionne toujours car le code-barres est rendu sur des pixels opaques.

## Accéder aux métadonnées PDF417 étendues

L’objet `Extended.Pdf417` expose chaque champ optionnel défini par la spécification PDF417. Vous pouvez mapper ces champs à un modèle métier, les stocker dans une base de données, ou les utiliser pour la validation.

```csharp
public class Pdf417Metadata
{
    public int FileID { get; set; }
    public int SegmentID { get; set; }
    public int SegmentsCount { get; set; }
    public string FileName { get; set; }
    public string Checksum { get; set; }
    public long FileSize { get; set; }
    public DateTime TimeStamp { get; set; }
    public string Addressee { get; set; }
    public string Sender { get; set; }
    public bool Terminator { get; set; }
}
```

Remplir le modèle :



## Que devriez‑vous apprendre ensuite ?

Les tutoriels suivants couvrent des sujets étroitement liés qui s’appuient sur les techniques démontrées dans ce guide. Chaque ressource comprend des exemples de code complets et fonctionnels avec des explications étape par étape pour vous aider à maîtriser des fonctionnalités API supplémentaires et explorer des approches d’implémentation alternatives dans vos propres projets.

- [Comment lire les codes-barres DataMatrix avec Aspose.BarCode pour .NET](/barcode/english/net/datamatrix-barcode-reading/)
- [Comment créer un code-barres – PDF417 compact avec Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [Lire le code-barres DataMatrix C# – Générer le mode DataMatrix (Auto)](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-auto/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}