---
category: general
date: 2026-11-27
description: Apprenez à générer un code‑barres PDF417 en C# avec Aspose.BarCode. Ajustez
  les dimensions, définissez le nombre de colonnes et enregistrez au format PNG en
  quelques lignes de code.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate PDF417 barcode
- Aspose.BarCode C#
- PDF417 barcode dimensions
- barcode image PNG
- BarcodeGenerator usage
language: fr
lastmod: 2026-11-27
og_description: Générez un code‑barres PDF417 en C# instantanément. Ce tutoriel montre
  comment configurer les dimensions, le nombre de colonnes et enregistrer le résultat
  en tant qu’image PNG.
og_image_alt: Screenshot showing a generated PDF417 barcode saved as a PNG file
og_title: Générer un code‑barres PDF417 en C# – guide rapide avec Aspose.BarCode
schemas:
- author: Aspose
  dateModified: '2026-11-27'
  description: Learn how to generate PDF417 barcode in C# using Aspose.BarCode. Adjust
    dimensions, set column count, and save as PNG in a few lines of code.
  headline: How to generate PDF417 barcode in C# with Aspose.BarCode
  type: TechArticle
- description: Learn how to generate PDF417 barcode in C# using Aspose.BarCode. Adjust
    dimensions, set column count, and save as PNG in a few lines of code.
  name: How to generate PDF417 barcode in C# with Aspose.BarCode
  steps:
  - name: Why each line matters
    text: '* **BarcodeGenerator** – the core class that creates a barcode image. Passing
      `EncodeTypes.Pdf417` selects the PDF417 symbology. * **XDimension.Pixels** –
      determines the smallest bar width. Smaller values shrink the image; larger values
      improve readability on low‑resolution scanners. * **Pdf417.Colu'
  - name: Changing the encoded data
    text: 'Replace the second argument of `BarcodeGenerator` with any UTF‑8 string,
      e.g.:'
  - name: Adjusting image size without losing quality
    text: 'If you need a larger image for printing, increase `XDimension.Pixels`:'
  - name: Handling very long inputs
    text: 'PDF417 can encode up to 1 850 characters. For extremely long strings, you
      may want to increase the column count:'
  - name: Saving in other formats
    text: 'Aspose.BarCode supports BMP, JPEG, TIFF, and SVG. Change the format like
      this:'
  type: HowTo
tags:
- barcode
- PDF417
- C#
- Aspose
title: Comment générer un code‑barres PDF417 en C# avec Aspose.BarCode
url: /fr/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-with-aspose-barcode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Comment générer un code-barres PDF417 en C# avec Aspose.BarCode

Si vous devez **générer un code-barres PDF417** dans une application .NET, ce guide vous montre une solution concise, de bout en bout. Vous verrez comment créer le code-barres, ajuster finement sa taille et écrire le résultat dans un fichier PNG — le tout avec la bibliothèque Aspose.BarCode.

Générer un code-barres PDF417 est courant lorsque vous devez encoder de grandes quantités de données pour la lecture sur des appareils mobiles, des cartes d'embarquement ou des étiquettes d'inventaire. À la fin de ce tutoriel, vous disposerez d'un programme console prêt à l'emploi qui produit une image PNG de haute qualité.

## Prérequis

* SDK .NET 6.0 ou version ultérieure installé  
* Une version récente de **Aspose.BarCode for .NET** (le package NuGet `Aspose.BarCode`)  
* Un IDE ou éditeur (Visual Studio, VS Code, Rider, etc.)  

Le code fonctionne sous Windows, Linux et macOS car Aspose.BarCode est multiplateforme.

## Étape 1 : Créer un nouveau projet console

Ouvrez un terminal et exécutez :

```bash
dotnet new console -n Pdf417Demo
cd Pdf417Demo
dotnet add package Aspose.BarCode
```

Cela crée un projet C# minimal nommé **Pdf417Demo** et ajoute la dépendance `Aspose.BarCode`.

## Étape 2 : Écrire le code de génération du code-barres

Ouvrez **Program.cs** et remplacez son contenu par ce qui suit :

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace Pdf417Demo
{
    class Program
    {
        static void Main(string[] args)
        {
            // 1️⃣ Create a PDF417 barcode generator with the desired text
            // EncodeTypes.Pdf417 tells Aspose.BarCode which symbology to use.
            BarcodeGenerator generator = new BarcodeGenerator(
                EncodeTypes.Pdf417, "Sample text for PDF417 barcode");

            // 2️⃣ Adjust barcode dimensions and column count
            // XDimension controls the width of a single module (pixel size).
            // Setting it to 2 pixels yields a compact yet readable barcode.
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // Columns define how many data columns the barcode will have.
            // A value of 3 works well for short strings; increase for longer data.
            generator.Parameters.Barcode.Pdf417.Columns = 3;

            // Optional: increase error correction level for more robust scanning.
            generator.Parameters.Barcode.Pdf417.ErrorCorrectionLevel = 2;

            // 3️⃣ Save the generated barcode as a PNG file
            // The output path can be absolute or relative to the project folder.
            string outputPath = "Pdf417Basic.png";
            generator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"PDF417 barcode saved to '{outputPath}'.");
        }
    }
}
```

### Pourquoi chaque ligne est importante

* **BarcodeGenerator** – la classe principale qui crée une image de code‑barres. Passer `EncodeTypes.Pdf417` sélectionne la symbologie PDF417.  
* **XDimension.Pixels** – détermine la largeur de barre la plus petite. Des valeurs plus petites réduisent l'image ; des valeurs plus grandes améliorent la lisibilité sur des lecteurs à basse résolution.  
* **Pdf417.Columns** – contrôle le nombre de colonnes de données. Plus de colonnes produisent un code‑barres plus court mais plus haut ; moins de colonnes l'élargissent.  
* **ErrorCorrectionLevel** – des niveaux plus élevés ajoutent des données redondantes, rendant le code‑barres tolérant aux dommages au prix d'une taille accrue.  
* **Save(..., BarCodeImageFormat.Png)** – écrit l'image sur le disque au format PNG, un format sans perte idéal pour un traitement ultérieur ou l'intégration dans des documents.

## Étape 3 : Compiler et exécuter le programme

Depuis le terminal, exécutez :

```bash
dotnet run
```

Vous devriez voir :

```
PDF417 barcode saved to 'Pdf417Basic.png'.
```

Un fichier nommé **Pdf417Basic.png** apparaît dans le dossier du projet. L'ouvrir montre un code‑barres PDF417 clair qui encode le texte *« Sample text for PDF417 barcode »*.

![Code‑barres PDF417 généré enregistré en fichier PNG](pdf417-barcode-example.png "Code‑barres PDF417 généré au format PNG")

*Texte alternatif de l'image : capture d'écran d'un code‑barres PDF417 généré enregistré en fichier PNG, démontrant le résultat du tutoriel de génération de code‑barres PDF417.*

## Étape 4 : Variantes courantes et cas limites

### Modifier les données encodées

Remplacez le deuxième argument de `BarcodeGenerator` par n'importe quelle chaîne UTF‑8, par exemple :

```csharp
new BarcodeGenerator(EncodeTypes.Pdf417, "https://example.com/checkout?order=12345")
```

Le générateur divise automatiquement les données entre les lignes et les colonnes.

### Ajuster la taille de l'image sans perdre en qualité

Si vous avez besoin d'une image plus grande pour l'impression, augmentez `XDimension.Pixels` :

```csharp
generator.Parameters.Barcode.XDimension.Pixels = 4; // double the module width
```

### Gérer des entrées très longues

PDF417 peut encoder jusqu'à 1 850 caractères. Pour des chaînes extrêmement longues, vous pouvez augmenter le nombre de colonnes :

```csharp
generator.Parameters.Barcode.Pdf417.Columns = 5; // more columns, less height
```

Si le contenu dépasse la capacité maximale, Aspose.BarCode lève une `ArgumentException`. Enveloppez le code de génération dans un bloc try‑catch pour afficher un message d'erreur convivial.

### Enregistrer dans d'autres formats

Aspose.BarCode prend en charge BMP, JPEG, TIFF et SVG. Changez le format ainsi :

```csharp
generator.Save("Pdf417Vector.svg", BarCodeImageFormat.Svg);
```

## Étape 5 : Vérifier le code‑barres

Vous pouvez confirmer que le code‑barres est valide en le scannant avec n'importe quelle application de lecture PDF417 (par ex., les applications de caméra de smartphone qui prennent en charge la lecture de codes‑barres). Le texte décodé doit correspondre à la chaîne que vous avez passée au générateur.

Si le scan échoue :

* Assurez‑vous que l'image n'est pas compressée (utilisez PNG ou SVG sans perte).  
* Vérifiez que `ErrorCorrectionLevel` est suffisamment élevé pour l'environnement visé.  
* Vérifiez que les dimensions du code‑barres sont appropriées à la résolution du lecteur.

## Conclusion

Vous savez maintenant comment **générer un code‑barres PDF417** en C# avec Aspose.BarCode, personnaliser ses dimensions, définir le nombre de colonnes et exporter le résultat sous forme d'image PNG. Cette approche fonctionne pour de nombreux scénarios, de la billetterie mobile à la gestion d'inventaire.

Ensuite, vous pourriez explorer :

* **Lecture** d'un code‑barres PDF417 avec `BarCodeReader`.  
* Génération d'autres symbologies telles que QR Code ou DataMatrix.  
* Intégration du PNG dans des PDF, rapports ou pages web.  

N'hésitez pas à expérimenter différents niveaux de correction d'erreur, formats d'image et charges utiles de données pour répondre aux besoins de votre projet. Bon codage !

## Que devriez‑vous apprendre ensuite ?

Les tutoriels suivants couvrent des sujets étroitement liés qui s'appuient sur les techniques démontrées dans ce guide. Chaque ressource comprend des exemples de code complets et fonctionnels avec des explications étape par étape pour vous aider à maîtriser des fonctionnalités supplémentaires de l'API et explorer des approches d'implémentation alternatives dans vos propres projets.

- [Comment générer un code‑barres PDF417 en C# avec Aspose.BarCode BarcodeGenerator](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-with-barcodegenerator/)
- [Comment générer un code‑barres PDF417 et le rendre en PNG](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-and-render-it-as-png/)
- [Comment générer un code‑barres PDF417 en C# et définir la taille du code‑barres](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-and-set-barcode-size/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}