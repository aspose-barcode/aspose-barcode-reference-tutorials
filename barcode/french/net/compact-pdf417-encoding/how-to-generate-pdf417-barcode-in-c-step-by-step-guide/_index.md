---
category: general
date: 2026-09-10
description: Générez rapidement un code‑barres PDF417 en C#. Apprenez à créer un PDF417
  et à modifier la taille du code‑barres avec Aspose.BarCode en quelques lignes seulement.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate PDF417 barcode
- how to generate PDF417
- how to change barcode size
language: fr
lastmod: 2026-09-10
og_description: Générez un code‑barres PDF417 en C# instantanément. Ce tutoriel montre
  comment générer un PDF417 et comment modifier la taille du code‑barres à l’aide
  d’Aspose.BarCode.
og_image_alt: generate PDF417 barcode example showing 4 columns and 9 rows
og_title: Générer un code‑barres PDF417 en C# – guide complet de programmation
schemas:
- author: Aspose
  dateModified: '2026-09-10'
  description: Generate PDF417 barcode in C# quickly. Learn how to generate PDF417
    and how to change barcode size with Aspose.BarCode in just a few lines.
  headline: How to generate PDF417 barcode in C# – step‑by‑step guide
  type: TechArticle
- description: Generate PDF417 barcode in C# quickly. Learn how to generate PDF417
    and how to change barcode size with Aspose.BarCode in just a few lines.
  name: How to generate PDF417 barcode in C# – step‑by‑step guide
  steps:
  - name: 'Create a new console project:'
    text: 'Create a new console project:'
  - name: Add the Aspose.BarCode reference (see prerequisites).
    text: Add the Aspose.BarCode reference (see prerequisites).
  - name: Open `Program.cs` and replace its content with the full example below.
    text: Open `Program.cs` and replace its content with the full example below.
  type: HowTo
tags:
- barcode
- C#
- PDF417
title: Comment générer un code‑barres PDF417 en C# – guide étape par étape
url: /fr/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Comment générer un code‑barres PDF417 en C# – guide étape par étape

Si vous devez **générer un code‑barres PDF417** dans une application .NET, ce guide vous montre exactement comment le faire. Vous verrez un exemple concis, prêt à l’emploi, qui crée un code‑barres PDF417, vous permet de contrôler sa taille et enregistre le résultat sous forme d’image PNG.

La génération d’un code‑barres PDF417 est une exigence courante pour les systèmes d’inventaire, les cartes d’embarquement et le suivi de documents. Dans ce tutoriel, nous abordons également **comment modifier la taille du code‑barres** afin que le code s’adapte à différents besoins d’impression ou d’affichage à l’écran.

## Prérequis

Avant de commencer, assurez‑vous d’avoir :

* .NET 6.0 ou supérieur (le code fonctionne également avec .NET Framework 4.6+)
* Visual Studio 2022 ou tout IDE C#
* Le package NuGet **Aspose.BarCode for .NET**  
  ```bash
  dotnet add package Aspose.BarCode
  ```
* Une connaissance de base des applications console C#

## Configuration du projet

1. Créez un nouveau projet console :

   ```bash
   dotnet new console -n Pdf417Demo
   cd Pdf417Demo
   ```

2. Ajoutez la référence Aspose.BarCode (voir les prérequis).  

3. Ouvrez `Program.cs` et remplacez son contenu par l’exemple complet ci‑dessous.

## Étape 1 : Générer le code‑barres PDF417

La première étape consiste à créer une instance `BarcodeGenerator` configurée pour la symbologie **PDF417**. Cet objet est le point d’entrée pour toutes les opérations de code‑barres.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Step 1: Create a PDF417 barcode generator with the desired text
        BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Layout test");
```

*Pourquoi c’est important* – La valeur d’énumération `EncodeTypes.Pdf417` indique à Aspose.BarCode d’utiliser la norme PDF417, tandis que le deuxième argument fournit les données à encoder. Le générateur possède maintenant un objet code‑barres complet que vous pouvez personnaliser avant de l’enregistrer.

## Étape 2 : Comment modifier la taille du code‑barres (taille du module)

Les codes‑barres PDF417 sont composés de petits modules carrés. Modifier la taille du module change les dimensions globales de l’image sans altérer les données encodées.

```csharp
        // Step 2: Define the module size (X‑dimension) in pixels
        generator.Parameters.Barcode.XDimension.Pixels = 2; // 2 px per module
```

*Pourquoi c’est important* – Un `XDimension` plus grand produit un code‑barres plus gros, adapté à l’impression haute résolution ; une valeur plus petite convient mieux à l’affichage à l’écran. La valeur par défaut est généralement de 1 px, ce qui peut paraître trop serré sur les écrans modernes.

## Étape 3 : Configurer la disposition – colonnes et lignes

PDF417 vous permet de définir le nombre de colonnes et de lignes, ce qui influence à la fois la forme du code‑barres et sa capacité de correction d’erreurs.

```csharp
        // Step 3: Configure the layout – set the number of columns and rows
        generator.Parameters.Barcode.Pdf417.Columns = 4; // 4 columns
        generator.Parameters.Barcode.Pdf417.Rows    = 9; // 9 rows
```

*Pourquoi c’est important* – Plus de colonnes rendent le code‑barres plus large, tandis que plus de lignes le rendent plus haut. Ajustez ces valeurs pour qu’elles s’adaptent à l’espace disponible dans votre interface ou sur votre étiquette imprimée.

## Étape 4 : Enregistrer l’image du code‑barres

Enfin, écrivez le code‑barres dans un fichier. Ici nous utilisons le PNG car il préserve les bords nets et prend en charge la transparence.

```csharp
        // Step 4: Save the generated barcode as a PNG image
        string outputPath = "LayoutPdf417.png";
        generator.Save(outputPath, BarCodeImageFormat.Png);

        Console.WriteLine($"PDF417 barcode saved to {outputPath}");
    }
}
```

L’exécution du programme crée `LayoutPdf417.png` dans le dossier de sortie du projet. L’image ressemble à ceci :

![générer un exemple de code‑barres PDF417 montrant 4 colonnes et 9 lignes](https://example.com/images/pdf417-sample.png){#barcode-image alt="générer un exemple de code‑barres PDF417 montrant 4 colonnes et 9 lignes"}

*Astuce* : Si vous avez besoin d’un autre format d’image (JPEG, BMP, TIFF), remplacez `BarCodeImageFormat.Png` par la valeur d’énumération appropriée.

## Comment générer PDF417 – sources de données alternatives

Le code ci‑dessus utilise une chaîne codée en dur `"Layout test"`. Dans des scénarios réels, vous récupérez souvent les données depuis une base de données, un fichier ou une saisie utilisateur.

```csharp
string dataFromDb = GetOrderNumber(); // your own method
BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, dataFromDb);
```

Le reste des étapes (taille, disposition, enregistrement) reste inchangé. Cela montre **comment générer PDF417** à partir de sources dynamiques sans complexité supplémentaire.

## Pièges courants et comment les éviter

| Problème | Pourquoi cela se produit | Solution |
|----------|--------------------------|----------|
| Le code‑barres apparaît flou | `XDimension` trop faible pour la résolution de sortie | Augmentez `XDimension.Pixels` ou enregistrez au format vectoriel comme SVG (`BarCodeImageFormat.Svg`) |
| Le texte ne tient pas dans la disposition choisie | Trop de caractères pour les lignes/colonnes sélectionnées | Réduisez le nombre de lignes/colonnes ou divisez les données en plusieurs codes‑barres |
| Le fichier image n’est pas créé | Le dossier de sortie n’existe pas ou les permissions d’écriture sont manquantes | Assurez‑vous que le répertoire existe (`Directory.CreateDirectory`) et que l’application s’exécute avec les droits appropriés |

## Vérification du code‑barres

Après avoir généré l’image, vous pouvez la vérifier avec n’importe quelle application de lecture PDF417 (les téléphones mobiles disposent d’applications gratuites) ou avec le lecteur intégré d’Aspose.BarCode :

```csharp
using Aspose.BarCode.BarCodeRecognition;

// Load the image we just saved
BarCodeReader reader = new BarCodeReader(outputPath, DecodeType.Pdf417);
if (reader.Read())
{
    Console.WriteLine($"Decoded text: {reader.GetCodeText()}");
}
else
{
    Console.WriteLine("Failed to decode the barcode.");
}
```

Si la sortie correspond au texte original, le processus **générer le code‑barres PDF417** a réussi.

## Exemple complet et exécutable

Voici le programme complet que vous pouvez copier‑coller dans `Program.cs`. Il comprend toutes les directives `using`, la gestion des erreurs et les commentaires.

```csharp
using System;
using System.IO;
using Aspose.BarCode;
using Aspose.BarCode.Generation;
using Aspose.BarCode.BarCodeRecognition;

class Program
{
    static void Main()
    {
        // Prepare output directory
        string outputDir = Path.Combine(Directory.GetCurrentDirectory(), "output");
        Directory.CreateDirectory(outputDir);
        string outputPath = Path.Combine(outputDir, "LayoutPdf417.png");

        // 1️⃣ Create the generator with the data to encode
        BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Layout test");

        // 2️⃣ Change barcode size (module size)
        generator.Parameters.Barcode.XDimension.Pixels = 2; // 2 px per module

        // 3️⃣ Set layout – columns and rows
        generator.Parameters.Barcode.Pdf417.Columns = 4;
        generator.Parameters.Barcode.Pdf417.Rows    = 9;

        // 4️⃣ Save as PNG
        generator.Save(outputPath, BarCodeImageFormat.Png);
        Console.WriteLine($"PDF417 barcode saved to {outputPath}");

        // 5️⃣ Verify the barcode by reading it back
        BarCodeReader reader = new BarCodeReader(outputPath, DecodeType.Pdf417);
        if (reader.Read())
        {
            Console.WriteLine($"Decoded text: {reader.GetCodeText()}");
        }
        else
        {
            Console.WriteLine("Failed to decode the barcode.");
        }
    }
}
```

L’exécution de ce programme affiche :

```
PDF417 barcode saved to C:\...\output\LayoutPdf417.png
Decoded text: Layout test
```

Vous disposez maintenant d’une **solution complète et autonome** pour générer des codes‑barres PDF417 et contrôler leur taille.

## Conclusion

Dans ce tutoriel, vous avez appris comment **générer un code‑barres PDF417** en C# avec Aspose.BarCode, comment **modifier la taille du code‑barres** en ajustant la dimension X, et comment configurer les colonnes et les lignes pour contrôler la mise en page. Vous avez également vu comment vérifier le résultat programmatiquement et comment adapter le code à des données dynamiques.

Ensuite, vous pourriez explorer :

* **Comment générer PDF417** avec réglage du niveau de correction d’erreurs (`generator.Parameters.Barcode.Pdf417.ErrorLevel`)
* Exportation vers des **formats vectoriels** (SVG, EPS) pour un redimensionnement infini
* Intégration du code‑barres dans un document PDF avec **Aspose.PDF**

Expérimentez différentes tailles de modules et options de mise en page pour répondre à vos exigences spécifiques d’interface ou d’impression. Bon codage !

## Que devriez‑vous apprendre ensuite ?

Les tutoriels suivants couvrent des sujets étroitement liés qui s’appuient sur les techniques démontrées dans ce guide. Chaque ressource inclut des exemples de code complets avec des explications étape par étape pour vous aider à maîtriser des fonctionnalités API supplémentaires et à explorer des approches d’implémentation alternatives dans vos propres projets.

- [How to Generate PDF417 Barcode with Aspose – Complete Guide](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-with-aspose-complete-guide/)
- [adjust barcode size – C# guide to generate PDF417 barcodes](/barcode/english/net/compact-pdf417-encoding/adjust-barcode-size-c-guide-to-generate-pdf417-barcodes/)
- [How to Save Barcode in C# – Generate PDF417 Barcodes](/barcode/english/net/compact-pdf417-encoding/how-to-save-barcode-in-c-generate-pdf417-barcodes/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}