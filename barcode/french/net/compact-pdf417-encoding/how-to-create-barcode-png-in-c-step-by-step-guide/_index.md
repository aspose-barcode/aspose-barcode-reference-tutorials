---
category: general
date: 2026-10-15
description: Créer un PNG de code‑barres en C# avec un exemple compact de PDF417 –
  apprenez à définir les colonnes, ajuster les dimensions et générer l’image.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode png
- how to create barcode
- how to set columns
- c# barcode example
language: fr
lastmod: 2026-10-15
og_description: Créer un PNG de code-barres en C# avec un exemple compact de PDF417.
  Ce guide montre comment définir les colonnes, ajuster les dimensions et enregistrer
  l'image.
og_image_alt: Screenshot showing a generated barcode PNG created with C#
og_title: Créer un code‑barres PNG en C# – tutoriel complet de programmation
schemas:
- author: Aspose
  dateModified: '2026-10-15'
  description: Create barcode PNG in C# with a compact PDF417 example – learn how
    to set columns, adjust dimensions, and generate the image.
  headline: How to create barcode PNG in C# – step‑by‑step guide
  type: TechArticle
- description: Create barcode PNG in C# with a compact PDF417 example – learn how
    to set columns, adjust dimensions, and generate the image.
  name: How to create barcode PNG in C# – step‑by‑step guide
  steps:
  - name: Initialise the barcode generator with the desired text
    text: '```csharp using Aspose.BarCode.Generation;'
  - name: Set the module (X) dimension in pixels
    text: '```csharp // Set the width of the smallest bar (module) to 2 pixels generator.Parameters.Barcode.XDimension.Pixels
      = 2; ```'
  - name: Define the number of columns for the PDF417 barcode
    text: '```csharp // Specify that the barcode should use 3 columns generator.Parameters.Barcode.Pdf417.Columns
      = 3; ```'
  - name: Enable the compact layout by truncating the barcode
    text: '```csharp // Truncate removes unnecessary empty rows, making the barcode
      shorter generator.Parameters.Barcode.Pdf417.Truncate = true; ```'
  - name: Save the barcode image as PNG
    text: '```csharp // Choose the output folder and file name string outputPath =
      Path.Combine(Environment.CurrentDirectory, "CompactPdf417.png");'
  - name: Full, runnable example
    text: 'Putting everything together, here is a self‑contained program you can copy,
      paste, and run:'
  type: HowTo
tags:
- barcode
- C#
- PDF417
- image generation
title: Comment créer un PNG de code‑barres en C# – guide étape par étape
url: /fr/net/compact-pdf417-encoding/how-to-create-barcode-png-in-c-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Comment créer un PNG de code-barres en C# – guide étape par étape

Si vous avez besoin de **créer des PNG de code-barres** à partir de code C#, ce tutoriel vous montre une solution complète en quelques lignes seulement. Vous verrez comment définir les colonnes, ajuster la taille du module et enregistrer un code-barres PDF417 compact en tant qu'image PNG — le tout avec un exemple unique et facile à lire.

Générer des codes-barres de manière programmatique supprime l'étape manuelle d'utilisation d'un éditeur graphique, et vous permet d'intégrer les codes-barres directement dans les factures, les tickets ou les étiquettes d'inventaire. Dans les sections suivantes, nous couvrirons tout ce que vous devez savoir pour **comment créer des images de code-barres**, pourquoi chaque configuration est importante, et comment adapter le code à différents cas d'utilisation.

## Prérequis

* .NET 6.0 ou ultérieur (le code fonctionne également avec .NET Framework 4.7+)
* Une référence à une bibliothèque de code-barres qui prend en charge PDF417, telle que **Aspose.BarCode for .NET** ou **IronBarcode**. L'exemple utilise Aspose.BarCode, que vous pouvez installer via NuGet :

```bash
dotnet add package Aspose.BarCode
```

* Une connaissance de base de la syntaxe C# et de Visual Studio (ou tout IDE de votre choix).

> **Astuce :** Si vous préférez une alternative gratuite, la bibliothèque open‑source **ZXing.Net** prend également en charge PDF417, mais les noms de propriétés diffèrent légèrement. Les concepts présentés ici restent les mêmes.

## Comment créer un PNG de code-barres en C# (étape principale)

Le cœur de la solution est un objet `BarcodeGenerator` configuré pour l'encodage PDF417. Les sections suivantes décomposent chaque ligne de code, expliquent **comment définir les colonnes**, et montrent pourquoi les paramètres affectent la taille finale du PNG.

### Étape 1 : Initialiser le générateur de code-barres avec le texte souhaité

```csharp
using Aspose.BarCode.Generation;

// The text you want to encode in the barcode
string barcodeText = "Compact example";

// Create a generator for PDF417 barcodes
using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, barcodeText))
{
    // Subsequent configuration goes here
}
```

*Pourquoi c'est important* : L'énumération `EncodeTypes.Pdf417` indique à la bibliothèque de produire un code-barres empilé bidimensionnel. Le constructeur accepte également les données que vous souhaitez encoder, vous n'avez donc pas besoin d'un appel séparé à `SetData`.

### Étape 2 : Définir la dimension du module (X) en pixels

```csharp
// Set the width of the smallest bar (module) to 2 pixels
generator.Parameters.Barcode.XDimension.Pixels = 2;
```

La **dimension X** contrôle la densité visuelle du code-barres. Une valeur plus petite produit une image plus compacte, ce qui est utile lorsque vous avez besoin d'un PNG compact pour les écrans mobiles ou un espace d'impression limité.

### Étape 3 : Définir le nombre de colonnes pour le code-barres PDF417

```csharp
// Specify that the barcode should use 3 columns
generator.Parameters.Barcode.Pdf417.Columns = 3;
```

Cette ligne montre **comment définir les colonnes**. PDF417 peut choisir automatiquement le nombre optimal de colonnes, mais le définir explicitement vous donne une largeur prévisible, surtout lorsque vous intégrez le PNG dans une mise en page de taille fixe.

### Étape 4 : Activer la mise en page compacte en tronquant le code-barres

```csharp
// Truncate removes unnecessary empty rows, making the barcode shorter
generator.Parameters.Barcode.Pdf417.Truncate = true;
```

Lorsque `Truncate` est vrai, la bibliothèque supprime les lignes de fin qui ne contiennent aucune donnée, réduisant ainsi la hauteur globale de l'image sans perdre d'information.

### Étape 5 : Enregistrer l'image du code-barres au format PNG

```csharp
// Choose the output folder and file name
string outputPath = Path.Combine(Environment.CurrentDirectory, "CompactPdf417.png");

// Save the generated barcode as a PNG file
generator.Save(outputPath, BarCodeImageFormat.Png);
```

La méthode `Save` écrit le code-barres sur le disque dans le format que vous spécifiez. PNG est sans perte, ce qui le rend idéal pour les applications de numérisation qui nécessitent une détection précise des bords.

### Exemple complet et exécutable

En réunissant tous les éléments, voici un programme autonome que vous pouvez copier, coller et exécuter :

```csharp
using System;
using System.IO;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // 1️⃣ Initialise the generator with the data to encode
        string barcodeText = "Compact example";

        using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, barcodeText))
        {
            // 2️⃣ Set module width to 2 pixels for a tighter image
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // 3️⃣ Explicitly set the number of columns (how to set columns)
            generator.Parameters.Barcode.Pdf417.Columns = 3;

            // 4️⃣ Enable compact layout by truncating empty rows
            generator.Parameters.Barcode.Pdf417.Truncate = true;

            // 5️⃣ Define the output path and save as PNG (create barcode PNG)
            string outputPath = Path.Combine(Directory.GetCurrentDirectory(), "CompactPdf417.png");
            generator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"Barcode PNG saved to: {outputPath}");
        }
    }
}
```

**Sortie attendue** – Après avoir exécuté le programme, vous trouverez `CompactPdf417.png` dans le dossier d'exécution. L'image contient un code-barres PDF417 à trois colonnes, suffisamment compact pour tenir sur une étiquette standard de 2 × 2 cm tout en restant entièrement lisible.

![Create barcode PNG example](placeholder.png){alt="Créer un PNG de code-barres avec C#"}

## Comment définir les colonnes pour différentes tailles de données (mot‑clé secondaire)

Le nombre de colonnes influence à la fois la largeur et la lisibilité du code-barres :

| Colonnes | Largeur approximative (px) | Cas d'utilisation typique |
|----------|----------------------------|---------------------------|
| 1‑2      | Étroit, haut               | Petites étiquettes, impressions de type RFID |
| 3‑5      | Équilibré                  | Étiquettes à usage général |
| 6‑9      | Large, court               | Grands affiches ou emballages |

Si votre chaîne de données s'allonge, la bibliothèque peut automatiquement augmenter le nombre de lignes pour garder le code-barres dans la limite de colonnes. Cependant, forcer un nombre de colonnes trop bas peut rendre le code-barres excessivement haut, ce qui peut ne pas tenir sur une imprimante de tickets. Ajustez le nombre de colonnes en fonction des contraintes physiques de votre support de sortie.

## Comment créer des images de code-barres dans d'autres formats (mot‑clé secondaire)

Bien que le PNG soit le format le plus courant pour le web et le mobile, vous pourriez avoir besoin de **comment créer des images de code-barres** en JPEG, BMP ou SVG pour des flux de travail spécialisés :

```csharp
// Save as JPEG with 90 % quality
generator.Save("CompactPdf417.jpg", BarCodeImageFormat.Jpeg, 90);

// Save as SVG (vector, infinite scaling)
generator.Save("CompactPdf417.svg", BarCodeImageFormat.Svg);
```

Le choix du bon format dépend du consommateur en aval :

* **PNG** – sans perte, idéal pour les scanners.
* **JPEG** – taille de fichier plus petite, acceptable lorsque de légères artefacts de compression sont tolérables.
* **SVG** – parfait pour l'impression haute résolution ou le redimensionnement d'interface.

## Exemple de code-barres C# : gestion des erreurs et des cas limites

Un **exemple de code-barres c#** robuste doit anticiper les problèmes d'exécution :

```csharp
try
{
    // All configuration steps as shown earlier
    generator.Save(outputPath, BarCodeImageFormat.Png);
}
catch (ArgumentException ex)
{
    Console.Error.WriteLine($"Invalid barcode parameter: {ex.Message}");
}
catch (IOException ex)
{
    Console.Error.WriteLine($"Failed to write file: {ex.Message}");
}
```

*Pourquoi encapsuler dans `try/catch` ?* Les caractères invalides dans le texte, les dimensions non prises en charge ou les problèmes de permissions d'écriture lanceront des exceptions. Les gérer correctement empêche votre application de planter lors du traitement par lots.

## Extension de l'exemple : ajout d'un logo ou d'un arrière‑plan

De nombreux scénarios réels nécessitent une superposition de logo ou un arrière‑plan coloré. L'API Aspose.BarCode vous permet de combiner le code-barres avec un bitmap :

```csharp
// Load a logo image
using (Bitmap logo = (Bitmap)Image.FromFile("logo.png"))
{
    generator.Parameters.Barcode.ImageFormat = BarCodeImageFormat.Png;
    generator.Parameters.Barcode.Pdf417.EnablePdf417CodewordCount = true; // optional

    // Merge the logo with the barcode (centered)
    generator.Save("BarcodeWithLogo.png", BarCodeImageFormat.Png, logo);
}
```

Cette technique maintient le flux de travail **create barcode PNG** intact tout en enrichissant le branding visuel de l'image finale.

## Résumé

Dans ce guide, nous avons démontré comment **créer des PNG de code-barres** en C# en utilisant une configuration PDF417 compacte. Vous avez appris :

* Le code exact nécessaire pour initialiser un `BarcodeGenerator`.
* **Comment définir les colonnes** et pourquoi le nombre de colonnes est important pour la taille et la lisibilité.
* Comment ajuster la dimension X et activer la troncature pour un PNG plus compact.
* Les différentes manières d'enregistrer l'image en PNG, JPEG ou SVG.
* Les modèles de gestion des erreurs pour un **exemple de code-barres c#** prêt pour la production.
* Les extensions optionnelles telles que la superposition de logo et la personnalisation de l'arrière‑plan.

Vous disposez maintenant d'un extrait prêt à l'exécution que vous pouvez intégrer aux générateurs de factures, aux systèmes de billetterie ou aux outils de gestion d'inventaire. Expérimentez avec différentes valeurs de colonnes, tailles de modules ou types de code-barres (par ex., QR, Code128) pour voir comment l'image change.

## Prochaines étapes

* Explorer d'autres types d'encodage (`EncodeTypes.QR`, `EncodeTypes.Code128`) pour couvrir plus de cas d'utilisation.
* Combiner la génération de code-barres avec des bibliothèques de création PDF (par ex., **iTextSharp**) pour intégrer le PNG directement dans les documents.
* Investiguer le dimensionnement dynamique : calculer le nombre optimal de colonnes en fonction de la longueur de la chaîne d'entrée et des dimensions de l'étiquette cible.

Bon codage, et profitez de la simplicité de la génération programmatique de PNG de code-barres nets en C# !

## Que devriez‑vous apprendre ensuite ?

Les tutoriels suivants couvrent des sujets étroitement liés qui s'appuient sur les techniques démontrées dans ce guide. Chaque ressource comprend des exemples de code complets et fonctionnels avec des explications étape par étape pour vous aider à maîtriser des fonctionnalités API supplémentaires et explorer des approches d'implémentation alternatives dans vos propres projets.

- [Comment créer un code-barres PDF417 et l'enregistrer en PNG en C#](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-and-save-it-as-png-in-c/)
- [Comment créer un code-barres PDF417 et définir sa taille en C#](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-and-set-its-size-in-c/)
- [Comment créer un code-barres PDF417 en C# avec le mode compact](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-in-c-with-compact-mode/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}