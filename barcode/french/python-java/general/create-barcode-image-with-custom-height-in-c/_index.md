---
category: general
date: 2026-10-28
description: Créer une image de code‑barres en C# et apprendre à ajuster la hauteur
  à l’aide de l’API BarcodeGenerator. Guide étape par étape pour une hauteur de code‑barres
  personnalisée et la modification de la hauteur des barres.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode image
- how to adjust height
- c# barcode generator
- custom barcode height
- change barcode height
language: fr
lastmod: 2026-10-28
og_description: Créez une image de code‑barres en C# et voyez instantanément comment
  ajuster la hauteur. Suivez cet exemple complet pour définir une hauteur de code‑barres
  personnalisée avec le BarcodeGenerator.
og_image_alt: Screenshot showing a generated barcode image with a custom height
og_title: Créer une image de code-barres avec une hauteur personnalisée en C# – guide
  complet
schemas:
- author: Aspose
  dateModified: '2026-10-28'
  description: Create barcode image in C# and learn how to adjust height using the
    BarcodeGenerator API. Step‑by‑step guide for custom barcode height and changing
    bar height.
  headline: Create barcode image with custom height in C#
  type: TechArticle
tags:
- barcode
- C#
- image generation
- GS1‑Databar
title: Créer une image de code‑barres avec une hauteur personnalisée en C#
url: /fr/python-java/general/create-barcode-image-with-custom-height-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Créer une image de code-barres avec hauteur personnalisée en C#

Si vous devez **créer une image de code-barres** et contrôler ses dimensions, ce guide vous montre exactement comment faire. En utilisant la bibliothèque Aspose.BarCode .NET, vous pouvez générer un code‑barres GS1‑Databar Omni‑Directional, puis **comment ajuster la hauteur** pour répondre à n'importe quelle exigence de mise en page.

Vous parcourrez un programme complet et exécutable qui montre un **générateur de code‑barres c#**, explique chaque propriété que vous définissez, et affiche deux sorties différentes — une avec une hauteur de barre de 30 pixels et une autre avec une hauteur de barre de 60 pixels. À la fin, vous serez capable de **modifier la hauteur du code‑barres** de façon programmatique pour tout type de code‑barres pris en charge par la bibliothèque.

## Prérequis

- .NET 6.0 SDK ou version ultérieure (le code fonctionne également avec .NET Framework 4.6+)
- Visual Studio 2022 ou tout éditeur capable de compiler des projets C#
- Package NuGet Aspose.BarCode pour .NET (`Install-Package Aspose.BarCode`)
- Familiarité de base avec la syntaxe C#

> **Astuce :** Si vous utilisez un pipeline CI, ajoutez le package NuGet à votre fichier `csproj` afin que la construction le restaure automatiquement.

## Étape 1 : Configurer le projet et importer les espaces de noms

Créez un nouveau projet console et ajoutez les instructions `using` requises. Les espaces de noms vous donnent accès à `BarcodeGenerator`, `EncodeTypes` et aux aides de format d'image.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace BarcodeHeightDemo
{
    class Program
    {
        static void Main()
        {
            // The rest of the tutorial code lives here.
        }
    }
}
```

> **Pourquoi c’est important :** Importer les bons espaces de noms évite les erreurs de compilation et rend l'API découvrable dans IntelliSense.

## Étape 2 : Initialiser le **générateur de code‑barres c#** pour un code GS1‑Databar Omni‑Directional

Le constructeur prend deux arguments : le type de code‑barres (`EncodeTypes.DatabarOmniDirectional`) et la chaîne de données. La chaîne de données doit respecter le format GS1 Application Identifier, par exemple `(01)12345678901231`.

```csharp
// Create a barcode generator for a GS1‑Databar Omni‑Directional code
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.DatabarOmniDirectional,
    "(01)12345678901231");
```

> **Explication :** L'objet `BarcodeGenerator` est le point d'entrée pour tous les paramètres liés aux code‑barres. Une fois que vous avez cette instance, vous pouvez ajuster les dimensions, les couleurs et le format de sortie.

## Étape 3 : Définir une X‑dimension commune (largeur en pixels de la barre la plus étroite)

Une X‑dimension de 2 pixels est un bon point de départ pour la plupart des scénarios d’affichage à l’écran.

```csharp
// Set a 2‑pixel X‑dimension (width of the smallest bar)
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

> **Pourquoi définir la X‑dimension ?** Elle contrôle la largeur globale du code‑barres. La garder constante garantit que la modification de la hauteur des barres ne déforme pas l’équilibre visuel.

## Étape 4 : **Créer une image de code‑barres** avec une hauteur de barre de 30 pixels

Nous configurons maintenant la hauteur des barres, enregistrons la première image, puis modifions la hauteur pour la seconde.

```csharp
// Configure a 30‑pixel bar height
barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 30;

// Save the first image
string output30 = "DatabarBarHeight30Pixels.png";
barcodeGenerator.Save(output30, BarCodeImageFormat.Png);
Console.WriteLine($"Saved barcode with 30 px height to {output30}");
```

> **Résultat :** Vous obtenez un fichier PNG où chaque barre verticale mesure 30 pixels de haut. La X‑dimension reste à 2 pixels, donc la largeur globale reste inchangée.

## Étape 5 : **Comment ajuster la hauteur** – changer la hauteur des barres à 60 pixels

Pour démontrer la **hauteur personnalisée du code‑barres**, il suffit d’attribuer une nouvelle valeur à la même propriété et d’enregistrer à nouveau.

```csharp
// Change the bar height to 60 pixels
barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 60;

// Save the second image
string output60 = "DatabarBarHeight60Pixels.png";
barcodeGenerator.Save(output60, BarCodeImageFormat.Png);
Console.WriteLine($"Saved barcode with 60 px height to {output60}");
```

> **Point clé :** La propriété `BarHeight` est mutable ; vous n’avez pas besoin de recréer l’instance `BarcodeGenerator`. Cela rend la génération de plusieurs tailles dans une boucle ou un traitement par lots peu coûteuse.

## Étape 6 : Vérifier la sortie

Exécutez le programme console (`dotnet run`). Après l'exécution, vous devriez voir deux fichiers PNG dans le dossier de sortie du projet :

- `DatabarBarHeight30Pixels.png` – barres courtes (30 px)
- `DatabarBarHeight60Pixels.png` – barres hautes (60 px)

Les deux images contiennent les mêmes données encodées, mais la hauteur visuelle diffère, ce qui est utile lors de l’intégration de code‑barres dans des formulaires, des étiquettes produit ou des composants UI avec des contraintes d’espace variables.

![Créer une image de code-barres avec hauteur personnalisée](barcode-example.png){.align-center width="600" alt="Créer une image de code-barres avec hauteur personnalisée"}

> **Conseil :** Ouvrez les fichiers PNG dans n’importe quel visualiseur d’image. Le code‑barres plus haut doit être exactement le double de la taille verticale du plus court, tandis que l’espacement horizontal reste identique.

## Étape 7 : Variantes courantes et cas limites

| Situation | Paramètre recommandé |
|-----------|----------------------|
| **Impression sur une imprimante d'étiquettes haute résolution** | Utilisez une X‑dimension plus grande (par ex., 4 px) et augmentez `BarHeight` proportionnellement. |
| **Affichage sur un écran basse résolution (low‑dpi)** | Conservez `XDimension` à 1 px et `BarHeight` entre 20‑40 px pour une bonne lisibilité. |
| **Génération de QR codes ou de codes‑barres 2‑D** | La propriété `BarHeight` est ignorée ; utilisez `EncodeTypes.QR` et ajustez `ImageHeight` à la place. |
| **Génération en lot de nombreuses hauteurs** | Parcourez un tableau de hauteurs et appelez `Save` dans la boucle ; il n’est pas nécessaire de recréer le générateur à chaque itération. |

### Gestion des hauteurs invalides

La bibliothèque lève une `ArgumentOutOfRangeException` si vous définissez `BarHeight` à une valeur non positive. Protégez‑vous contre cela avec une vérification simple :

```csharp
int desiredHeight = 0; // example invalid value
if (desiredHeight <= 0)
{
    throw new ArgumentException("Bar height must be greater than zero.");
}
barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = desiredHeight;
```

## Code source complet (prêt à copier)

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace BarcodeHeightDemo
{
    class Program
    {
        static void Main()
        {
            // 1️⃣ Create the barcode generator for GS1‑Databar Omni‑Directional
            BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
                EncodeTypes.DatabarOmniDirectional,
                "(01)12345678901231");

            // 2️⃣ Set a common 2‑pixel X‑dimension
            barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;

            // 3️⃣ First image – 30 pixel bar height
            barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 30;
            string path30 = "DatabarBarHeight30Pixels.png";
            barcodeGenerator.Save(path30, BarCodeImageFormat.Png);
            Console.WriteLine($"Saved barcode with 30 px height to {path30}");

            // 4️⃣ Second image – 60 pixel bar height
            barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 60;
            string path60 = "DatabarBarHeight60Pixels.png";
            barcodeGenerator.Save(path60, BarCodeImageFormat.Png);
            Console.WriteLine($"Saved barcode with 60 px height to {path60}");
        }
    }
}
```

> **Pourquoi cela fonctionne :** Tous les paramètres requis (`EncodeTypes`, `XDimension`, `BarHeight`) sont appliqués avant chaque appel à `Save`. La même instance `BarcodeGenerator` est réutilisée, ce qui est à la fois économique en mémoire et facile à lire.

## Conclusion

Vous savez maintenant comment **créer des fichiers d'image de code‑barres** en C# et modifier précisément la **hauteur du code‑barres** à l’aide de l’API `BarcodeGenerator`. En ajustant `BarHeight.Pixels`, vous obtenez une **hauteur de code‑barres personnalisée** sans reconstruire le générateur, ce qui rend la solution idéale pour la création d’étiquettes dynamiques, le rendu UI ou les pipelines de traitement par lots.

Ensuite, explorez des sujets connexes tels que **comment ajuster la largeur**, **ajouter du texte lisible par l’homme**, ou **exporter en SVG pour une utilisation web évolutive**. Le même schéma—définir une propriété, appeler `Save`—s’applique à ces scénarios, vous permettant d’étendre cet exemple en toute confiance.

## Que devriez‑vous apprendre ensuite ?

Les tutoriels suivants couvrent des sujets étroitement liés qui s’appuient sur les techniques démontrées dans ce guide. Chaque ressource comprend des exemples de code complets et fonctionnels avec des explications étape par étape pour vous aider à maîtriser des fonctionnalités supplémentaires de l’API et explorer des approches d’implémentation alternatives dans vos propres projets.

- [Comment changer la hauteur du code‑barres en C# – Guide complet](/barcode/english/python-java/general/how-to-change-barcode-height-in-c-complete-guide/)
- [Exemple de générateur de code‑barres – créer des codes Planet et RM4SCC avec hauteur personnalisée](/barcode/english/python-java/general/barcode-generator-example-create-planet-and-rm4scc-barcodes/)
- [Comment créer un code‑barres rm4scc et contrôler sa hauteur en C#](/barcode/english/python-java/general/how-to-create-rm4scc-barcode-and-control-its-height-in-c/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}