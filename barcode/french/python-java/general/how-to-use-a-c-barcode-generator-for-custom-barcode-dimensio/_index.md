---
category: general
date: 2026-08-22
description: Apprenez comment un générateur de codes‑barres C# peut modifier la taille
  du code‑barres, ajuster les dimensions et générer plusieurs lignes dans un code‑barres
  DataBar Expanded Stacked.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- c# barcode generator
- change barcode size
- custom barcode dimensions
- generate barcode multiple rows
- adjust barcode dimensions
language: fr
lastmod: 2026-08-22
og_description: Tutoriel de générateur de code-barres C# montrant comment modifier
  la taille du code-barres, ajuster les dimensions et générer plusieurs lignes de
  code-barres avec des paramètres personnalisés.
og_image_alt: Screenshot of a c# barcode generator output displaying a custom DataBar
  Expanded Stacked barcode
og_title: Guide du générateur de codes-barres C# – modifier la taille, les lignes
  et les colonnes
schemas:
- author: Aspose
  dateModified: '2026-08-22'
  description: Learn how a C# barcode generator can change barcode size, adjust dimensions,
    and generate multiple rows in a DataBar Expanded Stacked barcode.
  headline: How to use a C# barcode generator for custom barcode dimensions
  type: TechArticle
tags:
- barcode
- C#
- Aspose.Barcode
title: Comment utiliser un générateur de code-barres C# pour des dimensions de code-barres
  personnalisées
url: /fr/python-java/general/how-to-use-a-c-barcode-generator-for-custom-barcode-dimensio/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Comment utiliser un générateur de code-barres C# pour des dimensions de code-barres personnalisées

Si vous avez besoin d'un **c# barcode generator** qui vous permet de **modifier la taille du code-barres** à la volée, ce guide vous montre exactement comment faire. Nous générerons un code-barres DataBar Expanded Stacked, ajusterons sa largeur et sa hauteur en définissant des colonnes et des lignes personnalisées, et enregistrerons trois images d'exemple.

Vous terminerez le tutoriel avec un programme console complet et exécutable qui démontre les **custom barcode dimensions**, **generate barcode multiple rows**, et **adjust barcode dimensions** sans quitter l'IDE.

## Ce dont vous aurez besoin

| Prérequis | Pourquoi c'est important |
|--------------|----------------|
| .NET 6.0 SDK or later | Fournit le runtime pour l'application console |
| Visual Studio 2022 (or VS Code) | Vous fournit un éditeur avec IntelliSense |
| Aspose.Barcode for .NET NuGet package | Fournit la classe `BarcodeGenerator` utilisée dans les exemples |
| Write permission to a folder on disk | Le générateur enregistre les fichiers PNG à cet emplacement |

Installez la bibliothèque avec le CLI NuGet :

```bash
dotnet add package Aspose.Barcode
```

Ou utilisez le Gestionnaire de packages Visual Studio :

```powershell
Install-Package Aspose.Barcode
```

## Étape 1 : Configurer un générateur de code-barres C# de base

Créez un nouveau projet console et ajoutez les directives `using` requises. Cette étape crée un **c# barcode generator** minimal qui peut générer un simple code-barres DataBar Expanded Stacked.

```csharp
using System;
using Aspose.BarCode.Generation;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // Define the folder where PNG files will be saved.
            string outputPath = @"C:\Temp\Barcodes\";

            // Ensure the directory exists.
            System.IO.Directory.CreateDirectory(outputPath);

            // Create a basic generator for the DataBar Expanded Stacked type.
            BarcodeGenerator generator = new BarcodeGenerator(
                EncodeTypes.DatabarExpandedStacked,
                "Databar Expanded Stacked demo");

            // Save the default barcode (no custom dimensions yet).
            generator.Save($"{outputPath}DefaultDatabar.png", BarCodeImageFormat.Png);

            Console.WriteLine("Default barcode generated.");
        }
    }
}
```

**Pourquoi cela fonctionne :** `EncodeTypes.DatabarExpandedStacked` indique au générateur quelle symbologie utiliser. La méthode `Save` écrit un fichier PNG sur le disque. À ce stade, le code-barres utilise la taille par défaut de la bibliothèque.

## Étape 2 : Modifier la taille du code-barres en ajustant les colonnes

La largeur d'un code-barres DataBar Expanded Stacked est contrôlée par la propriété **columns**. Modifier cette propriété permet au **c# barcode generator** de produire un code-barres plus large ou plus étroit.

```csharp
// Adjust the number of columns to 4 (wider barcode)
generator.Parameters.Barcode.DataBar.Columns = 4;

// Save the barcode with custom columns.
generator.Save($"{outputPath}DatabarCols4.png", BarCodeImageFormat.Png);

Console.WriteLine("Barcode with 4 columns generated.");
```

**Explication :** Les colonnes affectent le nombre de modules horizontaux. Plus de colonnes signifient un code-barres plus large, ce qui est utile lorsque vous avez besoin d'espace supplémentaire pour un texte lisible plus long ou lors de l'impression sur des étiquettes larges.

## Étape 3 : Générer plusieurs lignes de code-barres pour contrôler la hauteur

La hauteur est régie par la propriété **rows**. En augmentant les lignes, vous **generate barcode multiple rows** et rendez le symbole plus haut — idéal pour les scans haute résolution.

```csharp
// Change the barcode to have 3 rows (taller barcode)
generator.Parameters.Barcode.DataBar.Rows = 3;

// Save the taller barcode.
generator.Save($"{outputPath}DatabarRows3.png", BarCodeImageFormat.Png);

Console.WriteLine("Barcode with 3 rows generated.");
```

**Pourquoi les lignes sont importantes :** Les lignes ajoutent des modules verticaux. Un code-barres plus haut peut améliorer la lisibilité sur des fonds à faible contraste ou lorsque la distance de mise au point du scanner varie.

## Étape 4 : Combiner colonnes et lignes personnalisées pour un contrôle complet

Maintenant que vous savez comment **adjust barcode dimensions**, vous pouvez définir les deux propriétés ensemble. Cette étape crée un code-barres avec six colonnes et dix lignes, démontrant la pleine flexibilité du **c# barcode generator**.

```csharp
// Set both columns and rows for a custom size.
generator.Parameters.Barcode.DataBar.Columns = 6; // Wider
generator.Parameters.Barcode.DataBar.Rows = 10;   // Taller

// Save the custom-sized barcode.
generator.Save($"{outputPath}DatabarCols6Rows10.png", BarCodeImageFormat.Png);

Console.WriteLine("Custom barcode with 6 columns and 10 rows generated.");
```

**Résultat :** Le fichier `DatabarCols6Rows10.png` contient un code-barres à la fois plus large et plus haut que les valeurs par défaut, prouvant que vous pouvez **adjust barcode dimensions** pour répondre à n'importe quelle exigence de mise en page.

## Exemple complet exécutable

Voici le programme complet qui intègre les quatre étapes. Copiez-le dans `Program.cs`, exécutez `dotnet run`, et vérifiez le dossier `C:\Temp\Barcodes\` pour les quatre fichiers PNG.

```csharp
using System;
using Aspose.BarCode.Generation;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // -------------------------------------------------
            // 1️⃣  Prepare output folder
            // -------------------------------------------------
            string outputPath = @"C:\Temp\Barcodes\";
            System.IO.Directory.CreateDirectory(outputPath);

            // -------------------------------------------------
            // 2️⃣  Create a basic C# barcode generator
            // -------------------------------------------------
            BarcodeGenerator generator = new BarcodeGenerator(
                EncodeTypes.DatabarExpandedStacked,
                "Databar Expanded Stacked demo");

            // -------------------------------------------------
            // 3️⃣  Default barcode (no size changes)
            // -------------------------------------------------
            generator.Save($"{outputPath}DefaultDatabar.png", BarCodeImageFormat.Png);
            Console.WriteLine("Default barcode generated.");

            // -------------------------------------------------
            // 4️⃣  Change barcode size – custom columns
            // -------------------------------------------------
            generator.Parameters.Barcode.DataBar.Columns = 4;
            generator.Save($"{outputPath}DatabarCols4.png", BarCodeImageFormat.Png);
            Console.WriteLine("Barcode with 4 columns generated.");

            // -------------------------------------------------
            // 5️⃣  Generate barcode multiple rows – custom rows
            // -------------------------------------------------
            generator.Parameters.Barcode.DataBar.Rows = 3;
            generator.Save($"{outputPath}DatabarRows3.png", BarCodeImageFormat.Png);
            Console.WriteLine("Barcode with 3 rows generated.");

            // -------------------------------------------------
            // 6️⃣  Adjust barcode dimensions – both columns & rows
            // -------------------------------------------------
            generator.Parameters.Barcode.DataBar.Columns = 6; // Wider
            generator.Parameters.Barcode.DataBar.Rows = 10;   // Taller
            generator.Save($"{outputPath}DatabarCols6Rows10.png", BarCodeImageFormat.Png);
            Console.WriteLine("Custom barcode with 6 columns and 10 rows generated.");

            Console.WriteLine("All barcodes saved to: " + outputPath);
        }
    }
}
```

### Résultat attendu

L'exécution du programme produit quatre fichiers PNG :

| Nom du fichier                | Description visuelle |
|--------------------------|--------------------|
| `DefaultDatabar.png`     | Largeur et hauteur standard |
| `DatabarCols4.png`       | Code-barres plus large (4 colonnes) |
| `DatabarRows3.png`       | Code-barres plus haut (3 lignes) |
| `DatabarCols6Rows10.png` | À la fois plus large et plus haut (6 colonnes, 10 lignes) |

Ouvrez n'importe quel PNG dans un visualiseur d'images ; vous verrez le motif DataBar Expanded Stacked ajusté exactement comme spécifié.

## Pièges courants et astuces professionnelles

- **Invalid column/row values** – La bibliothèque lance `ArgumentException` si vous définissez une valeur en dehors de la plage prise en charge (1‑12 pour les colonnes, 1‑10 pour les lignes). Validez les entrées avant d'assigner.
- **Directory permissions** – Si le dossier de sortie est protégé, `Save` échouera. Utilisez `System.IO.Directory.CreateDirectory` comme indiqué pour garantir que le chemin existe.
- **Performance** – Créer de nombreux codes-barres dans une boucle peut être intensif pour le CPU. Réutilisez la même instance `BarcodeGenerator` et ne modifiez que `Columns`/`Rows` entre les sauvegardes pour réduire la surcharge d'allocation d'objets.
- **Scanning considerations** – Des codes-barres extrêmement hauts ou larges peuvent dépasser le champ de vision du scanner. Testez avec votre matériel cible après avoir ajusté les dimensions.

## Conclusion

Vous disposez maintenant d'un exemple solide de **c# barcode generator** qui peut **change barcode size**, **custom barcode dimensions**, **generate barcode multiple rows**, et **adjust barcode dimensions** pour s'adapter à n'importe quelle application. En ajustant les propriétés `Columns` et `Rows`, vous obtenez un contrôle précis sur l'empreinte visuelle d'un code-barres DataBar Expanded Stacked.

N'hésitez pas à expérimenter d'autres symbologies (`EncodeTypes.QR`, `EncodeTypes.Code128`) ou formats de sortie (`BarCodeImageFormat.Jpeg`, `BarCodeImageFormat.Svg`). Le même schéma — créer un `BarcodeGenerator`, définir les propriétés de dimension, puis appeler `Save` — s'applique à l'ensemble de l'API Aspose.Barcode.

**Étapes suivantes**

- Explore **error correction levels** for QR codes.
- Combine **custom colors** and **background images** to brand your barcodes.
- Integrate the generator into an ASP.NET Core web service for on‑demand barcode creation.

Bon codage !

## Que devriez‑vous apprendre ensuite ?

Les tutoriels suivants couvrent des sujets étroitement liés qui s'appuient sur les techniques démontrées dans ce guide. Chaque ressource comprend des exemples de code complets et fonctionnels avec des explications étape par étape pour vous aider à maîtriser des fonctionnalités supplémentaires de l'API et explorer des approches d'implémentation alternatives dans vos propres projets.

- [Comment générer et ajuster la hauteur du code-barres pour Databar unidimensionnel avec Aspose.BarCode pour .NET](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-barcode-height-adjustment/)
- [Comment ajuster la taille du code-barres – Ratio d'aspect Codablock F avec Aspose.BarCode pour .NET](/barcode/english/net/codablock-f-encoding/codablock-f-aspect-ratio-customization/)
- [Comment générer un code-barres Aztec avec un ratio d'aspect personnalisé en utilisant Aspose.BarCode pour .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}