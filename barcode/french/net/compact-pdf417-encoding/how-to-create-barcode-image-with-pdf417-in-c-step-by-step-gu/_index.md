---
category: general
date: 2026-11-20
description: Créer une image de code‑barres en C# avec Aspose.BarCode. Apprenez à
  générer un code‑barres PDF417 avec une mise en page personnalisée et à l’enregistrer
  au format PNG.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode image
- generate pdf417 barcode
- how to generate pdf417
language: fr
lastmod: 2026-11-20
og_description: Créer une image de code-barres en C# avec Aspose.BarCode. Ce guide
  montre comment générer un code-barres PDF417, personnaliser la mise en page et exporter
  en PNG.
og_image_alt: Screenshot of generated barcode image created with PDF417 using C#
og_title: Créer une image de code-barres PDF417 en C# – tutoriel complet
schemas:
- author: Aspose
  dateModified: '2026-11-20'
  description: Create barcode image in C# using Aspose.BarCode. Learn how to generate
    PDF417 barcode with a custom layout and save it as PNG.
  headline: How to create barcode image with PDF417 in C# – step‑by‑step guide
  type: TechArticle
- description: Create barcode image in C# using Aspose.BarCode. Learn how to generate
    PDF417 barcode with a custom layout and save it as PNG.
  name: How to create barcode image with PDF417 in C# – step‑by‑step guide
  steps:
  - name: Why this code works
    text: '* **`BarcodeGenerator`** is the entry point for all barcode types. By passing
      `EncodeTypes.Pdf417` you tell the library to produce a PDF417 symbol. * **Columns
      and rows** are the primary levers for layout. Fewer columns produce a taller
      barcode; more columns make it wider. Adjust these values to fit'
  - name: Adjusting data length
    text: 'PDF417 can encode up to 1,850 characters. If you need to encode longer
      strings, consider splitting the data across multiple barcodes or using the **compact
      mode**:'
  - name: Controlling image size
    text: 'The default image size is calculated from the module size (the smallest
      square in the barcode). You can explicitly set the DPI or scale the image after
      generation:'
  - name: Handling special characters
    text: 'PDF417 supports the full ASCII set. If your data contains Unicode characters,
      ensure you encode the string as UTF‑8:'
  type: HowTo
tags:
- barcode
- PDF417
- C#
title: Comment créer une image de code‑barres PDF417 en C# – guide étape par étape
url: /fr/net/compact-pdf417-encoding/how-to-create-barcode-image-with-pdf417-in-c-step-by-step-gu/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Comment créer une image de code-barres avec PDF417 en C# – guide étape par étape

Si vous devez **create barcode image** dans une application .NET, ce guide vous montre exactement **how to generate PDF417 barcode** avec une mise en page personnalisée et l’enregistrer en tant que fichier PNG. Vous verrez le code complet et exécutable, comprendrez pourquoi chaque paramètre est important, et apprendrez les pièges courants afin que votre code-barres fonctionne de manière fiable en production.

Dans ce tutoriel vous allez :

* Initialiser le générateur Aspose.BarCode pour PDF417.  
* Configurer le nombre de colonnes et de lignes pour contrôler la forme du code‑barres.  
* Exporter le résultat en image PNG de haute qualité.  
* Explorer les paramètres optionnels pour la correction d’erreur et la longueur des données.

Le seul prérequis est un SDK .NET récent (.NET 6 ou ultérieur) et une licence ou un essai gratuit d’**Aspose.BarCode for .NET**.

---

## Prérequis et configuration

Avant de commencer, assurez-vous d'avoir :

| Exigence | Pourquoi c'est important |
|----------|---------------------------|
| .NET 6 SDK ou plus récent | Fournit le runtime pour l'application console C#. |
| Visual Studio 2022 (ou VS Code) | Vous fournit un IDE avec IntelliSense pour l'API Aspose. |
| Aspose.BarCode for .NET package NuGet | Fournit `BarcodeGenerator`, `EncodeTypes` et les assistants d'exportation d'image. |
| Permission d'écriture sur le dossier de sortie | Le générateur écrit le fichier PNG sur le disque. |

Vous pouvez ajouter le package NuGet avec la commande suivante :

```bash
dotnet add package Aspose.BarCode
```

---

## Étape 1 : Créer un nouveau projet console

Tout d'abord, créez une application console simple qui hébergera la logique de génération du code‑barres.

```csharp
using System;
using Aspose.BarCode.Generation;

namespace Pdf417Demo
{
    class Program
    {
        static void Main(string[] args)
        {
            // The full barcode generation flow is encapsulated in GeneratePdf417().
            GeneratePdf417();
            Console.WriteLine("Barcode image created successfully.");
        }

        // -----------------------------------------------------------------
        // Generates a PDF417 barcode with a custom layout and saves it as PNG.
        // -----------------------------------------------------------------
        static void GeneratePdf417()
        {
            // -------------------------------------------------------------
            // Step 2: Initialize the barcode generator for PDF417 with text.
            // -------------------------------------------------------------
            var generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Sample data for PDF417 barcode");

            // -------------------------------------------------------------
            // Step 3: Define a custom layout – set the number of columns and rows.
            // -------------------------------------------------------------
            generator.Parameters.Barcode.Pdf417.Columns = 4; // Controls horizontal density.
            generator.Parameters.Barcode.Pdf417.Rows = 9;    // Controls vertical density.

            // Optional: increase error correction level for noisy environments.
            // Values: 0 (no correction) to 8 (maximum correction).
            generator.Parameters.Barcode.Pdf417.ErrorCorrectionLevel = 2;

            // -------------------------------------------------------------
            // Step 4: Save the generated barcode as a PNG image.
            // -------------------------------------------------------------
            string outputPath = System.IO.Path.Combine(
                Environment.CurrentDirectory, "CustomPdf417.png");
            generator.Save(outputPath, BarCodeImageFormat.Png);
        }
    }
}
```

### Pourquoi ce code fonctionne

* **`BarcodeGenerator`** est le point d'entrée pour tous les types de code‑barres. En passant `EncodeTypes.Pdf417`, vous indiquez à la bibliothèque de produire un symbole PDF417.  
* **Colonnes et lignes** sont les principaux leviers pour la mise en page. Moins de colonnes produisent un code‑barres plus haut ; plus de colonnes le rendent plus large. Ajustez ces valeurs pour correspondre à l'espace où l'image sera affichée (par ex., une imprimante d'étiquettes vs. une page web).  
* **Correction d'erreur** améliore la fiabilité du scan lorsque le code‑barres peut être taché ou imprimé sur un support de mauvaise qualité. Le niveau par défaut est 0 ; l'augmenter légèrement (2–4) constitue un bon compromis entre taille et robustesse.  
* **`Save`** écrit l'image sur le disque au format PNG, ce qui préserve les bords nets et fonctionne sur tous les navigateurs et appareils mobiles.

Lorsque vous exécutez le programme (`dotnet run`), il crée `CustomPdf417.png` dans le dossier du projet. Le PNG ressemble à ceci :

![Generated PDF417 barcode image](https://example.com/images/pdf417-sample.png "Screenshot of generated barcode image created with PDF417 using C#")

*Texte alternatif :* **create barcode image** – code‑barres PDF417 généré en C# et enregistré en PNG.

---

## Étape 2 : Affiner le code‑barres pour des scénarios réels

### Ajustement de la longueur des données

PDF417 peut encoder jusqu'à 1 850 caractères. Si vous devez encoder des chaînes plus longues, envisagez de diviser les données sur plusieurs codes‑barres ou d'utiliser le **mode compact** :

```csharp
generator.Parameters.Barcode.Pdf417.CompactMode = true;
```

Le mode compact réduit le nombre de lignes mais peut augmenter la densité visuelle, donc testez avec votre lecteur.

### Contrôle de la taille de l'image

La taille d'image par défaut est calculée à partir de la taille du module (le plus petit carré du code‑barres). Vous pouvez définir explicitement le DPI ou redimensionner l'image après génération :

```csharp
generator.Parameters.ImageResolution = new Resolution(300); // 300 DPI for printing.
```

Ou, après l'enregistrement, redimensionnez avec System.Drawing si vous avez besoin d'une vignette.

### Gestion des caractères spéciaux

PDF417 prend en charge l'ensemble complet ASCII. Si vos données contiennent des caractères Unicode, assurez‑vous d'encoder la chaîne en UTF‑8 :

```csharp
var generator = new BarcodeGenerator(EncodeTypes.Pdf417, System.Text.Encoding.UTF8.GetString(bytes));
```

---

## Étape 3 : Pièges courants et comment les éviter

| Piège | Symptôme | Solution |
|-------|----------|----------|
| Trop de colonnes pour les données fournies | Le code‑barres apparaît tronqué ou lève une exception. | Réduisez `Columns` ou laissez la bibliothèque ajuster automatiquement en omettant ce paramètre. |
| Correction d'erreur faible sur une imprimante bruyante | Les lecteurs échouent à lire le code‑barres de façon intermittente. | Augmentez `ErrorCorrectionLevel` à au moins 2. |
| Enregistrement dans un répertoire en lecture seule | `UnauthorizedAccessException` à l'exécution. | Utilisez un dossier accessible en écriture comme `Environment.CurrentDirectory` ou `Path.GetTempPath()`. |
| Utilisation d'une version obsolète d'Aspose.BarCode | Propriétés manquantes comme `CompactMode`. | Mettez à jour le package NuGet vers la dernière version stable. |

---

## Étape 4 : Vérifier le résultat

Pour confirmer que le code‑barres a été généré correctement, vous pouvez :

1. Ouvrez `CustomPdf417.png` dans n'importe quel visualiseur d'images – le code‑barres doit être net, avec des modules noirs clairs sur un fond blanc.  
2. Utilisez une application gratuite de lecture PDF417 (disponible sur iOS et Android) pour scanner l'image. L'application doit afficher **« Sample data for PDF417 barcode »**.  
3. (Optionnel) Chargez l'image dans un test unitaire en utilisant `System.Drawing.Bitmap` et vérifiez que le pixel à `(0,0)` est noir, confirmant que l'image n'est pas vide.

```csharp
using System.Drawing;

Bitmap bmp = new Bitmap("CustomPdf417.png");
bool topLeftIsBlack = bmp.GetPixel(0, 0).R == 0;
Console.WriteLine($"Top‑left pixel black? {topLeftIsBlack}");
```

Si l'assertion réussit, vous avez réussi à **create barcode image** et **generate PDF417 barcode** de manière programmatique.

---

## Conclusion

Vous savez maintenant comment **create barcode image** en C# en **generating PDF417 barcode** avec une mise en page personnalisée, en ajustant la correction d’erreur et en exportant en PNG. L'exemple complet montre chaque étape requise — de l'initialisation de `BarcodeGenerator` à l'enregistrement de l'image finale—afin que vous puissiez le copier, le coller et l'exécuter dans votre propre projet.

Ensuite, vous pourriez explorer :

* **Intégrer le PNG dans une API web** afin que les clients puissent demander des codes‑barres à la demande (`generate pdf417` en tant que service).  
* **Génération par lots** pour de grands ensembles de données—boucler sur une liste de chaînes et stocker chaque PNG dans une base de données.  
* **Formats de sortie alternatifs** (SVG, JPEG) en changeant `BarCodeImageFormat`.

N'hésitez pas à expérimenter avec les rapports colonnes/lignes, les niveaux de correction d’erreur et la résolution d’image pour répondre exactement aux exigences de votre matériel de lecture ou de votre conception UI. Bon codage !

## Que devriez‑vous apprendre ensuite ?

Les tutoriels suivants couvrent des sujets étroitement liés qui s’appuient sur les techniques démontrées dans ce guide. Chaque ressource inclut des exemples de code complets et fonctionnels avec des explications étape par étape pour vous aider à maîtriser des fonctionnalités API supplémentaires et explorer des approches d’implémentation alternatives dans vos propres projets.

- [Comment créer une image de code‑barres PDF417 en C# – guide complet](/barcode/english/net/compact-pdf417-encoding/generate-pdf417-barcode-in-c-complete-guide/)
- [Comment créer une image de code‑barres PDF417 en C# avec les options Macro PDF417](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-image-in-c-with-macro-pdf417-op/)
- [Comment créer un code‑barres micro PDF417 et générer un PNG en C#](/barcode/english/net/compact-pdf417-encoding/how-to-create-micro-pdf417-barcode-and-generate-png-in-c/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}