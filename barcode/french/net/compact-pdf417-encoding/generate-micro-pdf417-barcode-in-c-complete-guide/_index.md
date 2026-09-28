---
category: general
date: 2026-07-18
description: Générez un code‑barres micro PDF417 avec Aspose.BarCode pour .NET – guide
  étape par étape couvrant les colonnes, les lignes et la sortie PNG.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate micro pdf417 barcode
- Aspose.BarCode for .NET
- MicroPdf417 columns
- MicroPdf417 rows
- C# barcode generation
language: fr
lastmod: 2026-07-18
og_description: Générez instantanément un code‑barres micro PDF417 avec Aspose.BarCode
  pour .NET. Apprenez à contrôler les colonnes, les lignes et à enregistrer au format
  PNG en quelques minutes.
og_image_alt: Screenshot of a generated Micro PDF417 barcode saved as PNG
og_title: Générer un code-barres Micro PDF417 – Tutoriel complet C#
schemas:
- author: Aspose
  dateModified: '2026-07-18'
  description: Generate micro pdf417 barcode with Aspose.BarCode for .NET – step‑by‑step
    guide covering columns, rows, and PNG output.
  headline: Generate Micro PDF417 Barcode in C# – Complete Guide
  type: TechArticle
- description: Generate micro pdf417 barcode with Aspose.BarCode for .NET – step‑by‑step
    guide covering columns, rows, and PNG output.
  name: Generate Micro PDF417 Barcode in C# – Complete Guide
  steps:
  - name: 4.1 Two Columns, Auto‑Calculated Rows
    text: '```csharp // Force 2 columns, let rows auto‑adjust generator.Parameters.Barcode.Pdf417.Columns
      = 2; generator.Parameters.Barcode.Pdf417.Rows = 0; // 0 = auto generator.Save("MicroPdf417Columns2.png",
      BarCodeImageFormat.Png); Console.WriteLine("Saved: MicroPdf417Columns2.png");
      ```'
  - name: 4.2 Six Rows, Auto‑Calculated Columns
    text: '```csharp // Switch to 6 rows, columns auto‑determined generator.Parameters.Barcode.Pdf417.Columns
      = 0; // auto columns generator.Parameters.Barcode.Pdf417.Rows = 6; generator.Save("MicroPdf417Rows6.png",
      BarCodeImageFormat.Png); Console.WriteLine("Saved: MicroPdf417Rows6.png"); ```'
  - name: 4.3 Four Columns × Eight Rows (Fully Specified)
    text: '```csharp // Explicitly set both columns and rows generator.Parameters.Barcode.Pdf417.Columns
      = 4; generator.Parameters.Barcode.Pdf417.Rows = 8; generator.Save("MicroPdf417Rows8Columns4.png",
      BarCodeImageFormat.Png); Console.WriteLine("Saved: MicroPdf417Rows8Columns4.png");
      ```'
  - name: Expected Output
    text: 'Running the program produces three PNG files:'
  type: HowTo
- questions:
  - answer: Call `Directory.CreateDirectory(path)` before the first `Save` to avoid
      a `DirectoryNotFoundException`.
    question: What if the output folder doesn’t exist?
  - answer: Absolutely. Replace `BarCodeImageFormat.Png` with `Jpeg`, `Bmp`, or `Gif`
      as needed.
    question: Can I change the image format?
  - answer: MicroPdf417 can encode up to 1 KB of data, but practical limits depend
      on the chosen rows/columns. If you hit an error, increase rows or columns.
    question: Is there a limit to the text length?
  - answer: Use Aspose.Pdf to insert the generated PNG, or switch to `BarCodeImageFormat.Pdf`
      for a direct PDF output.
    question: How do I embed the barcode in a PDF?
  type: FAQPage
tags:
- barcode
- C#
- Aspose
title: Générer un code‑barres Micro PDF417 en C# – Guide complet
url: /fr/net/compact-pdf417-encoding/generate-micro-pdf417-barcode-in-c-complete-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Générer un code‑barres Micro PDF417 en C# – Guide complet

Vous êtes‑vous déjà demandé comment **générer un code‑barres micro pdf417** directement depuis votre application C# ? Vous n'êtes pas le seul. Que vous étiquetiez des stocks, encodiez des URL courtes ou construisiez une solution de numérisation personnalisée, maîtriser ce petit mais puissant code 2‑D peut vous éviter bien des tracas.

Dans ce tutoriel, nous parcourrons un exemple réel en utilisant **Aspose.BarCode for .NET**, vous montrant comment ajuster les colonnes, les lignes et la taille du module, puis enregistrer le résultat dans un fichier PNG. À la fin, vous disposerez d’une application console prête à l’emploi qui génère trois images de code‑barres différentes — aucun mystère laissé derrière.

## Ce dont vous avez besoin

- .NET 6 ou version ultérieure (le code fonctionne également sur .NET Framework 4.7+)
- Visual Studio 2022 (ou tout IDE C# de votre choix)
- Le package NuGet **Aspose.BarCode** (`Aspose.BarCode`)
- Un dossier accessible en écriture sur le disque pour les PNG de sortie

Si vous avez déjà tout cela, super — plongeons‑y.

## Étape 1 : Configurer le projet et installer Aspose.BarCode

Tout d'abord, créez un nouveau projet console :

```bash
dotnet new console -n MicroPdf417Demo
cd MicroPdf417Demo
dotnet add package Aspose.BarCode
```

> **Astuce :** Exécutez `dotnet restore` après avoir ajouté le package pour vous assurer que toutes les dépendances sont résolues.

Ouvrez maintenant `Program.cs`. Nous commencerons par importer les espaces de noms nécessaires :

```csharp
using System;
using Aspose.BarCode.Generation;
```

Ces deux instructions `using` nous donnent accès à `BarcodeGenerator`, `EncodeTypes` et à l’énumération du format d’image dont nous aurons besoin plus tard.

## Étape 2 : Initialiser le générateur MicroPdf417

Le cœur de l’opération est l’objet `BarcodeGenerator`. Nous lui fournissons le type d’encodage **MicroPdf417** et le texte que nous voulons encoder — dans notre cas le mot « ASPOSE ».

```csharp
// Initialise generator with MicroPdf417 and sample text
var generator = new BarcodeGenerator(EncodeTypes.MicroPdf417, "ASPOSE");
```

Pourquoi `MicroPdf417` ? Comparé au PDF417 pleine taille, la version micro emporte plus de données dans un format plus réduit, parfait pour les étiquettes à espace limité.

## Étape 3 : Ajuster la taille du module (X‑Dimension)

La taille du module détermine le nombre de pixels que chaque petit carré du code‑barres occupe. Une valeur de **2 pixels** produit une image nette et lisible sans gonfler la taille du fichier.

```csharp
// Set X‑dimension to 2 pixels per module
generator.Parameters.Barcode.XDimension.Pixels = 2;
```

> **Remarque :** Si vous avez besoin d’un code‑barres plus grand pour une numérisation à distance, augmentez ce nombre à 3 ou 4.

## Étape 4 : Générer des codes‑barres avec différentes configurations de colonnes/lignes

### 4.1 Deux colonnes, lignes calculées automatiquement

```csharp
// Force 2 columns, let rows auto‑adjust
generator.Parameters.Barcode.Pdf417.Columns = 2;
generator.Parameters.Barcode.Pdf417.Rows = 0; // 0 = auto
generator.Save("MicroPdf417Columns2.png", BarCodeImageFormat.Png);
Console.WriteLine("Saved: MicroPdf417Columns2.png");
```

### 4.2 Six lignes, colonnes calculées automatiquement

```csharp
// Switch to 6 rows, columns auto‑determined
generator.Parameters.Barcode.Pdf417.Columns = 0; // auto columns
generator.Parameters.Barcode.Pdf417.Rows = 6;
generator.Save("MicroPdf417Rows6.png", BarCodeImageFormat.Png);
Console.WriteLine("Saved: MicroPdf417Rows6.png");
```

### 4.3 Quatre colonnes × huit lignes (spécifiées entièrement)

```csharp
// Explicitly set both columns and rows
generator.Parameters.Barcode.Pdf417.Columns = 4;
generator.Parameters.Barcode.Pdf417.Rows = 8;
generator.Save("MicroPdf417Rows8Columns4.png", BarCodeImageFormat.Png);
Console.WriteLine("Saved: MicroPdf417Rows8Columns4.png");
```

Chaque appel `Save` écrit un fichier PNG dans le répertoire de travail du projet. N’hésitez pas à modifier le chemin (`"YOUR_DIRECTORY/..."`) vers quelque chose comme `Path.Combine(Environment.CurrentDirectory, "output")` si vous préférez un dossier dédié.

## Étape 5 : Exemple complet fonctionnel

En rassemblant le tout, voici le programme complet, prêt à copier‑coller :

```csharp
using System;
using Aspose.BarCode.Generation;

namespace MicroPdf417Demo
{
    class Program
    {
        static void Main()
        {
            // 1️⃣ Initialise generator with MicroPdf417 and sample text
            var generator = new BarcodeGenerator(EncodeTypes.MicroPdf417, "ASPOSE");

            // 2️⃣ Set module size – 2 pixels per module for a sharp image
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // 3️⃣ Create three variants with different column/row settings

            // Variant A – 2 columns, rows auto‑adjust
            generator.Parameters.Barcode.Pdf417.Columns = 2;
            generator.Parameters.Barcode.Pdf417.Rows = 0; // auto rows
            generator.Save("MicroPdf417Columns2.png", BarCodeImageFormat.Png);
            Console.WriteLine("Saved: MicroPdf417Columns2.png");

            // Variant B – 6 rows, columns auto‑determine
            generator.Parameters.Barcode.Pdf417.Columns = 0; // auto columns
            generator.Parameters.Barcode.Pdf417.Rows = 6;
            generator.Save("MicroPdf417Rows6.png", BarCodeImageFormat.Png);
            Console.WriteLine("Saved: MicroPdf417Rows6.png");

            // Variant C – 4 columns × 8 rows (full control)
            generator.Parameters.Barcode.Pdf417.Columns = 4;
            generator.Parameters.Barcode.Pdf417.Rows = 8;
            generator.Save("MicroPdf417Rows8Columns4.png", BarCodeImageFormat.Png);
            Console.WriteLine("Saved: MicroPdf417Rows8Columns4.png");

            Console.WriteLine("All barcodes generated successfully!");
        }
    }
}
```

### Résultat attendu

L’exécution du programme génère trois fichiers PNG :

| Nom du fichier | Dimensions approximatives (px) | Indice visuel |
|----------------|-------------------------------|----------------|
| `MicroPdf417Columns2.png` | 180 × 120 | Code‑barres étroit et plus haut |
| `MicroPdf417Rows6.png` | 120 × 180 | Code‑barres plus large et plus court |
| `MicroPdf417Rows8Columns4.png` | 160 × 160 | Forme presque carrée, disposition équilibrée |

Ouvrez l’un d’eux dans un visualiseur d’images — vous verrez un code‑barres **Micro PDF417** net, prêt à être scanné.

## Questions fréquentes & cas particuliers

- **Et si le dossier de sortie n’existe pas ?**  
  Appelez `Directory.CreateDirectory(path)` avant le premier `Save` pour éviter une `DirectoryNotFoundException`.

- **Puis‑je changer le format de l’image ?**  
  Bien sûr. Remplacez `BarCodeImageFormat.Png` par `Jpeg`, `Bmp` ou `Gif` selon vos besoins.

- **Y a‑t‑il une limite à la longueur du texte ?**  
  MicroPdf417 peut encoder jusqu’à 1 KB de données, mais les limites pratiques dépendent des lignes/colonnes choisies. Si une erreur survient, augmentez le nombre de lignes ou de colonnes.

- **Comment intégrer le code‑barres dans un PDF ?**  
  Utilisez Aspose.Pdf pour insérer le PNG généré, ou passez à `BarCodeImageFormat.Pdf` pour une sortie PDF directe.

## Astuces pro pour la génération de codes‑barres en C#

1. **Mettez en cache le générateur** lorsque vous avez besoin de nombreux codes‑barres avec les mêmes paramètres — seul le texte doit changer, ce qui économise des cycles CPU.  
2. **Ajustez finement la correction d’erreurs** via `generator.Parameters.Barcode.Pdf417.ErrorLevel` si votre environnement de numérisation est bruyant.  
3. **Testez tôt avec de vrais scanners**. Certains appareils portables ont du mal avec des micro‑codes‑barres très denses ; ajuster `XDimension` peut faire une grande différence.

## Conclusion

Vous savez maintenant comment **générer un code‑barres micro pdf417** en utilisant **Aspose.BarCode for .NET**, manipuler les **colonnes MicroPdf417** et les **lignes MicroPdf417**, et enregistrer le résultat sous forme de fichiers PNG — le tout depuis une seule application console C# bien organisée. Expérimentez avec différentes tailles de module, niveaux d’erreur, ou même une sortie couleur pour répondre aux besoins de votre projet.

Ensuite, vous pourriez explorer la **génération de codes‑barres en C#** pour d’autres symbologies comme QR, Code128 ou DataMatrix, ou intégrer les images directement dans des PDF avec Aspose.Pdf. Le ciel est la limite une fois que vous maîtrisez les bases.

Bonne programmation, et que vos scans soient toujours sans erreur !

## Que devriez‑vous apprendre ensuite ?

Les tutoriels suivants couvrent des sujets étroitement liés qui s’appuient sur les techniques démontrées dans ce guide. Chaque ressource comprend des exemples de code complets et fonctionnels avec des explications étape par étape pour vous aider à maîtriser des fonctionnalités API supplémentaires et explorer des approches d’implémentation alternatives dans vos propres projets.

- [Comment créer un code‑barres – PDF417 compact avec Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [Créer une image de code‑barres DotCode – lignes & colonnes (Aspose.BarCode)](/barcode/english/net/dotcode-barcode-configuration/dotcode-rows-columns-configuration/)
- [Générer un code‑barres DataMatrix – Guide Pro avec Aspose.BarCode](/barcode/english/net/datamatrix-barcode-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}