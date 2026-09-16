---
category: general
date: 2026-07-15
description: Générez rapidement un code‑barres PDF417 avec C#. Apprenez à créer un
  code‑barres à partir de texte, à ajuster sa taille et à définir des dimensions personnalisées
  en quelques minutes.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate pdf417 barcode
- generate barcode from text
- adjust barcode size
- custom barcode dimensions
language: fr
lastmod: 2026-07-15
og_description: Générez un code‑barres PDF417 en C# instantanément. Ce guide montre
  comment créer un code‑barres à partir du texte, ajuster sa taille et appliquer des
  dimensions personnalisées.
og_image_alt: Screenshot of a PDF417 barcode generated with custom dimensions using
  C# code
og_title: Générer un code-barres PDF417 en C# – Tutoriel complet de programmation
schemas:
- author: Aspose
  dateModified: '2026-07-15'
  description: Generate PDF417 barcode quickly with C#. Learn how to generate barcode
    from text, adjust barcode size, and set custom barcode dimensions in minutes.
  headline: Generate PDF417 Barcode in C# – Complete Step‑by‑Step Guide
  type: TechArticle
tags:
- barcode
- pdf417
- csharp
title: Générer un code‑barres PDF417 en C# – Guide complet étape par étape
url: /fr/net/compact-pdf417-encoding/generate-pdf417-barcode-in-c-complete-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Générer un code‑barres PDF417 en C# – Guide complet étape par étape

Vous avez déjà eu besoin de **générer un code‑barres PDF417** mais vous ne saviez pas quels paramètres ajuster ? Vous n'êtes pas le seul—de nombreux développeurs rencontrent le même problème lorsqu'ils manipulent pour la première fois des codes‑barres 2‑D. La bonne nouvelle ? En quelques lignes de C#, vous pouvez transformer n'importe quelle chaîne en une image PDF417 scannable, contrôler sa taille exacte, et même définir une disposition personnalisée de colonnes et de lignes.

Dans ce tutoriel, nous allons parcourir comment **générer un code‑barres à partir de texte**, ajuster la taille du code‑barres, et définir des dimensions personnalisées du code‑barres — le tout en utilisant la populaire bibliothèque Aspose.BarCode. À la fin, vous disposerez d'un exemple prêt à l'exécution que vous pourrez intégrer dans n'importe quel projet .NET.

![Exemple de génération de code‑barres PDF417](https://example.com/og-image.png "Exemple de génération de code‑barres PDF417")

## Ce que vous allez créer

- Un code‑barres PDF417 qui encode la chaîne `Åspóse.Barcóde©`.
- Un contrôle précis de la X‑dimension (largeur en pixels de chaque module).
- Une disposition personnalisée de 4 colonnes et 9 lignes.
- Un fichier PNG enregistré sur le disque.

Pas de services externes, pas de tours de magie—juste du code C# pur que vous pouvez compiler dès maintenant.

## Prérequis

- .NET 6.0 ou ultérieur (le code fonctionne également sur .NET Framework 4.8).
- Visual Studio 2022 ou tout IDE supportant C#.
- Aspose.BarCode pour .NET (version d'essai gratuite ou version sous licence). Installez via NuGet :

```bash
dotnet add package Aspose.BarCode
```

C’est tout—une fois le package référencé, vous êtes prêt à partir.

## Étape 1 – Générer un code‑barres PDF417 avec des données texte

La première chose dont nous avons besoin est une instance de `BarcodeGenerator` qui sait que nous travaillons avec la symbologie PDF417 et le texte exact que nous voulons encoder.

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;

// Step 1: Initialize the barcode generator with PDF417 symbology and the data to encode
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(EncodeTypes.Pdf417, "Åspóse.Barcóde©");
```

> **Pourquoi c'est important :**  
> `EncodeTypes.Pdf417` indique à la bibliothèque d'utiliser le format PDF417 2‑D, tandis que le deuxième argument est la charge utile **générer un code‑barres à partir de texte**. Tout ce que vous passez ici devient les données stockées dans la matrice du code‑barres.

## Étape 2 – Ajuster la taille du code‑barres (X‑Dimension)

Si vous avez déjà imprimé un code‑barres qui semblait trop petit sur un reçu, vous connaissez la frustration du scanner qui ne le détecte pas. La propriété `XDimension` contrôle la largeur d'un seul module (le plus petit carré noir ou blanc) en pixels.

```csharp
// Step 2: Set the module (X) dimension in pixels to control barcode size
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2; // 2 px per module
```

> **Astuce pro :**  
> Une valeur de 2 px fonctionne bien pour la plupart des scénarios d'affichage à l'écran. Pour les impressions haute résolution, vous pouvez l'augmenter à 3 ou 4 px. N'oubliez pas que des X‑dimensions plus grandes augmentent la taille globale de l'image.

## Étape 3 – Définir des dimensions personnalisées du code‑barres (Colonnes & Lignes)

PDF417 vous permet de définir le nombre de colonnes et de lignes que le code‑barres doit occuper. C'est ici que les **dimensions personnalisées du code‑barres** entrent en jeu. Modifier ces valeurs peut vous aider à adapter le code‑barres à un espace UI restreint ou à répondre à une taille d'étiquette spécifique.

```csharp
// Step 3: Define the layout of the PDF417 barcode: number of columns and rows
barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 4; // 4 columns
barcodeGenerator.Parameters.Barcode.Pdf417.Rows    = 9; // 9 rows
```

> **Que se passe-t-il en coulisses ?**  
> La bibliothèque redistribue les données encodées sur la grille spécifiée. Moins de colonnes signifie des codes‑barres plus hauts ; plus de lignes les rendent plus courts. Expérimentez avec les nombres jusqu'à ce que l'équilibre visuel vous convienne pour votre application.

## Étape 4 – Enregistrer l'image du code‑barres

Maintenant que nous avons tout configuré, nous demandons simplement au générateur d'écrire un fichier PNG. Le PNG est sans perte, donc la netteté des modules reste intacte.

```csharp
// Step 4: Save the generated barcode as a PNG image
barcodeGenerator.Save(@"C:\Barcodes\CustomLayout.png", BarCodeImageFormat.Png);
```

Lorsque vous exécutez le programme, vous devriez voir un fichier à `C:\Barcodes\CustomLayout.png` qui ressemble à la capture d'écran ci‑dessus. Le scanner avec n'importe quel lecteur compatible PDF417 renverra la chaîne originale `Åspóse.Barcóde©`.

## Exemple complet fonctionnel

Voici le programme complet que vous pouvez copier‑coller dans une application console. Il inclut toutes les directives using et la gestion des erreurs que l’on attend d’un code de production.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        try
        {
            // 1️⃣ Initialize generator with PDF417 symbology and text
            BarcodeGenerator generator = new BarcodeGenerator(
                EncodeTypes.Pdf417,
                "Åspóse.Barcóde©");

            // 2️⃣ Adjust X‑dimension to control overall size
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // 3️⃣ Apply custom layout: 4 columns × 9 rows
            generator.Parameters.Barcode.Pdf417.Columns = 4;
            generator.Parameters.Barcode.Pdf417.Rows    = 9;

            // 4️⃣ Save as PNG
            string outPath = @"C:\Barcodes\CustomLayout.png";
            generator.Save(outPath, BarCodeImageFormat.Png);

            Console.WriteLine($"✅ Barcode generated successfully → {outPath}");
        }
        catch (Exception ex)
        {
            Console.WriteLine($"❌ Error: {ex.Message}");
        }
    }
}
```

### Sortie attendue

L'exécution du code affiche :

```
✅ Barcode generated successfully → C:\Barcodes\CustomLayout.png
```

…et crée un PNG qui peut être ouvert dans n'importe quel visualiseur d'images. Si vous le scannez avec une application mobile (par ex., “Barcode Scanner” sur iOS/Android), le texte décodé devrait être exactement **Åspóse.Barcóde©**.

## Questions fréquentes & cas particuliers

| Question | Réponse |
|----------|--------|
| **Puis-je utiliser un autre format d'image ?** | Oui—`BarCodeImageFormat.Jpeg`, `Bmp`, `Gif` ou `Svg` sont tous pris en charge. Il suffit de changer le deuxième argument de `Save`. |
| **Et si mon texte contient des caractères Unicode ?** | Aspose.BarCode prend en charge pleinement UTF‑8, donc l'exemple avec `Å` et `©` fonctionne immédiatement. |
| **Comment modifier le niveau de correction d'erreur ?** | Utilisez `generator.Parameters.Barcode.Pdf417.ErrorCorrectionLevel = Pdf417ErrorCorrectionLevel.Level5;` (niveaux 0‑8). Des niveaux plus élevés augmentent la redondance mais aussi la taille. |
| **J'ai besoin d'un arrière-plan transparent—est‑ce possible ?** | Définissez `generator.Parameters.Barcode.Image.TransparentBackground = true;` avant d'enregistrer. |
| **Existe‑t‑il un moyen d'intégrer le code‑barres directement dans un PDF ?** | Absolument. Remplacez l'appel `Save` par `generator.Save("output.pdf", BarCodeImageFormat.Pdf);` et vous obtiendrez un PDF d'une page contenant le code‑barres. |

## Conclusion

Vous savez maintenant comment **générer un code‑barres PDF417** en C# à partir de n'importe quelle chaîne, **ajuster la taille du code‑barres**, et appliquer des **dimensions personnalisées du code‑barres** pour répondre à vos besoins de mise en page. Le flux en quatre étapes—initialisation, taille, disposition, enregistrement—couvre le processus principal pour la plupart des scénarios de codes‑barres 2‑D.

Et ensuite ? Essayez de remplacer `EncodeTypes.Pdf417` par `EncodeTypes.QR` ou `EncodeTypes.Code128` pour voir comment l'API s'adapte. Expérimentez avec différentes valeurs de `XDimension`, jouez avec la matrice colonnes/lignes, ou intégrez l'image dans un rapport PDF. Les possibilités sont pratiquement infinies, et vous disposez maintenant d'une base solide pour construire.

Vous avez d'autres questions, ou avez découvert une astuce ingénieuse en manipulant PDF417 ? Laissez un commentaire ci‑dessous—continuons la discussion. Bon codage !

## Que devriez‑vous apprendre ensuite ?

Les tutoriels suivants couvrent des sujets étroitement liés qui s'appuient sur les techniques démontrées dans ce guide. Chaque ressource comprend des exemples de code complets et fonctionnels avec des explications étape par étape pour vous aider à maîtriser des fonctionnalités API supplémentaires et explorer des approches d'implémentation alternatives dans vos propres projets.

- [Comment générer un code‑barres Aztec avec un ratio d'aspect personnalisé en utilisant Aspose.BarCode pour .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)
- [Comment générer des codes‑barres - Types de codes‑barres unidimensionnels](/barcode/english/net/one-dimensional-barcode-types/)
- [Générer un code‑barres DataMatrix – Guide pro avec Aspose.BarCode](/barcode/english/net/datamatrix-barcode-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}