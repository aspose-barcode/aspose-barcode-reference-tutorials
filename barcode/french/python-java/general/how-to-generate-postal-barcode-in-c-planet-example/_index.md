---
category: general
date: 2026-10-28
description: Générez un code‑barres postal en C# en utilisant le format Planet. Cet
  exemple de code‑barres Planet montre comment définir la largeur du code‑barres et
  enregistrer les barres remplies et vides.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate postal barcode
- set barcode width
- planet barcode example
language: fr
lastmod: 2026-10-28
og_description: Générez un code‑barres postal en C# avec un exemple complet de code‑barres
  Planet. Apprenez à définir la largeur du code‑barres, à produire des barres remplies
  et à créer des images de barres vides.
og_image_alt: Screenshot of a generated Planet postal barcode saved as PNG
og_title: Générer un code‑barres postal en C# – guide étape par étape
schemas:
- author: Aspose
  dateModified: '2026-10-28'
  description: Generate postal barcode in C# using the Planet format. This planet
    barcode example shows how to set barcode width and save both filled and empty
    bars.
  headline: How to generate postal barcode in C# – planet example
  type: TechArticle
- description: Generate postal barcode in C# using the Planet format. This planet
    barcode example shows how to set barcode width and save both filled and empty
    bars.
  name: How to generate postal barcode in C# – planet example
  steps:
  - name: Build the project (`dotnet build`).
    text: Build the project (`dotnet build`).
  - name: Run the executable (`dotnet run`).
    text: Run the executable (`dotnet run`).
  - name: Locate `PostalPlanetFilledBars.png` and `PostalPlanetEmptyBars.png` in the
      `bin/Debug/net6.0` folder.
    text: Locate `PostalPlanetFilledBars.png` and `PostalPlanetEmptyBars.png` in the
      `bin/Debug/net6.0` folder.
  - name: Open each image; you should see a series of vertical bars representing the
      numeric string
    text: Open each image; you should see a series of vertical bars representing the
      numeric string
  type: HowTo
tags:
- barcode
- C#
- Aspose.BarCode
title: Comment générer un code‑barres postal en C# – exemple de planète
url: /fr/python-java/general/how-to-generate-postal-barcode-in-c-planet-example/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Comment générer un code-barres postal en C# – exemple Planet

Si vous devez générer un code-barres postal en C#, ce guide vous accompagne à travers une solution complète. Vous verrez un exemple pratique de code-barres Planet qui encode une chaîne numérique, vous permet de définir la largeur du code-barres et enregistre à la fois les images de barres remplies et vides.

Créer un code-barres postal ne nécessite pas de pipeline de construction complexe. À la fin de ce tutoriel, vous pourrez intégrer la génération de code-barres dans n'importe quelle application .NET, personnaliser la X‑dimension et choisir si les barres apparaissent remplies ou vides.

## Prérequis

* .NET 6.0 SDK ou version ultérieure installé  
* Un environnement de développement C# (Visual Studio, VS Code ou Rider)  
* Le package NuGet **Aspose.BarCode for .NET** (version 23.10 ou plus récent)  

Vous pouvez ajouter le package avec la commande suivante :

```bash
dotnet add package Aspose.BarCode
```

Les extraits de code ci‑dessous supposent que vous avez ajouté `using Aspose.BarCode.Generation;` en haut de votre fichier.

## Générer un code-barres postal avec la symbologie Planet

La première étape consiste à créer une instance de `BarcodeGenerator` qui utilise la symbologie Planet. Planet est un format de code-barres postal utilisé par plusieurs services postaux nationaux.

```csharp
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Create a Planet barcode generator with the data to encode
        BarcodeGenerator barcodeGenerator = new BarcodeGenerator(EncodeTypes.Planet, "123456");

        // Additional configuration will be applied here (see next steps)

        // Save the filled‑bars image
        barcodeGenerator.Save("PostalPlanetFilledBars.png", BarCodeImageFormat.Png);

        // Switch to empty bars and save the second image
        barcodeGenerator.Parameters.Barcode.FilledBars = false;
        barcodeGenerator.Save("PostalPlanetEmptyBars.png", BarCodeImageFormat.Png);
    }
}
```

**Pourquoi c’est important :**  
`EncodeTypes.Planet` indique à la bibliothèque d’utiliser la norme de code-barres Planet, qui encode des données numériques sous forme de barres et d’espaces. Le constructeur reçoit la chaîne de données (`"123456"` dans ce cas) que vous souhaitez encoder.

L’exécution du programme génère deux fichiers PNG dans le répertoire de travail de l’exécutable :

* **PostalPlanetFilledBars.png** – les barres sont rendues sous forme de rectangles noirs solides.  
* **PostalPlanetEmptyBars.png** – les barres sont rendues sous forme de rectangles blancs avec un contour noir, utile pour l’impression sur des fonds sombres.

## Définir la largeur du code-barres (X‑dimension) en pixels

La taille visuelle d’un code-barres est contrôlée par la X‑dimension, qui définit la largeur d’une seule barre. Ajuster cette valeur garantit que le code-barres sera correctement scanné à la résolution d’impression prévue.

```csharp
// Define the width of each bar (X‑dimension) in pixels
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 4;
```

**Pourquoi vous devez le définir :**  
Une X‑dimension plus grande rend le code-barres plus facile à scanner avec des scanners basse résolution, tandis qu’une valeur plus petite réduit la taille globale de l’image pour une impression haute densité. La largeur par défaut est de 2 pixels ; 4 pixels est un compromis courant pour la plupart des imprimantes de bureau.

Vous pouvez expérimenter avec différentes valeurs :

| Pixels | Cas d’utilisation typique |
|--------|---------------------------|
| 2      | Étiquettes haute densité |
| 4      | Impression bureautique standard |
| 6‑8    | Signalétique grand format |

**Astuce :** Testez toujours le code-barres généré avec votre scanner cible après avoir modifié la X‑dimension.

## Exemple de code-barres Planet – barres remplies vs vides

Un code-barres Planet peut être rendu avec des barres solides (remplies) ou des barres contournées (vides). La propriété `FilledBars` bascule ce comportement.

```csharp
// Save the barcode with the default filled bars
barcodeGenerator.Save("PostalPlanetFilledBars.png", BarCodeImageFormat.Png);

// Configure the generator to produce empty (unfilled) bars
barcodeGenerator.Parameters.Barcode.FilledBars = false;

// Save the barcode with empty bars
barcodeGenerator.Save("PostalPlanetEmptyBars.png", BarCodeImageFormat.Png);
```

**Pourquoi vous pourriez choisir des barres vides :**  
Les barres vides améliorent le contraste sur les emballages de couleur sombre, car l’intérieur blanc de chaque barre ressort sur un fond sombre. Les barres remplies sont le réglage par défaut et fonctionnent bien sur des supports de couleur claire.

**Résultat attendu :**  

*Les deux images affichent les mêmes données encodées (`123456`).* La seule différence visuelle est le style des barres. Voici une description textuelle de ce que vous verrez :

* **Image à barres remplies :** Barres verticales noires solides sur fond blanc.  
* **Image à barres vides :** Contours noirs formant le même motif, avec des intérieurs blancs.

Vous pouvez ouvrir les fichiers PNG dans n'importe quel visualiseur d'images pour vérifier que le motif correspond à la spécification Planet.

## Personnaliser des propriétés supplémentaires du code-barres (facultatif)

Bien que les étapes principales ci‑dessus couvrent la plupart des scénarios, vous pourriez vouloir affiner d’autres paramètres :

| Property | Description | Valeur typique |
|----------|-------------|----------------|
| `Barcode.Color` | Foreground color of the bars | `System.Drawing.Color.Black` |
| `Barcode.BackgroundColor` | Background fill color | `System.Drawing.Color.White` |
| `Barcode.CodeText` | Human‑readable text displayed below the barcode | Same as encoded data or a custom label |
| `Barcode.ImageFormat` | Output format (PNG, JPEG, BMP, etc.) | `BarCodeImageFormat.Png` |

Exemple de définition d’une couleur de premier plan personnalisée :

```csharp
barcodeGenerator.Parameters.Barcode.Color = System.Drawing.Color.DarkBlue;
```

Ces ajustements facultatifs vous aident à correspondre à l’image de marque de l’entreprise ou à répondre à des exigences d’impression spécifiques.

## Pièges courants et comment les éviter

| Problème | Cause | Solution |
|----------|-------|----------|
| Le code-barres est illisible | X‑dimension trop petite pour le DPI de l’imprimante | Augmentez `XDimension.Pixels` à 4 ou plus |
| Le fichier image est corrompu | Permissions d’écriture manquantes dans le dossier cible | Utilisez un chemin absolu ou assurez‑vous que le répertoire existe |
| Mauvaise symbologie utilisée | Passer `EncodeTypes.Code128` au lieu de `EncodeTypes.Planet` | Vérifiez que l’argument `EncodeTypes` correspond au format postal |

**Astuce pro :** Générez toujours un code-barres de test et scannez‑le avec le matériel prévu avant de le déployer en production.

## Exemple complet et exécutable

Ci‑dessous se trouve une application console autonome qui intègre toutes les étapes abordées. Copiez le code dans un nouveau projet console .NET et exécutez‑le pour voir les deux fichiers PNG apparaître dans le dossier de sortie.

```csharp
using System;
using Aspose.BarCode.Generation;

namespace PostalBarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // 1️⃣ Create a Planet barcode generator with the data to encode
            BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Planet, "123456");

            // 2️⃣ Set the width of each bar (X‑dimension) to 4 pixels
            generator.Parameters.Barcode.XDimension.Pixels = 4;

            // 3️⃣ Save the barcode with the default filled bars
            generator.Save("PostalPlanetFilledBars.png", BarCodeImageFormat.Png);
            Console.WriteLine("Saved filled‑bars barcode as PostalPlanetFilledBars.png");

            // 4️⃣ Configure the generator to produce empty (unfilled) bars
            generator.Parameters.Barcode.FilledBars = false;

            // 5️⃣ Save the barcode with empty bars
            generator.Save("PostalPlanetEmptyBars.png", BarCodeImageFormat.Png);
            Console.WriteLine("Saved empty‑bars barcode as PostalPlanetEmptyBars.png");
        }
    }
}
```

**Étapes de vérification :**  

1. Construisez le projet (`dotnet build`).  
2. Exécutez l’exécutable (`dotnet run`).  
3. Localisez `PostalPlanetFilledBars.png` et `PostalPlanetEmptyBars.png` dans le dossier `bin/Debug/net6.0`.  
4. Ouvrez chaque image ; vous devriez voir une série de barres verticales représentant la chaîne numérique


## Que devriez‑vous apprendre ensuite ?

Les tutoriels suivants couvrent des sujets étroitement liés qui s’appuient sur les techniques démontrées dans ce guide. Chaque ressource comprend des exemples de code complets et fonctionnels avec des explications étape par étape pour vous aider à maîtriser des fonctionnalités supplémentaires de l’API et à explorer des approches d’implémentation alternatives dans vos propres projets.

- [Comment créer un code-barres planet avec des barres remplies et vides](/barcode/english/python-java/general/how-to-create-planet-barcode-with-filled-and-empty-bars/)
- [Comment définir la largeur et générer un code-barres Planet en C#](/barcode/english/python-java/general/how-to-set-width-and-generate-a-planet-barcode-in-c/)
- [Créer un code-barres postal en C# – Exemple complet du générateur](/barcode/english/python-java/general/create-postal-barcode-in-c-full-generator-example/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}