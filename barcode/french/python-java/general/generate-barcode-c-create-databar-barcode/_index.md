---
category: general
date: 2026-07-21
description: Générez rapidement des codes-barres C# avec Aspose.BarCode. Apprenez
  à créer un code-barres DataBar, à personnaliser la taille du code-barres et à exporter
  l'image du code-barres en quelques étapes seulement.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate barcode c#
- create databar barcode
- customize barcode size
- change barcode dimensions
- export barcode image
language: fr
lastmod: 2026-07-21
og_description: Générez un code‑barres C# avec Aspose.BarCode. Créez un code‑barres
  DataBar, personnalisez sa taille et exportez l’image instantanément.
og_image_alt: Screenshot of a DataBar Expanded Stacked barcode saved as PNG
og_title: Générer un code-barres C# – Créez des codes-barres DataBar avec une taille
  personnalisée
schemas:
- author: Aspose
  dateModified: '2026-07-21'
  description: Generate barcode C# quickly with Aspose.BarCode. Learn to create DataBar
    barcode, customize barcode size, and export barcode image in just a few steps.
  headline: Generate barcode C# – Create DataBar barcode
  type: TechArticle
- questions:
  - answer: Replace `BarCodeImageFormat.Png` with `Jpeg`, `Bmp`, `Gif`, or `Svg`.
      The API handles the conversion automatically.
    question: What if I need a different image format?
  - answer: Technically you can set both, but Aspose will prioritize the last property
      you modify. It's safer to set *one* dimension and let the library compute the
      other for a valid DataBar.
    question: Can I change both rows and columns simultaneously?
  - answer: 'Use `barcodeGen.Parameters.Barcode.ForegroundColor` and `BackgroundColor`.
      Example:'
    question: How do I apply a foreground/background color?
  - answer: DataBar Expanded Stacked supports up to 74 numeric characters (or 30 alphanumeric).
      Exceeding that throws an exception.
    question: Is there a size limit for the encoded data?
  type: FAQPage
tags:
- barcode
- csharp
- databar
- image-export
- aspnet
title: Générer un code‑barres C# – Créer un code‑barres DataBar
url: /fr/python-java/general/generate-barcode-c-create-databar-barcode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Générer un code‑barres C# – Créer un code‑barres DataBar

Vous cherchez à **générer un code‑barres C#** sans vous perdre dans une infinité de documents ? Vous êtes au bon endroit. Dans ce guide, nous allons créer un **code‑barres DataBar**, ajuster ses dimensions, puis **exporter l’image du code‑barres**—le tout en quelques lignes de C#.

Imaginez que vous ayez besoin d’une étiquette produit compacte qui tient sur un petit porte‑étiquette. Un symbole DataBar Expanded Stacked fait l’affaire, et avec Aspose.BarCode vous pouvez contrôler exactement le nombre de colonnes ou de rangées utilisées. Prêt ? Allons‑y.

## Ce que vous allez réaliser

- **Créer un code‑barres DataBar** (la variante « expanded stacked ») à partir de zéro.  
- **Personnaliser la taille du code‑barres** en définissant directement les colonnes ou les rangées.  
- **Modifier les dimensions du code‑barres** à la volée sans reconstruire le générateur.  
- **Exporter l’image du code‑barres** au format PNG (ou tout autre format supporté par Aspose).  

Aucun service externe, aucune configuration compliquée—juste du C# propre et exécutable.

## Prérequis

- .NET 6.0 ou supérieur (le code fonctionne également avec .NET Framework 4.7+).  
- Une licence valide d’Aspose.BarCode for .NET (ou vous pouvez travailler en mode d’évaluation).  
- Un IDE de votre choix—Visual Studio, Rider ou VS Code conviendra.  

Si vous n’avez pas encore installé le package NuGet, exécutez :

```bash
dotnet add package Aspose.BarCode
```

C’est tout—aucune autre dépendance.

## Étape 1 : Configurer le générateur de code‑barres (Comment **générer un code‑barres C#**)

Tout d’abord, nous avons besoin d’une instance `BarcodeGenerator` pointant sur le symbole **DataBar Expanded Stacked**. Cet objet est le moteur qui créera l’image plus tard.

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;

// Initialize the generator with the desired symbology and data
BarcodeGenerator barcodeGen = new BarcodeGenerator(
    EncodeTypes.DatabarExpandedStacked,   // Symbology
    "Databar Expanded Stacked long");    // Human‑readable text (optional)
```

*Pourquoi c’est important* : l’énumération `EncodeTypes.DatabarExpandedStacked` indique à Aspose que nous voulons la version empilée, idéale pour les espaces étroits. Le texte que nous transmettons devient la valeur encodée ; vous pouvez le remplacer par n’importe quelle chaîne numérique requise par votre application.

## Étape 2 : **Personnaliser la taille du code‑barres** – définir les colonnes

Les codes‑barres DataBar vous permettent d’influencer la densité visuelle en spécifiant soit le nombre de **colonnes** *soit* de **rangées**. Commençons par les colonnes. Le nombre de rangées sera calculé automatiquement pour garder le code‑barres valide.

```csharp
// Set the number of columns; rows are computed automatically
barcodeGen.Parameters.Barcode.DataBar.Columns = 4;
```

*Astuce pro* : les colonnes affectent la largeur du code‑barres. Plus de colonnes → code‑barres plus large, ce qui peut améliorer la fiabilité de la lecture sur des imprimantes à basse résolution.

## Étape 3 : **Exporter l’image du code‑barres** avec le réglage des colonnes

Nous écrivons maintenant l’image sur le disque. Vous pouvez choisir PNG, JPEG, BMP ou même SVG. Voici le PNG pour une sortie nette et sans perte.

```csharp
// Save the barcode image using the current column configuration
barcodeGen.Save(@"C:\Barcodes\DatabarCols4.png", BarCodeImageFormat.Png);
```

> **Résultat attendu** – Ouvrez `DatabarCols4.png` et vous devriez voir un DataBar empilé proprement avec quatre colonnes. Il ressemble à une pile dense de barres verticales, parfaite pour une petite étiquette.

## Étape 4 : **Modifier les dimensions du code‑barres** – définir les rangées

Parfois, vous avez besoin d’un code‑barres plus haut plutôt que plus large. Passez au contrôle par rangées ; Aspose recalculera automatiquement les colonnes.

```csharp
// Switch to row control – columns will be derived automatically
barcodeGen.Parameters.Barcode.DataBar.Rows = 3;
```

*Pourquoi changer ?* Les rangées affectent la hauteur du code‑barres. Plus de rangées → symbole plus haut, ce qui peut être pratique lorsque vous disposez d’espace vertical mais d’une largeur limitée.

## Étape 5 : **Exporter l’image du code‑barres** avec le réglage des rangées

Enregistrez la seconde variante. Remarquez que le nom de fichier reflète le changement ; vous pouvez également conserver les deux images pour les comparer.

```csharp
// Save the barcode image using the new row configuration
barcodeGen.Save(@"C:\Barcodes\DatabarRows3.png", BarCodeImageFormat.Png);
```

> **Résultat** – `DatabarRows3.png` affiche maintenant une version plus haute des mêmes données, toujours parfaitement lisible.

## Exemple complet fonctionnel

En rassemblant le tout, voici une application console autonome que vous pouvez copier‑coller et exécuter immédiatement :

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Program
{
    static void Main()
    {
        // 1️⃣ Initialize generator for DataBar Expanded Stacked
        BarcodeGenerator barcodeGen = new BarcodeGenerator(
            EncodeTypes.DatabarExpandedStacked,
            "Databar Expanded Stacked long");

        // 2️⃣ Customize size – set columns (width)
        barcodeGen.Parameters.Barcode.DataBar.Columns = 4;

        // 3️⃣ Export image with column setting
        string colPath = @"C:\Barcodes\DatabarCols4.png";
        barcodeGen.Save(colPath, BarCodeImageFormat.Png);
        Console.WriteLine($"Saved column‑based barcode to {colPath}");

        // 4️⃣ Change dimensions – set rows (height)
        barcodeGen.Parameters.Barcode.DataBar.Rows = 3;

        // 5️⃣ Export image with row setting
        string rowPath = @"C:\Barcodes\DatabarRows3.png";
        barcodeGen.Save(rowPath, BarCodeImageFormat.Png);
        Console.WriteLine($"Saved row‑based barcode to {rowPath}");
    }
}
```

Exécutez le programme, puis ouvrez les deux fichiers PNG. Vous avez maintenant **généré un code‑barres C#**, **personnalisé la taille du code‑barres**, **modifié les dimensions du code‑barres** et **exporté l’image du code‑barres**—le tout en moins d’une minute.

## Questions fréquentes & cas particuliers

- **Et si j’ai besoin d’un autre format d’image ?**  
  Remplacez `BarCodeImageFormat.Png` par `Jpeg`, `Bmp`, `Gif` ou `Svg`. L’API gère la conversion automatiquement.

- **Puis‑je changer à la fois les rangées et les colonnes simultanément ?**  
  Techniquement, vous pouvez définir les deux, mais Aspose priorisera la dernière propriété modifiée. Il est plus sûr de définir *une* dimension et de laisser la bibliothèque calculer l’autre pour obtenir un DataBar valide.

- **Comment appliquer une couleur de premier plan / arrière‑plan ?**  
  Utilisez `barcodeGen.Parameters.Barcode.ForegroundColor` et `BackgroundColor`. Exemple :  
  ```csharp
  barcodeGen.Parameters.Barcode.ForegroundColor = Color.DarkBlue;
  barcodeGen.Parameters.Barcode.BackgroundColor = Color.White;
  ```

- **Existe‑t‑il une limite de taille pour les données encodées ?**  
  DataBar Expanded Stacked accepte jusqu’à 74 caractères numériques (ou 30 alphanumériques). Dépasser cette limite déclenche une exception.

## Prochaines étapes

Maintenant que vous avez maîtrisé les bases de **création de code‑barres databar**, envisagez :

- D’ajouter des **annotations de texte** sous le code‑barres (`barcodeGen.Parameters.CaptionAbove.Text`).  
- D’intégrer le PNG directement dans un PDF avec Aspose.PDF.  
- De générer des codes‑barres en masse en parcourant un CSV d’identifiants produit.

Chacune de ces thématiques s’appuie sur le même objet `BarcodeGenerator`, vous n’aurez donc pas besoin de repartir de zéro.

---

**En résumé** : vous savez maintenant comment **générer un code‑barres C#**, **personnaliser la taille du code‑barres**, **modifier les dimensions du code‑barres** et **exporter l’image du code‑barres** avec Aspose.BarCode. Expérimentez avec les valeurs de colonnes/rangées, changez les formats d’image, et intégrez le code dans votre système d’inventaire ou de point de vente. Bon codage !


## Qu’allez‑vous apprendre ensuite ?


Les tutoriels suivants couvrent des sujets étroitement liés qui s’appuient sur les techniques présentées dans ce guide. Chaque ressource comprend des exemples de code complets avec des explications pas à pas pour vous aider à maîtriser d’autres fonctionnalités de l’API et à explorer des approches d’implémentation alternatives dans vos propres projets.

- [Generate barcode image – GS1 Coupon UPC-A Databar](/barcode/english/net/gs1-barcode-encoding/gs1-coupon-upc-a-databar-configuration/)
- [How to generate Aztec barcode with custom aspect ratio using Aspose.BarCode for .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)
- [Generate DataMatrix Barcode – Pro Guide with Aspose.BarCode](/barcode/english/net/datamatrix-barcode-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}