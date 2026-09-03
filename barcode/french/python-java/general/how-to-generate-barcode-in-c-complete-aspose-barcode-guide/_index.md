---
category: general
date: 2026-07-21
description: Comment générer rapidement un code‑barres avec Aspose.BarCode pour C#.
  Apprenez à créer un code‑barres avec Aspose, à ajuster les rapports d’aspect et
  à enregistrer des PNG en quelques minutes.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to generate barcode
- create barcode with aspose
- Aspose.BarCode example
- DataBar stacked omnidirectional
- barcode aspect ratio C#
language: fr
lastmod: 2026-07-21
og_description: Comment générer un code‑barres avec Aspose.BarCode pour C#. Ce guide
  étape par étape vous montre comment créer un code‑barres avec Aspose, ajuster les
  paramètres et exporter les images.
og_image_alt: Screenshot of generated DataBar barcode showing different aspect ratios
og_title: Comment générer un code-barres en C# – Tutoriel rapide Aspose.BarCode
schemas:
- author: Aspose
  dateModified: '2026-07-21'
  description: How to generate barcode quickly using Aspose.BarCode for C#. Learn
    to create barcode with Aspose, adjust aspect ratios, and save PNGs in minutes.
  headline: How to Generate Barcode in C# – Complete Aspose.BarCode Guide
  type: TechArticle
tags:
- barcode
- Aspose
- C#
- DataBar
title: Comment générer un code‑barres en C# – Guide complet d’Aspose.BarCode
url: /fr/python-java/general/how-to-generate-barcode-in-c-complete-aspose-barcode-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Comment générer un code-barres en C# – Guide complet Aspose.BarCode

Vous vous êtes déjà demandé **comment générer un code-barres** dans une application .NET sans vous battre avec du code d'image bas‑niveau ? Vous n'êtes pas le seul. Dans de nombreux projets d'entreprise, nous devons **créer des codes-barres avec Aspose** pour les factures, les étiquettes d'expédition ou le suivi des stocks, et la bibliothèque rend cela étonnamment simple.

Dans ce tutoriel, nous parcourrons un exemple réel qui crée un code-barres DataBar Stacked Omnidirectional, ajuste son ratio d’aspect et enregistre deux fichiers PNG. À la fin, vous disposerez d’un programme console prêt à l’exécution et d’une compréhension claire des propriétés clés que vous pouvez contrôler.

## Ce que vous apprendrez

- Configurer Aspose.BarCode dans un projet C# (NuGet, bases de licence)
- Initialiser un générateur **DataBar stacked omnidirectional**
- Ajuster la X‑dimension (taille en pixels) et le ratio d’aspect
- Enregistrer le code-barres en images PNG
- Étendre l’exemple à d’autres types de codes-barres ou formats de sortie

Aucune expérience préalable avec Aspose n’est requise — il vous suffit d’un SDK .NET 6 (ou ultérieur) fonctionnel et d’un IDE préféré.

## Prérequis

| Exigence | Raison |
|----------|--------|
| .NET 6 SDK ou plus récent | Fonctionnalités modernes du langage et création de projet simplifiée |
| Visual Studio 2022 (ou VS Code) | IDE pour la construction et le débogage |
| Aspose.BarCode for .NET package NuGet | Bibliothèque principale qui effectue le travail lourd |
| Une licence Aspose valide (ou d’évaluation) | Supprime le filigrane d’évaluation et débloque toutes les fonctionnalités |

Si vous n’avez pas encore installé le package NuGet, exécutez :

```bash
dotnet add package Aspose.BarCode
```

Maintenant que tout est prêt, plongeons dans le code.

## Étape 1 : créer un nouveau projet console

Tout d'abord, créez une nouvelle application console. Ouvrez un terminal et tapez :

```bash
dotnet new console -n BarcodeDemo
cd BarcodeDemo
```

## Étape 2 : initialiser le BarcodeGenerator

Le cœur du processus est la classe `BarcodeGenerator`. Nous demanderons une symbologie **DataBar stacked omnidirectional** et lui fournirons une chaîne d’exemple GS1‑128.

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;
using System;

class Program
{
    static void Main()
    {
        // Step 2.1: Choose the barcode type and data
        var generator = new BarcodeGenerator(
            EncodeTypes.DatabarStackedOmniDirectional,
            "(01)12345678901231"); // GS1-128 example

        // Step 2.2: Set the X‑dimension (pixel size) – controls overall size
        generator.Parameters.Barcode.XDimension.Pixels = 2;

        // Continue with aspect ratio adjustments...
        GenerateBarcodes(generator);
    }

    static void GenerateBarcodes(BarcodeGenerator generator)
    {
        // Placeholder for the rest of the steps
    }
}
```

**Pourquoi c’est important :** `EncodeTypes.DatabarStackedOmniDirectional` produit un code-barres compact et à haute densité, idéal pour les petites étiquettes. La chaîne de données suit l’identifiant d’application GS1 `(01)` pour une valeur GTIN‑14, que de nombreux systèmes de chaîne d'approvisionnement attendent.

## Étape 3 : ajuster le ratio d’aspect et enregistrer les images

Aspose.BarCode vous permet d’ajuster le **ratio d’aspect** des symboles DataBar via `Parameters.Barcode.DataBar.AspectRatio`. Modifier cette valeur change la proportion visuelle largeur‑hauteur, ce qui peut être crucial pour adapter le code-barres à une étiquette de taille fixe.

```csharp
static void GenerateBarcodes(BarcodeGenerator generator)
{
    string outputPath = "GeneratedBarcodes/"; // Ensure this folder exists
    System.IO.Directory.CreateDirectory(outputPath);

    // ---------- First image: Aspect Ratio 15 ----------
    generator.Parameters.Barcode.DataBar.AspectRatio = 15;
    string file15 = $"{outputPath}DatabarAspectRatio15.png";
    generator.Save(file15, BarCodeImageFormat.Png);
    Console.WriteLine($"Saved barcode with aspect ratio 15 to {file15}");

    // ---------- Second image: Aspect Ratio 30 ----------
    generator.Parameters.Barcode.DataBar.AspectRatio = 30;
    string file30 = $"{outputPath}DatabarAspectRatio30.png";
    generator.Save(file30, BarCodeImageFormat.Png);
    Console.WriteLine($"Saved barcode with aspect ratio 30 to {file30}");
}
```

**Explication de chaque ligne**

- `outputPath` pointe vers un dossier où les fichiers PNG seront enregistrés. `Directory.CreateDirectory` garantit que le dossier existe même sur une machine neuve.
- `AspectRatio = 15` produit un code-barres relativement haut ; `AspectRatio = 30` l’étire horizontalement.
- `generator.Save(...)` écrit l’image sur le disque. L’énumération `BarCodeImageFormat.Png` assure une qualité sans perte.
- `Console.WriteLine` vous donne un retour immédiat lorsque vous exécutez le programme.

### Sortie attendue

Lorsque vous exécutez `dotnet run`, vous devriez voir quelque chose comme :

```
Saved barcode with aspect ratio 15 to GeneratedBarcodes/DatabarAspectRatio15.png
Saved barcode with aspect ratio 30 to GeneratedBarcodes/DatabarAspectRatio30.png
```

Ouvrez les deux fichiers PNG côte à côte ; vous remarquerez que la deuxième image est nettement plus large tout en conservant la même hauteur. Les deux images sont lisibles avec des lecteurs de codes-barres standards.

## Étape 4 : exécuter l’exemple complet

Voici le **code complet et exécutable** en un seul bloc pour faciliter le copier‑coller :

```csharp
// Program.cs
using Aspose.BarCode.Generation;
using Aspose.BarCode;
using System;
using System.IO;

class Program
{
    static void Main()
    {
        // Initialise generator with DataBar stacked omnidirectional symbology
        var generator = new BarcodeGenerator(
            EncodeTypes.DatabarStackedOmniDirectional,
            "(01)12345678901231");

        // Set pixel size of the X‑dimension (controls overall size)
        generator.Parameters.Barcode.XDimension.Pixels = 2;

        // Generate two barcodes with different aspect ratios
        GenerateBarcodes(generator);
    }

    static void GenerateBarcodes(BarcodeGenerator generator)
    {
        string outputPath = "GeneratedBarcodes/";
        Directory.CreateDirectory(outputPath);

        // Aspect Ratio 15
        generator.Parameters.Barcode.DataBar.AspectRatio = 15;
        string file15 = Path.Combine(outputPath, "DatabarAspectRatio15.png");
        generator.Save(file15, BarCodeImageFormat.Png);
        Console.WriteLine($"Saved barcode with aspect ratio 15 to {file15}");

        // Aspect Ratio 30
        generator.Parameters.Barcode.DataBar.AspectRatio = 30;
        string file30 = Path.Combine(outputPath, "DatabarAspectRatio30.png");
        generator.Save(file30, BarCodeImageFormat.Png);
        Console.WriteLine($"Saved barcode with aspect ratio 30 to {file30}");
    }
}
```

Compilez et exécutez :

```bash
dotnet run
```

Voilà—deux PNG de codes-barres parfaitement rendus apparaissent dans `GeneratedBarcodes/`.

## Étape 5 : étendre l’exemple (optionnel)

Maintenant que vous **savez comment générer un code-barres** avec Aspose, vous pourriez vous demander : *Quoi d’autre puis‑je ajuster ?* Voici quelques idées rapides :

| Propriété | Ce que cela fait | Cas d’utilisation typique |
|-----------|------------------|----------------------------|
| `generator.Parameters.Barcode.CodeTextParameters.Font.Size` | Modifie la taille du texte lisible par l'homme | Police plus grande pour les scanners portatifs |
| `generator.Parameters.Barcode.ImageFormat` | Format de sortie global (PNG, JPEG, BMP, etc.) | JPEG pour une taille adaptée au web |
| `generator.Parameters.Barcode.Color` | Définit la couleur du premier plan | Catégories codées par couleur |
| `generator.Save(..., BarCodeImageFormat.Svg)` | Sortie vectorielle pour un redimensionnement infini | PDF prêts à l’impression |

Pour expérimenter, ajoutez simplement les lignes correspondantes avant chaque appel à `Save`.

## Pièges courants & astuces pro

- **Placement de la licence :** Si vous utilisez une licence payante, appelez `License license = new License(); license.SetLicense("Aspose.BarCode.lic");` avant de créer le générateur. Oublier cela laisse un filigrane sur l’image.
- **Chaîne de données invalide :** Les symbologies DataBar attendent des données GS1 numériques. Fournir des caractères alphabétiques déclenchera une `ArgumentException`.
- **Sécurité des threads :** Les instances de `BarcodeGenerator` ne sont **pas** thread‑safe. Créez une nouvelle instance par thread si vous générez des codes-barres en parallèle.
- **Taille de l’image vs capacité du scanner :** Un `XDimension.Pixels` très élevé peut produire une image massive que certains scanners ont du mal à lire. Testez avec votre matériel cible.

## Conclusion

Nous venons de couvrir **comment générer un code-barres** en C# avec Aspose.BarCode, depuis la configuration du projet jusqu’à l’enregistrement de deux images avec des ratios d’aspect différents. Les étapes clés—initialiser le générateur, configurer la X‑dimension et le ratio d’aspect, et appeler `Save`—forment un modèle réutilisable que vous pouvez appliquer à tout type de code-barres pris en charge par Aspose.

Vous pouvez maintenant **créer des codes-barres avec Aspose** pour les factures, les étiquettes d’expédition ou les tags d’inventaire, et vous disposez d’une base solide pour explorer des fonctionnalités plus avancées comme la couleur, les polices personnalisées ou la sortie SVG. N’hésitez pas à ajuster le code, à expérimenter d’autres `EncodeTypes`, et à intégrer le générateur dans vos services existants.

Des questions ou vous souhaitez voir un style de code-barres spécifique ? Laissez un commentaire ci‑dessous, et bon codage !

## Que devriez‑vous apprendre ensuite ?

Les tutoriels suivants couvrent des sujets étroitement liés qui s’appuient sur les techniques démontrées dans ce guide. Chaque ressource comprend des exemples de code complets et fonctionnels avec des explications étape par étape pour vous aider à maîtriser des fonctionnalités API supplémentaires et explorer des approches d’implémentation alternatives dans vos propres projets.

- [Comment générer un code-barres Aztec avec un ratio d’aspect personnalisé en utilisant Aspose.BarCode pour .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)
- [Comment personnaliser le code-barres - Ratio d’aspect Codablock F avec Aspose.BarCode pour .NET](/barcode/english/net/codablock-f-encoding/codablock-f-aspect-ratio-customization/)
- [Comment générer des codes-barres DataMatrix (ECC 200) avec Aspose.BarCode pour .NET](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-ecc-200-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}