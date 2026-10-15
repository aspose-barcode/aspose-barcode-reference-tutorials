---
category: general
date: 2026-10-08
description: Créez un code‑barres planète vide avec C# et apprenez à générer un code‑barres
  postal à l’aide d’Aspose.BarCode. Code pas à pas et astuces inclus.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create empty planet barcode
- how to generate postal barcode
- Aspose.BarCode C#
- postal barcode example
- barcode XDimension setting
language: fr
lastmod: 2026-10-08
og_description: Créez un code‑barres planète vide avec Aspose.BarCode en C# et voyez
  comment générer des images de codes‑barres postaux pour les applications de mailing.
og_image_alt: Screenshot of generated empty Planet barcode and filled RM4SCC barcode
og_title: Créer un code‑barres planète vide – Guide du code‑barres postal C#
schemas:
- author: Aspose
  dateModified: '2026-10-08'
  description: Create empty planet barcode with C# and learn how to generate postal
    barcode using Aspose.BarCode. Step‑by‑step code and tips included.
  headline: Create empty planet barcode, generate postal barcode in C#
  type: TechArticle
tags:
- barcode
- C#
- Aspose.BarCode
- postal
title: Créer un code‑barres de planète vide, générer un code‑barres postal en C#
url: /fr/python-java/general/create-empty-planet-barcode-generate-postal-barcode-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Créer un code‑barres planet vide, générer un code‑barres postal en C#

Si vous devez **créer un code‑barres planet vide** pour un système d'envoi, ce guide vous montre exactement comment le faire avec Aspose.BarCode pour .NET. Vous apprendrez également **comment générer des codes‑barres postaux** tels que Planet et RM4SCC, personnaliser la largeur des barres et contrôler l'option des barres remplies.

La génération de codes‑barres postaux ne nécessite pas de bibliothèque graphique séparée. Le SDK Aspose.BarCode fournit une API unique qui gère l'encodage, le rendu d'image et la sélection du format d'image. À la fin de ce tutoriel, vous disposerez de trois fichiers PNG prêts à l'emploi :

* `PostalPlanetEmptyBars.png` – un code‑barres Planet à barres vides  
* `PostalPlanetFilledBars.png` – le code‑barres Planet à barres remplies par défaut  
* `PostalRM4SCCFilledBars.png` – un code‑barres RM4SCC à barres remplies  

Vous pouvez placer ces fichiers dans n'importe quel modèle d'étiquette d'envoi, les imprimer sur des enveloppes ou les transmettre à un service tiers.

## Prérequis

* .NET 6.0 ou supérieur (le code fonctionne également avec .NET Framework 4.7+).  
* Visual Studio 2022 ou tout IDE C#.  
* Aspose.BarCode pour .NET – installer via NuGet :

```bash
dotnet add package Aspose.BarCode
```

Aucune dépendance supplémentaire n'est requise.

## Créer un code‑barres planet vide avec Aspose.BarCode

La symbologie Planet fait partie de la famille de codes‑barres du United States Postal Service (USPS). Par défaut, le SDK dessine des barres **remplies**. Pour **créer un code‑barres planet vide**, vous désactivez le drapeau `FilledBars`.

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;

// Step 1 – instantiate a Planet barcode generator with the data to encode.
BarcodeGenerator planetEmpty = new BarcodeGenerator(EncodeTypes.Planet, "123456");

// Step 2 – set the width of a single bar. XDimension defines the pixel size of one bar.
planetEmpty.Parameters.Barcode.XDimension.Pixels = 4;

// Step 3 – disable the FilledBars option to get empty (hollow) bars.
planetEmpty.Parameters.Barcode.FilledBars = false;

// Step 4 – save the image. The PNG format is widely supported by printers and browsers.
planetEmpty.Save("YOUR_DIRECTORY/PostalPlanetEmptyBars.png", BarCodeImageFormat.Png);
```

**Pourquoi cela fonctionne :**  
`EncodeTypes.Planet` indique au générateur d'utiliser la symbologie Planet. `XDimension.Pixels` contrôle la largeur physique de chaque barre, ce qui est crucial pour les scanners postaux qui attendent une taille de module spécifique. Définir `FilledBars` sur `false` indique au rendu de ne dessiner que le contour de chaque barre, produisant l'apparence *vide* requise par certaines normes d'envoi.

### Résultat attendu

Vous trouverez `PostalPlanetEmptyBars.png` dans le dossier cible. L'image montre un code‑barres Planet où chaque barre est un contour plutôt qu'un rectangle plein.

![Exemple de code‑barres Planet vide](empty-planet.png){: .align-center alt="Créer un code‑barres planet vide – exemple d'un code‑barres Planet à barres vides"}

## Comment générer des images de codes‑barres postaux (version remplie)

La plupart des flux de travail postaux utilisent la version par défaut à barres remplies. La même API peut générer un code‑barres Planet rempli et un code‑barres RM4SCC avec seulement quelques lignes de code.

```csharp
// Filled Planet barcode (default behavior)
BarcodeGenerator planetFilled = new BarcodeGenerator(EncodeTypes.Planet, "123456");
planetFilled.Parameters.Barcode.XDimension.Pixels = 4;
planetFilled.Save("YOUR_DIRECTORY/PostalPlanetFilledBars.png", BarCodeImageFormat.Png);

// RM4SCC barcode – another USPS format that always uses filled bars
BarcodeGenerator rm4sccFilled = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");
rm4sccFilled.Parameters.Barcode.XDimension.Pixels = 4;
rm4sccFilled.Save("YOUR_DIRECTORY/PostalRM4SCCFilledBars.png", BarCodeImageFormat.Png);
```

**Pourquoi vous pourriez avoir besoin de RM4SCC :**  
RM4SCC est le nouveau code‑barres USPS qui encode les mêmes données que Planet mais avec une densité supérieure. Certains transporteurs exigent le RM4SCC pour les remises sur les envois en masse. Le code ci‑dessus montre comment **générer un code‑barres postal** pour les deux normes sans modifier le flux de travail global.

### Résultat attendu

* `PostalPlanetFilledBars.png` – un code‑barres Planet à barres remplies classique.  
* `PostalRM4SCCFilledBars.png` – un code‑barres RM4SCC à barres remplies, visuellement similaire mais avec un espacement plus serré.

Les deux fichiers peuvent être ouverts dans n'importe quel visualiseur d'images pour vérifier les motifs de barres.

## Ajuster la largeur des barres pour différentes résolutions d'impression

Les scanners postaux spécifient souvent une largeur minimale de module (par ex., 0,013 pouces). Si votre imprimante fonctionne à 300 dpi, un module de 4 pixels correspond à 0,013 pouces. Ajustez la valeur `XDimension.Pixels` pour correspondre à votre matériel :

| Module souhaité (pouces) | DPI | Pixels nécessaires (`XDimension`) |
|--------------------------|-----|------------------------------------|
| 0.013                    | 300 | 4                                  |
| 0.013                    | 600 | 8                                  |
| 0.015                    | 300 | 5                                  |

**Astuce pro :** Testez toujours un

## Que devriez‑vous apprendre ensuite ?

Les tutoriels suivants couvrent des sujets étroitement liés qui s'appuient sur les techniques démontrées dans ce guide. Chaque ressource comprend des exemples de code complets et fonctionnels avec des explications étape par étape pour vous aider à maîtriser des fonctionnalités supplémentaires de l'API et explorer des approches d'implémentation alternatives dans vos propres projets.

- [Comment créer un code‑barres planet PNG avec C# – guide étape par étape](/barcode/english/python-java/general/how-to-create-planet-barcode-png-with-c-step-by-step-guide/)
- [Générer un code‑barres postal en C# – guide complet avec le code‑barres Planet](/barcode/english/python-java/general/generate-postal-barcode-in-c-complete-guide-with-planet-barc/)
- [Comment générer un code‑barres postal en C# avec Aspose.BarCode](/barcode/english/python-java/general/how-to-generate-postal-barcode-in-c-with-aspose-barcode/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}