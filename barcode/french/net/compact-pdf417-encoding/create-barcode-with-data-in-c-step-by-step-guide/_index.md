---
category: general
date: 2026-07-27
description: Créer un code-barres avec des données en C# rapidement. Apprenez comment
  créer un code-barres PDF417 en C# en utilisant Aspose.BarCode, définir les dimensions
  et l’enregistrer au format PNG.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode with data
- create pdf417 barcode c#
language: fr
lastmod: 2026-07-27
og_description: Créer un code-barres avec des données en C# en utilisant Aspose.BarCode.
  Ce guide montre comment créer un code-barres PDF417 en C# avec des paramètres personnalisés
  et l’enregistrer au format PNG.
og_image_alt: Screenshot of a barcode created with data in a C# application
og_title: Créer un code-barres avec des données en C# – Guide complet de programmation
schemas:
- author: Aspose
  dateModified: '2026-07-27'
  description: Create barcode with data in C# quickly. Learn how to create PDF417
    barcode c# using Aspose.BarCode, set dimensions, and save as PNG.
  headline: Create barcode with data in C# – Step‑by‑Step Guide
  type: TechArticle
- description: Create barcode with data in C# quickly. Learn how to create PDF417
    barcode c# using Aspose.BarCode, set dimensions, and save as PNG.
  name: Create barcode with data in C# – Step‑by‑Step Guide
  steps:
  - name: Initialising `BarcodeGenerator` with MicroPdf417 and a Unicode string.
    text: Initialising `BarcodeGenerator` with MicroPdf417 and a Unicode string.
  - name: Tweaking the X‑dimension for finer resolution.
    text: Tweaking the X‑dimension for finer resolution.
  - name: Limiting columns to keep the barcode compact.
    text: Limiting columns to keep the barcode compact.
  - name: Saving the result as a PNG file.
    text: Saving the result as a PNG file.
  type: HowTo
tags:
- barcode
- C#
- Aspose
title: Créer un code‑barres avec des données en C# – Guide étape par étape
url: /fr/net/compact-pdf417-encoding/create-barcode-with-data-in-c-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Créer un code‑barres avec des données en C# – Guide complet de programmation

Vous avez déjà eu besoin de **créer un code‑barres avec des données** dans une application .NET mais vous ne saviez pas quelles appels d'API utiliser ? Vous n'êtes pas seul. Que vous étiquetiez des stocks, imprimiez des billets ou intégriez des informations dans une numérisation mobile, maîtriser la création de codes‑barres est une compétence pratique pour tout développeur C#.

Dans ce tutoriel, nous parcourrons un exemple pratique qui vous montre comment **créer un code‑barres PDF417 c#** en utilisant la bibliothèque Aspose.BarCode, ajuster la largeur du module, limiter le nombre de colonnes, et enfin enregistrer le résultat dans un fichier PNG. À la fin, vous disposerez d’un programme console entièrement fonctionnel, prêt à être exécuté, que vous pourrez intégrer à n’importe quel projet.

## Prérequis — Ce dont vous avez besoin

- **.NET 6.0** ou supérieur (le code fonctionne également avec .NET Framework 4.7+)  
- **Aspose.BarCode for .NET** package NuGet (`Install-Package Aspose.BarCode`)  
- Un éditeur de code ou un IDE (Visual Studio, VS Code, Rider – choisissez votre préféré)  
- Permission d’écriture sur un dossier où le PNG sera enregistré  

Aucun fichier de configuration supplémentaire n’est requis ; la bibliothèque est autonome.

## Étape 1 : Configurer le projet et importer les espaces de noms

Tout d’abord, créez un nouveau projet console (ou ouvrez‑en un existant) et ajoutez la référence Aspose.BarCode.

```csharp
// Program.cs – entry point
using System;
using Aspose.BarCode.Generation;   // Core generator classes
using Aspose.BarCode;               // For BarCodeImageFormat enum

namespace BarcodeDemo
{
    class Program
    {
        static void Main(string[] args)
        {
            // We'll place the barcode generation logic here.
        }
    }
}
```

> **Pourquoi c’est important :** Importer les bons espaces de noms vous donne accès à `BarcodeGenerator` et aux paramètres associés sans devoir qualifier chaque type. Cela rend également le code plus propre pour la maintenance future.

## Étape 2 : Initialiser le générateur de code‑barres avec vos données

Nous allons maintenant réellement **créer un code‑barres avec des données**. Le constructeur `BarcodeGenerator` prend deux arguments : la symbologie (`EncodeTypes.MicroPdf417`) et la chaîne que vous souhaitez encoder.

```csharp
// Inside Main()
string dataToEncode = "Åspóse.Barcóde©";   // Example containing Unicode characters
var generator = new BarcodeGenerator(EncodeTypes.MicroPdf417, dataToEncode);
```

> **Astuce :** La symbologie MicroPdf417 est une version compacte du PDF417, parfaite lorsque vous avez besoin d’une image plus petite tout en conservant une grande capacité de données. La bibliothèque gère Unicode dès le départ, donc des caractères comme « Å » et « © » fonctionnent correctement.

## Étape 3 : Ajuster finement la X‑Dimension (largeur du module)

Si vous avez besoin d’une image plus nette et à plus haute résolution, vous pouvez réduire la largeur du module. La définir à **2 pixels** vous donne une grille plus fine sans augmenter la taille du fichier.

```csharp
// Adjust the module (X‑dimension) to 2 pixels
generator.Parameters.Barcode.XDimension.Pixels = 2;
```

> **Pourquoi ajuster la X‑Dimension ?** Une X‑dimension plus petite rend chaque barre plus étroite, ce qui améliore la lisibilité sur les scanners haute résolution tout en maintenant une taille globale du code‑barres raisonnable.

## Étape 4 : Limiter le nombre de colonnes PDF417 (Optionnel mais courant)

PDF417 vous permet de spécifier le nombre de colonnes. Pour MicroPdf417, le maximum est de **4**, ce qui garde le code‑barres court et large.

```csharp
// Set the column count to the maximum allowed (4)
generator.Parameters.Barcode.Pdf417.Columns = 4;
```

> **Cas limite :** Si vous définissez un nombre de colonnes supérieur au maximum autorisé, Aspose le limitera automatiquement, mais il est recommandé de rester dans la plage documentée pour éviter un redimensionnement inattendu.

## Étape 5 : Enregistrer le code‑barres en tant qu’image PNG

Enfin, écrivez l’image générée sur le disque. La méthode `Save` prend le chemin complet et le format d’image souhaité.

```csharp
// Define output path – adjust as needed
string outputPath = @"C:\Temp\MicroPdf417.png";

// Save as PNG (lossless, widely supported)
generator.Save(outputPath, BarCodeImageFormat.Png);

Console.WriteLine($"Barcode saved to {outputPath}");
```

> **Conseil pro :** PNG préserve les données de pixels exactes, ce qui est essentiel pour les codes‑barres. Si vous avez besoin d’un format vectoriel pour le redimensionnement, vous pouvez remplacer `BarCodeImageFormat.Png` par `BarCodeImageFormat.Svg`.

### Exemple complet fonctionnel

En réunissant le tout, voici le programme complet, prêt à copier‑coller :

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

namespace BarcodeDemo
{
    class Program
    {
        static void Main(string[] args)
        {
            // 1️⃣ Data we want to encode – includes special characters
            string dataToEncode = "Åspóse.Barcóde©";

            // 2️⃣ Initialise generator with MicroPdf417 symbology
            var generator = new BarcodeGenerator(EncodeTypes.MicroPdf417, dataToEncode);

            // 3️⃣ Fine‑tune resolution – 2‑pixel modules
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // 4️⃣ Use the maximum of 4 columns for a compact barcode
            generator.Parameters.Barcode.Pdf417.Columns = 4;

            // 5️⃣ Save the image
            string outputPath = @"C:\Temp\MicroPdf417.png";
            generator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"✅ Barcode created successfully! Saved at: {outputPath}");
        }
    }
}
```

L’exécution de ce programme produit un fichier PNG qui ressemble approximativement à ceci :

![Code‑barres créé avec des données en C#](barcode-sample.png "Capture d’écran d’un code‑barres créé avec des données dans une application C#")

*L’image ci‑dessus est un espace réservé — votre vrai code‑barres contiendra exactement la chaîne « Åspóse.Barcóde© *.

## Questions fréquentes & cas limites

| Question | Réponse |
|----------|--------|
| *Et si mes données dépassent la capacité du MicroPdf417 ?* | Passez à `EncodeTypes.Pdf417` (PDF417 standard) qui prend en charge jusqu’à 1 800 caractères. |
| *Puis-je changer le format d’image en JPEG ?* | Oui—remplacez `BarCodeImageFormat.Png` par `BarCodeImageFormat.Jpeg`. N’oubliez pas que le JPEG est avec perte ; cela peut affecter la fiabilité du scanner. |
| *Dois‑je gérer Unicode manuellement ?* | Non. Aspose.BarCode encode automatiquement les caractères Unicode, mais assurez‑vous que votre fichier source est enregistré en UTF‑8. |
| *Et si j’ai besoin d’un arrière‑plan transparent ?* | Définissez `generator.Parameters.Barcode.BackgroundColor = System.Drawing.Color.Transparent;` avant l’enregistrement. |
| *Existe‑t‑il un moyen de générer le code‑barres en mémoire ?* | Appelez `generator.GenerateBarCodeImage()` pour obtenir un objet `System.Drawing.Image` que vous pouvez diffuser directement. |

## Récapitulatif – Ce que nous avons appris

Nous avons démontré comment **créer un code‑barres avec des données** en C# en :

1. Initialiser `BarcodeGenerator` avec MicroPdf417 et une chaîne Unicode.  
2. Ajuster la X‑dimension pour une résolution plus fine.  
3. Limiter le nombre de colonnes pour garder le code‑barres compact.  
4. Enregistrer le résultat sous forme de fichier PNG.  

Tous ces étapes réunies répondent à la question principale « comment **créer un code‑barres PDF417 c#** » tout en vous montrant comment personnaliser les paramètres courants.

## Prochaines étapes & sujets liés

- **Ajouter du texte lisible par l’homme** sous le code‑barres en utilisant `generator.Parameters.Barcode.CodeTextParameters`.  
- **Intégrer le PNG dans un PDF** avec `Aspose.Pdf` pour des rapports imprimables.  
- **Générer d’autres symbologies** (QR, Code128, DataMatrix) en changeant `EncodeTypes`.  
- **Traitement par lots** – parcourir un CSV d’identifiants de produit et générer un dossier de codes‑barres.

N’hésitez pas à expérimenter avec le nombre de colonnes, le niveau de correction d’erreurs et les schémas de couleur. Une fois à l’aise, vous pourrez créer des solutions d’étiquetage complètes qui s’intègrent parfaitement aux systèmes d’inventaire ou de billetterie.

Bon codage, et que vos scans soient toujours sans erreur !

## Que devriez‑vous apprendre ensuite ?

Les tutoriels suivants couvrent des sujets étroitement liés qui s’appuient sur les techniques démontrées dans ce guide. Chaque ressource comprend des exemples de code complets et fonctionnels avec des explications étape par étape pour vous aider à maîtriser des fonctionnalités API supplémentaires et explorer des approches d’implémentation alternatives dans vos propres projets.

- [Comment créer un code‑barres – PDF417 compact avec Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [Créer une image de code‑barres DotCode – lignes & colonnes (Aspose.BarCode)](/barcode/english/net/dotcode-barcode-configuration/dotcode-rows-columns-configuration/)
- [Créer un code‑barres PNG – Ratio d’aspect DataMatrix – Aspose.BarCode](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-aspect-ratio-customization/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}