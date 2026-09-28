---
category: general
date: 2026-08-22
description: Créez un code‑barres FCC 11 en C# avec Aspose.BarCode. Apprenez le code
  étape par étape, configurez les dimensions et générez des images PNG pour Australia
  Post.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create fcc 11 barcode
- Australia Post barcode
- Aspose.BarCode C#
- FCC 59 barcode
- FCC 62 barcode
- N‑Table encoding
- C‑Table encoding
language: fr
lastmod: 2026-08-22
og_description: Créez un code‑barres FCC 11 en C# avec Aspose.BarCode. Suivez ce tutoriel
  concis pour générer des codes‑barres PNG pour Australia Post, y compris les variantes
  FCC 59 et FCC 62.
og_image_alt: Screenshot showing a generated FCC 11 barcode image
og_title: Créer un code‑barres FCC 11 en C# – guide complet d’Aspose.BarCode
schemas:
- author: Aspose
  dateModified: '2026-08-22'
  description: Create FCC 11 barcode in C# using Aspose.BarCode. Learn step‑by‑step
    code, configure dimensions, and generate PNG images for Australia Post.
  headline: How to create FCC 11 barcode in C# with Aspose.BarCode
  type: TechArticle
- description: Create FCC 11 barcode in C# using Aspose.BarCode. Learn step‑by‑step
    code, configure dimensions, and generate PNG images for Australia Post.
  name: How to create FCC 11 barcode in C# with Aspose.BarCode
  steps:
  - name: 4.1 FCC 59 with N‑Table encoding
    text: '```csharp barcodeGenerator = new BarcodeGenerator( EncodeTypes.AustraliaPost,
      "590123456701234"); // FCC 59 data (prefix 59 + 13‑digit payload)'
  - name: 4.2 FCC 62 with N‑Table encoding
    text: '```csharp barcodeGenerator = new BarcodeGenerator( EncodeTypes.AustraliaPost,
      "620123456701234"); // FCC 62 data (prefix 62 + 13‑digit payload)'
  - name: 4.3 FCC 62 with C‑Table encoding
    text: '```csharp barcodeGenerator = new BarcodeGenerator( EncodeTypes.AustraliaPost,
      "6201234567ASPOSE"); // FCC 62 data with alphanumeric suffix'
  - name: 4.4 FCC 62 with Other encoding
    text: '```csharp barcodeGenerator = new BarcodeGenerator( EncodeTypes.AustraliaPost,
      "6201234567321032103210"); // Long payload for "Other" table'
  type: HowTo
tags:
- barcode
- C#
- Aspose
- AustraliaPost
title: Comment créer un code‑barres FCC 11 en C# avec Aspose.BarCode
url: /fr/python-java/general/how-to-create-fcc-11-barcode-in-c-with-aspose-barcode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Comment créer un code-barres FCC 11 en C# avec Aspose.BarCode

Si vous devez **créer un code-barres FCC 11** dans une application .NET, ce guide vous montre le code exact requis. Vous verrez comment configurer les dimensions du code-barres, choisir la table d’encodage appropriée et enregistrer le résultat sous forme de fichier PNG.

Générer des codes-barres Australia Post est une exigence courante pour la logistique, les systèmes de courrier et le suivi d’inventaire. Ce tutoriel couvre le format FCC 11 et montre également comment produire des codes-barres FCC 59 et FCC 62 avec différentes tables d’encodage, afin que vous puissiez réutiliser le même modèle pour d’autres services postaux.

## Ce dont vous avez besoin

* .NET 6.0 SDK ou version ultérieure installé  
* Visual Studio 2022 (ou tout IDE compatible C#)  
* Une licence valide pour **Aspose.BarCode for .NET** – l’édition communautaire fonctionne pour l’évaluation  
* Permission d’écriture sur un dossier où les fichiers PNG seront enregistrés  

Ces prérequis garantissent que le code se compile et s’exécute sans configuration supplémentaire.

## Étape 1 : Installer le package NuGet Aspose.BarCode

Ouvrez un terminal dans le dossier du projet et exécutez :

```bash
dotnet add package Aspose.BarCode
```

La commande ajoute la dernière version stable de la bibliothèque à votre fichier de projet. Le package contient la classe `BarcodeGenerator` utilisée tout au long de ce tutoriel.

## Étape 2 : Définir le dossier de sortie

Créez un dossier où les images générées seront stockées. Le chemin peut être absolu ou relatif à l’exécutable.

```csharp
// Step 2: Define the output folder
string outputPath = Path.Combine(Environment.CurrentDirectory, "Barcodes");
Directory.CreateDirectory(outputPath);
```

`Directory.CreateDirectory` garantit que le dossier existe, évitant les erreurs d’exécution lorsque la méthode `Save` écrit le fichier.

## Étape 3 : Générer le code-barres FCC 11

Le format FCC 11 est l’encodage par défaut des codes-barres postaux d’Australia Post. Le code suivant crée un code-barres qui encode la chaîne numérique `1101234567`.

```csharp
// Step 3: Create a BarcodeGenerator for FCC 11
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.AustraliaPost,      // Use the Australia Post symbology
    "1101234567");                  // Data for FCC 11

// Configure visual appearance
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 4;   // Width of a single module
barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 50; // Height of the barcode

// Save as PNG
string fcc11Path = Path.Combine(outputPath, "PostalAustraliaPostFCC11.png");
barcodeGenerator.Save(fcc11Path, BarCodeImageFormat.Png);
```

**Pourquoi cela fonctionne :**  
* `EncodeTypes.AustraliaPost` indique à la bibliothèque d’appliquer les règles d’encodage d’Australia Post.  
* La chaîne de données `1101234567` suit la spécification FCC 11 : les deux premiers chiffres (`11`) identifient le format, suivis d’une référence client à 7 chiffres.  
* `XDimension` et `BarHeight` contrôlent la taille du code-barres imprimé, ce qui est important pour la lisibilité par le scanner.  

Après avoir exécuté le programme, vous trouverez `PostalAustraliaPostFCC11.png` dans le dossier `Barcodes`. L’image ressemble à ceci :

![create fcc 11 barcode example](https://example.com/fcc11.png "FCC 11 barcode generated by Aspose.BarCode")

## Étape 4 : Créer des codes-barres Australia Post supplémentaires (facultatif)

Bien que l’objectif principal soit de **créer un code-barres FCC 11**, vous avez souvent besoin de codes-barres FCC 59 ou FCC 62 pour différentes classes de courrier. Le code ci‑dessous réutilise la même instance `BarcodeGenerator`, ne changeant que la chaîne de données et la table d’encodage optionnelle.

### 4.1 FCC 59 avec encodage N‑Table

```csharp
barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.AustraliaPost,
    "590123456701234"); // FCC 59 data (prefix 59 + 13‑digit payload)

barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 4;
barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 50;

// Use N‑Table for customer information interpretation
barcodeGenerator.Parameters.Barcode.AustralianPost.AustralianPostEncodingTable =
    CustomerInformationInterpretingType.NTable;

string fcc59Path = Path.Combine(outputPath, "PostalAustraliaPostFCC59NTable.png");
barcodeGenerator.Save(fcc59Path, BarCodeImageFormat.Png);
```

### 4.2 FCC 62 avec encodage N‑Table

```csharp
barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.AustraliaPost,
    "620123456701234"); // FCC 62 data (prefix 62 + 13‑digit payload)

barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 4;
barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 50;
barcodeGenerator.Parameters.Barcode.AustralianPost.AustralianPostEncodingTable =
    CustomerInformationInterpretingType.NTable;

string fcc62NPath = Path.Combine(outputPath, "PostalAustraliaPostFCC62NTable.png");
barcodeGenerator.Save(fcc62NPath, BarCodeImageFormat.Png);
```

### 4.3 FCC 62 avec encodage C‑Table

```csharp
barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.AustraliaPost,
    "6201234567ASPOSE"); // FCC 62 data with alphanumeric suffix

barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 4;
barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 50;
barcodeGenerator.Parameters.Barcode.AustralianPost.AustralianPostEncodingTable =
    CustomerInformationInterpretingType.CTable;

string fcc62CPath = Path.Combine(outputPath, "PostalAustraliaPostFCC62CTable.png");
barcodeGenerator.Save(fcc62CPath, BarCodeImageFormat.Png);
```

### 4.4 FCC 62 avec autre encodage

```csharp
barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.AustraliaPost,
    "6201234567321032103210"); // Long payload for "Other" table

barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 4;
barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 50;
barcodeGenerator.Parameters.Barcode.AustralianPost.AustralianPostEncodingTable =
    CustomerInformationInterpretingType.Other;

string fcc62OtherPath = Path.Combine(outputPath, "PostalAustraliaPostFCC62OtherTable.png");
barcodeGenerator.Save(fcc62OtherPath, BarCodeImageFormat.Png);
```

Les quatre images sont enregistrées côte à côte dans le même dossier, ce qui facilite la comparaison des différences visuelles.

## Étape 5 : Comprendre les tables d’encodage

Australia Post définit trois tables d’encodage :

* **N‑Table** – interprète les informations client numériques. Utilisez‑la lorsque la charge utile ne contient que des chiffres.  
* **C‑Table** – prend en charge les caractères alphanumériques, utile pour les numéros de référence incluant des lettres.  
* **Other** – une solution de secours pour les formats de données personnalisés ou étendus.  

Choisir la bonne table garantit que le scanner de code-barres décode l’information exactement comme prévu. Si vous omettez la propriété `AustralianPostEncodingTable`, la bibliothèque utilise par défaut la N‑Table, ce qui peut tronquer les caractères non numériques.

## Astuces, cas limites et pièges courants

| Situation | Approche recommandée |
|-----------|----------------------|
| La longueur de la chaîne de données est plus courte que requis | Compléter la partie numérique avec des zéros en tête pour respecter la spécification FCC. |
| Le code-barres apparaît flou lorsqu’il est imprimé | Augmenter `XDimension` à 5 ou 6 pixels et vérifier les paramètres DPI de l’imprimante. |
| Le scanner renvoie « format invalide » | Vérifier que la table d’encodage correcte (N‑Table, C‑Table, Other) correspond à la charge de données. |
| Exécution sous Linux sans interface graphique | S’assurer que le package `System.Drawing.Common` est référencé, ou utiliser la méthode `Save` avec `BarCodeImageFormat.Png` qui ne nécessite pas de contexte d’affichage. |
| Besoin d’un format d’image différent | Remplacer `BarCodeImageFormat.Png` par `BarCodeImageFormat.Jpeg` ou `BarCodeImageFormat.Tiff` selon les besoins. |

Ces astuces pratiques proviennent de déploiements réels de solutions de codes-barres postaux.

## Exemple complet exécutable

Voici un programme autonome que vous pouvez copier dans un nouveau projet console (`dotnet new console`) et exécuter sans modification.



## Que devriez‑vous apprendre ensuite ?

Les tutoriels suivants couvrent des sujets étroitement liés qui s’appuient sur les techniques démontrées dans ce guide. Chaque ressource comprend des exemples de code complets avec des explications étape par étape pour vous aider à maîtriser des fonctionnalités API supplémentaires et explorer des approches d’implémentation alternatives dans vos propres projets.

- [Comment générer un code-barres Java – code-barres Australia Post avec Aspose](/barcode/english/java/barcode-configuration/generating-australia-post-barcode/)
- [Créer un encodage Databar unidimensionnel GS1 avec Aspose.BarCode](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-gs1-encoding/)
- [Comment créer une zone silencieuse de code-barres .NET pour Code 16K avec Aspose.BarCode](/barcode/english/net/code-16k-encoding/code-16k-quiet-zone-settings/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}