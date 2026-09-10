---
category: general
date: 2026-07-27
description: Créer une image de code‑barres omnidirectionnel avec Aspose.BarCode.
  Apprenez à générer un code‑barres avec Aspose, à ajuster le rapport d’aspect et
  à enregistrer des fichiers PNG.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create omnidirectional barcode image
- generate barcode with aspose
language: fr
lastmod: 2026-07-27
og_description: Créez une image de code‑barres omnidirectionnel avec Aspose. Suivez
  ce guide pour générer un code‑barres avec Aspose, ajuster les rapports d’aspect
  et exporter des PNG.
og_image_alt: Screenshot of two omnidirectional barcode images with different aspect
  ratios
og_title: Créer une image de code‑barres omnidirectionnel avec Aspose – Étape par
  étape
schemas:
- author: Aspose
  dateModified: '2026-07-27'
  description: Create omnidirectional barcode image using Aspose.BarCode. Learn how
    to generate barcode with Aspose, adjust aspect ratio, and save PNG files.
  headline: Create Omnidirectional Barcode Image with Aspose – Full Guide
  type: TechArticle
- description: Create omnidirectional barcode image using Aspose.BarCode. Learn how
    to generate barcode with Aspose, adjust aspect ratio, and save PNG files.
  name: Create Omnidirectional Barcode Image with Aspose – Full Guide
  steps:
  - name: 1. Different Image Formats
    text: 'Aspose supports BMP, JPEG, TIFF, and SVG in addition to PNG. Swap the enum
      value:'
  - name: 2. Customizing Colors
    text: 'You might need a white barcode on a dark background. Set `ForeColor` and
      `BackColor`:'
  - name: 3. Handling Invalid Aspect Ratios
    text: 'Aspose validates the range (usually 5‑50). If you pass an out‑of‑range
      value, an `ArgumentException` is thrown. Wrap the save call in a try‑catch to
      give a friendly message:'
  - name: 4. Batch Generation
    text: When you have a list of GTINs, loop over them, update `CodeText`, and save
      each file with a unique name. The generator object can be reused, keeping memory
      usage low.
  type: HowTo
tags:
- barcode
- Aspose
- C#
- image-generation
title: Créer une image de code‑barres omnidirectionnel avec Aspose – Guide complet
url: /fr/python-java/general/create-omnidirectional-barcode-image-with-aspose-full-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Créer une image de code-barres omnidirectionnel avec Aspose – Guide complet

Vous avez déjà eu besoin de **créer une image de code‑barres omnidirectionnel** sans savoir quelle bibliothèque choisir ? Vous n'êtes pas seul. Dans de nombreux projets logistiques et de distribution, le format DataBar Stacked Omnidirectional est la sauce secrète pour un encodage compact et à haute densité.  

La bonne nouvelle ? Avec **Aspose.BarCode**, vous pouvez générer ce code‑barres en quelques lignes, ajuster son ratio d’aspect, et enregistrer le PNG directement sur le disque. Vous verrez ci‑dessous exactement comment **générer un code‑barres avec Aspose**, pourquoi chaque paramètre compte, et ce à quoi il faut faire attention lorsque vous modifiez le ratio d’aspect.

---

## Ce que couvre ce tutoriel

Nous parcourrons l’ensemble du cycle de vie :

1. Configuration du dossier de sortie.  
2. Instanciation d’un générateur DataBar Stacked Omnidirectional.  
3. Configuration des dimensions en pixels et des ratios d’aspect.  
4. Enregistrement du code‑barres au format PNG.  
5. Extension de l’exemple à d’autres formats et cas particuliers.

À la fin, vous disposerez d’une application console C# prête à l’emploi qui génère deux images de code‑barres distinctes. Aucun outil externe, uniquement du code Aspose pur.

**Prérequis**

- SDK .NET 6.0 ou ultérieur (le code fonctionne également avec .NET Framework 4.7.2).  
- Package NuGet Aspose.BarCode for .NET (`Install-Package Aspose.BarCode`).  
- Un dossier sur le disque où les images peuvent être écrites.

Si vous avez déjà tout cela, plongeons‑y.

---

## Étape 1 : préparer le dossier de sortie

Première chose à faire — indiquer au programme où déposer les fichiers PNG. Hard‑coder un chemin fonctionne pour une démo, mais en production vous lirez probablement cette valeur depuis la configuration.

```csharp
using System;
using System.IO;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Step 1: Define the folder where the images will be saved
        string outputFolder = Path.Combine(Environment.CurrentDirectory, "Barcodes");
        Directory.CreateDirectory(outputFolder);   // ensures the folder exists
```

*Pourquoi c’est important :* `Directory.CreateDirectory` est idempotent ; il ne lèvera pas d’exception si le dossier existe déjà, vous évitant ainsi un bloc `try‑catch`.

---

## Étape 2 : créer un générateur DataBar Stacked Omnidirectional

Nous créons maintenant le générateur avec le type d’encodage spécifique et des données d’exemple. La chaîne `"(01)12345678901231"` suit la syntaxe de l’identifiant d’application GS1 pour un GTIN à 14 chiffres.

```csharp
        // Step 2: Create a DataBar Stacked Omnidirectional barcode generator with sample data
        BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
            EncodeTypes.DatabarStackedOmniDirectional,
            "(01)12345678901231");
```

*Explication :* `EncodeTypes.DatabarStackedOmniDirectional` indique à Aspose d’utiliser la variante omnidirectionnelle, lisible depuis n’importe quelle orientation — idéal pour les petites étiquettes qui peuvent être tournées.

---

## Étape 3 : définir les paramètres communs du code‑barres

Avant de rendre quoi que ce soit, nous définissons la plus petite taille d’élément (X‑Dimension). Une valeur de **2 pixels** donne une image nette sans gonfler la taille du fichier.

```csharp
        // Step 3: Set common barcode parameters (pixel size of the smallest element)
        barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

*Astuce :* Si vous avez besoin d’une résolution supérieure pour l’impression, passez à 3 ou 4. N’oubliez pas que des X‑Dimensions plus grandes augmentent proportionnellement la largeur et la hauteur.

---

## Étape 4 : générer et enregistrer avec le ratio d’aspect 15

La famille DataBar vous permet d’ajuster le **ratio d’aspect**, qui contrôle la relation hauteur‑largeur. Un ratio d’aspect de **15** est la valeur par défaut courante pour les codes‑barres omnidirectionnels.

```csharp
        // Step 4: Generate a barcode with an aspect ratio of 15 and save it as PNG
        barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = 15;
        barcodeGenerator.Save(Path.Combine(outputFolder, "DatabarAspectRatio15.png"),
                              BarCodeImageFormat.Png);
```

*Ce que vous verrez :* Un code‑barres relativement haut qui tient confortablement sur une étiquette de 2 × 1 cm. Le format PNG conserve une qualité sans perte, idéal pour un traitement ultérieur ou l’impression.

---

## Étape 5 : changer le ratio d’aspect à 30 et enregistrer à nouveau

Vous voulez un code‑barres plus plat ? Il suffit de modifier la propriété `AspectRatio` et d’appeler à nouveau `Save`. Pas besoin de recréer le générateur.

```csharp
        // Step 5: Change the aspect ratio to 30 and save the new image
        barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = 30;
        barcodeGenerator.Save(Path.Combine(outputFolder, "DatabarAspectRatio30.png"),
                              BarCodeImageFormat.Png);
    }
}
```

*Pourquoi réutiliser le même générateur ?* Les objets Aspose sont légers ; changer une propriété et ré‑enregistrer est plus rapide que de construire une nouvelle instance, et cela garantit que les mêmes paramètres d’encodage (par ex. X‑Dimension) restent cohérents.

---

## Exemple complet fonctionnel

En réunissant tous les morceaux, voici le programme complet, autonome, que vous pouvez copier‑coller dans un nouveau projet console.

```csharp
using System;
using System.IO;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Define output folder
        string outputFolder = Path.Combine(Environment.CurrentDirectory, "Barcodes");
        Directory.CreateDirectory(outputFolder);

        // Initialize generator with omnidirectional DataBar
        BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
            EncodeTypes.DatabarStackedOmniDirectional,
            "(01)12345678901231");

        // Common settings
        barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;

        // First image – aspect ratio 15
        barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = 15;
        barcodeGenerator.Save(Path.Combine(outputFolder, "DatabarAspectRatio15.png"),
                              BarCodeImageFormat.Png);
        Console.WriteLine("Saved: DatabarAspectRatio15.png");

        // Second image – aspect ratio 30
        barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = 30;
        barcodeGenerator.Save(Path.Combine(outputFolder, "DatabarAspectRatio30.png"),
                              BarCodeImageFormat.Png);
        Console.WriteLine("Saved: DatabarAspectRatio30.png");
    }
}
```

**Sortie attendue**

L’exécution du programme crée un sous‑dossier `Barcodes` contenant :

- `DatabarAspectRatio15.png` – apparence plus haute, classique.  
- `DatabarAspectRatio30.png` – apparence plus plate, adaptée aux étiquettes larges.

Les deux images codent les mêmes données GTIN ; seules les proportions visuelles diffèrent.

---

## Extension de l’exemple (cas limites & variations)

### 1. Formats d’image différents

Aspose prend en charge BMP, JPEG, TIFF et SVG en plus du PNG. Remplacez simplement la valeur d’énumération :

```csharp
barcodeGenerator.Save(Path.Combine(outputFolder, "Databar.svg"),
                      BarCodeImageFormat.Svg);
```

Le SVG est vectoriel, ce qui signifie que vous pouvez le mettre à l’échelle sans perte de netteté — pratique pour les applications web responsives.

### 2. Personnalisation des couleurs

Vous pourriez avoir besoin d’un code‑barres blanc sur fond sombre. Définissez `ForeColor` et `BackColor` :

```csharp
barcodeGenerator.Parameters.Barcode.ForeColor = System.Drawing.Color.White;
barcodeGenerator.Parameters.Barcode.BackColor = System.Drawing.Color.Black;
```

### 3. Gestion des ratios d’aspect invalides

Aspose valide la plage (généralement 5‑50). Si vous fournissez une valeur hors de cette plage, une `ArgumentException` est levée. Enveloppez l’appel `Save` dans un `try‑catch` pour afficher un message convivial :

```csharp
try
{
    barcodeGenerator.Save(...);
}
catch (ArgumentException ex)
{
    Console.WriteLine($"Invalid aspect ratio: {ex.Message}");
}
```

### 4. Génération en lot

Lorsque vous avez une liste de GTIN, bouclez dessus, mettez à jour `CodeText`, et enregistrez chaque fichier avec un nom unique. L’objet générateur peut être réutilisé, ce qui maintient une faible consommation mémoire.

---

## Pièges courants & astuces avancées

- **N’oubliez jamais de définir `XDimension`** avant l’enregistrement ; la valeur par défaut (0,33 mm) peut produire des images floues sur des écrans basse résolution.  
- **Le ratio d’aspect est hauteur‑à‑largeur**, pas l’inverse. Un nombre plus grand rend le code‑barres *plus court* verticalement.  
- **Chemins de fichiers :** utilisez `Path.Combine` pour éviter les problèmes de séparateurs spécifiques à la plateforme—surtout si votre code s’exécute dans des conteneurs Linux.  
- **Licence :** Aspose.BarCode est commercial. En mode d’essai, un filigrane apparaît sur l’image. Enregistrez une licence tôt pour éviter les surprises en production.

---

## Conclusion

Vous savez maintenant comment **créer une image de code‑barres omnidirectionnel** avec Aspose, ajuster le ratio d’aspect et exporter des fichiers PNG—le tout en moins de 30 lignes de C#. Ce tutoriel a présenté le processus pas à pas, expliqué l’importance de chaque paramètre, et abordé des extensions comme les formats différents, les couleurs et la génération en lot.

Prêt pour le prochain défi ? Essayez de générer des QR codes, d’intégrer le code‑barres dans un PDF, ou d’intégrer la sortie dans une API ASP.NET Core. Les mêmes principes de **générer un code‑barres avec Aspose** s’appliquent à tous les types de codes‑barres, vous permettant de réutiliser ce que vous avez appris aujourd’hui.

Des questions ou des astuces à partager ? Laissez un commentaire ci‑dessous—bon codage !

## Que devriez‑vous apprendre ensuite ?

Les tutoriels suivants abordent des sujets étroitement liés qui s’appuient sur les techniques démontrées dans ce guide. Chaque ressource comprend des exemples de code complets avec des explications pas à pas pour vous aider à maîtriser des fonctionnalités API supplémentaires et explorer des approches d’implémentation alternatives dans vos propres projets.

- [How to generate Aztec barcode with custom aspect ratio using Aspose.BarCode for .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)
- [How to Create Barcode Aspose Java - Adjust Image Quality](/barcode/english/java/image-manipulation/adjusting-image-quality-barcode/)
- [How to Generate Barcode Image in Java with Aspose.BarCode](/barcode/english/java/barcode-rendering-techniques/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}