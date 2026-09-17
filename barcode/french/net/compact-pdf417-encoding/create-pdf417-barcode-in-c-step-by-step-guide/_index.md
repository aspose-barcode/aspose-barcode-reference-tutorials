---
category: general
date: 2026-08-03
description: Créez rapidement un code‑barres PDF417 en C#. Apprenez comment générer
  un code‑barres PDF417 et comment enregistrer l’image du code‑barres au format PNG
  avec Aspose.Barcode.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create pdf417 barcode
- how to generate pdf417 barcode
- how to save barcode image
language: fr
lastmod: 2026-08-03
og_description: Créez un code‑barres PDF417 en C# avec Aspose.Barcode. Suivez ce guide
  pour générer un code‑barres PDF417 et apprendre à enregistrer l’image du code‑barres
  efficacement.
og_image_alt: Screenshot of a generated compact PDF417 barcode saved as PNG
og_title: Créer un code-barres PDF417 en C# – tutoriel complet de codage
schemas:
- author: Aspose
  dateModified: '2026-08-03'
  description: Create PDF417 barcode in C# quickly. Learn how to generate PDF417 barcode
    and how to save barcode image as PNG with Aspose.Barcode.
  headline: Create PDF417 barcode in C# – step‑by‑step guide
  type: TechArticle
- description: Create PDF417 barcode in C# quickly. Learn how to generate PDF417 barcode
    and how to save barcode image as PNG with Aspose.Barcode.
  name: Create PDF417 barcode in C# – step‑by‑step guide
  steps:
  - name: Why this matters
    text: '* **EncodeTypes.Pdf417** tells the library to use the PDF417 standard,
      which supports large data payloads and error correction. * Providing Unicode
      characters proves the generator handles non‑ASCII input without extra configuration.'
  - name: Practical tip
    text: If you need a taller barcode for limited horizontal space, increase `Columns`.
      Setting `Truncate` to `true` reduces the overall height by removing quiet zones,
      which is ideal for mobile screens.
  - name: Expected result
    text: Running the program creates `CompactPdf417.png` in the project folder. Opening
      the file shows a compact PDF417 barcode that encodes the string *Åspóse.Barcóde©*.
      The image can be embedded in HTML, PDF reports, or printed on labels.
  - name: Verifying the output
    text: 'After the program finishes, you can verify the file exists with a quick
      command:'
  type: HowTo
tags:
- barcode
- C#
- PDF417
- image generation
title: Créer un code‑barres PDF417 en C# – guide étape par étape
url: /fr/net/compact-pdf417-encoding/create-pdf417-barcode-in-c-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Créer un code-barres PDF417 en C# – guide étape par étape

Si vous devez **créer un code-barres PDF417** dans une application .NET, ce guide vous montre exactement comment générer un code-barres PDF417 et comment enregistrer l'image du code-barres. Vous obtiendrez un fichier PNG qui peut être utilisé dans des rapports, des tickets ou des applications de numérisation mobile.

Le tutoriel couvre tout, de la configuration du projet au fichier PNG final. Aucune documentation externe n'est requise ; il suffit de suivre les étapes et d'exécuter le code.

## Ce dont vous avez besoin

* .NET 6.0 SDK ou version ultérieure (le code fonctionne également avec .NET Framework 4.7+)
* Visual Studio 2022 ou tout IDE supportant C#
* Accès à Internet pour installer le package NuGet **Aspose.Barcode for .NET**

Ces prérequis garantissent que le code se compile sans configuration supplémentaire.

## Créer un code-barres PDF417 – configuration du projet

1. Ouvrez une invite de commande et créez un nouveau projet console :

   ```bash
   dotnet new console -n Pdf417Demo
   cd Pdf417Demo
   ```

2. Ajoutez la bibliothèque Aspose.Barcode :

   ```bash
   dotnet add package Aspose.Barcode
   ```

3. Ouvrez le fichier `Program.cs` généré. Les instructions `using` en haut vous donnent accès aux classes de code-barres :

   ```csharp
   using System;
   using Aspose.Barcode.Generation;
   using Aspose.Barcode;
   ```

Le projet est maintenant prêt à **créer un code-barres PDF417**.

## Comment générer un code-barres PDF417 avec Aspose.Barcode

Le cœur de la création du code-barres se trouve dans la classe `BarcodeGenerator`. Vous spécifiez la symbologie (`EncodeTypes.Pdf417`) et les données que vous souhaitez encoder.

```csharp
// Step 1: Initialise the generator with PDF417 symbology and sample text.
// The text includes Unicode characters to demonstrate full‑range support.
BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Åspóse.Barcóde©");
```

### Pourquoi c'est important

* **EncodeTypes.Pdf417** indique à la bibliothèque d'utiliser la norme PDF417, qui prend en charge de grandes charges de données et la correction d'erreurs.
* Fournir des caractères Unicode prouve que le générateur gère les entrées non‑ASCII sans configuration supplémentaire.

## Comment configurer l'apparence du code-barres

Vous pouvez contrôler la taille de chaque module, le nombre de colonnes, et si le code-barres utilise le mode compact (truncaté). Ces paramètres affectent à la fois la lisibilité et la taille du fichier.

```csharp
// Step 2: Set the module (X) dimension – each barcode element will be 2 pixels wide.
generator.Parameters.Barcode.XDimension.Pixels = 2;

// Step 3: Configure PDF417‑specific options.
generator.Parameters.Barcode.Pdf417.Columns = 3;      // Number of columns (affects height)
generator.Parameters.Barcode.Pdf417.Truncate = true; // Enable compact mode
```

### Astuce pratique

Si vous avez besoin d'un code-barres plus haut pour un espace horizontal limité, augmentez `Columns`. Mettre `Truncate` à `true` réduit la hauteur globale en supprimant les zones silencieuses, ce qui est idéal pour les écrans mobiles.

## Comment enregistrer l'image du code-barres au format PNG

Après avoir configuré le générateur, appelez `Save` avec un chemin de fichier et le format d'image souhaité. La méthode écrit l'image directement sur le disque.

```csharp
// Step 4: Save the generated barcode as a PNG image.
string outputPath = @"./CompactPdf417.png";
generator.Save(outputPath, BarCodeImageFormat.Png);
Console.WriteLine($"Barcode saved to {outputPath}");
```

### Résultat attendu

L'exécution du programme crée `CompactPdf417.png` dans le dossier du projet. L'ouverture du fichier montre un code-barres PDF417 compact qui encode la chaîne *Åspóse.Barcóde©*. L'image peut être intégrée dans du HTML, des rapports PDF, ou imprimée sur des étiquettes.

## Code source complet

Ci-dessous se trouve le programme complet et exécutable. Copiez-le dans `Program.cs` et exécutez `dotnet run`.

```csharp
using System;
using Aspose.Barcode.Generation;
using Aspose.Barcode;

namespace Pdf417Demo
{
    class Program
    {
        static void Main()
        {
            // Initialise the generator with PDF417 symbology and sample text.
            BarcodeGenerator generator = new BarcodeGenerator(
                EncodeTypes.Pdf417,
                "Åspóse.Barcóde©");

            // Set the module width to 2 pixels.
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // Configure PDF417‑specific options.
            generator.Parameters.Barcode.Pdf417.Columns = 3;
            generator.Parameters.Barcode.Pdf417.Truncate = true;

            // Define the output file path.
            string outputPath = @"./CompactPdf417.png";

            // Save the barcode as a PNG image.
            generator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"Barcode saved to {outputPath}");
        }
    }
}
```

### Vérification de la sortie

Après la fin du programme, vous pouvez vérifier que le fichier existe avec une commande rapide :

```bash
dotnet run && ls -l CompactPdf417.png
```

Si le fichier apparaît, le processus de **création d'un code-barres PDF417** a réussi.

## Variations courantes et cas limites

| Situation | Ajustement |
|-----------|------------|
| **Chaîne de données plus longue** | Augmentez `Columns` ou définissez `Rows` pour accueillir plus de codewords. |
| **Format d'image différent** | Remplacez `BarCodeImageFormat.Png` par `Jpeg`, `Bmp` ou `Gif`. |
| **Résolution plus élevée** | Définissez `generator.Parameters.ImageResolution` avant `Save`. |
| **Couleur de fond** | Utilisez `generator.Parameters.Barcode.ImageBackgroundColor = Color.White;` |
| **Gestion des exceptions** | Enveloppez `generator.Save` dans un bloc `try/catch` pour capturer les erreurs d'E/S. |

## Conclusion

Vous savez maintenant comment **créer un code-barres PDF417** en C# avec Aspose.Barcode, configurer son apparence, et **enregistrer l'image du code-barres** au format PNG. L'exemple complet montre chaque étape requise, de la configuration du projet à la vérification, afin que vous puissiez intégrer la génération de code-barres dans toute solution .NET.

Ensuite, envisagez d'explorer des sujets connexes tels que **comment générer des QR codes**, **intégrer des codes-barres dans des documents PDF**, ou **personnaliser les couleurs des codes-barres**. Chacun de ces sujets s'appuie sur la même API de générateur, vous permettant d'étendre les capacités de numérisation de votre application avec un effort minimal. Bon codage !

## Que devriez‑vous apprendre ensuite ?

Les tutoriels suivants couvrent des sujets étroitement liés qui s'appuient sur les techniques démontrées dans ce guide. Chaque ressource inclut des exemples de code complets et fonctionnels avec des explications étape par étape pour vous aider à maîtriser des fonctionnalités supplémentaires de l'API et explorer des approches d'implémentation alternatives dans vos propres projets.

- [Comment créer un code-barres – PDF417 compact avec Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [Comment générer des codes-barres DataMatrix (ECC 200) avec Aspose.BarCode pour .NET](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-ecc-200-configuration/)
- [Comment générer un code-barres Aztec avec un ratio d'aspect personnalisé en utilisant Aspose.BarCode pour .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}