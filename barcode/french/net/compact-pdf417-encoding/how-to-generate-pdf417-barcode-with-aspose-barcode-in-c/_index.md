---
category: general
date: 2026-10-24
description: Apprenez à générer un code‑barres PDF417 en utilisant Aspose.BarCode
  en C# avec des paramètres compacts et le contrôle de la XDimension du code‑barres.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate PDF417 barcode
- Aspose.BarCode
- compact PDF417
- barcode XDimension
- PDF417 columns
language: fr
lastmod: 2026-10-24
og_description: Générez un code‑barres PDF417 en C# avec Aspose.BarCode. Suivez ce
  guide complet pour créer des images PDF417 compactes, contrôler la XDimension et
  définir les colonnes.
og_image_alt: Screenshot of generated PDF417 barcode using Aspose.BarCode
og_title: Générer un code‑barres PDF417 avec Aspose.BarCode – C# étape par étape
schemas:
- author: Aspose
  dateModified: '2026-10-24'
  description: Learn how to generate PDF417 barcode using Aspose.BarCode in C# with
    compact settings and barcode XDimension control.
  headline: How to generate PDF417 barcode with Aspose.BarCode in C#
  type: TechArticle
- description: Learn how to generate PDF417 barcode using Aspose.BarCode in C# with
    compact settings and barcode XDimension control.
  name: How to generate PDF417 barcode with Aspose.BarCode in C#
  steps:
  - name: 1. Changing the image format
    text: '```csharp generator.Save("CompactPdf417.svg", BarCodeImageFormat.Svg);
      ```'
  - name: 2. Encoding large amounts of data
    text: 'PDF417 can store up to ~1.1 KB of text. When the payload exceeds the capacity
      of three columns, the library automatically adds rows. To keep the barcode compact,
      you can:'
  - name: 3. Using a license to remove the trial watermark
    text: '```csharp Aspose.BarCode.License license = new Aspose.BarCode.License();
      license.SetLicense("Aspose.BarCode.lic"); ```'
  - name: 4. Handling exceptions
    text: '```csharp try { generator.Save(outputPath, BarCodeImageFormat.Png); } catch
      (Exception ex) { Console.Error.WriteLine($"Failed to generate barcode: {ex.Message}");
      } ```'
  type: HowTo
tags:
- barcode
- Aspose.BarCode
- PDF417
- C#
title: Comment générer un code‑barres PDF417 avec Aspose.BarCode en C#
url: /fr/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-with-aspose-barcode-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Comment générer un code‑barres PDF417 avec Aspose.BarCode en C#

Si vous devez **générer un code‑barres PDF417** dans une application .NET, ce guide vous présente une solution complète, prête à l’emploi. Vous verrez comment Aspose.BarCode simplifie le processus tout en vous offrant un contrôle précis sur le **PDF417 compact**, la **XDimension du code‑barres**, et les **colonnes PDF417**.

Créer un code‑barres est une exigence courante pour les systèmes d’inventaire, les plateformes de billetterie et les flux de documents. À la fin de ce tutoriel, vous disposerez d’un programme C# autonome qui génère une image PNG nette d’un code‑barres PDF417, prête à être intégrée dans n’importe quelle interface ou imprimée sur une étiquette.

## Ce dont vous avez besoin

- SDK .NET 6.0 ou ultérieur (le code fonctionne également avec .NET Framework 4.6+)
- Visual Studio 2022 ou tout éditeur C# de votre choix
- Une licence valide d’Aspose.BarCode pour .NET (l’essai gratuit suffit pour le développement)
- Une connaissance de base de la syntaxe C#

> **Astuce :** Si vous évaluez Aspose.BarCode, téléchargez l’essai depuis le site officiel et ajoutez le package NuGet `Aspose.BarCode` à votre projet. L’essai ajoute un petit filigrane à l’image générée, qui disparaît dès que vous appliquez une licence.

## Étape 1 : Installer le package NuGet Aspose.BarCode

Ouvrez un terminal dans le dossier de votre solution et exécutez :

```bash
dotnet add package Aspose.BarCode
```

La commande récupère la dernière version stable (en date d’octobre 2026, version 23.12). L’ajout du package restaure l’espace de noms `Aspose.BarCode.Generation` que vous utiliserez pour **générer des images de code‑barres PDF417**.

## Étape 2 : Créer un projet console C# de base

Si vous n’avez pas encore de projet, créez‑en un :

```bash
dotnet new console -n Pdf417Demo
cd Pdf417Demo
```

Ouvrez `Program.cs`. Le squelette contient déjà une méthode `Main` où nous placerons le code de génération du code‑barres.

## Étape 3 : Initialiser le générateur de code‑barres

Tout d’abord, importez l’espace de noms requis :

```csharp
using Aspose.BarCode.Generation;
```

Ensuite, dans `Main`, créez une instance de `BarcodeGenerator` avec la symbologie PDF417 et les données que vous souhaitez encoder :

```csharp
// Step 3: Initialize the generator for a PDF417 barcode
BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Åspóse.Barcóde©");
```

La chaîne inclut des caractères Unicode pour démontrer qu’Aspose.BarCode gère correctement les entrées non‑ASCII. Si vous n’avez besoin que d’ASCII, remplacez le texte par n’importe quelle chaîne simple.

## Étape 4 : Ajuster la XDimension du code‑barres (taille du module)

La **XDimension du code‑barres** détermine la largeur du plus petit module (la barre). La définir en pixels vous donne un contrôle pixel‑parfait sur la taille finale de l’image :

```csharp
// Step 4: Set the module size – XDimension in pixels
generator.Parameters.Barcode.XDimension.Pixels = 2;
```

Une valeur de `2` pixels produit une image compacte sans sacrifier la fiabilité du scan. Augmentez la valeur pour des codes‑barres plus grands ou diminuez‑la pour des mises en page très denses.

## Étape 5 : Configurer les options PDF417 compactes

Deux paramètres spécifiques à PDF417 influencent fortement l’empreinte visuelle :

| Paramètre | Signification | Valeur typique pour une sortie compacte |
|-----------|---------------|------------------------------------------|
| `Columns` | Nombre de colonnes de données | `3` |
| `Truncate` (mode compact) | Omet la zone silencieuse droite et réduit le nombre de lignes | `true` |

Appliquez‑les comme suit :

```csharp
// Step 5: Use a small number of columns and enable compact mode
generator.Parameters.Barcode.Pdf417.Columns = 3;      // PDF417 columns
generator.Parameters.Barcode.Pdf417.Truncate = true; // compact PDF417
```

Utiliser les **colonnes PDF417** réglées à `3` avec `Truncate = true` crée un code‑barres *PDF417 compact* qui s’adapte parfaitement à une étiquette standard tout en restant lisible par la plupart des lecteurs.

## Étape 6 : Enregistrer l’image du code‑barres

Enfin, écrivez le code‑barres sur le disque. L’exemple enregistre un PNG, mais Aspose.BarCode prend également en charge BMP, JPEG, GIF, TIFF et SVG :

```csharp
// Step 6: Save the barcode as a PNG file
string outputPath = Path.Combine(Environment.CurrentDirectory, "CompactPdf417.png");
generator.Save(outputPath, BarCodeImageFormat.Png);
Console.WriteLine($"Barcode saved to {outputPath}");
```

La constante `BarCodeImageFormat.Png` indique à la bibliothèque de produire un PNG sans perte, idéal pour un traitement ultérieur ou l’impression.

## Code source complet et exécutable

```csharp
using System;
using System.IO;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // 1️⃣ Create the generator for PDF417 with Unicode text
        BarcodeGenerator generator = new BarcodeGenerator(
            EncodeTypes.Pdf417,
            "Åspóse.Barcóde©");

        // 2️⃣ Set module size – barcode XDimension in pixels
        generator.Parameters.Barcode.XDimension.Pixels = 2;

        // 3️⃣ Configure compact PDF417 options
        generator.Parameters.Barcode.Pdf417.Columns = 3;      // PDF417 columns
        generator.Parameters.Barcode.Pdf417.Truncate = true; // compact PDF417

        // 4️⃣ Save as PNG
        string outputPath = Path.Combine(
            Environment.CurrentDirectory,
            "CompactPdf417.png");

        generator.Save(outputPath, BarCodeImageFormat.Png);
        Console.WriteLine($"Barcode saved to {outputPath}");
    }
}
```

Exécuter le programme génère `CompactPdf417.png` dans le répertoire racine du projet. Ouvrez le fichier avec n’importe quel visualiseur d’images ; vous verrez un code‑barres PDF417 très compact qui encode la chaîne *Åspóse.Barcóde©*.

![Capture d’écran du code‑barres PDF417 généré avec Aspose.BarCode](placeholder-image.png "Code‑barres PDF417 généré")

*Texte alternatif de l’image : Capture d’écran du code‑barres PDF417 généré avec Aspose.BarCode* – ce texte alternatif contient le mot‑clé principal pour l’accessibilité et le SEO.

## Vérification du résultat

1. Ouvrez le fichier PNG. Le code‑barres doit comporter trois colonnes de données verticales avec une mise en page compacte (pas de zones silencieuses supplémentaires du côté droit).
2. Scannez l’image avec un lecteur de code‑barres smartphone qui prend en charge PDF417. Le texte décodé doit correspondre à la chaîne d’entrée originale.
3. Si le lecteur échoue, essayez d’augmenter `XDimension.Pixels` à `3` ou `4`. Des modules plus grands améliorent la lisibilité sur les appareils à faible résolution.

## Variations courantes et cas limites

### 1. Modifier le format d’image

```csharp
generator.Save("CompactPdf417.svg", BarCodeImageFormat.Svg);
```

SVG est basé sur le vecteur, ce qui maintient le code‑barres net à n’importe quel niveau de zoom — utile pour les pages web.

### 2. Encoder de grandes quantités de données

PDF417 peut stocker jusqu’à ~1,1 KB de texte. Lorsque la charge dépasse la capacité de trois colonnes, la bibliothèque ajoute automatiquement des lignes. Pour garder le code‑barres compact, vous pouvez :

- Réduire la longueur des données (par ex., utiliser un identifiant au lieu d’un message complet)
- Augmenter le nombre de **colonnes PDF417** (par ex., `generator.Parameters.Barcode.Pdf417.Columns = 5;`)

### 3. Utiliser une licence pour supprimer le filigrane d’essai

```csharp
Aspose.BarCode.License license = new Aspose.BarCode.License();
license.SetLicense("Aspose.BarCode.lic");
```

Placez le fichier de licence à côté de l’exécutable. Après activation de la licence, l’image générée ne comporte aucun filigrane.

### 4. Gestion des exceptions

```csharp
try
{
    generator.Save(outputPath, BarCodeImageFormat.Png);
}
catch (Exception ex)
{
    Console.Error.WriteLine($"Failed to generate barcode: {ex.Message}");
}
```

Les échecs typiques incluent des permissions d’écriture insuffisantes ou un format d’image non pris en charge.

## Pourquoi ces paramètres sont importants

- **XDimension du code‑barres** – Contrôle le poids visuel de chaque barre. Trop petite rend le code‑barres illisible ; trop grande gaspille de l’espace.
- **Colonnes PDF417** – Moins de colonnes produisent un code‑barres plus étroit mais augmentent le nombre de lignes

## Que devriez‑vous apprendre ensuite ?

Les tutoriels suivants couvrent des sujets étroitement liés qui s’appuient sur les techniques présentées dans ce guide. Chaque ressource comprend des exemples de code complets et fonctionnels avec des explications pas à pas pour vous aider à maîtriser des fonctionnalités supplémentaires de l’API et explorer des approches d’implémentation alternatives dans vos propres projets.

- [Comment générer un code‑barres PDF417 avec Aspose – Guide complet](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-with-aspose-complete-guide/)
- [Générer un code‑barres PDF417 avec des paramètres compacts en C#](/barcode/english/net/compact-pdf417-encoding/generate-pdf417-barcode-with-compact-settings-in-c/)
- [Comment enregistrer un code‑barres et générer PDF417 avec Aspose en C#](/barcode/english/net/compact-pdf417-encoding/how-to-save-barcode-and-generate-pdf417-with-aspose-in-c/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}