---
category: general
date: 2026-08-19
description: Le tutoriel du générateur de codes‑barres C# montre comment générer des
  codes‑barres DataBar Expanded Stacked, personnaliser la taille du code‑barres et
  configurer les lignes et les colonnes.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- c# barcode generator
- how to generate barcode
- create databar barcode
- customize barcode size
- configure databar parameters
language: fr
lastmod: 2026-08-19
og_description: Le tutoriel du générateur de codes-barres C# vous apprend à créer
  des codes-barres DataBar, à personnaliser la taille et à configurer les lignes et
  les colonnes pour un rendu précis.
og_image_alt: Screenshot of a DataBar Expanded Stacked barcode generated with C#
og_title: Générateur de codes-barres C# – guide étape par étape pour les codes-barres
  DataBar personnalisés
schemas:
- author: Aspose
  dateModified: '2026-08-19'
  description: C# barcode generator tutorial shows how to generate DataBar Expanded
    Stacked barcodes, customize barcode size, and configure rows and columns.
  headline: 'C# barcode generator: create custom DataBar barcodes'
  type: TechArticle
- description: C# barcode generator tutorial shows how to generate DataBar Expanded
    Stacked barcodes, customize barcode size, and configure rows and columns.
  name: 'C# barcode generator: create custom DataBar barcodes'
  steps:
  - name: Initialise the barcode generator with sample text
    text: '```csharp using Aspose.BarCode.Generation;'
  - name: Set the number of columns (default rows are used)
    text: '```csharp // Configure the DataBar to use four columns. barcodeGenerator.Parameters.Barcode.DataBar.Columns
      = 4; ```'
  - name: Save the barcode image that uses four columns
    text: '```csharp // Save the barcode as a PNG file. barcodeGenerator.Save("YOUR_DIRECTORY/DatabarCols4.png",
      BarCodeImageFormat.Png); ```'
  - name: Re‑initialise the generator for a new configuration
    text: '```csharp // Create a new generator instance for the same symbology and
      text. barcodeGenerator = new BarcodeGenerator( EncodeTypes.DatabarExpandedStacked,
      "Databar Expanded Stacked long"); ```'
  - name: Set the number of rows (default columns are used)
    text: '```csharp // Configure the DataBar to use three rows. barcodeGenerator.Parameters.Barcode.DataBar.Rows
      = 3; ```'
  - name: Save the barcode image that uses three rows
    text: '```csharp // Save the barcode with three rows. barcodeGenerator.Save("YOUR_DIRECTORY/DatabarRows3.png",
      BarCodeImageFormat.Png); ```'
  type: HowTo
tags:
- barcode
- csharp
- databar
title: 'Générateur de codes-barres C# : créer des codes-barres DataBar personnalisés'
url: /fr/python-java/general/c-barcode-generator-create-custom-databar-barcodes/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Générateur de codes-barres C# : créer des codes-barres DataBar personnalisés

Si vous avez besoin d’un **c# barcode generator** capable de produire des symboles DataBar Expanded Stacked, ce guide vous montre exactement comment générer des images de codes-barres avec des lignes et des colonnes personnalisées. Vous apprendrez à configurer les paramètres databar, ajuster la taille du code-barres et enregistrer le résultat au format PNG.

Créer des codes-barres de façon programmatique supprime les étapes de conception manuelle et garantit une sortie cohérente sur toutes les plateformes. Dans ce tutoriel, vous allez :

* Installer et référencer la bibliothèque Aspose.BarCode pour .NET (ou tout package compatible).
* Créer un générateur de code-barres pour la symbologie DataBar Expanded Stacked.
* **Comment générer des images de code-barres** avec des paramètres de colonne et de ligne spécifiques.
* **Personnaliser la taille du code-barres** en contrôlant les lignes et colonnes DataBar.
* **Configurer les paramètres databar** tels que le texte, le format et la qualité de l’image.

## Prérequis

* SDK .NET 6.0 ou version ultérieure installé.
* Un environnement de développement C# (Visual Studio, VS Code, Rider, etc.).
* Package NuGet `Aspose.BarCode` (ou une bibliothèque équivalente qui fournit `BarcodeGenerator`, `EncodeTypes` et `BarCodeImageFormat`).

Ajoutez le package avec la CLI .NET :

```bash
dotnet add package Aspose.BarCode
```

## Utilisation du générateur de codes-barres C# pour créer des codes-barres DataBar

Les sections suivantes vous guident à travers chaque étape. L’accent principal est mis sur l’API **c# barcode generator**, mais le même modèle s’applique aux autres bibliothèques de codes-barres qui exposent des propriétés similaires.

### Étape 1 : Initialiser le générateur de code-barres avec du texte d’exemple

```csharp
using Aspose.BarCode.Generation;

// Create a generator for DataBar Expanded Stacked with sample text.
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.DatabarExpandedStacked,
    "Databar Expanded Stacked long");
```

*Pourquoi cette étape ?*  
`BarcodeGenerator` est le point d’entrée pour toutes les tâches de création de code-barres. Fournir l’énumération `EncodeTypes.DatabarExpandedStacked` indique à la bibliothèque quelle symbologie utiliser, tandis que l’argument texte devient la valeur lisible par l’homme encodée dans le symbole.

### Étape 2 : Définir le nombre de colonnes (les lignes par défaut sont utilisées)

```csharp
// Configure the DataBar to use four columns.
barcodeGenerator.Parameters.Barcode.DataBar.Columns = 4;
```

*Pourquoi cette étape ?*  
Les symboles DataBar Expanded Stacked sont composés d’éléments linéaires empilés. Ajuster la propriété `Columns` modifie la densité horizontale, vous permettant d’insérer des chaînes de données plus longues sans augmenter la hauteur globale. Cela **personnalise directement la taille du code-barres**.

### Étape 3 : Enregistrer l’image du code-barres qui utilise quatre colonnes

```csharp
// Save the barcode as a PNG file.
barcodeGenerator.Save("YOUR_DIRECTORY/DatabarCols4.png", BarCodeImageFormat.Png);
```

*Ce que vous voyez :*  
L’image enregistrée `DatabarCols4.png` montre un code-barres DataBar plus large que la valeur par défaut car il contient quatre colonnes. Vous pouvez ouvrir le fichier dans n’importe quel visualiseur d’images pour vérifier le résultat.

### Étape 4 : Ré‑initialiser le générateur pour une nouvelle configuration

```csharp
// Create a new generator instance for the same symbology and text.
barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.DatabarExpandedStacked,
    "Databar Expanded Stacked long");
```

*Pourquoi ré‑initialiser ?*  
Modifier la propriété `Rows` tout en conservant le réglage de colonne précédent pourrait produire une combinaison inattendue. Commencer avec une nouvelle instance garantit que seul le paramètre prévu (`Rows`) influence l’image suivante.

### Étape 5 : Définir le nombre de lignes (les colonnes par défaut sont utilisées)

```csharp
// Configure the DataBar to use three rows.
barcodeGenerator.Parameters.Barcode.DataBar.Rows = 3;
```

*Pourquoi cette étape ?*  
La propriété `Rows` contrôle l’empilement vertical. Augmenter le nombre de lignes rend le code-barres plus haut, ce qui peut être utile lorsque l’espace est limité horizontalement mais abondant verticalement. C’est une autre façon de **personnaliser la taille du code-barres**.

### Étape 6 : Enregistrer l’image du code-barres qui utilise trois lignes

```csharp
// Save the barcode with three rows.
barcodeGenerator.Save("YOUR_DIRECTORY/DatabarRows3.png", BarCodeImageFormat.Png);
```

*Résultat :*  
`DatabarRows3.png` montre un code-barres plus haut avec trois lignes empilées, démontrant comment **configurer les paramètres databar** influence l’apparence visuelle.

## Exemple complet exécutable

Voici un programme complet que vous pouvez copier, coller et exécuter. Il inclut tous les imports, la gestion des erreurs et des commentaires pour plus de clarté.

```csharp
using System;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Define output folder (adjust as needed).
        string outputFolder = @"C:\Barcodes";

        // -----------------------------------------------------------------
        // Create barcode with custom column count.
        // -----------------------------------------------------------------
        BarcodeGenerator generator = new BarcodeGenerator(
            EncodeTypes.DatabarExpandedStacked,
            "Databar Expanded Stacked long");

        // Set 4 columns – this widens the symbol.
        generator.Parameters.Barcode.DataBar.Columns = 4;

        // Save the first image.
        string colsPath = System.IO.Path.Combine(outputFolder, "DatabarCols4.png");
        generator.Save(colsPath, BarCodeImageFormat.Png);
        Console.WriteLine($"Saved barcode with 4 columns to: {colsPath}");

        // -----------------------------------------------------------------
        // Create barcode with custom row count.
        // -----------------------------------------------------------------
        generator = new BarcodeGenerator(
            EncodeTypes.DatabarExpandedStacked,
            "Databar Expanded Stacked long");

        // Set 3 rows – this makes the symbol taller.
        generator.Parameters.Barcode.DataBar.Rows = 3;

        // Save the second image.
        string rowsPath = System.IO.Path.Combine(outputFolder, "DatabarRows3.png");
        generator.Save(rowsPath, BarCodeImageFormat.Png);
        Console.WriteLine($"Saved barcode with 3 rows to: {rowsPath}");
    }
}
```

**Sortie attendue**

Exécuter le programme produit deux fichiers PNG :

* `DatabarCols4.png` – un code-barres DataBar large avec quatre colonnes.
* `DatabarRows3.png` – un code-barres DataBar haut avec trois lignes.

Ouvrez les images pour confirmer que les dimensions du code-barres correspondent aux paramètres configurés.

## Questions fréquentes et gestion des cas limites

| Question | Réponse |
|----------|--------|
| *Et si j’ai besoin à la fois de lignes personnalisées **et** de colonnes ?* | Définissez `Rows` **et** `Columns` sur la même instance de `BarcodeGenerator` avant d’appeler `Save`. La bibliothèque combine les deux valeurs pour produire une grille de la taille demandée. |
| *Puis-je changer le format de l’image ?* | Oui. Remplacez `BarCodeImageFormat.Png` par `Jpeg`, `Bmp` ou `Gif` selon votre flux de travail. |
| *Que se passe-t-il lorsque le texte est plus long que ce que le symbole peut contenir ?* | Le générateur lève une `ArgumentException`. Raccourcissez le texte ou augmentez `Columns`/`Rows` pour offrir plus de capacité. |
| *Existe-t-il un moyen de définir le DPI ou la résolution de l’image ?* | Utilisez `generator.Parameters.ImageResolution` pour spécifier le DPI souhaité avant l’enregistrement. Cela **personnalise davantage la taille du code-barres** pour l’impression haute résolution. |
| *La bibliothèque prend‑elle en charge d’autres variantes DataBar ?* | Oui. Remplacez `EncodeTypes.DatabarExpandedStacked` par `DatabarExpanded`, `DatabarLimited`, etc., tout en conservant la même structure de paramètres. |

## Conseils pour une génération fiable de codes-barres

* **Astuce pro :** Vérifiez toujours l’image générée avec un scanner ou une application mobile avant de la déployer en production.  
* **Attention à :** Les répertoires de sortie nuls ou vides—`Save` lèvera une exception si le chemin n’existe pas. Créez le dossier programmatique si nécessaire.  
* **Note de performance :** Réutiliser une seule instance de `BarcodeGenerator` et ne modifier que `Rows` ou `Columns` peut réduire la surcharge de création d’objets lors de la génération de nombreux codes-barres dans une boucle.

## Conclusion

Vous savez maintenant comment utiliser un **c# barcode generator** pour **créer des images de code-barres databar**, **personnaliser la taille du code-barres** et **configurer les paramètres databar** tels que les lignes et les colonnes. En ajustant ces paramètres, vous pouvez adapter les codes-barres à n’importe quelle exigence de mise en page tout en conservant la fiabilité du scan.

Ensuite, explorez des sujets connexes comme **comment générer des PDF de code-barres**, l’intégration de codes-barres dans des rapports, ou le passage à d’autres symbologies (QR, Code‑128, etc.). Expérimentez avec différents `Rows`, `Columns` et résolutions d’image pour trouver la configuration optimale pour votre cas d’utilisation spécifique.

---


## Que devriez‑vous apprendre ensuite ?

Les tutoriels suivants couvrent des sujets étroitement liés qui s’appuient sur les techniques démontrées dans ce guide. Chaque ressource comprend des exemples de code complets et fonctionnels avec des explications étape par étape pour vous aider à maîtriser des fonctionnalités API supplémentaires et explorer des approches d’implémentation alternatives dans vos propres projets.

- [Comment générer et ajuster la hauteur du code-barres pour Databar unidimensionnel avec Aspose.BarCode pour .NET](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-barcode-height-adjustment/)
- [Générer des codes-barres Databar 2D unidimensionnels en utilisant l’API Aspose.BarCode .NET](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-2d-component-configuration/)
- [Générer un code-barres Aspose.BarCode Databar avec l’API .NET – Configuration des lignes et colonnes](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-row-column-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}