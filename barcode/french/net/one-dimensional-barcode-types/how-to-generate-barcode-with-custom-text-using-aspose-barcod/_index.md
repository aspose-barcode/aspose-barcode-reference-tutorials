---
category: general
date: 2026-10-28
description: Comment générer un code‑barres avec du texte personnalisé en utilisant
  Aspose.BarCode – guide étape par étape pour les développeurs .NET afin de créer
  des images de code‑barres Aspose.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to generate barcode
- generate barcode custom text
- create barcode aspose
language: fr
lastmod: 2026-10-28
og_description: Comment générer un code-barres avec du texte personnalisé en .NET
  à l’aide d’Aspose.BarCode. Suivez ce guide complet pour créer et enregistrer un
  code‑barres Macro PDF417.
og_image_alt: how to generate barcode example PNG image showing a Macro PDF417 barcode
og_title: Comment générer un code‑barres avec du texte personnalisé – Tutoriel Aspose.BarCode
schemas:
- author: Aspose
  dateModified: '2026-10-28'
  description: How to generate barcode with custom text using Aspose.BarCode – step‑by‑step
    guide for .NET developers to create barcode Aspose images.
  headline: How to generate barcode with custom text using Aspose.BarCode for .NET
  type: TechArticle
- description: How to generate barcode with custom text using Aspose.BarCode – step‑by‑step
    guide for .NET developers to create barcode Aspose images.
  name: How to generate barcode with custom text using Aspose.BarCode for .NET
  steps:
  - name: Why each line matters
    text: '* **EncodeTypes.MacroPdf417** – selects the Macro PDF417 symbology, which
      supports segmented data and metadata. * **XDimension.Pixels** – controls the
      size of each module; a value of 2 pixels yields a clear, scannable image. *
      **Pdf417.Columns** – reduces the overall width, making the barcode more c'
  - name: Using a different barcode type
    text: If you need to **generate barcode custom text** for a QR code instead of
      Macro PDF417, replace `EncodeTypes.MacroPdf417` with `EncodeTypes.QR`. The rest
      of the parameter structure stays the same, but QR codes do not support Macro
      metadata fields.
  - name: Handling Unicode characters
    text: The example already includes Unicode characters (`Å`, `ó`, `©`). Aspose.BarCode
      handles UTF‑8 input out of the box, but you should ensure the source file is
      saved with UTF‑8 encoding to avoid compile‑time warnings.
  - name: Saving to other image formats
    text: 'Aspose.BarCode supports BMP, JPEG, TIFF, and SVG in addition to PNG. Change
      the `BarCodeImageFormat` enum value accordingly:'
  - name: Large data sets
    text: Macro PDF417 can split data across multiple segments. When the text exceeds
      the capacity of a single segment, increment `MacroPdf417SegmentID` and keep
      `MacroPdf417SegmentsCount` consistent across all generated parts. This approach
      is essential for **create barcode aspose** scenarios where the paylo
  - name: Error handling
    text: 'Wrap the generation logic in a try‑catch block to surface runtime issues
      such as invalid file paths or unsupported characters:'
  type: HowTo
tags:
- barcode
- Aspose.BarCode
- .NET
title: Comment générer un code‑barres avec du texte personnalisé en utilisant Aspose.BarCode
  pour .NET
url: /fr/net/one-dimensional-barcode-types/how-to-generate-barcode-with-custom-text-using-aspose-barcod/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Comment générer un code-barres avec du texte personnalisé en utilisant Aspose.BarCode pour .NET

Générer un code-barres avec du texte personnalisé est une exigence fréquente lorsque vous devez intégrer des identifiants, des horodatages ou d’autres métadonnées directement dans un code visuel. Ce tutoriel vous montre comment générer un code-barres Macro PDF417 qui porte du texte personnalisé et un ensemble complet de métadonnées, en utilisant la bibliothèque **Aspose.BarCode** pour .NET.

Vous apprendrez comment configurer le générateur, appliquer du texte personnalisé, définir les champs spécifiques à Macro PDF417, et enregistrer le résultat sous forme d’image PNG. Aucun outil externe n’est requis — uniquement le package NuGet Aspose.BarCode et un environnement de développement .NET.

## Prérequis

* SDK .NET 6.0 ou version ultérieure installé  
* Visual Studio 2022 (ou tout IDE supportant .NET)  
* Package NuGet **Aspose.BarCode for .NET** (`Install-Package Aspose.BarCode`)  

Ces prérequis garantissent que le code se compile et s’exécute sans configuration supplémentaire.

## Étape 1 : Installer le package Aspose.BarCode

Ouvrez un terminal dans le dossier de votre projet et exécutez :

```bash
dotnet add package Aspose.BarCode
```

La commande ajoute la dernière version stable d’Aspose.BarCode à votre projet, vous donnant accès à la classe `BarcodeGenerator` et à tous les paramètres associés.

## Étape 2 : Créer une nouvelle application console

Créez une application console minimale qui hébergera la logique de génération du code-barres :

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

namespace BarcodeDemo
{
    internal class Program
    {
        private static void Main()
        {
            // The full barcode generation flow is encapsulated in a separate method
            GenerateMacroPdf417Barcode();
        }

        /// <summary>
        /// Generates a Macro PDF417 barcode with custom text and metadata, then saves it as PNG.
        /// </summary>
        private static void GenerateMacroPdf417Barcode()
        {
            // Step 1: Instantiate the generator with the desired encode type and data
            using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.MacroPdf417, "Åspóse.Barcóde©"))
            {
                // Step 2: Define the visual appearance of the barcode
                generator.Parameters.Barcode.XDimension.Pixels = 2;          // Size of a single module
                generator.Parameters.Barcode.Pdf417.Columns = 5;            // Number of columns in the symbol

                // Step 3: Populate Macro PDF417 specific metadata fields
                generator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
                generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;
                generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;
                generator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";
                generator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234; // CCITT‑16 example value
                generator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400_000;
                generator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = new DateTime(2019, 11, 1);
                generator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
                generator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
                generator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;

                // Step 4: Save the barcode image to disk
                string outputPath = @"ExtPDF417Meta.png";
                generator.Save(outputPath, BarCodeImageFormat.Png);
                Console.WriteLine($"Barcode saved to {outputPath}");
            }
        }
    }
}
```

### Pourquoi chaque ligne est importante

* **EncodeTypes.MacroPdf417** – sélectionne la symbologie Macro PDF417, qui prend en charge les données segmentées et les métadonnées.  
* **XDimension.Pixels** – contrôle la taille de chaque module ; une valeur de 2 pixels produit une image claire et lisible.  
* **Pdf417.Columns** – réduit la largeur globale, rendant le code-barres plus compact pour les étiquettes imprimées.  
* **MacroPdf417* properties** – intègrent des informations au niveau du fichier (ID, nombre de segments, horodatages, etc.) directement dans le code-barres. Cette capacité est propre à Macro PDF417 et est souvent utilisée dans la logistique ou les systèmes de gestion de documents.  
* **Save(..., BarCodeImageFormat.Png)** – écrit un fichier PNG sans perte, préservant les bords nets du code-barres pour un scan fiable.

## Étape 3 : Exécuter le programme et vérifier la sortie

Compilez et exécutez l’application console :

```bash
dotnet run
```

Le programme crée `ExtPDF417Meta.png` dans le répertoire de travail du projet. L’ouverture du fichier affiche un code-barres Macro PDF417 qui encode le texte **« Åspóse.Barcóde© »** ainsi que les métadonnées que vous avez fournies.

**Sortie attendue** – une image PNG similaire à celle ci‑dessous :

![exemple de sortie de génération de code-barres image PNG montrant un code-barres Macro PDF417](ExtPDF417Meta.png)

*Le texte alternatif de l’image (« how to generate barcode example output PNG image ») renforce le mot‑clé principal pour l’accessibilité et le SEO.*

## Variantes courantes et cas limites

### Utiliser un type de code-barres différent

Si vous devez **générer un code-barres avec texte personnalisé** pour un QR code au lieu de Macro PDF417, remplacez `EncodeTypes.MacroPdf417` par `EncodeTypes.QR`. Le reste de la structure des paramètres reste identique, mais les QR codes ne prennent pas en charge les champs de métadonnées Macro.

### Gestion des caractères Unicode

L’exemple inclut déjà des caractères Unicode (`Å`, `ó`, `©`). Aspose.BarCode gère l’entrée UTF‑8 nativement, mais vous devez vous assurer que le fichier source est enregistré avec l’encodage UTF‑8 afin d’éviter les avertissements lors de la compilation.

### Enregistrement dans d’autres formats d’image

Aspose.BarCode prend en charge BMP, JPEG, TIFF et SVG en plus du PNG. Modifiez la valeur de l’énumération `BarCodeImageFormat` en conséquence :

```csharp
generator.Save("barcode.svg", BarCodeImageFormat.Svg);
```

### Jeux de données volumineux

Macro PDF417 peut diviser les données en plusieurs segments. Lorsque le texte dépasse la capacité d’un seul segment, incrémentez `MacroPdf417SegmentID` et maintenez `MacroPdf417SegmentsCount` cohérent sur toutes les parties générées. Cette approche est essentielle pour les scénarios **create barcode aspose** où la charge utile est plus grande qu’un seul code-barres ne peut contenir.

### Gestion des erreurs

Enveloppez la logique de génération dans un bloc try‑catch afin de détecter les problèmes d’exécution tels que des chemins de fichier invalides ou des caractères non pris en charge :

```csharp
try
{
    GenerateMacroPdf417Barcode();
}
catch (Exception ex)
{
    Console.Error.WriteLine($"Barcode generation failed: {ex.Message}");
}
```

## Astuces professionnelles pour une génération fiable de code-barres

* **Validez le code-barres** après sa création en utilisant `BarCodeReader`. Cette étape supplémentaire confirme que les données encodées correspondent à vos attentes.

  ```csharp
  using (BarCodeReader reader = new BarCodeReader("ExtPDF417Meta.png", DecodeType.MacroPdf417))
  {
      if (reader.Read())
          Console.WriteLine($"Decoded text: {reader.GetCodeText()}");
  }
  ```

* **Conservez la X‑dimension entre 2 – 4 pixels** pour la plupart des scanners. Des valeurs plus petites peuvent produire des images illisibles sur des appareils à basse résolution.

* **Évitez les noms de fichier très longs** dans `MacroPdf417FileName`. La spécification limite le champ à 32 caractères.

* **Utilisez des horodatages cohérents** (UTC) lors de la génération de plusieurs segments afin de simplifier le traitement en aval.

## Conclusion

Vous savez maintenant **comment générer un code-barres** avec du texte personnalisé en utilisant Aspose.BarCode pour .NET, comment configurer les métadonnées Macro PDF417, et comment enregistrer le résultat sous forme d’image PNG. L’exemple complet et exécutable montre chaque étape requise — de l’installation du package NuGet à la gestion des caractères Unicode en passant par l’enregistrement de la sortie.

À partir d’ici, vous pouvez :

* **Générer du texte personnalisé pour les code-barres** pour d’autres symbologies (QR, DataMatrix, etc.)  
* **Créer des flux de travail barcode Aspose** qui traitent par lots des milliers d’images  
* Intégrer le code de génération de code-barres dans les services ASP.NET Core, les services Windows ou les Azure Functions  

Expérimentez avec différents paramètres, explorez des champs de métadonnées supplémentaires, et intégrez le code-barres dans vos pipelines d’automatisation de documents. Bon codage !

## Que devriez‑vous apprendre ensuite ?

Les tutoriels suivants couvrent des sujets étroitement liés qui s’appuient sur les techniques démontrées dans ce guide. Chaque ressource comprend des exemples de code complets et fonctionnels avec des explications étape par étape pour vous aider à maîtriser des fonctionnalités API supplémentaires et à explorer des approches d’implémentation alternatives dans vos propres projets.

- [Comment créer un code-barres PDF417 avec Aspose – Guide complet étape par étape](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-with-aspose-complete-step-by-st/)
- [Générer un code-barres à partir du texte avec Aspose.BarCode – Guide C#](/barcode/english/net/one-dimensional-barcode-types/generate-barcode-from-text-using-aspose-barcode-c-guide/)
- [Comment utiliser Aspose.BarCode pour créer du texte de code DataMatrix en .NET](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-extended-code-text-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}