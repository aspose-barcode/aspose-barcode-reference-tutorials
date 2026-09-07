---
category: general
date: 2026-09-07
description: Apprenez à générer un code‑barres micro PDF417 en C# avec un exemple
  de code complet, le réglage de la dimension X, la configuration des colonnes et
  l’exportation PNG.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate micro pdf417 barcode
- C# barcode generator
- MicroPdf417 encode type
- barcode X-dimension
- barcode column configuration
- save barcode as PNG
language: fr
lastmod: 2026-09-07
og_description: Générez un code‑barres micro PDF417 en C# avec ce tutoriel concis.
  Comprend les réglages de la dimension X, le choix des colonnes et l’exportation
  PNG pour une utilisation immédiate.
og_image_alt: Screenshot showing a generated micro pdf417 barcode saved as a PNG file
og_title: Générer un code‑barres micro PDF417 en C# – guide complet de programmation
schemas:
- author: Aspose
  dateModified: '2026-09-07'
  description: Learn how to generate micro pdf417 barcode in C# with a complete code
    example, X‑dimension tuning, column configuration, and PNG export.
  headline: How to generate micro pdf417 barcode in C# – step‑by‑step guide
  type: TechArticle
tags:
- barcode
- C#
- MicroPdf417
- image export
title: Comment générer un code‑barres micro PDF417 en C# – guide étape par étape
url: /fr/net/compact-pdf417-encoding/how-to-generate-micro-pdf417-barcode-in-c-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Comment générer un code-barres micro pdf417 en C# – guide étape par étape

Si vous devez **générer un code-barres micro pdf417** dans une application .NET, ce tutoriel vous montre une solution prête à l’emploi. Vous verrez comment configurer la X‑dimension du code-barres, choisir le nombre de colonnes et exporter le résultat sous forme d’image PNG — le tout avec la bibliothèque Aspose.BarCode C#.

Générer un code-barres micro pdf417 est courant lorsque vous devez encoder des données compactes pour des billets mobiles, des étiquettes d’inventaire ou des documents sécurisés. À la fin de ce guide, vous disposerez d’un extrait de code réutilisable que vous pourrez intégrer à n’importe quel projet C#.

## Prérequis

* .NET 6.0 ou ultérieur (le code fonctionne également avec .NET Framework 4.7+)
* Visual Studio 2022 (ou tout IDE supportant C#)
* Le package NuGet **Aspose.BarCode for .NET** (version 23.9 ou plus récente)

Vous pouvez installer le package depuis la ligne de commande :

```bash
dotnet add package Aspose.BarCode
```

Aucune dépendance supplémentaire n’est requise.

## Étape 1 : Créer un générateur de code-barres pour MicroPdf417

La première tâche consiste à instancier un `BarcodeGenerator` avec la valeur d’énumération `EncodeTypes.MicroPdf417` et le texte que vous souhaitez encoder. Le texte peut contenir des caractères Unicode, que la bibliothèque gère automatiquement.

```csharp
using Aspose.BarCode.Generation;

// Step 1: Create a barcode generator for MicroPdf417 with the desired text
BarcodeGenerator generator = new BarcodeGenerator(
    EncodeTypes.MicroPdf417,
    "Åspóse.Barcóde©"
);
```

**Pourquoi c’est important :**  
`EncodeTypes.MicroPdf417` indique à la bibliothèque d’utiliser la symbologie compacte MicroPdf417, qui stocke plus de données dans un espace plus réduit que le PDF417 complet. Fournir le texte lors de la construction garantit que le générateur sait exactement ce qu’il doit encoder.

## Étape 2 : Ajuster la X‑dimension pour une résolution plus fine

La X‑dimension (largeur du module) contrôle le nombre de pixels occupés par chaque colonne du code-barres. Une valeur de **2 pixels** produit un code-barres haute résolution qui reste lisible par la plupart des scanners.

```csharp
// Step 2: Set the X‑dimension (module width) to 2 pixels for finer resolution
generator.Parameters.Barcode.XDimension.Pixels = 2;
```

**Astuce :**  
Si vous ciblez des écrans ou imprimantes à basse résolution, augmentez la valeur à 3‑4 pixels pour éviter les bords flous. À l’inverse, pour des étiquettes à haute densité, vous pouvez la réduire à 1 pixel, mais testez le résultat avec votre scanner.

## Étape 3 : Choisir le nombre de colonnes

MicroPdf417 autorise **de 1 à 4 colonnes**. Plus de colonnes produisent un code-barres plus court mais réduisent la capacité de correction d’erreurs. Pour la plupart des scénarios de billetterie, **4 colonnes** offrent une forme compacte tout en conservant la robustesse.

```csharp
// Step 3: Choose the number of columns (1‑4 are allowed) to control barcode size
generator.Parameters.Barcode.Pdf417.Columns = 4;
```

**Pourquoi vous pourriez modifier cela :**  
Si le texte encodé est plus long que la capacité par défaut, augmentez le nombre de colonnes pour éviter les erreurs de dépassement. Diminuez-le lorsque vous avez besoin d’un code-barres étroit pour un espace limité.

## Étape 4 : Définir le dossier de sortie et le nom de fichier

Sélectionnez un dossier où l’image générée sera enregistrée. L’utilisation de `Path.Combine` garantit des séparateurs de chemin corrects sous Windows, Linux et macOS.

```csharp
using System.IO;

// Step 4: Define the output folder and file name
string outputFolder = Path.Combine(
    Environment.GetFolderPath(Environment.SpecialFolder.Desktop),
    "Barcodes"
);
Directory.CreateDirectory(outputFolder); // Ensure the folder exists
string outputPath = Path.Combine(outputFolder, "MicroPdf417.png");
```

**Gestion des cas limites :**  
Si le chemin du dossier est invalide ou que l’application n’a pas les permissions d’écriture, `Directory.CreateDirectory` lève une exception. Enveloppez la logique d’enregistrement dans un bloc `try/catch` pour le code de production.

## Étape 5 : Enregistrer le code-barres en image PNG

Enfin, exportez le code-barres vers un fichier PNG. Le PNG préserve les bords nets et prend en charge la transparence, ce qui le rend idéal pour le rendu UI ou l’impression.

```csharp
using Aspose.BarCode;

// Step 5: Save the generated barcode as a PNG image
generator.Save(outputPath, BarCodeImageFormat.Png);
```

Après exécution, vous trouverez **MicroPdf417.png** dans le dossier `Barcodes` sur votre bureau. L’ouverture du fichier montre un code-barres micro pdf417 clair et haute résolution, prêt à être scanné.

### Résultat attendu

L’image enregistrée ressemble à l’illustration ci‑dessous (le motif réel dépend du texte encodé).

![Generated micro pdf417 barcode saved as PNG](https://example.com/placeholder-micro-pdf417.png "Screenshot of a generated micro pdf417 barcode saved as a PNG file")

*Texte alternatif :* code‑barres micro pdf417 généré enregistré en image PNG

## Exemple complet, exécutable

En combinant toutes les étapes, vous obtenez un programme unique et autonome :

```csharp
using System;
using System.IO;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // 1️⃣ Create generator with MicroPdf417 and Unicode text
        BarcodeGenerator generator = new BarcodeGenerator(
            EncodeTypes.MicroPdf417,
            "Åspóse.Barcóde©"
        );

        // 2️⃣ Set X‑dimension for high‑resolution output
        generator.Parameters.Barcode.XDimension.Pixels = 2;

        // 3️⃣ Choose 4 columns to keep the barcode compact
        generator.Parameters.Barcode.Pdf417.Columns = 4;

        // 4️⃣ Prepare output folder on the desktop
        string outputFolder = Path.Combine(
            Environment.GetFolderPath(Environment.SpecialFolder.Desktop),
            "Barcodes"
        );
        Directory.CreateDirectory(outputFolder);
        string outputPath = Path.Combine(outputFolder, "MicroPdf417.png");

        // 5️⃣ Save as PNG
        generator.Save(outputPath, BarCodeImageFormat.Png);

        Console.WriteLine($"Barcode saved to: {outputPath}");
    }
}
```

Exécutez le programme (`dotnet run` depuis le dossier du projet) et vérifiez que le fichier PNG apparaît comme prévu.

## Questions fréquentes et dépannage

| Question | Réponse |
|----------|--------|
| **Puis-je générer le code-barres au format JPEG au lieu de PNG ?** | Oui. Remplacez `BarCodeImageFormat.Png` par `BarCodeImageFormat.Jpeg`. Le JPEG compresse l’image mais peut introduire des artefacts qui affectent la lisibilité du scanner. |
| **Que se passe-t-il si le texte contient des caractères non pris en charge par MicroPdf417 ?** | MicroPdf417 prend en charge l’ensemble complet du jeu Unicode. Si vous recevez une `ArgumentException`, vérifiez que la chaîne est correctement encodée (par ex., évitez les paires de substitution qui dépassent la capacité du symbole). |
| **Comment changer la couleur du premier plan ?** | Utilisez `generator.Parameters.Barcode.BarColor = Color.Blue;` avant d’appeler `Save`. |
| **Existe‑t‑il un moyen d’intégrer le code-barres directement dans un PDF ?** | Oui. Utilisez `generator.Save(stream, BarCodeImageFormat.Pdf);` ou ajoutez l’image à un document PDF avec une bibliothèque PDF telle qu’Aspose.PDF. |
| **Mon scanner ne peut pas lire le code-barres—que dois‑je vérifier ?** | Assurez‑vous que la X‑dimension est d’au moins 2 pixels pour la plupart des scanners, vérifiez que le nombre de colonnes correspond à la plage prise en charge par le scanner, et confirmez que la taille imprimée respecte la taille minimale du module du scanner (généralement 0,5 mm). |

## Conclusion

Vous savez maintenant comment **générer un code-barres micro pdf417** en C# du début à la fin. Le guide a couvert la création du `BarcodeGenerator`, la configuration de la X‑dimension et du nombre de colonnes, la préparation d’un chemin de sortie et l’enregistrement du résultat en PNG. En ajustant les paramètres secondaires — tels que la couleur des barres, le format d’image ou le niveau de correction d’erreurs — vous pouvez adapter le code-barres à n’importe quelle application, des billets mobiles aux étiquettes d’inventaire.

### Prochaines étapes

* Expérimentez avec les valeurs de **X‑dimension du code-barres** pour équilibrer taille et lisibilité.  
* Explorez d’autres symbologies (par ex., `EncodeTypes.Pdf417`, `EncodeTypes.QR`) en utilisant le même modèle de générateur.  
* Intégrez le PNG généré dans un rapport PDF avec **Aspose.PDF** ou intégrez‑le directement dans une interface WinForms/WPF.  

Bonne programmation, et profitez de la flexibilité que la bibliothèque Aspose.BarCode apporte à la génération de codes-barres en C# !

## Que devriez‑vous apprendre ensuite ?

Les tutoriels suivants couvrent des sujets étroitement liés qui s’appuient sur les techniques démontrées dans ce guide. Chaque ressource comprend des exemples de code complets et fonctionnels avec des explications étape par étape pour vous aider à maîtriser des fonctionnalités supplémentaires de l’API et explorer des approches d’implémentation alternatives dans vos propres projets.

- [Tutoriel du générateur de code-barres : comment générer un code-barres PDF417 en C#](/barcode/english/net/compact-pdf417-encoding/barcode-generator-tutorial-how-to-generate-pdf417-barcode-in/)
- [Comment enregistrer un code-barres en C# – générer des codes-barres PDF417](/barcode/english/net/compact-pdf417-encoding/how-to-save-barcode-in-c-generate-pdf417-barcodes/)
- [Comment générer un code-barres PDF417 – guide complet de programmation](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-complete-programming-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}