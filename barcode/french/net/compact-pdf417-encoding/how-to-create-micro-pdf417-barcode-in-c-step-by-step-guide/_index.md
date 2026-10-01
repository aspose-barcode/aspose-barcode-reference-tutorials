---
category: general
date: 2026-08-22
description: Apprenez à créer un code‑barres micro PDF417 en C# et à générer une image
  PNG du code‑barres. Inclut la définition des dimensions du code‑barres et l’enregistrement
  du fichier.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create micro pdf417 barcode
- how to generate barcode png
- create barcode image c#
- how to set barcode dimensions
language: fr
lastmod: 2026-08-22
og_description: Créez un code‑barres micro PDF417 en C# et exportez‑le au format PNG.
  Suivez ce guide pour définir les dimensions du code‑barres et générer rapidement
  une image de code‑barres.
og_image_alt: Screenshot of a micro PDF417 barcode generated with C# code
og_title: Créer un code‑barres micro PDF417 en C# – tutoriel complet de codage
schemas:
- author: Aspose
  dateModified: '2026-08-22'
  description: Learn how to create micro PDF417 barcode in C# and generate a barcode
    PNG image. Includes setting barcode dimensions and saving the file.
  headline: How to create micro PDF417 barcode in C# – step‑by‑step guide
  type: TechArticle
- description: Learn how to create micro PDF417 barcode in C# and generate a barcode
    PNG image. Includes setting barcode dimensions and saving the file.
  name: How to create micro PDF417 barcode in C# – step‑by‑step guide
  steps:
  - name: 'Build the project: `dotnet build`.'
    text: 'Build the project: `dotnet build`.'
  - name: 'Execute: `dotnet run`.'
    text: 'Execute: `dotnet run`.'
  - name: Open `MicroPdf417.png` on your desktop and scan it with a mobile barcode
      scanner app.
    text: Open `MicroPdf417.png` on your desktop and scan it with a mobile barcode
      scanner app.
  type: HowTo
tags:
- barcode
- C#
- MicroPdf417
- image generation
title: Comment créer un code‑barres micro PDF417 en C# – guide étape par étape
url: /fr/net/compact-pdf417-encoding/how-to-create-micro-pdf417-barcode-in-c-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Comment créer un code-barres micro PDF417 en C# – guide étape par étape

Si vous devez **créer un code-barres micro PDF417** pour un système de billetterie, une étiquette d'inventaire ou une numérisation mobile, ce tutoriel vous montre exactement comment faire. Vous verrez le programme complet en C# qui génère un PNG de code-barres, apprendrez à définir les dimensions du code-barres et comprendrez chaque option de configuration.

À la fin de ce guide, vous serez capable de générer une image de code-barres haute résolution, de personnaliser la X‑dimension, de choisir le nombre de colonnes et d’enregistrer le résultat sous forme de fichier PNG — le tout en quelques lignes de code.

## Ce dont vous avez besoin

- .NET 6.0 SDK ou version ultérieure (le code fonctionne avec .NET Core et .NET Framework)
- Visual Studio 2022 ou tout IDE compatible C#
- Le package NuGet **Aspose.BarCode for .NET** (ou toute bibliothèque qui prend en charge `EncodeTypes.MicroPdf417`)
- Une connaissance de base de la syntaxe C#

> **Astuce :** L’édition communautaire gratuite d’Aspose.BarCode suffit pour le développement et les tests. Pour la production, obtenez une licence afin de supprimer les filigranes d’évaluation.

## Étape 1 : Installer la bibliothèque de codes-barres

Ouvrez un terminal dans le dossier de votre projet et exécutez :

```bash
dotnet add package Aspose.BarCode
```

Cela ajoute l'assembly `Aspose.BarCode`, qui fournit la classe `BarcodeGenerator` utilisée pour **créer des applications d’image de code-barres C#**.

## Étape 2 : Initialiser le générateur – créer un code-barres micro PDF417

La première ligne opérationnelle crée une instance de `BarcodeGenerator` configurée pour la symbologie Micro PDF417 et fournit les données que vous souhaitez encoder.

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Program
{
    static void Main()
    {
        // Step 2: Initialize a Micro PDF417 barcode generator with the data to encode
        BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.MicroPdf417, "Sample text");
```

*Pourquoi c’est important* : L’énumération `EncodeTypes.MicroPdf417` indique à la bibliothèque d’utiliser la version compacte du PDF417, idéale pour les petites étiquettes et les écrans mobiles.

## Étape 3 : Comment définir les dimensions du code-barres en C#

Le réglage fin de la largeur du module (X‑dimension) contrôle la densité visuelle du code-barres. Une valeur plus petite produit une image plus nette, tandis qu’une valeur plus grande rend le code-barres plus facile à scanner à distance.

```csharp
        // Step 3: Set the X‑dimension (module width) to 2 pixels for finer resolution
        generator.Parameters.Barcode.XDimension.Pixels = 2;
```

> **Pourquoi vous devez définir les dimensions** : Sans ajuster la X‑dimension, la valeur par défaut peut produire un code-barres flou lorsqu’il est rendu à haute résolution DPI. La régler à 2 pixels constitue un bon compromis pour la plupart des scans basés sur écran.

## Étape 4 : Choisir le nombre de colonnes – contrôler la largeur du code-barres

Micro PDF417 autorise entre 1 et 4 colonnes. Plus de colonnes compressent les données horizontalement, réduisant la largeur globale de l’image.

```csharp
        // Step 4: Define the number of columns (allowed values: 1‑4)
        generator.Parameters.Barcode.Pdf417.Columns = 4;
```

*Cas limite* : Si vous demandez 5 colonnes, la bibliothèque lève une `ArgumentOutOfRangeException`. Restez toujours dans la plage documentée.

## Étape 5 : Comment générer un PNG de code-barres – enregistrer l’image

Vous pouvez maintenant exporter le code-barres généré vers un fichier PNG. Le PNG conserve une qualité sans perte, ce qui est essentiel pour un scan fiable.

```csharp
        // Step 5: Save the generated barcode as a PNG image
        string outputPath = Path.Combine(
            Environment.GetFolderPath(Environment.SpecialFolder.Desktop),
            "MicroPdf417.png");
        generator.Save(outputPath, BarCodeImageFormat.Png);
        Console.WriteLine($"Barcode saved to {outputPath}");
    }
}
```

Lorsque vous exécutez le programme, vous verrez un message console confirmant l’emplacement du fichier. Le `MicroPdf417.png` résultant ressemble à ceci :

![Capture d’écran montrant un code-barres micro PDF417 généré avec C#](micro-pdf417-example.png "Code-barres micro PDF417 généré")

*Texte alternatif de l’image* : **code-barres micro PDF417 généré en C#** – montre le résultat final après l’application des dimensions et des paramètres de colonnes.

## Étape 6 : Exécuter et vérifier la sortie

1. Construisez le projet : `dotnet build`.
2. Exécutez : `dotnet run`.
3. Ouvrez `MicroPdf417.png` sur votre bureau et scannez‑le avec une application de scanner de code‑barres mobile.

Vous devriez voir le texte **« Sample text »** décodé. Si le scanner signale une erreur, revérifiez la X‑dimension et le nombre de colonnes – des valeurs extrêmes peuvent rendre le code‑barres trop dense pour certains appareils.

## Variations courantes et dépannage

| Situation | Ajustement |
|-----------|------------|
| **Besoin d’un code‑barres plus grand pour les imprimantes basse résolution** | Augmentez `XDimension.Pixels` à 3 ou 4. |
| **Voulez un code‑barres plus haut sans changer la largeur** | Définissez `generator.Parameters.Barcode.Pdf417.Rows` (plage de lignes 3‑90). |
| **Générer plusieurs codes‑barres dans une boucle** | Réutilisez la même instance `BarcodeGenerator` et ne changez que `CodeText` avant chaque `Save`. |
| **Enregistrer en JPEG au lieu de PNG** | Remplacez `BarCodeImageFormat.Png` par `BarCodeImageFormat.Jpeg`. |
| **Exécuter sur .NET Framework 4.7** | Le même code fonctionne ; il suffit de référencer le `Aspose.BarCode.dll` approprié. |

## Liste complète du code source (exécutable)

```csharp
using System;
using System.IO;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace MicroPdf417Demo
{
    class Program
    {
        static void Main()
        {
            // Initialize a Micro PDF417 barcode generator with the data to encode
            BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.MicroPdf417, "Sample text");

            // Set the X‑dimension (module width) to 2 pixels for finer resolution
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // Define the number of columns (allowed values: 1‑4)
            generator.Parameters.Barcode.Pdf417.Columns = 4;

            // Save the generated barcode as a PNG image
            string outputPath = Path.Combine(
                Environment.GetFolderPath(Environment.SpecialFolder.Desktop),
                "MicroPdf417.png");
            generator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"Barcode saved to {outputPath}");
        }
    }
}
```

**Sortie attendue** – un fichier PNG de 200 × 100 pixels contenant un code‑barres Micro PDF417 net qui se décode en « Sample text ».

## Conclusion

Vous savez maintenant comment **créer un code‑barres micro PDF417** en C#, **définir les dimensions du code‑barres**, et **générer une image PNG de code‑barres**. L’exemple complet montre chaque étape requise — de l’installation de la bibliothèque à l’enregistrement du fichier final — afin que vous puissiez intégrer la génération de codes‑barres directement dans vos propres applications.

Ensuite, explorez des sujets connexes tels que **créer des QR codes avec Aspose.BarCode**, **personnaliser les couleurs**, ou **intégrer des codes‑barres dans des documents PDF**. Chacun de ces sujets s’appuie sur les mêmes fondamentaux `BarcodeGenerator` présentés ici.

N’hésitez pas à expérimenter avec différentes chaînes de données, nombres de colonnes et valeurs de X‑dimension pour répondre à votre environnement de scan spécifique. Bon codage !

## Que devriez‑vous apprendre ensuite ?

Les tutoriels suivants couvrent des sujets étroitement liés qui s’appuient sur les techniques démontrées dans ce guide. Chaque ressource inclut des exemples de code complets et fonctionnels avec des explications étape par étape pour vous aider à maîtriser des fonctionnalités API supplémentaires et explorer des approches d’implémentation alternatives dans vos propres projets.

- [Comment créer un code‑barres – PDF417 compact avec Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [Comment générer un code‑barres PDF417 – Encodage PDF417 compact](/barcode/english/net/compact-pdf417-encoding/)
- [Comment créer un code‑barres Aztec avec Aspose.BarCode pour .NET](/barcode/english/net/aztec-barcode-encoding/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}