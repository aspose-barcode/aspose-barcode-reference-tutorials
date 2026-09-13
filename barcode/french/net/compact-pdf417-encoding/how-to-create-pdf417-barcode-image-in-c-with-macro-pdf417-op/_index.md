---
category: general
date: 2026-09-13
description: Apprenez à créer une image de code‑barres PDF417 en C# en utilisant BarcodeGenerator
  et les options Macro PDF417. Code étape par étape, astuces et exemple complet.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create PDF417 barcode image
- macro PDF417 options
- BarcodeGenerator class
- C# barcode generation
- barcode image format
language: fr
lastmod: 2026-09-13
og_description: Créez une image de code‑barres PDF417 en C# avec BarcodeGenerator.
  Suivez ce tutoriel détaillé pour configurer les options Macro PDF417 et enregistrer
  un code‑barres PNG.
og_image_alt: Screenshot of a generated PDF417 barcode image created with C# code
og_title: Créer une image de code-barres PDF417 en C# – guide complet
schemas:
- author: Aspose
  dateModified: '2026-09-13'
  description: Learn how to create PDF417 barcode image in C# using BarcodeGenerator
    and Macro PDF417 options. Step‑by‑step code, tips, and full example.
  headline: How to create PDF417 barcode image in C# with Macro PDF417 options
  type: TechArticle
- description: Learn how to create PDF417 barcode image in C# using BarcodeGenerator
    and Macro PDF417 options. Step‑by‑step code, tips, and full example.
  name: How to create PDF417 barcode image in C# with Macro PDF417 options
  steps:
  - name: '**Create the generator** – instantiate `BarcodeGenerator` with `EncodeTypes.MacroPdf417`
      and the data you want to encode.'
    text: '**Create the generator** – instantiate `BarcodeGenerator` with `EncodeTypes.MacroPdf417`
      and the data you want to encode.'
  - name: '**Define the module size** – set `XDimension.Pixels` to control the physical
      width of each barcode element.'
    text: '**Define the module size** – set `XDimension.Pixels` to control the physical
      width of each barcode element.'
  - name: '**Configure Macro PDF417 options** – specify columns, file identifiers,
      segment numbers, and optional checksum.'
    text: '**Configure Macro PDF417 options** – specify columns, file identifiers,
      segment numbers, and optional checksum.'
  - name: '**Save the barcode** – write the generated image to disk using a supported
      **barcode image format** such as PNG.'
    text: '**Save the barcode** – write the generated image to disk using a supported
      **barcode image format** such as PNG.'
  - name: Create a new .NET 6 (or later) console project.
    text: Create a new .NET 6 (or later) console project.
  - name: Add the Aspose.BarCode NuGet package (`dotnet add package Aspose.BarCode`).
    text: Add the Aspose.BarCode NuGet package (`dotnet add package Aspose.BarCode`).
  - name: Replace the generated `Program.cs` with the code above.
    text: Replace the generated `Program.cs` with the code above.
  - name: Adjust `outputPath` to a folder you have write access to.
    text: Adjust `outputPath` to a folder you have write access to.
  - name: Build and run – the console will confirm the image location.
    text: Build and run – the console will confirm the image location.
  type: HowTo
tags:
- PDF417
- C#
- Barcode
title: Comment créer une image de code‑barres PDF417 en C# avec les options Macro
  PDF417
url: /fr/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-image-in-c-with-macro-pdf417-op/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Comment créer une image de code‑barres PDF417 en C# avec les options Macro PDF417

Si vous devez **créer une image de code‑barres PDF417** en C#, ce guide vous montre exactement comment le faire en utilisant la **classe BarcodeGenerator**. Que vous construisiez un système de suivi de documents ou que vous codiez de gros fichiers, les instructions pas à pas ci‑dessous couvrent tout, de la configuration des options Macro PDF417 à l’enregistrement du PNG final.

Générer un code‑barres est simple une fois que vous comprenez les paramètres clés. Dans ce tutoriel, vous apprendrez à :

* Initialiser un `BarcodeGenerator` pour **Macro PDF417**.  
* Ajuster la taille du module du code‑barres (`XDimension`).  
* Configurer les paramètres spécifiques au segment tels que l’ID du fichier, l’ID du segment et la somme de contrôle.  
* Enregistrer le résultat sous un **format d’image de code‑barres** (PNG) qui peut être affiché dans n’importe quelle interface utilisateur.

Le seul prérequis est un environnement de développement .NET (Visual Studio 2022 ou version ultérieure) et le package NuGet Aspose.BarCode for .NET, qui fournit l’API `BarcodeGenerator` utilisée dans les exemples.

---

## Comment créer une image de code‑barres PDF417 en C# – aperçu

Créer une image de code‑barres PDF417 se compose de quatre étapes logiques :

1. **Créer le générateur** – instancier `BarcodeGenerator` avec `EncodeTypes.MacroPdf417` et les données que vous souhaitez encoder.  
2. **Définir la taille du module** – définir `XDimension.Pixels` pour contrôler la largeur physique de chaque élément du code‑barres.  
3. **Configurer les options Macro PDF417** – spécifier les colonnes, les identifiants de fichier, les numéros de segment et la somme de contrôle optionnelle.  
4. **Enregistrer le code‑barres** – écrire l’image générée sur le disque en utilisant un **format d’image de code‑barres** pris en charge tel que PNG.

Chaque étape est expliquée en détail ci‑dessous, avec du code C# complet et exécutable.

---

## Étape 1 : Initialiser le BarcodeGenerator pour Macro PDF417

La première ligne crée un objet `BarcodeGenerator` qui sait qu’il doit produire un code‑barres **Macro PDF417**. Le constructeur prend deux arguments : le type d’encodage et la chaîne de données brute.

```csharp
using Aspose.BarCode.Generation;   // NuGet: Aspose.BarCode
using System.Drawing.Imaging;      // For ImageFormat if you prefer System.Drawing

// Step 1 – create a barcode generator for Macro PDF417
using (var barcodeGenerator = new BarcodeGenerator(EncodeTypes.MacroPdf417, "Sample data"))
{
    // Subsequent configuration goes here
}
```

**Pourquoi c’est important :**  
`EncodeTypes.MacroPdf417` indique à la bibliothèque de traiter le code‑barres comme un conteneur multi‑segment, ce qui est essentiel lorsque vous devez diviser un gros fichier en plusieurs symboles. L’instance `BarcodeGenerator` est jetable, de sorte que le bloc `using` garantit que toutes les ressources non gérées sont libérées après l’enregistrement de l’image.

---

## Étape 2 : Définir la taille du module du code‑barres (XDimension)

`XDimension` contrôle la largeur en pixels d’un seul module du code‑barres (la plus petite barre noire ou blanche). Une valeur de **2 pixels** donne une image compacte mais lisible.

```csharp
    // Step 2 – define the size of each barcode module (pixel width)
    barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

**Astuce pratique :**  
Si votre imprimante cible a une résolution DPI faible, augmentez le nombre de pixels (par ex., `3` ou `4`) pour éviter les bavures. À l’inverse, pour un affichage à l’écran, vous pouvez le garder bas afin de réduire la taille du fichier.

---

## Étape 3 : Configurer les options spécifiques à Macro PDF417

Macro PDF417 ajoute des métadonnées qui permettent à un lecteur de reconstruire le fichier original à partir de plusieurs segments de code‑barres. Les options les plus courantes sont :

| Propriété | Signification |
|-----------|---------------|
| `Columns` | Nombre de colonnes dans chaque symbole (affecte la largeur). |
| `MacroPdf417FileID` | Identifiant unique pour l’ensemble du fichier. |
| `MacroPdf417SegmentID` | Index du segment actuel (commence à 1). |
| `MacroPdf417SegmentsCount` | Nombre total de segments composant le fichier. |
| `MacroPdf417FileName` | Nom du fichier original (facultatif, pour affichage). |
| `MacroPdf417Checksum` | Somme de contrôle 16 bits optionnelle pour vérifier l’intégrité. |

```csharp
    // Step 3 – configure Macro PDF417 specific options
    barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 5;                     // Number of columns in the symbol
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;    // Unique file identifier
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 1;       // Current segment number
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 10; // Total number of segments
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "report.pdf"; // Original file name
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 0x1A2B;    // Optional checksum
```

**Pourquoi ces réglages sont importants :**  
- **Columns** influence la lisibilité et les dimensions globales de l’image.  
- **FileID** doit être identique pour tous les segments afin que le décodeur sache qu’ils appartiennent ensemble.  
- **SegmentID** et **SegmentsCount** permettent au lecteur d’ordonner correctement les morceaux.  
- **FileName** et **Checksum** sont optionnels mais améliorent l’expérience utilisateur et l’intégrité des données.

**Cas limite :** Si vous générez plus de 999 segments, le champ `SegmentID` déborde ; divisez alors les données en plusieurs fichiers.

---

## Étape 4 : Enregistrer le code‑barres généré sous forme d’image PNG

La dernière étape écrit le code‑barres sur le disque. `BarCodeImageFormat.Png` produit une image sans perte qui fonctionne sur le web, le bureau et les plateformes mobiles.

```csharp
    // Step 4 – save the generated barcode as a PNG image
    barcodeGenerator.Save("YOUR_DIRECTORY/MacroPdf417.png", BarCodeImageFormat.Png);
}
```

**Formats alternatifs :**  
Vous pouvez remplacer `BarCodeImageFormat.Png` par `Jpeg`, `Bmp` ou `Gif` si votre système en aval nécessite un format spécifique. Gardez à l’esprit que le JPEG introduit des artefacts de compression qui peuvent réduire la fiabilité du scan.

**Sortie attendue :**  
Le fichier `MacroPdf417.png` contiendra un code‑barres PDF417 multi‑segment à fort contraste. Lorsqu’il est ouvert, il devrait ressembler à l’illustration ci‑dessous.

![Créer un exemple d’image de code‑barres PDF417](image.png){: .align-center alt="Créer un exemple d’image de code‑barres PDF417 généré par le code C#"}

---

## Code source complet – prêt à copier et exécuter

Voici le programme complet, autonome. Il inclut les directives `using` nécessaires, la méthode `Main` et des commentaires expliquant chaque ligne non évidente.

```csharp
using System;
using Aspose.BarCode.Generation;   // Install-Package Aspose.BarCode
// No other external dependencies are required.

namespace Pdf417BarcodeDemo
{
    class Program
    {
        static void Main(string[] args)
        {
            // Data to encode – can be any UTF‑8 string up to 1,800 characters.
            const string dataToEncode = "Sample data";

            // Output directory – change this to a valid path on your machine.
            const string outputPath = @"C:\Barcodes\MacroPdf417.png";

            // Create a BarcodeGenerator for Macro PDF417.
            using (var barcodeGenerator = new BarcodeGenerator(EncodeTypes.MacroPdf417, dataToEncode))
            {
                // 1️⃣ Define module size (pixel width of each bar).
                barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;

                // 2️⃣ Configure Macro PDF417 options.
                barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 5;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 1;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 10;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "report.pdf";
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 0x1A2B;

                // 3️⃣ Save the barcode as a PNG image.
                barcodeGenerator.Save(outputPath, BarCodeImageFormat.Png);
            }

            Console.WriteLine($"PDF417 barcode image created at: {outputPath}");
        }
    }
}
```

**Exécution du programme :**  

1. Créez un nouveau projet console .NET 6 (ou version ultérieure).  
2. Ajoutez le package NuGet Aspose.BarCode (`dotnet add package Aspose.BarCode`).  
3. Remplacez le fichier `Program.cs` généré par le code ci‑dessus.  
4. Ajustez `outputPath` vers un dossier où vous avez les droits d’écriture.  
5. Compilez et exécutez – la console confirmera l’emplacement de l’image.

---

## Questions fréquentes & dépannage

| Question | Réponse |
|----------|---------|
| *Et si le code‑barres est trop large pour mon étiquette ?* | Réduisez `Columns` ou augmentez `XDimension.Pixels` pour équilibrer largeur et lisibilité. |
| *Dois‑je définir une somme de contrôle ?* | La somme de contrôle est optionnelle |

## Que devriez‑vous apprendre ensuite ?

Les tutoriels suivants couvrent des sujets étroitement liés qui s’appuient sur les techniques démontrées dans ce guide. Chaque ressource inclut des exemples de code complets avec des explications pas à pas pour vous aider à maîtriser d’autres fonctionnalités de l’API et explorer des approches d’implémentation alternatives dans vos propres projets.

- [Create PDF417 Barcode in C# – Complete Step‑by‑Step Guide](/barcode/english/net/compact-pdf417-encoding/create-pdf417-barcode-in-c-complete-step-by-step-guide/)
- [Create PDF417 Barcode Metadata in C# – Complete Step‑by‑Step Guide](/barcode/english/net/compact-pdf417-encoding/create-pdf417-barcode-metadata-in-c-complete-step-by-step-gu/)
- [Generate barcode with text – Full PDF417 Macro Guide](/barcode/english/net/compact-pdf417-encoding/generate-barcode-with-text-full-pdf417-macro-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}