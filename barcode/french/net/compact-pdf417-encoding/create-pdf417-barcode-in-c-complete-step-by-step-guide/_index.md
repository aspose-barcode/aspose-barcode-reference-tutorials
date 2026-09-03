---
category: general
date: 2026-07-18
description: Créez rapidement un code‑barres PDF417 avec C#. Apprenez à générer le
  code‑barres, à définir les paramètres et à enregistrer les fichiers image – inclut
  la prise en charge d’AI 10.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create pdf417 barcode
- how to generate barcode
- how to set parameters
- how to save image
- barcode ai 10
language: fr
lastmod: 2026-07-18
og_description: Créez un code‑barres PDF417 en C# avec un guide complet. Découvrez
  comment générer le code‑barres, ajuster les paramètres et enregistrer les images
  tout en gérant AI 10.
og_image_alt: Screenshot illustrating create pdf417 barcode code in C#
og_title: Créer un code‑barres PDF417 en C# – Exemple complet, rapide et flexible
schemas:
- author: Aspose
  dateModified: '2026-07-18'
  description: Create PDF417 barcode quickly with C#. Learn how to generate barcode,
    set parameters, and save image files – includes AI 10 handling.
  headline: Create PDF417 Barcode in C# – Complete Step‑by‑Step Guide
  type: TechArticle
- description: Create PDF417 barcode quickly with C#. Learn how to generate barcode,
    set parameters, and save image files – includes AI 10 handling.
  name: Create PDF417 Barcode in C# – Complete Step‑by‑Step Guide
  steps:
  - name: '**X‑dimension** – controls the width of the smallest bar (in pixels)'
    text: '**X‑dimension** – controls the width of the smallest bar (in pixels)'
  - name: '**Column count** – influences the overall shape; fewer columns = taller
      barcode'
    text: '**Column count** – influences the overall shape; fewer columns = taller
      barcode'
  - name: '**IsLinked** – enables the optional link module that ties the barcode to
      the data string'
    text: '**IsLinked** – enables the optional link module that ties the barcode to
      the data string'
  type: HowTo
tags:
- barcode
- pdf417
- csharp
- aspnet
- barcode-generation
title: Créer un code‑barres PDF417 en C# – Guide complet étape par étape
url: /fr/net/compact-pdf417-encoding/create-pdf417-barcode-in-c-complete-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Créer un code‑barres PDF417 en C# – Guide complet étape par étape

Vous avez déjà eu besoin de **créer un code‑barres pdf417** sans savoir quelle bibliothèque ou quels paramètres choisir ? Vous n'êtes pas seul — de nombreux développeurs rencontrent ce problème lorsqu'ils s'initient à GS1‑Micro‑PDF417. La bonne nouvelle, c’est qu’avec quelques lignes de C# vous pouvez générer un code‑barres parfaitement formaté, ajuster son apparence et enregistrer l’image directement sur le disque.

Dans ce tutoriel, nous allons parcourir **comment générer un code‑barres** à l’aide de la bibliothèque Aspose.BarCode, montrer **comment définir les paramètres** tels que la dimension X et le nombre de colonnes, et démontrer **comment enregistrer l’image** pour les variantes AI 10 et AI 21. À la fin, vous disposerez d’un extrait réutilisable à intégrer dans n’importe quel projet .NET.

## Prérequis

Avant de commencer, assurez‑vous d’avoir :

- .NET 6+ ou .NET Framework 4.7.2 (tout runtime récent convient)
- Visual Studio 2022 ou votre éditeur C# préféré
- Le package NuGet **Aspose.BarCode for .NET** (`Install-Package Aspose.BarCode`)
- Un dossier accessible en écriture où les fichiers PNG seront enregistrés

C’est tout — pas d’outils supplémentaires, pas de configuration complexe. Prêt ? C’est parti.

## Étape 1 : Créer un code‑barres PDF417 avec le format GS1‑Micro

La première chose que nous faisons est de **créer un code‑barres pdf417** et d’y injecter les données AI initiales. Dans GS1‑Micro‑PDF417, l’AI 10 (numéro de lot) est souvent le point de départ, nous l’encoderons donc immédiatement.

```csharp
using Aspose.BarCode.Generation;

// Define where the PNGs will be saved
string outputDir = @"C:\Barcodes\";

// Instantiate the generator for GS1‑Micro‑PDF417
BarcodeGenerator barcode = new BarcodeGenerator(
    EncodeTypes.GS1MicroPdf417,
    "(10)ABCD12345(240)ABCD");   // AI 10 + additional data
```

> **Pourquoi c’est important :** `EncodeTypes.GS1MicroPdf417` indique à la bibliothèque de suivre la spécification GS1‑Micro, qui préfixe automatiquement les crochets AI. Si vous omettez cela, vous obtiendrez un PDF417 générique qui pourrait ne pas être lisible dans les environnements de vente au détail.

## Étape 2 : Comment définir les paramètres du code‑barres

Maintenant que nous disposons d’une instance de code‑barres, nous devons affiner ses caractéristiques visuelles. C’est ici que **comment définir les paramètres** entre en jeu. Nous ajusterons trois réglages courants :

1. **Dimension X** – contrôle la largeur de la plus petite barre (en pixels)
2. **Nombre de colonnes** – influence la forme globale ; moins de colonnes = code‑barres plus haut
3. **IsLinked** – active le module de lien optionnel qui associe le code‑barres à la chaîne de données

```csharp
// X‑dimension: 2 pixels per module (good balance of size vs readability)
barcode.Parameters.Barcode.XDimension.Pixels = 2;

// Columns: 3 columns makes the barcode compact yet readable
barcode.Parameters.Barcode.Pdf417.Columns = 3;

// Enable linking (adds a special pattern that some scanners use)
barcode.Parameters.Barcode.Pdf417.IsLinked = true;
```

> **Astuce pro :** Si vous ciblez la numérisation mobile, augmentez la dimension X à 3‑4 pixels ; les modules plus grands résistent mieux aux caméras à faible résolution.

## Étape 3 : Comment enregistrer l’image – Première version (AI 10)

Une fois le générateur configuré, nous pouvons enfin **comment enregistrer l’image**. La méthode `Save` écrit le code‑barres dans un fichier au format que vous spécifiez. Ici nous utilisons le PNG car il conserve des bords nets sans artefacts de compression.

```csharp
// Save the barcode that encodes AI 10
barcode.Save($"{outputDir}GS1MicroPdf417_AI10.png", BarCodeImageFormat.Png);
```

À ce stade, vous devriez voir un fichier nommé `GS1MicroPdf417_AI10.png` dans votre `outputDir`. Ouvrez‑le avec n’importe quel visualiseur d’images — vous verrez un PDF417 net, à fort contraste, prêt à être imprimé.

## Étape 4 : Passer à un autre AI (AI 21) et enregistrer à nouveau

Souvent, il faut encoder un identifiant d’application différent, comme l’AI 21 (numéro de série). Modifier la propriété `CodeText` suffit. Cela montre la gestion de **barcode ai 10** versus **barcode ai 21** en une seule fois.

```csharp
// Change the encoded data – now using AI 21
barcode.CodeText = "(21)ABCD12345(240)ABCD";

// Save the new variant
barcode.Save($"{outputDir}GS1MicroPdf417_AI21.png", BarCodeImageFormat.Png);
```

> **Et si vous avez besoin de plus d’AIs ?** Il suffit de les concaténer dans la même chaîne, par ex. `"(10)ABCD(21)12345(240)XYZ"`. La bibliothèque analyse automatiquement les crochets.

## Exemple complet fonctionnel

En rassemblant le tout, voici un programme autonome que vous pouvez copier‑coller dans une application console :

```csharp
using System;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // 1️⃣ Output folder – change to suit your environment
        string outputDir = @"C:\Barcodes\";

        // 2️⃣ Create generator with initial AI 10 data
        BarcodeGenerator barcode = new BarcodeGenerator(
            EncodeTypes.GS1MicroPdf417,
            "(10)ABCD12345(240)ABCD");

        // 3️⃣ Set visual parameters
        barcode.Parameters.Barcode.XDimension.Pixels = 2;   // how to set parameters
        barcode.Parameters.Barcode.Pdf417.Columns = 3;
        barcode.Parameters.Barcode.Pdf417.IsLinked = true;

        // 4️⃣ Save first image (AI 10)
        barcode.Save($"{outputDir}GS1MicroPdf417_AI10.png", BarCodeImageFormat.Png);
        Console.WriteLine("Saved AI 10 barcode.");

        // 5️⃣ Switch to AI 21 and save second image
        barcode.CodeText = "(21)ABCD12345(240)ABCD";
        barcode.Save($"{outputDir}GS1MicroPdf417_AI21.png", BarCodeImageFormat.Png);
        Console.WriteLine("Saved AI 21 barcode.");
    }
}
```

**Résultat attendu :** Deux fichiers PNG apparaissent dans `C:\Barcodes\` — `GS1MicroPdf417_AI10.png` et `GS1MicroPdf417_AI21.png`. Les deux contiennent un PDF417 lisible ; le premier encode l’AI 10, le second l’AI 21.

## Pièges courants et comment les éviter

- **Permissions du dossier manquantes :** Si `Save` lève une `UnauthorizedAccessException`, vérifiez que le chemin existe et que votre application possède les droits d’écriture.
- **Mauvais format d’AI :** Oublier les parenthèses (`(10)`) entraînera le traitement du code‑barres comme des données brutes, ce qui rompra la validation GS1.
- **Dimension X trop petite :** Des barres plus fines qu’un pixel peuvent disparaître lors du redimensionnement de l’image. Optez pour au moins 2 pixels pour l’affichage à l’écran.

## Prochaines étapes et sujets associés

Maintenant que vous savez **comment générer un code‑barres**, **comment définir les paramètres**, et **comment enregistrer l’image**, vous pourriez explorer :

- Ajouter du **texte lisible par l’homme** sous le code‑barres (`barcode.Parameters.Barcode.CodeTextLocation = CodeLocation.BelowBarcode`)
- Exporter en **PDF** au lieu de PNG (`BarCodeImageFormat.Pdf`)
- Intégrer la génération de code‑barres dans une **API ASP.NET Core** pour créer des images à la volée

Chacun de ces sujets s’appuie directement sur les bases posées dans ce guide.

---

### Récapitulatif rapide

- **Créer un code‑barres pdf417** avec `BarcodeGenerator` et `EncodeTypes.GS1MicroPdf417`
- **Comment définir les paramètres** tels que dimension X, colonnes et liaison
- **Comment enregistrer l’image** en PNG pour les variantes AI 10 et AI 21
- Gestion du **barcode ai 10** et passage au **barcode ai 21** avec un simple changement de propriété

Testez, ajustez les réglages, et vous disposerez d’un moteur de code‑barres robuste prêt pour la production. Des questions ou besoin d’approfondir ? Laissez un commentaire ci‑dessous—bon codage !

## Que devriez‑vous apprendre ensuite ?

Les tutoriels suivants couvrent des sujets étroitement liés qui s’appuient sur les techniques démontrées dans ce guide. Chaque ressource comprend des exemples de code complets avec des explications pas à pas pour vous aider à maîtriser d’autres fonctionnalités de l’API et explorer des approches d’implémentation alternatives dans vos propres projets.

- [How to Create Barcode – Compact PDF417 with Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [How to Create Barcode Quiet Zone for ITF-14 Using Aspose.BarCode for .NET](/barcode/english/net/itf-14-barcode-customization/itf-14-barcode-quiet-zone-configuration/)
- [How to create Aztec barcode with error correction in .NET](/barcode/english/net/aztec-barcode-encoding/aztec-error-level-example/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}