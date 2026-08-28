---
category: general
date: 2026-08-19
description: Créer des fichiers PNG databar en C# avec Aspose.BarCode. Apprenez à
  générer des images databar, à configurer les paramètres databar et à enregistrer
  la sortie PNG.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create databar png
- how to generate databar
- configure databar parameters
language: fr
lastmod: 2026-08-19
og_description: Créez des fichiers PNG de databar en C# avec Aspose.BarCode. Ce tutoriel
  vous guide pas à pas pour générer des images databar, configurer les paramètres
  du databar tels que la dimension X et le rapport d’aspect, et enregistrer des fichiers
  PNG de haute qualité pour l’impression ou l’utilisation Web.
og_image_alt: create databar PNG example
og_title: Créer des images PNG de databar en C# – guide étape par étape
schemas:
- author: Aspose
  dateModified: '2026-08-19'
  description: Create databar PNG files in C# with Aspose.BarCode. Learn how to generate
    databar images, configure databar parameters, and save PNG output.
  headline: How to create databar PNG images with C# and Aspose.BarCode
  type: TechArticle
tags:
- barcode
- databar
- C#
- PNG
- Aspose.BarCode
title: Comment créer des images PNG de databar avec C# et Aspose.BarCode
url: /fr/python-java/general/how-to-create-databar-png-images-with-c-and-aspose-barcode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Comment créer des images PNG databar avec C# et Aspose.BarCode

Si vous devez **créer des fichiers PNG databar** dans une application .NET, ce guide vous montre exactement comment procéder. Vous verrez un exemple complet et exécutable qui génère des codes DataBar empilés omnidirectionnels, configure les paramètres clés et enregistre deux fichiers PNG avec des rapports d’aspect différents.

Générer une image DataBar ne consiste pas seulement à appeler une seule méthode. Vous devez également **configurer les paramètres du databar** tels que la X‑dimension (largeur du module) et le rapport d’aspect afin de répondre aux spécifications d’impression ou de numérisation. À la fin de ce tutoriel, vous comprendrez **comment générer des graphiques databar** qui fonctionnent de manière fiable dans des scénarios réels.

## Prérequis

- .NET 6.0 ou version ultérieure (le code fonctionne également avec .NET Framework 4.7+)
- Visual Studio 2022 ou tout IDE compatible C#
- Une licence valide pour **Aspose.BarCode for .NET** (l’évaluation gratuite fonctionne pour les tests)
- Familiarité de base avec la syntaxe C#

> **Astuce :** Si vous n’avez pas encore de licence, vous pouvez demander une clé d’évaluation temporaire depuis le portail Aspose. L’API se comporte de la même façon ; seul le filigrane change.

## Étape 1 : Installer le package NuGet Aspose.BarCode

Ouvrez votre projet dans Visual Studio, faites un clic droit sur la solution et sélectionnez **Manage NuGet Packages**. Recherchez `Aspose.BarCode` et installez la dernière version stable.

```bash
dotnet add package Aspose.BarCode
```

Cette commande ajoute l’assembly `Aspose.BarCode` à votre projet et rend la classe `BarcodeGenerator` disponible.

## Étape 2 : Initialiser le générateur de code-barres pour un DataBar empilé omnidirectionnel

Le constructeur `BarcodeGenerator` reçoit deux arguments : le type de code-barres et la chaîne de données brutes. Pour un DataBar empilé omnidirectional, vous utilisez `EncodeTypes.DatabarStackedOmniDirectional`.

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;

namespace DatabarPngDemo
{
    class Program
    {
        static void Main(string[] args)
        {
            // Step 2: Initialize the generator with the desired DataBar type
            BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
                EncodeTypes.DatabarStackedOmniDirectional,
                "(01)12345678901231"); // GS1 Application Identifier for a 14‑digit GTIN
```

**Pourquoi c’est important :** La constante `EncodeTypes.DatabarStackedOmniDirectional` indique à la bibliothèque de produire un code-barres qui peut être lu sous n’importe quelle orientation, ce qui est idéal pour les étiquettes de rayonnage en magasin.

## Étape 3 : Configurer la X‑dimension (largeur du module) en pixels

La X‑dimension contrôle la taille du plus petit élément de barre. La définir en pixels vous donne un contrôle précis sur la taille finale de l’image.

```csharp
            // Step 3: Define the X‑dimension (module width) in pixels
            barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

Une valeur de **2 pixels** représente un bon compromis entre lisibilité et compacité pour la plupart des imprimantes d’étiquettes. Ajustez cette valeur si vous avez besoin de modules plus grands ou plus petits.

## Étape 4 : Définir le premier rapport d’aspect et enregistrer le PNG

Le rapport d’aspect influence la hauteur du DataBar empilé. Un rapport d’aspect de **15** produit un code-barres relativement court, tandis que **30** le rend plus haut.

```csharp
            // Step 4: Set an aspect ratio of 15 and save the image
            barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = 15;
            barcodeGenerator.Save("DatabarAspectRatio15.png", BarCodeImageFormat.Png);
```

La méthode `Save` écrit le code-barres généré dans un fichier PNG. Le PNG est sans perte, ce qui préserve les bords nets requis pour les lecteurs de codes-barres.

## Étape 5 : Modifier le rapport d’aspect et enregistrer un deuxième PNG

Vous pouvez réutiliser la même instance `BarcodeGenerator` pour produire des variantes simplement en modifiant le rapport d’aspect.

```csharp
            // Step 5: Change the aspect ratio to 30 and save a new image
            barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = 30;
            barcodeGenerator.Save("DatabarAspectRatio30.png", BarCodeImageFormat.Png);
        }
    }
}
```

Vous avez maintenant deux fichiers PNG — `DatabarAspectRatio15.png` et `DatabarAspectRatio30.png` — chacun avec une densité visuelle différente.

## Étape 6 : Vérifier la sortie

Ouvrez les fichiers PNG générés dans n’importe quel visualiseur d’images. Vous devriez voir un code-barres DataBar net et à fort contraste. Scanner les images avec un lecteur de code-barres sur smartphone confirme que les deux rapports d’aspect décodent la valeur GTIN originale `12345678901231`.

![create databar PNG example](databar_example.png)

*L’image ci‑dessus montre les deux fichiers PNG côte à côte. L’image de gauche utilise le rapport d’aspect 15, celle de droite utilise le rapport d’aspect 30.*

## Variations courantes et cas limites

| Scénario | Ce qu’il faut modifier | Raison |
|----------|------------------------|--------|
| **Données différentes** | Remplacez la chaîne `(01)12345678901231` par tout identifiant d’application GS1 valide et les données | Permet d’encoder des ID produit, numéros de série, etc. |
| **Résolution supérieure** | Augmentez `XDimension.Pixels` à 3 ou 4 | Nécessaire lorsque le code-barres sera imprimé en grande taille ou scanné à distance. |
| **Autres types de DataBar** | Utilisez `EncodeTypes.DatabarStacked` ou `EncodeTypes.DatabarExpanded` | Choisissez le type qui convient le mieux à la mise en page de votre étiquette. |
| **Fond transparent** | Passez `BarCodeImageFormat.Png` avec `barcodeGenerator.Save(..., BarCodeImageFormat.Png, new ImageOptions { BackgroundColor = Color.Transparent })` | Utile pour superposer le code-barres sur des étiquettes colorées. |

> **Attention :** Définir une X‑dimension trop petite (< 1 pixel) peut produire un code-barres qui apparaît flou après

## Que devriez‑vous apprendre ensuite ?

Les tutoriels suivants couvrent des sujets étroitement liés qui s’appuient sur les techniques démontrées dans ce guide. Chaque ressource comprend des exemples de code complets et fonctionnels avec des explications étape par étape pour vous aider à maîtriser des fonctionnalités supplémentaires de l’API et à explorer des approches d’implémentation alternatives dans vos propres projets.

- [Comment générer et ajuster la hauteur du code-barres pour Databar unidimensionnel avec Aspose.BarCode pour .NET](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-barcode-height-adjustment/)
- [Créer un encodage GS1 Databar unidimensionnel avec Aspose.BarCode](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-gs1-encoding/)
- [Générer un code-barres Databar Aspose.BarCode en utilisant l’API .NET – Configuration des lignes et colonnes](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-row-column-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}