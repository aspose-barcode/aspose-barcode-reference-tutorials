---
category: general
date: 2026-07-18
description: Créez rapidement le code‑barres Planet avec C#. Apprenez à générer des
  barres pleines et vides, à définir la dimension X et à enregistrer des images PNG
  – le tout dans un seul tutoriel.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create planet barcode
- Planet barcode generator
- BarcodeGenerator parameters
- XDimension pixels
- filled bars vs empty bars
language: fr
lastmod: 2026-07-18
og_description: Créez le code‑barcode Planet instantanément. Ce guide vous montre
  comment définir la dimension X, basculer entre les barres pleines et vides, et exporter
  des fichiers PNG avec Aspose.BarCode.
og_image_alt: Screenshot of a generated Planet barcode saved as PNG
og_title: Créer le code-barres Planète en C# – Guide complet de programmation
schemas:
- author: Aspose
  dateModified: '2026-07-18'
  description: Create Planet barcode quickly with C#. Learn how to generate filled
    and empty bars, set X‑dimension, and save PNG images – all in one tutorial.
  headline: Create Planet Barcode in C# – Full Step‑by‑Step Guide
  type: TechArticle
- description: Create Planet barcode quickly with C#. Learn how to generate filled
    and empty bars, set X‑dimension, and save PNG images – all in one tutorial.
  name: Create Planet Barcode in C# – Full Step‑by‑Step Guide
  steps:
  - name: “Can I change the image format?”
    text: Absolutely. The `Save` method accepts `BarCodeImageFormat.Jpeg`, `Bmp`,
      `Gif`, etc. Just replace `BarCodeImageFormat.Png` with your desired format.
  - name: “What if I need a different barcode height?”
    text: 'Use `planetBarcode.Parameters.Barcode.BarHeight` (in points) to increase
      or decrease the vertical size. For example:'
  - name: “Is there a way to add a human‑readable caption?”
    text: 'Yes. Set the `CodeText` property on `planetBarcode.Parameters.Caption`:'
  - name: “Do I need to dispose the generator?”
    text: 'The `BarcodeGenerator` implements `IDisposable`. Wrap it in a `using` block
      if you’re creating many barcodes in a loop:'
  - name: “What about error handling?”
    text: 'Enclose the `Save` calls in a `try…catch` block to capture `IOException`
      (disk issues) or `ArgumentException` (invalid parameters). Example:'
  type: HowTo
tags:
- barcode
- C#
- Aspose.BarCode
title: Créer le code‑barres Planet en C# – Guide complet étape par étape
url: /fr/python-java/general/create-planet-barcode-in-c-full-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Créer un code-barres Planet en C# – Guide complet étape par étape

Vous avez déjà eu besoin de **créer un code-barres planet** images mais vous n'étiez pas sûr des propriétés à ajuster ? Vous n'êtes pas seul. De nombreux développeurs se heurtent à un mur lorsque les barres remplies par défaut ne correspondent pas aux exigences de la spécification, ou lorsque la largeur des barres doit correspondre au DPI d'une imprimante.  

Dans ce tutoriel, vous apprendrez exactement comment **créer des fichiers planet barcode** en utilisant la bibliothèque Aspose.BarCode, comment contrôler les **pixels XDimension**, et comment basculer entre les **barres remplies** et les **barres vides** sans réécrire de code. À la fin, vous disposerez de deux fichiers PNG — l'un avec des barres solides et l'autre avec des barres creuses — prêts pour tout système postal qui attend la symbologie Planet.

## Prérequis

- .NET 6.0 ou version ultérieure (le code fonctionne également sur .NET Framework 4.7 +)  
- Package NuGet Aspose.BarCode pour .NET (`Install-Package Aspose.BarCode`)  
- Connaissances de base en C# (vous verrez plus tard pourquoi nous utilisons les instructions `using`)  
- Un dossier accessible en écriture sur le disque où les PNG seront enregistrés  

Si vous avez tout cela, nous pouvons passer directement à l'implémentation.

## Étape 1 – Configurer le projet et ajouter la bibliothèque

Tout d'abord, créez une nouvelle application console (ou tout projet C#) et référencez la bibliothèque **Planet barcode generator**.

```csharp
using System;
using Aspose.BarCode.Generation;

namespace PlanetBarcodeDemo
{
    class Program
    {
        static void Main(string[] args)
        {
            // The rest of the code lives here
        }
    }
}
```

> **Astuce pro :** Dans Visual Studio, faites un clic droit sur le projet → *Manage NuGet Packages* → recherchez **Aspose.BarCode** et cliquez sur *Install*. Cela vous donne accès à `BarcodeGenerator` et à tous les **paramètres BarcodeGenerator** dont vous avez besoin.

## Étape 2 – Initialiser le générateur de code-barres Planet

Nous allons maintenant réellement **créer le générateur de planet barcode** et lui fournir les données que nous voulons encoder (`"123456"` dans cet exemple). L'énumération `EncodeTypes.Planet` indique à la bibliothèque quelle symbologie utiliser.

```csharp
// Step 2: Initialise the generator with Planet symbology and data
BarcodeGenerator planetBarcode = new BarcodeGenerator(EncodeTypes.Planet, "123456");
```

> **Pourquoi c'est important :** Le drapeau `EncodeTypes.Planet` applique automatiquement le bon checksum et les règles de mise en page pour le code-barres postal Planet, vous n'avez donc pas besoin de les calculer manuellement.

## Étape 3 – Configurer la X‑Dimension (largeur de la barre)

La plupart des imprimantes attendent que chaque barre soit un nombre spécifique de pixels. Ici, nous définissons les **pixels XDimension** à `4`, ce qui est une valeur courante pour les imprimantes thermiques à 203 dpi.

```csharp
// Step 3: Set the width of each bar (X‑dimension) to 4 pixels
planetBarcode.Parameters.Barcode.XDimension.Pixels = 4;
```

> **Cas particulier :** Si vous ciblez une imprimante à 300 dpi, vous pourriez avoir besoin de `3` ou `5` pixels à la place. Ajustez cette valeur en fonction de la documentation de votre appareil.

## Étape 4 – Enregistrer la version à barres remplies

Par défaut, le générateur produit des **barres remplies** (rectangles noirs solides). Enregistrons cela sur le disque :

```csharp
// Step 4: Save the barcode with default (filled) bars
planetBarcode.Save("YOUR_DIRECTORY/PostalPlanetFilledBars.png", BarCodeImageFormat.Png);
```

Remplacez `YOUR_DIRECTORY` par un chemin absolu ou relatif auquel votre application peut écrire. Après l'exécution de cette ligne, vous trouverez un fichier PNG qui ressemble à un code-barres Planet classique — parfait pour tester avec un scanner postal.

## Étape 5 – Passer aux barres vides

Parfois, les services postaux exigent le style « barres vides », où les barres sont découpées dans un fond blanc au lieu d'être peintes en noir. La bibliothèque expose un commutateur simple :

```csharp
// Step 5: Re‑configure the generator to produce empty bars
planetBarcode.Parameters.Barcode.FilledBars = false;
```

Définir `FilledBars` à `false` indique au rendu d'inverser la logique de remplissage des barres. Aucun besoin de créer une nouvelle instance `BarcodeGenerator` ; nous ajustons simplement les **paramètres BarcodeGenerator** existants.

## Étape 6 – Enregistrer la version à barres vides

Enfin, exportez la deuxième image :

```csharp
// Step 6: Save the barcode with empty bars
planetBarcode.Save("YOUR_DIRECTORY/PostalPlanetEmptyBars.png", BarCodeImageFormat.Png);
```

Vous avez maintenant deux fichiers PNG distincts, chacun répondant à une exigence visuelle différente.

## Exemple complet fonctionnel

En assemblant toutes les pièces, voici le programme complet, prêt à copier‑coller :

```csharp
using System;
using Aspose.BarCode.Generation;

namespace PlanetBarcodeDemo
{
    class Program
    {
        static void Main(string[] args)
        {
            // Initialise the Planet barcode generator with data
            BarcodeGenerator planetBarcode = new BarcodeGenerator(EncodeTypes.Planet, "123456");

            // Configure bar width (X‑dimension) – 4 pixels works for most 203 dpi printers
            planetBarcode.Parameters.Barcode.XDimension.Pixels = 4;

            // Save the default filled‑bars version
            planetBarcode.Save(@"C:\Barcodes\PostalPlanetFilledBars.png", BarCodeImageFormat.Png);

            // Switch to empty‑bars style
            planetBarcode.Parameters.Barcode.FilledBars = false;

            // Save the empty‑bars version
            planetBarcode.Save(@"C:\Barcodes\PostalPlanetEmptyBars.png", BarCodeImageFormat.Png);

            Console.WriteLine("Both Planet barcode images have been generated successfully.");
        }
    }
}
```

**Sortie attendue** (dans la console) :

```
Both Planet barcode images have been generated successfully.
```

Et dans `C:\Barcodes\` vous verrez :

- `PostalPlanetFilledBars.png` – barres noires solides  
- `PostalPlanetEmptyBars.png` – barres blanches avec contours noirs  

Ouvrez-les dans n'importe quel visualiseur d'images ; ils devraient tous deux être conformes à la spécification Planet.

## Questions fréquentes & astuces

### « Puis-je changer le format de l'image ? »

Absolument. La méthode `Save` accepte `BarCodeImageFormat.Jpeg`, `Bmp`, `Gif`, etc. Il suffit de remplacer `BarCodeImageFormat.Png` par le format souhaité.

### « Et si j'ai besoin d'une hauteur de code-barres différente ? »

Utilisez `planetBarcode.Parameters.Barcode.BarHeight` (en points) pour augmenter ou diminuer la taille verticale. Par exemple :

```csharp
planetBarcode.Parameters.Barcode.BarHeight = 30; // 30 points tall
```

### « Existe‑t‑il un moyen d'ajouter une légende lisible par l'homme ? »

Oui. Définissez la propriété `CodeText` sur `planetBarcode.Parameters.Caption` :

```csharp
planetBarcode.Parameters.Caption.Visible = true;
planetBarcode.Parameters.Caption.TopMargin = 5; // space between barcode and text
planetBarcode.Parameters.Caption.Text = "123456";
```

### « Dois‑je libérer le générateur ? »

Le `BarcodeGenerator` implémente `IDisposable`. Enveloppez‑le dans un bloc `using` si vous créez de nombreux codes-barres dans une boucle :

```csharp
using (BarcodeGenerator gen = new BarcodeGenerator(...))
{
    // configure and save
}
```

### « Et la gestion des erreurs ? »

Encapsulez les appels `Save` dans un bloc `try…catch` pour capturer `IOException` (problèmes de disque) ou `ArgumentException` (paramètres invalides). Exemple :

```csharp
try
{
    planetBarcode.Save(path, BarCodeImageFormat.Png);
}
catch (Exception ex)
{
    Console.Error.WriteLine($"Failed to save barcode: {ex.Message}");
}
```

## Récapitulatif

Nous avons couvert tout ce dont vous avez besoin pour **créer des images planet barcode** en C# :

1. Initialisez le **générateur de code-barres Planet** avec vos données.  
2. Ajustez les **pixels XDimension** pour correspondre aux spécifications de l'imprimante.  
3. Enregistrez un PNG avec des **barres remplies**.  
4. Basculez `FilledBars` pour produire des **barres vides**.  
5. Enregistrez le deuxième PNG.  

À partir de là, vous pouvez explorer davantage les **paramètres BarcodeGenerator**, expérimenter avec d'autres symbologies (`EncodeTypes.Postnet`, `EncodeTypes.Code128`, etc.), ou intégrer les images dans un flux de travail postal.

---

**Prêt pour l'étape suivante ?** Essayez d'ajouter un code QR au même document, ou générez un lot de codes-barres Planet à partir d'une liste CSV en utilisant une boucle `foreach`. L'API Aspose.BarCode est suffisamment flexible pour gérer des opérations en masse, des couleurs personnalisées, et même une sortie SVG vectorielle.

Si vous rencontrez des problèmes, laissez un commentaire ci‑dessous ou consultez la documentation officielle d'Aspose.BarCode pour des approfondissements des fonctionnalités avancées. Bon codage !

## Que devriez‑vous apprendre ensuite ?

Les tutoriels suivants couvrent des sujets étroitement liés qui s'appuient sur les techniques démontrées dans ce guide. Chaque ressource comprend des exemples de code complets et fonctionnels avec des explications étape par étape pour vous aider à maîtriser des fonctionnalités API supplémentaires et explorer des approches d'implémentation alternatives dans vos propres projets.

- [Créer un code-barres avec Aspose - Définir les dimensions X & Y en Java](/barcode/english/java/barcode-configuration/managing-x-y-dimension-barcode/)
- [Comment créer des images de code128 en Java avec Aspose.BarCode](/barcode/english/java/advanced-settings-and-optimization/saving-barcode-images-different-formats/)
- [Comment créer un code128 en Java et définir la hauteur des barres](/barcode/english/java/barcode-configuration/setting-bars-height/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}