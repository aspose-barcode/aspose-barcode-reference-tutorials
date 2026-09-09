---
category: general
date: 2026-07-21
description: Tutoriel générateur de code-barres C# montrant comment définir des dimensions
  personnalisées du code-barres, ajuster la hauteur en pixels du code-barres et modifier
  rapidement la hauteur de l'image du code-barres.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- barcode generator c#
- custom barcode dimensions
- barcode pixel height
- barcode image height
- change barcode height
language: fr
lastmod: 2026-07-21
og_description: Le générateur de codes‑barres C# vous permet de contrôler chaque pixel.
  Apprenez à définir des dimensions personnalisées, à ajuster la hauteur des pixels
  du code‑barres et à modifier la hauteur du code‑barres sans effort.
og_image_alt: Screenshot of barcode generator c# output with custom dimensions
og_title: Générateur de code-barres C# – Maîtrisez les dimensions personnalisées en
  quelques minutes
schemas:
- author: Aspose
  dateModified: '2026-07-21'
  description: Barcode generator c# tutorial showing how to set custom barcode dimensions,
    adjust barcode pixel height, and change barcode image height quickly.
  headline: Barcode generator c# – Custom barcode dimensions guide
  type: TechArticle
- description: Barcode generator c# tutorial showing how to set custom barcode dimensions,
    adjust barcode pixel height, and change barcode image height quickly.
  name: Barcode generator c# – Custom barcode dimensions guide
  steps:
  - name: What if I need a different **barcode image height** than the default?
    text: 'You can control the overall canvas size via `GeneratorParameters.ImageHeight.Pixels`.
      For example:'
  - name: How does `XDimension` affect scanning reliability?
    text: A smaller `XDimension` creates thinner bars, which can look sharper but
      may be harder for low‑resolution scanners. As a rule of thumb, keep `XDimension`
      ≥ 2 px for 300 dpi printing and ≥ 3 px for 200 dpi.
  - name: Can I switch from PNG to another format without changing code?
    text: 'Absolutely. The `Save` method accepts `BarCodeImageFormat.Jpeg`, `Gif`,
      `Bmp`, etc. Just replace the enum value:'
  - name: What if I need to generate dozens of barcodes with varying heights?
    text: 'Wrap the height‑changing logic in a loop:'
  type: HowTo
tags:
- barcode
- C#
- imaging
title: Générateur de code-barres C# – Guide des dimensions personnalisées.
url: /fr/python-java/general/barcode-generator-c-custom-barcode-dimensions-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Générateur de code‑barres c# – Guide des dimensions personnalisées

Vous êtes-vous déjà demandé comment faire en sorte qu’un **barcode generator c#** produise exactement la taille dont vous avez besoin ? Vous n’êtes pas le seul. Que vous imprimiez des étiquettes produit sur le terrain ou que vous génériez des tags de type QR pour un système d’inventaire, obtenir les bonnes dimensions est crucial.

Dans ce tutoriel, nous parcourrons un exemple complet, prêt à l’emploi, qui vous montre comment définir des **dimensions de code‑barres personnalisées**, ajuster la **hauteur en pixels du code‑barres**, et enfin **modifier la hauteur du code‑barres** à la volée. Pas de références vagues — juste le code que vous pouvez copier, coller et exécuter dès aujourd’hui.

## Ce que vous allez apprendre

- Comment instancier un **barcode generator c#** pour la symbologie DataBar Omnidirectionnelle.  
- La différence entre la **hauteur en pixels du code‑barres** et la **hauteur globale de l’image du code‑barres**.  
- Deux méthodes pratiques pour **modifier la hauteur du code‑barres** sans recréer le générateur.  
- Astuces pour enregistrer l’image aux dimensions exactes dont vous avez besoin.

Vous avez seulement besoin d’un runtime .NET récent (4.7+ ou .NET 6) et de la bibliothèque Aspose.BarCode for .NET (ou toute API compatible). Si vous avez déjà cela, plongeons‑y.

## Étape 1 : Configurer le projet et importer la bibliothèque

Tout d’abord, créez une nouvelle application console (ou ajoutez le code à une existante). Puis ajoutez le package NuGet :

```bash
dotnet add package Aspose.BarCode
```

Importez maintenant les espaces de noms dont vous aurez besoin :

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;
using System.Drawing;   // only if you manipulate the bitmap later
```

> **Astuce :** Si vous utilisez Visual Studio, le gestionnaire NuGet s’occupera de la référence pour vous—aucune recherche manuelle de DLL n’est nécessaire.

## Étape 2 : Créer une instance de barcode generator c# avec un code DataBar Omnidirectionnel

La classe **barcode generator c#** est votre point d’entrée. Nous allons encoder une simple valeur GTIN‑14 :

```csharp
// Step 2: Initialize the generator with the desired symbology and data
BarcodeGenerator generator = new BarcodeGenerator(
    EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");
```

À ce stade, le générateur sait *quoi* encoder mais pas *quelle* taille doivent avoir les barres. C’est là que les **dimensions de code‑barres personnalisées** entrent en jeu.

## Étape 3 : Définir des dimensions personnalisées – se concentrer sur la hauteur en pixels du code‑barres

Deux propriétés contrôlent la taille verticale :

| Propriété | Ce qu'elle fait | Plage typique |
|-----------|----------------|---------------|
| `XDimension.Pixels` | Largeur d’une seule barre (le “module”) | 1‑5 px est courant |
| `BarHeight.Pixels` | Hauteur des barres elles‑mêmes | 30‑100 px selon le DPI d’impression |

Fixons une largeur modeste de 2 pixels et une **hauteur en pixels du code‑barres** de 30 px :

```csharp
// Step 3: Apply custom barcode dimensions
generator.Parameters.Barcode.XDimension.Pixels = 2;   // thin bars
generator.Parameters.Barcode.BarHeight.Pixels = 30; // 30‑pixel tall bars
```

Pourquoi 30 px ? Sur une imprimante 300 dpi, 30 px correspondent à environ 0,1 pouce—parfait pour la plupart des étiquettes de vente au détail. Augmentez si vous avez besoin d’un impact visuel plus important.

## Étape 4 : Enregistrer l’image du code‑barres avec la hauteur d’image souhaitée

Lorsque vous appelez `Save`, la bibliothèque ajoute automatiquement du remplissage pour accueillir la **hauteur de l’image du code‑barres** (la hauteur totale du bitmap). L’image finale sera plus haute que 30 px à cause des zones calmes et de toute légende que vous pourriez activer. Voici comment écrire le premier PNG :

```csharp
// Step 4: Export the first image (30‑pixel bar height)
string output30 = @"YOUR_DIRECTORY\DatabarBarHeight30Pixels.png";
generator.Save(output30, BarCodeImageFormat.Png);
Console.WriteLine($"Saved 30‑pixel barcode to {output30}");
```

Ouvrez le fichier résultant et vous verrez un DataBar net avec une **hauteur d’image du code‑barres** légèrement supérieure à 30 px—exactement ce que la plupart des scanners attendent.

## Étape 5 : Modifier la hauteur du code‑barres sans reconstruire le générateur

Modifier la hauteur des barres est aussi simple que d’ajuster une seule propriété. Pas besoin de recréer l’instance `BarcodeGenerator` :

```csharp
// Step 5: Increase the bar height to 60 pixels
generator.Parameters.Barcode.BarHeight.Pixels = 60;

// Save the second image
string output60 = @"YOUR_DIRECTORY\DatabarBarHeight60Pixels.png";
generator.Save(output60, BarCodeImageFormat.Png);
Console.WriteLine($"Saved 60‑pixel barcode to {output60}");
```

Notez que nous n’avons modifié que `BarHeight.Pixels`. Cela illustre la capacité à **modifier la hauteur du code‑barres**—rapide, peu gourmand en mémoire, et parfait pour le traitement par lots où chaque étiquette peut nécessiter une taille différente.

## Résultat attendu

L’exécution du programme complet génère deux fichiers PNG :

- `DatabarBarHeight30Pixels.png` – les barres mesurent 30 px, l’image globale environ 40 px de haut (zones calmes incluses).  
- `DatabarBarHeight60Pixels.png` – les barres mesurent 60 px, l’image globale environ 70 px de haut.

Les deux images contiennent les mêmes données encodées, donc tout scanner qui lit la première lira également la seconde sans modification de configuration.

## Code source complet – copiez, collez et exécutez

```csharp
// ------------------------------------------------------------
// Barcode generator c# – Custom dimensions demo
// ------------------------------------------------------------
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Program
{
    static void Main()
    {
        // 1️⃣ Initialize generator for DataBar Omnidirectional
        BarcodeGenerator generator = new BarcodeGenerator(
            EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");

        // 2️⃣ Set custom barcode dimensions (X‑dimension & bar height)
        generator.Parameters.Barcode.XDimension.Pixels = 2;   // thin bars
        generator.Parameters.Barcode.BarHeight.Pixels = 30; // 30‑pixel bars

        // 3️⃣ Save first image – demonstrates barcode pixel height = 30
        string path30 = @"YOUR_DIRECTORY\DatabarBarHeight30Pixels.png";
        generator.Save(path30, BarCodeImageFormat.Png);
        System.Console.WriteLine($"Saved 30‑pixel barcode to {path30}");

        // 4️⃣ Change barcode height – now 60 pixels
        generator.Parameters.Barcode.BarHeight.Pixels = 60;

        // 5️⃣ Save second image – demonstrates change barcode height
        string path60 = @"YOUR_DIRECTORY\DatabarBarHeight60Pixels.png";
        generator.Save(path60, BarCodeImageFormat.Png);
        System.Console.WriteLine($"Saved 60‑pixel barcode to {path60}");
    }
}
```

> **Remarque :** Remplacez `YOUR_DIRECTORY` par un chemin de dossier réel que votre application peut écrire. Sous Windows, quelque chose comme `@"C:\Temp"` fonctionne parfaitement.

## Questions fréquentes & gestion des cas particuliers

### Et si j’ai besoin d’une **hauteur d’image du code‑barres** différente de la valeur par défaut ?

Vous pouvez contrôler la taille globale du canevas via `GeneratorParameters.ImageHeight.Pixels`. Par exemple :

```csharp
generator.Parameters.ImageHeight.Pixels = 120; // forces total image height
```

C’est utile lorsque vous devez intégrer le code‑barres dans un modèle d’étiquette pré‑conçu.

### Comment `XDimension` influence‑t‑il la fiabilité du scan ?

Une `XDimension` plus petite crée des barres plus fines, ce qui peut paraître plus net mais être plus difficile à lire pour des scanners basse résolution. En règle générale, gardez `XDimension` ≥ 2 px pour une impression à 300 dpi et ≥ 3 px pour 200 dpi.

### Puis‑je passer de PNG à un autre format sans changer le code ?

Absolument. La méthode `Save` accepte `BarCodeImageFormat.Jpeg`, `Gif`, `Bmp`, etc. Il suffit de remplacer la valeur de l’énumération :

```csharp
generator.Save(@"path\barcode.jpg", BarCodeImageFormat.Jpeg);
```

### Et si je dois générer des dizaines de codes‑barres avec des hauteurs variables ?

Enveloppez la logique de modification de hauteur dans une boucle :

```csharp
int[] heights = {30, 45, 60, 75};
foreach (int h in heights)
{
    generator.Parameters.Barcode.BarHeight.Pixels = h;
    generator.Save($@"YOUR_DIRECTORY\BarHeight{h}.png", BarCodeImageFormat.Png);
}
```

Ainsi vous **modifiez la hauteur du code‑barres** de façon programmatique à chaque itération sans réinstancier le générateur.

## Récapitulatif

Nous venons de voir comment un **barcode generator c#** peut être réglé pour produire des **dimensions de code‑barres personnalisées**, manipuler la **hauteur en pixels du code‑barres**, et **modifier la hauteur du code‑barres** à la volée. L’exemple complet montre l’initialisation, les ajustements de propriétés, et deux sauvegardes illustrant la différence visuelle.

Prêt pour l’étape suivante ? Essayez de combiner ces réglages avec des légendes textuelles, des couleurs de fond, ou même d’intégrer le code‑barres dans un PDF à l’aide d’Aspose.PDF. Les mêmes principes s’appliquent—il suffit d’ajuster les paramètres pertinents.

Si ce guide vous a été utile, donnez‑lui une étoile sur GitHub, partagez‑le avec vos collègues, ou laissez un commentaire ci‑dessous avec vos propres expériences. Bon codage !

## Que devriez‑vous apprendre ensuite ?

Les tutoriels suivants couvrent des sujets étroitement liés qui s’appuient sur les techniques démontrées dans ce guide. Chaque ressource comprend des exemples de code complets avec des explications pas à pas pour vous aider à maîtriser d’autres fonctionnalités de l’API et explorer des approches d’implémentation alternatives dans vos propres projets.

- [Create Barcode Custom Height – One-Dimensional Barcodes](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-barcode-height-adjustment/)
- [One-Dimensional Databar Barcode Height Adjustment](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-barcode-height-adjustment/)
- [barcode generator tutorial c# – Customize Code 16K Barcode Aspect Ratios with Aspose.BarCode for .NET](/barcode/english/net/code-16k-encoding/code-16k-aspect-ratio-customization/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}