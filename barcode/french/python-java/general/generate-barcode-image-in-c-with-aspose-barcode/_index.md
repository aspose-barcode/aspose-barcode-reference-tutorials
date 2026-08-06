---
category: general
date: 2026-08-06
description: Générez une image de code‑barres en C# avec Aspose.BarCode. Apprenez
  à créer un Databar, à ajuster la taille personnalisée du code‑barres et à modifier
  la hauteur du code‑barres avec un code simple.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate barcode image
- how to generate databar
- custom barcode size
- create databar barcode
- change barcode height
language: fr
lastmod: 2026-08-06
og_description: Générez une image de code‑barres en C# avec Aspose.BarCode. Ce tutoriel
  vous montre comment créer un code‑barres Databar omnidirectionnel, personnaliser
  sa taille et modifier la hauteur du code‑barres efficacement.
og_image_alt: Screenshot of a Databar barcode generated with custom height in C#
og_title: Générer une image de code‑barres en C# – guide complet Aspose.BarCode
schemas:
- author: Aspose
  dateModified: '2026-08-06'
  description: Generate barcode image in C# using Aspose.BarCode. Learn how to generate
    Databar, adjust custom barcode size, and change barcode height with simple code.
  headline: Generate barcode image in C# with Aspose.BarCode
  type: TechArticle
- questions:
  - answer: The evaluation version of Aspose.BarCode works without a license but adds
      a small watermark. For production use, apply a purchased license using `License
      license = new License(); license.SetLicense("Aspose.BarCode.lic");`.
    question: Can I generate a barcode without installing a license?
  - answer: Yes. Very small X‑dimensions can make the barcode unreadable on low‑resolution
      printers. A minimum of 1 px for screen rendering is recommended; for print,
      use at least 0.25 mm.
    question: Does changing the X‑dimension affect readability?
  - answer: 'Replace `BarCodeImageFormat.Png` with `BarCodeImageFormat.Jpeg`. You
      may also set `generator.Parameters.ImageQuality` to control compression. ##
      Conclusion You now know how to **generate barcode image** in C# using Aspose.BarCode,
      how to **create Databar barcode**, adjust a **custom barcode size**, '
    question: What if I need to generate a barcode in JPEG format?
  type: FAQPage
tags:
- barcode
- C#
- Aspose.BarCode
title: Générer une image de code‑barres en C# avec Aspose.BarCode
url: /fr/python-java/general/generate-barcode-image-in-c-with-aspose-barcode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Générer une image de code-barres en C# avec Aspose.BarCode

Si vous devez **générer une image de code‑barres** de façon programmatique, ce guide vous montre exactement comment faire. Que vous construisiez un système d’inventaire retail ou un portail de suivi logistique, vous verrez le flux complet pour créer un code‑barres Databar Omnidirectionnel, ajuster ses dimensions et enregistrer le résultat au format PNG.

Générer une image de code‑barres est une exigence courante, mais les développeurs se demandent souvent **comment générer un Databar** avec la taille exacte dont ils ont besoin. Dans ce tutoriel, vous apprendrez à créer un code‑barres Databar, à personnaliser sa largeur et sa hauteur, et à modifier la hauteur du code‑barres sans réécrire tout le générateur.

## Prérequis

Avant de commencer, assurez‑vous d’avoir :

* SDK .NET 6.0 ou ultérieur (le code fonctionne avec .NET Core et .NET Framework)
* Visual Studio 2022 (ou tout IDE supportant C#)
* Une licence valide d’Aspose.BarCode for .NET (l’évaluation gratuite suffit pour les tests)
* Une connaissance de base de la syntaxe C#

## Étape 1 : Installer Aspose.BarCode

Ajoutez le package NuGet Aspose.BarCode à votre projet :

```bash
dotnet add package Aspose.BarCode
```

Le package contient la classe `BarcodeGenerator` utilisée tout au long de ce tutoriel. Après l’installation, restaurez le projet pour récupérer les dépendances.

## Étape 2 : Créer un générateur de code‑barres de base

La première ligne de code crée un **générateur de code‑barres** qui produira un symbole Databar Omnidirectionnel. L’énumération `EncodeTypes.DatabarOmniDirectional` indique à la bibliothèque quelle symbologie utiliser, et la chaîne de données suit la syntaxe de l’identifiant d’application GS1.

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Program
{
    static void Main()
    {
        // Step 2: Initialize the generator for a Databar Omnidirectional barcode
        BarcodeGenerator generator = new BarcodeGenerator(
            EncodeTypes.DatabarOmniDirectional,
            "(01)12345678901231"); // GS1-14 data (example GTIN)
```

**Pourquoi c’est important :** L’objet `BarcodeGenerator` est le point d’entrée pour chaque opération de code‑barres. En sélectionnant `DatabarOmniDirectional`, vous vous assurez que la sortie respecte la norme GS1 pour le scan retail.

## Étape 3 : Définir une X‑dimension personnalisée (largeur du module)

La X‑dimension contrôle la largeur de la barre la plus étroite. La régler à une petite valeur en pixels vous donne un code‑barres compact, tandis que des valeurs plus grandes augmentent la largeur globale.

```csharp
        // Step 3: Define a custom X‑dimension (module width) of 2 px
        generator.Parameters.Barcode.XDimension.Pixels = 2;
```

**Explication :** Une X‑dimension de 2 pixels est un choix courant pour les écrans haute résolution. Ajustez cette valeur si vous avez besoin d’une densité visuelle plus serrée ou plus lâche.

## Étape 4 : Générer la première image de code‑barres avec une hauteur spécifique

La hauteur du code‑barres est indépendante de la X‑dimension. Ici, nous fixons la hauteur des barres à **30 px**, puis enregistrons l’image au format PNG.

```csharp
        // Step 4: Set bar height to 30 px and save the image
        generator.Parameters.Barcode.BarHeight.Pixels = 30;
        generator.Save("DatabarBarHeight30Pixels.png", BarCodeImageFormat.Png);
```

**Résultat :** Vous disposez maintenant d’un fichier nommé `DatabarBarHeight30Pixels.png` qui montre un code‑barres Databar de 30 px de hauteur. Cela illustre la capacité de **taille de code‑barres personnalisée** pour un cas d’usage tel qu’une petite étiquette.

## Étape 5 : Modifier la hauteur du code‑barres pour une version plus grande

Si le même code‑barres doit apparaître sur une étiquette plus grande, il suffit de modifier la propriété de hauteur et de réutiliser la même instance du générateur.

```csharp
        // Step 5: Increase the bar height to 60 px for a larger barcode
        generator.Parameters.Barcode.BarHeight.Pixels = 60;
        generator.Save("DatabarBarHeight60Pixels.png", BarCodeImageFormat.Png);
    }
}
```

**Pourquoi vous pouvez réutiliser le générateur :** Modifier `BarHeight.Pixels` met à jour la mise en page interne sans recréer l’objet, ce qui économise de la mémoire et conserve la chaîne de données intacte. C’est la méthode recommandée pour **modifier la hauteur du code‑barres** à la volée.

## Étape 6 : Vérifier le résultat

Ouvrez les deux fichiers PNG dans n’importe quel visualiseur d’images. Vous devriez voir deux codes‑barres Databar Omnidirectionnels qui encodent le même GTIN mais diffèrent par leur taille verticale :

* `DatabarBarHeight30Pixels.png` – 30 px de hauteur, adapté aux reçus compacts.
* `DatabarBarHeight60Pixels.png` – 60 px de hauteur, idéal pour les étiquettes de bord de rayon plus grandes.

Les deux images conservent la même X‑dimension, de sorte que le rapport barre‑espace reste constant tandis que la hauteur globale s’ajuste.

## Variations courantes et cas limites

| Situation | Comment le gérer |
|-----------|------------------|
| **Symbologie de code‑barres différente** | Remplacez `EncodeTypes.DatabarOmniDirectional` par une autre valeur d’énumération (par ex., `EncodeTypes.Code128`). Le reste du code reste inchangé. |
| **Dimensions non exprimées en pixels** | Utilisez `generator.Parameters.Barcode.XDimension.Millimeters` ou `BarHeight.Millimeters` si vous avez besoin de mesures physiques pour une sortie prête à l’impression. |
| **Arrière‑plan transparent** | Définissez `generator.Parameters.ImageBackgroundColor = Color.Transparent;` avant d’appeler `Save`. |
| **Sortie haute résolution** | Augmentez proportionnellement `XDimension.Pixels` et `BarHeight.Pixels`, ou enregistrez en `BarCodeImageFormat.Tiff` pour une qualité sans perte. |
| **Plusieurs codes‑barres dans une même image** | Créez des instances séparées de `BarcodeGenerator`, rendez chacune dans un `Bitmap`, puis composez‑les avec `Graphics.DrawImage`. |

**Astuce pro :** Testez toujours le code‑barres généré avec un vrai scanner avant de le déployer en production. Les scanners peuvent interpréter différemment des barres très fines selon l’éclairage et la qualité du capteur.

## Code source complet à titre de référence

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // Initialize the generator for a Databar Omnidirectional barcode
            BarcodeGenerator generator = new BarcodeGenerator(
                EncodeTypes.DatabarOmniDirectional,
                "(01)12345678901231"); // Example GTIN

            // Custom X‑dimension (module width) – 2 px
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // First image: 30 px height
            generator.Parameters.Barcode.BarHeight.Pixels = 30;
            generator.Save("DatabarBarHeight30Pixels.png", BarCodeImageFormat.Png);

            // Second image: 60 px height (larger barcode)
            generator.Parameters.Barcode.BarHeight.Pixels = 60;
            generator.Save("DatabarBarHeight60Pixels.png", BarCodeImageFormat.Png);

            Console.WriteLine("Barcode images generated successfully.");
        }
    }
}
```

Copiez le code dans un nouveau projet console, exécutez‑le, et vous verrez les deux fichiers PNG apparaître dans le répertoire de sortie.

## Questions fréquentes

**Q : Puis‑je générer un code‑barres sans installer de licence ?**  
R : La version d’évaluation d’Aspose.BarCode fonctionne sans licence mais ajoute un petit filigrane. Pour une utilisation en production, appliquez une licence achetée avec `License license = new License(); license.SetLicense("Aspose.BarCode.lic");`.

**Q : Le changement de la X‑dimension affecte‑t‑il la lisibilité ?**  
R : Oui. Des X‑dimensions très petites peuvent rendre le code‑barres illisible sur des imprimantes basse résolution. Un minimum de 1 px pour le rendu à l’écran est recommandé ; pour l’impression, utilisez au moins 0,25 mm.

**Q : Et si je dois générer un code‑barres au format JPEG ?**  
R : Remplacez `BarCodeImageFormat.Png` par `BarCodeImageFormat.Jpeg`. Vous pouvez également régler `generator.Parameters.ImageQuality` pour contrôler la compression.

## Conclusion

Vous savez maintenant comment **générer une image de code‑barres** en C# avec Aspose.BarCode, comment **créer un code‑barres Databar**, ajuster une **taille de code‑barres personnalisée**, et **modifier la hauteur du code‑barres** à la demande. L’exemple complet montre le flux de travail le plus courant, et le tableau des variations vous prépare à gérer les cas réels.

Ensuite, explorez des sujets connexes tels que **l’insertion de codes‑barres dans des documents PDF**, **la génération en lot de plusieurs codes‑barres**, et **l’utilisation de QR codes pour les paiements mobiles**. Chacun de ces scénarios s’appuie sur les mêmes principes présentés ici, vous permettant d’étendre vos connaissances en toute confiance.

Bon codage, et que vos codes‑barres soient toujours lisibles !

## Que devez‑vous apprendre ensuite ?

Les tutoriels suivants couvrent des sujets étroitement liés qui s’appuient sur les techniques démontrées dans ce guide. Chaque ressource inclut des exemples de code complets avec des explications pas à pas pour vous aider à maîtriser des fonctionnalités API supplémentaires et à explorer des approches d’implémentation alternatives dans vos propres projets.

- [Generate barcode image – GS1 Coupon UPC-A Databar](/barcode/english/net/gs1-barcode-encoding/gs1-coupon-upc-a-databar-configuration/)
- [How to generate Aztec barcode with custom aspect ratio using Aspose.BarCode for .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)
- [How to Generate Barcode – Code 39 Configuration with Aspose.BarCode](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-code-39-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}