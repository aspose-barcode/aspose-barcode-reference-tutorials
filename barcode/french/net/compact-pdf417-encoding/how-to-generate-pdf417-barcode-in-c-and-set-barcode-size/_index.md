---
category: general
date: 2026-08-22
description: Apprenez comment générer un code‑barres PDF417 en C# avec Aspose.BarCode,
  définir la taille du code‑barres, ajuster les colonnes et activer le mode compact.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate pdf417 barcode
- how to generate pdf417
- set barcode size
language: fr
lastmod: 2026-08-22
og_description: Générez un code‑barres PDF417 en C# avec Aspose.BarCode. Ce guide
  montre comment définir la taille du code‑barres, contrôler les colonnes et activer
  le mode compact pour une image plus petite.
og_image_alt: Screenshot of a generated PDF417 barcode in C# showing compact mode
og_title: Générer un code‑barres PDF417 en C# – définir la taille, les colonnes et
  le mode compact
schemas:
- author: Aspose
  dateModified: '2026-08-22'
  description: Learn how to generate PDF417 barcode in C# with Aspose.BarCode, set
    barcode size, adjust columns, and enable compact mode.
  headline: How to generate PDF417 barcode in C# and set barcode size
  type: TechArticle
tags:
- pdf417
- barcode
- csharp
title: Comment générer un code‑barres PDF417 en C# et définir la taille du code‑barres
url: /fr/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-and-set-barcode-size/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Comment générer un code-barres PDF417 en C# et définir la taille du code-barres

Si vous devez **générer un code-barres PDF417** dans une application .NET, ce guide vous accompagne à travers le processus complet. Vous verrez exactement **comment générer PDF417** avec Aspose.BarCode, ajuster le **set barcode size**, et produire un PNG compact qui peut être intégré dans des rapports ou des applications mobiles.

Créer un code-barres ne nécessite pas d'éditeur graphique séparé. À la fin de ce tutoriel, vous disposerez d'une méthode C# entièrement fonctionnelle qui produit une image PDF417 avec les dimensions exactes dont vous avez besoin, prête pour le traitement en aval.

## Ce que vous apprendrez

* Installer et référencer la bibliothèque Aspose.BarCode.
* Créer un générateur de code-barres PDF417 et spécifier le texte encodé.
* **Set barcode size** en configurant la X‑dimension et le nombre de colonnes.
* Activer le mode compact (truncaté) pour réduire le symbole.
* Enregistrer le résultat sous forme de fichier PNG.
* Résoudre les problèmes courants tels que les codes illisibles et les images trop volumineuses.

### Prérequis

* .NET 6.0 ou ultérieur (l'API fonctionne également avec .NET Framework 4.6+).
* Familiarité de base avec C# et Visual Studio (ou tout IDE C#).
* Une licence valide Aspose.BarCode (l'évaluation gratuite fonctionne pour les tests).

> **Conseil pro** : Si vous prévoyez de générer de nombreux codes-barres dans une boucle, réutilisez une seule instance de `BarcodeGenerator` et ne modifiez que la propriété `CodeText`. Cela réduit les allocations de mémoire.

## Générer un code-barres PDF417 avec Aspose.BarCode

La première étape consiste à instancier le `BarcodeGenerator` pour la symbologie PDF417. Cet objet est le point d'entrée pour toutes les opérations de code-barres.

```csharp
using Aspose.BarCode.Generation;

// Step 1: Create a PDF417 barcode generator with the desired text
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.Pdf417,          // Symbology
    "Sample text for PDF417");   // Data to encode
```

*Pourquoi c'est important* : `EncodeTypes.Pdf417` indique à la bibliothèque d'utiliser la norme PDF417, qui prend en charge de gros volumes de données et la correction d'erreurs. Le constructeur accepte également les données que vous souhaitez encoder, éliminant ainsi le besoin d'une affectation séparée de `CodeText` ultérieurement.

## Définir la taille du code-barres et le nombre de colonnes

Les symboles PDF417 sont composés de rangées et de colonnes de petits modules rectangulaires. Contrôler la largeur du module (X‑dimension) et le nombre de colonnes vous permet d'ajuster finement les dimensions globales.

```csharp
// Step 2: Adjust the module size (X‑dimension) – 2 pixels per module
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;

// Step 3: Define the number of columns for the PDF417 code
barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 3;
```

*Explication* :  
* **X‑dimension** (`Pixels`) détermine la largeur de chaque module. Des valeurs plus petites produisent un code-barres plus compact, tandis que des valeurs plus grandes augmentent la lisibilité sur les scanners basse résolution.  
* **Columns** contrôle la disposition horizontale. Moins de colonnes rendent le code-barres plus haut ; plus de colonnes le rendent plus large. Ajustez ces deux paramètres ensemble pour obtenir la **set barcode size** exacte dont vous avez besoin.

## Activer le mode compact pour un code-barres plus petit

PDF417 comprend un mode « compact » (ou tronqué) qui supprime les remplissages inutiles et réduit l'empreinte globale. Ceci est particulièrement utile lorsque l'espace d'écran est limité.

```csharp
// Step 4: Enable compact mode to truncate the barcode data
barcodeGenerator.Parameters.Barcode.Pdf417.Truncate = true;
```

*Pourquoi activer la troncature ?*  
Lorsque `Truncate` est `true`, le générateur omet le motif d'arrêt et certains mots de correction d'erreur qui ne sont pas nécessaires pour la plupart des scénarios de lecture. L'image résultante est environ 15‑20 % plus petite sans sacrifier l'intégrité des données pour les cas d'utilisation typiques.

## Enregistrer le code-barres en tant qu'image PNG

Après avoir configuré la taille et le mode, écrivez le code-barres sur le disque. Le PNG est sans perte, garantissant que les bords des modules restent nets.

```csharp
// Step 5: Save the generated barcode as a PNG image
barcodeGenerator.Save(
    "YOUR_DIRECTORY/CompactPdf417.png",
    BarCodeImageFormat.Png);
```

Le fichier `CompactPdf417.png` contiendra un symbole PDF417 net qui correspond aux dimensions que vous avez définies aux étapes précédentes.

### Résultat attendu

L'ouverture du PNG enregistré doit afficher un code-barres PDF417 orienté verticalement composé de trois colonnes, chaque module de 2 px de large, et une taille totale d'environ **120 × 240 px** (largeur × hauteur). Scanner l'image avec n'importe quel lecteur PDF417 standard renvoie le texte original « Sample text for PDF417 ».

## Pièges courants et comment les éviter

| Symptôme | Cause probable | Solution |
|----------|----------------|----------|
| Le code-barres est illisible | X‑dimension trop petite pour le scanner | Augmenter `XDimension.Pixels` à 3 ou 4 |
| L'image est trop large pour l'interface | Trop de colonnes définies | Réduire `Pdf417.Columns` ou activer `Truncate` |
| Exception `ArgumentOutOfRangeException` | Nombre de colonnes négatif ou nul | S'assurer que `Columns` est un entier positif (minimum 1) |
| Le fichier PNG est vide | Le chemin de sortie n'existe pas ou manque d'autorisation d'écriture | Vérifier que le répertoire existe et que l'application a les droits d'écriture |

> **Conseil pro** : Utilisez `barcodeGenerator.ValidateParameters()` avant d'appeler `Save()` pour détecter les erreurs de configuration tôt.

## Exemple complet et exécutable

Voici un programme console autonome qui intègre toutes les étapes ci‑dessus. Copiez‑le dans un nouveau projet C#, restaurez le package NuGet Aspose.BarCode, et exécutez‑le pour voir le résultat.

```csharp
using System;
using Aspose.BarCode.Generation;

namespace Pdf417Demo
{
    class Program
    {
        static void Main()
        {
            // Create the generator with the data to encode
            var generator = new BarcodeGenerator(
                EncodeTypes.Pdf417,
                "Sample text for PDF417");

            // Set module width (X‑dimension) – 2 px per module
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // Choose a small number of columns to keep the barcode compact
            generator.Parameters.Barcode.Pdf417.Columns = 3;

            // Enable truncation for a smaller image
            generator.Parameters.Barcode.Pdf417.Truncate = true;

            // Optional: validate parameters before saving
            generator.ValidateParameters();

            // Save as PNG
            const string outputPath = "CompactPdf417.png";
            generator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"PDF417 barcode saved to {outputPath}");
        }
    }
}
```

**Exécution du programme** produit `CompactPdf417.png` dans le répertoire de travail de l'exécutable. Scannez l image avec une application mobile (par ex., « Barcode Scanner ») pour vérifier que le texte encodé correspond à la chaîne source.

## Prochaines étapes et sujets associés

* **Augmenter le niveau de correction d'erreur** – ajustez `Pdf417.ErrorLevel` pour les environnements avec des scans bruyants.  
* **Changer l'orientation** – définissez `Pdf417.Rotate` à `RotationAngle.Rotate90` si vous avez besoin d'une disposition horizontale.  
* **Intégrer le code-barres dans un PDF** – combinez Aspose.PDF avec Aspose.BarCode pour placer l'image directement dans un document.  
* **Générer d'autres codes-barres 2‑D** – la même classe `BarcodeGenerator` prend en charge DataMatrix, QR et Aztec ; il suffit de remplacer `EncodeTypes.Pdf417` par la symbologie souhaitée.

En maîtrisant les techniques de **generate PDF417 barcode**, vous pouvez automatiser la billetterie, l'étiquetage d'inventaire et la transmission sécurisée de données à travers une large gamme d'applications .NET.

## Conclusion

Vous savez maintenant comment **generate PDF417 barcode** en C#, définir précisément le **set barcode size**, configurer les colonnes, activer le mode compact et enregistrer le résultat en PNG. Appliquez ces paramètres pour répondre à toute contrainte d'interface ou exigence de lecture, et étendez l'approche à d'autres formats de code-barres selon les besoins. Bon codage !

## Que devriez‑vous apprendre ensuite ?

Les tutoriels suivants couvrent des sujets étroitement liés qui s'appuient sur les techniques démontrées dans ce guide. Chaque ressource comprend des exemples de code fonctionnels complets avec des explications étape par étape pour vous aider à maîtriser des fonctionnalités API supplémentaires et explorer des approches d'implémentation alternatives dans vos propres projets.

- [Comment générer un code-barres PDF417 – Encodage PDF417 compact](/barcode/english/net/compact-pdf417-encoding/)
- [Comment créer un code-barres – PDF417 compact avec Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [Comment générer des codes-barres DataMatrix avec Aspose.BarCode pour .NET – Guide étape par étape](/barcode/english/net/datamatrix-barcode-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}