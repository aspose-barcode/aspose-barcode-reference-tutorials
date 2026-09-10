---
category: general
date: 2026-07-27
description: Guide du code‑barres empilé étendu Databar – apprenez comment générer
  un code‑barres, définir les dimensions, créer un code‑barres Databar et configurer
  la taille du code‑barres en quelques étapes.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- databar expanded stacked
- how to generate barcode
- how to set dimensions
- create databar barcode
- configure barcode size
language: fr
lastmod: 2026-07-27
og_description: Le tutoriel sur le code‑barres empilé étendu Databar montre comment
  générer un code‑barres, définir les dimensions et configurer la taille du code‑barres
  avec des exemples de code clairs.
og_image_alt: Screenshot of a Databar Expanded Stacked barcode with custom column
  and row settings
og_title: code-barres empilé étendu Databar – tutoriel rapide C#
schemas:
- author: Aspose
  dateModified: '2026-07-27'
  description: databar expanded stacked barcode guide – learn how to generate barcode,
    set dimensions, create databar barcode, and configure barcode size in a few steps.
  headline: databar expanded stacked barcode guide – how to generate and size it in
    C#
  type: TechArticle
- description: databar expanded stacked barcode guide – learn how to generate barcode,
    set dimensions, create databar barcode, and configure barcode size in a few steps.
  name: databar expanded stacked barcode guide – how to generate and size it in C#
  steps:
  - name: Why we re‑instantiate the generator
    text: You might wonder why we create a new `BarcodeGenerator` before setting rows.
      The **columns** and **rows** properties belong to the same `DataBar` object,
      but they each have a default that the other side respects. By starting with
      a fresh instance we guarantee that the column setting doesn’t inadvert
  - name: What does “column” mean for a **databar expanded stacked** symbol?
    text: '- **Columns** split the stacked barcode horizontally. More columns mean
      the symbol becomes wider, which can be useful when you have limited vertical
      space. - **Rows** stack the columns vertically. Adding rows makes the barcode
      taller, helpful for narrow label widths.'
  - name: When should you adjust these dimensions?
    text: '| Scenario | Recommended tweak | |----------|-------------------| | Thin
      label printer (e.g., receipt printers) | Reduce columns, increase rows. | |
      Wide shelf label (e.g., price tags) | Increase columns, keep rows low. | | High‑resolution
      print (e.g., packaging) | Use default layout but boost DPI v'
  - name: 1️⃣ *What if my data string exceeds the maximum length?*
    text: The **databar expanded stacked** format can encode up to 74 numeric characters
      or 41 alphanumeric characters. If you exceed that, the generator throws a `BarcodeException`.
      Trim or hash the data, or switch to a different barcode type (e.g., `Pdf417`).
  - name: 2️⃣ *Can I output SVG instead of PNG?*
    text: Absolutely. Replace `BarCodeImageFormat.Png` with `BarCodeImageFormat.Svg`.
      SVG is vector‑based and scales without loss—great for web apps.
  - name: 3️⃣ *Do I need to worry about background color?*
    text: 'By default the background is white. To make it transparent, set:'
  - name: 4️⃣ *Is there a way to add a caption beneath the barcode?*
    text: Yes. Use `generator.Parameters.Barcode.BarcodeImageFormat = BarCodeImageFormat.Png;`
      and then combine the barcode with a `Graphics` object to draw text. That’s a
      bit more involved, but the Aspose API provides a `BarcodeGenerator.Save` overload
      that accepts a `Stream`—you can post‑process the image a
  type: HowTo
tags:
- barcode
- databar
- csharp
title: Guide du code‑barres Databar Expanded Stacked – comment le générer et le dimensionner
  en C#
url: /fr/python-java/general/databar-expanded-stacked-barcode-guide-how-to-generate-and-s/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# databar expanded stacked barcode – Tutoriel complet C#

Vous êtes‑vous déjà demandé comment générer un **databar expanded stacked** sans fouiller dans d’innombrables documents API ? Vous n’êtes pas le seul. Que vous construisiez un système de caisse de détail ou une imprimante d’étiquettes logistiques, maîtriser ce type de code‑barres peut vous faire gagner des heures d’essais et d’erreurs.

Dans ce guide, nous parcourrons l’ensemble du processus : de l’installation de la bibliothèque, à la création du code‑barres, en passant par **comment définir les dimensions** pour les colonnes et les lignes, et enfin **configurer la taille du code‑barres** selon vos besoins d’impression exacts. À la fin, vous disposerez d’un projet C# prêt à l’emploi qui génère deux images PNG — une avec des colonnes personnalisées, une autre avec des lignes personnalisées.

---

## Ce que vous apprendrez

- **Comment générer des images de code‑barres** en utilisant la bibliothèque Aspose.BarCode pour .NET.  
- La différence entre **columns** et **rows** dans un symbole **databar expanded stacked**.  
- Étapes pratiques pour **créer un code‑barres databar** avec une mise en page spécifique.  
- Conseils sur **configurer la taille du code‑barres**, DPI et format d’image.  
- Gestion des cas limites lorsque la chaîne de données est trop longue ou que vous avez besoin d’un arrière‑plan transparent.

Aucune expérience préalable avec Aspose n’est requise ; il suffit d’une configuration C# basique et d’une curiosité pour les codes‑barres.

---

## Prérequis

| Exigence | Pourquoi c’est important |
|----------|---------------------------|
| .NET 6.0 SDK ou version ultérieure | Fournit les dernières fonctionnalités du langage et les performances d’exécution. |
| Visual Studio 2022 (ou VS Code) | Facilite la gestion des packages NuGet et l’exécution de l’exemple. |
| Accès Internet pour télécharger le package NuGet **Aspose.BarCode** | La bibliothèque contient la classe `BarcodeGenerator` que nous utiliserons. |
| Un dossier dans lequel vous pouvez écrire (par ex., `C:\Barcodes\`) | Où les fichiers PNG seront enregistrés. |

Si l’un de ces éléments vous manque, procurez‑le‑vous maintenant — sinon vous rencontrerez une erreur « référence manquante » plus tard, ce qui est une perte de temps.

---

## Étape 1 : Installer Aspose.BarCode via NuGet

Ouvrez le dossier de votre projet dans un terminal et exécutez :

```bash
dotnet new console -n DatabarDemo
cd DatabarDemo
dotnet add package Aspose.BarCode
```

> **Astuce :** L’édition communautaire gratuite fonctionne pour la plupart des scénarios de développement, mais si vous avez besoin d’un support commercial, obtenez une licence auprès d’Aspose et appelez `License license = new License(); license.SetLicense("Aspose.BarCode.lic");` au début de `Main`.

Le package `Aspose.BarCode` fournit tout ce dont vous avez besoin pour générer des images de code‑barres, y compris la valeur d’énumération `EncodeTypes.DatabarExpandedStacked`.

---

## Étape 2 : Écrire le code principal – Créer le générateur de code‑barres

Créez un fichier nommé `Program.cs` (ou remplacez celui par défaut) et collez le code suivant. Ce bloc montre l’étape **créer un code‑barres databar** et prépare également la **configurer la taille du code‑barres** ultérieurement.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

namespace DatabarDemo
{
    class Program
    {
        static void Main(string[] args)
        {
            // Define the output folder – change this to your own path
            string outputFolder = @"C:\Barcodes\";

            // -----------------------------------------------------------------
            // 1️⃣  Create a barcode generator for Databar Expanded Stacked
            // -----------------------------------------------------------------
            // The second argument is the data you want to encode.
            // For Databar Expanded Stacked the string can be fairly long.
            BarcodeGenerator generator = new BarcodeGenerator(
                EncodeTypes.DatabarExpandedStacked,
                "Databar Expanded Stacked long");

            // -----------------------------------------------------------------
            // 2️⃣  Set a custom column count (default rows are used)
            // -----------------------------------------------------------------
            generator.Parameters.Barcode.DataBar.Columns = 4;   // ← how to set dimensions
            generator.Save($"{outputFolder}DatabarCols4.png", BarCodeImageFormat.Png);

            // -----------------------------------------------------------------
            // 3️⃣  Re‑initialize the generator for the same data
            // -----------------------------------------------------------------
            // This demonstrates that column and row settings are independent.
            generator = new BarcodeGenerator(
                EncodeTypes.DatabarExpandedStacked,
                "Databar Expanded Stacked long");

            // -----------------------------------------------------------------
            // 4️⃣  Set a custom row count (default columns are used)
            // -----------------------------------------------------------------
            generator.Parameters.Barcode.DataBar.Rows = 3;      // ← how to set dimensions
            generator.Save($"{outputFolder}DatabarRows3.png", BarCodeImageFormat.Png);

            // -----------------------------------------------------------------
            // 5️⃣  Optional: tweak overall image size and resolution
            // -----------------------------------------------------------------
            // If you need a larger barcode for printing, adjust the X/Y DPI.
            generator.Parameters.Image.XResolution = 300; // DPI
            generator.Parameters.Image.YResolution = 300;
            generator.Parameters.Image.Width = 400;       // pixels
            generator.Parameters.Image.Height = 200;      // pixels
            generator.Save($"{outputFolder}DatabarLarge.png", BarCodeImageFormat.Png);

            Console.WriteLine("Barcodes generated successfully!");
        }
    }
}
```

### Pourquoi nous ré‑instancions le générateur

Vous vous demandez peut‑être pourquoi nous créons un nouveau `BarcodeGenerator` avant de définir les lignes. Les propriétés **columns** et **rows** appartiennent au même objet `DataBar`, mais chacune possède une valeur par défaut que l’autre respecte. En partant d’une instance neuve, nous garantissons que le réglage des colonnes n’affecte pas involontairement le nombre de lignes, ce qui est un piège courant lors de la **configurer la taille du code‑barres**.

---

## Étape 3 : Exécuter le projet et vérifier la sortie

Depuis le terminal, exécutez :

```bash
dotnet run
```

Si tout est correctement configuré, vous verrez :

```
Barcodes generated successfully!
```

Naviguez vers `C:\Barcodes\` (ou le dossier que vous avez choisi). Vous devriez trouver trois fichiers PNG :

| Fichier | Ce qu’il montre |
|---------|------------------|
| `DatabarCols4.png` | Un code‑barres **databar expanded stacked** avec **4 colonnes** (lignes par défaut). |
| `DatabarRows3.png` | Même donnée, mais maintenant avec **3 lignes** (colonnes par défaut). |
| `DatabarLarge.png` | Une version plus grande où nous **configurer la taille du code‑barres** via DPI et dimensions en pixels. |

Ouvrez‑l’un d’eux dans un visualiseur d’images — oui, le code‑barres ressemble exactement à celui que vous verriez sur une étagère de supermarché, mais avec une mise en page personnalisée.

---

## Étape 4 : Analyse approfondie – Comprendre les colonnes vs. lignes

### Que signifie « colonne » pour un symbole **databar expanded stacked** ?

- **Columns** divisent le code‑barres empilé horizontalement. Plus de colonnes élargissent le symbole, ce qui peut être utile lorsque l’espace vertical est limité.  
- **Rows** empilent les colonnes verticalement. Ajouter des lignes rend le code‑barres plus haut, utile pour des largeurs d’étiquette étroites.

Les deux propriétés acceptent des valeurs de 2 à 8 (selon la longueur des données). Si vous essayez de définir une valeur en dehors de cette plage, Aspose lève une `ArgumentException`. C’est pourquoi nous avons conservé des nombres modestes (4 colonnes, 3 lignes) dans la démo.

### Quand devez‑vous ajuster ces dimensions ?

| Scénario | Ajustement recommandé |
|----------|-----------------------|
| Imprimante d’étiquettes fines (p. ex., imprimantes de reçus) | Réduire les colonnes, augmenter les lignes. |
| Étiquette d’étagère large (p. ex., étiquettes de prix) | Augmenter les colonnes, garder les lignes faibles. |
| Impression haute résolution (p. ex., emballage) | Utiliser la mise en page par défaut mais augmenter le DPI via `XResolution`/`YResolution`. |

---

## Étape 5 : Avancé – Ajustement fin de la taille du code‑barres

Si vous avez besoin de **configurer la taille du code‑barres** au‑delà des 200 × 100 px par défaut, vous avez deux leviers :

1. **Résolution d’image (DPI)** – Un DPI plus élevé offre plus de détails, essentiel pour les scanners qui exigent des bords nets.  
2. **Dimensions explicites en pixels** – Remplacez la taille auto‑calculée avec `Parameters.Image.Width` et `Height`.

```csharp
generator.Parameters.Image.XResolution = 600;
generator.Parameters.Image.YResolution = 600;
generator.Parameters.Image.Width = 600;   // pixels
generator.Parameters.Image.Height = 300;  // pixels
generator.Save($"{outputFolder}DatabarHighRes.png", BarCodeImageFormat.Png);
```

> **Attention :** Définir une largeur/hauteur trop petite pour le nombre de colonnes/lignes choisi tronquera le code‑barres, entraînant des échecs de lecture. Testez toujours avec un vrai scanner après avoir modifié les dimensions.

---

## Questions fréquentes & cas limites

### 1️⃣ *Que se passe‑t‑il si ma chaîne de données dépasse la longueur maximale ?*

Le format **databar expanded stacked** peut encoder jusqu’à 74 caractères numériques ou 41 caractères alphanumériques. Si vous dépassez cela, le générateur lève une `BarcodeException`. Coupez ou hachez les données, ou passez à un autre type de code‑barres (p. ex., `Pdf417`).

### 2️⃣ *Puis‑je générer du SVG au lieu de PNG ?*

Absolument. Remplacez `BarCodeImageFormat.Png` par `BarCodeImageFormat.Svg`. Le SVG est vectoriel et s’adapte sans perte — idéal pour les applications web.

### 3️⃣ *Dois‑je me soucier de la couleur d’arrière‑plan ?*

Par défaut, l’arrière‑plan est blanc. Pour le rendre transparent, définissez :

```csharp
generator.Parameters.Image.BackgroundColor = System.Drawing.Color.Transparent;
```

### 4️⃣ *Existe‑t‑il un moyen d’ajouter une légende sous le code‑barres ?*

Oui. Utilisez `generator.Parameters.Barcode.BarcodeImageFormat = BarCodeImageFormat.Png;` puis combinez le code‑barres avec un objet `Graphics` pour dessiner du texte. C’est un peu plus complexe, mais l’API Aspose propose une surcharge `BarcodeGenerator.Save` qui accepte un `Stream` — vous pouvez post‑traiter l’image ensuite.

---

## Récapitulatif étape par étape (Référence rapide)

| Étape | Action | Extrait de code |
|-------|--------|-----------------|
| 1️⃣ | Installer Aspose.BarCode | `dotnet add package Aspose.BarCode` |
| 2️⃣ | Créer le générateur pour **databar expanded stacked** | `new BarcodeGenerator(EncodeTypes.DatabarExpandedStacked, "your` |

## Que devriez‑vous apprendre ensuite ?

Les tutoriels suivants couvrent des sujets étroitement liés qui s’appuient sur les techniques démontrées dans ce guide. Chaque ressource comprend des exemples de code complets avec des explications étape par étape pour vous aider à maîtriser des fonctionnalités API supplémentaires et explorer des approches d’implémentation alternatives dans vos propres projets.

- [Générer une image de code‑barres – GS1 Coupon UPC‑A Databar](/barcode/english/net/gs1-barcode-encoding/gs1-coupon-upc-a-databar-configuration/)
- [Comment générer un code‑barres Java – Guide complet de configuration](/barcode/english/java/barcode-configuration/)
- [Créer un code‑barres avec Aspose - Définir les dimensions X & Y en Java](/barcode/english/java/barcode-configuration/managing-x-y-dimension-barcode/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}