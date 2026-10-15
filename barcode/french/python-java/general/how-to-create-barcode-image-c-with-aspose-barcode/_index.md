---
category: general
date: 2026-10-12
description: Créer une image de code‑barres en C# avec Aspose.BarCode en quelques
  minutes. Cet exemple de générateur de code‑barres pas à pas en C# montre comment
  définir les rapports d’aspect et enregistrer des fichiers PNG.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode image c#
- barcode generator example c#
language: fr
lastmod: 2026-10-12
og_description: Créez instantanément une image de code‑barres en C#. Suivez cet exemple
  de générateur de code‑barres en C# pour produire des codes‑barres PNG de haute qualité
  avec des rapports d’aspect personnalisés.
og_image_alt: Sample barcode image created with C# using Aspose.BarCode
og_title: Créer une image de code-barres C# – guide rapide avec Aspose.BarCode
schemas:
- author: Aspose
  dateModified: '2026-10-12'
  description: Create barcode image c# using Aspose.BarCode in minutes. This step‑by‑step
    barcode generator example c# shows how to set aspect ratios and save PNG files.
  headline: How to create barcode image c# with Aspose.BarCode
  type: TechArticle
- description: Create barcode image c# using Aspose.BarCode in minutes. This step‑by‑step
    barcode generator example c# shows how to set aspect ratios and save PNG files.
  name: How to create barcode image c# with Aspose.BarCode
  steps:
  - name: – Initialise the barcode generator
    text: '```csharp using Aspose.BarCode.Generation;'
  - name: – Set the module (X‑dimension) size
    text: '```csharp // Adjust visual parameters – set the module size (X‑dimension)
      in pixels. barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2; ```'
  - name: – Save the first image with aspect ratio 15
    text: '```csharp // Set the first aspect ratio (15) and save the image. barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio
      = 15; barcodeGenerator.Save("YOUR_DIRECTORY/DatabarAspectRatio15.png", BarCodeImageFormat.Png);
      ```'
  - name: – Change the aspect ratio to 30 and save a second image
    text: '```csharp // Change the aspect ratio to 30 and save the second image. barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio
      = 30; barcodeGenerator.Save("YOUR_DIRECTORY/DatabarAspectRatio30.png", BarCodeImageFormat.Png);
      ```'
  - name: Expected output
    text: 'Running the program creates two PNG files:'
  type: HowTo
tags:
- barcode
- C#
- image generation
title: Comment créer une image de code‑barres en C# avec Aspose.BarCode
url: /fr/python-java/general/how-to-create-barcode-image-c-with-aspose-barcode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Comment créer une image de code-barres c# avec Aspose.BarCode

Si vous devez **créer une image de code-barres c#** rapidement, ce guide vous accompagne à travers un exemple complet et exécutable. Que vous construisiez un système d'étiquettes d'expédition ou un scanner d'inventaire, les étapes ci‑dessous montrent exactement comment configurer un code‑barres DataBar Stacked Omnidirectional, ajuster ses paramètres visuels et enregistrer le résultat sous forme de fichier PNG.

Vous verrez également un **exemple de générateur de code-barres c#** qui montre comment modifier le ratio d’aspect à la volée, afin de produire plusieurs variantes sans réécrire le code. Aucune documentation externe n’est requise — il suffit de copier, coller et exécuter.

## Ce dont vous avez besoin

* .NET 6.0 ou ultérieur (le code fonctionne également avec .NET Framework 4.7+)
* Le package NuGet **Aspose.BarCode for .NET**  
  ```bash
  dotnet add package Aspose.BarCode
  ```
* Un dossier où les fichiers PNG générés seront écrits (remplacez `YOUR_DIRECTORY` dans le code)

Ces prérequis garantissent que l’**exemple de générateur de code-barres c#** s’exécute sur n’importe quelle machine de développement moderne sous Windows, Linux ou macOS.

## Comment créer une image de code-barres c# avec Aspose.BarCode

Le processus se compose de quatre courtes étapes : instancier le générateur, définir la taille du module, configurer le ratio d’aspect, puis enregistrer l’image. Chaque étape est expliquée afin que vous compreniez *pourquoi* elle est importante, et pas seulement *quoi* taper.

### Étape 1 – Initialiser le générateur de code-barres

```csharp
using Aspose.BarCode.Generation;

// Create a DataBar Stacked Omnidirectional barcode generator with the desired data.
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.DatabarStackedOmniDirectional,
    "(01)12345678901231");
```

**Pourquoi c’est important :** Le constructeur `BarcodeGenerator` prend deux arguments : la symbologie du code‑barres (`EncodeTypes.DatabarStackedOmniDirectional`) et la chaîne de données brutes. Le préfixe `(01)` indique au scanner que les 14 chiffres suivants représentent un identifiant GTIN‑14, ce qui est une exigence courante dans le commerce de détail et la logistique.

### Étape 2 – Définir la taille du module (dimension X)

```csharp
// Adjust visual parameters – set the module size (X‑dimension) in pixels.
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

**Pourquoi c’est important :** La dimension X contrôle la largeur de la plus petite barre (le « module »). Une valeur de `2` pixels donne un code‑barres net et haute résolution qui reste lisible après mise à l’échelle. Si vous avez besoin d’un code‑barres plus grand pour une affiche, augmentez cette valeur proportionnellement.

### Étape 3 – Enregistrer la première image avec un ratio d’aspect 15

```csharp
// Set the first aspect ratio (15) and save the image.
barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = 15;
barcodeGenerator.Save("YOUR_DIRECTORY/DatabarAspectRatio15.png", BarCodeImageFormat.Png);
```

**Pourquoi c’est important :** Les symboles DataBar prennent en charge un *ratio d’aspect* qui influence la relation hauteur‑largeur. Un ratio d’aspect de `15` est la valeur par défaut pour de nombreuses applications de vente au détail et produit un code‑barres compact, presque carré, qui s’adapte facilement aux petites étiquettes.

### Étape 4 – Modifier le ratio d’aspect à 30 et enregistrer une deuxième image

```csharp
// Change the aspect ratio to 30 and save the second image.
barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = 30;
barcodeGenerator.Save("YOUR_DIRECTORY/DatabarAspectRatio30.png", BarCodeImageFormat.Png);
```

**Pourquoi c’est important :** Augmenter le ratio d’aspect à `30` étire le code‑barres verticalement, améliorant la lisibilité sur les scanners basse résolution ou sur les étiquettes plus hautes que larges. Comme la même instance `BarcodeGenerator` est réutilisée, vous évitez d’allouer un nouvel objet pour chaque variante — un schéma efficace pour le traitement par lots.

## Exemple complet et exécutable

Voici le programme complet que vous pouvez copier dans une application console. Il inclut les directives `using` nécessaires, la gestion des erreurs et des commentaires expliquant chaque ligne.

```csharp
using System;
using Aspose.BarCode.Generation;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            try
            {
                // Initialise the generator with DataBar Stacked Omnidirectional symbology.
                BarcodeGenerator generator = new BarcodeGenerator(
                    EncodeTypes.DatabarStackedOmniDirectional,
                    "(01)12345678901231");

                // Set the module (X‑dimension) size – 2 pixels gives a clear image.
                generator.Parameters.Barcode.XDimension.Pixels = 2;

                // -----------------------------------------------------------------
                // First image – aspect ratio 15 (default for most retail use cases)
                // -----------------------------------------------------------------
                generator.Parameters.Barcode.DataBar.AspectRatio = 15;
                string path15 = "YOUR_DIRECTORY/DatabarAspectRatio15.png";
                generator.Save(path15, BarCodeImageFormat.Png);
                Console.WriteLine($"Saved barcode with aspect ratio 15 to {path15}");

                // -----------------------------------------------------------------
                // Second image – aspect ratio 30 (taller barcode for special scanners)
                // -----------------------------------------------------------------
                generator.Parameters.Barcode.DataBar.AspectRatio = 30;
                string path30 = "YOUR_DIRECTORY/DatabarAspectRatio30.png";
                generator.Save(path30, BarCodeImageFormat.Png);
                Console.WriteLine($"Saved barcode with aspect ratio 30 to {path30}");
            }
            catch (Exception ex)
            {
                Console.Error.WriteLine($"Error generating barcode: {ex.Message}");
            }
        }
    }
}
```

### Résultat attendu

L’exécution du programme crée deux fichiers PNG :

| Nom du fichier | Ratio d’aspect | Utilisation typique |
|----------------|----------------|---------------------|
| `DatabarAspectRatio15.png` | 15 | Étiquette de vente au détail standard |
| `DatabarAspectRatio30.png` | 30 | Étiquette haute ou scanner basse résolution |

Les deux images contiennent un code‑barres DataBar Stacked Omnidirectional net qui encode la valeur GTIN‑14 `12345678901231`. Vous pouvez ouvrir les PNG dans n’importe quel visualiseur d’images pour vérifier la qualité visuelle.

![Exemple d’image de code-barres créée avec C# utilisant Aspose.BarCode](https://example.com/placeholder.png){.align-center width=400 alt="Exemple d’image de code-barres créée avec C# utilisant Aspose.BarCode"}

*Le texte alternatif ci‑dessus inclut le mot‑clé principal, aidant à la fois les moteurs de recherche et les lecteurs d’écran.*

## Considérations supplémentaires et conseils de bonnes pratiques

* **Formats pris en charge** – `BarCodeImageFormat` prend en charge PNG, JPEG, BMP, GIF et TIFF. PNG est sans perte, ce qui en fait le choix le plus sûr pour le scan en aval.
* **Personnalisation des couleurs** – Vous pouvez modifier les couleurs de premier plan/arrière‑plan via `generator.Parameters.Barcode.ForegroundColor` et `BackgroundColor`. Ceci est utile lors de l’impression sur des supports colorés.
* **Génération par lots** – Pour de grands inventaires, encapsulez la logique d’enregistrement dans une boucle `foreach` qui lit les données produit depuis un fichier CSV. Réutiliser la même instance `BarcodeGenerator` réduit la pression mémoire.
* **Gestion des erreurs** – Le bloc `try/catch` dans l’exemple complet capture les problèmes tels que les chaînes de données invalides ou les erreurs de permission d’écriture, fréquents lorsque le répertoire cible n’existe pas.
* **Performance** – Définir `XDimension.Pixels` avant le premier appel `Save` garantit que le rendu calcule la taille du bitmap une seule fois par changement de ratio d’aspect.

## Conclusion

Vous savez maintenant comment **créer une image de code-barres c#** avec Aspose.BarCode, ajuster la dimension X, changer les ratios d’aspect et enregistrer des fichiers PNG dans un seul bloc de code réutilisable. Cet **exemple de générateur de code-barres c#** couvre les variations les plus courantes que vous rencontrerez lors de la génération de symboles DataBar Stacked Omnidirectional pour les applications de vente au détail ou de logistique.

## Et après ?

* Explorez d’autres symbologies comme `EncodeTypes.Code128` ou `EncodeTypes.QR` pour élargir votre solution.
* Expérimentez avec `generator.Parameters.Barcode.ImageMargin` pour ajouter de l’espace blanc autour du code‑barres.
* Intégrez les PNG générés dans des factures PDF à l’aide d’Aspose.PDF, ou intégrez‑les directement dans des rapports HTML.

N’hésitez pas à adapter le code à votre flux de travail spécifique — que vous ayez besoin d’une seule image par produit ou d’une exportation massive de milliers de codes‑barres, le modèle présenté ici s’adapte efficacement.

---

## Que devriez‑vous apprendre ensuite ?

Les tutoriels suivants couvrent des sujets étroitement liés qui s’appuient sur les techniques démontrées dans ce guide. Chaque ressource comprend des exemples de code complets et fonctionnels avec des explications étape par étape pour vous aider à maîtriser des fonctionnalités API supplémentaires et explorer des approches d’implémentation alternatives dans vos propres projets.

- [Comment créer une image de code-barres avec Aspose.Barcode en C#](/barcode/english/python-java/general/how-to-create-barcode-image-with-aspose-barcode-in-c/)
- [Exemple de générateur de code-barres en C# – Définir colonnes, lignes et exporter l’image](/barcode/english/python-java/general/barcode-generator-example-in-c-set-columns-rows-export-image/)
- [Comment créer une image de code-barres postal en C# avec Aspose.BarCode](/barcode/english/python-java/general/how-to-create-postal-barcode-image-in-c-using-aspose-barcode/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}