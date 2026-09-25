---
category: general
date: 2026-08-15
description: Image de code‑barres PNG en C# – apprenez à générer des codes‑barres
  postaux, créer un code‑barres Planet et modifier la hauteur du code‑barres avec
  un générateur simple.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- barcode image png
- barcode generator c#
- generate postal barcode
- create planet barcode
- change barcode height
language: fr
lastmod: 2026-08-15
og_description: Le tutoriel « Image de code‑barres PNG en C# » montre comment générer
  des codes‑barres postaux, créer un code‑barres Planet et modifier la hauteur du
  code‑barres à l’aide de l’API BarcodeGenerator.
og_image_alt: Screenshot of generated PNG barcode with custom height using C# BarcodeGenerator
og_title: Image de code-barres PNG en C# – générer et ajuster les codes-barres
schemas:
- author: Aspose
  dateModified: '2026-08-15'
  description: Barcode image PNG in C# – learn how to generate postal barcodes, create
    a Planet barcode, and change barcode height with a simple generator.
  headline: Barcode image PNG in C# generate barcodes, change height
  type: TechArticle
tags:
- barcode
- C#
- PNG
- postal
- generator
title: 'Image de code-barres PNG en C# : générer des codes-barres, modifier la hauteur'
url: /fr/python-java/general/barcode-image-png-in-c-generate-barcodes-change-height/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Image de code-barres PNG en C# – générer des codes-barres, modifier la hauteur

Si vous avez besoin d’une **barcode image PNG** en C#, ce guide vous accompagne tout au long du processus complet. Vous apprendrez à générer des codes-barres postaux, créer un code-barres Planet, et modifier la hauteur du code-barres sans quitter votre IDE.

Générer des codes-barres PNG fiables est une exigence courante pour les étiquettes d’expédition, les systèmes d’inventaire et les solutions de mailing automatisées. À la fin de ce tutoriel, vous disposerez d’un extrait de code réutilisable qui produit des fichiers PNG de haute qualité pour les formats Planet et RM4SCC, et vous comprendrez comment ajuster la hauteur des barres pour répondre aux spécifications postales.

## Ce dont vous aurez besoin

- .NET 6+ ou .NET Framework 4.7.2 (l’API BarcodeGenerator fonctionne avec n’importe quel runtime .NET récent)  
- Une référence au package NuGet **Aspose.BarCode for .NET** (ou toute bibliothèque compatible qui fournit `BarcodeGenerator`, `EncodeTypes` et `BarCodeImageFormat`)  
- Une connaissance de base de la syntaxe C# et des opérations d’E/S de fichiers  

Aucun outil supplémentaire n’est requis ; le code s’exécute dans Visual Studio, Rider ou le CLI `dotnet`.

## Image de code-barres PNG – génération de base

La première étape consiste à créer une **barcode image PNG** avec les dimensions par défaut. Cela établit le fichier de base que vous pourrez personnaliser ultérieurement.

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;

// Define the output folder (replace with your own path)
string outputFolder = @"C:\Barcodes";

// Ensure the folder exists
Directory.CreateDirectory(outputFolder);

// 1️⃣ Create a Planet barcode generator with default height
BarcodeGenerator planetGenerator = new BarcodeGenerator(EncodeTypes.Planet, "123456");

// Set the module width (X‑dimension) to 4 pixels – this defines the thin bar size
planetGenerator.Parameters.Barcode.XDimension.Pixels = 4;

// Save the image as PNG; this is the first **barcode image PNG** you’ll produce
planetGenerator.Save(Path.Combine(outputFolder, "PlanetBarHeightDefault.png"),
                     BarCodeImageFormat.Png);
```

**Pourquoi cela fonctionne :**  
- `EncodeTypes.Planet` indique au générateur d’utiliser la symbologie Planet, requise par de nombreux services postaux.  
- `XDimension.Pixels` contrôle la largeur de la plus petite barre ; une valeur de 4 px donne un code-barres lisible aux tailles d’étiquette typiques.  
- La méthode `Save` écrit un fichier **barcode image PNG** sur le disque, en conservant toutes les informations vectorielles sous forme de pixels raster.

## Modifier la hauteur du code-barres – personnaliser le poids visuel

Les directives postales exigent souvent une hauteur de barre spécifique. L’extrait suivant montre comment définir une hauteur personnalisée de 100 pixels pour le même code-barres Planet.

```csharp
// 2️⃣ Apply a custom 100‑pixel bar height
planetGenerator.Parameters.Barcode.BarHeight.Pixels = 100;

// Overwrite or save as a new file to keep both versions
planetGenerator.Save(Path.Combine(outputFolder, "PlanetBarHeight100.png"),
                     BarCodeImageFormat.Png);
```

**Pourquoi modifier la hauteur :**  
Une barre plus haute améliore la fiabilité du scan sur les imprimantes basse résolution, tandis qu’une barre plus courte libère de l’espace sur l’étiquette. La propriété `BarHeight.Pixels` vous permet d’ajuster finement cet attribut sans affecter la dimension X.

## Générer un code-barres postal – créer un exemple RM4SCC

Le format RM4SCC est un autre code-barres postal couramment utilisé au Royaume‑Uni. Les étapes de génération reflètent l’exemple Planet, renforçant le modèle **barcode generator c#**.

```csharp
// 3️⃣ Create an RM4SCC barcode generator with default height
BarcodeGenerator rm4sccGenerator = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");

// Keep the same module width for consistency
rm4sccGenerator.Parameters.Barcode.XDimension.Pixels = 4;

// Save the default‑height PNG
rm4sccGenerator.Save(Path.Combine(outputFolder, "RM4SCCBarHeightDefault.png"),
                     BarCodeImageFormat.Png);
```

## Modifier la hauteur du code-barres – variante RM4SCC

Tout comme pour le code-barres Planet, vous pouvez ajuster la hauteur des barres RM4SCC. Le code ci‑dessous fixe la hauteur à 100 px, produisant un second **barcode image PNG** pour la même chaîne de données.

```csharp
// 4️⃣ Set a custom 100‑pixel bar height for RM4SCC
rm4sccGenerator.Parameters.Barcode.BarHeight.Pixels = 100;

// Save the customized PNG
rm4sccGenerator.Save(Path.Combine(outputFolder, "RM4SCCBarHeight100.png"),
                     BarCodeImageFormat.Png);
```

## Exemple complet, exécutable

Assembler toutes les étapes donne un programme autonome qui crée quatre fichiers PNG :

```csharp
using System;
using System.IO;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Program
{
    static void Main()
    {
        string outputFolder = @"C:\Barcodes";
        Directory.CreateDirectory(outputFolder);

        // Planet barcode – default height
        var planet = new BarcodeGenerator(EncodeTypes.Planet, "123456");
        planet.Parameters.Barcode.XDimension.Pixels = 4;
        planet.Save(Path.Combine(outputFolder, "PlanetBarHeightDefault.png"),
                    BarCodeImageFormat.Png);

        // Planet barcode – custom 100‑pixel height
        planet.Parameters.Barcode.BarHeight.Pixels = 100;
        planet.Save(Path.Combine(outputFolder, "PlanetBarHeight100.png"),
                    BarCodeImageFormat.Png);

        // RM4SCC barcode – default height
        var rm4scc = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");
        rm4scc.Parameters.Barcode.XDimension.Pixels = 4;
        rm4scc.Save(Path.Combine(outputFolder, "RM4SCCBarHeightDefault.png"),
                    BarCodeImageFormat.Png);

        // RM4SCC barcode – custom 100‑pixel height
        rm4scc.Parameters.Barcode.BarHeight.Pixels = 100;
        rm4scc.Save(Path.Combine(outputFolder, "RM4SCCBarHeight100.png"),
                    BarCodeImageFormat.Png);

        Console.WriteLine("All barcode PNG files have been generated in " +


## Que devriez‑vous apprendre ensuite ?

Les tutoriels suivants couvrent des sujets étroitement liés qui s’appuient sur les techniques démontrées dans ce guide. Chaque ressource comprend des exemples de code complets et fonctionnels avec des explications pas à pas pour vous aider à maîtriser des fonctionnalités API supplémentaires et explorer des approches d’implémentation alternatives dans vos propres projets.

- [Créer un code-barres hauteur personnalisée – Codes-barres unidimensionnels](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-barcode-height-adjustment/)
- [Créer un code-barres PNG – Ratio d’aspect DataMatrix – Aspose.BarCode](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-aspect-ratio-customization/)
- [Créer une image de code-barres C# – Exemple GS1 DataMatrix](/barcode/english/net/gs1-barcode-encoding/gs1-datamatrix-example/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}