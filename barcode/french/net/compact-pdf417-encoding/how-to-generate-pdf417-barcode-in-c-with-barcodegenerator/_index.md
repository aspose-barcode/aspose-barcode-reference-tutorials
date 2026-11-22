---
category: general
date: 2026-11-20
description: Apprenez à générer un code‑barres PDF417 en C# avec BarcodeGenerator.
  Ce guide étape par étape couvre la dimension X, les paramètres de colonnes et l’exportation
  PNG.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate pdf417 barcode
- PDF417 barcode in C#
- BarcodeGenerator EncodeTypes
- set XDimension pixels
- configure PDF417 columns
- save barcode as PNG
language: fr
lastmod: 2026-11-20
og_description: Générez rapidement un code‑barres PDF417 en C#. Suivez ce guide pour
  définir les dimensions, les colonnes et exporter le code‑barres au format PNG.
og_image_alt: Screenshot of C# code that generates a PDF417 barcode and saves it as
  a PNG file
og_title: Générer un code‑barres PDF417 en C# – guide complet étape par étape
schemas:
- author: Aspose
  dateModified: '2026-11-20'
  description: Learn how to generate PDF417 barcode in C# using BarcodeGenerator.
    This step‑by‑step guide covers X‑Dimension, column settings, and PNG export.
  headline: How to generate PDF417 barcode in C# with BarcodeGenerator
  type: TechArticle
- description: Learn how to generate PDF417 barcode in C# using BarcodeGenerator.
    This step‑by‑step guide covers X‑Dimension, column settings, and PNG export.
  name: How to generate PDF417 barcode in C# with BarcodeGenerator
  steps:
  - name: '**Initialize the generator** – The `BarcodeGenerator` ties the chosen symbology
      (`EncodeTypes.Pdf417`) to the data you want to encode. Without this object you
      cannot access any further configuration.'
    text: '**Initialize the generator** – The `BarcodeGenerator` ties the chosen symbology
      (`EncodeTypes.Pdf417`) to the data you want to encode. Without this object you
      cannot access any further configuration.'
  - name: '**Set X‑Dimension** – PDF417 is built from tiny rectangular modules. Changing
      `XDimension.Pixels` lets you control the barcode’s visual density, which is
      crucial for readability on low‑resolution displays or printers.'
    text: '**Set X‑Dimension** – PDF417 is built from tiny rectangular modules. Changing
      `XDimension.Pixels` lets you control the barcode’s visual density, which is
      crucial for readability on low‑resolution displays or printers.'
  - name: '**Configure columns** – PDF417 can arrange its codewords in a variable
      number of columns. Fewer columns produce a taller barcode, while more columns
      flatten it. Adjust this to fit the space where the image will be placed.'
    text: '**Configure columns** – PDF417 can arrange its codewords in a variable
      number of columns. Fewer columns produce a taller barcode, while more columns
      flatten it. Adjust this to fit the space where the image will be placed.'
  - name: '**Save as PNG** – PNG is a loss‑less format, preserving the sharp edges
      required for accurate scanning. You could also choose JPEG or BMP, but PNG is
      the safest default.'
    text: '**Save as PNG** – PNG is a loss‑less format, preserving the sharp edges
      required for accurate scanning. You could also choose JPEG or BMP, but PNG is
      the safest default.'
  type: HowTo
tags:
- barcode
- PDF417
- C#
- Aspose.BarCode
title: Comment générer un code‑barres PDF417 en C# avec BarcodeGenerator
url: /fr/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-with-barcodegenerator/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Comment générer un code-barres PDF417 en C# avec BarcodeGenerator

Si vous devez **générer un code-barres PDF417** dans une application .NET, ce guide vous montre exactement comment procéder. Vous verrez un exemple complet et exécutable qui définit la X‑Dimension, choisit le nombre de colonnes et enregistre le résultat sous forme d’image PNG.

Générer un code-barres PDF417 est courant lorsque vous devez encoder une grande quantité de données — comme un permis de conduire, une carte d’embarquement ou un enregistrement d’inventaire — dans une image compacte et lisible par machine. Dans ce tutoriel, nous utilisons la classe **BarcodeGenerator** de la bibliothèque Aspose.BarCode, mais les concepts s’appliquent à toute bibliothèque prenant en charge PDF417.

À la fin de cet article, vous serez capable de :

* Initialiser un `BarcodeGenerator` pour l’encodage PDF417.  
* Ajuster la taille du module avec **set XDimension pixels**.  
* Contrôler la mise en page en utilisant **configure PDF417 columns**.  
* **Enregistrer le code-barres au format PNG** pour une utilisation dans les pages web, les applications mobiles ou le matériel imprimé.  

> **Prerequisites**  
> * .NET 6.0 ou version ultérieure (le code fonctionne également avec .NET Framework 4.7+).  
> * Une référence au package NuGet **Aspose.BarCode** (`Install-Package Aspose.BarCode`).  
> * Une connaissance de base de C# et de Visual Studio (ou tout autre IDE de votre choix).

---

## Comment générer un code-barres PDF417 en C#

Le cœur de la solution repose sur un court processus en quatre étapes. Chaque étape est encapsulée dans une méthode dédiée afin que vous puissiez réutiliser la logique dans des projets plus importants.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace Pdf417Demo
{
    class Program
    {
        static void Main()
        {
            // 1️⃣ Initialize the generator with the desired text
            var generator = CreateGenerator("Åspóse.Barcóde©");

            // 2️⃣ Adjust the X‑Dimension (module size)
            SetXDimension(generator, 2);

            // 3️⃣ Define how many columns the barcode should have
            SetPdf417Columns(generator, 3);

            // 4️⃣ Save the barcode as a PNG file
            SaveAsPng(generator, @"YOUR_DIRECTORY\Pdf417Basic.png");

            Console.WriteLine("PDF417 barcode generated successfully.");
        }

        // ---------------------------------------------------------
        // Step 1: Create a BarcodeGenerator for PDF417
        // ---------------------------------------------------------
        private static BarcodeGenerator CreateGenerator(string text)
        {
            // EncodeTypes.Pdf417 tells the library to use the PDF417 symbology.
            return new BarcodeGenerator(EncodeTypes.Pdf417, text);
        }

        // ---------------------------------------------------------
        // Step 2: Set the X‑Dimension (size of a single module)
        // ---------------------------------------------------------
        private static void SetXDimension(BarcodeGenerator generator, int pixels)
        {
            // XDimension controls the width of the smallest black/white bar.
            // A value of 2 pixels works well for most screen resolutions.
            generator.Parameters.Barcode.XDimension.Pixels = pixels;
        }

        // ---------------------------------------------------------
        // Step 3: Configure the number of columns in the PDF417 barcode
        // ---------------------------------------------------------
        private static void SetPdf417Columns(BarcodeGenerator generator, int columns)
        {
            // Columns affect the barcode’s aspect ratio.
            // Small numbers (e.g., 3) produce a tall barcode; larger numbers make it wider.
            generator.Parameters.Barcode.Pdf417.Columns = columns;
        }

        // ---------------------------------------------------------
        // Step 4: Export the barcode as a PNG image
        // ---------------------------------------------------------
        private static void SaveAsPng(BarcodeGenerator generator, string outputPath)
        {
            // BarCodeImageFormat.Png ensures lossless quality.
            generator.Save(outputPath, BarCodeImageFormat.Png);
        }
    }
}
```

### Pourquoi ces quatre étapes sont importantes

1. **Initialize the generator** – Le `BarcodeGenerator` lie la symbologie choisie (`EncodeTypes.Pdf417`) aux données que vous souhaitez encoder. Sans cet objet, vous ne pouvez pas accéder aux configurations supplémentaires.  
2. **Set X‑Dimension** – PDF417 est construit à partir de minuscules modules rectangulaires. Modifier `XDimension.Pixels` vous permet de contrôler la densité visuelle du code‑barres, ce qui est crucial pour la lisibilité sur des écrans ou imprimantes à basse résolution.  
3. **Configure columns** – PDF417 peut disposer ses codewords dans un nombre variable de colonnes. Moins de colonnes produisent un code‑barres plus haut, tandis que davantage de colonnes l’aplatissent. Ajustez cela pour l’adapter à l’espace où l’image sera placée.  
4. **Save as PNG** – PNG est un format sans perte, préservant les bords nets nécessaires à une numérisation précise. Vous pourriez également choisir JPEG ou BMP, mais PNG reste le choix le plus sûr par défaut.

## Configurer les dimensions du code-barres (X‑Dimension)

L’étape **set XDimension pixels** influence directement la façon dont les scanners interprètent le code‑barres. Si le module est trop petit, les caméras de faible qualité peuvent manquer des barres individuelles ; s’il est trop grand, le code‑barres peut devenir inutilement volumineux.

```csharp
generator.Parameters.Barcode.XDimension.Pixels = 2; // 2‑pixel modules
```

**Best practice:** Testez l’image générée à la taille d’impression prévue. Pour une impression haute densité (300 dpi ou plus), une valeur de `1` ou `2` fonctionne bien. Pour un affichage à l’écran à 96 dpi, `2`–`3` offre un rendu clair.

## Définir les colonnes PDF417

L’étape **configure PDF417 columns** vous permet de décider de la forme du code‑barres.

```csharp
generator.Parameters.Barcode.Pdf417.Columns = 3; // three columns → tall barcode
```

### Quand modifier le nombre de colonnes

| Colonnes | Forme résultante | Cas d’utilisation typique |
|----------|------------------|----------------------------|
| 1–3      | Haute, étroite   | Étiquettes avec largeur limitée |
| 4–9      | Équilibrée       | Numérisation à usage général |
| 10+      | Large, courte    | Grande signalétique ou graphiques web |

Si votre charge de données dépasse la capacité par défaut, la bibliothèque ajoute automatiquement des lignes supplémentaires, mais vous pouvez toujours influencer le ratio d’aspect en ajustant le nombre de colonnes.

## Exporter le code-barres au format PNG

Enregistrer le code‑barres sous forme d’image PNG est simple :

```csharp
generator.Save(@"C:\Barcodes\Pdf417Basic.png", BarCodeImageFormat.Png);
```

**Why PNG?**  
* La compression sans perte conserve les bords nets nécessaires aux lecteurs de codes‑barres.  
* PNG prend en charge la transparence, ce qui peut être utile si vous superposez le code‑barres sur un arrière‑plan coloré ultérieurement.

Si vous avez besoin d’un autre format, remplacez `BarCodeImageFormat.Png` par `Jpeg`, `Bmp` ou `Svg` — l’API gère automatiquement la conversion.

## Problèmes courants et dépannage

| Problème | Cause probable | Solution |
|----------|----------------|----------|
| Le code‑barres apparaît flou | X‑Dimension trop petite pour la résolution de sortie | Augmenter `XDimension.Pixels` à 3 ou 4. |
| Le scanner ne peut pas lire le code | Caractères Unicode non pris en charge par la police sélectionnée | Vérifiez que la police de la bibliothèque prend en charge les caractères, ou remplacez‑les par des équivalents ASCII. |
| Le fichier de sortie n’est pas créé | Chemin invalide ou permissions d’écriture manquantes | Utilisez un chemin absolu et vérifiez les droits d’écriture du dossier. |
| Trop de lignes, le code‑barres devient trop haut | Nombre de colonnes trop faible pour la longueur des données | Augmentez `Pdf417.Columns` à un nombre plus élevé (par ex., 6). |

## Récapitulatif de l’exemple complet

Voici le **programme complet** que vous pouvez copier‑coller dans un nouveau projet console. Aucun code supplémentaire n’est requis au‑delà des instructions `using` et du package Aspose.BarCode.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace Pdf417Demo
{
    class Program
    {
        static void Main()
        {
            var generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Åspóse.Barcóde©");
            generator.Parameters.Barcode.XDimension.Pixels = 2;
            generator.Parameters.Barcode.Pdf417.Columns = 3;
            generator.Save(@"YOUR_DIRECTORY\Pdf417Basic.png", BarCodeImageFormat.Png);
            Console.WriteLine("PDF417 barcode generated and saved as PNG.");
        }
    }
}
```

**Expected output:** Un fichier nommé `Pdf417Basic.png` contenant un code‑barres PDF417 clair qui encode la chaîne `Åspóse.Barcóde©`. Lorsqu’il est ouvert, l’image doit afficher une série de barres rectangulaires empilées avec une densité plus élevée du côté gauche (du fait de la disposition à trois colonnes).

## Conclusion

Vous savez maintenant comment **générer un code‑barres PDF417** en C# en utilisant la classe `BarcodeGenerator`. Le tutoriel a couvert l’initialisation du générateur, **set XDimension pixels**, **configure PDF417 columns**, et **save barcode as PNG** — les étapes essentielles pour tout flux de travail de code‑barres prêt pour la production.

À partir d’ici, vous pouvez :

* Expérimenter différents `EncodeTypes` (par ex., QR, Code128).  
* Ajouter des niveaux de correction d’erreurs via `generator.Parameters.Barcode.Pdf417.ErrorLevel`.  
* Rendre le code‑barres directement dans un `MemoryStream` pour les API web.  

N'hésitez pas à adapter le code à votre propre projet, et à partager vos résultats dans les commentaires ou sur Stack Overflow en utilisant le tag `#pdf417`. Bon codage !

## Que devriez‑vous apprendre ensuite ?

Les tutoriels suivants couvrent des sujets étroitement liés qui s’appuient sur les techniques démontrées dans ce guide. Chaque ressource inclut des exemples de code complets avec des explications étape par étape pour vous aider à maîtriser des fonctionnalités API supplémentaires et explorer des approches d’implémentation alternatives dans vos propres projets.

- [Générer un code‑barres PDF417 au format PNG en C# – guide étape par étape](/barcode/english/net/compact-pdf417-encoding/generate-pdf417-barcode-as-png-in-c-step-by-step-guide/)
- [Comment générer un code‑barres PDF417 en C# – guide étape par étape](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-step-by-step-guide/)
- [Comment générer un code‑barres PDF417 en C# avec des dimensions personnalisées](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-with-custom-dimensions/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}