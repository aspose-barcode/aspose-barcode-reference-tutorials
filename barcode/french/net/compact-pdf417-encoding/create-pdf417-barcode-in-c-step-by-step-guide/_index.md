---
category: general
date: 2026-10-04
description: Créez rapidement un code-barres PDF417 en C#. Apprenez à générer un code-barres
  PDF417 et à enregistrer l'image du code-barres au format PNG avec Aspose.Barcode.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create pdf417 barcode c#
- barcode for mobile scanning
- aspose barcode png generation
lastmod: 2026-10-04
og_description: Créer un code-barres PDF417 en C# avec Aspose.Barcode. Ce tutoriel
  vous montre comment générer un code-barres PDF417 compact, configurer son apparence
  et l’enregistrer au format PNG pour la numérisation mobile ou l’impression d’étiquettes.
og_image_alt: 'Developer guide: Create PDF417 barcode in C# and save as PNG using
  Aspose.Barcode'
og_title: Créer un code-barres PDF417 en C# – guide complet étape par étape
schemas:
- author: Aspose
  dateModified: '2026-10-04'
  description: Create PDF417 barcode in C# quickly. Learn how to generate PDF417 barcode
    and how to save barcode image as PNG with Aspose.Barcode.
  headline: Create PDF417 barcode in C# – step‑by‑step guide
  type: TechArticle
- description: Create PDF417 barcode in C# quickly. Learn how to generate PDF417 barcode
    and how to save barcode image as PNG with Aspose.Barcode.
  name: Create PDF417 barcode in C# – step‑by‑step guide
  steps:
  - name: Why this matters
    text: '* **EncodeTypes.Pdf417** tells the library to use the PDF417 standard,
      which supports large data payloads and error correction. * Providing Unicode
      characters proves the generator handles non‑ASCII input without extra configuration.'
  - name: Practical tip
    text: If you need a taller barcode for limited horizontal space, increase `Columns`.
      Setting `Truncate` to `true` reduces the overall height by removing quiet zones,
      which is ideal for mobile screens.
  - name: Expected result
    text: Running the program creates `CompactPdf417.png` in the project folder. Opening
      the file shows a compact PDF417 barcode that encodes the string *Åspóse.Barcóde©*.
      The image can be embedded in HTML, PDF reports, or printed on labels.
  - name: Verifying the output
    text: 'After the program finishes, you can verify the file exists with a quick
      command:'
  type: HowTo
tags:
- barcode
- C#
- PDF417
- image generation
- Aspose.Barcode
title: Créer un code-barres PDF417 en C# – guide étape par étape
url: /fr/net/compact-pdf417-encoding/create-pdf417-barcode-in-c-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Créer un code‑barres PDF417 en C# – guide étape par étape

Si vous devez **créer un code‑barres PDF417** dans une application .NET, ce guide vous montre exactement comment générer un code‑barres PDF417 et comment enregistrer l’image du code‑barres au format PNG. Vous obtiendrez une image compacte qui fonctionne très bien pour la numérisation mobile, les systèmes de billetterie ou les imprimantes d’étiquettes.

## Réponses rapides
- **Quelle bibliothèque gère la génération PDF417 ?** Aspose.Barcode for .NET.  
- **Quel format l'exemple enregistre‑t‑il ?** PNG, using `BarCodeImageFormat.Png`.  
- **Combien de lignes de code sont nécessaires ?** About 10 lines after project setup.  
- **Puis‑je personnaliser la taille et la troncature ?** Yes – `Columns`, `Rows`, and `Truncate` properties.  
- **Le code est‑il compatible avec .NET‑6 ?** Fully, and it also works with .NET Framework 4.7+.

## De quoi avez‑vous besoin pour créer un code‑barres PDF417 en C# ?
Pour commencer, vous avez besoin d’un SDK .NET récent, d’un IDE tel que Visual Studio 2022, et du package NuGet **Aspose.Barcode for .NET**. Ces outils permettent à l’exemple de se compiler et de s’exécuter sans configuration supplémentaire.

- .NET 6.0 SDK ou version ultérieure (fonctionne également avec .NET Framework 4.7+)
- Visual Studio 2022 ou tout éditeur compatible C#
- Accès Internet pour télécharger le package NuGet Aspose.Barcode

## Comment configurer un projet .NET pour la génération de code‑barres PDF417 ?
Créez un nouveau projet console, ajoutez le package Aspose.Barcode, et ouvrez le fichier généré `Program.cs`. Cela prépare un espace de travail propre où vous pouvez instancier le générateur de code‑barres et écrire le fichier de sortie.

```bash
   dotnet new console -n Pdf417Demo
   cd Pdf417Demo
   ```

## Comment générer un code‑barres PDF417 avec Aspose.Barcode ?
`BarcodeGenerator` est la classe Aspose.Barcode qui crée des images de code‑barres à partir des données et de la symbologie fournies. Vous spécifiez la symbologie PDF417, fournissez le texte à encoder, et ajustez éventuellement les paramètres de taille ou de correction d’erreurs.

```bash
   dotnet add package Aspose.Barcode
   ```

### Pourquoi c’est important
* **EncodeTypes.Pdf417** indique à la bibliothèque d’utiliser la norme PDF417, qui prend en charge de grandes charges de données et la correction d’erreurs.
* Fournir des caractères Unicode prouve que le générateur gère les entrées non‑ASCII sans configuration supplémentaire.

## Comment configurer l’apparence d’un code‑barres PDF417 ?
Vous pouvez contrôler la taille du module, le nombre de colonnes, et si le code‑barres utilise le mode compact (truncation). Ces paramètres affectent directement la lisibilité sur les petits écrans et la taille globale du fichier PNG.

`generator.Parameters.Barcode.XDimension` définit la largeur d’un seul module, tandis que `Columns` et `Rows` définissent les dimensions de la matrice. Mettre `Truncate` à `true` supprime les zones calmes pour une image plus compacte.

```csharp
   using System;
   using Aspose.Barcode.Generation;
   using Aspose.Barcode;
   ```

### Astuce pratique
Si vous avez besoin d’un code‑barres plus haut pour un espace horizontal limité, augmentez `Columns`. Mettre `Truncate` à `true` réduit la hauteur globale en supprimant les zones calmes, ce qui est idéal pour les écrans mobiles.

## Comment enregistrer l’image du code‑barres au format PNG ?
`Save` est une méthode de `BarcodeGenerator` qui écrit l’image générée dans un fichier. Passez un chemin de fichier et `BarCodeImageFormat.Png` pour créer une image PNG en une seule étape.

```csharp
// Step 1: Initialise the generator with PDF417 symbology and sample text.
// The text includes Unicode characters to demonstrate full‑range support.
BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Åspóse.Barcóde©");
```

### Résultat attendu
L’exécution du programme crée `CompactPdf417.png` dans le dossier du projet. L’ouverture du fichier affiche un code‑barres PDF417 compact qui encode la chaîne *Åspóse.Barcóde©*. L’image peut être intégrée dans du HTML, des rapports PDF, ou imprimée sur des étiquettes.

## Comment vérifier le fichier de code‑barres généré ?
Après la fin du programme, vous pouvez vérifier que le fichier existe avec une commande rapide. Cette vérification simple confirme que les étapes de génération et d’enregistrement se sont déroulées sans erreur.

```csharp
// Step 2: Set the module (X) dimension – each barcode element will be 2 pixels wide.
generator.Parameters.Barcode.XDimension.Pixels = 2;

// Step 3: Configure PDF417‑specific options.
generator.Parameters.Barcode.Pdf417.Columns = 3;      // Number of columns (affects height)
generator.Parameters.Barcode.Pdf417.Truncate = true; // Enable compact mode
```

Si le fichier apparaît, le processus de **création de code‑barres PDF417** a réussi.

## Quelles sont les variations courantes et les cas limites lors de la génération de code‑barres PDF417 ?
Différents scénarios peuvent nécessiter des ajustements des paramètres du générateur. Ci‑dessous se trouve un tableau de référence rapide montrant comment gérer les variations typiques.

| Situation | Ajustement |
|-----------|------------|
| **Chaîne de données plus longue** | Augmentez `Columns` ou définissez `Rows` pour accueillir plus de codewords. |
| **Format d’image différent** | Remplacez `BarCodeImageFormat.Png` par `Jpeg`, `Bmp` ou `Gif`. |
| **Résolution supérieure** | Définissez `generator.Parameters.ImageResolution` avant `Save`. |
| **Couleur d’arrière‑plan** | Utilisez `generator.Parameters.Barcode.ImageBackgroundColor = Color.White;`. |
| **Gestion des exceptions** | Encapsulez `generator.Save` dans un bloc `try/catch` pour capturer les erreurs d’E/S. |

Ces variations vous permettent d’adapter le code‑barres à des appareils spécifiques ou à des exigences de marque.

## Quelle est la prochaine étape après la création du code‑barres ?
Maintenant que vous pouvez générer et enregistrer un code‑barres PDF417, vous pouvez explorer des fonctionnalités connexes telles que la génération de QR codes, l’intégration de code‑barres dans des documents PDF, ou la personnalisation des couleurs pour l’alignement de la marque. Toutes utilisent la même API `BarcodeGenerator`, vous pouvez donc étendre l’exemple avec un effort minimal.

## Guides associés
- [Comment créer un code‑barres – PDF417 compact avec Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [Comment générer des codes‑barres DataMatrix (ECC 200) avec Aspose.BarCode pour .NET](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-ecc-200-configuration/)
- [Comment générer un code‑barres Aztec avec un ratio d’aspect personnalisé en utilisant Aspose.BarCode pour .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)

## Questions fréquemment posées

**Q : Puis‑je utiliser ce code dans une application web ?**  
R : Oui. La même classe `BarcodeGenerator` fonctionne dans les projets ASP.NET, MVC ou Blazor ; assurez‑vous simplement que le serveur a la permission d’écriture sur le dossier de sortie.

**Q : Aspose.Barcode prend‑il en charge d’autres symbologies 2‑D ?**  
R : Absolument. Plus de 30 types de codes‑barres 2‑D sont pris en charge, y compris QR, DataMatrix et Aztec.

**Q : Quelle taille de code‑barres puis‑je créer ?**  
R : PDF417 peut encoder jusqu’à 1 850 caractères dans un seul symbole ; vous pouvez également répartir les données sur plusieurs lignes en ajustant `Rows` et `Columns`.

**Q : Une licence est‑elle requise pour une utilisation en production ?**  
R : Oui. Un essai gratuit est disponible pour l’évaluation, mais une licence commerciale est nécessaire pour le déploiement.

**Q : Quelles versions de .NET sont compatibles ?**  
R : Aspose.Barcode prend en charge .NET Framework 4.5+, .NET Core 3.1+, et .NET 5/6/7.

---

**Dernière mise à jour :** 2026-10-04  
**Testé avec :** Aspose.Barcode 24.11 for .NET  
**Auteur :** Aspose  

```csharp
// Step 4: Save the generated barcode as a PNG image.
string outputPath = @"./CompactPdf417.png";
generator.Save(outputPath, BarCodeImageFormat.Png);
Console.WriteLine($"Barcode saved to {outputPath}");
```
```csharp
using System;
using Aspose.Barcode.Generation;
using Aspose.Barcode;

namespace Pdf417Demo
{
    class Program
    {
        static void Main()
        {
            // Initialise the generator with PDF417 symbology and sample text.
            BarcodeGenerator generator = new BarcodeGenerator(
                EncodeTypes.Pdf417,
                "Åspóse.Barcóde©");

            // Set the module width to 2 pixels.
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // Configure PDF417‑specific options.
            generator.Parameters.Barcode.Pdf417.Columns = 3;
            generator.Parameters.Barcode.Pdf417.Truncate = true;

            // Define the output file path.
            string outputPath = @"./CompactPdf417.png";

            // Save the barcode as a PNG image.
            generator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"Barcode saved to {outputPath}");
        }
    }
}
```
```bash
dotnet run && ls -l CompactPdf417.png
```

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}