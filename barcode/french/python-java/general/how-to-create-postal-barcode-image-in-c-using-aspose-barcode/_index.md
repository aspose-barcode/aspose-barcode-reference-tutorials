---
category: general
date: 2026-10-02
description: Créer une image de code‑barres postal en C# avec Aspose.BarCode. Apprenez
  à générer les codes‑barres Planet et RM4SCC, à personnaliser les barres remplies
  et à enregistrer les fichiers PNG.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create postal barcode image
- generate planet barcode
- Aspose.BarCode C#
- postal barcode PNG
- barcode XDimension setting
language: fr
lastmod: 2026-10-02
og_description: Créez une image de code‑barres postal en C# avec Aspose.BarCode. Ce
  tutoriel montre comment générer les codes‑barres Planet et RM4SCC, ajuster le remplissage
  des barres et exporter des fichiers PNG.
og_image_alt: Postal barcode image generated with Aspose.BarCode (filled bars)
og_title: Créer une image de code‑barres postal en C# – guide étape par étape
schemas:
- author: Aspose
  dateModified: '2026-10-02'
  description: Create postal barcode image in C# with Aspose.BarCode. Learn to generate
    Planet and RM4SCC barcodes, customize filled bars, and save PNG files.
  headline: How to create postal barcode image in C# using Aspose.BarCode
  type: TechArticle
- description: Create postal barcode image in C# with Aspose.BarCode. Learn to generate
    Planet and RM4SCC barcodes, customize filled bars, and save PNG files.
  name: How to create postal barcode image in C# using Aspose.BarCode
  steps:
  - name: Why each line matters
    text: '* **`new BarcodeGenerator(EncodeTypes.Planet, "123456")`** – The `EncodeTypes.Planet`
      enum tells Aspose.BarCode to use the *Planet* symbology, which is a standard
      postal barcode in many countries. This is the core of how you **generate planet
      barcode** images. * **`XDimension.Pixels = 4`** – The wid'
  - name: Expected output
    text: 'After running the program, the `YOUR_DIRECTORY` folder contains three PNG
      files:'
  - name: Change image format
    text: If you need a different format (e.g., JPEG for web delivery), replace `BarCodeImageFormat.Png`
      with `BarCodeImageFormat.Jpeg`. Keep in mind that JPEG introduces compression
      artifacts, which can affect scanner performance.
  - name: Adjust image size without scaling
    text: Instead of changing `XDimension`, you can control the overall image dimensions
      via `Parameters.Image.Height` and `Parameters.Image.Width`. This is useful when
      you have a fixed label size.
  - name: Use a different barcode symbology
    text: Aspose.BarCode supports dozens of postal symbologies (e.g., **USPS Intelligent
      Mail**, **Japan Post**). To **generate planet barcode** alternatives, replace
      `EncodeTypes.Planet` with the desired enum value.
  - name: Handling invalid data
    text: Postal barcodes have strict data length rules. If you pass a string that
      does not meet the specification, Aspose.BarCode throws an `ArgumentException`.
      Wrap the generator creation in a `try/catch` block to provide a friendly error
      message.
  type: HowTo
tags:
- barcode
- C#
- Aspose
title: Comment créer une image de code‑barres postal en C# avec Aspose.BarCode
url: /fr/python-java/general/how-to-create-postal-barcode-image-in-c-using-aspose-barcode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Comment créer une image de code-barres postal en C# avec Aspose.BarCode

Si vous devez **créer une image de code-barres postal** en C#, Aspose.BarCode fournit une API claire qui gère les tâches lourdes. Que vous construisiez un système d'étiquettes d'envoi ou un service de vérification d'adresses, ce guide vous montre exactement comment générer les codes-barres Planet et RM4SCC, basculer entre des barres remplies et vides, et exporter le résultat sous forme de fichiers PNG.

Vous apprendrez à configurer la taille du code-barres, à contrôler le comportement de remplissage des barres, et à enregistrer l'image sur le disque — le tout dans un seul programme exécutable. Aucun outil externe n'est requis en dehors de la bibliothèque Aspose.BarCode pour .NET.

## Prérequis

Avant de commencer, assurez-vous d'avoir :

* .NET 6.0 SDK ou version ultérieure (le code fonctionne également avec .NET Framework 4.7+)
* Visual Studio 2022 ou tout IDE compatible C#
* Une copie sous licence ou d'évaluation de **Aspose.BarCode for .NET** (disponible via NuGet)

```bash
dotnet add package Aspose.BarCode
```

## Vue d'ensemble de la solution

Le tutoriel est divisé en trois étapes logiques :

1. **Créer un code-barres Planet avec les barres par défaut (remplies)** – cela montre l'apparence typique pour les services postaux.  
2. **Créer un code-barres Planet avec des barres vides** – utile lorsque le processus d'impression attend des barres non remplies.  
3. **Créer un code-barres RM4SCC avec des barres remplies** – un autre format postal courant utilisé dans de nombreux pays.  

Chaque étape suit le même schéma : instancier `BarcodeGenerator`, définir `XDimension` (largeur en pixels d'une seule barre), ajuster éventuellement `FilledBars`, et appeler `Save` pour écrire un fichier PNG.

---

## Créer une image de code-barres postal avec Aspose.BarCode

Voici le programme complet et autonome. Enregistrez-le sous le nom `Program.cs` et exécutez-le depuis la ligne de commande ou votre IDE.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace PostalBarcodeDemo
{
    class Program
    {
        static void Main(string[] args)
        {
            // Define the output folder – change this to a writable location on your machine
            string outputDir = @"YOUR_DIRECTORY";

            // -------------------------------------------------
            // Step 1: Generate a Planet barcode with filled bars
            // -------------------------------------------------
            var planetFilled = new BarcodeGenerator(EncodeTypes.Planet, "123456")
            {
                // XDimension controls the width of a single bar in pixels.
                // A value of 4 gives a good balance between readability and file size.
                Parameters = { Barcode = { XDimension = { Pixels = 4 } } }
            };
            string planetFilledPath = System.IO.Path.Combine(outputDir, "PostalPlanetFilledBars.png");
            planetFilled.Save(planetFilledPath, BarCodeImageFormat.Png);
            Console.WriteLine($"Filled Planet barcode saved to {planetFilledPath}");

            // -------------------------------------------------
            // Step 2: Generate a Planet barcode with empty bars
            // -------------------------------------------------
            var planetEmpty = new BarcodeGenerator(EncodeTypes.Planet, "123456")
            {
                Parameters = {
                    Barcode = {
                        XDimension = { Pixels = 4 },
                        // Setting FilledBars to false renders the bars as empty outlines.
                        FilledBars = false
                    }
                }
            };
            string planetEmptyPath = System.IO.Path.Combine(outputDir, "PostalPlanetEmptyBars.png");
            planetEmpty.Save(planetEmptyPath, BarCodeImageFormat.Png);
            Console.WriteLine($"Empty Planet barcode saved to {planetEmptyPath}");

            // -------------------------------------------------
            // Step 3: Generate an RM4SCC barcode with filled bars
            // -------------------------------------------------
            var rm4sccFilled = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456")
            {
                Parameters = { Barcode = { XDimension = { Pixels = 4 } } }
            };
            string rm4sccPath = System.IO.Path.Combine(outputDir, "PostalRM4SCCFilledBars.png");
            rm4sccFilled.Save(rm4sccPath, BarCodeImageFormat.Png);
            Console.WriteLine($"Filled RM4SCC barcode saved to {rm4sccPath}");

            // End of demo
            Console.WriteLine("All barcode images have been generated successfully.");
        }
    }
}
```

### Pourquoi chaque ligne est importante

* **`new BarcodeGenerator(EncodeTypes.Planet, "123456")`** – L'énumération `EncodeTypes.Planet` indique à Aspose.BarCode d'utiliser la symbologie *Planet*, qui est un code-barres postal standard dans de nombreux pays. C’est le cœur de la façon dont vous **générez des images de code-barres planet**.  
* **`XDimension.Pixels = 4`** – La largeur d'une seule barre influence à la fois la fiabilité du scan et la taille visuelle. Une valeur de 4 px fonctionne bien pour la plupart des imprimantes d'étiquettes ; vous pouvez l'augmenter pour des sorties à plus haute résolution.  
* **`FilledBars = false`** – Par défaut, les barres sont remplies. Le définir à `false` crée le style « barre vide » requis par certaines spécifications d'envoi.  
* **`Save(..., BarCodeImageFormat.Png)`** – Le PNG conserve une qualité sans perte, ce qui le rend idéal pour les images de code-barres qui doivent être lues par des scanners.  

### Résultat attendu

Après l'exécution du programme, le dossier `YOUR_DIRECTORY` contient trois fichiers PNG :

| Nom du fichier                       | Description visuelle |
|--------------------------------------|----------------------|
| `PostalPlanetFilledBars.png`         | Code-barres Planet avec des barres noires pleines |
| `PostalPlanetEmptyBars.png`          | Code-barres Planet où les barres sont dessinées (vides) |
| `PostalRM4SCCFilledBars.png`         | Code-barres RM4SCC avec des barres pleines |

Vous pouvez ouvrir n'importe laquelle de ces images dans un visualiseur d'images ou les intégrer directement dans une étiquette PDF/HTML.

---

## Personnaliser davantage le code-barres (facultatif)

### Modifier le format de l'image

Si vous avez besoin d'un format différent (par ex., JPEG pour la diffusion web), remplacez `BarCodeImageFormat.Png` par `BarCodeImageFormat.Jpeg`. Gardez à l'esprit que le JPEG introduit des artefacts de compression, ce qui peut affecter les performances du scanner.

### Ajuster la taille de l'image sans mise à l'échelle

Au lieu de modifier `XDimension`, vous pouvez contrôler les dimensions globales de l'image via `Parameters.Image.Height` et `Parameters.Image.Width`. Cela est utile lorsque vous avez une taille d'étiquette fixe.

```csharp
planetFilled.Parameters.Image.Height = 150; // pixels
planetFilled.Parameters.Image.Width = 300;  // pixels
```

### Utiliser une symbologie de code-barres différente

Aspose.BarCode prend en charge des dizaines de symbologies postales (par ex., **USPS Intelligent Mail**, **Japan Post**). Pour **générer des alternatives de code-barres planet**, remplacez `EncodeTypes.Planet` par la valeur d'énumération souhaitée.

```csharp
var uspsBarcode = new BarcodeGenerator(EncodeTypes.USPSIntelligentMail, "123456789012");
```

### Gestion des données invalides

Les codes-barres postaux ont des règles strictes de longueur de données. Si vous transmettez une chaîne qui ne respecte pas la spécification, Aspose.BarCode lève une `ArgumentException`. Enveloppez la création du générateur dans un bloc `try/catch` pour fournir un message d'erreur convivial.

```csharp
try
{
    var invalid = new BarcodeGenerator(EncodeTypes.Planet, "ABC");
}
catch (ArgumentException ex)
{
    Console.Error.WriteLine($"Invalid barcode data: {ex.Message}");
}
```

---

## Pièges courants et astuces professionnelles

| Piège                                   | Pourquoi cela se produit                                            | Astuce |
|-----------------------------------------|---------------------------------------------------------------------|--------|
| **Utiliser une XDimension trop petite** | Les barres deviennent plus fines que la résolution minimale du scanner, entraînant des erreurs de lecture. | Commencez avec `Pixels = 4` et testez sur l'imprimante cible ; augmentez si nécessaire. |
| **Enregistrer dans un dossier en lecture seule** | `Save` lève une `UnauthorizedAccessException`.                     | Assurez-vous que `outputDir` pointe vers un emplacement accessible en écriture, ou utilisez `Environment.GetFolderPath(Environment.SpecialFolder.Desktop)`. |
| **Négliger de disposer le générateur** | Les images volumineuses peuvent retenir des ressources non gérées. | Enveloppez le générateur dans une instruction `using` ou appelez `Dispose()` après `Save`. |
| **Mélanger plusieurs formats de code-barres dans une même image** | Certaines imprimantes attendent une seule symbologie par étiquette. | Générez chaque code-barres séparément et combinez-les avec une bibliothèque graphique si nécessaire. |

---

## Vérifier les codes-barres générés

Pour confirmer que les codes-barres sont valides, vous pouvez utiliser le site gratuit **Aspose.BarCode Demo** ou toute application de scanner de code-barres standard. Chargez les fichiers PNG et scannez‑les ; la valeur décodée doit être `123456` pour les exemples Planet et RM4SCC.

---

## Conclusion

Dans ce tutoriel, vous avez appris à **créer des fichiers d'image de code-barres postal** en C# avec Aspose.BarCode. Vous avez vu comment **générer des images de code-barres planet** avec des barres remplies et vides, comment produire un code-barres RM4SCC, et comment personnaliser la taille, le format et la gestion des erreurs. Avec le code complet et exécutable, vous pouvez désormais intégrer la génération de codes-barres postaux dans n'importe quelle application .NET.

**Étapes suivantes**

* Explorez d'autres symbologies postales telles que `EncodeTypes.USPSIntelligentMail` (mot‑clé secondaire : postal barcode PNG).

## Que devriez‑vous apprendre ensuite ?

Les tutoriels suivants couvrent des sujets étroitement liés qui s'appuient sur les techniques démontrées dans ce guide. Chaque ressource comprend des exemples de code complets et fonctionnels avec des explications étape par étape pour vous aider à maîtriser des fonctionnalités supplémentaires de l'API et explorer des approches d'implémentation alternatives dans vos propres projets.

- [Create Postal Barcode Image in C# – Full Step‑by‑Step Guide](/barcode/english/python-java/general/create-postal-barcode-image-in-c-full-step-by-step-guide/)
- [Generate Postal Barcode in C# – Complete Guide with Planet Barcode](/barcode/english/python-java/general/generate-postal-barcode-in-c-complete-guide-with-planet-barc/)
- [How to generate postal barcode in C# with Aspose.BarCode](/barcode/english/python-java/general/how-to-generate-postal-barcode-in-c-with-aspose-barcode/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}