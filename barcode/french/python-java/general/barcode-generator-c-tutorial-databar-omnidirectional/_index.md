---
category: general
date: 2026-11-14
description: Tutoriel C# sur le générateur de codes‑barres montrant comment créer
  des codes‑barres DataBar omnidirectionnels, définir la dimension X et ajuster la
  hauteur des barres en pixels.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- barcode generator c# tutorial
- DataBar Omnidirectional
- set bar height
- XDimension pixels
- BarCodeImageFormat PNG
language: fr
lastmod: 2026-11-14
og_description: Le tutoriel C# du générateur de codes‑barres explique étape par étape
  comment générer un code‑barres DataBar omnidirectionnel, définir la XDimension en
  pixels et modifier la hauteur des barres pour la sortie PNG.
og_image_alt: Screenshot of barcode generator C# tutorial output showing a DataBar
  barcode
og_title: Tutoriel C# du générateur de codes-barres – créer des codes-barres DataBar
schemas:
- author: Aspose
  dateModified: '2026-11-14'
  description: Barcode generator C# tutorial that shows how to create DataBar Omnidirectional
    barcodes, set X‑dimension, and adjust bar height in pixels.
  headline: 'Barcode generator C# tutorial: DataBar Omnidirectional'
  type: TechArticle
tags:
- barcode
- C#
- DataBar
- tutorial
title: 'Tutoriel générateur de code-barres C# : DataBar omnidirectionnel'
url: /fr/python-java/general/barcode-generator-c-tutorial-databar-omnidirectional/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Tutoriel générateur de code-barres C# – créer des codes-barres DataBar omnidirectionnels

Si vous recherchez un **tutoriel générateur de code-barres C#**, vous êtes au bon endroit. Ce guide vous montre comment créer un code-barres DataBar omnidirectionnel, configurer la XDimension en pixels et ajuster la hauteur des barres pour produire des images PNG.

Vous verrez un exemple complet et exécutable qui couvre tout, de l'initialisation du générateur à l'enregistrement de plusieurs images avec des hauteurs de barres différentes. Aucune documentation externe n'est requise — il suffit de copier le code, de l'exécuter, et vous disposerez de deux fichiers de code-barres prêts à l'emploi.

## Prérequis

* .NET 6.0 ou version ultérieure installé  
* Une référence à la bibliothèque de code-barres qui fournit `BarcodeGenerator`, `EncodeTypes` et `BarCodeImageFormat` (par exemple, Aspose.BarCode pour .NET)  
* Une connaissance de base de la syntaxe C# et de Visual Studio ou de votre IDE préféré  

> **Astuce :** Si vous utilisez Aspose.BarCode, ajoutez le package NuGet `Aspose.BarCode` à votre projet.

## Tutoriel générateur de code-barres C# – étape 1 : créer le générateur

La première étape consiste à instancier un `BarcodeGenerator` avec le type d'encodage `DatabarOmniDirectional` et les données que vous souhaitez encoder.

```csharp
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Step 1: Create a DataBar Omnidirectional barcode generator with the desired data
        BarcodeGenerator generator = new BarcodeGenerator(
            EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");
```

*Pourquoi c'est important :* `EncodeTypes.DatabarOmniDirectional` indique à la bibliothèque de produire un code-barres lisible sous n'importe quel angle, ce qui est idéal pour l'emballage de détail et la logistique.

## Définir les pixels XDimension pour le code-barres

La X‑dimension définit la largeur du plus petit module (le « pixel ») du code-barres. La définir en pixels vous donne un contrôle précis sur la densité visuelle du code-barres.

```csharp
        // Step 2: Define the X‑dimension (module width) in pixels
        generator.Parameters.Barcode.XDimension.Pixels = 2;
```

*Explication :* Une valeur de `2` pixels produit un code-barres suffisamment net pour la plupart des scanners tout en maintenant une taille de fichier d'image raisonnable.

## Ajuster la hauteur des barres et enregistrer les images

La hauteur des barres détermine la taille verticale des barres. Vous pouvez générer plusieurs images avec des hauteurs différentes en modifiant la propriété `BarHeight.Pixels` et en appelant à nouveau `Save`.

```csharp
        // Step 3: Set the bar height to 30 px and save the image
        generator.Parameters.Barcode.BarHeight.Pixels = 30;
        string outputPath = @"YOUR_DIRECTORY\DatabarBarHeight30Pixels.png";
        generator.Save(outputPath, BarCodeImageFormat.Png);
```

La valeur d'énumération `BarCodeImageFormat.Png` garantit que la sortie est un fichier PNG sans perte, ce qui est le format recommandé pour les graphiques de code-barres car il préserve les dimensions exactes.

## Modifier la hauteur des barres pour créer plusieurs images

Il vous faut souvent le même code-barres à différentes tailles — par exemple, un pour une petite étiquette et un autre pour une grande affiche. Modifiez la hauteur des barres et réutilisez la même instance du générateur :

```csharp
        // Step 4: Change the bar height to 60 px and save a second image
        generator.Parameters.Barcode.BarHeight.Pixels = 60;
        outputPath = @"YOUR_DIRECTORY\DatabarBarHeight60Pixels.png";
        generator.Save(outputPath, BarCodeImageFormat.Png);
    }
}
```

*Cas limite :* Si la hauteur des barres est réglée trop basse (par ex., moins de 10 px), certains scanners peuvent avoir du mal à lire le code. Testez toujours les images générées avec le matériel scanner cible.

## Code source complet

Voici le programme complet que vous pouvez copier‑coller dans un nouveau projet console. Il inclut toutes les directives `using` requises et montre les deux variantes de hauteur de barre.

```csharp
using System;
using Aspose.BarCode.Generation;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // Create a DataBar Omnidirectional barcode generator
            BarcodeGenerator generator = new BarcodeGenerator(
                EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");

            // Set XDimension to 2 pixels
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // First image – 30 px bar height
            generator.Parameters.Barcode.BarHeight.Pixels = 30;
            string path30 = @"YOUR_DIRECTORY\DatabarBarHeight30Pixels.png";
            generator.Save(path30, BarCodeImageFormat.Png);
            Console.WriteLine($"Saved 30 px barcode to {path30}");

            // Second image – 60 px bar height
            generator.Parameters.Barcode.BarHeight.Pixels = 60;
            string path60 = @"YOUR_DIRECTORY\DatabarBarHeight60Pixels.png";
            generator.Save(path60, BarCodeImageFormat.Png);
            Console.WriteLine($"Saved 60 px barcode to {path60}");
        }
    }
}
```

Exécutez le programme, remplacez `YOUR_DIRECTORY` par un chemin de dossier valide, et vous trouverez deux fichiers PNG :

* `DatabarBarHeight30Pixels.png` – barres de 30 px de hauteur  
* `DatabarBarHeight60Pixels.png` – barres de 60 px de hauteur  

![sortie du tutoriel générateur de code-barres C#](images/databar-example.png "Tutoriel générateur de code-barres C# montrant deux images DataBar")

## Questions fréquentes

| Question | Réponse |
|----------|--------|
| **Puis-je changer le format de l'image ?** | Oui. Remplacez `BarCodeImageFormat.Png` par `Jpeg`, `Bmp` ou `Gif` selon vos besoins. PNG est préféré pour la qualité sans perte. |
| **Et si j'ai besoin d'une XDimension différente ?** | Ajustez `generator.Parameters.Barcode.XDimension.Pixels` à n'importe quel entier. Des valeurs plus grandes augmentent la largeur globale du code-barres. |
| **Le DataBar Omnidirectional convient-il à la numérisation mobile ?** | Oui, à condition que la taille imprimée respecte la taille minimale du module du scanner (généralement 0,33 mm). La XDimension basée sur les pixels vous aide à satisfaire cette exigence. |
| **Comment intégrer le code-barres dans un PDF ?** | Après avoir enregistré le PNG, utilisez une bibliothèque PDF (par ex., iTextSharp) pour insérer l'image dans une page PDF. |

## Conclusion

Ce **tutoriel générateur de code-barres C#** vous a montré comment créer un code-barres DataBar Omnidirectional, définir la XDimension en pixels et générer des fichiers PNG avec différentes hauteurs de barres. Vous disposez maintenant d'un extrait de code réutilisable que vous pouvez adapter à tout projet C# nécessitant la création de code-barres.

### Et après ?

* Explorez d'autres `EncodeTypes` comme `Code128` ou `QR` pour élargir votre répertoire de code-barres.  
* Combinez le PNG généré avec une bibliothèque de génération PDF pour produire des factures imprimables.  
* Expérimentez avec `generator.Parameters.Barcode.Color` pour ajouter des couleurs personnalisées tout en respectant les spécifications du scanner.

N'hésitez pas à modifier l'exemple, essayer des hauteurs de barres supplémentaires ou changer le format de sortie. Bon codage !

## Que devriez‑vous apprendre ensuite ?

Les tutoriels suivants couvrent des sujets étroitement liés qui s'appuient sur les techniques démontrées dans ce guide. Chaque ressource comprend des exemples de code complets et fonctionnels avec des explications étape par étape pour vous aider à maîtriser des fonctionnalités API supplémentaires et explorer des approches d'implémentation alternatives dans vos propres projets.

- [Comment définir la largeur et ajuster la hauteur d'un code-barres GS1 DataBar omnidirectionnel](/barcode/english/python-java/general/how-to-set-width-and-adjust-height-for-a-gs1-databar-omni-di/)
- [Comment définir la hauteur du code-barres, générer un code-barres DataBar en C#](/barcode/english/python-java/general/how-to-set-barcode-height-generate-databar-barcode-in-c/)
- [Comment créer un code-barres Databar omnidirectionnel en C#](/barcode/english/python-java/general/how-to-create-omnidirectional-databar-barcode-in-c/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}