---
category: general
date: 2026-09-19
description: Créer un code‑barres PDF417 en C# et apprendre comment générer une image
  de code‑barres, définir les dimensions du code‑barres et l’enregistrer au format
  PNG.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create PDF417 barcode
- how to generate barcode image
- how to set barcode dimensions
- how to create barcode png
language: fr
lastmod: 2026-09-19
og_description: Créez un code‑barres PDF417 en C# et découvrez comment générer une
  image de code‑barres, définir les dimensions du code‑barres et l’enregistrer au
  format PNG.
og_image_alt: Sample PDF417 barcode generated with C# showing custom dimensions saved
  as PNG
og_title: Créer un code‑barres PDF417 et exporter en PNG en C# – guide étape par étape
schemas:
- author: Aspose
  dateModified: '2026-09-19'
  description: Create PDF417 barcode in C# and learn how to generate barcode image,
    set barcode dimensions, and save as PNG.
  headline: How to create PDF417 barcode and export PNG in C#
  type: TechArticle
tags:
- barcode
- PDF417
- C#
- image generation
title: Comment créer un code‑barres PDF417 et l’exporter en PNG en C#
url: /fr/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-and-export-png-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Comment créer un code‑barres PDF417 et l’exporter en PNG en C#

Si vous devez **créer un code‑barres PDF417** dans une application .NET, ce guide vous montre comment générer une image de code‑barres, ajuster ses dimensions et l’enregistrer au format PNG. Vous verrez un exemple complet et exécutable qui utilise la bibliothèque Aspose.BarCode, afin que vous puissiez copier le code directement dans votre projet.

Générer une image de code‑barres est une exigence courante pour les systèmes de billetterie, le suivi d’inventaire et les cartes d’embarquement mobiles. À la fin de ce tutoriel, vous comprendrez **comment générer une image de code‑barres**, **comment définir les dimensions du code‑barres**, et **comment créer des fichiers PNG de code‑barres** qui répondent à vos exigences de qualité visuelle.

## Prérequis

Avant de commencer, assurez‑vous d’avoir :

* .NET 6.0 SDK ou version ultérieure (le code fonctionne également avec .NET Framework 4.7+).
* Un environnement de développement tel que Visual Studio 2022 ou VS Code.
* Une licence valide pour la bibliothèque **Aspose.BarCode for .NET** (l’essai gratuit suffit pour cet exemple).
* Une connaissance de base de la syntaxe C#.

Installez le package NuGet avec la commande suivante :

```bash
dotnet add package Aspose.BarCode
```

## Étape 1 : Configurer le projet et importer les espaces de noms

Créez une nouvelle application console ou ajoutez le code à un projet existant. Importez les espaces de noms requis en haut du fichier :

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;
```

Ces espaces de noms vous donnent accès à la classe `BarcodeGenerator` et à l’énumération `EncodeTypes`.

## Étape 2 : Comment créer un code‑barres PDF417 – configuration de base du générateur

La première opération consiste à instancier un `BarcodeGenerator` avec le type d’encodage `Pdf417` et le texte que vous souhaitez encoder. Cet objet représente le code‑barres que vous rendrez plus tard.

```csharp
// Step 2: Create a PDF417 barcode generator with the desired text
BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Sample");
```

*Pourquoi c’est important* : `EncodeTypes.Pdf417` indique à la bibliothèque d’utiliser la symbologie PDF417, qui est un code‑barres linéaire empilé capable de stocker de grandes quantités de données. Le deuxième argument (« Sample ») est la charge utile qui apparaîtra lors du scan du code‑barres.

## Étape 3 : Comment définir les dimensions du code‑barres – réglage fin de la densité et de la mise en page

Un code‑barres PDF417 est composé de rangées et de colonnes de modules. Ajuster la dimension X (largeur du module) et le nombre de rangées/colonnes vous permet de contrôler la densité visuelle et la taille globale de l’image.

```csharp
// Step 3: Set the module (X) dimension in pixels – controls the barcode's density
generator.Parameters.Barcode.XDimension.Pixels = 2;

// Define the barcode layout – number of columns and rows
generator.Parameters.Barcode.Pdf417.Columns = 4;   // up to 30 columns
generator.Parameters.Barcode.Pdf417.Rows    = 9;   // up to 90 rows
```

*Pourquoi c’est important* :  
* **Dimension X** détermine la largeur de chaque petit carré (module). Une valeur plus petite donne un code‑barres plus compact mais peut être plus difficile à lire pour les scanners basse résolution.  
* **Colonnes** et **Rangées** influencent la capacité de données et la forme physique. Augmenter les colonnes rend le code‑barres plus large ; augmenter les rangées le rend plus haut. Vous pouvez expérimenter avec des valeurs jusqu’aux limites indiquées dans les commentaires.

**Astuce** : Si le code‑barres paraît trop dense sur un écran haute DPI, augmentez `XDimension.Pixels` à 3 ou 4. Inversement, pour une petite étiquette, vous pouvez le régler à 1 pixel et réduire le nombre de colonnes.

## Étape 4 : Comment générer l’image du code‑barres – rendu dans un bitmap en mémoire

Après avoir configuré le générateur, vous pouvez rendre le code‑barres dans un objet image. Cette étape est optionnelle si vous avez seulement besoin d’enregistrer le fichier directement, mais exposer le bitmap vous permet d’appliquer d’autres traitements (par ex., ajouter un logo ou dessiner une bordure).

```csharp
// Step 4: Render the barcode to a bitmap (optional but useful for further manipulation)
using var barcodeImage = generator.GenerateBarCodeImage();
```

`GenerateBarCodeImage()` renvoie un `System.Drawing.Image` que vous pouvez manipuler avec GDI+ si vous le souhaitez.

## Étape 5 : Comment créer un PNG de code‑barres – sauvegarde du fichier image final

Enfin, écrivez l’image sur le disque au format PNG. Le PNG conserve une qualité sans perte, ce qui est idéal pour les applications de lecture.

```csharp
// Step 5: Save the generated barcode as a PNG image
string outputPath = @"YOUR_DIRECTORY\Pdf417Custom.png";
generator.Save(outputPath, BarCodeImageFormat.Png);
Console.WriteLine($"Barcode saved to {outputPath}");
```

*Pourquoi c’est important* : La méthode `Save` gère l’encodage et les entrées/sorties de fichier pour vous. Utiliser `BarCodeImageFormat.Png` garantit que la sortie est une image portable, sans perte, qui fonctionne sur tous les navigateurs et appareils mobiles.

### Exemple complet et exécutable

Voici le programme complet que vous pouvez coller dans `Program.cs` et exécuter. Remplacez `YOUR_DIRECTORY` par un dossier existant sur votre machine.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // 1. Create the generator with PDF417 symbology
        BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Sample");

        // 2. Adjust dimensions for desired visual density
        generator.Parameters.Barcode.XDimension.Pixels = 2;
        generator.Parameters.Barcode.Pdf417.Columns = 4; // up to 30
        generator.Parameters.Barcode.Pdf417.Rows    = 9; // up to 90

        // 3. (Optional) Render to a bitmap if you need further processing
        // using var image = generator.GenerateBarCodeImage();

        // 4. Save as PNG
        string outputPath = @"YOUR_DIRECTORY\Pdf417Custom.png";
        generator.Save(outputPath, BarCodeImageFormat.Png);

        Console.WriteLine($"PDF417 barcode created and saved to: {outputPath}");
    }
}
```

L’exécution du programme produit un fichier PNG qui ressemble à ceci :

![Generated PDF417 barcode example](https://example.com/placeholder-image.png "PDF417 barcode generated with custom dimensions saved as PNG")

*Texte alternatif* : **Exemple de code‑barres PDF417 généré avec C# montrant des dimensions personnalisées sauvegardées en PNG** – cela satisfait l’exigence **create PDF417 barcode** pour l’accessibilité des images.

## Variantes courantes et cas limites

| Situation | Ajustement recommandé |
|-----------|------------------------|
| **Étiquette très petite** (p. ex., 1 cm × 2 cm) | Définir `XDimension.Pixels = 1` et réduire `Columns` à 2‑3. Vérifier la lisibilité du scanner. |
| **Impression haute résolution** (300 dpi ou plus) | Augmenter `XDimension.Pixels` à 3‑4 et éventuellement augmenter `Rows` pour plus de capacité de données. |
| **Besoin d’un autre format d’image** (JPEG, BMP) | Remplacer `BarCodeImageFormat.Png` par `BarCodeImageFormat.Jpeg` ou `BarCodeImageFormat.Bmp`. |
| **Intégration dans un PDF** | Utiliser `generator.Save("output.pdf", BarCodeImageFormat.Pdf)` au lieu de PNG. |
| **Données dynamiques** (entrée utilisateur) | Remplacer la chaîne statique `"Sample"` par une variable, par ex., `userInput`. S’assurer que la longueur du texte ne dépasse pas les limites PDF417 (≈ 1 800 caractères). |

## Checklist de dépannage

* **Image blanche** – Vérifiez que le répertoire de sortie existe et que l’application possède les droits d’écriture.  
* **Code‑barres illisible** – Augmentez `XDimension.Pixels` ou ajoutez plus de colonnes/rangées ; des arrière‑plans à faible contraste peuvent également provoquer des échecs.  
* **Taille inattendue** – Revérifiez les valeurs de `Columns` et `Rows` ; la bibliothèque respecte les limites maximales indiquées dans les commentaires.  

## Prochaines étapes

Maintenant que vous savez **create PDF417 barcode**, envisagez d’explorer les sujets connexes suivants :

* **How to generate barcode image** dans d’autres formats tels que SVG pour des graphiques web évolutifs.  
* **How to set barcode dimensions** pour les symbologies QR code et DataMatrix.  
* **How to create barcode PNG** avec des couleurs personnalisées ou des logos intégrés en utilisant `System.Drawing`.  

Ces extensions vous permettent de créer un service complet de génération de codes‑barres pouvant servir des applications mobiles, des portails web et des utilitaires de bureau.

---

*Vous avez appris comment créer un code‑barres PDF417, personnaliser ses dimensions, rendre une image de code‑barres et l’enregistrer en PNG avec C#. Appliquez les modèles présentés ici à d’autres types de codes‑barres et formats d’image pour élargir vos capacités d’automatisation.*

## Que devriez‑vous apprendre ensuite ?


Les tutoriels suivants couvrent des sujets étroitement liés qui s’appuient sur les techniques démontrées dans ce guide. Chaque ressource inclut des exemples de code complets et fonctionnels avec des explications pas à pas pour vous aider à maîtriser d’autres fonctionnalités de l’API et à explorer des approches d’implémentation alternatives dans vos propres projets.

- [How to Generate PDF417 Barcode Image in C# with Aspose](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-image-in-c-with-aspose/)
- [How to Create PDF417 Barcode with Aspose – Complete Step‑by‑Step Guide](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-with-aspose-complete-step-by-st/)
- [How to Save Barcode in C# – Generate PDF417 Barcodes](/barcode/english/net/compact-pdf417-encoding/how-to-save-barcode-in-c-generate-pdf417-barcodes/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}