---
category: general
date: 2026-07-18
description: Créez des images de code‑barres GS1 en C# avec ce guide étape par étape
  sur la façon de générer des codes‑barres C# en utilisant Aspose.BarCode – pas de
  fioritures, juste du code fonctionnel.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create gs1 barcode images
- how to generate barcode c#
language: fr
lastmod: 2026-07-18
og_description: Créez des images de code‑barres GS1 en C# avec ce tutoriel concis.
  Apprenez à générer des codes‑barres C# en utilisant Aspose.BarCode et à enregistrer
  des fichiers PNG en quelques secondes.
og_image_alt: Screenshot of a generated GS1‑MicroPDF417 barcode saved as a PNG file
og_title: Créer des images de codes‑barres GS1 en C# – Guide complet
schemas:
- author: Aspose
  dateModified: '2026-07-18'
  description: Create GS1 barcode images in C# with this step‑by‑step guide on how
    to generate barcode C# using Aspose.BarCode – no fluff, just working code.
  headline: Create GS1 Barcode Images in C# – How to Generate Barcode C# Quickly
  type: TechArticle
tags:
- barcode
- csharp
- gs1
- aspose
title: Créer des images de code‑barres GS1 en C# – Comment générer rapidement un code‑barres
  en C#
url: /fr/net/gs1-barcode-encoding/create-gs1-barcode-images-in-c-how-to-generate-barcode-c-qui/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Créer des images de gs1 barcode en C# – Comment générer du barcode C#

Vous avez déjà eu besoin de **créer des gs1 barcode images** pour une étiquette d'emballage mais vous n'étiez pas sûr de par où commencer ? Vous n'êtes pas seul. Dans ce tutoriel, vous verrez exactement **comment générer du barcode c#** qui produit des images GS1‑MicroPDF417 en quelques minutes.

Nous parcourrons l’ensemble du processus — installation de la bibliothèque, configuration du générateur, échange des données AI (Application Identifier), et enfin sauvegarde d’un ensemble de fichiers PNG. À la fin, vous disposerez d’une application console prête à l’emploi qui génère une poignée d’images de code-barres GS1, chacune reflétant une combinaison AI différente.

---

## Ce dont vous avez besoin

- **.NET 6+** (ou .NET Framework 4.6+). Le runtime le plus récent fonctionne mieux avec Aspose.BarCode.
- **Aspose.BarCode for .NET** – installer via NuGet (`Install-Package Aspose.BarCode`).
- Un dossier sur le disque où les fichiers PNG seront écrits (nous l’appellerons `YOUR_DIRECTORY`).
- Une compréhension de base de la syntaxe C# — rien de compliqué requis.

Si vous avez déjà tout cela, super. Sinon, récupérez d’abord le package NuGet ; c’est une seule ligne dans la console du gestionnaire de packages et cela prend en charge toutes les dépendances.

---

## Étape 1 : Configurer un projet console minimal

Ouvrez votre IDE préféré (Visual Studio, Rider ou VS Code) et créez un nouveau projet console :

```bash
dotnet new console -n Gs1BarcodeDemo
cd Gs1BarcodeDemo
dotnet add package Aspose.BarCode
```

Remplacez le `Program.cs` auto‑généré par le code présenté dans les étapes suivantes. Ce squelette nous offre une toile vierge pour **créer des gs1 barcode images** sans encombrement supplémentaire.

---

## Étape 2 : Comment créer des gs1 barcode images – Initialiser le générateur

Le cœur de l’opération est `BarcodeGenerator`. Nous l’initialiserons avec une valeur GS1‑MicroPDF417, par exemple `(17)991231(10)ABCD`. Cette chaîne encode deux AI : date d’expiration (17) et lot (10).

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Program
{
    static void Main()
    {
        // Initialize the generator with a GS1‑MicroPDF417 barcode type
        BarcodeGenerator barcodeGen = new BarcodeGenerator(
            EncodeTypes.GS1MicroPdf417,
            "(17)991231(10)ABCD");
```

**Pourquoi c’est important :** `EncodeTypes.GS1MicroPdf417` indique à Aspose que nous utilisons un format GS1 compact et à haute densité. Commencer avec une chaîne AI valide garantit que le premier PNG que nous sauvegardons est déjà conforme aux normes GS1.

---

## Étape 3 : Ajuster les paramètres visuels – Affiner la taille et la mise en page

Un code‑barres trop petit ou de forme étrange ne sera pas lisible. Ici, nous définissons la X‑dimension (largeur du module) à 2 pixels, limitons le nombre de colonnes pour garder l’image étroite, et activons le lien afin que plusieurs codes‑barres puissent être concaténés plus tard si nécessaire.

```csharp
        // Set visual parameters for a crisp, scannable image
        barcodeGen.Parameters.Barcode.XDimension.Pixels = 2;      // module width
        barcodeGen.Parameters.Barcode.Pdf417.Columns = 2;        // column count
        barcodeGen.Parameters.Barcode.Pdf417.IsLinked = true;   // enable linking
```

**Astuce :** Si vous avez besoin d’un code‑barres plus haut, augmentez `Rows` plutôt que les colonnes. Ajustez `XDimension` pour atteindre la taille minimale de module de 0,33 mm requise par la plupart des scanners.

---

## Étape 4 : Enregistrer le premier code‑barres – AI 17 + AI 10

Nous écrivons maintenant réellement l’image sur le disque. Le nom du fichier reflète les AI utilisés, ce qui facilite la localisation ultérieure.

```csharp
        // Save the first image (AI 17 + AI 10)
        barcodeGen.Save(@"YOUR_DIRECTORY\GS1MicroPdf417_17_10.png",
                        BarCodeImageFormat.Png);
```

Après avoir exécuté le programme, vous devriez voir un PNG net dans `YOUR_DIRECTORY`. Ouvrez‑le — vous remarquerez les petites barres et le texte lisible sous‑jacent. C’est le premier de nombreux **gs1 barcode images** que nous générerons.

---

## Étape 5 : Modifier les données encodées – Réutiliser le même générateur

Au lieu de créer un nouveau `BarcodeGenerator` pour chaque paire d’AI, nous échangeons simplement la propriété `CodeText` et appelons à nouveau `Save`. Cette approche est la façon la plus efficace de **créer des gs1 barcode images** en masse.

```csharp
        // AI 15 (best before) + AI 10 (batch)
        barcodeGen.CodeText = "(15)991231(10)ABCD";
        barcodeGen.Save(@"YOUR_DIRECTORY\GS1MicroPdf417_15_10.png",
                        BarCodeImageFormat.Png);

        // AI 13 (production date) + AI 21 (serial)
        barcodeGen.CodeText = "(13)991231(21)ABCD";
        barcodeGen.Save(@"YOUR_DIRECTORY\GS1MicroPdf417_13_21.png",
                        BarCodeImageFormat.Png);

        // AI 11 (manufacture date) + AI 21 (serial)
        barcodeGen.CodeText = "(11)991231(21)ABCD";
        barcodeGen.Save(@"YOUR_DIRECTORY\GS1MicroPdf417_11_21.png",
                        BarCodeImageFormat.Png);

        // Only AI 17 (expiration) – no batch number
        barcodeGen.CodeText = "(17)991231";
        barcodeGen.Save(@"YOUR_DIRECTORY\GS1MicroPdf417_17.png",
                        BarCodeImageFormat.Png);
```

**Pourquoi réutiliser ?** Modifier `CodeText` évite le surcoût de réinstanciation du générateur et garantit des paramètres visuels cohérents pour toutes les images.

---

## Étape 6 : Exécuter, vérifier et ajuster

Compilez et exécutez :

```bash
dotnet run
```

Vous devriez maintenant disposer de cinq fichiers PNG, chacun nommé d’après la paire d’AI qu’il contient. Ouvrez‑en un avec un visualiseur d’images ; vous verrez le code‑barres et le texte encodé en dessous. Pour vérifier que les données sont correctes, utilisez une application gratuite de scanner GS1 sur votre téléphone — pointez‑la sur le PNG à l’écran et observez les valeurs AI apparaître.

**Problèmes courants et comment les éviter**

| Problème | Cause | Solution |
|----------|-------|----------|
| Code‑barres illisible | `XDimension` trop faible (ex. 1 pixel) | Augmenter à 2 ou 3 pixels |
| Parenthèses AI manquantes | Format `CodeText` incorrect | Toujours entourer chaque AI de parenthèses |
| Image trop grande | Trop de colonnes/rows | Réduire `Columns` ou laisser Aspose redimensionner automatiquement |
| Erreur d’exécution `EncodeTypes` introuvable | `using Aspose.BarCode.Generation` manquant | Ajouter la directive `using` manquante |

---

## Étape 7 : Étendre l’exemple – Générer plus de combinaisons AI

Si vous devez **créer des gs1 barcode images** pour des dizaines de variantes de produit, envisagez de charger les paires AI depuis un fichier CSV :

```csharp
using System.IO;

string[] lines = File.ReadAllLines(@"ai_pairs.csv"); // format: "(17)991231,(10)ABCD"
foreach (var line in lines)
{
    barcodeGen.CodeText = line.Replace(',', ' ');
    string fileName = $"GS1MicroPdf417_{line.Replace("(", "").Replace(")", "").Replace(",", "_")}.png";
    barcodeGen.Save(Path.Combine(@"YOUR_DIRECTORY", fileName), BarCodeImageFormat.Png);
}
```

Cette petite boucle lit chaque ligne, échange les données et sauvegarde un PNG avec un nom descriptif — parfait pour les pipelines d’impression d’étiquettes à grande échelle.

---

## Conclusion

Vous disposez maintenant d’un programme C# complet et prêt à l’exécution qui **crée des gs1 barcode images** pour plusieurs scénarios AI, démontrant la façon la plus simple de **how to generate barcode c#** avec Aspose.BarCode. En réutilisant une seule instance de `BarcodeGenerator`, en ajustant les paramètres visuels et en changeant `CodeText`, vous pouvez générer autant de PNG GS1‑MicroPDF417 conformes que votre projet nécessite.

Et ensuite ? Essayez d’ajouter des couleurs (`barcodeGen.Parameters.Barcode.ForeColor`), d’intégrer le code‑barres dans un PDF, ou de passer à une autre symbologie GS1 comme DataMatrix. Le même schéma s’applique — initialiser, configurer, définir `CodeText`, et sauvegarder.

N’hésitez pas à laisser un commentaire si vous rencontrez des problèmes, ou à partager vos propres variantes. Bon codage, et que vos scans soient toujours propres !

## Que devriez‑vous apprendre ensuite ?

Les tutoriels suivants couvrent des sujets étroitement liés qui s’appuient sur les techniques démontrées dans ce guide. Chaque ressource inclut des exemples de code complets et fonctionnels avec des explications étape par étape pour vous aider à maîtriser des fonctionnalités d’API supplémentaires et explorer des approches d’implémentation alternatives dans vos propres projets.

- [Comment créer une zone silencieuse de code‑barres pour Code 16K avec Aspose.BarCode pour .NET](/barcode/english/net/code-16k-encoding/code-16k-quiet-zone-settings/)
- [Comment créer une zone silencieuse de code‑barres pour ITF‑14 avec Aspose.BarCode pour .NET](/barcode/english/net/itf-14-barcode-customization/itf-14-barcode-quiet-zone-configuration/)
- [Comment générer un code‑barres – Configuration Code 39 avec Aspose.BarCode](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-code-39-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}