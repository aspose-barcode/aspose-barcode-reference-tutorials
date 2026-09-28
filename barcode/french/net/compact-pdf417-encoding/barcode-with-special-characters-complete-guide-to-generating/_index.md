---
category: general
date: 2026-07-27
description: Le tutoriel sur les codes‑barres avec caractères spéciaux montre comment
  générer des codes‑barres PDF417 avec Aspose. Apprenez la création et la gestion
  des données Unicode étape par étape.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- barcode with special characters
- how to generate pdf417
- create barcode with aspose
- Aspose PDF417 macro
- Unicode barcode generation
language: fr
lastmod: 2026-07-27
og_description: Le tutoriel sur les codes-barres avec caractères spéciaux explique
  comment générer des codes-barres PDF417 en utilisant Aspose, en couvrant la gestion
  Unicode et les métadonnées macro.
og_image_alt: Screenshot of a PDF417 barcode containing special characters generated
  with Aspose
og_title: Code-barres avec caractères spéciaux – Générer PDF417 avec Aspose
schemas:
- author: Aspose
  dateModified: '2026-07-27'
  description: Barcode with special characters tutorial shows how to generate PDF417
    barcodes with Aspose. Learn step‑by‑step creation and handling of Unicode data.
  headline: Barcode with Special Characters – Complete Guide to Generating PDF417
    Using Aspose
  type: TechArticle
- description: Barcode with special characters tutorial shows how to generate PDF417
    barcodes with Aspose. Learn step‑by‑step creation and handling of Unicode data.
  name: Barcode with Special Characters – Complete Guide to Generating PDF417 Using
    Aspose
  steps:
  - name: Expected Output
    text: If you open the PNG, you’ll see a rectangular barcode with a series of black
      and white bars. Scanning it with a PDF417‑compatible scanner (or a mobile app
      like “Barcode Scanner”) will return the exact text `"Åspóse.Barcóde©"` along
      with the macro metadata we set. In other words, the barcode faithful
  - name: What if my text contains emojis or non‑BMP characters?
    text: Aspose.BarCode supports full UTF‑16, so emojis work as long as the target
      scanner can decode them. Just pass the string directly; the library handles
      the encoding internally.
  - name: Do I need to set a specific character set?
    text: No. Unlike older barcode SDKs that required `CodePage` settings, Aspose
      automatically detects Unicode. However, if you target a legacy device that only
      understands ASCII, you’ll need to strip or replace special characters before
      generation.
  - name: How does this differ from a regular PDF417 barcode?
    text: The `MacroPdf417` variant adds extra fields (file ID, segment count, etc.)
      that help split large payloads across multiple barcodes. If you don’t need those,
      you can switch `EncodeTypes.Pdf417` and drop the macro‑specific properties.
  - name: Can I generate the barcode as a vector (SVG) instead of PNG?
    text: 'Absolutely. Change the `BarCodeImageFormat` to `Svg`:'
  type: HowTo
tags:
- barcode
- Aspose
- PDF417
- .NET
title: Code-barres avec caractères spéciaux – Guide complet pour générer PDF417 avec
  Aspose
url: /fr/net/compact-pdf417-encoding/barcode-with-special-characters-complete-guide-to-generating/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Code-barres avec caractères spéciaux – Guide complet pour générer du PDF417 avec Aspose

Vous vous êtes déjà demandé comment créer un **code-barres avec caractères spéciaux** incluant des accents, des symboles, voire des marques de copyright ? Vous n'êtes pas seul. De nombreux développeurs se heurtent à un mur lorsque leurs données contiennent des caractères comme « Å », « é » ou « © », et les exemples standards montrent rarement comment les gérer. Dans ce tutoriel, nous allons parcourir un exemple concret qui non seulement résout ce problème mais démontre également **comment générer des PDF417** code-barres à l'aide de la bibliothèque Aspose.BarCode.

Nous commencerons par configurer une simple application console .NET, puis nous plongerons dans le code qui produit un code-barres PDF417 contenant la chaîne `"Åspóse.Barcóde©"`. Au fil du texte, vous verrez pourquoi chaque paramètre est important, comment configurer les métadonnées macro‑PDF417, et à quoi faire attention lors de la gestion de l'Unicode. À la fin, vous serez prêt à **créer des codes-barres avec Aspose** dans n'importe lequel de vos projets, que ce soit pour l'inventaire, la billetterie ou le suivi sécurisé de documents.

## Prérequis

- .NET 6.0 SDK ou version ultérieure (le code fonctionne également avec .NET Framework 4.7+)
- Visual Studio 2022 (ou tout IDE de votre choix)
- Une licence valide Aspose.BarCode pour .NET (vous pouvez commencer avec un essai gratuit)
- Familiarité de base avec la syntaxe C#

Si l'un de ces éléments vous est inconnu, ne paniquez pas — il suffit d'installer le SDK .NET et de récupérer le package NuGet `Aspose.BarCode` et vous serez prêt à partir.

## Étape 1 : Installer Aspose.BarCode et configurer le projet

Pour générer un **code-barres avec caractères spéciaux**, la première chose dont vous avez besoin est la bibliothèque Aspose.BarCode. Ouvrez un terminal dans le dossier de votre projet et exécutez :

```bash
dotnet add package Aspose.BarCode
```

Cela récupère la dernière version (en date de juillet 2026, version 23.12) qui prend en charge la gestion complète d'Unicode dès le départ. Après la restauration du package, créez un nouveau fichier C# nommé `Program.cs` et ajoutez les directives `using` habituelles :

```csharp
using System;
using Aspose.BarCode.Generation;
```

Pourquoi le `using Aspose.BarCode.Generation` ? Il nous donne accès à la classe `BarcodeGenerator`, le cœur de **comment générer des PDF417** code-barres avec Aspose.

## Étape 2 : Initialiser le générateur de code-barres avec du texte Unicode

Voici la partie qui crée réellement un **code-barres avec caractères spéciaux**. Notez que la chaîne que nous passons au constructeur contient un « Å », un « ó » et un « © ». Aspose détecte automatiquement la plage Unicode, vous n'avez donc pas besoin d'étapes d'encodage supplémentaires — il suffit de fournir la chaîne .NET brute :

```csharp
// Step 2: Create a barcode generator for Macro PDF417 with Unicode text
using (BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
           EncodeTypes.MacroPdf417, "Åspóse.Barcóde©"))
{
    // The rest of the configuration goes here
}
```

Le `EncodeTypes.MacroPdf417` indique à Aspose que nous voulons un code-barres PDF417 capable de transporter des informations macro (utile pour diviser de grandes charges utiles). Le générateur possède maintenant un **code-barres avec caractères spéciaux** prêt à être ajusté davantage.

## Étape 3 : Affiner l'apparence et les métadonnées macro

Un code-barres simple fonctionne, mais la plupart des scénarios réels nécessitent un contrôle sur la taille, le nombre de colonnes et les champs macro. Ci-dessous, nous ajustons la dimension X, le nombre de colonnes, puis définissons un ensemble de propriétés macro‑PDF417. Chaque ligne est commentée afin que vous puissiez voir *pourquoi* elle est importante.

```csharp
    // Adjust basic barcode appearance
    barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;   // pixel size of a module
    barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 5;    // number of columns (affects width)

    // Define macro PDF417 metadata (file ID, segment info, etc.)
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234; // CCITT‑16
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400000;
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = new DateTime(2019, 11, 1);
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;
```

Astuce rapide : si vous constatez que le code-barres généré devient trop large, diminuez la valeur `Columns` ou augmentez `XDimension`. Les deux affectent la taille finale de l'image, ce qui est crucial lors de l'intégration du code-barres dans des PDF ou des étiquettes imprimées.

## Étape 4 : Enregistrer le code-barres en tant qu'image

Enfin, nous enregistrons le code-barres dans un fichier PNG. La méthode `Save` rend automatiquement le **code-barres avec caractères spéciaux** dans un format raster que vous pouvez afficher sur un site web, intégrer dans un rapport ou envoyer à une imprimante.

```csharp
    // Save the generated barcode as a PNG image
    barcodeGenerator.Save("YOUR_DIRECTORY/ExtPDF417Meta.png", BarCodeImageFormat.Png);
}
```

Remplacez `YOUR_DIRECTORY` par un chemin absolu ou relatif qui existe sur votre machine. Après l'exécution du programme, vous devriez voir `ExtPDF417Meta.png` contenant un code-barres PDF417 net qui encode la chaîne Unicode.

### Résultat attendu

Si vous ouvrez le PNG, vous verrez un code-barres rectangulaire composé d'une série de barres noires et blanches. Le scanner compatible PDF417 (ou une application mobile comme “Barcode Scanner”) renverra le texte exact `"Åspóse.Barcóde©"` ainsi que les métadonnées macro que nous avons définies. En d'autres termes, le code-barres préserve fidèlement les caractères spéciaux—aucune perte de données.

## Questions fréquentes & cas particuliers

### Et si mon texte contient des emojis ou des caractères non‑BMP ?

Aspose.BarCode prend en charge l'UTF‑16 complet, donc les emojis fonctionnent tant que le scanner cible peut les décoder. Il suffit de passer la chaîne directement ; la bibliothèque gère l'encodage en interne.

### Dois‑je définir un jeu de caractères spécifique ?

Non. Contrairement aux anciens SDK de code-barres qui nécessitaient des paramètres `CodePage`, Aspose détecte automatiquement l'Unicode. Cependant, si vous ciblez un appareil hérité qui ne comprend que l'ASCII, vous devrez supprimer ou remplacer les caractères spéciaux avant la génération.

### En quoi cela diffère‑t‑il d’un code‑barres PDF417 ordinaire ?

La variante `MacroPdf417` ajoute des champs supplémentaires (ID de fichier, nombre de segments, etc.) qui aident à diviser de grandes charges utiles sur plusieurs code‑barres. Si vous n’en avez pas besoin, vous pouvez passer à `EncodeTypes.Pdf417` et supprimer les propriétés spécifiques aux macros.

### Puis‑je générer le code‑barres en vecteur (SVG) au lieu de PNG ?

Absolument. Changez le `BarCodeImageFormat` en `Svg` :

```csharp
barcodeGenerator.Save("ExtPDF417Meta.svg", BarCodeImageFormat.Svg);
```

La sortie vectorielle s'adapte sans perte de qualité—pratique pour l'impression haute résolution.

## Exemple complet fonctionnel

Voici le programme complet, prêt à être exécuté. Copiez‑collez‑le dans `Program.cs`, ajustez le chemin de sortie, et appuyez sur **F5**.

```csharp
using System;
using Aspose.BarCode.Generation;

namespace BarcodeSpecialCharsDemo
{
    class Program
    {
        static void Main()
        {
            // Step 1: Create a barcode generator for Macro PDF417 with Unicode text
            using (BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
                       EncodeTypes.MacroPdf417, "Åspóse.Barcóde©"))
            {
                // Step 2: Adjust basic barcode appearance
                barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;   // pixel size of a module
                barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 5;    // number of columns

                // Step 3: Define macro PDF417 metadata (file ID, segment info, etc.)
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234; // CCITT‑16
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400000;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = new DateTime(2019, 11, 1);
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;

                // Step 4: Save the generated barcode as a PNG image
                barcodeGenerator.Save("ExtPDF417Meta.png", BarCodeImageFormat.Png);
            }

            Console.WriteLine("Barcode with special characters generated successfully!");
        }
    }
}
```

L'exécution de ce programme affiche une ligne de confirmation et crée `ExtPDF417Meta.png` dans le dossier de l'exécutable. Ouvrez le fichier, scannez‑le, et vérifiez que les caractères spéciaux survivent au trajet aller‑retour.

## Astuces professionnelles pour la production

- **Mettez en cache le générateur** si vous créez de nombreux code‑barres dans une boucle ; réutiliser la même instance `BarcodeGenerator` réduit la consommation de mémoire.
- **Définissez `Resolution`** (`barcodeGenerator.Parameters.ImageResolution`) lorsque vous avez besoin d'une résolution DPI plus élevée pour des actifs prêts à imprimer.
- **Validez l'entrée** : supprimez les caractères de contrôle qui pourraient casser les champs macro. Une expression régulière simple comme `^[\u0020-\u007E\u00A0-\u00FF]+$` fonctionne pour la plupart des cas d'utilisation Latin‑1.
- **Sécurité des threads** : chaque thread doit posséder son propre `BarcodeGenerator`. La classe n’est pas thread‑safe.

## Conclusion

Vous disposez maintenant d’une méthode solide, de bout en bout, pour créer un **code‑barres avec caractères spéciaux** avec Aspose, et vous avez également vu **comment générer des PDF417** code‑barres qui transportent des métadonnées macro. L'exemple a couvert tout, de l'installation du package NuGet à l'enregistrement du PNG final, et a mis en évidence les pièges courants tels que la gestion de l'Unicode et la taille de l'image.

Prêt pour l'étape suivante ? Essayez de changer le format d'image en SVG, expérimentez avec des charges utiles plus importantes

## Que devriez‑vous apprendre ensuite ?

Les tutoriels suivants couvrent des sujets étroitement liés qui s'appuient sur les techniques démontrées dans ce guide. Chaque ressource comprend des exemples de code complets et fonctionnels avec des explications étape par étape pour vous aider à maîtriser des fonctionnalités supplémentaires de l'API et explorer des approches d'implémentation alternatives dans vos propres projets.

- [Comment créer un code‑barres – PDF417 compact avec Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [Reconnaître le code‑barres PDF417 avec des caractères chinois en Java](/barcode/english/java/multilingual-support/recognizing-pdf417-chinese-characters/)
- [Reconnaître le code‑barres PDF417 avec des caractères turcs en Java](/barcode/english/java/multilingual-support/recognizing-pdf417-turkish-characters/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}