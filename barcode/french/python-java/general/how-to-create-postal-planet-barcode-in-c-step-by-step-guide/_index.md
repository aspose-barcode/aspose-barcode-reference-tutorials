---
category: general
date: 2026-09-23
description: Apprenez à créer des images de codes‑barres Postal Planet en C# avec
  des barres remplies et vides. Suivez cet exemple complet utilisant BarcodeGenerator
  et les paramètres de dimension X.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create postal planet barcode
- Planet barcode generator C#
- barcode X‑dimension pixels
- filled bars vs empty bars
- BarCodeImageFormat PNG
language: fr
lastmod: 2026-09-23
og_description: Créez un code‑barres Postal Planet en C# grâce à ce tutoriel détaillé.
  Générez les styles de barres remplis et vides en utilisant BarcodeGenerator et les
  paramètres de dimension X.
og_image_alt: Screenshot showing a created postal planet barcode with filled bars
og_title: Créer un code‑barres Postal Planet en C# – guide complet de programmation
schemas:
- author: Aspose
  dateModified: '2026-09-23'
  description: Learn how to create postal planet barcode images in C# with filled
    and empty bars. Follow this complete example using BarcodeGenerator and X‑dimension
    settings.
  headline: How to create postal planet barcode in C# – step‑by‑step guide
  type: TechArticle
tags:
- barcode
- C#
- Aspose.Barcode
title: Comment créer un code‑barres Postal Planet en C# – guide étape par étape
url: /fr/python-java/general/how-to-create-postal-planet-barcode-in-c-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Comment créer un code‑barres postal Planet en C# – guide étape par étape

Si vous devez **créer des images de code‑barres postal Planet** dans une application .NET, ce tutoriel vous propose une solution prête à l’emploi. Que vous construisiez un système d’étiquettes d’envoi ou un outil de vérification d’adresses, vous verrez exactement comment générer les variantes à barres pleines et à barres vides avec la classe `BarcodeGenerator` d’Aspose.Barcode.

Vous apprendrez à configurer le **générateur de code‑barres Planet**, à définir la **dimension X** (la largeur de chaque barre) en pixels, et à enregistrer le résultat sous forme de fichier PNG. Le guide explique également pourquoi vous pourriez choisir des barres pleines plutôt que des barres vides et comment basculer entre les deux avec une seule ligne de code.

## Ce dont vous avez besoin

Avant de commencer, assurez‑vous d’avoir :

* .NET 6.0 SDK ou version ultérieure (le code fonctionne également avec .NET Core et .NET Framework)
* Visual Studio 2022 (ou tout IDE supportant C#)
* Le package NuGet Aspose.Barcode for .NET (`Aspose.Barcode`) installé dans votre projet
* Des droits d’écriture sur le dossier où les fichiers PNG générés seront enregistrés

Ces prérequis garantissent que l’exemple se compile sans configuration supplémentaire.

## Étape 1 : Configurer le dossier de sortie

La première étape consiste à définir où les images de code‑barres seront écrites. Un chemin absolu ou relatif fonctionne ; assurez‑vous simplement que le dossier existe ou créez‑le programmétiquement.

```csharp
// Step 1: Define the output folder
string outputFolder = "C:/Barcodes/";

// Ensure the folder exists
if (!Directory.Exists(outputFolder))
{
    Directory.CreateDirectory(outputFolder);
}
```

*Pourquoi c’est important* : si le dossier n’existe pas, `BarcodeGenerator.Save` lève une exception. Créer le dossier à l’avance rend le code plus robuste pour les environnements de déploiement.

## Étape 2 : Initialiser un générateur de code‑barres Planet

Le **générateur de code‑barres Planet** (EncodeTypes.Planet) est la symbologie spécifique utilisée par de nombreux services postaux. Vous l’initialisez avec les données que vous souhaitez encoder — dans ce cas, la chaîne numérique `"123456"`.

```csharp
// Step 2: Create a Planet barcode generator with the data "123456"
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(EncodeTypes.Planet, "123456");
```

*Pourquoi c’est important* : `EncodeTypes.Planet` indique à Aspose.Barcode d’utiliser la symbologie Planet, qui possède un motif fixe de barres et d’espaces adapté au routage postal.

## Étape 3 : Configurer la dimension X du code‑barres

La **dimension X du code‑barres** contrôle la largeur de chaque barre individuelle. La régler à 4 pixels donne un code‑barres clair et lisible qui s’imprime correctement sur les imprimantes d’étiquettes standards.

```csharp
// Step 3: Set the X‑dimension (width of each bar) to 4 pixels
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 4;
```

*Pourquoi c’est important* : une dimension X trop petite peut rendre le code‑barres illisible, tandis qu’une valeur trop grande gaspille de l’espace sur l’étiquette. Quatre pixels constituent un compromis courant pour les imprimantes 300 dpi.

## Étape 4 : Générer un code‑barres Planet à barres pleines

Le mode de rendu par défaut utilise des **barres pleines** (barres noires sur fond blanc). Enregistrez l’image au format PNG pour préserver la qualité sans perte.

```csharp
// Step 4: Save the barcode using the default setting (filled bars)
barcodeGenerator.Save($"{outputFolder}PostalPlanetFilledBars.png", BarCodeImageFormat.Png);
```

**Résultat attendu** : `PostalPlanetFilledBars.png` montre un code‑barres Planet classique où chaque barre est remplie.  

![Exemple d’un code‑barres postal Planet créé avec des barres pleines](https://example.com/filled-bars.png "Exemple d’un code‑barres postal Planet créé avec des barres pleines")

*Pourquoi c’est important* : les barres pleines sont l’apparence standard de l’industrie pour la plupart des scanners postaux. Utiliser le PNG garantit que l’image reste nette lors de l’impression.

## Étape 5 : Créer un second générateur pour les barres vides

Pour illustrer la comparaison **barres pleines vs barres vides**, nous créons une autre instance de `BarcodeGenerator` avec les mêmes données. Réutiliser les mêmes données garantit que les deux images sont visuellement comparables.

```csharp
// Step 5: Create another Planet barcode generator for the same data
BarcodeGenerator emptyBarGenerator = new BarcodeGenerator(EncodeTypes.Planet, "123456");
```

## Étape 6 : Appliquer la même dimension X et basculer vers les barres vides

La propriété `FilledBars` bascule le mode de rendu. La régler à `false` produit des **barres vides** (barres blanches sur fond noir). La dimension X reste identique afin de conserver la même taille.

```csharp
// Step 6: Apply the same X‑dimension and configure the barcode to use empty bars
emptyBarGenerator.Parameters.Barcode.XDimension.Pixels = 4;
emptyBarGenerator.Parameters.Barcode.FilledBars = false;
```

*Pourquoi c’est important* : certains services postaux ou flux de travail personnalisés exigent le schéma de couleur inverse pour un meilleur contraste sur des supports sombres. Le drapeau `FilledBars` vous offre cette flexibilité avec une seule ligne de code.

## Étape 7 : Générer le code‑barres Planet à barres vides

Enfin, enregistrez la version à barres vides dans le même dossier de sortie.

```csharp
// Step 7: Save the barcode with empty bars
emptyBarGenerator.Save($"{outputFolder}PostalPlanetEmptyBars.png", BarCodeImageFormat.Png);
```

**Résultat attendu** : `PostalPlanetEmptyBars.png` affiche le même motif Planet, mais les barres sont vides (blanches) tandis que le fond est noir.

![Exemple d’un code‑barres postal Planet créé avec des barres vides](https://example.com/empty-bars.png "Exemple d’un code‑barres postal Planet créé avec des barres vides")

## Vérifier les résultats

Ouvrez les deux fichiers PNG dans n’importe quel visualiseur d’images. Vous devriez voir deux codes‑barres visuellement identiques, différant uniquement par l’inversion des couleurs. Pour confirmer que les codes‑barres sont lisibles, vous pouvez utiliser une application de lecture de code‑barres sur smartphone qui prend en charge la symbologie Planet.

Si les images apparaissent déformées, revérifiez la valeur de la **dimension X** et assurez‑vous que le chemin du dossier de sortie ne contient aucun caractère illégal.

## Pièges courants et bonnes pratiques

| Problème | Pourquoi cela se produit | Solution |
|----------|--------------------------|----------|
| **Dossier introuvable** | `Save` lève `DirectoryNotFoundException` lorsque le chemin est manquant. | Créez le dossier avec `Directory.CreateDirectory` avant d’enregistrer. |
| **Taille du code‑barres incorrecte** | Utiliser une dimension X non entière ou une valeur < 2 pixels produit des codes illisibles. | Gardez la dimension X ≥ 2 pixels ; 4 pixels convient à la plupart des imprimantes. |
| **Inversion des couleurs non appliquée** | Oublier de définir `FilledBars = false`. | Définissez explicitement `FilledBars` après la configuration de la dimension X. |
| **Mauvais format d’image** | Enregistrer en JPEG peut introduire des artefacts de compression. | Utilisez `BarCodeImageFormat.Png` pour une sortie sans perte. |

## Étendre l’exemple

* **Modifier les données** – Remplacez `"123456"` par n’importe quelle chaîne numérique jusqu’à 12 caractères (Planet accepte jusqu’à 12 chiffres).  
* **Ajuster la taille de l’image** – Modifiez `XDimension.Pixels` ou définissez `Height`/`Width` via `barcodeGenerator.Parameters.Image`.  
* **Ajouter une bordure** – Utilisez `barcodeGenerator.Parameters.Barcode.BorderWidth` pour dessiner un contour fin autour du code‑barres.  
* **Exporter vers d’autres formats** – Changez `BarCodeImageFormat.Png` en `Jpeg`, `Bmp` ou `Tiff` si votre flux de travail le nécessite.

## Conclusion

Vous savez maintenant comment **créer des images de code‑barres postal Planet** en C# avec la classe `BarcodeGenerator` d’Aspose.Barcode. Le tutoriel a couvert l’initialisation du **générateur de code‑barres Planet**, la définition de la **dimension X du code‑barres**, et la production de fichiers PNG à **barres pleines** et à **barres vides**. Avec ces bases, vous pouvez intégrer la génération de codes‑barres postaux dans n’importe quelle application .NET, personnaliser l’apparence et garantir une lecture fiable dans les systèmes d’envoi réels.

Prêt à explorer davantage ? Essayez de générer d’autres symbologies postales (par ex., **Postnet** ou **Intelligent Mail**) ou combinez le code‑barres avec une étiquette PDF à l’aide d’Aspose.PDF. Bon codage !


## Que devriez‑vous apprendre ensuite ?


Les tutoriels suivants couvrent des sujets étroitement liés qui s’appuient sur les techniques démontrées dans ce guide. Chaque ressource inclut des exemples de code complets avec des explications étape par étape pour vous aider à maîtriser des fonctionnalités supplémentaires de l’API et à explorer des approches d’implémentation alternatives dans vos propres projets.

- [Créer une image de code‑barres Planet en C# – Comment générer un code‑barres postal](/barcode/english/python-java/general/create-planet-barcode-image-in-c-how-to-generate-postal-barc/)
- [Générateur de code‑barres C# – créer un code‑barres Planet et un exemple RM4SCC](/barcode/english/python-java/general/barcode-generator-c-create-planet-barcode-and-rm4scc-example/)
- [Créer un code‑barres Planet en C# – Guide complet étape par étape](/barcode/english/python-java/general/create-planet-barcode-in-c-full-step-by-step-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}