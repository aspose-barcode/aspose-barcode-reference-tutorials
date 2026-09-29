---
category: general
date: 2026-09-29
description: Apprenez à créer un code‑barres Databar omnidirectionnel en C# avec Aspose.BarCode.
  Ajustez la dimension X, définissez le rapport d’aspect et enregistrez les images
  PNG.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create omnidirectional databar barcode
- DataBar stacked omnidirectional barcode
- set barcode aspect ratio
- Aspose.BarCode C#
- generate barcode image
language: fr
lastmod: 2026-09-29
og_description: Créez un code‑barres Databar omnidirectionnel en C# avec Aspose.BarCode.
  Apprenez à définir la dimension X, à ajuster le rapport d’aspect et à exporter des
  fichiers PNG.
og_image_alt: Screenshot showing two PNG files of an omnidirectional Databar barcode
  with different aspect ratios
og_title: Créer un code‑barres Databar omnidirectionnel en C# – guide étape par étape
schemas:
- author: Aspose
  dateModified: '2026-09-29'
  description: Learn how to create omnidirectional Databar barcode in C# with Aspose.BarCode.
    Adjust X‑dimension, set aspect ratio, and save PNG images.
  headline: How to create omnidirectional Databar barcode in C#
  type: TechArticle
- description: Learn how to create omnidirectional Databar barcode in C# with Aspose.BarCode.
    Adjust X‑dimension, set aspect ratio, and save PNG images.
  name: How to create omnidirectional Databar barcode in C#
  steps:
  - name: What if I need a different X‑dimension?
    text: You can assign any integer value to `XDimension.Pixels`. Values below `1`
      are ignored, and values above `10` may produce oversized modules that exceed
      printer margins. Test the visual output after each change.
  - name: How do I encode other AI‑generated data (e.g., UPC, EAN)?
    text: Replace the data string in the `BarcodeGenerator` constructor with the appropriate
      Application Identifier (AI). For a UPC‑A code, use `"012345678905"` without
      an AI prefix.
  - name: Can I export to formats other than PNG?
    text: Yes. The `Save` method accepts `BarCodeImageFormat.Jpeg`, `BarCodeImageFormat.Gif`,
      `BarCodeImageFormat.Tiff`, and `BarCodeImageFormat.Bmp`. Choose the format that
      matches your downstream workflow.
  type: HowTo
tags:
- barcode
- C#
- Aspose
title: Comment créer un code‑barres Databar omnidirectionnel en C#
url: /fr/python-java/general/how-to-create-omnidirectional-databar-barcode-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Comment créer un code-barres Databar omnidirectional en C#

Si vous devez **créer un code-barres Databar omnidirectional** dans une application .NET, ce guide vous montre les étapes exactes. Vous verrez comment initialiser un code-barres DataBar stacked omnidirectional, configurer sa X‑dimension, modifier le ratio d’aspect et générer des images PNG avec Aspose.BarCode.

Générer un **code-barres DataBar stacked omnidirectional** est courant lorsque vous devez encoder des identifiants de produit pour les scanners de vente au détail. Dans ce tutoriel, vous apprendrez à **définir le ratio d’aspect du code-barres**, contrôler la taille du module et exporter le résultat sans quitter l’IDE.

## Prérequis

Avant de commencer, assurez-vous d’avoir :

- .NET 6.0 ou version ultérieure installé
- Visual Studio 2022 (ou tout IDE compatible C#)
- Le package NuGet **Aspose.BarCode for .NET** (version 23.12 ou plus récente)

Vous pouvez ajouter le package via le Gestionnaire de packages NuGet :

```bash
dotnet add package Aspose.BarCode
```

## Étape 1 : Initialiser le code-barres Databar omnidirectional

La première étape consiste à créer une instance de `BarcodeGenerator` qui cible la symbologie **DataBar stacked omnidirectional**. Le constructeur reçoit le type d’encodage et la chaîne de données.

```csharp
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Initialise a DataBar stacked omnidirectional barcode with GTIN data
        var generator = new BarcodeGenerator(
            EncodeTypes.DatabarStackedOmniDirectional,
            "(01)12345678901231");
```

**Pourquoi c’est important :** La valeur `EncodeTypes.DatabarStackedOmniDirectional` indique à Aspose.BarCode de rendre le format Databar omnidirectional spécifique, nécessaire pour la lecture dans les deux sens.

## Étape 2 : Définir la X‑dimension (taille du module)

La X‑dimension contrôle la largeur d’un seul module du code-barres en pixels. Une valeur de `2` pixels convient bien pour le rendu à l’écran et la plupart des imprimantes.

```csharp
        // Set the basic size of the barcode modules (X‑dimension) in pixels
        generator.Parameters.Barcode.XDimension.Pixels = 2;
```

**Pourquoi c’est important :** Une X‑dimension constante garantit que le code-barres respecte les spécifications de taille minimale pour les scanners de vente au détail tout en maintenant une taille de fichier image raisonnable.

## Étape 3 : Définir le premier ratio d’aspect et enregistrer l’image

Le **ratio d’aspect** détermine la relation hauteur‑largeur du DataBar. Un ratio d’aspect de `15` produit un code-barres compact et haut, idéal pour les espaces d’étiquettes étroits.

```csharp
        // Apply aspect ratio 15 and save the first PNG
        generator.Parameters.Barcode.DataBar.AspectRatio = 15;
        generator.Save("DatabarAspectRatio15.png", BarCodeImageFormat.Png);
```

**Pourquoi c’est important :** Ajuster le ratio d’aspect vous permet d’adapter le code-barres à différentes mises en page d’étiquettes sans sacrifier la lisibilité. Le PNG enregistré peut être visualisé avec n’importe quel visualiseur d’images.

## Étape 4 : Modifier le ratio d’aspect et générer une seconde image

Parfois, un code-barres plus large est nécessaire—par exemple, lorsque l’étiquette dispose de plus d’espace horizontal. Modifier le ratio à `30` crée une apparence plus plate.

```csharp
        // Change aspect ratio to 30 and save a second PNG
        generator.Parameters.Barcode.DataBar.AspectRatio = 30;
        generator.Save("DatabarAspectRatio30.png", BarCodeImageFormat.Png);
    }
}
```

**Pourquoi c’est important :** En exposant la propriété **set barcode aspect ratio**, vous pouvez produire plusieurs variantes de code-barres à partir d’une même base de code, simplifiant les pipelines de génération d’étiquettes automatisées.

## Résultat attendu

L’exécution du programme génère deux fichiers PNG dans le dossier de sortie de l’application :

| Nom du fichier                | Ratio d’aspect | Description visuelle |
|-------------------------------|----------------|----------------------|
| `DatabarAspectRatio15.png`    | 15             | Code-barres haut et étroit adapté aux étiquettes étroites |
| `DatabarAspectRatio30.png`    | 30             | Code-barres plus large qui occupe plus d’espace horizontal |

![Exemple de création de code-barres Databar omnidirectional](databar-example.png "Exemple de création de code-barres Databar omnidirectional")

*La capture d’écran montre les deux fichiers PNG générés côte à côte.*

## Questions fréquentes et cas particuliers

### Et si j’ai besoin d’une X‑dimension différente ?

Vous pouvez attribuer n’importe quelle valeur entière à `XDimension.Pixels`. Les valeurs inférieures à `1` sont ignorées, et les valeurs supérieures à `10` peuvent produire des modules surdimensionnés qui dépassent les marges de l’imprimante. Testez le rendu visuel après chaque modification.

### Comment encoder d’autres données générées par AI (par ex., UPC, EAN) ?

Remplacez la chaîne de données dans le constructeur `BarcodeGenerator` par l’Identifiant d’Application (AI) approprié. Pour un code UPC‑A, utilisez `"012345678905"` sans préfixe AI.

### Puis-je exporter vers d’autres formats que PNG ?

Oui. La méthode `Save` accepte `BarCodeImageFormat.Jpeg`, `BarCodeImageFormat.Gif`, `BarCodeImageFormat.Tiff` et `BarCodeImageFormat.Bmp`. Choisissez le format qui correspond à votre flux de travail en aval.

## Astuce pro : réutiliser le générateur pour le traitement par lots

Si vous devez générer des dizaines de codes-barres avec des ratios d’aspect variables, conservez l’instance `BarcodeGenerator` en vie et ne modifiez que `DataBar.AspectRatio` avant chaque `Save`. Cela évite le surcoût de réinstancier le générateur pour chaque image.

```csharp
var ratios = new[] { 10, 15, 20, 30 };
foreach (var ratio in ratios)
{
    generator.Parameters.Barcode.DataBar.AspectRatio = ratio;
    generator.Save($"DatabarAspectRatio{ratio}.png", BarCodeImageFormat.Png);
}
```

## Conclusion

Vous savez maintenant comment **créer un code-barres Databar omnidirectional** en C# avec Aspose.BarCode. En initialisant un `BarcodeGenerator`, en définissant la X‑dimension, en ajustant le **set barcode aspect ratio**, et en enregistrant des fichiers PNG, vous pouvez produire des images de code-barres qui répondent à des exigences d’étiquetage variées.  

Ensuite, explorez des sujets connexes tels que **generate barcode image** pour les QR codes, la validation du **DataBar stacked omnidirectional barcode**, ou l’intégration des PNG générés dans des factures PDF avec Aspose.PDF. Expérimentez différents ratios d’aspect et tailles de modules pour trouver la configuration optimale pour votre matériel d’impression spécifique.

---


## Que devriez‑vous apprendre ensuite ?

Les tutoriels suivants couvrent des sujets étroitement liés qui s’appuient sur les techniques présentées dans ce guide. Chaque ressource comprend des exemples de code complets et fonctionnels avec des explications étape par étape pour vous aider à maîtriser des fonctionnalités supplémentaires de l’API et explorer des approches d’implémentation alternatives dans vos propres projets.

- [Comment utiliser un générateur de code-barres C# pour créer des codes-barres DataBar omnidirectional](/barcode/english/python-java/general/how-to-use-a-barcode-generator-c-to-create-databar-omni-dire/)
- [Code-barres Databar empilé omnidirectional en C# – Guide complet](/barcode/english/python-java/general/databar-stacked-omnidirectional-barcode-in-c-complete-guide/)
- [Comment générer un code-barres en C# – créer une image de code-barres C# avec DataBar Expanded](/barcode/english/python-java/general/how-to-generate-barcode-in-c-create-barcode-image-c-with-dat/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}