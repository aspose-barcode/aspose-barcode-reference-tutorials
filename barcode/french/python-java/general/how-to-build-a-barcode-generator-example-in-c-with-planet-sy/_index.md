---
category: general
date: 2026-10-05
description: Exemple de générateur de code‑barres en C# qui vous montre comment générer
  un code‑barres Planet et créer une image de code‑barres en C#. Suivez ce guide étape
  par étape.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- barcode generator example
- generate planet barcode
- create barcode image c#
language: fr
lastmod: 2026-10-05
og_description: Exemple de générateur de code‑barres en C# qui vous montre comment
  générer un code‑barres Planet et créer une image de code‑barres en C#. Obtenez une
  solution complète et exécutable.
og_image_alt: Screenshot of a generated Planet barcode image created by a C# barcode
  generator example
og_title: Exemple de générateur de code-barres en C# – générez rapidement le code-barres
  Planet
schemas:
- author: Aspose
  dateModified: '2026-10-05'
  description: barcode generator example in C# that shows you how to generate planet
    barcode and create barcode image c#. Follow this step‑by‑step guide.
  headline: How to build a barcode generator example in C# with Planet symbology
  type: TechArticle
tags:
- barcode
- C#
- Aspose.BarCode
title: Comment créer un exemple de générateur de code-barres en C# avec la symbologie
  Planet
url: /fr/python-java/general/how-to-build-a-barcode-generator-example-in-c-with-planet-sy/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Exemple de générateur de code‑barres en C# – générer un code‑barres Planet et créer une image de code‑barres

Si vous avez besoin d’un **exemple de générateur de code‑barres** en C#, ce guide vous montre exactement comment générer un code‑barres Planet et créer une image de code‑barres c# en quelques lignes de code seulement. Vous verrez une solution complète, prête à l’emploi, que vous pouvez intégrer dans n’importe quel projet .NET.

Un code‑barres Planet est utilisé par les services postaux pour encoder les informations de routage. À la fin de ce tutoriel, vous comprendrez pourquoi la bibliothèque détermine automatiquement la hauteur du code‑barres, comment contrôler la dimension X, et comment enregistrer le résultat sous forme de fichier PNG. Aucun outil externe n’est requis — seulement le package Aspose.BarCode for .NET et un environnement de développement .NET.

## Prérequis

Avant de commencer, assurez‑vous d’avoir :

* .NET 6.0 SDK ou version ultérieure installé  
* Visual Studio 2022 (ou tout IDE supportant .NET)  
* Le package NuGet **Aspose.BarCode for .NET** (`Aspose.BarCode`)  

Vous pouvez installer le package depuis la ligne de commande :

```bash
dotnet add package Aspose.BarCode
```

## Étape 1 : Initialiser le générateur de code‑barres pour l’encodage Planet

La première étape dans tout **exemple de générateur de code‑barres** consiste à créer une instance `BarcodeGenerator` et à spécifier le type d’encodage. Pour un code‑barres Planet, utilisez `EncodeTypes.Planet` et transmettez la chaîne de données que vous souhaitez encoder.

```csharp
using Aspose.BarCode.Generation;

// Create a Planet barcode generator with the data to encode
BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Planet, "123456");
```

**Pourquoi c’est important :** L’énumération `EncodeTypes.Planet` indique à la bibliothèque d’utiliser la symbologie Planet, qui possède un motif de modules fixe requis par les normes postales. Fournir les données (`"123456"` dans ce cas) garantit que le code‑barres contient le bon code de routage numérique.

## Étape 2 : Configurer la dimension X (largeur du module) en pixels

La dimension X contrôle la largeur de chaque module individuel (la plus petite barre). La modifier change la taille globale du code‑barres sans affecter la lisibilité.

```csharp
// Set the X dimension (module width) to 4 pixels
generator.Parameters.Barcode.XDimension.Pixels = 4;
```

**Pourquoi c’est important :** Une dimension X plus grande produit un code‑barres plus volumineux, ce qui peut être utile lors de l’impression sur de grandes enveloppes. La bibliothèque ajuste automatiquement la hauteur pour maintenir le bon rapport d’aspect des codes‑barres Planet.

## Étape 3 : Enregistrer l’image du code‑barres sur le disque

Enfin, vous enregistrez l’image générée. La bibliothèque détermine la hauteur optimale, vous n’avez donc qu’à spécifier le chemin de sortie et le format.

```csharp
using Aspose.BarCode;

// Define the output file path
string outputFile = @"C:\Barcodes\PlanetAutoHeight.png";

// Save the barcode as a PNG image
generator.Save(outputFile, BarCodeImageFormat.Png);
```

**Pourquoi c’est important :** Enregistrer au format PNG préserve les bords nets du code‑barres, ce qui est essentiel pour un scan fiable. La méthode `Save` prend également en charge d’autres formats (JPEG, BMP, TIFF) si vous avez besoin d’un autre type de sortie.

### Résultat attendu

Après l’exécution du code, vous trouverez un fichier nommé **PlanetAutoHeight.png** dans `C:\Barcodes`. L’image ressemblera à l’illustration ci‑dessous (texte alternatif : *exemple de générateur de code‑barres montrant un code‑barres Planet*).

![Planet barcode generated by the C# example](/images/planet-barcode-example.png){alt="exemple de générateur de code‑barres montrant un code‑barres Planet"}

## Étape 4 : Optionnel – personnaliser les couleurs de premier plan et d’arrière‑plan

Si votre application nécessite un style visuel différent, vous pouvez modifier les couleurs du code‑barres avant l’enregistrement.

```csharp
// Set foreground (bars) to dark blue and background to light gray
generator.Parameters.Barcode.BarColor = System.Drawing.Color.DarkBlue;
generator.Parameters.Barcode.BackgroundColor = System.Drawing.Color.LightGray;

// Save the customized image
generator.Save(@"C:\Barcodes\PlanetCustomColors.png", BarCodeImageFormat.Png);
```

**Astuce :** Testez toujours le code‑barres personnalisé avec un vrai scanner pour confirmer que les changements de couleur n’affectent pas la lisibilité.

## Étape 5 : Gestion des erreurs et validation

La bibliothèque Aspose.BarCode lève une `ArgumentException` si les données ne respectent pas les exigences de la symbologie Planet (par ex., caractères non numériques). Enveloppez le code de génération dans un bloc try‑catch afin de fournir un retour clair.

```csharp
try
{
    BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Planet, "ABC123");
    generator.Save(@"C:\Barcodes\InvalidPlanet.png", BarCodeImageFormat.Png);
}
catch (ArgumentException ex)
{
    Console.WriteLine($"Invalid data for Planet barcode: {ex.Message}");
}
```

**Pourquoi c’est important :** Les codes‑barres Planet n’acceptent que des données numériques de longueurs spécifiques. Une validation adéquate évite les échecs d’exécution et fait gagner du temps lors des tests d’intégration.

## Exemple complet, exécutable

Assembler toutes les étapes vous donne un programme autonome que vous pouvez copier, coller et exécuter.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Program
{
    static void Main()
    {
        // Step 1: Initialize the generator with Planet encoding
        BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Planet, "123456");

        // Step 2: Set the X dimension (module width) to 4 pixels
        generator.Parameters.Barcode.XDimension.Pixels = 4;

        // Optional: customize colors (comment out if not needed)
        // generator.Parameters.Barcode.BarColor = System.Drawing.Color.DarkBlue;
        // generator.Parameters.Barcode.BackgroundColor = System.Drawing.Color.LightGray;

        // Step 3: Save the barcode image
        string outputFile = @"C:\Barcodes\PlanetAutoHeight.png";
        generator.Save(outputFile, BarCodeImageFormat.Png);

        Console.WriteLine($"Planet barcode saved to {outputFile}");
    }
}
```

Compiler et exécuter le programme :

```bash
dotnet run
```

Vous devriez voir le message console confirmant l’emplacement du fichier, et le fichier PNG contiendra le code‑barres Planet généré.

## Variations courantes et cas limites

| Variation | Comment implémenter | Quand l’utiliser |
|-----------|---------------------|------------------|
| **Longueur de données différente** | Modifier le deuxième argument dans `new BarcodeGenerator(EncodeTypes.Planet, "987654321")` | Services postaux nécessitant des numéros de routage plus longs |
| **Résolution supérieure** | Définir `generator.Parameters.ImageResolution = 300;` avant `Save` | Impression sur des imprimantes haute‑dpi |
| **Format d’image différent** | Utiliser `BarCodeImageFormat.Jpeg` ou `BarCodeImageFormat.Tiff` | Lorsque le PNG n’est pas adapté à votre flux de travail |
| **Nom de fichier dynamique** | `string outputFile = Path.Combine(folder, $"Planet_{DateTime.Now:yyyyMMdd_HHmmss}.png");` | Traitement par lots de plusieurs codes‑barres |

## Conseils d’expert pour un exemple de générateur de code‑barres robuste

* **Réutilisez l’instance du générateur** lorsque vous créez de nombreux codes‑barres avec les mêmes paramètres ; ne changez que `EncodeTypes` ou la chaîne de données pour améliorer les performances.  
* **Validez les entrées** avant de les transmettre à `BarcodeGenerator`. Une expression régulière simple comme `^\d{6,9}$` garantit que les données respectent les exigences Planet.  
* **Libérez les ressources** si vous générez des milliers d’images dans un service de longue durée. `BarcodeGenerator` implémente `IDisposable`, donc encapsulez‑le dans un bloc `using` lorsque c’est approprié.

```csharp
using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Planet, data))
{
    // configure and save...
}
```

## Conclusion

Cet **exemple de générateur de code‑barres** montre comment **générer un code‑barres Planet** et **créer une image de code‑barres c#** en utilisant Aspose.BarCode for .NET. Vous avez appris à initialiser le générateur, définir la dimension X, personnaliser éventuellement les couleurs, gérer les erreurs de validation et enregistrer le résultat sous forme de fichier PNG. Avec le code source complet fourni, vous pouvez intégrer la génération de codes‑barres Planet dans n’importe quelle application C# immédiatement.

Ensuite, vous pourrez explorer d’autres symbologies telles que QR, Code128 ou DataMatrix — chacune suit le même schéma de création d’un `BarcodeGenerator`, de configuration des paramètres et d’appel à `Save`. Les mêmes principes s’appliquent, ce qui facilite l’extension de vos capacités de génération de codes‑barres à un large éventail de scénarios métier. Bon codage !


## Que devriez‑vous apprendre ensuite ?


Les tutoriels suivants couvrent des sujets étroitement liés qui s’appuient sur les techniques démontrées dans ce guide. Chaque ressource inclut des exemples de code complets et fonctionnels avec des explications étape par étape pour vous aider à maîtriser des fonctionnalités API supplémentaires et à explorer des approches d’implémentation alternatives dans vos propres projets.

- [create planet barcode image – Step‑by‑Step Guide](/barcode/english/python-java/general/create-planet-barcode-image-step-by-step-guide/)
- [Barcode generator C# – create Planet barcode and RM4SCC example](/barcode/english/python-java/general/barcode-generator-c-create-planet-barcode-and-rm4scc-example/)
- [Create barcode image C# with barcode generator example](/barcode/english/python-java/general/create-barcode-image-c-with-barcode-generator-example/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}