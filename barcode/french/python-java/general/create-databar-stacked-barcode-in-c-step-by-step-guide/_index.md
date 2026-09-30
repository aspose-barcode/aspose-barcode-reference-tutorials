---
category: general
date: 2026-08-06
description: Créez rapidement un code‑barres DataBar empilé en C#. Apprenez à définir
  la dimension X, à ajuster le rapport d’aspect et à exporter des fichiers PNG à l’aide
  du générateur DataBar Stacked Omnidirectional.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create databar stacked barcode
- DataBar Stacked Omnidirectional
- barcode aspect ratio
- BarcodeGenerator C#
- BarCodeImageFormat PNG
language: fr
lastmod: 2026-08-06
og_description: Créez un code‑barres Databar empilé en C# avec Aspose.BarCode. Ce
  tutoriel montre comment configurer la dimension X, modifier le rapport d’aspect
  et enregistrer des images PNG.
og_image_alt: Screenshot of two PNG files generated from a DataBar Stacked Omnidirectional
  barcode with different aspect ratios
og_title: Créer un code‑barres Databar empilé en C# – guide complet de programmation
schemas:
- author: Aspose
  dateModified: '2026-08-06'
  description: Create databar stacked barcode in C# quickly. Learn to set X dimension,
    adjust aspect ratio, and export PNG files using the DataBar Stacked Omnidirectional
    generator.
  headline: Create databar stacked barcode in C# – step‑by‑step guide
  type: TechArticle
tags:
- barcode
- C#
- Aspose.BarCode
title: Créer un code‑barres Databar empilé en C# – guide étape par étape
url: /fr/python-java/general/create-databar-stacked-barcode-in-c-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Créer un databar stacked barcode en C# – guide étape par étape

Si vous devez **créer des images de databar stacked barcode** en C#, ce guide vous montre exactement comment le faire en utilisant la bibliothèque Aspose.BarCode. Vous apprendrez à définir la dimension X, à modifier le ratio d’aspect du code‑barres et à enregistrer le résultat au format PNG — le tout en quelques étapes concises.

Générer un DataBar Stacked barcode est courant lorsque vous devez encoder des données GS1‑128 pour la lecture en magasin ou le suivi logistique. Dans les sections suivantes, nous couvrons tout, de la configuration du projet à la vérification du résultat, afin que vous puissiez intégrer la solution dans n’importe quelle application .NET sans rien manquer.

## Prérequis

* **.NET 6.0** (ou version ultérieure) installé – le code cible le SDK moderne.
* Une copie **licenciée** de **Aspose.BarCode for .NET**. L’évaluation gratuite fonctionne pour les tests mais ajoute un filigrane.
* Un IDE tel que **Visual Studio 2022** ou **VS Code** avec l’extension C#.
* Une connaissance de base de la syntaxe **C#** et du concept d’identifiants d’application GS1.

> **Astuce :** Si vous utilisez le gestionnaire de paquets NuGet, la commande `dotnet add package Aspose.BarCode` résout automatiquement toutes les dépendances.

## Étape 1 : Créer un nouveau projet console

Ouvrez un terminal ou la console du gestionnaire de paquets et exécutez :

```bash
dotnet new console -n DatabarStackedDemo
cd DatabarStackedDemo
dotnet add package Aspose.BarCode
```

La commande `dotnet new console` crée un fichier **Program.cs** minimal. L’ajout du package **Aspose.BarCode** rend la classe `BarcodeGenerator` disponible.

## Étape 2 : Initialiser le générateur DataBar Stacked Omnidirectional

Ouvrez **Program.cs** et remplacez le contenu par défaut par le code suivant. La première ligne crée un **BarcodeGenerator** configuré pour la symbologie **DataBar Stacked Omnidirectional** et fournit une charge utile GS1‑128.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Step 2: Initialize the generator for a DataBar Stacked Omnidirectional barcode
        // "(01)12345678901231" encodes a GTIN‑14 with Application Identifier (01)
        var generator = new BarcodeGenerator(
            EncodeTypes.DatabarStackedOmniDirectional,
            "(01)12345678901231");

        // Continue with configuration...
```

**Pourquoi c’est important :** La valeur d’énumération `EncodeTypes.DatabarStackedOmniDirectional` indique à la bibliothèque de produire un **databar stacked barcode**, qui est la variante empilée de la famille DataBar omnidirectionnelle. Cette symbologie peut contenir jusqu’à 14 caractères numériques, ce qui la rend idéale pour les codes GTIN‑14.

## Étape 3 : Définir la dimension X (largeur du module)

La dimension X contrôle la largeur de la plus petite barre (le module). Une valeur trop petite peut rendre le code de mauvaise qualité sur des imprimantes basse résolution, tandis qu’une valeur trop grande peut dépasser l’espace disponible sur l’étiquette.

```csharp
        // Step 3: Define the module width – 2 pixels gives a crisp, printable barcode
        generator.Parameters.Barcode.XDimension.Pixels = 2;
```

> **Conseil :** La propriété `Pixels` est pratique pour les tests sur écran. Pour les scénarios d’impression, utilisez plutôt `generator.Parameters.Barcode.XDimension.Millimeters`.

## Étape 4 : Ajuster le ratio d’aspect et enregistrer la première image

Le **ratio d’aspect** influence la relation hauteur‑largeur du code‑barres empilé. Le type DataBar Stacked Omnidirectional prend en charge des ratios de 10 à 30. Nous générerons deux images pour illustrer l’impact visuel.

```csharp
        // Step 4a: Set aspect ratio to 15 (default is 15) and save as PNG
        generator.Parameters.Barcode.DataBar.AspectRatio = 15;
        generator.Save("DatabarAspectRatio15.png", BarCodeImageFormat.Png);
```

L’appel à `generator.Save` écrit un fichier **PNG** dans le répertoire de travail actuel. L’énumération `BarCodeImageFormat.Png` garantit une compression sans perte, idéale pour un traitement ultérieur ou l’intégration dans des PDF.

## Étape 5 : Modifier le ratio d’aspect à 30 et enregistrer la deuxième image

Nous augmentons maintenant la hauteur des barres empilées en changeant le ratio d’aspect à **30**. Cela rend le code‑barres plus haut sans modifier la dimension X.

```csharp
        // Step 5a: Increase aspect ratio to 30 for a taller barcode
        generator.Parameters.Barcode.DataBar.AspectRatio = 30;
        generator.Save("DatabarAspectRatio30.png", BarCodeImageFormat.Png);

        Console.WriteLine("Two barcode images have been generated:");
        Console.WriteLine(" • DatabarAspectRatio15.png");
        Console.WriteLine(" • DatabarAspectRatio30.png");
    }
}
```

L’exécution du programme génère maintenant deux fichiers PNG :

* **DatabarAspectRatio15.png** – un code‑barres compact adapté aux petites étiquettes.
* **DatabarAspectRatio30.png** – un code‑barres plus haut qui améliore la fiabilité de la lecture sur des surfaces à faible contraste.

Vous pouvez ouvrir les images avec n’importe quel visualiseur pour vérifier que les barres sont correctement empilées et que les données encodées correspondent à la chaîne GS1 d’origine.

## Étape 6 : Vérifier la valeur encodée (facultatif)

Si vous devez confirmer que le code‑barres représente réellement la chaîne d’entrée, vous pouvez le décoder avec la même bibliothèque :

```csharp
        // Optional: Decode the generated PNG to ensure correctness
        var decoder = new BarCodeReader("DatabarAspectRatio15.png", DecodeType.DatabarStackedOmniDirectional);
        foreach (BarCodeResult result in decoder.ReadBarCodes())
        {
            Console.WriteLine($"Decoded text: {result.CodeText}");
        }
```

Le décodeur devrait renvoyer `(01)12345678901231`, prouvant que le processus de **création d’un databar stacked barcode** a conservé les données.

## Pièges courants et comment les éviter

| Problème | Cause | Solution |
|----------|-------|----------|
| Le code‑barres apparaît flou | Dimension X trop faible pour la résolution de sortie | Augmenter `XDimension.Pixels` ou utiliser `Millimeters` pour l’impression |
| Le scanner signale « symbole non trouvé » | Ratio d’aspect en dehors de la plage prise en charge de 10‑30 | Conserver le ratio entre 10 et 30 ; 15 et 30 sont des valeurs sûres |
| Le PNG contient un filigrane | Utilisation de la licence d’évaluation gratuite d’Aspose.BarCode | Acheter une licence complète ou n’utiliser l’essai que pour les tests |
| Le décodage échoue sur la deuxième image | Le décodeur était configuré pour la mauvaise symbologie | Utiliser `DecodeType.DatabarStackedOmniDirectional` lors de la lecture des codes‑barres empilés |

## Prochaines étapes

Maintenant que vous pouvez **créer des images de databar stacked barcode**, vous pourriez vouloir :

* **Intégrer les PNG dans des factures PDF** à l’aide d’une bibliothèque PDF telle que **Aspose.PDF**.
* **Générer des codes‑barres à la volée dans une API web** – renvoyer les octets PNG directement depuis un contrôleur ASP.NET Core.
* **Expérimenter d’autres variantes DataBar** (par ex., `DatabarExpanded`, `DatabarLimited`) en modifiant l’énumération `EncodeTypes`.
* **Ajuster les couleurs** en définissant `generator.Parameters.Barcode.ForeColor` et `BackColor` pour des designs spécifiques à la marque.

Chaque sujet s’appuie sur les mêmes concepts de base présentés ici : initialiser `BarcodeGenerator`, configurer les paramètres visuels et enregistrer le résultat avec `BarCodeImageFormat`.

---

### Conclusion

Ce tutoriel a démontré comment **créer des images de databar stacked barcode** en C# en utilisant Aspose.BarCode. Vous avez appris à définir la **dimension X**, à modifier le **ratio d’aspect du code‑barres**, et à exporter le résultat sous forme de fichiers **PNG** avec `BarcodeGenerator`. Avec l’étape de décodage optionnelle, vous pouvez également vérifier que les données GS1 encodées sont exactes. Appliquez ces modèles à vos propres applications d’inventaire, d’expédition ou de point de vente, et explorez les nombreuses options de personnalisation offertes par la bibliothèque. Bon codage !

## Que devriez‑vous apprendre ensuite ?

Les tutoriels suivants couvrent des sujets étroitement liés qui s’appuient sur les techniques démontrées dans ce guide. Chaque ressource comprend des exemples de code complets avec des explications étape par étape pour vous aider à maîtriser des fonctionnalités supplémentaires de l’API et à explorer des approches d’implémentation alternatives dans vos propres projets.

- [Ajustement de la hauteur du code‑barres Databar unidimensionnel](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-barcode-height-adjustment/)
- [Générer une image de code‑barres – Coupon GS1 UPC‑A Databar](/barcode/english/net/gs1-barcode-encoding/gs1-coupon-upc-a-databar-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}