---
category: general
date: 2026-09-16
description: Apprenez comment définir la largeur, créer des barres vides et remplir
  les barres lors de la génération d’un code‑barcode Planet avec Aspose.BarCode.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to set width
- how to make empty
- how to fill bars
- generate planet barcode
language: fr
lastmod: 2026-09-16
og_description: Comment définir la largeur, créer des barres vides et remplir les
  barres lors de la génération d’un code‑barcode Planet avec Aspose.BarCode – guide
  complet étape par étape.
og_image_alt: Screenshot showing how to set width for a Planet barcode in C#
og_title: Comment définir la largeur et générer un code‑barres Planet en C#
schemas:
- author: Aspose
  dateModified: '2026-09-16'
  description: Learn how to set width, how to make empty bars, and how to fill bars
    when you generate Planet barcode using Aspose.BarCode.
  headline: How to set width and generate a Planet barcode in C#
  type: TechArticle
tags:
- barcode
- C#
- Aspose.BarCode
title: Comment définir la largeur et générer un code‑barres Planet en C#
url: /fr/python-java/general/how-to-set-width-and-generate-a-planet-barcode-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Comment définir la largeur et générer un code-barres Planet en C#

Si vous avez besoin de **how to set width** pour un code-barres Planet, ce guide montre le processus complet. Vous verrez également **how to make empty** barres, **how to fill bars**, et les étapes exactes pour **generate Planet barcode** avec Aspose.BarCode pour .NET.

Générer un code-barres Planet de style postal est courant lors de la création d'applications d'étiquettes d'envoi ou d'intégrations de services postaux. À la fin de ce tutoriel, vous disposerez d'un programme console prêt à l'emploi qui crée à la fois une image à barres remplies et une image à barres vides, chacune utilisant la même chaîne de données.

## Prérequis

- .NET 6.0 SDK ou version ultérieure (le code fonctionne également avec .NET Framework 4.7+)
- Visual Studio 2022 ou tout IDE compatible C#
- Package NuGet Aspose.BarCode pour .NET (`Aspose.BarCode`)  
  Installer avec :

```bash
dotnet add package Aspose.BarCode
```

Aucune configuration supplémentaire n'est requise ; la bibliothèque gère l'encodage d'image en interne.

## Étape 1 : Créer un projet console et ajouter la bibliothèque

Ouvrez un terminal et exécutez :

```bash
dotnet new console -n PlanetBarcodeDemo
cd PlanetBarcodeDemo
dotnet add package Aspose.BarCode
```

Cela crée un fichier `Program.cs` où nous écrirons la logique du code-barres.

## Étape 2 : Écrire le code – how to set width and generate Planet barcode

Ouvrez `Program.cs` et remplacez son contenu par l'exemple complet suivant :

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Data to encode – the same value is used for both images
        const string data = "123456";

        // -----------------------------------------------------------------
        // Part A: Filled‑bars version (default style)
        // -----------------------------------------------------------------
        // Step 2.1: Create a Planet barcode generator
        var filledGenerator = new BarcodeGenerator(EncodeTypes.Planet, data);

        // Step 2.2: How to set width – define the width of a single bar in pixels
        // The XDimension controls bar width; 4 pixels yields a clear, printable image
        filledGenerator.Parameters.Barcode.XDimension.Pixels = 4;

        // Step 2.3: Save the filled‑bars image (default is FilledBars = true)
        string filledPath = "PostalPlanetFilledBars.png";
        filledGenerator.Save(filledPath, BarCodeImageFormat.Png);
        Console.WriteLine($"Filled‑bars barcode saved to {filledPath}");

        // -----------------------------------------------------------------
        // Part B: Empty‑bars version (unfilled style)
        // -----------------------------------------------------------------
        // Step 3.1: Re‑instantiate the generator for the same data
        var emptyGenerator = new BarcodeGenerator(EncodeTypes.Planet, data);

        // Step 3.2: How to set width again – required after re‑instantiation
        emptyGenerator.Parameters.Barcode.XDimension.Pixels = 4;

        // Step 3.3: How to make empty – disable the filled‑bars flag
        emptyGenerator.Parameters.Barcode.FilledBars = false;

        // Step 3.4: Save the empty‑bars image
        string emptyPath = "PostalPlanetEmptyBars.png";
        emptyGenerator.Save(emptyPath, BarCodeImageFormat.Png);
        Console.WriteLine($"Empty‑bars barcode saved to {emptyPath}");

        // -----------------------------------------------------------------
        // Verification output
        // -----------------------------------------------------------------
        Console.WriteLine("Both barcodes generated successfully.");
    }
}
```

### Pourquoi chaque étape est importante

- **How to set width** : La propriété `XDimension.Pixels` influence directement la taille physique de chaque barre. Choisir une valeur entre 2 et 6 pixels équilibre la lisibilité à l'écran et la qualité d'impression.
- **How to make empty** : Définir `FilledBars = false` indique au générateur de ne dessiner que les contours des barres. Ce style est utile pour l'impression « clair‑sur‑sombre » ou lorsque vous souhaitez que la texture du papier sous‑jacent apparaisse.
- **How to fill bars** : La valeur par défaut `FilledBars = true` crée des barres noires pleines, ce qui est la norme pour la plupart des lecteurs postaux.
- **Generate Planet barcode** : Utiliser `EncodeTypes.Planet` sélectionne l'encodage spécifique requis par le United States Postal Service (USPS) pour les codes-barres Planet.

## Étape 3 : Compiler et exécuter le programme

Depuis le dossier du projet, exécutez :

```bash
dotnet run
```

Vous devriez voir une sortie console similaire à :

```
Filled‑bars barcode saved to PostalPlanetFilledBars.png
Empty‑bars barcode saved to PostalPlanetEmptyBars.png
Both barcodes generated successfully.
```

Deux fichiers PNG apparaissent dans le répertoire du projet :

- `PostalPlanetFilledBars.png` – barres noires pleines (style par défaut)
- `PostalPlanetEmptyBars.png` – barres en contour (style vide)

Ouvrez-les dans n'importe quel visualiseur d'images pour vérifier que la largeur des barres correspond au réglage de 4 pixels et que la version vide montre des barres non remplies.

## Questions fréquentes et cas particuliers

| Question | Réponse |
|----------|--------|
| *Puis-je utiliser un autre format d'image ?* | Oui. Remplacez `BarCodeImageFormat.Png` par `Jpeg`, `Bmp` ou `Gif` selon vos besoins. |
| *Que faire si le code-barres devient trop large pour mon étiquette ?* | Réduisez `XDimension.Pixels` (par ex., à `2`) ou augmentez la largeur du module de l'imprimante d'étiquettes. |
| *Dois-je définir `Height` manuellement ?* | La bibliothèque calcule automatiquement la hauteur en fonction de l'encodage. Vous pouvez la remplacer avec `Parameters.Barcode.BarHeight`. |
| *Le style barres vides est‑il pris en charge par toutes les imprimantes ?* | La plupart des imprimantes thermiques modernes gèrent les deux styles, remplis et vides, mais vérifiez avec un test d'impression si vous utilisez un appareil ancien. |
| *Comment ajouter une légende lisible par l'homme sous le code-barres ?* | Utilisez `Parameters.Caption` pour activer et styliser une légende ; définissez `CaptionAbove` à `false` pour la placer en dessous. |

## Astuces professionnelles

- **Reuse the same generator** uniquement lorsque vous conservez tous les paramètres identiques. Modifier `FilledBars` après une sauvegarde n'affecte pas l'image déjà enregistrée, donc ré‑instancier (comme montré) garantit un départ propre.
- **Batch generation** : Enveloppez le code dans une boucle et modifiez `data` à chaque itération pour créer une série de codes-barres Planet pour un envoi en masse.
- **Performance** : Pour des milliers de codes-barres, créez une seule instance de `BarcodeGenerator`, ajustez `XDimension` et `FilledBars` selon les besoins, et réutilisez l'objet afin de réduire les allocations de mémoire.

## Conclusion

Vous savez maintenant **how to set width**, **how to make empty**, **how to fill bars**, et les étapes exactes pour **generate Planet barcode** avec Aspose.BarCode en C#. L'exemple complet et exécutable produit à la fois des fichiers PNG à barres pleines et à barres vides, prêts à être intégrés dans n'importe quel flux de travail d'étiquettes d'envoi.

Ensuite, explorez des sujets connexes tels que **how to add QR codes to the same label**, **customizing barcode colors**, ou **embedding the barcode into a PDF document**. Chacun de ces points s'appuie sur les mêmes fondamentaux présentés ici. Bon codage !

## Que devriez‑vous apprendre ensuite ?

Les tutoriels suivants couvrent des sujets étroitement liés qui s'appuient sur les techniques démontrées dans ce guide. Chaque ressource comprend des exemples de code complets et fonctionnels avec des explications étape par étape pour vous aider à maîtriser des fonctionnalités supplémentaires de l'API et explorer des approches d'implémentation alternatives dans vos propres projets.

- [Créer une image de code-barres Planet en C# – Comment générer un code-barres postal](/barcode/english/python-java/general/create-planet-barcode-image-in-c-how-to-generate-postal-barc/)
- [Comment créer un code-barres Code128 avec des barres vides en Java](/barcode/english/java/image-manipulation/generating-barcode-empty-bars/)
- [Comment générer une image de code-barres en Java avec Aspose.BarCode](/barcode/english/java/barcode-rendering-techniques/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}