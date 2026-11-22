---
category: general
date: 2026-11-20
description: Apprenez à créer un code‑barres macro PDF417 en C# avec Aspose.BarCode.
  Ce guide couvre les métadonnées, les paramètres et la sauvegarde de l’image.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create macro PDF417 barcode
- macro PDF417 metadata
- Aspose.BarCode C#
- PDF417 macro parameters
- barcode generator example
language: fr
lastmod: 2026-11-20
og_description: Créer un code‑barres macro PDF417 en C# avec Aspose.BarCode. Suivez
  ce tutoriel complet pour définir les métadonnées, configurer les paramètres et exporter
  un PNG.
og_image_alt: Screenshot of a generated macro PDF417 barcode image
og_title: Créer un code‑barres macro PDF417 en C# – guide étape par étape
schemas:
- author: Aspose
  dateModified: '2026-11-20'
  description: Learn how to create macro PDF417 barcode in C# using Aspose.BarCode.
    This guide covers metadata, parameters, and saving the image.
  headline: How to create macro PDF417 barcode with Aspose.BarCode in C#
  type: TechArticle
- description: Learn how to create macro PDF417 barcode in C# using Aspose.BarCode.
    This guide covers metadata, parameters, and saving the image.
  name: How to create macro PDF417 barcode with Aspose.BarCode in C#
  steps:
  - name: Expected output
    text: 'Running the program prints a confirmation line similar to:'
  - name: What if I need more than 20 segments?
    text: The `MacroPdf417SegmentsCount` property can be set up to `255`. Ensure the
      receiving system can handle the larger segment count, and consider splitting
      the data into a manageable number of symbols.
  - name: How does the checksum affect scanning?
    text: The CCITT‑16 checksum (`MacroPdf417Checksum`) provides an additional error‑checking
      layer. If a scanner detects a mismatch, it will reject the barcode. You can
      omit the checksum if your workflow does not require it.
  - name: Can I generate a PDF417 macro barcode without Aspose?
    text: Yes, other libraries (e.g., ZXing.Net, Dynamsoft) support PDF417, but macro‑specific
      fields are often missing. Aspose.BarCode offers the most complete implementation
      for macro metadata.
  - name: What image formats are supported for saving?
    text: The `Save` method accepts any format defined in `BarCodeImageFormat`, such
      as `Png`, `Jpeg`, `Gif`, `Bmp`, and `Tiff`. Choose a format that matches your
      downstream processing pipeline.
  type: HowTo
tags:
- barcode
- PDF417
- C#
- Aspose
title: Comment créer un code‑barres macro PDF417 avec Aspose.BarCode en C#
url: /fr/net/compact-pdf417-encoding/how-to-create-macro-pdf417-barcode-with-aspose-barcode-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Comment créer un code-barres macro PDF417 avec Aspose.BarCode en C#

Si vous devez **créer un code-barres macro PDF417** dans une application .NET, ce tutoriel montre les étapes exactes. Vous verrez comment configurer les métadonnées spécifiques aux macros, ajuster les paramètres visuels et enregistrer le résultat sous forme de fichier PNG.

Générer un code-barres macro PDF417 est utile lorsque vous souhaitez diviser un grand ensemble de données en plusieurs symboles tout en conservant un identifiant valable pour l’ensemble du fichier. Dans l’exemple ci‑dessous, nous utilisons la bibliothèque Aspose.BarCode, qui fournit une API fluide pour toutes les fonctionnalités PDF417.

À la fin de ce guide, vous disposerez d’un programme console prêt à l’exécution qui génère une image de code‑barres contenant toutes les informations macro.

## Prérequis

* .NET 6.0 SDK ou version ultérieure installé.
* Visual Studio 2022 (ou tout IDE prenant en charge C#).
* Le package NuGet **Aspose.BarCode for .NET** (`Aspose.BarCode`).

Vous pouvez ajouter le package avec la commande suivante :

```bash
dotnet add package Aspose.BarCode
```

## Étape 1 : Initialiser le générateur de code‑barres pour macro PDF417

La première étape consiste à instancier un `BarcodeGenerator` avec la valeur d’énumération `EncodeTypes.MacroPdf417`. Cela indique à la bibliothèque de traiter le code‑barres comme un symbole macro PDF417.

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;

using (BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
           EncodeTypes.MacroPdf417, "Åspóse.Barcóde©"))
{
    // The generator is now ready for further configuration.
```

*Pourquoi c’est important* : sélectionner `MacroPdf417` active toutes les propriétés liées aux macros sur l’objet paramètre `Pdf417`.

## Étape 2 : Définir l’apparence visuelle de base

Un code‑barres lisible commence par une taille de module et un nombre de colonnes appropriés. La propriété `XDimension.Pixels` contrôle la largeur d’un seul module, tandis que `Pdf417.Columns` définit le nombre de colonnes de données que chaque ligne contient.

```csharp
    // Set module width to 2 pixels.
    barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;

    // Use 5 columns per row – a compact layout for this example.
    barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 5;
```

L’ajustement de ces valeurs influence à la fois la fiabilité du scanner et la taille de l’image.

## Étape 3 : Définir les détails d’identification du fichier macro

Macro PDF417 nécessite un identifiant de fichier, un identifiant de segment et le nombre total de segments. Ces trois champs permettent à un scanner de réassembler l’ensemble de données d’origine.

```csharp
    // Unique file identifier for the whole macro file.
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;

    // Identifier of the current segment (starting at 0 or 1 based on your protocol).
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;

    // Total number of segments that compose the complete file.
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;

    // Optional human‑readable file name.
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";
```

Ces **paramètres macro PDF417** sont le cœur de la fonctionnalité macro. Sans eux, un scanner ne peut pas lier les symboles entre eux.

## Étape 4 : Ajouter des métadonnées macro optionnelles

Au-delà des identifiants obligatoires, le format macro prend en charge des champs supplémentaires tels que le checksum, la taille du fichier, le horodatage, le destinataire, l’expéditeur et un drapeau de terminaison. Fournir ces données améliore la détection d’erreurs et fournit un contexte aux systèmes en aval.

```csharp
    // CCITT‑16 checksum example.
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234;

    // Approximate file size in bytes (helps the receiver allocate buffers).
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400_000;

    // Timestamp of when the macro file was generated.
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = new DateTime(2019, 11, 1);

    // Optional address fields.
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";

    // Terminator indicates that this is the final segment.
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;
```

*Astuce* : Si votre flux de travail n’a pas besoin d’un champ particulier, vous pouvez le laisser à sa valeur par défaut. La bibliothèque omettra l’élément de données correspondant du code‑barres.

## Étape 5 : Enregistrer l’image du code‑barres

Après avoir configuré tous les paramètres, appelez `Save` pour exporter le code‑barres. L’exemple enregistre le fichier PNG dans un répertoire spécifié par l’utilisateur.

```csharp
    // Replace with a valid folder on your machine.
    string outputPath = "YOUR_DIRECTORY/ExtPDF417Meta.png";

    // Save as PNG – other formats (Jpeg, Gif, etc.) are also supported.
    barcodeGenerator.Save(outputPath, BarCodeImageFormat.Png);
}
```

Lorsque le programme se termine, `ExtPDF417Meta.png` contient un code‑barres macro PDF417 qui encode le texte `"Åspóse.Barcóde©"` ainsi que toutes les métadonnées macro.

## Code source complet

Ci‑dessous se trouve le programme complet et autonome. Copiez‑le dans un nouveau projet console et exécutez‑le après avoir installé le package NuGet Aspose.BarCode.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace MacroPdf417Demo
{
    class Program
    {
        static void Main()
        {
            // Step 1: Create a macro PDF417 barcode generator.
            using (BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
                       EncodeTypes.MacroPdf417, "Åspóse.Barcóde©"))
            {
                // Step 2: Visual appearance.
                barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
                barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 5;

                // Step 3: Core macro identifiers.
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";

                // Step 4: Optional macro metadata.
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400_000;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = new DateTime(2019, 11, 1);
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;

                // Step 5: Export the image.
                string outputPath = "YOUR_DIRECTORY/ExtPDF417Meta.png";
                barcodeGenerator.Save(outputPath, BarCodeImageFormat.Png);
                Console.WriteLine($"Macro PDF417 barcode saved to {outputPath}");
            }
        }
    }
}
```

### Sortie attendue

L’exécution du programme affiche une ligne de confirmation similaire à :

```
Macro PDF417 barcode saved to YOUR_DIRECTORY/ExtPDF417Meta.png
```

L’ouverture du fichier PNG montre un code‑barres dense et à fort contraste. Le scanner le lisant avec un lecteur compatible PDF417 renvoie le texte original ainsi que tous les champs macro.

## Questions fréquentes et cas particuliers

### Que faire si j’ai besoin de plus de 20 segments ?

La propriété `MacroPdf417SegmentsCount` peut être définie jusqu’à `255`. Assurez‑vous que le système récepteur peut gérer ce nombre de segments plus élevé, et envisagez de diviser les données en un nombre gérable de symboles.

### Comment le checksum affecte‑t‑il le scan ?

Le checksum CCITT‑16 (`MacroPdf417Checksum`) fournit une couche supplémentaire de vérification d’erreurs. Si un scanner détecte une incohérence, il rejettera le code‑barres. Vous pouvez omettre le checksum si votre flux de travail ne le nécessite pas.

### Puis‑je générer un code‑barres PDF417 macro sans Aspose ?

Oui, d’autres bibliothèques (par ex., ZXing.Net, Dynamsoft) prennent en charge PDF417, mais les champs spécifiques aux macros sont souvent absents. Aspose.BarCode propose l’implémentation la plus complète pour les métadonnées macro.

### Quels formats d’image sont pris en charge pour l’enregistrement ?

La méthode `Save` accepte tout format défini dans `BarCodeImageFormat`, tel que `Png`, `Jpeg`, `Gif`, `Bmp` et `Tiff`. Choisissez un format qui correspond à votre pipeline de traitement en aval.

## Conclusion

Vous savez maintenant comment **créer un code‑barres macro PDF417** en C# avec Aspose.BarCode. Le tutoriel a couvert l’initialisation du générateur, les paramètres visuels, les identifiants de fichier macro, les métadonnées optionnelles et l’exportation d’image. Avec cette base, vous pouvez intégrer des PDF macro dans des systèmes d’inventaire, le suivi de documents ou tout scénario nécessitant une transmission de données segmentée.

Les prochaines étapes incluent l’expérimentation avec différentes valeurs de `XDimension` pour une résolution supérieure, l’ajout d’ajustements du niveau de correction d’erreurs, ou l’intégration du code‑barres dans une API web qui renvoie directement le flux PNG. Pour des sujets connexes, consultez les tutoriels sur **exemple de générateur de code‑barres**, **paramètres macro PDF417**, et la gestion des **métadonnées macro PDF417**.

Bon codage !

## Que devriez‑vous apprendre ensuite ?

Les tutoriels suivants couvrent des sujets étroitement liés qui s’appuient sur les techniques démontrées dans ce guide. Chaque ressource comprend des exemples de code complets et fonctionnels avec des explications étape par étape pour vous aider à maîtriser des fonctionnalités API supplémentaires et explorer des approches d’implémentation alternatives dans vos propres projets.

- [Comment créer une image de code‑barres PDF417 en C# avec les options Macro PDF417](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-image-in-c-with-macro-pdf417-op/)
- [Lire un code‑barres depuis une image C# – guide complet avec Macro PDF417](/barcode/english/net/compact-pdf417-encoding/read-barcode-from-image-c-complete-guide-with-macro-pdf417/)
- [Comment créer un code‑barres PDF417 avec Aspose – guide complet étape par étape](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-with-aspose-complete-step-by-st/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}