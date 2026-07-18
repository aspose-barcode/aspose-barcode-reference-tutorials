---
category: general
date: 2026-07-18
description: Comment définir le niveau d’erreur dans le code‑barres PDF417 avec Aspose.BarCode.
  Apprenez à générer un code‑barres PDF417 avec du texte personnalisé et à ajuster
  la correction d’erreur en quelques minutes.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to set error
- generate pdf417 barcode
- how to generate pdf417
- barcode with custom text
language: fr
lastmod: 2026-07-18
og_description: Comment définir rapidement le niveau d’erreur dans le code‑barres
  PDF417. Ce tutoriel vous guide dans la génération d’un code‑barres PDF417 avec du
  texte personnalisé et différents niveaux de correction d’erreur.
og_image_alt: how to set error level in PDF417 barcode example
og_title: Comment définir le niveau d’erreur dans le code‑barres PDF417 – Guide étape
  par étape
schemas:
- author: Aspose
  dateModified: '2026-07-18'
  description: how to set error level in PDF417 barcode using Aspose.BarCode. Learn
    to generate PDF417 barcode with custom text and tweak error correction in minutes.
  headline: How to Set Error Level in PDF417 Barcode – Complete Guide
  type: TechArticle
- description: how to set error level in PDF417 barcode using Aspose.BarCode. Learn
    to generate PDF417 barcode with custom text and tweak error correction in minutes.
  name: How to Set Error Level in PDF417 Barcode – Complete Guide
  steps:
  - name: What if my text contains line breaks?
    text: 'PDF417 automatically encodes line‑feed (`

      `) characters. Just include them in the string:'
  - name: Can I use a different image format?
    text: Absolutely. Replace `BarCodeImageFormat.Png` with `Jpeg`, `Bmp`, or `Svg`
      depending on your downstream workflow.
  - name: Does changing the X‑dimension affect error correction?
    text: Indirectly, yes. A larger X‑dimension yields bigger modules, which can improve
      scanning reliability but does **not** alter the logical error‑correction level.
      Adjust both parameters independently for best results.
  - name: How to generate PDF417 barcode in a web API?
    text: Wrap the same code in an ASP.NET Core controller and stream the PNG back
      as a `FileResult`. The core logic stays unchanged, which means **how to generate
      PDF417** remains consistent across desktop and web environments.
  type: HowTo
tags:
- PDF417
- barcode
- error correction
title: Comment définir le niveau d’erreur dans le code‑barres PDF417 – Guide complet
url: /fr/net/compact-pdf417-encoding/how-to-set-error-level-in-pdf417-barcode-complete-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Comment définir le niveau d’erreur dans un code‑barres PDF417 – Guide complet

Vous vous êtes déjà demandé **comment définir l’erreur** lors de la génération d’un code‑barres PDF417 ? Vous n’êtes pas seul — la plupart des développeurs rencontrent ce problème lorsqu’ils ont besoin d’un code‑barres plus robuste pour la lecture dans des environnements difficiles. Bonne nouvelle : ajuster le niveau de correction d’erreur est un jeu d’enfant avec Aspose.BarCode, et vous apprendrez aussi **comment générer PDF417** avec votre propre texte personnalisé.

Dans ce tutoriel, nous passerons en revue chaque étape, de la création d’un générateur de code‑barres avec des caractères spéciaux à l’enregistrement de deux fichiers PNG illustrant différents niveaux de correction d’erreur. À la fin, vous serez à l’aise avec **la génération de code‑barres PDF417**, le réglage de sa dimension X, du nombre de colonnes et, surtout, **la définition des niveaux d’erreur** adaptés à votre cas d’utilisation.

## Prérequis

- .NET 6.0 ou version ultérieure (le code fonctionne également avec .NET Framework)
- Aspose.BarCode pour .NET installé (`Install-Package Aspose.BarCode` via NuGet)
- Un dossier sur le disque où les images peuvent être écrites (remplacez `YOUR_DIRECTORY/` dans l’exemple)
- Connaissances de base en C# — si vous avez déjà écrit un `Console.WriteLine`, vous êtes prêt

> **Astuce pro :** Si vous ciblez la lecture mobile, optez pour un niveau d’erreur plus élevé (Niveau 5) afin de résister à la saleté, aux rayures ou aux conditions de faible luminosité.

## Étape 1 : Créer un générateur de code‑barres avec texte personnalisé

La première chose dont vous avez besoin est une instance `BarcodeGenerator` qui sait qu’elle doit produire un **code‑barres PDF417** et qui porte le texte exact que vous souhaitez encoder. Notez l’utilisation de caractères accentués et du symbole de copyright — cela prouve que le générateur peut gérer l’Unicode dès le départ.

```csharp
using Aspose.BarCode.Generation;

// Step 1: Create a PDF417 barcode generator with the desired text
BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Åspóse.Barcóde©");
```

*Pourquoi c’est important :* le drapeau `EncodeTypes.Pdf417` indique à Aspose que vous travaillez avec un code‑barres 2‑D empilé, tandis que l’argument chaîne devient la charge utile des données. Si vous sautez cette étape, vous obtiendrez un code‑barres Code128 par défaut au lieu du PDF417 à haute capacité dont vous avez besoin.

## Étape 2 : Affiner les paramètres visuels

Un code‑barres PDF417 n’est pas seulement des données ; c’est aussi un motif visuel. Ajuster la **dimension X** (la largeur du plus petit module) et le nombre de **colonnes** vous permet de contrôler la taille physique du code‑barres et sa lisibilité.

```csharp
// Step 2: Adjust visual parameters – set the X‑dimension and number of columns
generator.Parameters.Barcode.XDimension.Pixels = 2;   // each module is 2 pixels wide
generator.Parameters.Barcode.Pdf417.Columns = 3;    // three columns across the page
```

*Pourquoi c’est important :* une dimension X plus petite produit une image plus compacte mais peut devenir illisible avec des scanners à faible résolution. Trois colonnes offrent un ratio d’aspect équilibré pour la plupart des tailles d’étiquettes.

## Étape 3 : Définir le niveau de correction d’erreur à 2 et enregistrer

La correction d’erreur est le cœur de **comment définir l’erreur** pour PDF417. L’énumération `Pdf417ErrorLevel` va de `Level0` (pas de données supplémentaires) à `Level5` (redondance maximale). Ici, nous commençons avec le **Niveau 2**, qui ajoute une quantité modérée de résilience sans gonfler excessivement l’image.

```csharp
// Define the output folder (replace with your actual path)
string outputFolder = "YOUR_DIRECTORY/";

// Step 3: Set error correction level to 2 and save the image
generator.Parameters.Barcode.Pdf417.ErrorLevel = Pdf417ErrorLevel.Level2;
generator.Save($"{outputFolder}Pdf417ErrorLevel2.png", BarCodeImageFormat.Png);
```

Après avoir exécuté cet extrait, vous trouverez `Pdf417ErrorLevel2.png` dans votre dossier. Ouvrez‑le, et vous devriez voir un code‑barres à trois colonnes propre qui contient encore une quantité décente de redondance.

## Étape 4 : Augmenter la correction d’erreur au Niveau 5 et enregistrer à nouveau

Parfois, il faut que le code‑barres survive à des dommages plus agressifs — pensez à un entrepôt où les étiquettes sont frottées. Passer au **Niveau 5** maximise la correction d’erreur au prix d’une image légèrement plus grande.

```csharp
// Step 4: Change error correction level to 5 and save the second image
generator.Parameters.Barcode.Pdf417.ErrorLevel = Pdf417ErrorLevel.Level5;
generator.Save($"{outputFolder}Pdf417ErrorLevel5.png", BarCodeImageFormat.Png);
```

Vous avez maintenant deux fichiers PNG côte à côte : l’un avec une correction d’erreur modérée, l’autre avec le maximum. Comparez‑les ; la version Niveau 5 comportera plus de modules sombres, ce que l’algorithme ajoute pour protéger les données.

![exemple de réglage du niveau d'erreur dans le code-barres PDF417](image.png)

*Description de l’image (texte alternatif) : exemple de réglage du niveau d'erreur dans le code-barres PDF417 – montre deux fichiers PNG avec différents niveaux de correction d'erreur.*

## Résultat attendu

| Nom du fichier                | Niveau d'erreur | Dimensions approximatives (px) |
|-------------------------------|-----------------|--------------------------------|
| `Pdf417ErrorLevel2.png`       | Niveau 2        | 150 × 80                       |
| `Pdf417ErrorLevel5.png`       | Niveau 5        | 180 × 95                       |

Les deux images encodent la chaîne **« Åspóse.Barcóde© »** et peuvent être lues avec n’importe quel lecteur PDF417 standard (par ex., ZXing, Scandit). L’image Niveau 5 tolère jusqu’à ~30 % de dommages, tandis que le Niveau 2 en supporte environ ~15 %.

## Questions fréquentes et cas particuliers

### Que faire si mon texte contient des sauts de ligne ?
PDF417 encode automatiquement les caractères de saut de ligne (`\n`). Il suffit de les inclure dans la chaîne :

```csharp
new BarcodeGenerator(EncodeTypes.Pdf417, "Line1\nLine2\nLine3");
```

### Puis‑je utiliser un autre format d’image ?
Absolument. Remplacez `BarCodeImageFormat.Png` par `Jpeg`, `Bmp` ou `Svg` selon votre flux de travail en aval.

### Le changement de la dimension X affecte‑t‑il la correction d’erreur ?
Indirectement, oui. Une dimension X plus grande produit des modules plus gros, ce qui peut améliorer la fiabilité de lecture mais **n’altère pas** le niveau logique de correction d’erreur. Ajustez les deux paramètres indépendamment pour obtenir les meilleurs résultats.

### Comment générer un code‑barres PDF417 dans une API web ?
Enveloppez le même code dans un contrôleur ASP.NET Core et diffusez le PNG en tant que `FileResult`. La logique principale reste inchangée, ce qui signifie que **comment générer PDF417** reste cohérent entre les environnements desktop et web.

## Récapitulatif

Nous avons couvert **comment définir l’erreur** pour un code‑barres PDF417, démontré **comment générer PDF417** avec du texte Unicode personnalisé, et montré comment ajuster les paramètres visuels comme la dimension X et le nombre de colonnes. En remplaçant `Pdf417ErrorLevel.Level2` par `Level5`, vous contrôlez le compromis entre la taille de l’image et la résilience.

## Prochaines étapes

- Expérimentez avec **un code‑barres à texte personnalisé** incluant des URL ou des identifiants produit.
- Essayez différents nombres de colonnes (`generator.Parameters.Barcode.Pdf417.Columns = 5`) pour voir comment la forme change.
- Combinez PDF417 avec d’autres types de code‑barres dans le même document pour des solutions de lecture multimodale.
- Plongez dans la [documentation officielle d’Aspose](https://docs.aspose.com/barcode/net/) pour des fonctionnalités avancées telles que le macro PDF417 ou le mode compact.

N’hésitez pas à laisser un commentaire si vous rencontrez des problèmes, ou à partager vos propres résultats de lecture. Bonne création de code‑barres !

## Quoi apprendre ensuite ?

Les tutoriels suivants couvrent des sujets étroitement liés qui s’appuient sur les techniques démontrées dans ce guide. Chaque ressource comprend des exemples de code complets avec des explications pas à pas pour vous aider à maîtriser des fonctionnalités API supplémentaires et explorer des approches d’implémentation alternatives dans vos propres projets.

- [How to Create Barcode – Compact PDF417 with Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [How to create Aztec barcode with error correction in .NET](/barcode/english/net/aztec-barcode-encoding/aztec-error-level-example/)
- [How to Generate DataMatrix Barcodes (ECC 200) with Aspose.BarCode for .NET](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-ecc-200-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}