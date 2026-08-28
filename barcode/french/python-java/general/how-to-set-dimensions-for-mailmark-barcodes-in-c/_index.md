---
category: general
date: 2026-08-22
description: Apprenez à définir les dimensions des codes‑barres Mailmark en C# et
  à les enregistrer en images PNG. Comprend le code complet, des explications et des
  astuces.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to set dimensions
- Mailmark barcode C# example
- BarcodeGenerator dimensions
- set barcode size in C#
- save barcode as PNG
language: fr
lastmod: 2026-08-22
og_description: Comment définir les dimensions des codes‑barres Mailmark en C# et
  les exporter en fichiers PNG. Suivez l’exemple complet et évitez les pièges courants.
og_image_alt: Screenshot of two generated Mailmark barcode PNG files showing different
  dimensions
og_title: Comment définir les dimensions des codes‑barres Mailmark en C# – guide étape
  par étape
schemas:
- author: Aspose
  dateModified: '2026-08-22'
  description: Learn how to set dimensions for Mailmark barcodes in C# and save them
    as PNG images. Includes full code, explanations, and tips.
  headline: How to set dimensions for Mailmark barcodes in C#
  type: TechArticle
tags:
- C#
- barcode
- Mailmark
- image generation
title: Comment définir les dimensions des codes-barres Mailmark en C#
url: /fr/python-java/general/how-to-set-dimensions-for-mailmark-barcodes-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Comment définir les dimensions des codes-barres Mailmark en C#

Si vous avez besoin de **définir les dimensions** d'un code-barres Mailmark en C#, ce guide montre les étapes exactes. Vous verrez comment configurer la X‑dimension et la hauteur des barres, puis enregistrer le code-barres en tant qu'image PNG sans outil supplémentaire.

Générer des codes-barres postaux est une tâche courante lors de la création d'un logiciel d'étiquetage postal, mais la taille par défaut ne correspond souvent pas aux exigences de l'imprimante ou de la mise en page. À la fin de ce tutoriel, vous serez capable de contrôler précisément la taille du code-barres et de produire deux types Mailmark valides (type C et type L) prêts à être imprimés.

**Ce que vous apprendrez**

* Comment définir la X‑dimension (largeur du module) et la hauteur des barres pour un `BarcodeGenerator`.
* Comment enregistrer le code-barres généré en fichier PNG en utilisant `BarCodeImageFormat`.
* Écueils courants tels que des chemins de dossiers invalides ou des valeurs de dimensions non prises en charge.
* Conseils pour réutiliser la même configuration sur plusieurs codes-barres.

## Prérequis

* .NET 6.0 ou version ultérieure (le code fonctionne également avec .NET Framework 4.6+).
* Le package NuGet **Aspose.BarCode for .NET** (ou toute bibliothèque compatible qui fournit `BarcodeGenerator`, `EncodeTypes` et `BarCodeImageFormat`).
* Familiarité de base avec la syntaxe C# et les opérations d'E/S de fichiers.

> **Astuce pro** : Installez le package avec la commande CLI  
> `dotnet add package Aspose.BarCode` pour garder votre projet propre.

## Étape 1 : Définir le dossier de sortie

Avant de créer un code-barres, vous devez décider où les fichiers PNG seront écrits. Utiliser un chemin absolu évite les surprises sur différentes machines.

```csharp
// Step 1: Define the folder where the barcode images will be saved
string outputFolder = @"C:\Temp\Barcodes\";

// Ensure the directory exists; create it if necessary
if (!Directory.Exists(outputFolder))
{
    Directory.CreateDirectory(outputFolder);
}
```

*Pourquoi c'est important* : Si le dossier n'existe pas, `Save` lève une `IOException`. L'appel `Directory.CreateDirectory` est idempotent — il ne fait rien si le dossier existe déjà.

## Étape 2 : Créer un code-barres Mailmark de type C et **définir les dimensions**

Le type C de Mailmark encode une chaîne alphanumérique de 20 caractères. Après avoir initialisé le générateur, vous pouvez **définir les dimensions** via l'objet `Parameters.Barcode`.

```csharp
// Step 2: Create a Mailmark C‑type barcode, configure its size, and save it as PNG
BarcodeGenerator mailmarkC = new BarcodeGenerator(EncodeTypes.Mailmark, "21B2254800659JW5O9QA6Y");

// Set the width of a single module (X‑dimension) to 4 pixels
mailmarkC.Parameters.Barcode.XDimension.Pixels = 4;

// Set the overall bar height to 50 pixels
mailmarkC.Parameters.Barcode.BarHeight.Pixels = 50;

// Save the image; the second argument specifies PNG format
mailmarkC.Save($"{outputFolder}PostalMailmarkCType.png", BarCodeImageFormat.Png);
```

### Pourquoi choisir ces valeurs ?

* **La X‑dimension** contrôle la largeur de la plus petite barre (un « module »). Une valeur de `4` pixels produit un code-barres facilement lisible par la plupart des imprimantes laser tout en gardant la taille du fichier modeste.
* **BarHeight** détermine la taille verticale des barres. `50` pixels est une hauteur courante pour les étiquettes postales standard, mais vous pouvez l'augmenter pour des formats plus grands.

> **Cas limite** : Certaines imprimantes exigent une hauteur minimale de 30 px. Définir une hauteur inférieure à la capacité de l'imprimante peut rendre le code-barres illisible.

## Étape 3 : Créer un code-barres Mailmark de type L et **définir les dimensions**

Le type L utilise une chaîne de données plus longue (jusqu'à 30 caractères). La même approche de définition des dimensions s'applique.

```csharp
// Step 3: Create a Mailmark L‑type barcode, configure its size, and save it as PNG
BarcodeGenerator mailmarkL = new BarcodeGenerator(EncodeTypes.Mailmark, "41038422416563762EF61AH8T");

// Reuse the same dimension settings for consistency
mailmarkL.Parameters.Barcode.XDimension.Pixels = 4;
mailmarkL.Parameters.Barcode.BarHeight.Pixels = 50;

// Save the L‑type barcode image
mailmarkL.Save($"{outputFolder}PostalMailmarkLType.png", BarCodeImageFormat.Png);
```

### Réutilisation de la configuration

Si vous générez de nombreux codes-barres avec des dimensions identiques, envisagez d'extraire la configuration dans une méthode d'assistance :

```csharp
void ApplyStandardDimensions(BarcodeGenerator generator)
{
    generator.Parameters.Barcode.XDimension.Pixels = 4;
    generator.Parameters.Barcode.BarHeight.Pixels = 50;
}
```

Appeler `ApplyStandardDimensions(mailmarkC)` et `ApplyStandardDimensions(mailmarkL)` réduit la duplication et rend les modifications futures (par ex., passer à des modules de 5 pixels) éditables en une seule ligne.

## Étape 4 : Vérifier les fichiers PNG générés

Après avoir exécuté le programme, ouvrez les deux fichiers PNG dans n'importe quel visualiseur d'images. Vous devriez voir deux codes-barres Mailmark distincts, chacun de 4 px par module et 50 px de hauteur.

*Sortie attendue*

| Nom du fichier                 | Dimensions approximatives (px) |
|-------------------------------|-------------------------------|
| `PostalMailmarkCType.png`     | 4 px × module × N modules |
| `PostalMailmarkLType.png`     | 4 px × module × N modules |

La largeur exacte dépend de la longueur des données encodées, mais la hauteur sera toujours **50 px** car nous avons défini `BarHeight.Pixels`.

## Problèmes courants et comment les éviter

| Problème                         | Symptôme                                      | Solution |
|----------------------------------|-----------------------------------------------|----------|
| Chemin de dossier invalide       | `IOException: Could not find a part of the path` | Utilisez `Path.Combine` avec `Environment.SpecialFolder` ou vérifiez la chaîne du chemin. |
| X‑dimension définie à 0 ou négative | Le code-barres apparaît comme un bloc plein   | Assurez‑vous que `XDimension.Pixels` est un entier positif (minimum 1). |
| EncodeTypes.Mailmark non pris en charge | `ArgumentException` at generator construction | Vérifiez que vous disposez d'une version récente de la bibliothèque Aspose.BarCode incluant la prise en charge de Mailmark. |
| Enregistrement avec un mauvais format d'image | Fichier PNG corrompu                         | Utilisez `BarCodeImageFormat.Png` (ou `Jpeg` si vous avez besoin d'un autre format). |

## Extension de l'exemple

* **Tailles différentes** – Changez `XDimension.Pixels` à 3 pour un code-barres plus compact, ou augmentez `BarHeight.Pixels` à 70 pour des étiquettes plus grandes.
* **Génération par lots** – Parcourez une collection de chaînes de données, en appliquant les mêmes paramètres de dimensions à chaque itération.
* **Autres formats d'image** – Remplacez `BarCodeImageFormat.Png` par `BarCodeImageFormat.Jpeg` ou `BarCodeImageFormat.Bmp` si votre flux de travail le nécessite.

## Conclusion

Vous savez maintenant **comment définir les dimensions** des codes-barres Mailmark en C# et les exporter en fichiers PNG. En configurant `XDimension.Pixels` et `BarHeight.Pixels`, vous contrôlez la taille visuelle des deux types C et L, garantissant qu'ils respectent les spécifications d'imprimante et les contraintes de mise en page.  

À partir de là, vous pouvez expérimenter différentes valeurs de dimensions, intégrer le code dans un système d'étiquetage postal plus vaste, ou générer des lots de codes-barres pour des opérations d'envoi en masse.

---

*Prochaines étapes* : explorez les **dimensions du BarcodeGenerator** pour les QR codes, ou lisez la documentation Aspose.BarCode sur **la définition du DPI** pour des impressions haute résolution. Si vous devez intégrer le code-barres dans un PDF, combinez cette approche avec la bibliothèque **Aspose.PDF** pour une solution complète de bout en bout.

## Que devriez‑vous apprendre ensuite ?

Les tutoriels suivants couvrent des sujets étroitement liés qui s'appuient sur les techniques démontrées dans ce guide. Chaque ressource inclut des exemples de code complets avec des explications étape par étape pour vous aider à maîtriser des fonctionnalités API supplémentaires et explorer des approches d'implémentation alternatives dans vos propres projets.

- [Comment définir la bordure pour la personnalisation du code-barres ITF-14](/barcode/english/net/itf-14-barcode-customization/)
- [Comment configurer les codes Patch avec Aspose.BarCode pour .NET](/barcode/english/net/patch-code-configuration/)
- [Comment générer des codes-barres DataMatrix en utilisant Aspose.BarCode pour .NET – Guide étape par étape](/barcode/english/net/datamatrix-barcode-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}