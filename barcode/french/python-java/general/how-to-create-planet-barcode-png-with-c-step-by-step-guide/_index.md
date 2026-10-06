---
category: general
date: 2026-09-07
description: Créez rapidement un code‑barres Planet au format PNG en C#. Apprenez
  à générer des images de code‑barres Planet à l’aide d’Aspose.BarCode avec des barres
  remplies et vides.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create planet barcode png
- how to generate planet barcode
language: fr
lastmod: 2026-09-07
og_description: Créez rapidement un PNG de code‑barres Planet en C#. Suivez ce guide
  pour apprendre à générer des images de code‑barres Planet avec des barres remplies
  et vides en utilisant Aspose.BarCode.
og_image_alt: Planet barcode PNG image showing filled bars and empty‑bars version
og_title: Créer un code‑barres planétaire PNG en C# – tutoriel complet de codage
schemas:
- author: Aspose
  dateModified: '2026-09-07'
  description: Create planet barcode PNG in C# quickly. Learn how to generate planet
    barcode images using Aspose.BarCode with filled and empty bars.
  headline: How to create planet barcode PNG with C# – step‑by‑step guide
  type: TechArticle
- description: Create planet barcode PNG in C# quickly. Learn how to generate planet
    barcode images using Aspose.BarCode with filled and empty bars.
  name: How to create planet barcode PNG with C# – step‑by‑step guide
  steps:
  - name: What if I need a different data format?
    text: 'Planet barcodes accept numeric strings up to 12 digits. If you pass a non‑numeric
      value, Aspose throws an `ArgumentException`. Validate the input before creating
      the generator:'
  - name: How do I change the image size without altering bar thickness?
    text: 'Use the `Resolution` property or scale the resulting bitmap after saving:'
  - name: Can I generate other image formats?
    text: Yes. Replace `BarCodeImageFormat.Png` with `BarCodeImageFormat.Jpeg`, `Bmp`,
      or `Gif`. The API supports all common raster formats.
  - name: What about color customization?
    text: 'Set `BarColor` and `BackColor` on the `Barcode` parameters:'
  type: HowTo
tags:
- barcode
- C#
- Aspose.BarCode
title: Comment créer un code‑barres planétaire PNG avec C# – guide pas à pas
url: /fr/python-java/general/how-to-create-planet-barcode-png-with-c-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Comment créer un code-barres Planet PNG avec C# – guide étape par étape

Si vous devez **créer des fichiers PNG de code-barres Planet** en C#, ce guide vous montre les étapes exactes. Que vous construisiez une intégration de service postal ou un tableau de bord logistique, vous apprendrez **comment générer des images de code-barres Planet** avec des barres remplies et vides en utilisant la bibliothèque Aspose.BarCode.

Dans ce tutoriel vous allez :

* Configurer le dossier de sortie pour vos images.  
* Configurer un `BarcodeGenerator` pour la symbologie Planet.  
* Générer un PNG avec le style par défaut des barres remplies.  
* Générer un PNG avec des barres vides pour un contraste visuel.  

Aucun service externe n’est requis—tout s’exécute localement sur .NET 6 ou version ultérieure.

## Prérequis

Avant de commencer, assurez‑vous d’avoir :

| Exigence | Pourquoi c’est important |
|----------|---------------------------|
| .NET 6 SDK (ou version plus récente) | Fournit le runtime pour l’application console C#. |
| Visual Studio 2022 ou VS Code | Tout IDE capable de compiler des projets C#. |
| Aspose.BarCode for .NET (package NuGet `Aspose.BarCode`) | Fournit la classe `BarcodeGenerator` utilisée pour rendre les codes-barres Planet. |
| Permission d’écriture sur un dossier du disque | Les fichiers PNG seront enregistrés à cet emplacement. |

Installez le package NuGet avec la commande suivante :

```bash
dotnet add package Aspose.BarCode
```

## Étape 1 : Créer un nouveau projet console

Ouvrez un terminal et exécutez :

```bash
dotnet new console -n PlanetBarcodeDemo
cd PlanetBarcodeDemo
```

Cela crée une application console C# minimale nommée **PlanetBarcodeDemo**.

## Étape 2 : Définir le répertoire de sortie

Le premier morceau de code détermine où les fichiers PNG générés seront stockés. L’utilisation d’un chemin absolu ou relatif fonctionne ; assurez‑vous simplement que le dossier existe ou laissez le programme le créer.

```csharp
using System;
using System.IO;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Program
{
    static void Main()
    {
        // Step 2: Define the output directory
        string outputDir = Path.Combine(Directory.GetCurrentDirectory(), "Barcodes");
        Directory.CreateDirectory(outputDir); // Guarantees the folder exists
```

*Pourquoi cette étape ?* Séparer la sortie du code source maintient votre projet propre et évite les écrasements accidentels.

## Étape 3 : Générer un code-barres Planet à barres remplies

Un code-barres Planet se compose de cercles concentriques (remplis par défaut). Nous configurons la dimension X (largeur en pixels de chaque barre) puis enregistrons l’image au format PNG.

```csharp
        // Step 3: Create a Planet barcode with the default (filled) bars
        BarcodeGenerator planetFilled = new BarcodeGenerator(EncodeTypes.Planet, "123456");
        planetFilled.Parameters.Barcode.XDimension.Pixels = 4; // Controls bar thickness

        // Save the filled‑bars barcode as PNG
        string filledPath = Path.Combine(outputDir, "PostalPlanetFilledBars.png");
        planetFilled.Save(filledPath, BarCodeImageFormat.Png);
        Console.WriteLine($"Filled‑bars barcode saved to: {filledPath}");
```

**Explication**

* `EncodeTypes.Planet` indique à Aspose d’utiliser la symbologie Planet, courante pour les services postaux.  
* `XDimension.Pixels = 4` donne une taille claire et imprimable sans mise à l’échelle manuelle.  
* La méthode `Save` écrit un fichier PNG ; vous pouvez également choisir JPEG ou BMP en modifiant le `BarCodeImageFormat`.

## Étape 4 : Générer un code-barres Planet à barres vides

Parfois, une représentation avec des barres vides (transparentes) est requise—par exemple, lorsque le code-barres est superposé sur un fond coloré. Définir `FilledBars` à `false` produit ce style.

```csharp
        // Step 4: Create a Planet barcode with empty bars
        BarcodeGenerator planetEmpty = new BarcodeGenerator(EncodeTypes.Planet, "123456");
        planetEmpty.Parameters.Barcode.XDimension.Pixels = 4;
        planetEmpty.Parameters.Barcode.FilledBars = false; // Switch to empty‑bars mode

        // Save the empty‑bars barcode as PNG
        string emptyPath = Path.Combine(outputDir, "PostalPlanetEmptyBars.png");
        planetEmpty.Save(emptyPath, BarCodeImageFormat.Png);
        Console.WriteLine($"Empty‑bars barcode saved to: {emptyPath}");
```

**Explication**

* `FilledBars = false` désactive les cercles pleins, ne laissant que les contours.  
* Tous les autres paramètres (dimension X, chaîne de données) restent identiques, garantissant que les deux images représentent les mêmes données.

## Étape 5 : Exécuter le programme et vérifier la sortie

Compilez et exécutez :

```bash
dotnet run
```

Vous devriez voir des messages dans la console confirmant l’enregistrement des fichiers, et le dossier `Barcodes` contiendra :

* `PostalPlanetFilledBars.png` – un code-barres Planet à barres remplies classique.  
* `PostalPlanetEmptyBars.png` – les mêmes données rendues avec des barres vides.

Ouvrez les PNG dans n’importe quel visualiseur d’images. Les deux images codent la chaîne numérique **123456** et peuvent être lues par les lecteurs de codes-barres postaux standards.

## Questions fréquentes et gestion des cas limites

### Et si j’ai besoin d’un format de données différent ?

Les codes-barres Planet acceptent des chaînes numériques jusqu’à 12 chiffres. Si vous fournissez une valeur non numérique, Aspose lève une `ArgumentException`. Validez l’entrée avant de créer le générateur :

```csharp
if (!Regex.IsMatch(data, @"^\d{1,12}$"))
    throw new ArgumentException("Planet barcode data must be numeric and up to 12 digits.");
```

### Comment modifier la taille de l’image sans changer l’épaisseur des barres ?

Utilisez la propriété `Resolution` ou redimensionnez le bitmap résultant après l’enregistrement :

```csharp
planetFilled.Parameters.ImageResolution = 300; // DPI for high‑resolution print
```

### Puis‑je générer d’autres formats d’image ?

Oui. Remplacez `BarCodeImageFormat.Png` par `BarCodeImageFormat.Jpeg`, `Bmp` ou `Gif`. L’API prend en charge tous les formats raster courants.

### Et la personnalisation des couleurs ?

Définissez `BarColor` et `BackColor` sur les paramètres du `Barcode` :

```csharp
planetFilled.Parameters.Barcode.BarColor = Color.DarkBlue;
planetFilled.Parameters.Barcode.BackColor = Color.LightYellow;
```

Ces options fonctionnent pour les versions à barres remplies et vides.

## Astuces pro pour la production

* **Mettez en cache le générateur** lorsque vous devez rendre de nombreux codes-barres avec les mêmes paramètres—l’initialisation répétée de l’objet ajoute une surcharge.  
* **Disposez** les objets `BarcodeGenerator` si vous en créez beaucoup dans une boucle (ils implémentent `IDisposable`).  
* **Validez le dossier de sortie** dès le départ pour éviter les exceptions d’exécution sur les répertoires protégés en écriture.  

## Conclusion

Vous savez maintenant comment **créer des fichiers PNG de code-barres Planet** en C# et comprendre **comment générer des images de code-barres Planet** avec des styles à barres remplies et vides. L’exemple complet et exécutable montre comment configurer le répertoire de sortie, configurer le `BarcodeGenerator` et enregistrer les résultats au format PNG.

Ensuite, vous pourriez explorer :

* Ajouter du **texte lisible** sous le code-barres (`planetFilled.Parameters.Caption.Visible = true`).  
* Intégrer les PNG générés dans une **facture PDF** en utilisant Aspose.PDF.  
* Passer à d’autres symbologies postales comme **IMB** ou **ITF** (`EncodeTypes.IMB`, `EncodeTypes.ITF`).  

N’hésitez pas à expérimenter avec l’épaisseur des barres, les couleurs et les résolutions d’image pour répondre aux exigences spécifiques de votre application. Bon codage !

## Que devriez‑vous apprendre ensuite ?

Les tutoriels suivants couvrent des sujets étroitement liés qui s’appuient sur les techniques démontrées dans ce guide. Chaque ressource comprend des exemples de code complets et fonctionnels avec des explications étape par étape pour vous aider à maîtriser des fonctionnalités supplémentaires de l’API et explorer des approches d’implémentation alternatives dans vos propres projets.

- [Créer une image de code-barres Planet en C# – Comment générer un code-barres postal](/barcode/english/python-java/general/create-planet-barcode-image-in-c-how-to-generate-postal-barc/)
- [Créer un code-barres Planet en C# – Guide complet étape par étape](/barcode/english/python-java/general/create-planet-barcode-in-c-full-step-by-step-guide/)
- [Générer un code-barres PNG avec Aspose.BarCode pour .NET : barres remplies unidimensionnelles](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-filled-bars-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}