---
category: general
date: 2026-09-13
description: Créez rapidement un code‑barres Databar empilé en C# avec Aspose.Barcode
  – apprenez à définir les colonnes, les lignes et à enregistrer les images.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create databar stacked barcode
- Databar Expanded Stacked
- barcode columns
- barcode rows
- Aspose.Barcode for .NET
- C# barcode generator
language: fr
lastmod: 2026-09-13
og_description: Créer un code‑barres databar empilé en C# avec Aspose.Barcode. Ce
  guide montre comment configurer les colonnes, les lignes et exporter des images
  PNG.
og_image_alt: Screenshot of a generated Databar stacked barcode saved as PNG
og_title: Créer un code‑barres Databar empilé en C# – Guide complet étape par étape
schemas:
- author: Aspose
  dateModified: '2026-09-13'
  description: Create databar stacked barcode in C# quickly using Aspose.Barcode –
    learn to set columns, rows, and save images.
  headline: How to create databar stacked barcode in C# with Aspose.Barcode
  type: TechArticle
- description: Create databar stacked barcode in C# quickly using Aspose.Barcode –
    learn to set columns, rows, and save images.
  name: How to create databar stacked barcode in C# with Aspose.Barcode
  steps:
  - name: 'Create a new Console App project:'
    text: 'Create a new Console App project:'
  - name: 'Add the Aspose.Barcode package:'
    text: 'Add the Aspose.Barcode package:'
  - name: 'Open **Program.cs** and add the required `using` statements:'
    text: 'Open **Program.cs** and add the required `using` statements:'
  type: HowTo
tags:
- barcode
- C#
- Aspose
- Databar
title: Comment créer un code‑barres Databar empilé en C# avec Aspose.Barcode
url: /fr/python-java/general/how-to-create-databar-stacked-barcode-in-c-with-aspose-barco/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Comment créer un code‑barres Databar empilé en C# avec Aspose.Barcode

Si vous devez **créer un code‑barres databar empilé** dans une application .NET, ce guide vous fournit une solution complète, prête à l’exécution. Vous verrez exactement comment configurer le nombre de colonnes, ajuster les lignes et enregistrer le résultat sous forme de fichier PNG — le tout avec la bibliothèque Aspose.Barcode pour .NET.

Générer un code‑barres **Databar Expanded Stacked** n’est pas un mystère une fois que vous comprenez le flux de travail en trois étapes : instancier le générateur, définir les dimensions souhaitées et écrire l’image sur le disque. Les sections suivantes vous accompagnent pas à pas, expliquent pourquoi ces paramètres sont importants et vous montrent le résultat final que vous pouvez vérifier immédiatement.

## Prérequis

Avant de commencer, assurez‑vous d’avoir :

- **Visual Studio 2022** (ou tout IDE C#) avec .NET 6+ installé.  
- Le package NuGet **Aspose.Barcode for .NET** (`Install-Package Aspose.Barcode`).  
- Des droits d’écriture sur un dossier où les fichiers PNG seront enregistrés.

Aucune dépendance supplémentaire n’est requise.

## Étape 1 : Configurer le projet et ajouter Aspose.Barcode

1. Créez un nouveau projet Console App :

   ```bash
   dotnet new console -n DatabarStackedDemo
   cd DatabarStackedDemo
   ```

2. Ajoutez le package Aspose.Barcode :

   ```bash
   dotnet add package Aspose.Barcode
   ```

3. Ouvrez **Program.cs** et ajoutez les instructions `using` requises :

   ```csharp
   using Aspose.BarCode;
   using Aspose.BarCode.Generation;
   using System;
   ```

Ces étapes garantissent que les classes **C# barcode generator** sont disponibles dans votre code.

## Étape 2 : Créer un générateur pour un code‑barres Databar empilé

Le premier objet dont vous avez besoin est un `BarcodeGenerator` configuré pour la symbologie **Databar Expanded Stacked**. Cet objet est le point d’entrée pour toutes les opérations liées aux codes‑barres.

```csharp
// Step 2: Initialize a generator for Databar Expanded Stacked
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.DatabarExpandedStacked, // Symbology
    "Databar Expanded Stacked long");   // Human‑readable text (optional)
```

**Pourquoi c’est important :**  
`EncodeTypes.DatabarExpandedStacked` indique à Aspose.Barcode d’utiliser la version empilée de la famille DataBar, idéale pour les espaces à hauteur limitée comme les tickets de caisse. Le deuxième argument fournit les données encodées dans le code‑barres ; vous pouvez le remplacer par n’importe quelle chaîne numérique ou alphanumérique conforme à la norme DataBar.

## Étape 3 : Configurer les colonnes du code‑barres et enregistrer l’image

Un DataBar empilé peut être affiché avec un nombre configurable de **colonnes**. La valeur par défaut est trois, mais vous pouvez avoir besoin de quatre colonnes pour des chaînes de données plus longues. Ajustez la propriété `Columns` avant d’enregistrer.

```csharp
// Step 3: Set the barcode to use 4 columns (default rows) and save the image
barcodeGenerator.Parameters.Barcode.DataBar.Columns = 4;

// Choose an output folder that exists on your machine
string outputPathCols = @"YOUR_DIRECTORY\DatabarCols4.png";
barcodeGenerator.Save(outputPathCols, BarCodeImageFormat.Png);

Console.WriteLine($"Barcode with 4 columns saved to {outputPathCols}");
```

**Explication :**  
- `Parameters.Barcode.DataBar.Columns` influence directement la segmentation horizontale du code‑barres. Plus de colonnes créent une image plus large tout en conservant la même hauteur.  
- `Save` écrit le code‑barres dans un fichier PNG. D’autres formats (JPEG, BMP, SVG) sont également pris en charge en passant une valeur différente de `BarCodeImageFormat`.

## Étape 4 : Créer un autre générateur et configurer les lignes du code‑barres

Parfois, l’environnement de numérisation nécessite un code‑barres plus haut, ce que vous obtenez en augmentant le nombre de **lignes**. L’extrait suivant crée une seconde instance de générateur, définit trois lignes et enregistre le résultat.

```csharp
// Step 4: Create a new generator for the same data but with 3 rows
BarcodeGenerator barcodeGeneratorRows = new BarcodeGenerator(
    EncodeTypes.DatabarExpandedStacked,
    "Databar Expanded Stacked long");

// Set the barcode to use 3 rows (default columns)
barcodeGeneratorRows.Parameters.Barcode.DataBar.Rows = 3;

// Save the image with rows configured
string outputPathRows = @"YOUR_DIRECTORY\DatabarRows3.png";
barcodeGeneratorRows.Save(outputPathRows, BarCodeImageFormat.Png);

Console.WriteLine($"Barcode with 3 rows saved to {outputPathRows}");
```

**Pourquoi une instance séparée ?**  
Modifier `Rows` sur le même `BarcodeGenerator` après un appel à `Save` fonctionnerait également, mais créer une nouvelle instance garde chaque configuration isolée et rend le code plus lisible — surtout lorsque vous étendrez le tutoriel pour couvrir d’autres variantes (par ex., différentes chaînes de données ou niveaux de correction d’erreurs).

## Étape 5 : Vérifier les codes‑barres générés

Ouvrez les deux fichiers PNG que vous venez de créer. Vous devriez voir :

- **DatabarCols4.png** – un code‑barres plus large composé de quatre colonnes verticales.  
- **DatabarRows3.png** – un code‑barres plus haut composé de trois lignes horizontales.

Les deux images encodent le même texte (`"Databar Expanded Stacked long"`), mais leurs structures visuelles diffèrent. Scannez‑les avec n’importe quel lecteur DataBar standard ou une application mobile qui prend en charge DataBar pour confirmer qu’ils se décodent correctement.

## Pièges courants et astuces professionnelles

| Problème | Pourquoi cela se produit | Comment l’éviter |
|----------|--------------------------|------------------|
| **Chemin de dossier incorrect** | `Save` lève `DirectoryNotFoundException` si le répertoire n’existe pas. | Utilisez `Directory.CreateDirectory(Path.GetDirectoryName(outputPath))` avant d’appeler `Save`. |
| **Trop de colonnes/lignes** | Les spécifications DataBar limitent les colonnes à 4 et les lignes à 3. | Respectez la plage autorisée ; Aspose.Barcode lèvera `ArgumentOutOfRangeException` sinon. |
| **Code‑barres illisible** | Une résolution d’image faible peut rendre le code‑barres flou. | Augmentez le DPI via `barcodeGenerator.Parameters.ImageResolution` si vous avez besoin d’une meilleure qualité (par ex., 300 dpi). |
| **Format de données incorrect** | DataBar n’accepte que des chaînes numériques jusqu’à 13 chiffres pour certains modes. | Validez votre chaîne d’entrée avant de la transmettre au générateur. |

## Extension de l’exemple

Maintenant que vous pouvez **créer un code‑barres databar empilé** avec des colonnes et des lignes personnalisées, vous pourriez explorer :

- **Modifier les couleurs de premier plan/arrière‑plan** (`barcodeGenerator.Parameters.Barcode.Color = Color.Blue;`).  
- **Ajouter une zone silencieuse** (`barcodeGenerator.Parameters.Barcode.Qz = 2;`).  
- **Exporter en SVG** pour un rendu indépendant de la résolution (`BarCodeImageFormat.Svg`).

Toutes ces options sont documentées dans la [référence API Aspose.Barcode for .NET](https://docs.aspose.com/barcode/net/).

## Code source complet

Voici le programme complet, exécutable, qui intègre chaque étape décrite ci‑dessus. Copiez‑le dans votre `Program.cs`, remplacez `YOUR_DIRECTORY` par un chemin réel, puis exécutez `dotnet run`.

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;
using System;
using System.IO;

class Program
{
    static void Main()
    {
        // Ensure the output directory exists
        string outputDir = @"YOUR_DIRECTORY";
        Directory.CreateDirectory(outputDir);

        // -------------------------------------------------
        // Step 1: Generator for 4‑column stacked barcode
        // -------------------------------------------------
        BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
            EncodeTypes.DatabarExpandedStacked,
            "Databar Expanded Stacked long");

        // Set 4 columns (default rows = 2)
        barcodeGenerator.Parameters.Barcode.DataBar.Columns = 4;

        string colsPath = Path.Combine(outputDir, "DatabarCols4.png");
        barcodeGenerator.Save(colsPath, BarCodeImageFormat.Png);
        Console.WriteLine($"Saved 4‑column barcode to {colsPath}");

        // -------------------------------------------------
        // Step 2: Generator for 3‑row stacked barcode
        // -------------------------------------------------
        BarcodeGenerator barcodeGeneratorRows = new BarcodeGenerator(
            EncodeTypes.DatabarExpandedStacked,
            "Databar Expanded Stacked long");

        // Set 3 rows (default columns = 2)
        barcodeGeneratorRows.Parameters.Barcode.DataBar.Rows = 3;

        string rowsPath = Path.Combine(outputDir, "DatabarRows3.png");
        barcodeGeneratorRows.Save(rowsPath, BarCodeImageFormat.Png);
        Console.WriteLine($"Saved 3‑row barcode to {rowsPath}");
    }
}
```

L’exécution du programme produit deux fichiers PNG qui démontrent comment les **colonnes de code‑barres** et les **lignes de code‑barres** influencent la mise en page visuelle d’un symbole **Databar Expanded Stacked**.

## Conclusion

Vous savez maintenant comment **créer un code‑barres databar empilé** en C# avec Aspose.Barcode pour .NET. En ajustant les propriétés `Columns` et `Rows`, vous pouvez générer des codes‑barres qui s’adaptent à une large gamme de contraintes d’espace tout en préservant l’intégrité des données. L’exemple couvre tout, de la configuration du projet au dépannage, vous offrant une base solide pour des scénarios de codes‑barres plus avancés.

**Étapes suivantes :**  
- Expérimentez avec différentes chaînes de données et observez comment les limites de colonnes/lignes impactent la lisibilité.  
- Combinez ce code avec une API web pour générer des codes‑barres à la demande.  
- Explorez d’autres symbologies (par ex., QR, Code128) en utilisant le même modèle `BarcodeGenerator`.

Bon codage, et que vos scans soient toujours réussis !

## Que devez‑vous apprendre ensuite ?

Les tutoriels suivants couvrent des sujets étroitement liés qui s’appuient sur les techniques démontrées dans ce guide. Chaque ressource inclut des exemples de code complets avec des explications pas à pas pour vous aider à maîtriser d’autres fonctionnalités de l’API et à explorer des approches d’implémentation alternatives dans vos propres projets.

- [Barcode Generator C# – Create DataBar Expanded Stacked Images](/barcode/english/python-java/general/barcode-generator-c-create-databar-expanded-stacked-images/)
- [databar expanded stacked barcode guide – how to generate and size it in C#](/barcode/english/python-java/general/databar-expanded-stacked-barcode-guide-how-to-generate-and-s/)
- [Generate Aspose.BarCode Databar barcode using .NET API – Row & Column Configuration](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-row-column-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}