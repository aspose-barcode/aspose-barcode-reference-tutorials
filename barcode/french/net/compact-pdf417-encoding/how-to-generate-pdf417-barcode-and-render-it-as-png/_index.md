---
category: general
date: 2026-11-17
description: Apprenez à générer un code‑barres PDF417, à définir la taille du code‑barres
  et à rendre le code‑barres en image avec C#. Guide complet étape par étape.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate PDF417 barcode
- how to generate PDF417
- render barcode to image
- how to set barcode size
language: fr
lastmod: 2026-11-17
og_description: Générez un code‑barres PDF417 en C# et rendez‑le sous forme d’image.
  Suivez ce guide pour définir la taille du code‑barres et enregistrer un fichier
  PNG.
og_image_alt: Screenshot of a generated PDF417 barcode saved as a PNG image
og_title: Générer un code‑barres PDF417 et le rendre au format PNG – Guide C#
schemas:
- author: Aspose
  dateModified: '2026-11-17'
  description: Learn how to generate PDF417 barcode, set barcode size, and render
    barcode to image using C#. Complete step‑by‑step guide.
  headline: How to generate PDF417 barcode and render it as PNG
  type: TechArticle
- description: Learn how to generate PDF417 barcode, set barcode size, and render
    barcode to image using C#. Complete step‑by‑step guide.
  name: How to generate PDF417 barcode and render it as PNG
  steps:
  - name: Open the PNG file in any image viewer.
    text: Open the PNG file in any image viewer.
  - name: Use a smartphone barcode scanning app that supports PDF417 (e.g., Google
      Lens, QR & Barcode Scanner).
    text: Use a smartphone barcode scanning app that supports PDF417 (e.g., Google
      Lens, QR & Barcode Scanner).
  - name: Scan the image; the app should return the text *Layout demo*.
    text: Scan the image; the app should return the text *Layout demo*.
  type: HowTo
tags:
- barcode
- PDF417
- C#
- image generation
title: Comment générer un code‑barres PDF417 et le rendre en PNG
url: /fr/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-and-render-it-as-png/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Comment générer un code-barres PDF417 et le rendre en PNG

Si vous devez **générer un code-barres PDF417** dans une application .NET, ce tutoriel vous montre exactement comment faire. Vous verrez comment définir la taille du code-barres, configurer la mise en page, et **rendre le code-barres en image** avec seulement quelques lignes de code C#.

Générer un code-barres PDF417 est courant lorsque vous souhaitez encoder de grandes quantités de données pour la lecture sur des appareils mobiles ou des imprimantes. À la fin de ce guide, vous disposerez d’un fichier PNG prêt à l’emploi que vous pourrez intégrer dans des rapports, des e‑mails ou des pages Web.

## Prérequis

- .NET 6.0 SDK ou version ultérieure installé  
- Un IDE C# tel que Visual Studio 2022 (tout éditeur fonctionne)  
- Le package NuGet **Aspose.BarCode for .NET** (ou toute bibliothèque compatible qui fournit `BarcodeGenerator`)  

Vous pouvez ajouter le package avec:

```bash
dotnet add package Aspose.BarCode
```

## Étape 1 : Créer un projet console C#

Tout d’abord, configurez une application console minimale qui hébergera le code de génération du code‑barres.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace Pdf417Demo
{
    class Program
    {
        static void Main(string[] args)
        {
            // The barcode generation logic will be placed here.
        }
    }
}
```

> **Astuce :** Gardez la méthode `Main` courte et déléguez le travail lourd aux méthodes auxiliaires. Cela améliore la lisibilité et facilite les tests unitaires.

## Étape 2 : Générer un code‑barres PDF417 avec une taille personnalisée

Nous allons maintenant **générer un code‑barres PDF417** et spécifier la taille du module (dimension X). La dimension X contrôle la largeur de chaque petit carré du code‑barres, définissant ainsi la taille globale du code‑barres.

```csharp
static void GeneratePdf417(string text, string outputPath)
{
    // Initialize a PDF417 barcode generator with the desired text
    BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, text);

    // Set the size of a single barcode module (X‑dimension) in pixels
    generator.Parameters.Barcode.XDimension.Pixels = 2; // 2 px per module

    // Optional: adjust the number of columns and rows for layout control
    generator.Parameters.Barcode.Pdf417.Columns = 4;   // 4 columns
    generator.Parameters.Barcode.Pdf417.Rows    = 9;   // 9 rows

    // Render the barcode and save it as a PNG image
    generator.Save(outputPath, BarCodeImageFormat.Png);
}
```

### Pourquoi définir la dimension X ?

L’étape **comment définir la taille du code‑barres** est importante car une dimension X trop petite peut rendre le code‑barres illisible sur des lecteurs à basse résolution, tandis qu’une valeur trop grande gaspille de l’espace. Une valeur de `2` pixels fonctionne bien pour la plupart des affichages d’écran et des scénarios d’impression.

## Étape 3 : Appeler la méthode de génération depuis `Main`

Raccordez le tout en invoquant `GeneratePdf417` avec le texte souhaité et l’emplacement de sortie.

```csharp
static void Main(string[] args)
{
    string barcodeText = "Layout demo";
    string outputFile = @"C:\Barcodes\LayoutPdf417.png";

    GeneratePdf417(barcodeText, outputFile);

    Console.WriteLine($"PDF417 barcode saved to {outputFile}");
}
```

L’exécution du programme crée `LayoutPdf417.png` contenant le code‑barres :

![Code‑barres PDF417 généré](/images/layout-pdf417.png "Code‑barres PDF417 généré par le code du tutoriel"){: .align-center alt="Code‑barres PDF417 généré et enregistré en PNG"}

> **Résultat attendu :** Un fichier PNG d’une taille d’environ 200 × 100 px (selon les paramètres de colonnes/ligne) affichant un motif PDF417 clair prêt à être scanné.

## Étape 4 : Vérifier que le code‑barres fonctionne

Pour vous assurer que le code‑barres est valide :

1. Ouvrez le fichier PNG dans n’importe quel visualiseur d’image.  
2. Utilisez une application de lecture de code‑barres sur smartphone qui prend en charge le PDF417 (par ex., Google Lens, QR & Barcode Scanner).  
3. Scannez l’image ; l’application doit renvoyer le texte *Layout demo*.

Si le scan échoue, revérifiez la dimension X et les valeurs de colonnes/ligne — des modules plus grands améliorent la lisibilité sur les caméras à basse résolution.

## Variations courantes et cas limites

| Scénario | Ajustement |
|----------|------------|
| **Plus de données** (p. ex., une URL) | Augmentez `Columns` ou `Rows` pour accueillir des mots‑code supplémentaires. |
| **Impression haute résolution** | Augmentez `XDimension.Pixels` à 3‑4 px pour des barres plus nettes. |
| **Arrière‑plan transparent** | Utilisez `generator.Save(outputPath, BarCodeImageFormat.Png, new ImageOptions { BackgroundColor = Color.Transparent })`. |
| **Format d’image différent** | Remplacez `BarCodeImageFormat.Png` par `Jpeg` ou `Bmp` selon les besoins. |

Ces variations répondent à la question **comment générer PDF417** pour différents besoins tout en conservant la logique de base identique.

## Conclusion

Vous savez maintenant comment **générer un code‑barres PDF417**, **définir la taille du code‑barres**, et **rendre le code‑barres en image** en utilisant C#. L’exemple complet et exécutable crée un fichier PNG qui peut être intégré partout où vous avez besoin d’un code‑barres lisible par machine.

Ensuite, explorez des sujets connexes tels que **intégrer le PNG dans un PDF** (recherchez *render barcode to PDF*), ou **générer d’autres codes‑barres 2‑D** comme les QR codes. Ajustez les paramètres de mise en page pour correspondre à votre conception UI, et expérimentez les options de couleur pour le branding.

Bonne programmation, et laissez vos codes‑barres faire le travail lourd !

## Que devriez‑vous apprendre ensuite ?

Les tutoriels suivants couvrent des sujets étroitement liés qui s’appuient sur les techniques démontrées dans ce guide. Chaque ressource comprend des exemples de code complets et fonctionnels avec des explications étape par étape pour vous aider à maîtriser des fonctionnalités d’API supplémentaires et explorer des approches d’implémentation alternatives dans vos propres projets.

- [Comment générer un code‑barres PDF417 en C# – guide complet étape par étape](/barcode/english/net/compact-pdf417-encoding/generate-pdf417-barcode-in-c-complete-step-by-step-guide/)
- [Comment générer un micro PDF417 en C# – guide étape par étape](/barcode/english/net/compact-pdf417-encoding/how-to-generate-micro-pdf417-barcode-in-c-step-by-step-guide/)
- [Comment définir le niveau d’erreur dans le code‑barres PDF417 – guide complet](/barcode/english/net/compact-pdf417-encoding/how-to-set-error-level-in-pdf417-barcode-complete-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}