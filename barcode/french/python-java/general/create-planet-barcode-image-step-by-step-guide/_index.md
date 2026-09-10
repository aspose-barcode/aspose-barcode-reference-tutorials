---
category: general
date: 2026-07-27
description: Créez rapidement une image de code‑barres planétaire. Apprenez à générer
  un code‑barres planétaire avec C# et à personnaliser les barres remplies ou vides.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create planet barcode image
- how to generate planet barcode
- planet barcode C#
- barcode X‑dimension
- filled vs empty bars
language: fr
lastmod: 2026-07-27
og_description: Créez une image de code‑barres planétaire en quelques secondes. Suivez
  ce guide pour apprendre à générer un code‑barres planétaire, ajuster la dimension
  X et passer des barres pleines aux barres vides.
og_image_alt: Screenshot showing a create planet barcode image with filled bars
og_title: Créer une image de code‑barres de planète – Tutoriel complet C#
schemas:
- author: Aspose
  dateModified: '2026-07-27'
  description: create planet barcode image quickly. Learn how to generate planet barcode
    with C# and customize filled or empty bars.
  headline: create planet barcode image – Step‑by‑Step Guide
  type: TechArticle
- description: create planet barcode image quickly. Learn how to generate planet barcode
    with C# and customize filled or empty bars.
  name: create planet barcode image – Step‑by‑Step Guide
  steps:
  - name: Why the X‑dimension matters
    text: The X‑dimension controls how wide each tiny bar (or “module”) is. A value
      of **4 pixels** yields a barcode that’s clear on screen and prints nicely on
      standard label printers. If you need a denser image for a high‑resolution print,
      bump the value up to 6 or 8.
  - name: Expected output
    text: Open the resulting `PostalPlanetFilledBars.png` and you should see a classic
      Planet barcode—solid vertical bars with a quiet zone on each side. It looks
      just like the example you’d find on a postal envelope.
  - name: What “FilledBars = false” does
    text: Setting `FilledBars` to `false` tells the rendering engine to draw only
      the bar outlines. This is useful when you need a lighter‑weight image for on‑screen
      display or when a printing guideline explicitly requires the empty style.
  - name: Expected output
    text: The `PostalPlanetEmptyBars.png` file shows the same pattern as before, but
      each bar is a thin line instead of a solid block. It’s perfect for low‑contrast
      printing on colored paper.
  - name: When to use RM4SCC
    text: RM4SCC is the Dutch “Postcode” barcode. If you’re building a multi‑country
      logistics platform, having both Planet and RM4SCC generators at hand saves you
      a lot of boilerplate code.
  - name: What if I need a different image format?
    text: Just swap `BarCodeImageFormat.Png` for `Jpeg`, `Bmp`, or `Gif`. The library
      handles the conversion automatically.
  - name: How do I change the barcode height?
    text: Use `planetFilled.Parameters.Barcode.BarHeight = 50; // height in points`
      (or pixels, depending on the library version). Higher values give you a taller
      barcode, which can improve scan reliability on low‑resolution scanners.
  - name: Can I embed the barcode directly into a PDF?
    text: Absolutely. The `Save` method returns a `byte[]` if you call the overload
      that writes to a stream. Feed that stream into a PDF generation library (e.g.,
      iTextSharp) and you’ve got a fully‑automated mailing label.
  - name: What if the data string contains non‑numeric characters?
    text: 'Planet and RM4SCC expect **numeric only** payloads. Passing letters will
      throw an `ArgumentException`. Validate your input first:'
  - name: Does the X‑dimension affect scanning speed?
    text: A larger X‑dimension creates a more robust barcode, which generally improves
      scanning speed, especially on low‑quality scanners. However, it also increases
      the physical size of the label, so balance readability with space constraints.
  type: HowTo
tags:
- barcode
- C#
- imaging
title: Créer une image de code‑barres planétaire – Guide étape par étape
url: /fr/python-java/general/create-planet-barcode-image-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# créer une image de code-barres planet – Tutoriel complet C#

Vous vous êtes déjà demandé **comment générer un code-barres planet** pour un système de messagerie ou une application logistique ? Vous n'êtes pas le premier à vous creuser la tête à ce sujet. Dans ce tutoriel, nous passerons en revue tout ce dont vous avez besoin pour **créer des images de code-barres planet**, des bases de la classe `BarcodeGenerator` à l'ajustement de la X‑dimension et au remplacement des barres pleines par des barres vides.

Nous jetterons également un œil à une symbologie connexe—RM4SCC—pour que vous puissiez voir comment le même motif fonctionne pour d’autres codes-barres postaux. À la fin, vous disposerez de trois extraits prêts à l'emploi qui génèrent des fichiers PNG que vous pourrez intégrer directement à votre projet.

## Ce dont vous avez besoin

- .NET 6.0 ou ultérieur (le code fonctionne également sur .NET Framework 4.7+)  
- Une référence à **Aspose.BarCode** (ou toute bibliothèque exposant `BarcodeGenerator`, `EncodeTypes`, `BarCodeImageFormat`)  
- Un IDE avec lequel vous êtes à l'aise—Visual Studio, Rider ou VS Code conviendra  
- Un dossier où vous pouvez écrire des images (remplacez `YOUR_DIRECTORY` dans les exemples)

C’est tout. Aucun package NuGet supplémentaire au-delà de la bibliothèque de code-barres elle-même.

---

## Étape 1 : Configurer le projet et les imports

Tout d'abord, créons une petite application console afin de pouvoir exécuter le code immédiatement.

```csharp
using System;
using Aspose.BarCode.Generation;   // Core barcode generator
using Aspose.BarCode;               // For BarCodeImageFormat enum

namespace PlanetBarcodeDemo
{
    class Program
    {
        static void Main(string[] args)
        {
            // We'll call helper methods here (see later)
            GeneratePlanetFilledBars();
            GeneratePlanetEmptyBars();
            GenerateRM4SCCFilledBars();
        }
```

> **Astuce :** Gardez votre méthode `Main` propre ; déléguez chaque scénario à sa propre méthode. Cela rend le code plus lisible et reflète les trois exemples du fragment original.

---

## Étape 2 : **create planet barcode image** avec des barres pleines par défaut

La symbologie Planet est utilisée par de nombreux services postaux pour les numéros de suivi. Pour **create planet barcode image** avec les barres solides habituelles, suivez ces trois lignes :

```csharp
        static void GeneratePlanetFilledBars()
        {
            // 1️⃣ Create a generator for the Planet symbology with data "123456"
            BarcodeGenerator planetFilled = new BarcodeGenerator(EncodeTypes.Planet, "123456");

            // 2️⃣ Set the X‑dimension (module width) to 4 pixels for better visibility
            planetFilled.Parameters.Barcode.XDimension.Pixels = 4;

            // 3️⃣ Save the barcode as a PNG image
            planetFilled.Save("YOUR_DIRECTORY/PostalPlanetFilledBars.png", BarCodeImageFormat.Png);
        }
```

### Pourquoi la X‑dimension est importante
La X‑dimension contrôle la largeur de chaque petite barre (ou « module »). Une valeur de **4 pixels** produit un code-barres lisible à l’écran et s’imprime correctement sur les imprimantes d’étiquettes standard. Si vous avez besoin d’une image plus dense pour une impression haute résolution, augmentez la valeur à 6 ou 8.

### Résultat attendu
Ouvrez le fichier `PostalPlanetFilledBars.png` généré et vous devriez voir un code-barres Planet classique — des barres verticales pleines avec une zone silencieuse de chaque côté. Il ressemble exactement à l’exemple que l’on trouve sur une enveloppe postale.

---

## Étape 3 : **create planet barcode image** avec des barres vides

Parfois, la spécification postale exige un style *barres‑vides*, où les barres sont des contours plutôt que des remplissages pleins. Passer à ce mode ne nécessite qu’un seul changement de propriété.

```csharp
        static void GeneratePlanetEmptyBars()
        {
            // 1️⃣ Create the generator (same data as before)
            BarcodeGenerator planetEmpty = new BarcodeGenerator(EncodeTypes.Planet, "123456");

            // 2️⃣ Keep the X‑dimension consistent
            planetEmpty.Parameters.Barcode.XDimension.Pixels = 4;

            // 3️⃣ Disable filled bars → we get an empty‑bar representation
            planetEmpty.Parameters.Barcode.FilledBars = false;

            // 4️⃣ Save the PNG
            planetEmpty.Save("YOUR_DIRECTORY/PostalPlanetEmptyBars.png", BarCodeImageFormat.Png);
        }
```

### Ce que fait “FilledBars = false”
Définir `FilledBars` à `false` indique au moteur de rendu de ne dessiner que les contours des barres. Cela est utile lorsque vous avez besoin d’une image plus légère pour l’affichage à l’écran ou lorsqu’une directive d’impression exige explicitement le style vide.

### Résultat attendu
Le fichier `PostalPlanetEmptyBars.png` montre le même motif qu’auparavant, mais chaque barre est une fine ligne plutôt qu’un bloc plein. C’est parfait pour une impression à faible contraste sur du papier coloré.

---

## Étape 4 : Générer un code-barres RM4SCC (Bonus)

Bien que notre objectif principal soit la symbologie Planet, la même API vous permet d’obtenir des résultats similaires à **create planet barcode image** pour d’autres codes postaux. Voici comment obtenir une sortie de style **how to generate planet barcode** pour RM4SCC :

```csharp
        static void GenerateRM4SCCFilledBars()
        {
            // 1️⃣ Create a generator for the RM4SCC symbology
            BarcodeGenerator rm4sccFilled = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");

            // 2️⃣ Align X‑dimension with the other examples
            rm4sccFilled.Parameters.Barcode.XDimension.Pixels = 4;

            // 3️⃣ Save the image
            rm4sccFilled.Save("YOUR_DIRECTORY/PostalRM4SCCFilledBars.png", BarCodeImageFormat.Png);
        }
    }
}
```

### Quand utiliser RM4SCC
RM4SCC est le code-barres « Postcode » néerlandais. Si vous développez une plateforme logistique multi‑pays, disposer à la fois des générateurs Planet et RM4SCC vous évite beaucoup de code répétitif.

---

## Questions fréquentes & cas limites

### Et si j’ai besoin d’un format d’image différent ?
Il suffit de remplacer `BarCodeImageFormat.Png` par `Jpeg`, `Bmp` ou `Gif`. La bibliothèque gère automatiquement la conversion.

### Comment modifier la hauteur du code-barres ?
Utilisez `planetFilled.Parameters.Barcode.BarHeight = 50; // hauteur en points` (ou en pixels, selon la version de la bibliothèque). Des valeurs plus élevées donnent un code-barres plus haut, ce qui peut améliorer la fiabilité du scan sur des lecteurs basse résolution.

### Puis-je intégrer le code-barres directement dans un PDF ?
Absolument. La méthode `Save` renvoie un `byte[]` si vous appelez la surcharge qui écrit dans un flux. Transmettez ce flux à une bibliothèque de génération de PDF (par ex., iTextSharp) et vous obtenez une étiquette d’envoi entièrement automatisée.

### Et si la chaîne de données contient des caractères non numériques ?
Planet et RM4SCC attendent des charges utiles **numériques uniquement**. Passer des lettres déclenchera une `ArgumentException`. Validez d’abord votre entrée :

```csharp
if (!Regex.IsMatch(data, @"^\d+$"))
    throw new ArgumentException("Planet barcode data must be numeric.");
```

### La X‑dimension affecte‑t‑elle la vitesse de numérisation ?
Une X‑dimension plus grande crée un code-barres plus robuste, ce qui améliore généralement la vitesse de numérisation, surtout sur des lecteurs de mauvaise qualité. Cependant, cela augmente également la taille physique de l’étiquette, il faut donc équilibrer lisibilité et contraintes d’espace.

---

## Exemple complet fonctionnel (les trois méthodes)

Voici le programme complet que vous pouvez copier‑coller dans un nouveau projet console. Remplacez `YOUR_DIRECTORY` par un chemin absolu ou relatif où votre application peut écrire.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

namespace PlanetBarcodeDemo
{
    class Program
    {
        static void Main(string[] args)
        {
            GeneratePlanetFilledBars();
            GeneratePlanetEmptyBars();
            GenerateRM4SCCFilledBars();

            Console.WriteLine("All barcode images have been saved.");
        }

        static void GeneratePlanetFilledBars()
        {
            BarcodeGenerator planetFilled = new BarcodeGenerator(EncodeTypes.Planet, "123456");
            planetFilled.Parameters.Barcode.XDimension.Pixels = 4;
            planetFilled.Save("YOUR_DIRECTORY/PostalPlanetFilledBars.png", BarCodeImageFormat.Png);
        }

        static void GeneratePlanetEmptyBars()
        {
            BarcodeGenerator planetEmpty = new BarcodeGenerator(EncodeTypes.Planet, "123456");
            planetEmpty.Parameters.Barcode.XDimension.Pixels = 4;
            planetEmpty.Parameters.Barcode.FilledBars = false;
            planetEmpty.Save("YOUR_DIRECTORY/PostalPlanetEmptyBars.png", BarCodeImageFormat.Png);
        }

        static void GenerateRM4SCCFilledBars()
        {
            BarcodeGenerator rm4sccFilled = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");
            rm4sccFilled.Parameters.Barcode.XDimension.Pixels = 4;
            rm4sccFilled.Save("YOUR_DIRECTORY/PostalRM4SCCFilledBars.png", BarCodeImageFormat.Png);
        }
    }
}
```

Exécutez le programme, ouvrez les trois fichiers PNG, et vous verrez exactement les images décrites précédemment. Aucune configuration supplémentaire n’est requise.

---

## Récapitulatif & étapes suivantes

Nous avons couvert **how to generate planet barcode** images depuis le départ, en alternant entre les styles plein et contour, et en étendant la même approche à RM4SCC. Les points clés :

1. Instancier `BarcodeGenerator` avec le bon `EncodeTypes` et les données.  
2. Ajuster `XDimension.Pixels` pour contrôler la largeur des barres.  
3. Utiliser `FilledBars = false` pour la variante à barres vides.  
4. Enregistrer le résultat dans le format d’image de votre choix.

Maintenant que vous pouvez **create planet barcode image** fichiers, envisagez ces idées de suivi :

- **Génération par lots** : Parcourez un CSV de numéros de suivi et générez un PNG pour chacun.  
- **Dimensionnement dynamique** : Exposez la X‑dimension et la hauteur des barres comme paramètres de configuration dans une API web.  
- **Intégration avec les imprimantes d’étiquettes** : Envoyez les octets PNG directement à une imprimante compatible ZPL pour créer des étiquettes à la volée.

N’hésitez pas à expérimenter — changez la chaîne de données, essayez différentes dimensions, ou combinez le code-barres avec un QR code sur la même étiquette. La bibliothèque de code-barres est suffisamment flexible pour gérer tout cela.

Vous avez un scénario difficile dont vous n’êtes pas sûr ? Laissez un commentaire ci‑dessous, et nous résoudrons le problème ensemble. Bon codage !

## Que devriez‑vous apprendre ensuite ?

Les tutoriels suivants couvrent des sujets étroitement liés qui s’appuient sur les techniques démontrées dans ce guide. Chaque ressource comprend des exemples de code complets et fonctionnels avec des explications étape par étape pour vous aider à maîtriser des fonctionnalités supplémentaires de l’API et explorer des approches d’implémentation alternatives dans vos propres projets.

- [Créer une image de code-barres DotCode – lignes & colonnes (Aspose.BarCode)](/barcode/english/net/dotcode-barcode-configuration/dotcode-rows-columns-configuration/)
- [Créer une image de code-barres C# – Exemple GS1 DataMatrix](/barcode/english/net/gs1-barcode-encoding/gs1-datamatrix-example/)
- [Créer une image de code-barres c# – Configurer les lignes & colonnes de Codablock F](/barcode/english/net/codablock-f-encoding/codablock-f-row-column-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}