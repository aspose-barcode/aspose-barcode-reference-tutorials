---
category: general
date: 2026-08-22
description: Comment générer un code‑barres en C# avec Aspose.BarCode. Apprenez à
  créer une image de code‑barres en C# étape par étape, désactiver le composant 2‑D
  et enregistrer des fichiers PNG.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to generate barcode
- create barcode image c#
language: fr
lastmod: 2026-08-22
og_description: Comment générer un code‑barres en C# avec Aspose.BarCode. Ce tutoriel
  vous montre comment créer une image de code‑barres en C# en utilisant DataBar Expanded,
  activer le composant 2‑D et enregistrer des fichiers PNG.
og_image_alt: C# code screenshot generating a DataBar Expanded barcode image without
  the 2‑D component
og_title: Comment générer un code-barres en C# – guide complet pour créer une image
  de code-barres en C#
schemas:
- author: Aspose
  dateModified: '2026-08-22'
  description: How to generate barcode in C# using Aspose.BarCode. Learn to create
    barcode image c# step‑by‑step, disable the 2‑D component, and save PNG files.
  headline: How to generate barcode in C# – create barcode image c# with DataBar Expanded
  type: TechArticle
tags:
- barcode
- C#
- Aspose.BarCode
- image generation
title: Comment générer un code‑barres en C# – créer une image de code‑barres C# avec
  DataBar Expanded
url: /fr/python-java/general/how-to-generate-barcode-in-c-create-barcode-image-c-with-dat/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Comment générer un code-barres en C# – créer une image de code‑barres c# avec DataBar Expanded

Générer un code‑barres en C# est une exigence fréquente lorsque vous devez intégrer des données lisibles par machine dans vos applications. Ce guide vous montre comment créer une image de code‑barres c# en utilisant la bibliothèque Aspose.BarCode, désactiver le composant composite 2‑D, et enregistrer le résultat au format PNG.

Vous verrez un programme complet et exécutable, une explication de chaque option de configuration, ainsi que des conseils pour personnaliser la sortie. Aucun document externe n’est requis — seulement le code ci‑dessous et un environnement de développement .NET.

## Prérequis

Avant de commencer, assurez‑vous d’avoir :

* SDK .NET 6.0 ou version ultérieure installé  
* Visual Studio 2022 (ou tout IDE supportant .NET)  
* Package NuGet Aspose.BarCode for .NET (`Aspose.BarCode`)  

Vous pouvez ajouter le package avec la commande suivante :

```bash
dotnet add package Aspose.BarCode
```

La bibliothèque fournit la classe `BarcodeGenerator` utilisée tout au long de ce tutoriel.

## Étape 1 : Configurer le projet et importer les espaces de noms

Créez une nouvelle application console et importez les espaces de noms requis :

```csharp
using System;
using Aspose.BarCode.Generation;

namespace BarcodeDemo
{
    internal class Program
    {
        private static void Main()
        {
            // The rest of the code lives here
        }
    }
}
```

L’espace de noms `Aspose.BarCode.Generation` contient toutes les classes nécessaires pour configurer et rendre les codes‑barres.

## Étape 2 : Initialiser le générateur de code‑barres DataBar Expanded

La première ligne fonctionnelle crée un `BarcodeGenerator` pour la symbologie **DataBar Expanded** et fournit la chaîne de données brute. La chaîne de données suit le format d’identifiant d’application GS1 `(01)12345678901231`.

```csharp
// Step 2: Create a DataBar Expanded barcode generator with the desired data
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.DatabarExpanded, "(01)12345678901231");
```

La création du générateur alloue le canevas bitmap interne, vous permettant d’ajuster la taille et l’apparence avant le rendu.

## Étape 3 : Définir la largeur du module (dimension X)

La dimension X contrôle la largeur de l’élément le plus petit du code‑barres. La définir en pixels vous donne un contrôle précis sur la taille finale de l’image.

```csharp
// Step 3: Set the X‑dimension (module width) in pixels
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

Une valeur de `2` pixels fonctionne bien pour l’affichage à l’écran ; augmentez‑la pour des impressions à plus haute résolution.

## Étape 4 : Désactiver le composant composite 2‑D

DataBar Expanded peut éventuellement inclure un composant 2‑D qui transporte des informations supplémentaires. Pour générer un code‑barres **sans** ce composant, réglez le drapeau sur `false`.

```csharp
// Step 4: Disable the 2‑D composite component of the DataBar barcode
barcodeGenerator.Parameters.Barcode.DataBar.Is2DCompositeComponent = false;
```

Désactiver le composant réduit la complexité visuelle et produit un fichier PNG plus petit.

## Étape 5 : Enregistrer l’image du code‑barres sans le composant 2‑D

Choisissez un répertoire de sortie et écrivez l’image sur le disque. L’énumération `BarCodeImageFormat.Png` garantit un fichier PNG sans perte.

```csharp
// Step 5: Save the barcode image without the 2‑D component
string outputDir = "YOUR_DIRECTORY/"; // replace with your actual path
barcodeGenerator.Save($"{outputDir}Databar2DComponentDisabled.png", BarCodeImageFormat.Png);
```

Après cet appel, `Databar2DComponentDisabled.png` contient un code‑barres DataBar Expanded propre.

## Étape 6 : Activer le composant composite 2‑D

Si vous avez besoin de la couche de données supplémentaire, réactivez le drapeau. La même instance du générateur peut être réutilisée, ce qui évite de créer un second objet.

```csharp
// Step 6: Enable the 2‑D composite component
barcodeGenerator.Parameters.Barcode.DataBar.Is2DCompositeComponent = true;
```

## Étape 7 : Enregistrer l’image du code‑barres avec le composant 2‑D activé

Rendez la seconde image en utilisant les mêmes paramètres, à l’exception du drapeau 2‑D.

```csharp
// Step 7: Save the barcode image with the 2‑D component enabled
barcodeGenerator.Save($"{outputDir}Databar2DComponentEnabled.png", BarCodeImageFormat.Png);
```

Maintenant `Databar2DComponentEnabled.png` montre le code‑barres avec le motif 2‑D additionnel.

## Code source complet

Copiez l’ensemble du fragment ci‑dessous dans `Program.cs` et exécutez le projet. Le programme crée les deux fichiers PNG dans le dossier que vous spécifiez.

```csharp
using System;
using Aspose.BarCode.Generation;

namespace BarcodeDemo
{
    internal class Program
    {
        private static void Main()
        {
            // Create a DataBar Expanded barcode generator with the desired data
            BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
                EncodeTypes.DatabarExpanded, "(01)12345678901231");

            // Set the X‑dimension (module width) in pixels
            barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;

            // Define the output directory (change to a valid path on your machine)
            string outputDir = "YOUR_DIRECTORY/";

            // ---------- First image: 2‑D component disabled ----------
            barcodeGenerator.Parameters.Barcode.DataBar.Is2DCompositeComponent = false;
            barcodeGenerator.Save($"{outputDir}Databar2DComponentDisabled.png",
                                 BarCodeImageFormat.Png);

            // ---------- Second image: 2‑D component enabled ----------
            barcodeGenerator.Parameters.Barcode.DataBar.Is2DCompositeComponent = true;
            barcodeGenerator.Save($"{outputDir}Databar2DComponentEnabled.png",
                                 BarCodeImageFormat.Png);

            Console.WriteLine("Barcode images generated successfully.");
        }
    }
}
```

### Résultat attendu

L’exécution du programme affiche :

```
Barcode images generated successfully.
```

et crée deux fichiers :

* `Databar2DComponentDisabled.png` – code‑barres sans le composant 2‑D  
* `Databar2DComponentEnabled.png` – code‑barres avec le composant 2‑D  

Ouvrez les PNG avec n’importe quel visualiseur d’images pour vérifier la différence visuelle.

## Variations courantes et cas limites

| Situation | Ajustement |
|-----------|------------|
| **Symbologie différente** | Remplacez `EncodeTypes.DatabarExpanded` par une autre valeur, par ex. `EncodeTypes.Code128`. |
| **Résolution supérieure** | Augmentez `XDimension.Pixels` à 4 ou 5, ou définissez `Resolution` dans `barcodeGenerator.Parameters.Image`. |
| **Autres formats d’image** | Utilisez `BarCodeImageFormat.Jpeg`, `BarCodeImageFormat.Bmp` ou `BarCodeImageFormat.Svg`. |
| **Exécution dans une application web** | Diffusez les octets de l’image directement dans la réponse HTTP au lieu de les enregistrer sur disque. |
| **Gestion de la mémoire** | Encapsulez le générateur dans un bloc `using` si vous ciblez .NET Framework afin de libérer les ressources non gérées. |

## Astuces professionnelles

* **Réutiliser le générateur** – Modifier uniquement le drapeau 2‑D évite de réinstancier l’objet, ce qui économise des cycles CPU.  
* **Valider les données** – Les données GS1 doivent respecter la longueur exacte et les règles de checksum ; une entrée invalide lève une `ArgumentException`.  
* **Traitement par lots** – Parcourez une collection de chaînes de données, basculez le drapeau 2‑D selon les besoins, et enregistrez chaque image avec un nom de fichier unique.  

## Conclusion

Vous savez maintenant comment générer un code‑barres en C# et créer une image de code‑barres c# avec un contrôle complet du composant composite 2‑D. L’exemple montre comment initialiser le générateur, configurer la dimension X, basculer le composant, et enregistrer des fichiers PNG. À partir d’ici, vous pouvez explorer d’autres symbologies, intégrer les images dans des PDF, ou incorporer la génération de codes‑barres dans des services ASP.NET Core.

--- 

*Prochaines étapes* : essayez de générer des QR codes, expérimentez différentes résolutions d’image, ou intégrez les PNG générés dans un PDF avec Aspose.PDF. Ces extensions s’appuient sur la même API `BarcodeGenerator` et maintiennent la cohérence de votre flux de travail.


## Que devez‑vous apprendre ensuite ?


Les tutoriels suivants couvrent des sujets étroitement liés qui s’appuient sur les techniques démontrées dans ce guide. Chaque ressource comprend des exemples de code complets avec des explications pas à pas pour vous aider à maîtriser des fonctionnalités supplémentaires de l’API et explorer des approches d’implémentation alternatives dans vos propres projets.

- [How to Generate DataMatrix Barcodes Using Aspose.BarCode for .NET – Step‑by‑Step Guide](/barcode/english/net/datamatrix-barcode-configuration/)
- [How to Generate and Adjust Barcode Height for One-Dimensional Databar using Aspose.BarCode for .NET](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-barcode-height-adjustment/)
- [How to generate Aztec barcode with custom aspect ratio using Aspose.BarCode for .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}