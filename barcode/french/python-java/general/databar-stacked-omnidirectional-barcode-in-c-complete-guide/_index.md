---
category: general
date: 2026-07-15
description: Tutoriel C# sur le code‑barres Databar empilé omnidirectionnel. Apprenez
  à générer un Databar, à définir le rapport d’aspect et à utiliser un générateur
  de code‑barres C# pour des résultats parfaits.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- databar stacked omnidirectional
- barcode generator c#
- how to set aspect ratio
- how to generate databar
- create databar barcode
language: fr
lastmod: 2026-07-15
og_description: Code‑barres Databar empilé omnidirectionnel en C# expliqué. Suivez
  ce tutoriel étape par étape pour générer le Databar, ajuster le rapport d’aspect
  et maîtriser le générateur de code‑barres C#.
og_image_alt: Two PNG images showing a databar stacked omnidirectional barcode with
  aspect ratios 15 and 30
og_title: Code-barres DataBar empilé omnidirectionnel – Guide C#
schemas:
- author: Aspose
  dateModified: '2026-07-15'
  description: databar stacked omnidirectional barcode in C# tutorial. Learn how to
    generate databar, set aspect ratio, and use a barcode generator c# for perfect
    results.
  headline: databar stacked omnidirectional barcode in C# – Complete Guide
  type: TechArticle
- description: databar stacked omnidirectional barcode in C# tutorial. Learn how to
    generate databar, set aspect ratio, and use a barcode generator c# for perfect
    results.
  name: databar stacked omnidirectional barcode in C# – Complete Guide
  steps:
  - name: The **X‑Dimension** isn’t too low (below 1 pixel is impossible).
    text: The **X‑Dimension** isn’t too low (below 1 pixel is impossible).
  - name: The **AspectRatio** matches what your scanning hardware expects.
    text: The **AspectRatio** matches what your scanning hardware expects.
  - name: The **output path** is writable—sometimes `UnauthorizedAccessException`
      hides behind a silent failure.
    text: The **output path** is writable—sometimes `UnauthorizedAccessException`
      hides behind a silent failure.
  type: HowTo
tags:
- barcode
- C#
- Aspose.BarCode
title: Code-barres Databar empilé omnidirectionnel en C# – Guide complet
url: /fr/python-java/general/databar-stacked-omnidirectional-barcode-in-c-complete-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# code-barres databar empilé omnidirectionnel en C# – guide complet

Vous vous êtes déjà demandé comment définir le ratio d’aspect lorsque vous **databar stacked omnidirectional barcode** en C# ? Vous n'êtes pas le seul. De nombreux développeurs se heurtent à un mur en essayant d’ajuster ces codes-barres pour les étiquettes de vente au détail ou de logistique, et la documentation peut sembler un peu maigre.  

Dans ce tutoriel, nous allons parcourir **comment générer databar**, configurer la X‑Dimension, et—plus important encore—**comment définir le ratio d’aspect** afin que le lecteur le lise parfaitement. À la fin, vous disposerez d’un exemple de code prêt à l’emploi qui crée deux images de code-barres côte à côte, l’une avec un ratio d’aspect de 15 et l’autre de 30. Aucun mystère, juste des étapes claires.

## Ce que couvre ce guide

- Configurer un **barcode generator c#** en utilisant la populaire bibliothèque Aspose.BarCode.  
- Comprendre l’anatomie d’un symbole **databar stacked omnidirectional**.  
- Ajuster le **aspect ratio** pour répondre aux spécifications GS1.  
- Enregistrer le résultat sous forme de fichiers PNG que vous pouvez intégrer à n’importe quel projet .NET.  

Prérequis ? Juste un SDK .NET récent (4.6+ ou .NET Core 3.1+) et une référence NuGet à `Aspose.BarCode`. Si vous avez cela, vous êtes prêt à démarrer.

---

## Comprendre le code-barres databar empilé omnidirectionnel

Le format **databar stacked omnidirectional** regroupe un GTIN 14 et quelques chiffres supplémentaires dans un symbole compact à deux rangées. C’est le choix privilégié pour les petits articles où l’espace est limité—pensez aux cosmétiques, aux produits pharmaceutiques ou aux mini‑paquets de snacks.

Pourquoi le ratio d’aspect est‑il important ? La spécification du code‑barres définit une relation largeur‑hauteur qui influence la fiabilité du scan. Trop écrasé, le lecteur peut manquer une barre ; trop étiré, le code peut dépasser les dimensions de l’étiquette. La propriété `AspectRatio` de l’objet `DataBar` vous permet d’ajuster finement cet équilibre.

## Étape 1 : Créer un générateur de code‑barres **databar stacked omnidirectional**

Tout d’abord, lancez le générateur avec le bon type d’encodage et les données que vous souhaitez intégrer. Ici, nous utilisons une valeur GTIN‑14 d’exemple entourée de parenthèses, comme l’exige la spécification.

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;

// Initialize the generator for a DataBar Stacked Omnidirectional barcode
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.DatabarStackedOmniDirectional, "(01)12345678901231");
```

> **Astuce :** La chaîne doit commencer par « (01) » pour indiquer à la bibliothèque que les 14 chiffres suivants sont un GTIN. Oublier les parenthèses déclenche une `ArgumentException`.

## Étape 2 : Définir la taille de base des barres (X‑Dimension)

La X‑Dimension contrôle le nombre de pixels occupés par chaque module (la plus petite barre). Un point de départ courant est de 2 pixels par module, offrant un bon compromis entre lisibilité et taille du fichier.

```csharp
// Set 2 pixels per module – a safe default for most printers
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

Si vous imprimez sur une imprimante laser haute résolution, vous pouvez augmenter cela à 3 ou 4 pixels. N’oubliez pas : une X‑Dimension plus grande entraîne des dimensions globales du code‑barres plus importantes.

## Étape 3 : **Comment définir le ratio d’aspect** – première version (15)

Voici la partie qui bloque beaucoup de gens : le `AspectRatio`. C’est un entier simple, mais il influence directement la hauteur des rangées empilées par rapport à la largeur.

```csharp
// Aspect ratio of 15 – the default for many retail scenarios
barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = 15;

// Save the first image
barcodeGenerator.Save(@"YOUR_DIRECTORY\DatabarAspectRatio15.png", BarCodeImageFormat.Png);
```

Le PNG résultant ressemblera à ceci (image de substitution) :

![code-barres databar empilé omnidirectionnel avec un ratio d’aspect 15](databar_aspect_ratio_15.png)

*Texte alternatif de l’image (pour le SEO) :* **code-barres databar empilé omnidirectionnel avec un ratio d’aspect 15**.

## Étape 4 : **Comment définir le ratio d’aspect** – deuxième version (30)

Parfois, un ratio plus élevé est requis, surtout lorsque la hauteur de l’étiquette est généreuse ou que le lecteur attend un symbole plus haut. Passons à 30 et enregistrons un second fichier.

```csharp
// Change the aspect ratio to 30 for a taller barcode
barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = 30;

// Save the second image
barcodeGenerator.Save(@"YOUR_DIRECTORY\DatabarAspectRatio30.png", BarCodeImageFormat.Png);
```

Et le résultat :

![code-barres databar empilé omnidirectionnel avec un ratio d’aspect 30](databar_aspect_ratio_30.png)

*Texte alternatif de l’image :* **code-barres databar empilé omnidirectionnel avec un ratio d’aspect 30**.

Vous remarquerez que les barres sont plus hautes, mais la largeur reste identique car nous avons maintenu la X‑Dimension constante.

## Étape 5 : Vérifier le résultat – contrôle rapide

Ouvrez les deux fichiers PNG dans n’importe quel visualiseur d’images. Tous deux doivent afficher un code‑barres à deux rangées propre avec les mêmes données numériques. Si vous avez un lecteur portable à portée de main, essayez de scanner chaque fichier. Le lecteur doit renvoyer la chaîne GTIN brute `(01)12345678901231`.  

Si un scan échoue, revérifiez :

1. Que la **X‑Dimension** n’est pas trop basse (moins de 1 pixel est impossible).  
2. Que le **AspectRatio** correspond à ce que votre matériel de lecture attend.  
3. Que le **chemin de sortie** est accessible en écriture—parfois `UnauthorizedAccessException` se cache derrière un échec silencieux.

## Pièges courants lors de la **création d’un code‑barres databar**

| Symptom | Likely cause | Fix |
|---------|--------------|-----|
| Image vide enregistrée | `EncodeTypes` mismatch (e.g., using `DatabarExpanded` instead of `DatabarStackedOmniDirectional`) | Verify `EncodeTypes.DatabarStackedOmniDirectional` |
| Code‑barres trop large | X‑Dimension set too high | Reduce `XDimension.Pixels` |
| Le lecteur signale “format invalide” | Aspect ratio not supported by the scanner model | Adjust `AspectRatio` to 15 or 30 as per device specs |
| Exception lors du `Save` | Output folder missing or no write permission | Create folder or run with elevated rights |

## Avancé : Choisir dynamiquement le ratio d’aspect

Dans les applications réelles, vous pourriez devoir choisir un ratio d’aspect en fonction de la taille de l’étiquette. Voici une petite méthode d’aide qui sélectionne 15 pour les étiquettes étroites et 30 pour les étiquettes hautes.

```csharp
private static int ChooseAspectRatio(int labelWidthPx, int labelHeightPx)
{
    // Simple heuristic: if height > 2× width, use a taller ratio
    return (labelHeightPx > 2 * labelWidthPx) ? 30 : 15;
}

// Usage
int chosenRatio = ChooseAspectRatio(200, 500);
barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = chosenRatio;
barcodeGenerator.Save(@"YOUR_DIRECTORY\DatabarDynamic.png", BarCodeImageFormat.Png);
```

Ainsi, votre code **barcode generator c#** s’adapte à la volée—pas besoin de coder en dur deux sauvegardes séparées.

## Récapitulatif – ce que nous avons accompli

- **Créé** un générateur de code‑barres **databar stacked omnidirectional** en C#.  
- **Défini** la X‑Dimension à 2 pixels par module pour un rendu net.  
- **Démontré** **comment définir le ratio d’aspect** à la fois à 15 et 30, en enregistrant chaque version en PNG.  
- **Exploré** les erreurs courantes et fourni une petite aide dynamique de ratio.

Tout cela tient dans un seul fichier autonome que vous pouvez placer dans n’importe quel projet .NET. Aucun script externe, aucune configuration mystérieuse.

## Et après ? Élargissez votre boîte à outils de codes‑barres

Maintenant que vous avez maîtrisé les bases du **create databar barcode**, envisagez d’explorer :

- **Ajouter du texte lisible par l’homme** sous le symbole (`barcodeGenerator.Parameters.Barcode.CodeTextParameters.ShowCodeText = true`).  
- **Intégrer le code‑barres** directement dans un PDF avec `Aspose.Pdf` pour la génération de factures.  
- **Traitement par lots** d’une liste de GTIN avec une boucle `foreach` et nommer chaque fichier d’après son code produit.  

Chacun de ces sujets s’appuie sur les mêmes concepts fondamentaux que vous venez d’apprendre, et ils rendront vos projets **barcode generator c#** encore plus puissants.

### Dernières réflexions

Générer un **databar stacked omnidirectional** en C# n’est pas de la magie ; c’est simplement quelques ajustements de propriétés sur une bibliothèque solide. En contrôlant la X‑Dimension et le **aspect ratio**, vous avez le plein contrôle sur la forme du code‑barres et sa fiabilité de lecture.  

Lancez le code, modifiez les valeurs, et voyez le lecteur danser. Si vous rencontrez un problème, revenez au tableau « Pièges courants » — la plupart des soucis se résolvent avec un petit ajustement de propriété.  

Bon codage, et que vos étiquettes soient toujours lues du premier coup !

## Que devriez‑vous apprendre ensuite ?

Les tutoriels suivants couvrent des sujets étroitement liés qui s’appuient sur les techniques démontrées dans ce guide. Chaque ressource inclut des exemples de code complets et fonctionnels avec des explications pas à pas pour vous aider à maîtriser des fonctionnalités API supplémentaires et explorer des approches d’implémentation alternatives dans vos propres projets.

- [Customize databar stacked omnidirectional Aspect Ratio in .NET](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-aspect-ratio-customization/)
- [One-Dimensional Databar Barcode Height Adjustment](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-barcode-height-adjustment/)
- [Generate barcode image – GS1 Coupon UPC-A Databar](/barcode/english/net/gs1-barcode-encoding/gs1-coupon-upc-a-databar-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}