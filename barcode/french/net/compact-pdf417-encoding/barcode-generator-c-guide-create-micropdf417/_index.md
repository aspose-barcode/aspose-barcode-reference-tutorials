---
category: general
date: 2026-09-29
description: Le guide du générateur de codes‑barres C# montre comment générer un code‑barres
  MicroPdf417, modifier les dimensions, définir les colonnes et personnaliser la taille
  du code‑barres en quelques lignes seulement.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- barcode generator c#
- how to generate barcode
- how to change dimensions
- how to set columns
- customize barcode size
language: fr
lastmod: 2026-09-29
og_description: Le guide du générateur de codes-barres C# montre comment générer un
  code‑barres MicroPdf417, modifier les dimensions, définir les colonnes et personnaliser
  la taille du code‑barres en quelques lignes seulement.
og_image_alt: Screenshot of a MicroPdf417 barcode generated with a C# barcode generator
og_title: Guide du générateur de codes-barres C# – créer et personnaliser MicroPdf417
schemas:
- author: GroupDocs
  dateModified: '2026-09-29'
  description: Barcode generator C# guide shows how to generate a MicroPdf417 barcode,
    change dimensions, set columns, and customize barcode size in just a few lines.
  headline: 'Barcode generator C# guide: create MicroPdf417'
  type: TechArticle
tags:
- barcode
- C#
- MicroPdf417
- barcode generation
title: 'Guide du générateur de codes-barres C# : créer MicroPdf417'
url: /fr/net/compact-pdf417-encoding/barcode-generator-c-guide-create-micropdf417/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Guide du générateur de codes-barres C# : créer MicroPdf417

Si vous avez besoin d’un **générateur de codes-barres C#** pour votre projet .NET, ce tutoriel vous montre comment créer un code‑barres MicroPdf417 à partir de zéro. Vous apprendrez **comment générer un code‑barres**, modifier les dimensions, définir le nombre de colonnes et **personnaliser la taille du code‑barres** en toute simplicité.

MicroPdf417 est une symbologie 2‑D compacte qui convient parfaitement à l’étiquetage de petites pièces, de tickets ou d’étiquettes d’inventaire. À la fin de ce guide, vous disposerez d’une application console complète et exécutable qui génère une image PNG du code‑barres, et vous comprendrez comment chaque paramètre influence la taille finale.

## Prérequis

Avant de commencer, assurez‑vous d’avoir :

* .NET 6.0 SDK ou version ultérieure (le code fonctionne également avec .NET Framework 4.7+)
* Un IDE compatible C# (Visual Studio, VS Code, Rider, etc.)
* Le package NuGet **GroupDocs.Barcode** – installez‑le avec  

  ```bash
  dotnet add package GroupDocs.Barcode
  ```

Aucun outil externe supplémentaire n’est requis ; la bibliothèque gère l’encodage, le rendu et l’enregistrement du fichier.

## Générateur de codes‑barres C# : initialisation du générateur

La première étape consiste à créer une instance de `BarcodeGenerator` et à spécifier la symbologie (`EncodeTypes.MicroPdf417`) ainsi que les données que vous souhaitez encoder.

```csharp
using System;
using GroupDocs.Barcode;
using GroupDocs.Barcode.Enums;
using GroupDocs.Barcode.Common;

namespace MicroPdf417Demo
{
    class Program
    {
        static void Main()
        {
            // Step 1 – create the generator with the desired text
            var generator = new BarcodeGenerator(
                EncodeTypes.MicroPdf417,
                "Åspóse.Barcóde©"
            );

            // Subsequent configuration steps go here...

            // Save the final image
            generator.Save("MicroPdf417.png", BarCodeImageFormat.Png);
            Console.WriteLine("Barcode saved as MicroPdf417.png");
        }
    }
}
```

**Pourquoi c’est important :**  
`BarcodeGenerator` est le point d’entrée pour toutes les opérations de code‑barres. Le constructeur lie le **EncodeTypes** choisi (MicroPdf417) à la chaîne de données brute. La bibliothèque gère automatiquement les caractères Unicode comme « Å » et « © », vous n’avez donc pas besoin de logique d’encodage supplémentaire.

## Comment modifier les dimensions du code‑barres

La lisibilité d’un code‑barres dépend fortement de la largeur du module (la dimension X). L’augmenter en nombre de pixels rend les barres plus larges et l’image plus facile à scanner, surtout sur des écrans à faible résolution.

```csharp
// Step 2 – adjust the X‑dimension (module width) to 2 pixels
generator.Parameters.Barcode.XDimension.Pixels = 2;
```

**Explication :**  
`XDimension.Pixels` contrôle la largeur d’un seul module du code‑barres. La valeur par défaut est de 1 pixel, ce qui peut paraître fin sur les moniteurs haute‑DPI. La porter à 2 pixels double la largeur globale sans affecter les données encodées.

**Astuce :** Si vous prévoyez d’imprimer le code‑barres à 300 dpi, une valeur de 3 ou 4 pixels offre généralement le meilleur compromis entre taille et fiabilité de lecture.

## Comment définir les colonnes pour contrôler la taille

MicroPdf417 vous permet de spécifier le nombre de colonnes (jusqu’à 4). Moins de colonnes produisent un code‑barres plus haut ; plus de colonnes le rendent plus large mais plus court. Ajuster cette valeur est le principal moyen de **personnaliser la taille du code‑barres**.

```csharp
// Step 3 – set the maximum number of columns (4 is the limit for MicroPdf417)
generator.Parameters.Barcode.Pdf417.Columns = 4;
```

**Pourquoi cela fonctionne :**  
La propriété `Pdf417.Columns` est partagée par toutes les symbologies basées sur PDF417, y compris MicroPdf417. La régler au maximum (4) répartit les données sur la mise en page la plus large possible, réduisant ainsi la hauteur globale. Si vous avez besoin d’une hauteur plus compacte, baissez le nombre de colonnes à 2 ou 3.

**Cas particulier :** Lorsque la chaîne de données est longue, la bibliothèque peut automatiquement augmenter le nombre de lignes pour accueillir le contenu, quel que soit le nombre de colonnes. Gardez la charge utile sous 50 caractères pour une taille prévisible.

## Personnaliser la taille du code‑barres pour différentes sorties

En plus de la dimension X et des colonnes, vous pouvez influencer la taille finale de l’image en choisissant un format d’image approprié et un DPI. PNG est sans perte, parfait pour l’affichage web, tandis que BMP ou TIFF peuvent être préférés pour l’impression haute qualité.

```csharp
// Step 4 – save as PNG (lossless) with default 96 dpi
generator.Save("MicroPdf417.png", BarCodeImageFormat.Png);
```

Si vous avez besoin d’un DPI plus élevé, vous pouvez le définir explicitement :

```csharp
generator.Parameters.Image.DpiX = 300;
generator.Parameters.Image.DpiY = 300;
generator.Save("MicroPdf417_300dpi.png", BarCodeImageFormat.Png);
```

**Résultat :** Le fichier PNG enregistré contient un code‑barres MicroPdf417 net qui respecte les dimensions que vous avez configurées. Ouvrez le fichier dans n’importe quel visualiseur d’image pour vérifier la taille visuelle.

### Résultat attendu

L’exécution du programme crée un fichier nommé **MicroPdf417.png** (ou **MicroPdf417_300dpi.png** si vous avez défini le DPI). Le code‑barres ressemblera à l’illustration ci‑dessous :

![Barcode generator C# output showing a MicroPdf417 PNG](barcode-micro-pdf417.png)

*Texte alternatif :* *Sortie du générateur de codes‑barres C# affichant un PNG MicroPdf417*

Scanner l’image avec un lecteur de codes‑barres 2‑D standard renvoie la chaîne originale `Åspóse.Barcóde©`.

## Code source complet pour copier‑coller rapidement

```csharp
using System;
using GroupDocs.Barcode;
using GroupDocs.Barcode.Enums;
using GroupDocs.Barcode.Common;

namespace MicroPdf417Demo
{
    class Program
    {
        static void Main()
        {
            // 1️⃣ Create the generator with the desired text
            var generator = new BarcodeGenerator(
                EncodeTypes.MicroPdf417,
                "Åspóse.Barcóde©"
            );

            // 2️⃣ Change dimensions – make modules 2 pixels wide
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // 3️⃣ Set columns – use the maximum of 4 for a wider, shorter barcode
            generator.Parameters.Barcode.Pdf417.Columns = 4;

            // (Optional) Increase DPI for high‑resolution output
            // generator.Parameters.Image.DpiX = 300;
            // generator.Parameters.Image.DpiY = 300;

            // 4️⃣ Save the barcode as a PNG image
            generator.Save("MicroPdf417.png", BarCodeImageFormat.Png);

            Console.WriteLine("Barcode saved as MicroPdf417.png");
        }
    }
}
```

Copiez le code dans un nouveau projet console, restaurez les packages NuGet, puis exécutez `dotnet run`. La console confirmera l’emplacement de l’image, et vous verrez le code‑barres généré dans le dossier de votre projet.

## Questions fréquentes et dépannage

| Question | Réponse |
|----------|--------|
| **Et si le code‑barres apparaît flou ?** | Augmentez `XDimension.Pixels` ou le DPI (`Parameters.Image.DpiX/Y`). Les deux agrandissent les modules et améliorent la fidélité visuelle. |
| **Puis‑je utiliser un autre format d’image ?** | Oui. Remplacez `BarCodeImageFormat.Png` par `Jpeg`, `Bmp` ou `Tiff`. PNG reste le choix le plus sûr pour une qualité sans perte. |
| **Mes données contiennent des emojis—seront‑ils encodés ?** | MicroPdf417 prend en charge UTF‑8, donc la plupart des emojis s’encodent correctement. En cas d’erreur, vérifiez que la chaîne est correctement normalisée (`System.Text.Encoding.UTF8`). |
| **Comment générer d’autres symbologies ?** | Changez `EncodeTypes.MicroPdf417` par n’importe quelle autre valeur de `EncodeTypes` (


## Que devriez‑vous apprendre ensuite ?


Les tutoriels suivants couvrent des sujets étroitement liés qui s’appuient sur les techniques présentées dans ce guide. Chaque ressource comprend des exemples de code complets avec des explications pas à pas pour vous aider à maîtriser d’autres fonctionnalités de l’API et explorer des approches d’implémentation alternatives dans vos propres projets.

- [How to Generate Barcode Image in C# – MicroPdf417 Guide](/barcode/english/net/compact-pdf417-encoding/how-to-generate-barcode-image-in-c-micropdf417-guide/)
- [How to generate PDF417 barcode in C# with custom dimensions](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-with-custom-dimensions/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}