---
category: general
date: 2026-09-10
description: Comment générer des codes‑barres PDF417 en C# avec Aspose.BarCode. Suivez
  un guide étape par étape pour créer un Macro PDF417, ajuster les paramètres et exporter
  en PNG.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to generate pdf417
- macro pdf417 barcode
- aspose.barcode for .net
- c# barcode generator
- pdf417 barcode parameters
- barcode image export
language: fr
lastmod: 2026-09-10
og_description: Comment générer des codes-barres PDF417 en C# avec Aspose.BarCode.
  Découvrez le flux complet, de la configuration à l’enregistrement d’une image PNG
  Macro PDF417.
og_image_alt: Screenshot of a generated Macro PDF417 barcode saved as a PNG file
og_title: Comment générer des codes-barres PDF417 en C# – guide complet d’Aspose.BarCode
schemas:
- author: Aspose
  dateModified: '2026-09-10'
  description: How to generate PDF417 barcodes in C# using Aspose.BarCode. Follow
    a step‑by‑step guide to create Macro PDF417, adjust parameters, and export as
    PNG.
  headline: How to generate PDF417 barcodes in C# with Aspose.BarCode
  type: TechArticle
- description: How to generate PDF417 barcodes in C# using Aspose.BarCode. Follow
    a step‑by‑step guide to create Macro PDF417, adjust parameters, and export as
    PNG.
  name: How to generate PDF417 barcodes in C# with Aspose.BarCode
  steps:
  - name: '**Create a Macro PDF417 generator** – `EncodeTypes.MacroPdf417` tells Aspose.BarCode
      to use the macro version of PDF417, which supports splitting a large payload
      across multiple symbols.'
    text: '**Create a Macro PDF417 generator** – `EncodeTypes.MacroPdf417` tells Aspose.BarCode
      to use the macro version of PDF417, which supports splitting a large payload
      across multiple symbols.'
  - name: '**Adjust basic appearance** – `XDimension` controls the module (dot) width;
      `Columns` defines how many columns each symbol will contain, influencing both
      size and readability.'
    text: '**Adjust basic appearance** – `XDimension` controls the module (dot) width;
      `Columns` defines how many columns each symbol will contain, influencing both
      size and readability.'
  - name: '**Set macro‑specific fields** – These properties (`MacroPdf417FileID`,
      `MacroPdf417SegmentID`, etc.) are required by the PDF417 macro specification
      to re‑assemble the original data on the scanner side.'
    text: '**Set macro‑specific fields** – These properties (`MacroPdf417FileID`,
      `MacroPdf417SegmentID`, etc.) are required by the PDF417 macro specification
      to re‑assemble the original data on the scanner side.'
  - name: '**Export the image** – `BarCodeImageFormat.Png` provides a lossless image
      that works well for web, print, and mobile scenarios.'
    text: '**Export the image** – `BarCodeImageFormat.Png` provides a lossless image
      that works well for web, print, and mobile scenarios.'
  - name: '**Visual verification** – Open `MacroPdf417.png` in any image viewer. You
      should see a stacked set of vertical bars with a small text caption (the encoded
      data).'
    text: '**Visual verification** – Open `MacroPdf417.png` in any image viewer. You
      should see a stacked set of vertical bars with a small text caption (the encoded
      data).'
  - name: '**Scanner test** – Use a mobile barcode scanner app that supports PDF417.
      Scan the image; the app should return the original “Sample text” plus macro
      metadata (file ID, segment ID, etc.).'
    text: '**Scanner test** – Use a mobile barcode scanner app that supports PDF417.
      Scan the image; the app should return the original “Sample text” plus macro
      metadata (file ID, segment ID, etc.).'
  - name: '**Error handling** – If the scanner reports “checksum error,” double‑check
      `MacroPdf417Checksum` and ensure the `MacroPdf417Terminator` is set correctly
      on the last segment.'
    text: '**Error handling** – If the scanner reports “checksum error,” double‑check
      `MacroPdf417Checksum` and ensure the `MacroPdf417Terminator` is set correctly
      on the last segment.'
  - name: '**Performance** – Generating many segments in a loop can be CPU‑intensive.
      Re‑use a single `BarcodeGenerator` instance and only update the macro fields
      between saves to improve throughput.'
    text: '**Performance** – Generating many segments in a loop can be CPU‑intensive.
      Re‑use a single `BarcodeGenerator` instance and only update the macro fields
      between saves to improve throughput.'
  type: HowTo
tags:
- barcode
- pdf417
- csharp
- aspose
title: Comment générer des codes-barres PDF417 en C# avec Aspose.BarCode
url: /fr/net/compact-pdf417-encoding/how-to-generate-pdf417-barcodes-in-c-with-aspose-barcode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Comment générer des codes-barres PDF417 en C# avec Aspose.BarCode

Si vous avez besoin de **comment générer pdf417** dans un projet .NET, ce tutoriel montre le flux de travail complet. Vous verrez comment créer un code-barres Macro PDF417, affiner ses paramètres et exporter le résultat sous forme d'image PNG — le tout avec Aspose.BarCode pour .NET.

La génération de codes-barres PDF417 est courante dans la logistique, la billetterie et les flux de documents sécurisés. À la fin de ce guide, vous disposerez d'un générateur de code-barres C# prêt à l'emploi que vous pourrez intégrer à n'importe quelle application.

## Ce dont vous aurez besoin

- **Visual Studio 2022** (ou tout IDE C#)  
- **.NET 6.0** ou version ultérieure  
- **Aspose.BarCode for .NET** package NuGet (`Install-Package Aspose.BarCode`)  
- Familiarité de base avec la syntaxe C#  

> **Astuce :** Utilisez la dernière version d'Aspose.BarCode pour obtenir les nouvelles fonctionnalités Macro PDF417 et les corrections de bugs.

---

## Comment générer des codes-barres PDF417 en C#  

Voici un exemple complet et exécutable qui crée un code-barres **Macro PDF417**, configure ses champs spécifiques aux macros et enregistre l'image.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // STEP 1 – create a Macro PDF417 generator with the desired text
        using (BarcodeGenerator generator =
               new BarcodeGenerator(EncodeTypes.MacroPdf417, "Sample text"))
        {
            // STEP 2 – adjust basic barcode appearance
            generator.Parameters.Barcode.XDimension.Pixels = 2;   // module width
            generator.Parameters.Barcode.Pdf417.Columns = 5;     // number of columns

            // STEP 3 – configure Macro PDF417 specific fields
            generator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
            generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;
            generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;
            generator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";
            generator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234; // CCITT‑16
            generator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400_000;
            generator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp =
                new DateTime(2023, 11, 1);
            generator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
            generator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
            generator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;

            // STEP 4 – save the generated barcode as a PNG image
            generator.Save("MacroPdf417.png", BarCodeImageFormat.Png);
        }

        Console.WriteLine("Macro PDF417 barcode generated: MacroPdf417.png");
    }
}
```

### Pourquoi chaque étape est importante

1. **Créer un générateur Macro PDF417** – `EncodeTypes.MacroPdf417` indique à Aspose.BarCode d'utiliser la version macro de PDF417, qui prend en charge la division d'une charge utile importante en plusieurs symboles.  
2. **Ajuster l'apparence de base** – `XDimension` contrôle la largeur du module (point) ; `Columns` définit le nombre de colonnes que chaque symbole contiendra, influençant à la fois la taille et la lisibilité.  
3. **Définir les champs spécifiques aux macros** – Ces propriétés (`MacroPdf417FileID`, `MacroPdf417SegmentID`, etc.) sont requises par la spécification macro PDF417 pour reconstituer les données originales du côté du lecteur.  
4. **Exporter l'image** – `BarCodeImageFormat.Png` fournit une image sans perte qui fonctionne bien pour le web, l'impression et les scénarios mobiles.

## Configurer Aspose.BarCode pour .NET (générateur de code-barres C#)

Avant de pouvoir exécuter le code ci‑above, vous devez ajouter la bibliothèque Aspose.BarCode à votre projet :

```bash
dotnet add package Aspose.BarCode
```

*Le package NuGet inclut toutes les dépendances, aucune DLL supplémentaire n'est nécessaire.*  
Si vous ciblez le .NET Framework, la même commande `Install-Package Aspose.BarCode` fonctionne depuis la console du gestionnaire de packages.

### Pièges courants

- **Licence manquante** – Par défaut, Aspose fonctionne en mode évaluation, ce qui ajoute un filigrane au code‑barres. Enregistrez un fichier de licence (`License license = new License(); license.SetLicense("Aspose.BarCode.lic");`) pour le supprimer.  
- **`EncodeTypes` incorrect** – Utiliser `EncodeTypes.Pdf417` au lieu de `EncodeTypes.MacroPdf417` ignorera tous les champs macro, empêchant la reconstruction multi‑segment.

## Configurer les paramètres du code‑barres Macro PDF417

Les champs macro vous permettent de diviser un grand document en plusieurs symboles PDF417. Voici une référence rapide :

| Propriété | Objectif | Plage typique |
|----------|----------|---------------|
| `MacroPdf417FileID` | Identifiant unique pour le fichier complet | 0‑2³¹‑1 |
| `MacroPdf417SegmentID` | Indice du segment actuel (commence à 0) | 0‑254 |
| `MacroPdf417SegmentsCount` | Nombre total de segments dans le fichier | 1‑255 |
| `MacroPdf417FileName` | Nom lisible par l'homme (optionnel) | 0‑255 characters |
| `MacroPdf417Checksum` | Somme de contrôle CCITT‑16 pour la détection d'erreurs | 0‑65535 |
| `MacroPdf417FileSize` | Taille du fichier original en octets | 0‑2³¹‑1 |
| `MacroPdf417TimeStamp` | Horodatage de création (optionnel) | `DateTime` value |
| `MacroPdf417Addressee` / `MacroPdf417Sender` | Métadonnées optionnelles pour le routage | Any string |
| `MacroPdf417Terminator` | Indique le segment final (`Set` ou `Unset`) | `Pdf417MacroTerminator` enum |

Ajustez ces valeurs pour correspondre aux données que vous encodez. Par exemple, si vous divisez un fichier de 2 Mo en 20 segments, définissez `MacroPdf417FileSize` à `2_000_000` et `MacroPdf417SegmentsCount` à `20`.

## Exporter le code‑barres en image PNG (exportation d'image de code‑barres)

Enregistrer le code‑barres au format PNG est le format d'exportation le plus courant car il préserve les bords nets et prend en charge la transparence. Aspose.BarCode prend également en charge JPEG, BMP, GIF et TIFF — choisissez celui qui convient à votre processus en aval.

```csharp
generator.Save("MacroPdf417.png", BarCodeImageFormat.Png);
```

**Conseils pour une sortie de haute qualité**

- Augmentez `XDimension.Pixels` pour des modules plus grands lors de l'impression sur des supports haute résolution.  
- Utilisez `BarCodeImageFormat.Tiff` avec compression CCITT Group 4 pour des PDF compatibles fax.  
- Définissez `generator.Parameters.ImageOptions.Resolution` si vous avez besoin d'une résolution DPI spécifique (par ex., 300 dpi pour l'impression).

## Tester et dépanner votre code‑barres PDF417

1. **Vérification visuelle** – Ouvrez `MacroPdf417.png` dans n'importe quel visualiseur d'images. Vous devriez voir un ensemble empilé de barres verticales avec une petite légende texte (les données encodées).  
2. **Test du scanner** – Utilisez une application de scanner de code‑barres mobile qui prend en charge PDF417. Scannez l'image ; l'application doit renvoyer le texte original « Sample text » ainsi que les métadonnées macro (ID du fichier, ID du segment, etc.).  
3. **Gestion des erreurs** – Si le scanner signale « checksum error », revérifiez `MacroPdf417Checksum` et assurez‑vous que `MacroPdf417Terminator` est correctement défini sur le dernier segment.  
4. **Performance** – Générer de nombreux segments dans une boucle peut être intensif pour le CPU. Réutilisez une seule instance de `BarcodeGenerator` et ne mettez à jour les champs macro qu'entre les sauvegardes pour améliorer le débit.

## Conclusion

Vous savez maintenant **comment générer des codes‑barres PDF417** en C# avec Aspose.BarCode, depuis l'installation de la bibliothèque jusqu'à la configuration des champs Macro PDF417 et l'exportation d'une image PNG nette. La solution complète démontre :

- Configurer un **générateur de code‑barres C#** avec le type Macro PDF417  
- Personnaliser les **paramètres du code‑barres PDF417** pour des données multi‑segment  
- Effectuer l'**exportation d'image de code‑barres** pour une utilisation en aval  

À partir de là, vous pouvez explorer des sujets avancés tels que l'intégration du code‑barres dans des documents PDF, la génération de compagnons QR‑code, ou l'automatisation du traitement par lots de gros fichiers.

**Étapes suivantes**

- Essayez différentes valeurs de `BarCodeImageFormat` (par ex., `Tiff` pour des impressions haute résolution).  
- Combinez Macro PDF417 avec d'autres symbologies dans le même document en utilisant `generator.Parameters.Barcode.Symbology`.  
- Consultez la [documentation Aspose.BarCode](https://docs.aspose.com/barcode/net/) pour des options de personnalisation plus approfondies comme le niveau de correction d'erreurs et les modes d'encodage.

Bon codage!

## Que devriez‑vous apprendre ensuite ?

Les tutoriels suivants couvrent des sujets étroitement liés qui s'appuient sur les techniques démontrées dans ce guide. Chaque ressource comprend des exemples de code fonctionnels complets avec des explications étape par étape pour vous aider à maîtriser des fonctionnalités API supplémentaires et explorer des approches d'implémentation alternatives dans vos propres projets.

- [Générer un code‑barres avec texte – Guide complet Macro PDF417](/barcode/english/net/compact-pdf417-encoding/generate-barcode-with-text-full-pdf417-macro-guide/)
- [ajuster la taille du code‑barres – Guide C# pour générer des codes‑barres PDF417](/barcode/english/net/compact-pdf417-encoding/adjust-barcode-size-c-guide-to-generate-pdf417-barcodes/)
- [Comment générer un code‑barres PDF417 – Guide complet de programmation](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-complete-programming-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}