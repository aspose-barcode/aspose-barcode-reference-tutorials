---
category: general
date: 2026-07-18
description: Apprenez à générer des images de codes-barres avec un générateur de codes-barres
  .net et à modifier facilement la hauteur du code-barres pour les symboles GS1‑Databar
  omnidirectionnels.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- .net barcode generator
- how to generate barcode
- change barcode height
- GS1‑Databar Omni‑Directional
- barcode image export
language: fr
lastmod: 2026-07-18
og_description: Le générateur de codes-barres .net vous permet de créer rapidement
  des images de codes-barres. Ce guide montre comment générer un code-barres, ajuster
  la hauteur des barres et enregistrer des fichiers PNG.
og_image_alt: Screenshot of a .net barcode generator output showing different bar
  heights
og_title: Modifier la hauteur du code‑barres avec le générateur de code‑barres .NET
schemas:
- author: Aspose
  dateModified: '2026-07-18'
  description: Learn how to generate barcode images with a .net barcode generator
    and easily change barcode height for GS1‑Databar Omni‑Directional symbols.
  headline: .net barcode generator – change barcode height
  type: TechArticle
- description: Learn how to generate barcode images with a .net barcode generator
    and easily change barcode height for GS1‑Databar Omni‑Directional symbols.
  name: .net barcode generator – change barcode height
  steps:
  - name: Why each line matters
    text: '| Line | Reason | |------|--------| | `BarcodeGenerator generator = new
      BarcodeGenerator(...);` | Instantiates the **.net barcode generator** with the
      desired symbology and data payload. The `EncodeTypes.DatabarOmniDirectional`
      enum tells the library to use the GS1‑Databar Omni‑Directional format. |'
  - name: Adjusting the X‑dimension for larger prints
    text: '```csharp generator.Parameters.Barcode.XDimension.Pixels = 4; // Double
      the narrow bar width ``` Increasing the X‑dimension makes the whole barcode
      larger without altering the encoded data. This is handy when you print on large
      labels.'
  - name: Switching output formats
    text: '```csharp generator.Save($"{outFolder}/Databar.svg", BarCodeImageFormat.Svg);
      ``` SVG scales infinitely, which is perfect for web‑based scanners that need
      crisp vectors.'
  - name: Adding human‑readable text
    text: '```csharp generator.Parameters.Barcode.CodeTextVisible = true; generator.Parameters.Barcode.CodeTextAlignment
      = CodeLocation.Below; ``` Enabling `CodeTextVisible` appends the raw data under
      the barcode, useful for verification during testing.'
  type: HowTo
tags:
- barcode
- .net
- image export
title: Générateur de code‑barres .NET – modifier la hauteur du code‑barres
url: /fr/python-java/general/net-barcode-generator-change-barcode-height/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# .net barcode generator – modifier la hauteur du code‑barres

Vous êtes-vous déjà demandé **comment générer des images de code‑barres** sans jongler avec une douzaine d’outils tiers ? Dans l’univers .NET, il existe une méthode étonnamment simple, et l’élément clé est le **.net barcode generator**. En quelques lignes de C#, vous pouvez créer un symbole GS1‑Databar Omni‑Directional, ajuster la hauteur des barres et enregistrer le résultat dans un fichier PNG.

Que vous construisiez un système d’inventaire, une imprimante d’étiquettes d’expédition, ou toute application nécessitant un code scannable, ce tutoriel vous fera passer de zéro à un code‑barres fonctionnel en quelques minutes. Nous passerons en revue le code complet, expliquerons pourquoi chaque paramètre est important, et vous montrerons comment **modifier la hauteur du code‑barres** sans enfreindre la spécification.

## Ce dont vous avez besoin

- .NET 6.0 ou ultérieur (l’API fonctionne de la même façon sur .NET Framework 4.7+)
- Une référence à la bibliothèque de code‑barres (par exemple, Aspose.BarCode for .NET – les mêmes classes sont utilisées par de nombreux kits commerciaux)
- Un environnement de développement (Visual Studio, Rider ou VS Code avec l’extension C#)
- Un dossier où vous avez les droits d’écriture – le tutoriel enregistrera les fichiers PNG dans ce répertoire

C’est tout. Aucun package NuGet supplémentaire en dehors de la bibliothèque de code‑barres elle‑même.

## Utiliser le .net barcode generator pour modifier la hauteur du code‑barres

Voici un **programme console complet et exécutable**. Copiez‑le dans un nouveau projet C#, ajustez le dossier de sortie, puis appuyez sur F5.

```csharp
using System;
using Aspose.BarCode.Generation;   // Namespace for the barcode generator
using Aspose.BarCode;               // For BarCodeImageFormat enum

namespace BarcodeHeightDemo
{
    class Program
    {
        static void Main()
        {
            // 1️⃣ Create a barcode generator for a GS1‑Databar Omni‑Directional symbol.
            // The string "(01)12345678901231" follows the GS1 Application Identifier syntax.
            BarcodeGenerator generator = new BarcodeGenerator(
                EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");

            // 2️⃣ Define common visual parameters.
            // X‑dimension controls the width of the narrowest bar; 2 pixels works well for screen display.
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // 3️⃣ Set the initial bar height to 30 pixels.
            generator.Parameters.Barcode.BarHeight.Pixels = 30;

            // 4️⃣ Save the first image – a compact barcode.
            string outFolder = @"YOUR_DIRECTORY"; // ← replace with a real path
            generator.Save($"{outFolder}/DatabarBarHeight30Pixels.png", BarCodeImageFormat.Png);

            // 5️⃣ Increase the bar height to 60 pixels for a larger, more readable code.
            generator.Parameters.Barcode.BarHeight.Pixels = 60;

            // 6️⃣ Save the second image – a taller barcode.
            generator.Save($"{outFolder}/DatabarBarHeight60Pixels.png", BarCodeImageFormat.Png);

            Console.WriteLine("Two barcode images have been generated successfully.");
        }
    }
}
```

### Pourquoi chaque ligne est importante

| Ligne | Raison |
|------|--------|
| `BarcodeGenerator generator = new BarcodeGenerator(...);` | Instancie le **.net barcode generator** avec la symbologie et les données souhaitées. L’énumération `EncodeTypes.DatabarOmniDirectional` indique à la bibliothèque d’utiliser le format GS1‑Databar Omni‑Directional. |
| `XDimension.Pixels = 2;` | La X‑dimension correspond à la largeur de la barre la plus fine. La régler à *2 pixels* donne une image nette sur la plupart des écrans tout en conservant une petite taille de fichier. |
| `BarHeight.Pixels = 30;` | C’est l’étape **modifier la hauteur du code‑barres** qui détermine la hauteur de chaque barre. Une hauteur de 30 pixels est une bonne valeur par défaut pour les petites étiquettes. |
| `generator.Save(...);` | Enregistre le code‑barres dans un fichier PNG. Le PNG est sans perte, ce qui signifie que les scanners voient exactement le motif généré. |
| `BarHeight.Pixels = 60;` | Ici nous **modifions à nouveau la hauteur du code‑barres** – cette fois à 60 pixels. La bibliothèque re‑rend automatiquement le symbole avec la nouvelle dimension lorsque vous appelez `Save` une seconde fois. |
| `Console.WriteLine(...);` | Vous donne un retour rapide indiquant que le processus s’est terminé sans lever d’exception. |

> **Astuce :** Si vous avez besoin d’une sortie haute résolution pour l’impression, remplacez `BarCodeImageFormat.Png` par `BarCodeImageFormat.Tiff` et augmentez la propriété `Resolution` (par ex., `generator.Parameters.ImageResolution = 300;`). La hauteur des barres sera toujours respectée, simplement rendue à une résolution DPI plus fine.

## Générer des images de code‑barres avec différents paramètres

L’extrait ci‑dessus couvre les bases, mais les scénarios réels exigent souvent des ajustements supplémentaires :

### Ajuster la X‑dimension pour des impressions plus grandes
```csharp
generator.Parameters.Barcode.XDimension.Pixels = 4; // Double the narrow bar width
```
Augmenter la X‑dimension rend le code‑barres entier plus grand sans modifier les données encodées. C’est pratique lorsqu’on imprime sur de grandes étiquettes.

### Changer de format de sortie
```csharp
generator.Save($"{outFolder}/Databar.svg", BarCodeImageFormat.Svg);
```
Le SVG s’adapte à l’infini, ce qui est parfait pour les scanners web qui nécessitent des vecteurs nets.

### Ajouter du texte lisible par l’homme
```csharp
generator.Parameters.Barcode.CodeTextVisible = true;
generator.Parameters.Barcode.CodeTextAlignment = CodeLocation.Below;
```
Activer `CodeTextVisible` ajoute les données brutes sous le code‑barres, utile pour la vérification lors des tests.

## Pièges courants lors de la **modification de la hauteur du code‑barres**

1. **Hauteur trop petite** – Certains scanners exigent une hauteur minimale de barre (souvent 10 mm en unités physiques). Si vous définissez `BarHeight.Pixels` trop bas, l’image générée peut être illisible par un scanner réel. Testez toujours avec le matériel cible.  
2. **X‑dimension et hauteur incompatibles** – Une hauteur de barre très élevée associée à une X‑dimension minuscule peut donner un aspect étiré et provoquer des erreurs de décodage. Visez un ratio équilibré (environ 3 : 1 à 5 : 1) sauf indication contraire de la spécification.  
3. **Oublier de réinitialiser les paramètres** – Le générateur conserve son état entre les sauvegardes. Si vous changez `BarHeight` pour une image puis réutilisez la même instance pour un autre code‑barres, la hauteur précédente restera en vigueur. Réinitialisez la propriété ou créez un nouveau `BarcodeGenerator` pour chaque code‑barres distinct.

## Exemple complet de bout en bout (avec installation NuGet)

Si vous partez de zéro, suivez ces étapes pour lancer le projet :

```bash
dotnet new console -n BarcodeHeightDemo
cd BarcodeHeightDemo
dotnet add package Aspose.BarCode
```

Remplacez le `Program.cs` généré automatiquement par le bloc de code montré précédemment, **n’oubliez pas de remplacer `YOUR_DIRECTORY`** par quelque chose comme `Path.Combine(Environment.CurrentDirectory, "output")`. Ensuite :

```bash
dotnet run
```

Vous devriez voir deux fichiers PNG dans le dossier `output` :

- `DatabarBarHeight30Pixels.png` – un code‑barres compact de 30 pixels de hauteur.  
- `DatabarBarHeight60Pixels.png` – une version de 60 pixels, plus haute.

Les deux images se ressemblent, mais la seconde possède des barres visiblement plus longues, ce qui facilite la lecture par les scanners à basse résolution.

![Barcode height example](/images/barcode-height.png){alt="Sortie du .net barcode generator montrant différentes hauteurs de barres"}

## Récapitulatif & étapes suivantes

Nous avons vu comment **générer des images de code‑barres** à l’aide d’un **.net barcode generator**, affiner la propriété **modifier la hauteur du code‑barres**, et enregistrer les résultats au format PNG. Les points clés sont :

- Instancier le générateur avec le bon `EncodeTypes`.  
- Contrôler la taille visuelle via `XDimension` et `BarHeight`.  
- Appeler `Save` après chaque modification pour créer une nouvelle image.  
- Ajuster la résolution, le format,

## Que devriez‑vous apprendre ensuite ?

Les tutoriels suivants abordent des sujets étroitement liés qui s’appuient sur les techniques présentées dans ce guide. Chaque ressource comprend des exemples de code complets avec des explications pas à pas pour vous aider à maîtriser d’autres fonctionnalités de l’API et explorer des approches d’implémentation alternatives dans vos propres projets.

- [How to generate Aztec barcode with custom aspect ratio using Aspose.BarCode for .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)
- [How to create dotcode extended codetext with Aspose.BarCode for .NET](/barcode/english/net/dotcode-barcode-configuration/dotcode-extended-code-text-configuration/)
- [How to Generate DataMatrix Barcodes (ECC 200) with Aspose.BarCode for .NET](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-ecc-200-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}