---
category: general
date: 2026-10-02
description: Apprenez à définir les colonnes et les lignes dans un générateur de codes‑barres
  C# pour créer des codes‑barres DataBar. Guide étape par étape avec le code complet.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- c# barcode generator
- how to set columns
- how to set rows
- create databar barcode
language: fr
lastmod: 2026-10-02
og_description: Guide du générateur de codes-barres C# – apprenez comment définir
  les colonnes et les lignes pour créer des codes-barres DataBar avec des exemples
  de code complets.
og_image_alt: Screenshot of a DataBar Expanded Stacked barcode generated with a C#
  barcode generator
og_title: 'Générateur de codes-barres C# : définir les colonnes et les lignes pour
  les codes-barres DataBar'
schemas:
- author: Aspose
  dateModified: '2026-10-02'
  description: Learn how to set columns and rows in a C# barcode generator to create
    DataBar barcodes. Step‑by‑step guide with complete code.
  headline: How to use a C# barcode generator to create DataBar barcodes with custom
    columns and rows
  type: TechArticle
tags:
- barcode
- c#
- databar
title: Comment utiliser un générateur de codes-barres C# pour créer des codes-barres
  DataBar avec des colonnes et des lignes personnalisées
url: /fr/python-java/general/how-to-use-a-c-barcode-generator-to-create-databar-barcodes/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Comment utiliser un générateur de code‑barres C# pour créer des codes‑barres DataBar avec des colonnes et des lignes personnalisées

Si vous avez besoin d'un **générateur de code‑barres c#** capable de produire des codes‑barres DataBar avec des configurations précises de colonnes et de lignes, ce tutoriel vous montre exactement comment faire. Vous verrez pourquoi ajuster les colonnes et les lignes est important, et vous obtiendrez un exemple complet, prêt à l'exécution, qui crée à la fois un code‑barres DataBar Expanded Stacked à 4 colonnes et à 3 lignes.

Dans les sections suivantes, nous couvrons :

* Les prérequis pour utiliser la bibliothèque Aspose.BarCode for .NET.
* Comment définir les colonnes (`how to set columns`) et les lignes (`how to set rows`) sur un code‑barres DataBar.
* Un programme console C# complet que vous pouvez copier, compiler et exécuter.
* Les fichiers de sortie attendus et des conseils de dépannage.

À la fin de ce guide, vous serez capable de **créer des images de code‑barres databar** adaptées à vos exigences de mise en page.

## Prerequisites

Avant de commencer, assurez‑vous d’avoir :

| Exigence | Raison |
|----------|--------|
| .NET 6.0 SDK ou version ultérieure | Fournit le runtime pour le code C#. |
| Visual Studio 2022 (ou tout IDE supportant .NET) | Facilite la création du projet et le débogage. |
| Aspose.BarCode for .NET package NuGet | Fournit la classe `BarcodeGenerator` utilisée dans les exemples. |
| Permission d’écriture sur un dossier pour les fichiers PNG de sortie | Le générateur écrit les images du code‑barres sur le disque. |

Installez le package Aspose.BarCode avec la commande suivante :

```bash
dotnet add package Aspose.BarCode
```

## Étape 1 : Créer un code‑barres DataBar Expanded Stacked de base

La première étape consiste à instancier un **générateur de code‑barres c#** avec le format `EncodeTypes.DatabarExpandedStacked`. Ce format est un code‑barres DataBar bidimensionnel qui peut encoder jusqu’à 74 caractères numériques.

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;

// ...

// Create a generator for a DataBar Expanded Stacked barcode
var generator = new BarcodeGenerator(
    EncodeTypes.DatabarExpandedStacked,
    "Databar Expanded Stacked long");
```

Le constructeur reçoit deux arguments :

* `EncodeTypes.DatabarExpandedStacked` – indique à la bibliothèque quelle symbologie utiliser.
* `"Databar Expanded Stacked long"` – le texte qui sera encodé.

## Étape 2 : How to set columns

Les colonnes affectent la densité horizontale du code‑barres DataBar. Augmenter le nombre de colonnes rend le code‑barres plus large, ce qui peut améliorer la fiabilité de lecture sur des imprimantes à basse résolution.

```csharp
// Set the number of columns to 4
generator.Parameters.Barcode.DataBar.Columns = 4;
```

**Pourquoi 4 colonnes ?**  
Quatre colonnes offrent un bon équilibre entre taille et lisibilité pour la plupart des applications de vente au détail. Vous pouvez expérimenter avec des valeurs de 1 à 8 ; la bibliothèque ajustera automatiquement la largeur du module.

## Étape 3 : Enregistrer le code‑barres configuré en colonnes

```csharp
// Save the image that uses the column setting
generator.Save(@"C:\Barcodes\DatabarCols4.png", BarCodeImageFormat.Png);
```

L’image est enregistrée au format PNG, ce qui préserve les bords nets requis par les lecteurs de code‑barres.

## Étape 4 : Créer un générateur séparé pour la configuration des lignes

La configuration des lignes fonctionne de la même manière mais influence la densité verticale. Pour éviter de mélanger les réglages de colonnes et de lignes, nous créons une nouvelle instance de générateur.

```csharp
var generatorRows = new BarcodeGenerator(
    EncodeTypes.DatabarExpandedStacked,
    "Databar Expanded Stacked long");
```

## Étape 5 : How to set rows

```csharp
// Set the number of rows to 3
generatorRows.Parameters.Barcode.DataBar.Rows = 3;
```

**Quand utiliser davantage de lignes ?**  
Ajouter des lignes rend le code‑barres plus haut, ce qui peut être utile lorsque l’espace imprimé est limité horizontalement mais abondant verticalement (par ex., sur une étiquette produit plus haute que large).

## Étape 6 : Enregistrer le code‑barres configuré en lignes

```csharp
// Save the image that uses the row setting
generatorRows.Save(@"C:\Barcodes\DatabarRows3.png", BarCodeImageFormat.Png);
```

Les deux fichiers PNG (`DatabarCols4.png` et `DatabarRows3.png`) apparaîtront dans le dossier `C:\Barcodes`.

## Exemple complet, exécutable

Voici une application console autonome qui intègre chaque étape décrite ci‑dessus. Copiez le code dans un nouveau projet console .NET et exécutez‑le.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace DatabarDemo
{
    class Program
    {
        static void Main()
        {
            // Output directory – change to a folder that exists on your machine
            const string outputDir = @"C:\Barcodes";

            // -------------------------------------------------
            // 1️⃣ Create a barcode generator for column testing
            // -------------------------------------------------
            var colGenerator = new BarcodeGenerator(
                EncodeTypes.DatabarExpandedStacked,
                "Databar Expanded Stacked long");

            // Set the number of columns (how to set columns)
            colGenerator.Parameters.Barcode.DataBar.Columns = 4;

            // Save the column‑based barcode
            string colPath = System.IO.Path.Combine(outputDir, "DatabarCols4.png");
            colGenerator.Save(colPath, BarCodeImageFormat.Png);
            Console.WriteLine($"Column barcode saved to: {colPath}");

            // -------------------------------------------------
            // 2️⃣ Create a barcode generator for row testing
            // -------------------------------------------------
            var rowGenerator = new BarcodeGenerator(
                EncodeTypes.DatabarExpandedStacked,
                "Databar Expanded Stacked long");

            // Set the number of rows (how to set rows)
            rowGenerator.Parameters.Barcode.DataBar.Rows = 3;

            // Save the row‑based barcode
            string rowPath = System.IO.Path.Combine(outputDir, "DatabarRows3.png");
            rowGenerator.Save(rowPath, BarCodeImageFormat.Png);
            Console.WriteLine($"Row barcode saved to: {rowPath}");

            // -------------------------------------------------
            // 3️⃣ Confirmation message
            // -------------------------------------------------
            Console.WriteLine("Both DataBar barcodes have been generated successfully.");
        }
    }
}
```

### Ce que fait le code

| Section | Objectif |
|---------|----------|
| **Importations d'espaces de noms** | Récupère `Aspose.BarCode` et `Aspose.BarCode.Generation`. |
| **Répertoire de sortie** | Centralise le chemin afin que vous n'ayez à modifier qu’une seule ligne si vous déplacez le dossier. |
| **Générateur de colonnes** | Démonstre **how to set columns** sur un `c# barcode generator`. |
| **Générateur de lignes** | Démonstre **how to set rows** sur un `c# barcode generator`. |
| **Appels de sauvegarde** | Écrit les fichiers PNG sur le disque, les rendant prêts à être scannés ou inclus dans des rapports. |
| **Sortie console** | Fournit un retour immédiat, utile pendant le développement. |

## Résultat attendu

Après l’exécution du programme, vous devriez voir deux fichiers PNG :

* **DatabarCols4.png** – un code‑barres plus large reflétant quatre colonnes.
* **DatabarRows3.png** – un code‑barres plus haut reflétant trois lignes.

Les deux images contiennent le texte *« Databar Expanded Stacked long »* encodé dans la symbologie DataBar Expanded Stacked. Vous pouvez les ouvrir avec n’importe quel visualiseur d’images ou les soumettre à un lecteur de code‑barres pour vérifier la lisibilité.

## Problèmes courants et comment les éviter

| Problème | Raison | Solution |
|----------|--------|----------|
| **File‑access exception** | Le dossier de sortie n’existe pas ou vous n’avez pas les droits d’écriture. | Créez le dossier manuellement ou exécutez le programme avec des privilèges élevés. |
| **Incorrect column/row values** | La bibliothèque n’accepte que les valeurs 1‑8 pour les colonnes et 1‑4 pour les lignes. | Validez les valeurs avant de les assigner, par ex., `if (value < 1 || value > 8) throw new ArgumentOutOfRangeException();`. |
| **Barcode not scanning** | L’image générée est trop petite pour la résolution du lecteur. | Augmentez `ImageHeight` ou `ImageWidth` via `generator.Parameters.Image.Height` / `...Width`. |
| **Text truncation** | Le texte encodé dépasse la longueur maximale pour la variante DataBar choisie. | Utilisez une chaîne plus courte ou passez à `EncodeTypes.DatabarExpanded` si vous avez besoin de plus de capacité. |

## Astuces pro

* **Mettre en cache le générateur** – Si vous devez créer de nombreux codes‑barres avec les mêmes réglages de colonnes/lignes, réutilisez la même instance `BarcodeGenerator` et ne modifiez que la propriété `CodeText`.
* **Traitement par lots** – Parcourez une collection d’identifiants produit, définissez `generator.CodeText` dans la boucle, puis appelez `Save` avec un nom de fichier unique à chaque itération.
* **Performance** – Pour les scénarios à haut volume, désactivez l’anti‑aliasing (`generator.Parameters.Image.AntiAlias = false`) afin d’accélérer la génération d’image sans nuire à la qualité de lecture.

## Prochaines étapes

Maintenant que vous savez **how to set columns** et **how to set rows** avec un **c# barcode generator**, vous pouvez explorer :

* **Ajouter du texte lisible** sous le code‑barres (`generator.Parameters.Barcode.CodeTextLocation`).
* **Modifier les couleurs** (`generator.Parameters.Image.ForegroundColor` et `BackgroundColor`).
* **Générer d’autres variantes DataBar** telles que `DatabarLimited` ou `DatabarExpanded`.
* **Intégrer des codes‑barres dans des rapports PDF** en utilisant Aspose.PDF.

Chaque sujet s’appuie sur les bases présentées ici et vous aide à créer des solutions de code‑barres plus riches et prêtes pour la production.

---

*Bon codage ! Si vous rencontrez des problèmes, n’hésitez pas à laisser un commentaire ou à consulter la documentation Aspose.BarCode pour des détails d’API plus approfondis.*

## Que devriez‑vous apprendre ensuite ?


Les tutoriels suivants couvrent des sujets étroitement liés qui s’appuient sur les techniques démontrées dans ce guide. Chaque ressource inclut des exemples de code complets avec des explications pas à pas pour vous aider à maîtriser des fonctionnalités API supplémentaires et explorer des approches d’implémentation alternatives dans vos propres projets.

- [How to set barcode columns and rows with C# BarcodeGenerator](/barcode/english/python-java/general/how-to-set-barcode-columns-and-rows-with-c-barcodegenerator/)
- [Barcode Generator Example in C# – Set Columns, Rows & Export Image](/barcode/english/python-java/general/barcode-generator-example-in-c-set-columns-rows-export-image/)
- [How to use a barcode generator C# to create DataBar barcodes](/barcode/english/python-java/general/how-to-use-a-barcode-generator-c-to-create-databar-barcodes/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}