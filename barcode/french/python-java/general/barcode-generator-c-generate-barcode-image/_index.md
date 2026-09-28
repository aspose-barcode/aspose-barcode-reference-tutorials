---
category: general
date: 2026-08-03
description: Le tutoriel de génération de code‑barres en C# montre comment créer une
  image de code‑barres avec Aspose.BarCode, définir les colonnes et les lignes, et
  enregistrer des fichiers PNG pour DataBar Expanded Stacked.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- barcode generator c#
- generate barcode image
language: fr
lastmod: 2026-08-03
og_description: Le tutoriel du générateur de code‑barres C# explique comment créer
  une image de code‑barres avec Aspose.BarCode, configurer les colonnes et lignes
  DataBar Expanded Stacked, puis enregistrer des fichiers PNG.
og_image_alt: Screenshot of a DataBar Expanded Stacked barcode generated with C#
og_title: Générateur de code-barres C# – guide étape par étape pour générer une image
  de code-barres
schemas:
- author: Aspose
  dateModified: '2026-08-03'
  description: Barcode generator C# tutorial shows how to generate barcode image with
    Aspose.BarCode, set columns and rows, and save PNG files for DataBar Expanded
    Stacked.
  headline: Barcode generator C# – generate barcode image
  type: TechArticle
tags:
- barcode
- C#
- Aspose.BarCode
title: Générateur de code-barres C# – générer une image de code-barres
url: /fr/python-java/general/barcode-generator-c-generate-barcode-image/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Générateur de code-barres C# – générer une image de code-barres

Si vous avez besoin d'un générateur de code-barres C# capable de créer une image de code-barres pour DataBar Expanded Stacked, ce guide vous accompagne tout au long du processus complet. Vous apprendrez comment configurer les paramètres de colonnes et de lignes, enregistrer le résultat au format PNG, et adapter le code à d'autres symbologies.

Générer des images de code-barres par programme élimine les étapes manuelles et garantit la cohérence sur les factures, les étiquettes d'expédition et les systèmes d'inventaire. Ce tutoriel couvre tout ce dont vous avez besoin, de la configuration du projet au code source complet, afin que vous puissiez exécuter l'exemple immédiatement.

## Prérequis

Avant de commencer, assurez-vous d'avoir :

* .NET 6.0 ou version ultérieure installé  
* Un IDE tel que Visual Studio 2022 (tout éditeur supportant C# fonctionne)  
* Une licence pour **Aspose.BarCode for .NET** – l'évaluation gratuite fonctionne pour les tests  
* Familiarité de base avec la syntaxe C#  

Si l'un de ces éléments manque, installez le SDK .NET depuis dotnet.microsoft.com et obtenez le package NuGet Aspose.BarCode avec :

```bash
dotnet add package Aspose.BarCode
```

## Étape 1 : Créer un projet de générateur de code-barres C# 

Créez une nouvelle application console et ajoutez les directives `using` requises :

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // The implementation starts in the next sections
        }
    }
}
```

La classe `BarcodeGenerator` est le cœur de l'API du générateur de code-barres C#. Elle reçoit le type de symbologie et le texte à encoder.

## Étape 2 : Générer un code-barres DataBar Expanded Stacked et définir les colonnes

Le premier exemple crée un code-barres avec quatre colonnes. Modifier la propriété `Columns` change la densité visuelle de la symbologie DataBar Expanded Stacked.

```csharp
// Step 2: Create a barcode generator for DataBar Expanded Stacked
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.DatabarExpandedStacked, "Databar Expanded Stacked long");

// Set the number of columns to 4
barcodeGenerator.Parameters.Barcode.DataBar.Columns = 4;

// Save the barcode image as PNG
string colsPath = @"YOUR_DIRECTORY\DatabarCols4.png";
barcodeGenerator.Save(colsPath, BarCodeImageFormat.Png);

Console.WriteLine($"Barcode with 4 columns saved to {colsPath}");
```

**Pourquoi c'est important :** Le nombre de colonnes influence la quantité de données pouvant être stockées dans un espace compact. Le régler à 4 produit un code-barres plus large qui reste lisible par la plupart des scanners.

## Étape 3 : Générer un code-barres avec un nombre de lignes personnalisé

Le deuxième exemple montre comment contrôler la disposition verticale en définissant la propriété `Rows`. Une configuration à trois lignes est utile lorsque vous avez besoin d'un code-barres plus haut pour un espace horizontal limité.

```csharp
// Step 3: Create a second barcode generator for the same type
BarcodeGenerator barcodeGeneratorRows = new BarcodeGenerator(
    EncodeTypes.DatabarExpandedStacked, "Databar Expanded Stacked long");

// Set the number of rows to 3
barcodeGeneratorRows.Parameters.Barcode.DataBar.Rows = 3;

// Save the barcode image as PNG
string rowsPath = @"YOUR_DIRECTORY\DatabarRows3.png";
barcodeGeneratorRows.Save(rowsPath, BarCodeImageFormat.Png);

Console.WriteLine($"Barcode with 3 rows saved to {rowsPath}");
```

**Pourquoi c'est important :** Ajuster les lignes vous permet d'adapter le code-barres à une colonne étroite tout en préservant la lisibilité. Le générateur de code-barres C# recalcule automatiquement la taille du module pour respecter la spécification.

## Étape 4 : Exemple complet et exécutable

Ci-dessous se trouve un programme autonome qui combine les étapes précédentes. Copiez le code dans `Program.cs`, remplacez `YOUR_DIRECTORY` par un chemin de dossier existant, puis exécutez l'application.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // ---------- Generate barcode with 4 columns ----------
            BarcodeGenerator colsGenerator = new BarcodeGenerator(
                EncodeTypes.DatabarExpandedStacked, "Databar Expanded Stacked long");

            colsGenerator.Parameters.Barcode.DataBar.Columns = 4;

            string colsFile = @"YOUR_DIRECTORY\DatabarCols4.png";
            colsGenerator.Save(colsFile, BarCodeImageFormat.Png);
            Console.WriteLine($"Generated barcode image with columns saved to {colsFile}");

            // ---------- Generate barcode with 3 rows ----------
            BarcodeGenerator rowsGenerator = new BarcodeGenerator(
                EncodeTypes.DatabarExpandedStacked, "Databar Expanded Stacked long");

            rowsGenerator.Parameters.Barcode.DataBar.Rows = 3;

            string rowsFile = @"YOUR_DIRECTORY\DatabarRows3.png";
            rowsGenerator.Save(rowsFile, BarCodeImageFormat.Png);
            Console.WriteLine($"Generated barcode image with rows saved to {rowsFile}");
        }
    }
}
```

### Sortie attendue

Lorsque vous exécutez le programme, deux fichiers PNG apparaissent dans le répertoire cible :

* **DatabarCols4.png** – un code-barres DataBar Expanded Stacked avec quatre colonnes  
* **DatabarRows3.png** – les mêmes données encodées sur trois lignes  

Ouvrez les images avec n'importe quel visualiseur d'images ; elles affichent des codes-barres nets et scannables, prêts à être imprimés ou intégrés dans des PDF.

## Comment générer une image de code-barres avec des dimensions personnalisées

Si vous avez besoin d'une taille d'image spécifique, ajustez les propriétés `ImageHeight` et `ImageWidth` avant d'appeler `Save` :

```csharp
colsGenerator.Parameters.ImageHeight = 150; // pixels
colsGenerator.Parameters.ImageWidth = 300;  // pixels
colsGenerator.Save(colsFile, BarCodeImageFormat.Png);
```

Modifier les dimensions n'affecte pas les données encodées ; cela ne fait que mettre à l'échelle la représentation visuelle. Cette technique est utile lors de l'intégration de codes-barres dans des composants UI avec des contraintes de mise en page fixes.

## Écueils courants et astuces professionnelles

* **Séparateurs de chemin :** Utilisez des chaînes verbatim (`@"C:\Path\file.png"`) ou `Path.Combine` pour éviter les problèmes de caractères d'échappement sous Windows.  
* **Application de la licence :** Sans licence valide, les images générées contiennent un filigrane. Appliquez votre licence tôt dans l'application :

  ```csharp
  Aspose.BarCode.License license = new Aspose.BarCode.License();
  license.SetLicense("Aspose.BarCode.lic");
  ```

* **Limites d'encodage :** DataBar Expanded Stacked prend en charge jusqu'à 74 caractères numériques. Dépasser cette limite génère une exception. Validez la longueur de l'entrée avant de créer le générateur.  
* **Performance :** Réutiliser une seule instance de `BarcodeGenerator` pour plusieurs sauvegardes réduit l'allocation mémoire. Ne modifiez les propriétés `Rows` ou `Columns` entre les sauvegardes que si le texte encodé reste identique.

## Étapes suivantes

Maintenant que vous pouvez générer des images de code-barres avec le générateur de code-barres C#, envisagez d'explorer :

* **Différentes symbologies** – essayez `EncodeTypes.QR`, `EncodeTypes.Code128` ou `EncodeTypes.Pdf417`.  
* **Personnalisation des couleurs** – définissez `Parameters.Barcode.ForeColor` et `BackColor` pour correspondre à votre identité visuelle.  
* **Intégration dans les PDF** – combinez le PNG généré avec Aspose.PDF pour créer des documents imprimables.  

Ces extensions vous permettent de créer une solution de code-barres complète pour les applications d'inventaire, de logistique ou de vente au détail.

---


## Que devriez‑vous apprendre ensuite ?

Les tutoriels suivants couvrent des sujets étroitement liés qui s'appuient sur les techniques démontrées dans ce guide. Chaque ressource comprend des exemples de code complets et fonctionnels avec des explications étape par étape pour vous aider à maîtriser des fonctionnalités API supplémentaires et explorer des approches d'implémentation alternatives dans vos propres projets.

- [Générer une image de code-barres – GS1 Coupon UPC‑A Databar](/barcode/english/net/gs1-barcode-encoding/gs1-coupon-upc-a-databar-configuration/)
- [Créer une image de code-barres DotCode – lignes & colonnes (Aspose.BarCode)](/barcode/english/net/dotcode-barcode-configuration/dotcode-rows-columns-configuration/)
- [Comment générer des codes-barres DataMatrix (ECC 200) avec Aspose.BarCode pour .NET](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-ecc-200-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}