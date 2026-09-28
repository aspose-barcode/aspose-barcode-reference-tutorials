---
category: general
date: 2026-07-18
description: Générez rapidement le code‑barres PDF417. Apprenez comment configurer
  le mode lié et comment générer un code‑barres PDF417 avec Aspose.BarCode dans un
  tutoriel clair étape par étape.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate pdf417 barcode
- how to set linked mode
- how to generate pdf417 barcode
language: fr
lastmod: 2026-07-18
og_description: Générez un code‑barres PDF417 instantanément. Ce tutoriel montre comment
  définir le mode lié et comment générer un code‑barres PDF417 avec Aspose.BarCode,
  complet avec du code exécutable.
og_image_alt: Screenshot of a generated PDF417 barcode with linked mode enabled
og_title: Générer un code‑barres PDF417 en C# – Guide complet étape par étape
schemas:
- author: Aspose
  dateModified: '2026-07-18'
  description: Generate PDF417 barcode quickly. Learn how to set linked mode and how
    to generate PDF417 barcode with Aspose.BarCode in a clear step‑by‑step tutorial.
  headline: Generate PDF417 Barcode in C# – Complete Programming Guide
  type: TechArticle
- description: Generate PDF417 barcode quickly. Learn how to set linked mode and how
    to generate PDF417 barcode with Aspose.BarCode in a clear step‑by‑step tutorial.
  name: Generate PDF417 Barcode in C# – Complete Programming Guide
  steps:
  - name: Prerequisites
    text: '- .NET 6.0 or later (the code also works on .NET Framework 4.7+). - Basic
      C# knowledge. - Visual Studio 2022 (or any IDE you prefer). - A free Aspose.BarCode
      trial or licensed copy.'
  - name: Expected Output
    text: Running the program prints a confirmation line, and the folder now contains
      `Pdf417Linked.png`. Opening the PNG shows a three‑column PDF417 barcode that
      may span two rows (thanks to linked mode). Scanning it with a smartphone app
      reveals the text **“Aspose”**.
  - name: 1. *What if the barcode looks blurry?*
    text: Usually this is a DPI issue. Increase `XDimension.Pixels` or save the image
      at a higher resolution using `generator.Save(..., BarCodeImageFormat.Png, 300)`
      where `300` is the DPI.
  - name: 2. *Can I encode longer strings?*
    text: Yes—PDF417 can hold up to ~1,850 characters. If you exceed the capacity
      of the chosen column count, the library automatically adds rows. Adjust `Columns`
      or enable `IsLinked` to keep the barcode compact.
  - name: 3. *Do I need a license for production?*
    text: Aspose.BarCode works in evaluation mode, but the generated barcode will
      have a small watermark. Purchase a license to remove it and unlock advanced
      features like error‑correction level tweaking.
  - name: 4. *How to generate PDF417 barcode in other formats?*
    text: Simply change the second argument of `Save`. For JPEG use `BarCodeImageFormat.Jpeg`;
      for PDF use `BarCodeImageFormat.Pdf`.
  type: HowTo
tags:
- barcode
- pdf417
- csharp
- aspose
title: Générer un code‑barres PDF417 en C# – Guide complet de programmation
url: /fr/net/compact-pdf417-encoding/generate-pdf417-barcode-in-c-complete-programming-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Générer un code‑barres PDF417 en C# – Guide complet de programmation

Vous avez déjà eu besoin de **générer un code‑barres PDF417** dans une application .NET sans savoir par où commencer ? Vous n’êtes pas seul. Que vous construisiez une imprimante de cartes d’embarquement, un scanner d’entrepôt, ou que vous expérimentiez simplement avec les codes‑barres 2‑D, mettre en place un PDF417 est plus simple que vous ne le pensez.

Dans ce guide, nous passerons en revue les étapes exactes pour **générer un code‑barres PDF417** avec Aspose.BarCode, montrer **comment définir le mode lié**, et couvrir **comment générer un code‑barres PDF417** avec des paramètres personnalisés — le tout dans un exemple prêt à copier‑coller.

## Ce que vous allez apprendre

- Le paquet NuGet minimal dont vous avez besoin.  
- Comment initialiser le générateur PDF417 avec votre propre texte.  
- **Comment définir le mode lié** afin que le code‑barres puisse s’étendre sur plusieurs lignes.  
- Des ajustements supplémentaires comme la taille du module et le nombre de colonnes.  
- Comment enregistrer le résultat en PNG, JPEG ou tout autre format supporté.  
- Les pièges courants et des astuces de dépannage rapides.

### Prérequis

- .NET 6.0 ou supérieur (le code fonctionne également avec .NET Framework 4.7+).  
- Connaissances de base en C#.  
- Visual Studio 2022 (ou tout autre IDE de votre choix).  
- Une version d’essai gratuite d’Aspose.BarCode ou une copie sous licence.

> **Astuce pro :** Si vous partez d’une machine neuve, exécutez `dotnet add package Aspose.BarCode` depuis le terminal dans le dossier de votre projet. Cela récupère tout ce dont vous avez besoin.

---

## Étape 1 : Installer Aspose.BarCode et ajouter les espaces de noms

Première chose à faire — importer la bibliothèque dans le projet.

```csharp
// Using the .NET CLI
dotnet add package Aspose.BarCode
```

Ensuite, en haut de votre fichier C#, incluez les espaces de noms requis :

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;
using System.Drawing.Imaging;   // For image format enums
```

> **Pourquoi c’est important :** Sans l’espace de noms `Aspose.BarCode.Generation`, vous n’aurez pas accès à `BarcodeGenerator`, et l’espace de noms `System.Drawing.Imaging` vous fournit l’énumération `ImageFormat` pour enregistrer les fichiers.

---

## Étape 2 : Initialiser le générateur de code‑barres PDF417

Nous créons maintenant une instance du générateur et lui transmettons le texte à encoder. C’est le cœur de **comment générer un code‑barres PDF417**.

```csharp
// Step 2: Create a generator for PDF417 with the desired payload
var generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Aspose");
```

> **Explication :** `EncodeTypes.Pdf417` indique à Aspose que nous travaillons avec la symbologie PDF417. Le deuxième argument, `"Aspose"`, représente les données qui apparaîtront lorsqu’on scannera le code‑barres.

---

## Étape 3 : Définir la taille du module (X‑Dimension)

La taille du module contrôle la dimension de chaque petit carré (ou « pixel ») du code‑barres. Des valeurs plus petites donnent un code plus compact ; des valeurs plus grandes le rendent plus lisible sur des imprimantes à basse résolution.

```csharp
// Step 3: Set the X‑dimension in pixels (module size)
generator.Parameters.Barcode.XDimension.Pixels = 2;
```

> **Plage typique :** 1–4 pixels convient à la plupart des écrans. Si vous imprimez sur une imprimante d’étiquettes haute DPI, montez à 3 ou 4.

---

## Étape 4 : Configurer les colonnes et activer le mode lié

C’est ici que nous répondons à **comment définir le mode lié**. Le mode lié permet à un code‑barres PDF417 de se diviser sur plusieurs lignes, ce qui est pratique lorsque l’espace horizontal est limité.

```csharp
// Step 4a: Choose the number of columns (affects data capacity & shape)
generator.Parameters.Barcode.Pdf417.Columns = 3;

// Step 4b: Turn on linked mode so the barcode can wrap
generator.Parameters.Barcode.Pdf417.IsLinked = true;
```

> **Pourquoi le mode lié ?** Imaginez que le code‑barres doit tenir dans un élément d’interface étroit. Avec `IsLinked = true`, la bibliothèque découpe automatiquement le symbole en lignes tout en conservant sa lisibilité.  
> **Cas limite :** Si vous définissez `Columns` trop bas tout en activant le mode lié, Aspose peut augmenter considérablement le nombre de lignes, ce qui pourrait dépasser la taille d’une petite toile d’image. Surveillez les dimensions finales de l’image.

---

## Étape 5 : Enregistrer l’image du code‑barres

Enfin, écrivez le code‑barres dans un fichier. Vous pouvez choisir PNG, JPEG, BMP ou même PDF. Le PNG est sans perte, idéal pour un traitement ultérieur.

```csharp
// Step 5: Persist the barcode as a PNG file
string outputPath = Path.Combine(Environment.CurrentDirectory, "Pdf417Linked.png");
generator.Save(outputPath, BarCodeImageFormat.Png);
Console.WriteLine($"Barcode saved to {outputPath}");
```

> **Résultat :** Vous obtiendrez un code‑barres PDF417 net avec trois colonnes, une taille de module de 2 pixels, et des lignes liées si les données dépassent la largeur d’une seule ligne.

---

## Exemple complet fonctionnel

Voici le programme complet, prêt à être exécuté. Copiez‑collez‑le dans un nouveau projet console (`dotnet new console`) et appuyez sur **F5**.

```csharp
using System;
using System.IO;
using Aspose.BarCode.Generation;
using Aspose.BarCode;
using System.Drawing.Imaging;

class Program
{
    static void Main()
    {
        // 1️⃣ Initialize generator with PDF417 and payload
        var generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Aspose");

        // 2️⃣ Set module size (X‑dimension) – 2 pixels works well on most screens
        generator.Parameters.Barcode.XDimension.Pixels = 2;

        // 3️⃣ Define columns and enable linked mode
        generator.Parameters.Barcode.Pdf417.Columns = 3;
        generator.Parameters.Barcode.Pdf417.IsLinked = true;   // ← how to set linked mode

        // 4️⃣ Choose output path and save as PNG
        string outputPath = Path.Combine(Environment.CurrentDirectory, "Pdf417Linked.png");
        generator.Save(outputPath, BarCodeImageFormat.Png);

        Console.WriteLine($"✅ PDF417 barcode generated! Saved at: {outputPath}");
    }
}
```

### Résultat attendu

L’exécution du programme affiche une ligne de confirmation, et le dossier contient maintenant `Pdf417Linked.png`. L’ouverture du PNG montre un code‑barres PDF417 à trois colonnes qui peut s’étendre sur deux lignes (grâce au mode lié). Le scanner d’un smartphone révèle le texte **« Aspose »**.

---

## Questions fréquentes & dépannage

### 1. *Et si le code‑barres apparaît flou ?*  
En général, c’est un problème de DPI. Augmentez `XDimension.Pixels` ou enregistrez l’image à une résolution supérieure avec `generator.Save(..., BarCodeImageFormat.Png, 300)` où `300` représente le DPI.

### 2. *Puis‑je encoder des chaînes plus longues ?*  
Oui—PDF417 peut contenir jusqu’à ~1 850 caractères. Si vous dépassez la capacité du nombre de colonnes choisi, la bibliothèque ajoute automatiquement des lignes. Ajustez `Columns` ou activez `IsLinked` pour garder le code compact.

### 3. *Ai‑je besoin d’une licence pour la production ?*  
Aspose.BarCode fonctionne en mode évaluation, mais le code‑barres généré comporte un petit filigrane. Achetez une licence pour le supprimer et débloquer des fonctionnalités avancées comme le réglage du niveau de correction d’erreurs.

### 4. *Comment générer le code‑barres PDF417 dans d’autres formats ?*  
Il suffit de changer le deuxième argument de `Save`. Pour JPEG, utilisez `BarCodeImageFormat.Jpeg` ; pour PDF, `BarCodeImageFormat.Pdf`.

---

## Extension de l’exemple

Maintenant que vous savez **comment générer un code‑barres PDF417** et **comment définir le mode lié**, vous pouvez explorer :

- **Niveau de correction d’erreurs** – `generator.Parameters.Barcode.Pdf417.ErrorCorrection = Pdf417ErrorCorrectionLevel.Level3;`  
- **Ajout d’une bordure** – `generator.Parameters.Barcode.BorderWidth = 1;`  
- **Couleurs personnalisées** – `generator.Parameters.Barcode.ForeColor = Color.DarkBlue;`  
- **Intégration du code‑barres dans un rapport PDF** – combinez Aspose.PDF avec Aspose.BarCode.

Chacune de ces personnalisations suit le même schéma : localisez la propriété appropriée sous `generator.Parameters.Barcode.Pdf417` (ou l’objet générique `Barcode`) et affectez‑lui une valeur.

---

## Conclusion

Nous avons couvert tout ce qu’il faut pour **générer un code‑barres PDF417** en C#, de l’installation d’Aspose.BarCode à la configuration du mode lié et à l’enregistrement de l’image. En suivant les étapes ci‑dessus, vous disposerez d’un générateur de code‑barres prêt pour la production, intégrable à n’importe quelle solution .NET.

Rappelez‑vous les points clés :

1. Initialisez avec `EncodeTypes.Pdf417`.  
2. Ajustez `XDimension` pour la clarté visuelle.  
3. Définissez `Columns` et activez `IsLinked` pour contrôler la mise en page (**comment définir le mode lié**).  
4. Enregistrez dans le format souhaité.

N’hésitez pas à expérimenter avec les paramètres supplémentaires, et partagez vos résultats ou posez vos questions dans les commentaires. Bon codage, et que vos codes‑barres soient toujours lisibles du premier coup !

## Que devez‑vous apprendre ensuite ?

Les tutoriels suivants traitent de sujets étroitement liés qui s’appuient sur les techniques présentées dans ce guide. Chaque ressource comprend des exemples de code complets avec des explications pas à pas pour vous aider à maîtriser d’autres fonctionnalités de l’API et à explorer des approches d’implémentation alternatives dans vos propres projets.

- [How to Create Barcode – Compact PDF417 with Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)  
- [How to Generate PDF417 Barcodes – Compact PDF417 Encoding](/barcode/english/net/compact-pdf417-encoding/)  
- [How to Generate Barcode Image in Java with Aspose.BarCode](/barcode/english/java/barcode-rendering-techniques/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}