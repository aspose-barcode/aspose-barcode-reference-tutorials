---
category: general
date: 2026-07-18
description: Exemple de générateur de codes‑barres montrant comment définir les dimensions
  et générer une image de code‑barres DataBar Stacked Omni‑Directional en C#. Apprenez
  rapidement les types d’encodage de codes‑barres.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- barcode generator example
- how to set dimensions
- how to generate databar
- barcode encode types
- create barcode image c#
language: fr
lastmod: 2026-07-18
og_description: L'exemple de générateur de codes‑barres vous montre comment définir
  les dimensions, choisir les types d’encodage et créer des projets d’images de codes‑barres
  en C# avec un code minimal.
og_image_alt: Barcode generator example output showing DataBar barcode with aspect
  ratio 15
og_title: Exemple de générateur de code‑barres – Création rapide d’image DataBar en
  C#
schemas:
- author: Aspose
  dateModified: '2026-07-18'
  description: Barcode generator example showing how to set dimensions and generate
    a DataBar Stacked Omni‑Directional barcode image in C#. Learn barcode encode types
    quickly.
  headline: Barcode Generator Example – Build DataBar Image in C#
  type: TechArticle
tags:
- barcode
- C#
- Aspose
- image generation
title: Exemple de générateur de code-barres – Créez une image DataBar en C#
url: /fr/python-java/general/barcode-generator-example-build-databar-image-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Exemple de générateur de code‑barres – Créer une image DataBar en C#

Vous avez déjà eu besoin d’un **exemple de générateur de code‑barres** qui crée réellement un code‑barres utilisable sans vous arracher les cheveux ? Vous n’êtes pas seul. La plupart des développeurs se heurtent à un mur lorsqu’ils essaient de déterminer **comment définir les dimensions** d’un code‑barres DataBar Stacked Omni‑Directional, surtout quand la documentation est enfouie sous des couches de jargon.

Dans ce tutoriel, nous allons parcourir un programme C# complet, prêt à l’exécution, qui montre **comment générer des images databar**, sélectionne les bons **types d’encodage de code‑barres**, et enfin **crée des fichiers image de code‑barres c#** que vous pouvez intégrer à n’importe quel projet. Pas de blabla—juste le code à copier‑coller, plus le raisonnement derrière chaque ligne.

## Ce dont vous avez besoin

- **.NET 6** (ou toute version récente de .NET) – l’API que nous utilisons cible .NET Standard, elle fonctionne donc aussi sur .NET Framework.  
- **Aspose.BarCode for .NET** – la bibliothèque qui fournit `BarcodeGenerator`. Vous pouvez l’obtenir via NuGet avec `Install-Package Aspose.BarCode`.  
- Un **IDE C#** – Visual Studio, Rider ou VS Code feront l’affaire.  
- Un dossier sur le disque où les fichiers PNG seront enregistrés (le code crée `DatabarAspectRatio15.png` et `DatabarAspectRatio30.png`).

Tout est‑t‑il prêt ? Parfait—plongeons‑y.

## Exemple de générateur de code‑barres – Initialiser le générateur

Première étape : nous avons besoin d’une instance de `BarcodeGenerator` configurée pour la symbologie **DataBar Stacked Omni‑Directional**. C’est le **type d’encodage de code‑barres** avec lequel nous allons travailler.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Program
{
    static void Main()
    {
        // Step 1: Create a DataBar Stacked Omni‑Directional barcode generator
        // with the desired GTIN content.
        var generator = new BarcodeGenerator(
            EncodeTypes.DatabarStackedOmniDirectional,
            "(01)12345678901231");   // GTIN‑14 example
```

> **Pourquoi c’est important :** `EncodeTypes.DatabarStackedOmniDirectional` indique à Aspose exactement quelle symbologie rendre. Si vous choisissez le mauvais type, le lecteur ne reconnaîtra pas le code‑barres, aussi joli soit l’image.

## Comment définir les dimensions du code‑barres

La lisibilité d’un code‑barres dépend de son **X‑dimension** (la largeur de la barre la plus étroite). Dans la plupart des cas, une valeur de 2 pixels suffit, mais vous pouvez l’ajuster selon votre imprimante ou votre écran.

```csharp
        // Step 2: Set a common X‑dimension (pixel width of the narrowest bar)
        generator.Parameters.Barcode.XDimension.Pixels = 2;
```

> **Astuce pro :** Si vous vous demandez **comment définir les dimensions** pour une autre famille de codes‑barres, la même chaîne de propriétés (`Parameters.Barcode.XDimension`) s’applique—il suffit de changer la valeur `Pixels`.

## Comment générer un code‑barres DataBar Stacked Omni‑Directional

Maintenant que le générateur est prêt, nous allons jouer avec la propriété **aspect ratio**. Celle‑ci contrôle la relation hauteur‑largeur du DataBar, vous permettant de produire un symbole court et carré ou un symbole haut et étroit.

```csharp
        // Step 3: Generate and save a barcode with aspect ratio 15
        generator.Parameters.Barcode.DataBar.AspectRatio = 15;
        generator.Save("DatabarAspectRatio15.png", BarCodeImageFormat.Png);
```

> **Que se passe‑t‑il ?** `AspectRatio = 15` indique au moteur de rendre les barres 15 fois plus hautes qu’elles ne sont larges. Le PNG résultant est enregistré juste à côté de votre exécutable.

## Créer une image de code‑barres C# – Modifier le rapport d’aspect

Prouvons la flexibilité en changeant le ratio à 30 et en enregistrant un deuxième fichier.

```csharp
        // Step 4: Change the aspect ratio to 30 and save another barcode
        generator.Parameters.Barcode.DataBar.AspectRatio = 30;
        generator.Save("DatabarAspectRatio30.png", BarCodeImageFormat.Png);

        Console.WriteLine("Two barcode images have been saved successfully.");
    }
}
```

Lorsque vous exécuterez le programme, vous obtiendrez deux fichiers PNG :

| Fichier | Rapport d’aspect | Taille approximative |
|------|--------------|--------------|
| `DatabarAspectRatio15.png` | 15 | 120 × 180 px |
| `DatabarAspectRatio30.png` | 30 | 120 × 360 px |

Ouvrez‑les avec n’importe quel visualiseur d’images — vous devriez voir des symboles DataBar propres et lisibles.

## Aperçu des types d’encodage de code‑barres (Optionnel mais pratique)

Si vous êtes curieux des autres **types d’encodage de code‑barres** pris en charge par Aspose, voici une petite feuille de référence :

| Enum EncodeTypes | Description |
|------------------|-------------|
| `EncodeTypes.Code128` | Alphanumérique haute densité |
| `EncodeTypes.QR` | Code matriciel 2‑D |
| `EncodeTypes.DatabarExpanded` | GS1 DataBar pour le commerce de détail |
| `EncodeTypes.DatabarStackedOmniDirectional` | **Notre focus** – compact, omnidirectionnel |

Connaître le bon enum vous évite de nombreux essais‑erreurs lorsque vous changez de projet.

## Pièges courants & comment les éviter

- **Package NuGet manquant** – Le code ne compilera pas sans `Aspose.BarCode`. Exécutez d’abord `dotnet add package Aspose.BarCode`.  
- **Chemin de fichier incorrect** – Si vous utilisez un chemin absolu, vérifiez les antislashs (`\\`) sous Windows. Les chemins relatifs (comme indiqué) restent portables.  
- **Rapport d’aspect trop extrême** – Des ratios supérieurs à 50 peuvent rendre le code‑barres trop haut pour les lecteurs classiques. Restez entre 15 et 30 pour la plupart des cas d’usage.

## Code source complet (prêt à copier‑coller)

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Program
{
    static void Main()
    {
        // 1️⃣ Initialize generator with DataBar Stacked Omni‑Directional type
        var generator = new BarcodeGenerator(
            EncodeTypes.DatabarStackedOmniDirectional,
            "(01)12345678901231"); // GTIN‑14 sample

        // 2️⃣ Set X‑dimension (how to set dimensions) – 2 pixels is a safe default
        generator.Parameters.Barcode.XDimension.Pixels = 2;

        // 3️⃣ First barcode: aspect ratio 15
        generator.Parameters.Barcode.DataBar.AspectRatio = 15;
        generator.Save("DatabarAspectRatio15.png", BarCodeImageFormat.Png);

        // 4️⃣ Second barcode: aspect ratio 30
        generator.Parameters.Barcode.DataBar.AspectRatio = 30;
        generator.Save("DatabarAspectRatio30.png", BarCodeImageFormat.Png);

        Console.WriteLine("✅ Two barcode images saved – check your project folder.");
    }
}
```

Exécutez le programme (`dotnet run` ou appuyez sur **F5** dans Visual Studio) et vous verrez le message console confirmant que les fichiers sont bien sur le disque.

![Barcode generator example output showing DataBar barcode with aspect ratio 15](placeholder/path/to/image.png){: .align-center alt="Exemple de sortie du générateur de code‑barres montrant le DataBar avec un rapport d’aspect de 15"}

## Conclusion

Nous venons de terminer un **exemple de générateur de code‑barres** qui montre **comment définir les dimensions**, sélectionne les bons **types d’encodage de code‑barres**, et enfin **crée des fichiers image de code‑barres c#** que vous pouvez intégrer où vous le souhaitez. Le code est minuscule, les concepts sont limpides, et vous disposez maintenant d’une base solide pour étendre la solution—peut‑être en ajoutant des légendes, en faisant pivoter l’image, ou en passant à une autre symbologie.

### Et après ?

- Expérimentez avec **différentes X‑dimensions** pour observer comment la tolérance du lecteur varie.  
- Essayez d’autres **EncodeTypes** comme `Code128` ou `QR` pour élargir votre boîte à outils.  
- Automatisez la génération en lot : bouclez sur un CSV d’identifiants produit et créez un PNG pour chacun.

Si vous rencontrez un problème, laissez un commentaire ci‑dessous ou consultez la documentation Aspose.BarCode—elle regorge d’exemples qui complètent ce que nous avons vu ici.

Bon codage, et que vos codes‑barres soient toujours lus du premier coup !

## Que devriez‑vous apprendre ensuite ?

Les tutoriels suivants couvrent des sujets étroitement liés qui s’appuient sur les techniques démontrées dans ce guide. Chaque ressource inclut des exemples de code complets avec des explications pas à pas pour vous aider à maîtriser d’autres fonctionnalités de l’API et explorer des approches d’implémentation alternatives dans vos propres projets.

- [How to Generate Barcode - One-Dimensional Barcode Types](/barcode/english/net/one-dimensional-barcode-types/)
- [Create barcode image C# – GS1 DataMatrix Example](/barcode/english/net/gs1-barcode-encoding/gs1-datamatrix-example/)
- [How to Generate DataMatrix Barcodes (ECC 200) with Aspose.BarCode for .NET](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-ecc-200-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}