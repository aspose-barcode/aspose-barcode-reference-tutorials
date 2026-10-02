---
category: general
date: 2026-10-02
description: Créez rapidement un code‑barres stacked databars en C#. Apprenez à définir
  XDimension, à ajuster le rapport d’aspect et à exporter des images PNG avec un générateur
  de code‑barres.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create stacked databars barcode
- C# barcode generator
- DataBar stacked omnidirectional
- barcode aspect ratio
- XDimension pixel size
- BarCodeImageFormat PNG
language: fr
lastmod: 2026-10-02
og_description: Créez un code‑barres à barres de données empilées en C# avec un exemple
  complet de code. Ajustez la XDimension, modifiez le rapport d’aspect et enregistrez
  les fichiers PNG en quelques lignes seulement.
og_image_alt: Screenshot showing a create stacked databars barcode example generated
  with C#
og_title: Créer un code-barres à barres de données empilées en C# – tutoriel rapide
schemas:
- author: Aspose
  dateModified: '2026-10-02'
  description: Create stacked databars barcode in C# quickly. Learn to set XDimension,
    adjust aspect ratio, and export PNG images with a barcode generator.
  headline: Create stacked databars barcode in C# – step‑by‑step guide
  type: TechArticle
tags:
- barcode
- C#
- DataBar
- Aspose
- image generation
title: Créer un code‑barres à barres de données empilées en C# – guide étape par étape
url: /fr/python-java/general/create-stacked-databars-barcode-in-c-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Créer un code‑barres DataBar empilé en C# – guide étape par étape

Si vous devez **créer un code‑barres DataBar empilé** dans un projet .NET, ce tutoriel vous montre exactement comment procéder. Vous verrez comment configurer la X‑dimension, changer les rapports d’aspect, et enregistrer le résultat sous forme de fichiers PNG — le tout avec la bibliothèque Aspose.BarCode.

Générer un code‑barres DataBar empilé ne nécessite pas de pipeline graphique complexe. À la fin de ce guide, vous disposerez de deux images PNG prêtes à l’emploi illustrant différents rapports d’aspect, et vous comprendrez pourquoi ces paramètres sont importants pour la fiabilité du scan.

## Ce dont vous avez besoin

- .NET 6.0 ou ultérieur (le code fonctionne également avec .NET Framework 4.6+)
- Visual Studio 2022 ou tout IDE C#
- **Aspose.BarCode for .NET** package NuGet  
  ```bash
  dotnet add package Aspose.BarCode
  ```
- Permission d’écriture sur le dossier où les fichiers PNG seront enregistrés

## Étape 1 : Configurer le projet et importer les espaces de noms

Créez une nouvelle application console (ou ajoutez le code à un projet existant) et importez les espaces de noms requis :

```csharp
using System;
using Aspose.BarCode.Generation;   // BarcodeGenerator lives here
using Aspose.BarCode;               // BarCodeImageFormat enum
```

> **Pourquoi c’est important :** `Aspose.BarCode.Generation` fournit la classe `BarcodeGenerator`, tandis que `Aspose.BarCode` contient l’énumération `BarCodeImageFormat` utilisée pour enregistrer les images.

## Étape 2 : Initialiser le générateur pour un DataBar omnidirectionnel empilé

La valeur `EncodeTypes.DatabarStackedOmniDirectional` sélectionne la symbologie DataBar empilée. La chaîne de données doit suivre le format GS1 Application Identifier (AI) ; ici nous utilisons une valeur GTIN‑14 factice.

```csharp
// Initialise a generator for a stacked omnidirectional DataBar barcode
var barcodeGen = new BarcodeGenerator(
    EncodeTypes.DatabarStackedOmniDirectional,
    "(01)12345678901231");
```

> **Pourquoi c’est important :** Le type d’encodage choisi indique à la bibliothèque de rendre un code‑barres *empilé*, ce qui est essentiel pour les étiquettes à haute densité où l’espace vertical est limité.

## Étape 3 : Définir la taille du module (X‑dimension) en pixels

La X‑dimension contrôle la largeur de la plus petite barre (le « module »). Une valeur de 2 pixels fonctionne bien pour la plupart des sorties à résolution d’écran.

```csharp
// Set the X‑dimension to 2 pixels (module width)
barcodeGen.Parameters.Barcode.XDimension.Pixels = 2;
```

> **Pourquoi c’est important :** Les scanners interprètent la largeur du module comme l’unité de mesure de base. Une valeur trop petite peut entraîner des impressions floues ; une valeur trop grande gaspille de l’espace.

## Étape 4 : Enregistrer la première image avec un rapport d’aspect de 15

La propriété `AspectRatio` influence la relation hauteur‑largeur de chaque segment empilé. Un rapport d’aspect de 15 est une valeur par défaut courante pour les applications de vente au détail.

```csharp
// Apply aspect ratio 15 and save the first PNG
barcodeGen.Parameters.Barcode.DataBar.AspectRatio = 15;
barcodeGen.Save("DatabarAspectRatio15.png", BarCodeImageFormat.Png);
```

> **Pourquoi c’est important :** Un rapport d’aspect plus faible produit un code‑barres plus plat, ce qui peut être plus facile à scanner sur certains matériaux d’étiquette. Le format PNG préserve une qualité sans perte pour les tests.

## Étape 5 : Modifier le rapport d’aspect à 30 et enregistrer la deuxième image

Augmenter le rapport d’aspect rend chaque segment empilé plus haut, ce qui peut améliorer la fiabilité du scan sur des fonds à faible contraste.

```csharp
// Apply aspect ratio 30 and save the second PNG
barcodeGen.Parameters.Barcode.DataBar.AspectRatio = 30;
barcodeGen.Save("DatabarAspectRatio30.png", BarCodeImageFormat.Png);
```

> **Pourquoi c’est important :** Différents détaillants ou partenaires logistiques peuvent exiger des dimensions de code‑barres spécifiques. Fournir les deux versions vous permet de comparer rapidement les performances de scan.

## Exemple complet, exécutable

Voici le programme complet que vous pouvez copier‑coller dans `Program.cs`. Il se compile et s’exécute sans modification après l’installation du package NuGet Aspose.BarCode.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

namespace StackedDataBarDemo
{
    class Program
    {
        static void Main()
        {
            // 1️⃣ Initialise the generator for stacked omnidirectional DataBar
            var barcodeGen = new BarcodeGenerator(
                EncodeTypes.DatabarStackedOmniDirectional,
                "(01)12345678901231");

            // 2️⃣ Define the module (X‑dimension) size in pixels
            barcodeGen.Parameters.Barcode.XDimension.Pixels = 2;

            // 3️⃣ Save first image with aspect ratio 15
            barcodeGen.Parameters.Barcode.DataBar.AspectRatio = 15;
            barcodeGen.Save("DatabarAspectRatio15.png", BarCodeImageFormat.Png);
            Console.WriteLine("Saved DatabarAspectRatio15.png");

            // 4️⃣ Save second image with aspect ratio 30
            barcodeGen.Parameters.Barcode.DataBar.AspectRatio = 30;
            barcodeGen.Save("DatabarAspectRatio30.png", BarCodeImageFormat.Png);
            Console.WriteLine("Saved DatabarAspectRatio30.png");
        }
    }
}
```

### Résultat attendu

L’exécution du programme crée deux fichiers dans le dossier d’exécution :

| Nom du fichier                | Rapport d’aspect | Description visuelle |
|-------------------------------|------------------|----------------------|
| `DatabarAspectRatio15.png`    | 15               | Code‑barres empilé plus court et plus plat |
| `DatabarAspectRatio30.png`    | 30               | Code‑barres empilé plus haut et plus allongé |

Vous pouvez ouvrir les fichiers PNG avec n’importe quel visualiseur d’images pour vérifier que le code‑barres est rendu correctement.

![Exemple de création de code‑barres DataBar empilé](placeholder-image.png){alt="Exemple de création de code‑barres DataBar empilé"}

## Questions fréquentes et cas particuliers

| Question | Réponse |
|----------|--------|
| **Puis‑je utiliser une X‑dimension différente ?** | Oui. Les valeurs typiques vont de 1 à 4 pixels. Des valeurs plus grandes augmentent la taille du code‑barres mais peuvent améliorer la lisibilité sur des imprimantes basse résolution. |
| **Et si j’ai besoin d’une symbologie différente ?** | Remplacez `EncodeTypes.DatabarStackedOmniDirectional` par une autre valeur `EncodeTypes`, comme `DatabarStacked` (non omnidirectionnel) ou `DatabarLimited`. |
| **Comment changer le format de sortie ?** | Utilisez `BarCodeImageFormat.Jpeg`, `Gif` ou `Bmp` dans l’appel `Save`. |
| **Le format GTIN‑14 est‑il obligatoire ?** | La symbologie DataBar attend une chaîne numérique préfixée d’un AI approprié (par ex., `(01)` pour GTIN‑14). Adaptez les données à votre cas d’utilisation. |
| **Qu’en est‑il des paramètres DPI ?** | Le générateur respecte la propriété `Resolution`. Pour des impressions haute résolution, définissez `barcodeGen.Parameters.ImageResolution.DpiX` et `DpiY` en conséquence. |

## Astuces professionnelles

- **Génération par lots :** Encapsulez la logique d’enregistrement dans une boucle et alimentez‑la avec une liste de GTIN pour produire des milliers de codes‑barres automatiquement.
- **Validation :** Utilisez `barcodeGen.Validate()` avant d’enregistrer pour détecter tôt les données mal formées.
- **Performance :** Réutiliser la même instance `BarcodeGenerator` (en ne changeant que les paramètres) est plus rapide que de créer un nouvel objet pour chaque image.

## Prochaines étapes

Maintenant que vous pouvez **créer un code‑barres DataBar empilé** avec des rapports d’aspect personnalisés, envisagez d’explorer :

- Ajouter du texte lisible par l’homme sous le code‑barres (`barcodeGen.Parameters.Barcode.CodeText`).
- Exporter en **PDF** pour des feuilles d’étiquettes imprimables (`BarCodeImageFormat.Pdf`).
- Intégrer le générateur dans une API web pour fournir des codes‑barres à la demande.
- Expérimenter avec d’autres **mots‑clés secondaires** tels que *générateur de code‑barres C#* et *rapport d’aspect du code‑barres* afin d’ajuster votre implémentation pour du matériel spécifique.

Bon codage, et profitez de la flexibilité qu’Aspose.BarCode apporte à vos projets de code‑barres C# !

## Que devriez‑vous apprendre ensuite ?

Les tutoriels suivants couvrent des sujets étroitement liés qui s’appuient sur les techniques démontrées dans ce guide. Chaque ressource comprend des exemples de code complets avec des explications étape par étape pour vous aider à maîtriser des fonctionnalités supplémentaires de l’API et explorer des approches d’implémentation alternatives dans vos propres projets.

- [Créer un code‑barres DataBar empilé en C# – guide étape par étape](/barcode/english/python-java/general/create-databar-stacked-barcode-in-c-step-by-step-guide/)
- [Code‑barres DataBar empilé omnidirectionnel en C# – Guide complet](/barcode/english/python-java/general/databar-stacked-omnidirectional-barcode-in-c-complete-guide/)
- [Comment créer des images PNG DataBar avec C# et Aspose.BarCode](/barcode/english/python-java/general/how-to-create-databar-png-images-with-c-and-aspose-barcode/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}