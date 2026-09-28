---
category: general
date: 2026-08-25
description: Créer un code‑barres RM4SCC en C# avec un code pas à pas et apprendre
  à régler la hauteur du code‑barres pour un dimensionnement précis.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create rm4scc barcode c#
- how to set barcode height
language: fr
lastmod: 2026-08-25
og_description: Créez un code‑barres RM4SCC en C# avec Aspose.BarCode et apprenez
  à définir la hauteur du code‑barres pour un contrôle précis dans vos applications
  .NET.
og_image_alt: Screenshot of an RM4SCC barcode generated with C#
og_title: Créer un code‑barres RM4SCC C# – guide pour régler la hauteur du code‑barres
schemas:
- author: Aspose
  dateModified: '2026-08-25'
  description: Create RM4SCC barcode C# with step‑by‑step code and learn how to set
    barcode height for precise sizing.
  headline: Create RM4SCC barcode C# and set barcode height
  type: TechArticle
tags:
- barcode
- C#
- RM4SCC
- Aspose.BarCode
title: Créer un code‑barres RM4SCC en C# et définir la hauteur du code‑barres
url: /fr/python-java/general/create-rm4scc-barcode-c-and-set-barcode-height/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Créer un code‑barres RM4SCC C# et définir la hauteur du code‑barres

Créez rapidement un code‑barres RM4SCC C# à l’aide de la bibliothèque Aspose.BarCode. Ce tutoriel montre **comment définir la hauteur du code‑barres** et personnaliser d’autres propriétés visuelles afin que le code‑barres s’adapte exactement à votre mise en page.

Vous verrez un programme console complet, prêt à être exécuté, qui génère trois fichiers PNG :

* un code‑barres Planet de hauteur par défaut (pour comparaison)  
* un code‑barres RM4SCC avec une hauteur manuelle de 100 px  
* un code‑barres Planet avec des barres vides (non remplies)  

L’exemple suppose que vous disposez de Visual Studio 2022 (ou de tout IDE .NET 6+) et d’une licence valide d’Aspose.BarCode pour .NET ou d’une copie d’évaluation.

## Prérequis

| Exigence | Raison |
|----------|--------|
| .NET 6 SDK (ou version ultérieure) | Fournit le runtime pour l’application console |
| Package NuGet Aspose.BarCode pour .NET | Fournit `BarcodeGenerator`, `EncodeTypes` et les API d’exportation d’image |
| Connaissances de base en C# | Nécessaires pour comprendre le flux du code |

Installez le package NuGet avec :

```bash
dotnet add package Aspose.BarCode
```

> **Astuce pro :** Si vous exécutez le code sans licence, les images générées contiendront un petit filigrane Aspose.

## Étape 1 : Configurer la structure du projet

Créez un nouveau projet console et ajoutez les directives `using` nécessaires :

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;
using Aspose.BarCode.BarCodeImageFormat; // optional, you can use the enum directly
```

Les instructions `using` vous donnent accès aux classes du générateur de code‑barres et à l’énumération du format PNG.

## Étape 2 : Définir le dossier de sortie

Choisissez un dossier où les fichiers PNG seront enregistrés. Le dossier doit exister avant d’appeler `Save`.

```csharp
// Step 1: Define the output folder
string outputFolder = "GeneratedBarcodes/";

// Ensure the directory exists
System.IO.Directory.CreateDirectory(outputFolder);
```

Créer le répertoire par programme évite une *FileNotFoundException* lorsque le code s’exécute sur une machine neuve.

## Étape 3 : Générer un code‑barres Planet avec la hauteur par défaut (référence)

Le code‑barres Planet n’est pas le sujet principal de ce guide, mais il fournit une référence visuelle pour comparer avec le code‑barres RM4SCC à taille manuelle.

```csharp
// Step 2: Generate a Planet barcode with the default (auto) height
BarcodeGenerator planetAuto = new BarcodeGenerator(EncodeTypes.Planet, "123456");
planetAuto.Parameters.Barcode.XDimension.Pixels = 4; // controls bar width
planetAuto.Save($"{outputFolder}PostalPlanetBarHeightNone.png", BarCodeImageFormat.Png);
```

*Pourquoi c’est important :*  
`XDimension` détermine la largeur d’une seule barre. Le garder constant tout en modifiant `BarHeight` isole l’effet de la hauteur.

## Étape 4 : **Créer un code‑barres RM4SCC C#** – définir une hauteur manuelle

Nous abordons maintenant la tâche principale : **créer un code‑barres RM4SCC C#** et contrôler explicitement sa hauteur.

```csharp
// Step 3: Generate an RM4SCC barcode with a manual height of 100 px
BarcodeGenerator rm4sccManual = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");
rm4sccManual.Parameters.Barcode.XDimension.Pixels = 4;           // same bar width as Planet example
rm4sccManual.Parameters.Barcode.BarHeight.Pixels = 100;          // <-- how to set barcode height
rm4sccManual.Save($"{outputFolder}PostalRM4SCCBarHeight100Pixels.png", BarCodeImageFormat.Png);
```

### Comment définir la hauteur du code‑barres

La propriété `BarHeight` se trouve sous `Parameters.Barcode`. Elle accepte une valeur `float` exprimée en **pixels**, **points** ou **millimètres** selon l’unité (`Pixels`, `Points`, `Millimeters`) que vous choisissez. Dans l’exemple, nous utilisons `Pixels` parce que le format de sortie est PNG.

Si vous avez besoin d’une hauteur en millimètres, changez d’abord l’unité :

```csharp
rm4sccManual.Parameters.Barcode.BarHeight.Unit = BarHeightUnit.Millimeters;
rm4sccManual.Parameters.Barcode.BarHeight.Value = 25; // 25 mm tall
```

## Étape 5 : Générer un code‑barres Planet avec des barres vides (non remplies)

Cette étape montre une autre propriété utile — `FilledBars`. La définir à `false` crée un code‑barres « creux », ce qui peut être pratique pour le design.

```csharp
// Step 4: Generate a Planet barcode with empty (unfilled) bars
BarcodeGenerator planetEmptyBars = new BarcodeGenerator(EncodeTypes.Planet, "123456");
planetEmptyBars.Parameters.Barcode.XDimension.Pixels = 4;
planetEmptyBars.Parameters.Barcode.FilledBars = false; // makes bars transparent
planetEmptyBars.Save($"{outputFolder}PostalPlanetEmptyBars.png", BarCodeImageFormat.Png);
```

## Programme complet, exécutable

Copiez le code suivant dans `Program.cs`. Compilez et exécutez le projet ; trois fichiers PNG apparaîtront dans le dossier `GeneratedBarcodes`.



## Que devriez‑vous apprendre ensuite ?

Les tutoriels suivants couvrent des sujets étroitement liés qui s’appuient sur les techniques démontrées dans ce guide. Chaque ressource comprend des exemples de code complets et fonctionnels avec des explications pas à pas pour vous aider à maîtriser d’autres fonctionnalités de l’API et explorer des approches d’implémentation alternatives dans vos propres projets.

- [Comment créer un code‑barres code128 Java et définir la hauteur des barres](/barcode/english/java/barcode-configuration/setting-bars-height/)
- [Comment créer une zone silencieuse de code‑barres .NET pour Code 16K avec Aspose.BarCode](/barcode/english/net/code-16k-encoding/code-16k-quiet-zone-settings/)
- [Comment créer un code‑barres Aztec avec Aspose.BarCode pour .NET](/barcode/english/net/aztec-barcode-encoding/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}