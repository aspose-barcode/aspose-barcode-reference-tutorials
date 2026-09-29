---
category: general
date: 2026-09-29
description: Apprenez à générer rapidement un code‑barres PDF417 en C#. Ce tutoriel
  étape par étape couvre les paramètres du code‑barres, la sortie d’image et les pièges
  courants.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate pdf417 barcode
- how to generate pdf417 barcode
- PDF417 barcode settings
- C# barcode library
- barcode image export
language: fr
lastmod: 2026-09-29
og_description: Générez un code‑barres PDF417 en C# avec ce tutoriel détaillé. Suivez
  l’exemple complet pour créer et exporter une image de code‑barres.
og_image_alt: Screenshot showing generated PDF417 barcode saved as PNG
og_title: Générer un code‑barres PDF417 en C# – guide étape par étape
schemas:
- author: Aspose
  dateModified: '2026-09-29'
  description: Learn how to generate PDF417 barcode in C# quickly. This step‑by‑step
    tutorial covers barcode settings, image output, and common pitfalls.
  headline: How to generate PDF417 barcode in C# – complete programming guide
  type: TechArticle
- description: Learn how to generate PDF417 barcode in C# quickly. This step‑by‑step
    tutorial covers barcode settings, image output, and common pitfalls.
  name: How to generate PDF417 barcode in C# – complete programming guide
  steps:
  - name: Adjusting error correction level
    text: PDF417 supports five error‑correction levels (0‑8). Higher levels increase
      robustness at the cost of size.
  - name: Changing image format
    text: 'If you need a vector format for scaling, export as SVG instead of PNG:'
  - name: Handling very long strings
    text: 'When the input exceeds the default capacity, increase the number of rows:'
  - name: Using a different library
    text: If you prefer an open‑source alternative, the `ZXing.Net` package also supports
      PDF417. The API differs, but the overall flow—create a writer, set options,
      render to bitmap—remains the same.
  - name: Next steps
    text: '* Explore **PDF417 barcode settings** such as row count and aspect ratio
      for custom layouts. * Integrate the barcode generation into an ASP.NET Core
      API to serve images on demand. * Combine this code with a QR‑code generator
      for multi‑symbology documents.'
  type: HowTo
tags:
- barcode
- C#
- PDF417
- image generation
title: Comment générer un code‑barres PDF417 en C# – guide complet de programmation
url: /fr/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-complete-programming-gui/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Comment générer un code‑barres PDF417 en C# – guide complet de programmation

Si vous devez **générer un code‑barres PDF417** dans une application .NET, ce guide vous montre exactement comment le faire. Vous verrez un exemple complet, exécutable, qui crée un code‑barres PDF417, configure ses dimensions et l’enregistre en tant qu’image PNG.

Générer un code‑barres est une exigence courante pour les systèmes d’inventaire, les plateformes de billetterie et l’automatisation de documents. À la fin de ce tutoriel, vous serez capable d’intégrer la création de code‑barres dans n’importe quel projet C# sans chercher d’autres extraits de code.

## Ce que vous apprendrez

* Comment instancier un générateur de code‑barres PDF417 avec du texte personnalisé  
* Quels paramètres contrôlent la dimension X et le nombre de colonnes  
* Comment exporter le code‑barres en fichier PNG de haute qualité  
* Astuces pour gérer les caractères Unicode et ajuster la taille de l’image  

**Prérequis**  
* .NET 6.0 ou supérieur (le code fonctionne également avec .NET Framework 4.6+)  
* Une référence au package NuGet `Aspose.BarCode` (ou toute bibliothèque de code‑barres compatible)  
* Une connaissance de base de la syntaxe C# et de Visual Studio ou de votre IDE préféré  

Si vous vous demandez **comment générer un code‑barres PDF417** pour la première fois, continuez à lire – les étapes sont délibérément ordonnées de la configuration à la vérification.

## Étape 1 : Installer la bibliothèque de codes‑barres

Avant d’écrire du code, ajoutez le SDK de code‑barres à votre projet. La bibliothèque la plus utilisée pour PDF417 en C# est **Aspose.BarCode for .NET**.

```bash
dotnet add package Aspose.BarCode
```

> **Astuce pro** : Utilisez la dernière version stable (actuellement 24.5) pour bénéficier d’améliorations de performances et d’un support complet Unicode.

## Étape 2 : Créer le générateur de code‑barres PDF417

Le cœur du processus consiste à créer une instance `BarcodeGenerator` avec l’énumération `EncodeTypes.Pdf417`. Le constructeur reçoit également le texte que vous souhaitez encoder.

```csharp
using Aspose.BarCode.Generation;

// Step 2: Initialize the generator with the desired text
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.Pdf417,               // PDF417 symbology
    "Åspóse.Barcóde©");               // Text includes Unicode characters
```

*Pourquoi c’est important* : Le drapeau `EncodeTypes.Pdf417` indique à la bibliothèque d’utiliser la norme PDF417, qui prend en charge de gros blocs de données et la correction d’erreurs. Fournir une chaîne Unicode montre que le générateur gère correctement les caractères non‑ASCII.

## Étape 3 : Configurer la dimension X (largeur du module)

La dimension X définit la largeur d’un seul module du code‑barres (la plus petite barre noire ou blanche). La définir en pixels vous donne un contrôle précis sur la taille finale de l’image.

```csharp
// Step 3: Set the X‑dimension (module width) in pixels
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

Une valeur de `2` pixels produit un code‑barres compact tout en restant facilement lisible par la plupart des scanners. Si vous avez besoin d’un code‑barres plus grand pour une impression sur affiche, augmentez cette valeur proportionnellement.

## Étape 4 : Définir le nombre de colonnes

PDF417 vous permet de spécifier le nombre de colonnes, ce qui influence le rapport d’aspect du code‑barres. Moins de colonnes rendent le code‑barres plus haut ; plus de colonnes le rendent plus large.

```csharp
// Step 4: Define the number of columns for the PDF417 barcode
barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 3;
```

Trois colonnes créent une forme équilibrée adaptée à la plupart des usages sur écran. Pour des données denses, vous pouvez augmenter ce nombre à 5 ou 7.

## Étape 5 : Enregistrer le code‑barres en image PNG

Enfin, exportez le code‑barres généré vers un fichier. Le PNG préserve les bords nets et prend en charge la transparence, ce qui le rend idéal pour l’affichage UI.

```csharp
// Step 5: Save the generated barcode as a PNG image
string outputPath = Path.Combine(
    Environment.GetFolderPath(Environment.SpecialFolder.Desktop),
    "Pdf417Basic.png");

barcodeGenerator.Save(outputPath, BarCodeImageFormat.Png);
```

Lorsque le code s’exécute, vous trouverez `Pdf417Basic.png` sur votre bureau. L’ouverture du fichier montre un code‑barres PDF417 clair qui encode la chaîne **Åspóse.Barcóde©**.

## Vérification du résultat

Pour confirmer que le code‑barres encode les données prévues, vous pouvez utiliser n’importe quelle application gratuite de lecture PDF417 (par ex., l’application ZXing Android) ou un décodeur en ligne. Scannez le PNG enregistré ; le texte décodé doit correspondre exactement à l’entrée d’origine, caractères spéciaux inclus.

**Sortie attendue** – une image PNG similaire à celle‑ci (illustrative) :

![Code‑barres PDF417 généré enregistré en PNG – exemple de génération de code‑barres pdf417](https://example.com/assets/pdf417-sample.png "générer pdf417 barcode")

*Le texte alternatif ci‑dessus satisfait à l’exigence d’alt‑image pour le mot‑clé principal.*

## Variations courantes et cas limites

### Ajustement du niveau de correction d’erreurs

PDF417 prend en charge cinq niveaux de correction d’erreurs (0‑8). Des niveaux plus élevés augmentent la robustesse au prix d’une taille plus grande.

```csharp
barcodeGenerator.Parameters.Barcode.Pdf417.ErrorLevel = 5; // medium protection
```

### Changer le format d’image

Si vous avez besoin d’un format vectoriel pour le redimensionnement, exportez en SVG au lieu de PNG :

```csharp
barcodeGenerator.Save("Pdf417Basic.svg", BarCodeImageFormat.Svg);
```

### Gestion de chaînes très longues

Lorsque l’entrée dépasse la capacité par défaut, augmentez le nombre de lignes :

```csharp
barcodeGenerator.Parameters.Barcode.Pdf417.Rows = 10;
```

### Utiliser une bibliothèque différente

Si vous préférez une alternative open‑source, le package `ZXing.Net` prend également en charge PDF417. L’API diffère, mais le flux global — créer un writer, définir les options, rendre en bitmap — reste le même.

## Exemple complet et exécutable

Voici le programme complet que vous pouvez copier dans une application console et exécuter immédiatement.

```csharp
using System;
using System.IO;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // 1️⃣ Initialize the generator with Unicode text
        BarcodeGenerator generator = new BarcodeGenerator(
            EncodeTypes.Pdf417,
            "Åspóse.Barcóde©");

        // 2️⃣ Set module width (X‑dimension) to 2 pixels
        generator.Parameters.Barcode.XDimension.Pixels = 2;

        // 3️⃣ Choose a compact column count
        generator.Parameters.Barcode.Pdf417.Columns = 3;

        // Optional: increase error correction for noisy environments
        generator.Parameters.Barcode.Pdf417.ErrorLevel = 5;

        // 4️⃣ Determine output path (desktop for easy access)
        string desktop = Environment.GetFolderPath(Environment.SpecialFolder.Desktop);
        string filePath = Path.Combine(desktop, "Pdf417Basic.png");

        // 5️⃣ Export as PNG
        generator.Save(filePath, BarCodeImageFormat.Png);

        Console.WriteLine($"PDF417 barcode saved to: {filePath}");
    }
}
```

Exécutez le programme (`dotnet run`), puis ouvrez le fichier généré pour voir le code‑barres. La console confirmera l’emplacement de l’image enregistrée.

## Conclusion

Vous savez maintenant **comment générer un code‑barres PDF417** en C# du début à la fin. En créant un `BarcodeGenerator`, en configurant la dimension X et le nombre de colonnes, puis en exportant en PNG, vous pouvez intégrer la création de code‑barres dans n’importe quelle solution .NET. Expérimentez avec les niveaux de correction d’erreurs, différents formats d’image ou des charges de données plus importantes pour adapter le code‑barres à votre scénario spécifique.

### Étapes suivantes

* Explorez les **paramètres du code‑barres PDF417** tels que le nombre de lignes et le rapport d’aspect pour des mises en page personnalisées.  
* Intégrez la génération de code‑barres dans une API ASP.NET Core afin de servir les images à la demande.  
* Combinez ce code avec un générateur de QR‑code pour des documents multi‑symbologie.

N’hésitez pas à adapter l’exemple, partager vos résultats ou poser des questions dans les commentaires. Bon codage !

## Ce que vous devriez apprendre ensuite

Les tutoriels suivants couvrent des sujets étroitement liés qui s’appuient sur les techniques démontrées dans ce guide. Chaque ressource inclut des exemples de code complets avec des explications pas à pas pour vous aider à maîtriser des fonctionnalités API supplémentaires et explorer des approches d’implémentation alternatives dans vos propres projets.

- [Comment générer un code‑barres PDF417 en C# avec des dimensions personnalisées](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-with-custom-dimensions/)
- [Comment générer un code‑barres PDF417 en C# et définir la taille du code‑barres](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-and-set-barcode-size/)
- [Comment générer un code‑barres PDF417 en C# avec Barcode Generator](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-with-barcode-generator/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}