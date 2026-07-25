---
category: general
date: 2026-07-24
description: Tutoriel C# sur la génération de codes-barres montrant comment créer
  une image de code-barres, définir les colonnes, définir les lignes et créer un code-barres
  Databar en quelques lignes de code.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- barcode generator c#
- generate barcode image
- how to set columns
- how to set rows
- create databar barcode
language: fr
lastmod: 2026-07-24
og_description: Le tutoriel Barcode Generator C# vous guide à travers la génération
  d’une image de code‑barres, la configuration des colonnes et des lignes, et la création
  d’un code‑barres Databar avec des exemples de code clairs.
og_image_alt: Screenshot of a DataBar Expanded Stacked barcode generated with C#
og_title: Générateur de codes-barres C# – Créez rapidement des codes-barres DataBar
  empilés
schemas:
- author: Aspose
  dateModified: '2026-07-24'
  description: Barcode Generator C# tutorial that shows how to generate barcode image,
    set columns, set rows, and create Databar barcode in just a few lines of code.
  headline: Barcode Generator C# – Create DataBar Expanded Stacked Images
  type: TechArticle
tags:
- barcode
- C#
- Aspose.BarCode
title: Générateur de codes-barres C# – Créer des images DataBar Expanded Stacked
url: /fr/python-java/general/barcode-generator-c-create-databar-expanded-stacked-images/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Barcode Generator C# – Guide complet sur DataBar Expanded Stacked

Vous vous êtes déjà demandé comment utiliser **barcode generator c#** pour générer des images nettes et lisibles en quelques secondes ? Peut‑être avez‑vous fixé un projet vierge, sans savoir où placer les colonnes ou les rangées, ou comment réellement *generate barcode image* sans prise de tête. Eh bien, vous êtes au bon endroit. Dans ce tutoriel, nous allons créer une petite application console, créer un code‑barres DataBar Expanded Stacked, ajuster sa mise en page, et enregistrer le résultat au format PNG — le tout avec la bibliothèque **barcode generator c#**.

Nous couvrirons tout ce que vous devez savoir : installation du package, configuration des colonnes et des rangées (oui, nous répondrons à *how to set columns* et *how to set rows*), et enfin comment **create databar barcode** des objets que vous pourrez insérer dans des factures, tickets ou tout autre support nécessitant une étiquette lisible par machine. Aucun document externe requis ; copiez‑collez, exécutez, et vous verrez deux fichiers PNG apparaître dans votre dossier.

## Ce dont vous aurez besoin

- .NET 6.0 SDK ou version ultérieure (le code fonctionne sur .NET Core, .NET Framework et .NET 5+)
- Un projet console vierge (`dotnet new console`) – vous pouvez également utiliser Visual Studio si vous préférez une interface graphique.
- Le package NuGet Aspose.BarCode for .NET (la bibliothèque qui alimente **barcode generator c#**). Installez‑le avec :

```bash
dotnet add package Aspose.BarCode
```

C’est tout. Une fois le package restauré, vous êtes prêt à démarrer.

## Barcode Generator C# – Configuration du projet

Tout d’abord, importons les espaces de noms nécessaires et créons une méthode d’aide qui gardera notre routine principale propre.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Program
{
    static void Main()
    {
        // Folder where PNG files will be saved
        string outputFolder = Environment.CurrentDirectory;

        // Build the first barcode with custom columns
        GenerateDatabarWithColumns(outputFolder, columns: 4);

        // Build the second barcode with custom rows
        GenerateDatabarWithRows(outputFolder, rows: 3);
    }

    // -----------------------------------------------------------------
    // Helper: creates a DataBar Expanded Stacked barcode and sets columns
    // -----------------------------------------------------------------
    static void GenerateDatabarWithColumns(string folder, int columns)
    {
        // Step 1: Create a DataBar Expanded Stacked barcode generator with the desired text
        var barcodeGenerator = new BarcodeGenerator(
            EncodeTypes.DatabarExpandedStacked, "Databar Expanded Stacked long");

        // Step 2: Configure the barcode to use the supplied number of columns
        // This answers the “how to set columns” question.
        barcodeGenerator.Parameters.Barcode.DataBar.Columns = columns;

        // Step 3: Save the barcode image as PNG – this is the “generate barcode image” part.
        string filePath = System.IO.Path.Combine(folder, $"DatabarCols{columns}.png");
        barcodeGenerator.Save(filePath, BarCodeImageFormat.Png);

        Console.WriteLine($"✅ Created barcode with {columns} columns: {filePath}");
    }

    // -----------------------------------------------------------------
    // Helper: creates a DataBar Expanded Stacked barcode and sets rows
    // -----------------------------------------------------------------
    static void GenerateDatabarWithRows(string folder, int rows)
    {
        // Step 4: Create another generator for the same barcode type and text
        var barcodeGenerator = new BarcodeGenerator(
            EncodeTypes.DatabarExpandedStacked, "Databar Expanded Stacked long");

        // Step 5: Configure the barcode to use the supplied number of rows
        // This answers the “how to set rows” query.
        barcodeGenerator.Parameters.Barcode.DataBar.Rows = rows;

        // Step 6: Save the second barcode image as PNG
        string filePath = System.IO.Path.Combine(folder, $"DatabarRows{rows}.png");
        barcodeGenerator.Save(filePath, BarCodeImageFormat.Png);

        Console.WriteLine($"✅ Created barcode with {rows} rows: {filePath}");
    }
}
```

### Pourquoi cette structure fonctionne

- **Séparation des responsabilités** – chaque aide se concentre sur une configuration unique (colonnes vs. rangées). Cela rend le code plus lisible et réutilisable.  
- **Paramètres explicites** – nous transmettons `columns` ou `rows` en arguments, ce qui vous permet d’appeler la même méthode avec n’importe quelle valeur sans modifier le corps.  
- **Retour immédiat** – `Console.WriteLine` vous indique exactement où le fichier a été enregistré, ce qui est pratique lorsque vous exécutez le programme depuis un terminal.

## Comment définir les colonnes pour DataBar Expanded Stacked

La propriété `DataBar.Columns` est le réglage qui détermine le nombre de tranches verticales que le code‑barres contiendra. La valeur par défaut est `4`, mais vous pourriez avoir besoin de `2` ou `6` selon la quantité de données que vous encodez ou les exigences du lecteur. Voici un extrait rapide qui isole la logique de réglage des colonnes :

```csharp
var generator = new BarcodeGenerator(EncodeTypes.DatabarExpandedStacked, "Sample Text");
generator.Parameters.Barcode.DataBar.Columns = 5;   // ← change this number as needed
generator.Save("databar_columns5.png", BarCodeImageFormat.Png);
```

**Astuce :** lorsque vous augmentez le nombre de colonnes, la largeur globale du code‑barres augmente proportionnellement. Si vous prévoyez d’insérer l’image dans un PDF ou une page web, assurez‑vous que le conteneur peut accueillir cette largeur supplémentaire, sinon le lecteur pourrait mal l’interpréter.

## Comment définir les rangées pour DataBar Expanded Stacked

Les rangées fonctionnent de la même façon, mais elles affectent la hauteur du code‑barres. Le nombre de rangées par défaut est `3`. Si votre étiquette dispose de peu d’espace vertical, vous pouvez le réduire à `2`. À l’inverse, davantage de rangées peuvent améliorer la lisibilité sur des imprimantes à basse résolution.

```csharp
var generator = new BarcodeGenerator(EncodeTypes.DatabarExpandedStacked, "Sample Text");
generator.Parameters.Barcode.DataBar.Rows = 2;   // ← adjust rows here
generator.Save("databar_rows2.png", BarCodeImageFormat.Png);
```

**Attention :** définir les rangées à une valeur inférieure au minimum requis pour les données encodées déclenchera une exception à l’exécution. La bibliothèque lève `ArgumentException` avec un message clair, vous indiquant instantanément si la configuration est invalide.

## Générer l’image du code‑barres – Enregistrement au format PNG

Les deux aides ci‑dessus se terminent par un appel à `Save`. L’énumération `BarCodeImageFormat.Png` indique à Aspose.BarCode de produire un fichier PNG sans perte, idéal pour la plupart des scénarios de numérisation car il conserve les bords nets. Si vous préférez un autre format (JPEG pour le web, BMP pour les systèmes anciens), il suffit d’échanger la valeur de l’énumération — aucune autre modification du code n’est nécessaire.

```csharp
generator.Save("mybarcode.jpeg", BarCodeImageFormat.Jpeg);
```

Les PNG générés ressemblent à ceci (imaginez l’image ; le texte alternatif ci‑dessous la décrit) :

> **Alt text for the generated images:** *DataBar Expanded Stacked barcode with 4 columns (left) and 3 rows (right), rendered in high‑contrast black on a transparent background.*

## Créer un code‑barres DataBar – Exemple complet

En réunissant tous les éléments, voici une version compacte que vous pouvez placer directement dans `Program.cs`. Elle montre la configuration des colonnes et des rangées, ainsi qu’une vérification rapide de l’existence des fichiers après l’enregistrement.

```csharp
using System;
using System.IO;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Demo
{
    static void Main()
    {
        string outDir = Directory.GetCurrentDirectory();

        // ---------- Create barcode with custom columns ----------
        var colGen = new BarcodeGenerator(EncodeTypes.DatabarExpandedStacked,
                                          "Databar Expanded Stacked long");
        colGen.Parameters.Barcode.DataBar.Columns = 4;   // how to set columns
        string colPath = Path.Combine(outDir, "DatabarCols4.png");
        colGen.Save(colPath, BarCodeImageFormat.Png);
        Console.WriteLine($"Saved column barcode → {colPath}");

        // ---------- Create barcode with custom rows ----------
        var rowGen = new BarcodeGenerator(EncodeTypes.DatabarExpandedStacked,
                                          "Databar Expanded Stacked long");
        rowGen.Parameters.Barcode.DataBar.Rows = 3;      // how to set rows
        string rowPath = Path.Combine(outDir, "DatabarRows3.png");
        rowGen.Save(rowPath, BarCodeImageFormat.Png);
        Console.WriteLine($"Saved row barcode → {rowPath}");

        // ---------- Verify files exist ----------
        Console.WriteLine(File.Exists(colPath)
            ? "✅ Column image generated successfully."
            : "❌ Column image missing.");
        Console.WriteLine(File.Exists(rowPath)
            ? "✅ Row image generated successfully."
            : "❌ Row image missing.");
    }
}
```

### Résultat attendu

Lorsque vous exécutez le programme (`dotnet run`), vous devriez voir des lignes de console similaires à :

```
Saved column barcode → C:\MyProject\DatabarCols4.png
Saved row barcode → C:\MyProject\DatabarRows3.png
✅ Column image generated successfully.
✅ Row image generated successfully.
```

Ouvrez les deux fichiers PNG avec n’importe quel visualiseur d’images ; vous remarquerez que le fichier de gauche possède quatre modules verticaux (colonnes) tandis que celui de droite en a trois en hauteur (rangées). Les deux sont parfaitement lisibles avec n’importe quel lecteur DataBar standard.

## Pièges courants & comment les éviter

| Symptôme | Cause probable | Solution |
|----------|----------------|----------|
| `ArgumentException: Columns value is out of range` | Colonnes définies à 0 ou > 8 (la bibliothèque limite à 8). | Respectez des valeurs comprises entre **1** et **8**. |
| Le code‑barres apparaît flou dans le PDF | PNG enregistré avec la DPI par défaut (96) puis redimensionné. | Utilisez `generator.Parameters.ImageResolution = 300;` avant l’enregistrement. |
| Le scanner échoue avec une configuration uniquement en rangées | Rangées modifiées mais colonnes laissées à la valeur par défaut qui ne correspond pas à la longueur des données. | Ajustez à la fois les rangées **et** les colonnes, ou laissez la bibliothèque redimensionner automatiquement en omettant les réglages manuels. |

## Prochaines étapes

Maintenant que vous savez **generate barcode image**, **set columns**, **set rows**, et **create databar barcode** avec **barcode generator c#**, vous pouvez :

- Intégrer les PNG dans des PDF à l’aide de `Aspose.PDF` ou `iTextSharp`.  
- Passer à `EncodeTypes.DatabarLimited` si vous avez besoin d’une empreinte plus petite.  
- Expérimenter avec les couleurs (`generator.Parameters.Barcode.ForeColor = Color.Blue`).  
- Ajouter des QR codes ou d’autres symbologies dans le même projet — Aspose.BarCode prend en charge plus de 150 types.

Si vous rencontrez des difficultés, laissez un commentaire ci‑dessous ou consultez la documentation officielle d’Aspose.BarCode (la référence API est exhaustive et comprend des dizaines d’exemples de code en direct). Bon codage, et que vos scanners ne manquent jamais une marque !

## Que devriez‑vous apprendre ensuite ?

Les tutoriels suivants couvrent des sujets étroitement liés qui s’appuient sur les techniques démontrées dans ce guide. Chaque ressource inclut des exemples de code complets avec des explications pas à pas pour vous aider à maîtriser des fonctionnalités API supplémentaires et explorer des approches d’implémentation alternatives dans vos propres projets.

- [Créer une image de code‑barres DotCode – rangées & colonnes (Aspose.BarCode)](/barcode/english/net/dotcode-barcode-configuration/dotcode-rows-columns-configuration/)
- [Créer une image de code‑barres c# – Configurer les rangées & colonnes de Codablock F](/barcode/english/net/codablock-f-encoding/codablock-f-row-column-configuration/)
- [Générer une image de code‑barres – GS1 Coupon UPC‑A Databar](/barcode/english/net/gs1-barcode-encoding/gs1-coupon-upc-a-databar-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}