---
category: general
date: 2026-07-15
description: Créez un code‑barres omnidirectionnel en C# rapidement avec Aspose.BarCode
  – apprenez à générer un code‑barres C# avec hauteur de barre et dimension X réglables.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create omni-directional barcode
- how to generate barcode c#
- GS1 DataBar Omni-Directional
- barcode XDimension
- barcode BarHeight
language: fr
lastmod: 2026-07-15
og_description: Créez un code‑barres omnidirectionnel en C# avec Aspose.BarCode. Maîtrisez
  la génération de code‑barres en C# en ajustant XDimension et BarHeight pour des
  résultats parfaits.
og_image_alt: Screenshot showing a create omni-directional barcode generated in C#
  with 60 px bar height
og_title: Créer un code-barres omnidirectionnel en C# – Guide complet de programmation
schemas:
- author: Aspose
  dateModified: '2026-07-15'
  description: create omni-directional barcode in C# quickly with Aspose.BarCode –
    learn how to generate barcode C# with adjustable bar height and X‑dimension.
  headline: create omni-directional barcode in C# – Step‑by‑Step Guide
  type: TechArticle
- description: create omni-directional barcode in C# quickly with Aspose.BarCode –
    learn how to generate barcode C# with adjustable bar height and X‑dimension.
  name: create omni-directional barcode in C# – Step‑by‑Step Guide
  steps:
  - name: Expected output
    text: '- `DatabarBarHeight30Pixels.png` – a 30 px tall omni‑directional barcode.
      - `DatabarBarHeight60Pixels.png` – the same data, but with a 60 px tall barcode.'
  - name: What if I need a different X‑dimension?
    text: Simply assign a new value before calling `Save`. For ultra‑high‑density
      printing you might go down to 1 px, but test with your scanner first—some devices
      struggle with sub‑2 px bars.
  - name: Can I add human‑readable text below the barcode?
    text: Yes. Set `barcodeGenerator.Parameters.Barcode.CodeText` to a string and
      optionally adjust `barcodeGenerator.Parameters.Barcode.CodeLocation` to `BarCodeTextLocation.Below`.
      This is handy for retail environments where the numeric GTIN must be visible.
  - name: Is PNG the best format for printing?
    text: PNG is lossless, which preserves the sharp edges needed for barcode scanners.
      If your downstream system expects a different format (TIFF, BMP), just change
      the `BarCodeImageFormat` enum.
  type: HowTo
tags:
- barcode
- C#
- Aspose
- GS1
- DataBar
title: Créer un code‑barres omnidirectionnel en C# – Guide étape par étape
url: /fr/python-java/general/create-omni-directional-barcode-in-c-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Créer un code-barres omni-directionnel en C# – Guide étape par étape

Vous vous êtes déjà demandé comment générer un code-barres C# qui respecte la symbologie GS1 DataBar Omni‑Directional ? Vous n'êtes pas seul. Dans ce tutoriel, nous allons **créer un code-barres omni-directionnel** à partir de zéro, ajuster la X‑dimension et jouer avec la hauteur des barres — le tout en utilisant la bibliothèque Aspose.BarCode.

Nous parcourrons un scénario réel : vous avez besoin d'un code-barres compact et à haute densité pour une étiquette de vente au détail, et vous souhaitez un contrôle total sur sa taille visuelle. À la fin, vous disposerez de deux fichiers PNG — l'un avec une hauteur de barre de 30 px et l'autre de 60 px — prêts à être intégrés à n'importe quel flux d'impression.

## Prérequis

- .NET 6 (ou tout runtime .NET récent) installé sur votre machine.  
- Visual Studio 2022 ou VS Code — votre IDE préféré fera l'affaire.  
- Un package NuGet gratuit Aspose.BarCode pour .NET (`Aspose.BarCode`).

Aucune autre dépendance n'est requise. Si vous n'avez jamais utilisé NuGet auparavant, ouvrez simplement la console du gestionnaire de packages et exécutez :

```powershell
Install-Package Aspose.BarCode
```

## créer un code-barres omni-directionnel – Comprendre les bases

La symbologie **GS1 DataBar Omni‑Directional** est conçue pour être scannée sous n'importe quelle orientation, ce qui la rend parfaite pour les étiquettes de bord de rayon. Lorsque vous appelez `new BarcodeGenerator(EncodeTypes.DatabarOmniDirectional, data)`, la bibliothèque effectue le travail lourd : elle encode les données, applique les règles de la symbologie et prépare une image raster.

> **Conseil pro :** Enveloppez toujours les données brutes dans le format d'Identifiant d'Application (AI) approprié, par ex. `"(01)12345678901231"` pour un GTIN‑14. Cela indique au scanner ce que représentent les chiffres.

## Étape 1 – Configurer le générateur de code-barres (how to generate barcode c#)

Tout d'abord, nous créons l'objet générateur. C'est la pierre angulaire de **how to generate barcode c#** avec Aspose.

```csharp
using Aspose.BarCode.Generation;

// Step 1: Create a barcode generator for the GS1 DataBar Omni‑Directional symbology
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");
```

## Étape 2 – Ajuster la X‑Dimension (barcode XDimension)

La **barcode XDimension** contrôle la largeur de la plus petite barre. Une valeur de 2 px représente un bon compromis entre lisibilité et compacité pour la plupart des imprimantes d'étiquettes.

```csharp
// Step 2: Define common barcode parameters (2 px X‑dimension)
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

Si vous avez besoin d'un rendu plus fin ou plus épais, modifiez simplement le nombre. Rappelez‑vous : la X‑dimension est l'unité fondamentale ; toutes les autres largeurs de barres sont des multiples de cette valeur.

## Étape 3 – Créer la première image avec une hauteur de barre de 30 px (barcode BarHeight)

Nous définissons maintenant la **barcode BarHeight** à 30 px et enregistrons l'image. Cela produit un code-barres de taille modeste qui s'adapte parfaitement à une étiquette standard.

```csharp
// Step 3: Set a 30 px bar height and save the first image
barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 30;
barcodeGenerator.Save("YOUR_DIRECTORY/DatabarBarHeight30Pixels.png", BarCodeImageFormat.Png);
```

La méthode `Save` écrit un fichier PNG sur le disque. Vous pouvez remplacer `BarCodeImageFormat.Jpeg` si vous préférez une sortie JPEG.

## Étape 4 – Augmenter la hauteur de barre à 60 px pour les étiquettes plus grandes (barcode BarHeight)

Parfois, un code-barres plus grand est nécessaire — peut‑être pour une étiquette de rayon placée plus loin du scanner. Doublons la hauteur.

```csharp
// Step 4: Increase the bar height to 60 px for a larger barcode
barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 60;
```

Notez que nous **n'avons pas** besoin de recréer le générateur ; nous ajustons simplement le paramètre et réutilisons le même objet. Cela économise de la mémoire et garde le code propre.

## Étape 5 – Enregistrer la deuxième image (how to generate barcode c#)

Enfin, nous enregistrons le deuxième PNG. Vous avez maintenant deux fichiers qui ne diffèrent que par la hauteur des barres.

```csharp
// Step 5: Save the second image with the updated height
barcodeGenerator.Save("YOUR_DIRECTORY/DatabarBarHeight60Pixels.png", BarCodeImageFormat.Png);
```

### Résultat attendu

- `DatabarBarHeight30Pixels.png` – un code-barres omni‑directionnel de 30 px de hauteur.  
- `DatabarBarHeight60Pixels.png` – les mêmes données, mais avec un code-barres de 60 px de hauteur.

Ouvrez les fichiers dans n'importe quel visualiseur d'images ; vous verrez des barres nettes et scannables qui respectent la spécification GS1 DataBar Omni‑Directional.

## Questions fréquentes & cas limites

### Et si j'ai besoin d'une X‑dimension différente ?

Attribuez simplement une nouvelle valeur avant d'appeler `Save`. Pour une impression ultra‑haute densité, vous pourriez descendre à 1 px, mais testez d'abord avec votre scanner — certains appareils ont du mal avec des barres inférieures à 2 px.

### Puis‑je ajouter du texte lisible sous le code‑barres ?

Oui. Définissez `barcodeGenerator.Parameters.Barcode.CodeText` sur une chaîne et ajustez éventuellement `barcodeGenerator.Parameters.Barcode.CodeLocation` à `BarCodeTextLocation.Below`. Cela est pratique pour les environnements de vente au détail où le GTIN numérique doit être visible.

```csharp
barcodeGenerator.Parameters.Barcode.CodeText = "(01)12345678901231";
barcodeGenerator.Parameters.Barcode.CodeLocation = BarCodeTextLocation.Below;
```

### Le PNG est‑il le meilleur format pour l’impression ?

Le PNG est sans perte, ce qui préserve les bords nets nécessaires aux scanners de codes‑barres. Si votre système en aval attend un format différent (TIFF, BMP), il suffit de changer l'énumération `BarCodeImageFormat`.

## Exemple complet fonctionnel (create omni-directional barcode)

Voici le programme complet, prêt à être exécuté. Copiez‑collez‑le dans un nouveau projet console et appuyez sur **F5**.

```csharp
using System;
using Aspose.BarCode.Generation;

namespace OmniDirectionalDemo
{
    class Program
    {
        static void Main()
        {
            // 1️⃣ Create generator for GS1 DataBar Omni‑Directional
            BarcodeGenerator generator = new BarcodeGenerator(
                EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");

            // 2️⃣ Set X‑dimension (2 px)
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // 3️⃣ First image – 30 px height
            generator.Parameters.Barcode.BarHeight.Pixels = 30;
            generator.Save("DatabarBarHeight30Pixels.png", BarCodeImageFormat.Png);

            // 4️⃣ Second image – 60 px height
            generator.Parameters.Barcode.BarHeight.Pixels = 60;
            generator.Save("DatabarBarHeight60Pixels.png", BarCodeImageFormat.Png);

            Console.WriteLine("Two omni‑directional barcodes created successfully.");
        }
    }
}
```

Exécutez le programme, vérifiez le dossier de sortie, et vous verrez les deux fichiers PNG exactement comme décrit.

## Récapitulatif

Nous avons montré le code **how to generate barcode C#** qui crée un **create omni-directional barcode** en utilisant Aspose.BarCode. En ajustant la **barcode XDimension** et la **barcode BarHeight**, vous obtenez un contrôle fin de la taille visuelle sans sacrifier la fiabilité du scan.

## Et après ?

- Expérimentez d'autres paramètres de **GS1 DataBar Omni-Directional** comme `Color` ou `Margin`.  
- Combinez plusieurs codes‑barres sur une même toile en utilisant `Graphics` pour des conceptions d'étiquettes complexes.  
- Intégrez le générateur dans une API web afin que votre plateforme e‑commerce puisse générer des codes‑barres à la demande.

Vous avez une variante à partager ? Laissez un commentaire, et continuons la discussion. Bon codage !

## Que devriez‑vous apprendre ensuite ?

Les tutoriels suivants couvrent des sujets étroitement liés qui s'appuient sur les techniques démontrées dans ce guide. Chaque ressource comprend des exemples de code complets avec des explications étape par étape pour vous aider à maîtriser des fonctionnalités supplémentaires de l'API et explorer des approches d'implémentation alternatives dans vos propres projets.

- [Comment générer un code‑barres – Configuration Code 39 avec Aspose.BarCode](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-code-39-configuration/)
- [Comment créer une zone silencieuse de code‑barres pour ITF-14 avec Aspose.BarCode pour .NET](/barcode/english/net/itf-14-barcode-customization/itf-14-barcode-quiet-zone-configuration/)
- [Comment créer une zone silencieuse de code‑barres pour Code 16K avec Aspose.BarCode pour .NET](/barcode/english/net/code-16k-encoding/code-16k-quiet-zone-settings/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}