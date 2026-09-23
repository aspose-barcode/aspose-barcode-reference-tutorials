---
category: general
date: 2026-07-27
description: Créez rapidement une image de code‑barres postal en C# — apprenez à générer
  un code‑barres postal, à générer un code‑barres Planet et à définir la hauteur du
  code‑barres.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create postal barcode image
- how to generate postal barcode
- generate planet barcode
- how to set barcode height
language: fr
lastmod: 2026-07-27
og_description: Créez une image de code‑barres postal en C# et maîtrisez la génération
  de code‑barres postal, la génération de code‑barres Planet, ainsi que le réglage
  de la hauteur du code‑barres pour des résultats parfaits.
og_image_alt: Sample PNG showing Planet and RM4SCC postal barcodes generated with
  Aspose.BarCode
og_title: Créer une image de code-barres postal en C# – Guide complet de programmation
schemas:
- author: Aspose
  dateModified: '2026-07-27'
  description: Create postal barcode image in C# quickly—learn how to generate postal
    barcode, generate planet barcode, and how to set barcode height.
  headline: Create Postal Barcode Image in C# – Full Step‑by‑Step Guide
  type: TechArticle
- description: Create postal barcode image in C# quickly—learn how to generate postal
    barcode, generate planet barcode, and how to set barcode height.
  name: Create Postal Barcode Image in C# – Full Step‑by‑Step Guide
  steps:
  - name: Why set `XDimension`?
    text: '`XDimension` is the pixel width of the smallest bar. If you leave it at
      the library’s default (usually 1 px), the barcode can look cramped on high‑resolution
      screens. Setting it to **4 px** gives a nicely spaced image that prints cleanly
      on most printers.'
  - name: What does `BarHeight.Pixels` actually do?
    text: When you **set barcode height**, you override the library’s automatic calculation.
      By default Aspose.BarCode chooses a height that keeps the barcode square‑ish,
      which is fine for many use‑cases. However, postal standards sometimes demand
      a minimum bar height (e.g., 100 px for high‑resolution printin
  - name: Edge Cases & Common Pitfalls
    text: '- **Zero or negative height** – the library throws `ArgumentException`.
      Always validate user input. - **Non‑integer pixel values** – the property is
      an `int`, so fractions are rounded down automatically. - **Changing DPI after
      setting height** – the visual size changes, but the pixel count stays the'
  - name: Expected Output
    text: 'When you open the generated PNG files you’ll see:'
  type: HowTo
tags:
- barcode
- C#
- Aspose
- postal
title: Créer une image de code‑barres postal en C# – Guide complet étape par étape
url: /fr/python-java/general/create-postal-barcode-image-in-c-full-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Créer une image de code‑barres postal en C# – Guide complet étape par étape

Vous avez déjà eu besoin de **créer une image de code‑barres postal** en C# sans savoir quelles propriétés ajuster ? Vous n'êtes pas seul. Que vous construisiez un système d'étiquettes postales ou que vous expérimentiez simplement avec les symbologies postales, maîtriser les bons appels d'API rend le tout très simple.

Dans ce tutoriel, nous allons voir **comment générer des images de code‑barres postal** aux formats Planet et RM4SCC, et nous vous montrerons **comment définir la hauteur du code‑barres** afin que les barres apparaissent exactement comme vous le souhaitez. À la fin, vous disposerez d’une application console prête à l’emploi qui génère quatre fichiers PNG — deux avec des hauteurs par défaut et deux avec une hauteur de barre explicite de 100 px.

## Ce dont vous aurez besoin

- **.NET 6.0** ou version ultérieure (le code se compile également sous .NET Framework 4.6+)
- **Aspose.BarCode for .NET** – le package NuGet qui fournit `BarcodeGenerator`
- Un dossier sur le disque où les fichiers PNG pourront être enregistrés (remplacez `YOUR_DIRECTORY` dans l’exemple)

Si vous n’avez jamais utilisé Aspose.BarCode auparavant, récupérez‑le depuis NuGet :

```bash
dotnet add package Aspose.BarCode
```

C’est tout — pas de DLL supplémentaires, pas de dépendances natives. Passons à l’action.

## Créer une image de code‑barres postal – Initialiser le générateur

La première chose à faire est de créer une instance de `BarcodeGenerator`. Cet objet est le point d’entrée pour *tout* code‑barres que vous souhaitez rendre. Vous transmettez deux arguments au constructeur :

1. Le **type d’encodage** (`EncodeTypes.Planet` ou `EncodeTypes.RM4SCC`)
2. La **chaîne de données** (le code postal numérique, par exemple `"123456"`)

```csharp
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Folder where PNG files will be saved
        const string outputFolder = @"C:\Temp\Barcodes";

        // Ensure the folder exists
        System.IO.Directory.CreateDirectory(outputFolder);

        // ---------- Planet barcode with default height ----------
        var planetGenerator = new BarcodeGenerator(EncodeTypes.Planet, "123456");
        // X‑dimension controls the width of the narrowest bar (in pixels)
        planetGenerator.Parameters.Barcode.XDimension.Pixels = 4;
        string planetDefaultPath = System.IO.Path.Combine(outputFolder, "PlanetDefault.png");
        planetDefaultPath = System.IO.Path.ChangeExtension(planetDefaultPath, "png");
        planetGenerator.Save(planetDefaultPath, BarCodeImageFormat.Png);

        // ---------- RM4SCC barcode with default height ----------
        var rm4sccGenerator = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");
        rm4sccGenerator.Parameters.Barcode.XDimension.Pixels = 4;
        string rm4sccDefaultPath = System.IO.Path.Combine(outputFolder, "RM4SCCDefault.png");
        rm4sccGenerator.Save(rm4sccDefaultPath, BarCodeImageFormat.Png);
```

### Pourquoi définir `XDimension` ?

`XDimension` correspond à la largeur en pixels de la plus petite barre. Si vous laissez la valeur par défaut de la bibliothèque (généralement 1 px), le code‑barres peut paraître trop serré sur des écrans haute résolution. Le régler à **4 px** donne une image bien espacée qui s’imprime proprement sur la plupart des imprimantes.

## Comment générer un code‑barres postal – Types Planet et RM4SCC

Maintenant que nous disposons d’un générateur, parlons des *deux* symbologies postales les plus courantes : **Planet** (utilisé au Royaume‑Uni) et **RM4SCC** (utilisé aux États‑Unis). La seule différence dans le code réside dans la valeur de l’énumération `EncodeTypes`. Tout le reste — comme l’enregistrement, le DPI ou le format PNG — reste identique.

```csharp
        // ---------- Planet barcode with explicit 100 px height ----------
        var planetHeightGenerator = new BarcodeGenerator(EncodeTypes.Planet, "123456");
        planetHeightGenerator.Parameters.Barcode.XDimension.Pixels = 4;
        // Here we answer the “how to set barcode height” question.
        planetHeightGenerator.Parameters.Barcode.BarHeight.Pixels = 100;
        string planetHeightPath = System.IO.Path.Combine(outputFolder, "PlanetHeight100.png");
        planetHeightGenerator.Save(planetHeightPath, BarCodeImageFormat.Png);

        // ---------- RM4SCC barcode with explicit 100 px height ----------
        var rm4sccHeightGenerator = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");
        rm4sccHeightGenerator.Parameters.Barcode.XDimension.Pixels = 4;
        rm4sccHeightGenerator.Parameters.Barcode.BarHeight.Pixels = 100;
        string rm4sccHeightPath = System.IO.Path.Combine(outputFolder, "RM4SCCHeight100.png");
        rm4sccHeightGenerator.Save(rm4sccHeightPath, BarCodeImageFormat.Png);
    }
}
```

### Que fait réellement la propriété `BarHeight.Pixels` ?

Lorsque vous **définissez la hauteur du code‑barres**, vous remplacez le calcul automatique de la bibliothèque. Par défaut, Aspose.BarCode choisit une hauteur qui garde le code‑barres presque carré, ce qui convient à de nombreux cas d’utilisation. Cependant, les normes postales exigent parfois une hauteur minimale de barre (par ex., 100 px pour une impression haute résolution). La propriété `BarHeight.Pixels` vous permet de respecter précisément ces spécifications.

## Comment définir la hauteur du code‑barres – Contrôler la hauteur des barres selon les normes postales

Si vous vous demandez **comment définir la hauteur du code‑barres** pour une résolution d’imprimante spécifique, vous pouvez combiner `BarHeight.Pixels` avec les paramètres de `Resolution` :

```csharp
        // Example: 300 DPI, 1 inch tall => 300 px
        planetHeightGenerator.Parameters.ImageResolution = 300;
        planetHeightGenerator.Parameters.Barcode.BarHeight.Pixels = 300; // 1‑inch bar at 300 DPI
```

> **Astuce :** Testez toujours quelques hauteurs différentes sur votre imprimante cible. Trop haut et le code‑barres peut dépasser la zone imprimable de l’étiquette ; trop bas et les scanners risquent de ne pas détecter la zone silencieuse.

### Cas limites et pièges courants

- **Hauteur nulle ou négative** – la bibliothèque lève une `ArgumentException`. Validez toujours les entrées utilisateur.  
- **Valeurs de pixel non entières** – la propriété est un `int`, les fractions sont donc automatiquement arrondies vers le bas.  
- **Modification du DPI après avoir fixé la hauteur** – la taille visuelle change, mais le nombre de pixels reste identique. Si vous avez besoin d’une taille physique (par ex., 1 cm), calculez `pixels = DPI * cm / 2.54`.

## Exemple complet fonctionnel – Toutes les étapes combinées

Voici le programme complet, prêt à copier‑coller. Il inclut la gestion des erreurs, la création du dossier et des commentaires expliquant chaque ligne. Exécutez‑le depuis un projet console et vous obtiendrez quatre fichiers PNG dans `C:\Temp\Barcodes`.

```csharp
using System;
using System.IO;
using Aspose.BarCode.Generation;

namespace PostalBarcodeDemo
{
    class Program
    {
        static void Main()
        {
            const string outputFolder = @"C:\Temp\Barcodes";
            Directory.CreateDirectory(outputFolder);

            try
            {
                // 1️⃣ Planet barcode – default (automatic) height
                var planetDefault = new BarcodeGenerator(EncodeTypes.Planet, "123456");
                planetDefault.Parameters.Barcode.XDimension.Pixels = 4;
                string planetDefaultPath = Path.Combine(outputFolder, "PlanetDefault.png");
                planetDefault.Save(planetDefaultPath, BarCodeImageFormat.Png);
                Console.WriteLine($"Saved: {planetDefaultPath}");

                // 2️⃣ RM4SCC barcode – default (automatic) height
                var rm4sccDefault = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");
                rm4sccDefault.Parameters.Barcode.XDimension.Pixels = 4;
                string rm4sccDefaultPath = Path.Combine(outputFolder, "RM4SCCDefault.png");
                rm4sccDefault.Save(rm4sccDefaultPath, BarCodeImageFormat.Png);
                Console.WriteLine($"Saved: {rm4sccDefaultPath}");

                // 3️⃣ Planet barcode – explicit 100 px height
                var planetHeight = new BarcodeGenerator(EncodeTypes.Planet, "123456");
                planetHeight.Parameters.Barcode.XDimension.Pixels = 4;
                planetHeight.Parameters.Barcode.BarHeight.Pixels = 100;
                string planetHeightPath = Path.Combine(outputFolder, "PlanetHeight100.png");
                planetHeight.Save(planetHeightPath, BarCodeImageFormat.Png);
                Console.WriteLine($"Saved: {planetHeightPath}");

                // 4️⃣ RM4SCC barcode – explicit 100 px height
                var rm4sccHeight = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");
                rm4sccHeight.Parameters.Barcode.XDimension.Pixels = 4;
                rm4sccHeight.Parameters.Barcode.BarHeight.Pixels = 100;
                string rm4sccHeightPath = Path.Combine(outputFolder, "RM4SCCHeight100.png");
                rm4sccHeight.Save(rm4sccHeightPath, BarCodeImageFormat.Png);
                Console.WriteLine($"Saved: {rm4sccHeightPath}");
            }
            catch (Exception ex)
            {
                Console.Error.WriteLine($"Something went wrong: {ex.Message}");
            }
        }
    }
}
```

### Résultat attendu

Lorsque vous ouvrirez les fichiers PNG générés, vous verrez :

| Fichier | Symbologie | Hauteur | Notes visuelles |
|---------|------------|---------|-----------------|
| `PlanetDefault.png` | Planet | Automatique (≈ 50 px) | Fine |

## Que devriez‑vous apprendre ensuite ?

Les tutoriels suivants couvrent des sujets étroitement liés qui s’appuient sur les techniques présentées dans ce guide. Chaque ressource comprend des exemples de code complets avec des explications pas à pas pour vous aider à maîtriser d’autres fonctionnalités de l’API et explorer des approches d’implémentation alternatives dans vos propres projets.

- [How to Generate Barcode - One-Dimensional Barcode Types](/barcode/english/net/one-dimensional-barcode-types/)
- [How to Generate Barcode – Code 39 Configuration with Aspose.BarCode](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-code-39-configuration/)
- [How to Generate DataMatrix Barcodes (ECC 200) with Aspose.BarCode for .NET](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-ecc-200-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}