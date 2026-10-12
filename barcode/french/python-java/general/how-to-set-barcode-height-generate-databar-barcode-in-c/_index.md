---
category: general
date: 2026-10-12
description: Comment définir la hauteur du code‑barres et générer un code‑barres DataBar
  en C# avec Aspose.BarCode. Suivez un guide étape par étape avec le code complet.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to set barcode
- generate barcode c#
- how to create databar
- create databar barcode
- change barcode height
language: fr
lastmod: 2026-10-12
og_description: Comment définir la hauteur du code-barres en C# et générer un code-barres
  DataBar avec Aspose.BarCode. Découvrez le code complet, pourquoi chaque étape est
  importante et comment modifier la hauteur du code-barres.
og_image_alt: Screenshot showing how to set barcode height in a C# barcode generator
og_title: Comment définir la hauteur du code‑barres et générer un code‑barres DataBar
  en C#
schemas:
- author: Aspose
  dateModified: '2026-10-12'
  description: How to set barcode height and generate a DataBar barcode in C# using
    Aspose.BarCode. Follow a step‑by‑step guide with complete code.
  headline: How to set barcode height, generate DataBar barcode in C#
  type: TechArticle
tags:
- barcode
- C#
- Aspose.BarCode
title: Comment définir la hauteur du code-barres, générer un code-barres DataBar en
  C#
url: /fr/python-java/general/how-to-set-barcode-height-generate-databar-barcode-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Comment définir la hauteur du code‑barres, générer un code‑barres DataBar en C#

Si vous devez **comment définir le code‑barres** dimensions de façon programmatique, ce guide vous montre les étapes exactes. Vous apprendrez à générer un code‑barres DataBar omnidirectionnel, à ajuster sa hauteur et à enregistrer les deux versions au format PNG.

Modifier la hauteur des barres d’un code‑barres est une exigence courante lorsque vous intégrez des codes‑barres dans des tickets de caisse, des étiquettes produit ou des écrans mobiles. L’exemple ci‑dessous utilise la bibliothèque Aspose.BarCode, qui prend en charge toute la gamme des symbologies GS1 DataBar.

## Ce que vous allez réaliser

À la fin de ce tutoriel vous serez capable de :

* **comment définir le code‑barres** hauteur pour un code‑barres DataBar omnidirectionnel  
* **générer le code‑barres c#** qui crée deux images avec des hauteurs différentes  
* comprendre **comment créer databar** et pourquoi la hauteur des barres est importante  
* appliquer la logique de **modifier la hauteur du code‑barres** sans recréer le générateur  

Aucun outil externe n’est requis au‑delà du package NuGet Aspose.BarCode et d’un runtime .NET 6+.

## Prérequis

* SDK .NET 6 ou version ultérieure installé  
* Visual Studio 2022 (ou tout éditeur C#)  
* Aspose.BarCode pour .NET – installer via `dotnet add package Aspose.BarCode`  

> **Astuce pro :** Utilisez la licence d’essai gratuite d’Aspose si vous n’avez pas de clé commerciale ; l’API fonctionne de la même façon.

## Étape 1 : Installer le package Aspose.BarCode

Ouvrez un terminal dans le dossier de votre projet et exécutez :

```bash
dotnet add package Aspose.BarCode
```

Le package ajoute l’espace de noms `Aspose.BarCode`, qui contient la classe `BarcodeGenerator` que nous utiliserons pour **générer le code‑barres c#** images.

## Étape 2 : Créer un générateur de code‑barres DataBar

La première action concrète pour **comment définir le code‑barres** paramètres consiste à instancier `BarcodeGenerator` avec la symbologie souhaitée et la chaîne de données.

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;

// Step 2: Initialize the generator for a DataBar Omni‑directional barcode
var barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.DatabarOmniDirectional, // symbology
    "(01)12345678901231");               // GS1 data payload
```

*Pourquoi c’est important :* `EncodeTypes.DatabarOmniDirectional` produit un DataBar compact et omnidirectionnel qui peut être scanné sous n’importe quel angle — idéal pour les petites étiquettes.

## Étape 3 : Définir les paramètres communs du code‑barres (y compris la hauteur initiale des barres)

Nous répondons maintenant à **comment définir le code‑barres** X‑dimension et hauteur des barres avant d’enregistrer la première image.

```csharp
// Step 3: Configure X‑dimension (module width) and initial bar height
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;    // 2‑pixel modules
barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 30;   // 30‑pixel height
```

La X‑dimension contrôle la largeur globale de chaque barre ; un réglage de 2 pixels donne une image lisible et nette sur la plupart des écrans. L’étape **modifier la hauteur du code‑barres** ultérieure réutilisera le même générateur, ce qui fait gagner du temps et de la mémoire.

## Étape 4 : Enregistrer la première image du code‑barres (hauteur de 30 pixels)

```csharp
// Step 4: Save the 30‑pixel barcode image
barcodeGenerator.Save("DatabarHeight30.png", BarCodeImageFormat.Png);
```

Le fichier `DatabarHeight30.png` contient maintenant un code‑barres DataBar avec une hauteur de barre de 30 pixels.

## Étape 5 : Modifier uniquement la hauteur des barres à 60 pixels

Pour démontrer **modifier la hauteur du code‑barres**, nous modifions simplement la propriété `BarHeight`. Tous les autres paramètres restent inchangés, ce qui est la façon la plus efficace de produire plusieurs tailles à partir d’un seul générateur.

```csharp
// Step 5: Update the bar height to 60 pixels
barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 60;
```

## Étape 6 : Enregistrer la deuxième image du code‑barres (hauteur de 60 pixels)

```csharp
// Step 6: Save the 60‑pixel barcode image
barcodeGenerator.Save("DatabarHeight60.png", BarCodeImageFormat.Png);
```

Vous avez maintenant deux fichiers PNG, chacun avec une hauteur de barre différente mais des données et X‑dimension identiques.

## Exemple complet, exécutable

Voici le programme complet que vous pouvez copier‑coller dans une nouvelle application console (`dotnet new console`) et exécuter immédiatement.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Program
{
    static void Main()
    {
        // Initialize the generator for a DataBar Omni‑directional barcode
        var barcodeGenerator = new BarcodeGenerator(
            EncodeTypes.DatabarOmniDirectional,
            "(01)12345678901231");

        // Set X‑dimension and initial bar height (30 pixels)
        barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
        barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 30;

        // Save the first image (30‑pixel height)
        barcodeGenerator.Save("DatabarHeight30.png", BarCodeImageFormat.Png);
        Console.WriteLine("Saved DatabarHeight30.png");

        // Change only the bar height to 60 pixels
        barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 60;

        // Save the second image (60‑pixel height)
        barcodeGenerator.Save("DatabarHeight60.png", BarCodeImageFormat.Png);
        Console.WriteLine("Saved DatabarHeight60.png");
    }
}
```

### Résultat attendu

L’exécution du programme crée deux fichiers dans le répertoire de travail de l’exécutable :

* `DatabarHeight30.png` – un code‑barres DataBar avec des barres de 30 pixels de haut.  
* `DatabarHeight60.png` – le même code‑barres, mais chaque barre est deux fois plus haute.

Les deux images peuvent être ouvertes avec n’importe quel visualiseur d’images ou intégrées directement dans des PDF, des pages HTML ou des étiquettes imprimées.

## Pourquoi ajuster la hauteur des barres est important

* **Fiabilité du scan :** Certains lecteurs ont du mal avec des barres très courtes sur des supports à basse résolution ; augmenter la hauteur améliore la détection.  
* **Contraintes de conception :** Une application mobile peut nécessiter un code‑barres compact (30 px) tandis qu’un ticket imprimé peut exiger une version plus grande (60 px).  
* **Conformité réglementaire :** Certaines industries imposent une hauteur minimale des barres pour les symboles GS1 DataBar.

En réutilisant la même instance de `BarcodeGenerator`, vous évitez le surcoût de re‑parsing de la chaîne de données, ce qui est particulièrement bénéfique dans des environnements à haut débit.

## Variations courantes et cas limites

| Situation | Ajustement recommandé |
|-----------|-----------------------|
| Besoin d’une X‑dimension différente | Modifier `XDimension.Pixels` avant le premier `Save`. |
| Souhait d’une symbologie différente (p. ex., DataBar Stacked) | Utiliser `EncodeTypes.DatabarStacked` lors de la construction de `BarcodeGenerator`. |
| Nécessité d’intégrer le code‑barres dans un PDF | Utiliser `barcodeGenerator.Save(stream, BarCodeImageFormat.Png)` et ajouter le flux à une bibliothèque PDF. |
| Exécution sous .NET Framework 4.6 | Le même code fonctionne ; il suffit de référencer l’assembly Aspose.BarCode approprié. |

## Astuces pro pour une génération fiable de codes‑barres

* **Mettre en cache le générateur** lorsque vous créez de nombreux codes‑barres avec les mêmes données mais des tailles différentes.  
* **

## Que devez‑vous apprendre ensuite ?

Les tutoriels suivants couvrent des sujets étroitement liés qui s’appuient sur les techniques démontrées dans ce guide. Chaque ressource inclut des exemples de code complets avec des explications pas à pas pour vous aider à maîtriser d’autres fonctionnalités de l’API et explorer des approches d’implémentation alternatives dans vos propres projets.

- [How to Generate and Adjust Barcode Height for One-Dimensional Databar using Aspose.BarCode for .NET](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-barcode-height-adjustment/)
- [How to create databar PNG images with C# and Aspose.BarCode](/barcode/english/python-java/general/how-to-create-databar-png-images-with-c-and-aspose-barcode/)
- [How to generate barcode set custom size and save image in C#](/barcode/english/python-java/general/how-to-generate-barcode-set-custom-size-and-save-image-in-c/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}