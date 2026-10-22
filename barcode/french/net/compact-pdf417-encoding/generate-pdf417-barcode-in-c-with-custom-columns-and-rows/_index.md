---
category: general
date: 2026-10-21
description: Générez rapidement un code‑barres PDF417 en C#. Apprenez à créer un code‑barres
  PDF417 avec une mise en page personnalisée, des colonnes, des lignes et une sortie
  PNG.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate pdf417 barcode
- how to generate pdf417 barcode
- pdf417 barcode layout
- barcode generator C#
- save barcode as PNG
language: fr
lastmod: 2026-10-21
og_description: Générez un code‑barres PDF417 en C#. Suivez ce tutoriel pour apprendre
  à créer un code‑barres PDF417 avec des colonnes, des lignes personnalisées et une
  sortie PNG.
og_image_alt: Screenshot showing a generated PDF417 barcode saved as a PNG file
og_title: Générer un code‑barres PDF417 en C# – guide complet étape par étape
schemas:
- author: Aspose
  dateModified: '2026-10-21'
  description: Generate pdf417 barcode quickly in C#. Learn how to generate pdf417
    barcode with custom layout, columns, rows, and PNG output.
  headline: Generate pdf417 barcode in C# with custom columns and rows
  type: TechArticle
- description: Generate pdf417 barcode quickly in C#. Learn how to generate pdf417
    barcode with custom layout, columns, rows, and PNG output.
  name: Generate pdf417 barcode in C# with custom columns and rows
  steps:
  - name: Open the PNG file in any image viewer.
    text: Open the PNG file in any image viewer.
  - name: Use a free PDF417 scanner app (e.g., ZXing, PDF417 Decoder) to scan the
      image.
    text: Use a free PDF417 scanner app (e.g., ZXing, PDF417 Decoder) to scan the
      image.
  - name: Confirm that the decoded text matches the original input.
    text: Confirm that the decoded text matches the original input.
  type: HowTo
tags:
- barcode
- pdf417
- C#
- image generation
title: Générer un code‑barres PDF417 en C# avec des colonnes et des lignes personnalisées
url: /fr/net/compact-pdf417-encoding/generate-pdf417-barcode-in-c-with-custom-columns-and-rows/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Générer un code‑barres pdf417 en C# – guide complet de programmation

Si vous avez besoin de **générer un code‑barres pdf417** dans une application .NET, ce guide vous montre comment le faire en quelques lignes de code. Vous verrez un exemple pratique qui configure le nombre de colonnes et de rangées, puis enregistre le résultat sous forme d’image PNG. La même approche fonctionne pour tout texte que vous souhaitez encoder, vous pouvez donc l’adapter aux factures, aux tickets ou aux cartes d’identité.

Générer un **code‑barres pdf417** donne souvent l’impression d’être une tâche distincte du reste de votre base de code. À la fin de ce tutoriel, vous comprendrez pourquoi les paramètres de mise en page sont importants, comment contrôler la qualité de l’image, et quels appels de bibliothèque sont nécessaires pour **générer un code‑barres pdf417** de manière fiable.

## Ce dont vous avez besoin

* .NET 6.0 SDK ou version ultérieure installé  
* Un IDE compatible C# (Visual Studio, VS Code, Rider, etc.)  
* Le package NuGet **Aspose.BarCode for .NET** (ou toute bibliothèque de codes‑barres compatible)  

Vous pouvez ajouter la bibliothèque avec la commande suivante :

```bash
dotnet add package Aspose.BarCode
```

La bibliothèque fournit la classe `BarcodeGenerator` utilisée tout au long de ce tutoriel.

## Étape 1 : Créer une instance de générateur de code‑barres

La première ligne crée un objet qui sait comment **générer un code‑barres pdf417**. Vous devez spécifier le type d’encodage (`EncodeTypes.Pdf417`) et le texte que vous souhaitez encoder.

```csharp
using Aspose.BarCode.Generation;

BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Sample Text");
```

*Pourquoi cette étape est importante* – Le `BarcodeGenerator` encapsule tous les paramètres du code‑barres. L’instancier avec le bon `EncodeTypes` indique au moteur d’utiliser la symbologie PDF417 au lieu de QR, Code128 ou d’autres formats.

## Étape 2 : Configurer la mise en page PDF417

PDF417 vous permet de contrôler le nombre de colonnes et de rangées, ce qui influence directement la taille et la densité du code‑barres. Ajuster ces valeurs est l’essentiel de **comment générer un code‑barres pdf417** avec une mise en page personnalisée.

```csharp
// Set the number of data columns (valid range: 2‑30)
generator.Parameters.Barcode.Pdf417.Columns = 4;

// Set the number of rows (up to 90 rows)
generator.Parameters.Barcode.Pdf417.Rows = 9;
```

*Pourquoi vous pourriez modifier ces valeurs* – Plus de colonnes réduisent la hauteur du code‑barres, tandis que plus de rangées augmentent la largeur. Choisissez des valeurs qui correspondent à l’appareil de lecture cible et à la zone d’impression disponible.

> **Astuce :** Si vous omettez les rangées, la bibliothèque calcule automatiquement le nombre optimal en fonction de la longueur des données. Définir explicitement les rangées est utile lorsque vous avez besoin d’une taille d’image fixe pour les mises en page UI.

## Étape 3 : Choisir un format d’image et enregistrer le fichier

Après avoir configuré la mise en page, vous pouvez rendre le code‑barres sous forme d’image. L’exemple ci‑dessous enregistre le code‑barres en fichier PNG, mais vous pouvez également choisir JPEG, BMP ou TIFF.

```csharp
using Aspose.BarCode;
using System.IO;

// Define the output path – replace with your actual directory
string outputPath = Path.Combine("C:\\Barcodes", "CustomLayout.png");

// Save the barcode image as PNG
generator.Save(outputPath, BarCodeImageFormat.Png);
```

Lorsque le code s’exécute, `CustomLayout.png` contiendra un **code‑barres pdf417** clair qui correspond aux paramètres de colonnes/rangées que vous avez fournis.

### Résultat attendu

L’ouverture de `CustomLayout.png` montre un code‑barres rectangulaire avec quatre colonnes de données et neuf rangées. Scanner l’image avec n’importe quel lecteur PDF417 renvoie le texte original **« Sample Text »**.

![Exemple de code‑barres PDF417 généré](generated-pdf417.png){: .center-image alt="Code‑barres PDF417 généré enregistré en fichier PNG"}

## Étape 4 : Exemple complet et exécutable

Ci‑dessous se trouve une application console autonome qui assemble toutes les pièces. Copiez le code dans un nouveau projet `.csproj` et exécutez‑le — aucun fichier supplémentaire n’est requis.

```csharp
using System;
using System.IO;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace Pdf417Demo
{
    class Program
    {
        static void Main()
        {
            // 1️⃣ Create the generator with the desired text
            BarcodeGenerator generator = new BarcodeGenerator(
                EncodeTypes.Pdf417,
                "Sample Text for PDF417 barcode");

            // 2️⃣ Configure layout – custom columns and rows
            generator.Parameters.Barcode.Pdf417.Columns = 4; // 2‑30
            generator.Parameters.Barcode.Pdf417.Rows = 9;    // up to 90

            // Optional: increase image resolution for sharper output
            generator.Parameters.ImageResolution = 300; // DPI

            // 3️⃣ Define the output location
            string folder = Path.Combine(Environment.CurrentDirectory, "output");
            Directory.CreateDirectory(folder);
            string filePath = Path.Combine(folder, "CustomLayout.png");

            // 4️⃣ Save as PNG
            generator.Save(filePath, BarCodeImageFormat.Png);

            Console.WriteLine($"PDF417 barcode generated at: {filePath}");
        }
    }
}
```

L’exécution du programme affiche une ligne de confirmation et crée le fichier PNG dans un sous‑dossier `output`. L’image peut être intégrée dans des rapports, imprimée sur des étiquettes, ou envoyée à un appareil mobile pour la numérisation.

## Variations courantes et cas limites

| Scénario | Ce qu’il faut changer | Pourquoi c’est important |
|----------|-----------------------|---------------------------|
| **Encoder une longue chaîne** | Augmenter `Rows` ou laisser la bibliothèque calculer automatiquement en omettant l’affectation de `Rows` | PDF417 peut contenir jusqu’à 1 850 caractères ; un nombre insuffisant de rangées entraîne une troncature |
| **Qualité visuelle supérieure** | Définir `generator.Parameters.ImageResolution` à 600 DPI | Utile pour l’impression sur des imprimantes haute résolution |
| **Format d’image différent** | Remplacer `BarCodeImageFormat.Png` par `Jpeg` ou `Tiff` | JPEG réduit la taille du fichier ; TIFF conserve les données sans perte pour l’archivage |
| **Ajouter une zone silencieuse** | `generator.Parameters.Barcode.XDimension = 2;` (ou ajuster `Margins`) | Les zones silencieuses améliorent la fiabilité du scanner dans les environnements bruyants |
| **Texte dynamique provenant de l’entrée utilisateur** | Remplacer la chaîne codée en dur par `Console.ReadLine()` | Permet la génération à l’exécution basée sur les données de l’utilisateur |

### Comment générer un code‑barres pdf417 dans une API web

Si vous devez exposer la génération de code‑barres via un point de terminaison ASP.NET Core, renvoyez l’image sous forme de tableau d’octets :

```csharp
[HttpGet("api/barcode/pdf417")]
public IActionResult GetPdf417([FromQuery] string data)
{
    var generator = new BarcodeGenerator(EncodeTypes.Pdf417, data);
    generator.Parameters.Barcode.Pdf417.Columns = 5;
    generator.Parameters.Barcode.Pdf417.Rows = 10;

    using var ms = new MemoryStream();
    generator.Save(ms, BarCodeImageFormat.Png);
    return File(ms.ToArray(), "image/png");
}
```

Cet extrait répond à **comment générer un code‑barres pdf417** à la volée sans écrire sur le disque, ce qui est idéal pour les micro‑services ou les back‑ends mobiles.

## Tester le code‑barres généré

Pour vérifier que le code‑barres a été créé correctement :

1. Ouvrez le fichier PNG dans n’importe quel visualiseur d’image.  
2. Utilisez une application de scanner PDF417 gratuite (par ex., ZXing, PDF417 Decoder) pour scanner l’image.  
3. Confirmez que le texte décodé correspond à l’entrée originale.

Si le scanner signale des erreurs, revérifiez les valeurs de colonnes/rangées et assurez‑vous que la résolution de l’image est suffisamment élevée pour votre appareil.

## Conclusion

Vous savez maintenant comment **générer un code‑barres pdf417** en C# avec un contrôle complet sur les colonnes, les rangées et le format de sortie. L’exemple complet montre l’ensemble du flux de travail — de la création du `BarcodeGenerator` à l’enregistrement d’un fichier PNG — afin que vous puissiez intégrer la création de codes‑barres dans n’importe quel projet .NET.

Ensuite, explorez des sujets connexes tels que l’optimisation de la **mise en page du code‑barres pdf417**, l’intégration de codes‑barres dans des rapports PDF, ou le décodage de codes‑barres sur des appareils mobiles. Ajuster les niveaux de correction d’erreurs et expérimenter différentes résolutions d’image vous aidera à affiner la solution pour votre cas d’utilisation spécifique. Bon codage !

## Que devriez‑vous apprendre ensuite ?

Les tutoriels suivants couvrent des sujets étroitement liés qui s’appuient sur les techniques démontrées dans ce guide. Chaque ressource inclut des exemples de code complets et fonctionnels avec des explications pas à pas pour vous aider à maîtriser des fonctionnalités d’API supplémentaires et explorer des approches d’implémentation alternatives dans vos propres projets.

- [Comment générer un code‑barres PDF417 en C# – guide étape par étape](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-step-by-step-guide/)
- [Comment enregistrer un code‑barres en C# – générer des codes‑barres PDF417](/barcode/english/net/compact-pdf417-encoding/how-to-save-barcode-in-c-generate-pdf417-barcodes/)
- [Comment générer un code‑barres PDF417 – guide complet de programmation](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-complete-programming-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}