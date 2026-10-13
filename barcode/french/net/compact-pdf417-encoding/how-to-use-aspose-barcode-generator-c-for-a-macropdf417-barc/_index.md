---
category: general
date: 2026-10-05
description: Aspose Barcode Generator C# vous permet d’ajouter des données macro et
  de générer des codes‑barres PDF417 sans effort. Apprenez étape par étape comment
  ajouter des métadonnées macro et créer une image PDF417.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- aspose barcode generator c#
- how to add macro
- how to generate pdf417
language: fr
lastmod: 2026-10-05
og_description: Aspose Barcode Generator C# vous montre comment ajouter des métadonnées
  macro et générer un code‑barres PDF417 en quelques lignes de code.
og_image_alt: Screenshot of a MacroPdf417 barcode created with Aspose Barcode Generator
  C#
og_title: Générateur de code-barres Aspose C# – ajouter une macro et générer un code-barres
  PDF417
schemas:
- author: Aspose
  dateModified: '2026-10-05'
  description: Aspose Barcode Generator C# lets you add macro data and generate PDF417
    barcodes effortlessly. Learn step‑by‑step how to add macro metadata and create
    a PDF417 image.
  headline: How to use Aspose Barcode Generator C# for a MacroPdf417 barcode
  type: TechArticle
tags:
- barcode
- csharp
- aspose
title: Comment utiliser Aspose Barcode Generator C# pour un code‑barres MacroPdf417
url: /fr/net/compact-pdf417-encoding/how-to-use-aspose-barcode-generator-c-for-a-macropdf417-barc/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Comment utiliser Aspose Barcode Generator C# pour un code-barres MacroPdf417

Si vous devez créer un code-barres MacroPdf417 en C#, **Aspose Barcode Generator C#** fournit une API concise qui gère à la fois l'image du code-barres et les métadonnées macro requises. Ce tutoriel vous montre exactement comment ajouter des informations macro et générer une image de code-barres PDF417 en quelques étapes seulement.

Vous apprendrez à configurer les paramètres visuels, à intégrer des champs macro tels que l'ID de fichier et l'horodatage, et à enregistrer le résultat au format PNG. Aucun outil externe n'est requis — uniquement la bibliothèque Aspose.BarCode et un environnement de développement .NET.

## Prérequis

Avant de commencer, assurez-vous d'avoir :

* .NET 6.0 ou version ultérieure installé  
* Visual Studio 2022 (ou tout IDE C#)  
* Une copie sous licence ou d'évaluation de **Aspose.BarCode for .NET**  

Le code fonctionne sous Windows, Linux et macOS car la bibliothèque est indépendante de la plateforme.

## Étape 1 : Installer le package NuGet Aspose.BarCode

Ouvrez votre projet dans Visual Studio, puis exécutez la commande suivante dans la **Package Manager Console** :

```powershell
Install-Package Aspose.BarCode
```

Cela ajoute l'assembly `Aspose.BarCode` ainsi que ses dépendances à votre projet.

## Étape 2 : Créer l'instance du générateur de code-barres

La première ligne crée un objet `BarcodeGenerator` pour la symbologie **MacroPdf417** et fournit le texte que vous souhaitez encoder.

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode.BarCodeImageFormat;

// Step 2: Initialise the generator with MacroPdf417 and the payload text
using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.MacroPdf417, "Åspóse.Barcóde©"))
{
    // subsequent configuration goes here
}
```

*Pourquoi c'est important* : la valeur `EncodeTypes.MacroPdf417` indique à la bibliothèque qu'elle doit s'attendre à des champs liés aux macros, que vous définirez à l'étape suivante.

## Étape 3 : Définir l'apparence visuelle

Vous pouvez contrôler la taille de chaque module (le plus petit carré noir ou blanc) et le nombre de colonnes dans la matrice PDF417. Modifier `XDimension` influence la résolution globale de l'image.

```csharp
    // Step 3: Visual settings
    generator.Parameters.Barcode.XDimension.Pixels = 2;          // width of a single module
    generator.Parameters.Barcode.Pdf417.Columns = 5;           // number of columns in the symbol
```

Augmenter `Columns` réduit la hauteur du code-barres, tandis qu'une `XDimension` plus grande rend l'image plus nette sur les écrans haute résolution (DPI).

## Étape 4 : Ajouter les métadonnées macro (comment ajouter la macro)

MacroPdf417 nécessite plusieurs champs supplémentaires qui décrivent le fichier source et sa segmentation. Les propriétés suivantes correspondent directement aux spécifications macro du PDF417 :

```csharp
    // Step 4: Macro fields – how to add macro data
    generator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;               // unique file identifier
    generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;                  // current segment number
    generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;              // total number of segments
    generator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";             // optional file name
    generator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234;                // CCITT‑16 placeholder
    generator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400_000;              // size in bytes
    generator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = 
        new DateTime(2019, 11, 1);                                                   // creation timestamp
    generator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";            // recipient identifier
    generator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";               // sender identifier
    generator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = 
        Pdf417MacroTerminator.Set;                                                   // marks the last segment
```

*Pourquoi ces champs* :  
* `MacroPdf417FileID` relie tous les segments, garantissant qu'un scanner puisse réassembler le document original.  
* `MacroPdf417SegmentID` et `MacroPdf417SegmentsCount` indiquent au décodage l'ordre et le nombre total de parties.  
* `MacroPdf417FileSize` et `MacroPdf417Checksum` offrent des contrôles d'intégrité, utiles pour les transferts de données volumineuses.

## Étape 5 : Enregistrer l'image du code-barres (comment générer le pdf417)

Enfin, écrivez le code-barres sur le disque. La méthode `Save` accepte un chemin de fichier et un format d'image. Le PNG préserve les bords nets du code-barres sans artefacts de compression.

```csharp
    // Step 5: Save the generated barcode – how to generate pdf417 image
    generator.Save("ExtPDF417Meta.png", BarCodeImageFormat.Png);
}
```

Lorsque le programme s'exécute, vous trouverez **ExtPDF417Meta.png** dans le dossier de sortie. L'ouverture de l'image montre un code-barres MacroPdf417 propre, prêt à être imprimé ou intégré dans un PDF.

### Résultat attendu

| Nom du fichier | Format | Dimensions (approx.) |
|----------------|--------|----------------------|
| ExtPDF417Meta.png | PNG | 300 × 150 px (varie avec `XDimension`) |

Scanner l'image avec un lecteur compatible PDF417 (par ex., ZXing, Aspose.BarCode for .NET) renvoie le texte original **“Åspóse.Barcóde©”** ainsi que tous les champs macro.

## Problèmes courants et comment les éviter

| Problème | Pourquoi cela se produit | Solution |
|----------|--------------------------|----------|
| **Incorrect `EncodeTypes`** | Using `EncodeTypes.Pdf417` instead of `EncodeTypes.MacroPdf417` disables macro fields. | Always instantiate the generator with `EncodeTypes.MacroPdf417`. |
| **Missing macro fields** | Some scanners ignore the barcode if required macro fields are omitted. | Populate at least `FileID`, `SegmentID`, `SegmentsCount`, and `Terminator`. |
| **Too small `XDimension`** | A value under 1 pixel can produce an unreadable barcode on low‑resolution displays. | Keep `XDimension` ≥ 2 pixels for most screen and print scenarios. |
| **File path errors** | Providing a relative path that doesn’t exist throws an exception. | Use `Path.Combine(Environment.CurrentDirectory, "ExtPDF417Meta.png")` or an absolute path. |

## Code source complet

Ci-dessous le exemple complet et exécutable que vous pouvez copier dans un nouveau projet console.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode.BarCodeImageFormat;

namespace MacroPdf417Demo
{
    class Program
    {
        static void Main()
        {
            // Initialise the generator with MacroPdf417 and the payload text
            using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.MacroPdf417, "Åspóse.Barcóde©"))
            {
                // Visual appearance
                generator.Parameters.Barcode.XDimension.Pixels = 2;          // module width
                generator.Parameters.Barcode.Pdf417.Columns = 5;           // number of columns

                // Macro fields – how to add macro
                generator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
                generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;
                generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;
                generator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";
                generator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234;
                generator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400_000;
                generator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = new DateTime(2019, 11, 1);
                generator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
                generator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
                generator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;

                // Save the barcode – how to generate pdf417
                generator.Save("ExtPDF417Meta.png", BarCodeImageFormat.Png);
            }

            Console.WriteLine("MacroPdf417 barcode generated successfully.");
        }
    }
}
```

Exécutez le programme (`dotnet run`). Après l'exécution, la console affiche un message de succès et le fichier PNG apparaît dans le dossier de sortie du projet.

## Prochaines étapes

* **Encoder plus de données** – Augmentez `Columns` ou ajustez `Rows` (via `Pdf417.Rows`) pour contenir plus de caractères.  
* **Intégrer dans un PDF** – Utilisez Aspose.PDF pour placer le PNG généré dans un document.  
* **Vérification par scan** – Utilisez `Aspose.BarCode.Reader` pour décoder le code-barres et confirmer les champs macro programmatiquement.  

Explorer ces sujets approfondit votre compréhension de **comment générer des codes-barres PDF417** avec des informations macro riches et vous prépare à des cas d'utilisation réels tels que le traitement par lots de documents ou l'échange sécurisé de données.

---

*Bonne programmation ! Si vous avez trouvé ce guide utile, pensez à le partager avec vos coéquipiers ou à mettre une étoile au dépôt Aspose.BarCode sur GitHub.*

## Que devriez‑vous apprendre ensuite ?

Les tutoriels suivants couvrent des sujets étroitement liés qui s'appuient sur les techniques démontrées dans ce guide. Chaque ressource comprend des exemples de code complets et fonctionnels avec des explications étape par étape pour vous aider à maîtriser des fonctionnalités API supplémentaires et explorer des approches d'implémentation alternatives dans vos propres projets.

- [Comment créer un code-barres macro PDF417 en C# avec Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/how-to-create-macro-pdf417-barcode-in-c-using-aspose-barcode/)
- [Comment générer un code-barres PDF417 en C# avec Barcode Generator](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-with-barcode-generator/)
- [Exemple Aspose barcode : générer Macro PDF417 en C#](/barcode/english/net/compact-pdf417-encoding/aspose-barcode-example-generate-macro-pdf417-in-c/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}