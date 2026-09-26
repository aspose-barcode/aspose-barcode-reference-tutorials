---
category: general
date: 2026-09-26
description: Apprenez à créer un code‑barres en C# avec Aspose.BarCode. Ce guide pas
  à pas comprend un exemple de générateur de code‑barres et montre comment ajuster
  la hauteur des barres.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode c#
- barcode generator example
- how to adjust bar height
- change barcode height
- generate barcode aspose
language: fr
lastmod: 2026-09-26
og_description: Créer un code-barres en C# avec Aspose.BarCode. Suivez ce guide pour
  générer un code-barres, ajuster la hauteur des barres et enregistrer des images
  PNG.
og_image_alt: Diagram illustrating how to create barcode in C# using Aspose.BarCode
og_title: Créer un code‑barres en C# avec Aspose.BarCode – guide complet
schemas:
- author: Aspose
  dateModified: '2026-09-26'
  description: Learn how to create barcode in C# using Aspose.BarCode. This step‑by‑step
    guide includes a barcode generator example and shows how to adjust bar height.
  headline: How to create barcode in C# with Aspose.BarCode
  type: TechArticle
- description: Learn how to create barcode in C# using Aspose.BarCode. This step‑by‑step
    guide includes a barcode generator example and shows how to adjust bar height.
  name: How to create barcode in C# with Aspose.BarCode
  steps:
  - name: Import required namespaces
    text: '```csharp using System; using Aspose.BarCode.Generation; using Aspose.BarCode;
      ```'
  - name: Initialise the barcode generator
    text: We’ll generate a **Databar Omni‑Directional** symbol that encodes a GTIN‑14
      value. The constructor takes the symbology and the raw data string.
  - name: Set common barcode parameters
    text: 'Two visual parameters are most often tweaked: the X‑dimension (the narrow
      bar width) and the overall bar height.'
  - name: Save the first image (30‑pixel height)
    text: '```csharp // Save the barcode as a 30‑pixel‑high PNG generator.Save("DatabarBarHeight30Pixels.png",
      BarCodeImageFormat.Png); ```'
  - name: Change the bar height to 60 pixels
    text: Now we demonstrate **how to adjust bar height** at runtime. The same `generator`
      instance is reused; only the `BarHeight` property changes.
  - name: Full source code
    text: 'Putting everything together yields a concise, runnable program:'
  - name: Switching to a different symbology
    text: 'If you need a QR code instead of a Databar, replace the `EncodeTypes` value:'
  - name: Using `BarHeight` in millimetres
    text: 'Aspose.BarCode also supports physical units. To set a height of 10 mm:'
  - name: Handling errors
    text: 'If the data string does not conform to the selected symbology, `BarcodeGenerator`
      throws an `ArgumentException`. Wrap the generation logic in a try‑catch block
      to provide a friendly message:'
  type: HowTo
tags:
- barcode
- C#
- Aspose
title: Comment créer un code‑barres en C# avec Aspose.BarCode
url: /fr/python-java/general/how-to-create-barcode-in-c-with-aspose-barcode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Comment créer un code‑barres en C# avec Aspose.BarCode  

Si vous devez **créer des codes‑barres c#** rapidement, Aspose.BarCode fournit une API fluide qui prend en charge les tâches lourdes. Dans ce tutoriel, vous verrez un **exemple complet de générateur de code‑barres**, apprendrez **comment ajuster la hauteur des barres**, et exporterez le résultat au format PNG.  

Que vous construisiez un système de caisse, que vous génériez des étiquettes d’inventaire ou que vous automatisiez des étiquettes d’expédition, la capacité de modifier programmatique la taille visuelle d’un code‑barres est essentielle. Ce guide suppose que vous avez une compréhension de base du C# et d’un environnement de développement tel que Visual Studio 2022.  

## Prérequis  

Avant de commencer, assurez‑vous d’avoir :  

* .NET 6.0 SDK ou version ultérieure installé.  
* Visual Studio 2022 (ou tout IDE C#).  
* Une licence active Aspose.BarCode (l’essai gratuit suffit pour l’apprentissage).  

Vous devrez également ajouter le package NuGet Aspose.BarCode à votre projet :

```bash
dotnet add package Aspose.BarCode
```

> **Astuce :** Si vous prévoyez de générer de nombreux codes‑barres dans une boucle, réutilisez une seule instance de `BarcodeGenerator` et ne modifiez que les paramètres qui changent. Cela réduit les allocations mémoire et améliore les performances.

## Comment créer un code‑barres en C# avec Aspose.BarCode  

Les sections suivantes détaillent chaque étape de l’**exemple de générateur de code‑barres**. Le code est autonome ; copiez‑le dans une nouvelle application console et exécutez‑le.

### Étape 1 : Importer les espaces de noms requis  

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;
```

Ces espaces de noms vous donnent accès à la classe `BarcodeGenerator` et à l’énumération `EncodeTypes`.

### Étape 2 : Initialiser le générateur de code‑barres  

Nous allons générer un symbole **Databar Omni‑Directional** qui encode une valeur GTIN‑14. Le constructeur prend la symbologie et la chaîne de données brute.

```csharp
// Initialise a generator for Databar Omni‑Directional
BarcodeGenerator generator = new BarcodeGenerator(
    EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");
```

La valeur `EncodeTypes.DatabarOmniDirectional` indique à Aspose.BarCode la norme de code‑barres à utiliser. La chaîne de données suit le format d’Identifiant d’Application GS1, couramment utilisé pour les codes‑barres de détail.

### Étape 3 : Définir les paramètres communs du code‑barres  

Deux paramètres visuels sont le plus souvent ajustés : la dimension X (largeur de la barre étroite) et la hauteur globale des barres.  

```csharp
// Set the narrow bar width to 2 pixels
generator.Parameters.Barcode.XDimension.Pixels = 2;

// Set the initial bar height to 30 pixels
generator.Parameters.Barcode.BarHeight.Pixels = 30;
```

La **dimension X** contrôle la densité du code‑barres, tandis que **BarHeight** détermine la taille verticale de chaque barre. Ajuster **BarHeight** est exactement ce qu’il faut lorsque vous souhaitez **modifier la hauteur du code‑barres** pour différents supports d’impression.

### Étape 4 : Enregistrer la première image (hauteur de 30 pixels)  

```csharp
// Save the barcode as a 30‑pixel‑high PNG
generator.Save("DatabarBarHeight30Pixels.png", BarCodeImageFormat.Png);
```

La méthode `Save` écrit l’image rendue sur le disque. Le nom du fichier indique clairement la hauteur utilisée, ce qui facilite la comparaison des différents résultats.

### Étape 5 : Modifier la hauteur des barres à 60 pixels  

Nous montrons maintenant **comment ajuster la hauteur des barres** à l’exécution. La même instance `generator` est réutilisée ; seule la propriété `BarHeight` change.

```csharp
// Increase the bar height to 60 pixels
generator.Parameters.Barcode.BarHeight.Pixels = 60;

// Save the larger barcode
generator.Save("DatabarBarHeight60Pixels.png", BarCodeImageFormat.Png);
```

Comme le générateur conserve tous les autres paramètres (symbologie, données, dimension X), la seule différence visuelle entre les deux fichiers PNG est la taille verticale des barres.

### Code source complet  

En réunissant le tout, on obtient un programme concis et exécutable :

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // 1️⃣ Initialise the generator for Databar Omni‑Directional
            BarcodeGenerator generator = new BarcodeGenerator(
                EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");

            // 2️⃣ Configure visual parameters
            generator.Parameters.Barcode.XDimension.Pixels = 2;   // narrow bar width
            generator.Parameters.Barcode.BarHeight.Pixels = 30; // first height

            // 3️⃣ Save the 30‑pixel‑high image
            generator.Save("DatabarBarHeight30Pixels.png", BarCodeImageFormat.Png);
            Console.WriteLine("Saved 30‑pixel barcode.");

            // 4️⃣ Change the bar height to 60 pixels (how to adjust bar height)
            generator.Parameters.Barcode.BarHeight.Pixels = 60;

            // 5️⃣ Save the 60‑pixel‑high image
            generator.Save("DatabarBarHeight60Pixels.png", BarCodeImageFormat.Png);
            Console.WriteLine("Saved 60‑pixel barcode.");

            // Optional: clean up resources
            generator.Dispose();
        }
    }
}
```

**Résultat attendu**  

L’exécution du programme crée deux fichiers PNG dans le répertoire de travail de l’exécutable :

* `DatabarBarHeight30Pixels.png` – un code‑barres avec une hauteur de barre de 30 px.  
* `DatabarBarHeight60Pixels.png` – le même code‑barres, mais chaque barre est deux fois plus haute.

Ouvrez les images avec n’importe quel visualiseur ; vous verrez que le motif global reste identique tandis que la dimension verticale change, confirmant que l’opération **modifier la hauteur du code‑barres** a réussi.

## Variantes avancées  

### Passer à une symbologie différente  

Si vous avez besoin d’un QR code au lieu d’un Databar, remplacez la valeur `EncodeTypes` :

```csharp
generator = new BarcodeGenerator(EncodeTypes.QR, "https://example.com");
```

Tous les autres paramètres (dimension X, BarHeight) restent applicables lorsqu’ils ont du sens.

### Utiliser `BarHeight` en millimètres  

Aspose.BarCode prend également en charge les unités physiques. Pour définir une hauteur de 10 mm :

```csharp
generator.Parameters.Barcode.BarHeight.Millimeters = 10;
```

C’est pratique lorsque vous générez des codes‑barres pour des mises en page d’impression nécessitant des mesures précises.

### Gestion des erreurs  

Si la chaîne de données ne correspond pas à la symbologie sélectionnée, `BarcodeGenerator` lève une `ArgumentException`. Encapsulez la logique de génération dans un bloc try‑catch pour fournir un message convivial :

```csharp
try
{
    generator.Save("output.png", BarCodeImageFormat.Png);
}
catch (ArgumentException ex)
{
    Console.Error.WriteLine($"Invalid barcode data: {ex.Message}");
}
```

## Questions fréquentes  

* **Le fait de changer BarHeight affecte‑t‑il la lisibilité ?**  
  Le code‑barres reste lisible tant que la dimension X et la zone silencieuse globale respectent les spécifications de la symbologie. Augmenter la hauteur ne fait que rendre les barres plus longues ; cela ne réduit jamais le contraste.

* **Puis‑je définir des hauteurs différentes pour chaque barre ?**  
  Non. La propriété `BarHeight` s’applique uniformément à l’ensemble du symbole. Pour des conceptions à hauteurs variables, il faudrait une routine de rendu personnalisée en dehors du périmètre d’Aspose.BarCode.

* **Le PNG est‑il le meilleur format pour l’impression ?**  
  Le PNG conserve les données pixels sans perte, ce qui le rend idéal pour l’affichage à l’écran. Pour des travaux d’impression haute résolution, envisagez `BarCodeImageFormat.Tiff` ou `Pdf` afin de conserver les informations vectorielles.

## Conclusion  

Vous savez maintenant comment **créer des applications de code‑barres c#** avec Aspose.BarCode, voir un **exemple complet de générateur de code‑barres**, et comprendre **comment ajuster la hauteur des barres** pour répondre à différentes exigences de mise en page. En réutilisant la même instance de générateur et en ne modifiant que `BarHeight`, vous pouvez efficacement **modifier la hauteur du code‑barres** sans reconstruire l’objet entier.

À partir d’ici, vous pouvez explorer :

* Générer d’autres symbologies (`EncodeTypes.Code128`, `EncodeTypes.EAN13`).  
* Exporter vers SVG ou PDF pour des graphiques évolutifs.  
* Intégrer des codes‑barres directement dans des documents Word ou Excel à l’aide d’Aspose.Words ou d’Aspose.Cells.

Bon codage, et profitez de la flexibilité qu’Aspose.BarCode apporte à vos projets de code‑barres en C# !

## Que devez‑vous apprendre ensuite ?


Les tutoriels suivants couvrent des sujets étroitement liés qui s’appuient sur les techniques démontrées dans ce guide. Chaque ressource inclut des exemples de code complets avec des explications pas à pas pour vous aider à maîtriser d’autres fonctionnalités de l’API et explorer des approches d’implémentation alternatives dans vos propres projets.

- [How to Generate and Adjust Barcode Height for One-Dimensional Databar using Aspose.BarCode for .NET](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-barcode-height-adjustment/)
- [How to create a barcode PNG file with adjustable height in C#](/barcode/english/python-java/general/how-to-create-a-barcode-png-file-with-adjustable-height-in-c/)
- [How to Generate Barcode in C# – Complete Aspose.BarCode Guide](/barcode/english/python-java/general/how-to-generate-barcode-in-c-complete-aspose-barcode-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}