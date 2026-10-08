---
category: general
date: 2026-09-26
description: Le guide du générateur de codes‑barres C# montre comment définir les
  lignes et les colonnes lors de la création de codes‑barres Databar Expanded Stacked
  en C#.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- barcode generator c#
- how to set rows
- how to set columns
- Databar Expanded Stacked barcode
- C# barcode library
language: fr
lastmod: 2026-09-26
og_description: Le tutoriel du générateur de codes‑barres C# explique comment définir
  les lignes et les colonnes pour les codes‑barres Databar Expanded Stacked, avec
  le code complet et des astuces.
og_image_alt: Barcode generator C# example showing rows and columns settings
og_title: Générateur de code-barres C# – définir les lignes et les colonnes étape
  par étape
schemas:
- author: Aspose
  dateModified: '2026-09-26'
  description: barcode generator C# guide shows how to set rows and how to set columns
    when creating Databar Expanded Stacked barcodes in C#.
  headline: How to use barcode generator C# for rows and columns
  type: TechArticle
- description: barcode generator C# guide shows how to set rows and how to set columns
    when creating Databar Expanded Stacked barcodes in C#.
  name: How to use barcode generator C# for rows and columns
  steps:
  - name: Create a generator for a Databar Expanded Stacked barcode
    text: '```csharp // Create a generator for a Databar Expanded Stacked barcode
      with sample text BarcodeGenerator barcodeGenerator = new BarcodeGenerator( EncodeTypes.DatabarExpandedStacked,
      "Databar Expanded Stacked long"); ```'
  - name: How to set columns – configure the barcode to use 4 columns
    text: '```csharp // How to set columns: set the Columns property to 4 barcodeGenerator.Parameters.Barcode.DataBar.Columns
      = 4; ```'
  - name: Save the barcode image with the column setting
    text: '```csharp // Save the PNG image that reflects the column configuration
      barcodeGenerator.Save("YOUR_DIRECTORY/DatabarCols4.png", BarCodeImageFormat.Png);
      ```'
  - name: Re‑initialize the generator for a different layout
    text: When you need a separate barcode with a different visual arrangement, create
      a new instance rather than re‑using the previous one. This guarantees that previous
      settings (like columns) do not bleed into the new configuration.
  - name: How to set rows – configure the barcode to use 3 rows
    text: '```csharp // How to set rows: assign the Rows property to 3 barcodeGenerator.Parameters.Barcode.DataBar.Rows
      = 3; ```'
  - name: Save the barcode image that includes the row setting
    text: '```csharp // Save the PNG image that reflects the row configuration barcodeGenerator.Save("YOUR_DIRECTORY/DatabarRows3.png",
      BarCodeImageFormat.Png); ```'
  - name: Expected output
    text: 'Running the program produces two PNG files:'
  - name: Pro tip
    text: 'If you need to generate many barcodes with varying rows and columns, wrap
      the configuration logic in a helper method:'
  type: HowTo
tags:
- barcode
- C#
- code example
title: Comment utiliser le générateur de codes-barres C# pour les lignes et les colonnes
url: /fr/python-java/general/how-to-use-barcode-generator-c-for-rows-and-columns/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Comment utiliser le générateur de code‑barres C# pour les lignes et les colonnes

Si vous avez besoin d’un **barcode generator C#** qui vous permette de contrôler la disposition visuelle d’un code‑barres Databar Expanded Stacked, ce tutoriel vous fournit une solution complète et exécutable. Vous apprendrez **comment définir les lignes** et **comment définir les colonnes** afin que l’image générée corresponde exactement au design requis.

Générer des codes‑barres de façon programmatique ressemble souvent à deviner quelle propriété fait quoi. À la fin de ce guide, vous comprendrez la surface de l’API, éviterez les pièges courants et disposerez d’un exemple de code prêt à l’emploi que vous pourrez copier dans votre propre projet.

## Prérequis

Avant de commencer, assurez‑vous d’avoir :

* .NET 6.0 ou version ultérieure installé (le code fonctionne également avec .NET Core et .NET Framework)
* Une référence à la bibliothèque de génération de code‑barres qui fournit `BarcodeGenerator` et `EncodeTypes` (par exemple, Aspose.BarCode, Dynamsoft, ou tout SDK compatible)
* Un IDE tel que Visual Studio ou VS Code
* Des droits d’écriture sur un dossier où les fichiers PNG seront enregistrés

Aucun package NuGet supplémentaire n’est requis au‑delà du SDK de code‑barres lui‑même.

## Barcode generator C# – définition des lignes et des colonnes

Les sections suivantes parcourent chaque étape de configuration. Les extraits de code sont complets et peuvent être collés directement dans la méthode `Main` d’une application console.

### Étape 1 : Créer un générateur pour un code‑barres Databar Expanded Stacked

```csharp
// Create a generator for a Databar Expanded Stacked barcode with sample text
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.DatabarExpandedStacked, "Databar Expanded Stacked long");
```

*Pourquoi c’est important :* Instancier `BarcodeGenerator` est la première action que vous effectuez dans tout flux de travail **barcode generator C#**. Le constructeur reçoit le type d’encodage et la chaîne de données qui sera encodée.

### Étape 2 : Comment définir les colonnes – configurer le code‑barres pour utiliser 4 colonnes

```csharp
// How to set columns: set the Columns property to 4
barcodeGenerator.Parameters.Barcode.DataBar.Columns = 4;
```

Définir la propriété `Columns` modifie le nombre de modules verticaux que le DataBar utilise. Une valeur de `4` crée un code‑barres plus dense et plus compact, ce qui est utile lorsque l’espace horizontal est limité.

### Étape 3 : Enregistrer l’image du code‑barres avec la configuration des colonnes

```csharp
// Save the PNG image that reflects the column configuration
barcodeGenerator.Save("YOUR_DIRECTORY/DatabarCols4.png", BarCodeImageFormat.Png);
```

La méthode `Save` écrit l’image générée sur le disque. Vérifiez le fichier de sortie pour confirmer que la disposition à quatre colonnes apparaît comme prévu.

![Exemple de barcode generator C# montrant les réglages des lignes et des colonnes](./images/barcode-rows-columns.png)

*L’image ci‑dessus illustre le résultat de la configuration des colonnes.*

### Étape 4 : Ré‑initialiser le générateur pour une disposition différente

Lorsque vous avez besoin d’un code‑barres distinct avec une autre organisation visuelle, créez une nouvelle instance plutôt que de réutiliser la précédente. Cela garantit que les réglages antérieurs (comme les colonnes) ne débordent pas sur la nouvelle configuration.

```csharp
// Re‑initialize to start a fresh configuration
barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.DatabarExpandedStacked, "Databar Expanded Stacked long");
```

### Étape 5 : Comment définir les lignes – configurer le code‑barres pour utiliser 3 lignes

```csharp
// How to set rows: assign the Rows property to 3
barcodeGenerator.Parameters.Barcode.DataBar.Rows = 3;
```

La propriété `Rows` contrôle l’empilement vertical des modules DataBar. Une disposition à trois lignes est la valeur par défaut pour de nombreux appareils de lecture, mais vous pouvez l’augmenter pour une densité de données supérieure.

### Étape 6 : Enregistrer l’image du code‑barres incluant le réglage des lignes

```csharp
// Save the PNG image that reflects the row configuration
barcodeGenerator.Save("YOUR_DIRECTORY/DatabarRows3.png", BarCodeImageFormat.Png);
```

Ouvrez `DatabarRows3.png` pour voir la disposition à trois lignes. Si le code‑barres ne se lit pas, revérifiez les valeurs lignes/colonnes par rapport aux spécifications de votre scanner.

## Code source complet – prêt à copier

Voici le programme complet qui combine toutes les étapes ci‑dessus. Remplacez `YOUR_DIRECTORY` par un chemin absolu ou relatif existant sur votre machine.

```csharp
using System;
using YourBarcodeSdkNamespace;   // Replace with the actual namespace of your SDK

class Program
{
    static void Main()
    {
        // ---------- Columns configuration ----------
        // 1. Create generator
        BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
            EncodeTypes.DatabarExpandedStacked, "Databar Expanded Stacked long");

        // 2. Set columns (how to set columns)
        barcodeGenerator.Parameters.Barcode.DataBar.Columns = 4;

        // 3. Save image with column setting
        barcodeGenerator.Save("YOUR_DIRECTORY/DatabarCols4.png", BarCodeImageFormat.Png);
        Console.WriteLine("Saved barcode with 4 columns to DatabarCols4.png");

        // ---------- Rows configuration ----------
        // 4. Re‑initialize generator for a fresh instance
        barcodeGenerator = new BarcodeGenerator(
            EncodeTypes.DatabarExpandedStacked, "Databar Expanded Stacked long");

        // 5. Set rows (how to set rows)
        barcodeGenerator.Parameters.Barcode.DataBar.Rows = 3;

        // 6. Save image with row setting
        barcodeGenerator.Save("YOUR_DIRECTORY/DatabarRows3.png", BarCodeImageFormat.Png);
        Console.WriteLine("Saved barcode with 3 rows to DatabarRows3.png");
    }
}
```

### Résultat attendu

L’exécution du programme produit deux fichiers PNG :

| Nom du fichier        | Description de la disposition                         |
|-----------------------|--------------------------------------------------------|
| `DatabarCols4.png`    | Databar Expanded Stacked avec **4 colonnes**          |
| `DatabarRows3.png`    | Databar Expanded Stacked avec **3 lignes**            |

Les deux images doivent être lisibles par les lecteurs de code‑barres standards qui prennent en charge la symbologie Databar Expanded Stacked.

## Pièges courants et astuces professionnelles

| Piège                                                   | Pourquoi cela se produit                              | Solution / Astuce |
|----------------------------------------------------------|--------------------------------------------------------|-------------------|
| Utiliser la même instance de `BarcodeGenerator` pour les lignes et les colonnes | Le SDK conserve la configuration précédente, de sorte que définir les lignes après les colonnes peut produire un mélange inattendu | Ré‑initialiser le générateur (comme montré à l’Étape 4) avant de changer l’autre dimension |
| Oublier de définir correctement `EncodeTypes`            | Le SDK utilise par défaut une symbologie différente, entraînant un code‑barres invalide | Toujours passer `EncodeTypes.DatabarExpandedStacked` lorsque vous avez besoin de ce format précis |
| Enregistrer dans un dossier inexistant                  | `Save` lève une exception si le chemin est invalide      | S’assurer que `YOUR_DIRECTORY` existe ou utiliser `Directory.CreateDirectory` avant d’appeler `Save` |
| Utiliser des valeurs hors de la plage autorisée (ex. 0 colonne) | Le SDK valide la plage et lève `ArgumentOutOfRangeException` | Les valeurs de colonne valides sont 1‑4 ; les valeurs de ligne valides sont 1‑3 pour cette symbologie |

### Astuce professionnelle

Si vous devez générer de nombreux codes‑barres avec des lignes et colonnes variables, encapsulez la logique de configuration dans une méthode d’aide :

```csharp
static void GenerateDatabar(string text, int? rows, int? columns, string outputPath)
{
    var generator = new BarcodeGenerator(EncodeTypes.DatabarExpandedStacked, text);
    if (rows.HasValue)    generator.Parameters.Barcode.DataBar.Rows = rows.Value;
    if (columns.HasValue) generator.Parameters.Barcode.DataBar.Columns = columns.Value;
    generator.Save(outputPath, BarCodeImageFormat.Png);
}
```

Cette approche réduit la duplication et rend le code plus facile à maintenir.

## Conclusion

Vous disposez maintenant d’un exemple clair, de bout en bout, d’utilisation d’un **barcode generator C#** pour contrôler à la fois le nombre de lignes et le nombre de colonnes d’un code‑barres Databar Expanded Stacked. En suivant les étapes ci‑dessus, vous pouvez générer des images de code‑barres précises qui répondent exactement aux exigences de mise en page de votre matériel de lecture.

À partir d’ici, vous pouvez explorer :

* Ajuster d’autres propriétés `DataBar` telles que **AspectRatio** ou **BarHeight**
* Générer d’autres symbologies (par ex. QR, Code128) avec la même classe `BarcodeGenerator`
* Intégrer le PNG généré dans des PDF ou l’imprimer directement depuis C#

N’hésitez pas à expérimenter avec différentes combinaisons de lignes/colonnes, et partagez vos résultats dans les commentaires. Bon codage !

## Que devez‑vous apprendre ensuite ?

Les tutoriels suivants couvrent des sujets étroitement liés qui s’appuient sur les techniques démontrées dans ce guide. Chaque ressource inclut des exemples de code complets et fonctionnels avec des explications pas à pas pour vous aider à maîtriser des fonctionnalités API supplémentaires et à explorer des approches d’implémentation alternatives dans vos propres projets.

- [How to set columns for a Databar Expanded Stacked barcode – complete C# guide](/barcode/english/python-java/general/how-to-set-columns-for-a-databar-expanded-stacked-barcode-co/)
- [databar expanded stacked barcode guide – how to generate and size it in C#](/barcode/english/python-java/general/databar-expanded-stacked-barcode-guide-how-to-generate-and-s/)
- [Barcode Generator Example in C# – Set Columns, Rows & Export Image](/barcode/english/python-java/general/barcode-generator-example-in-c-set-columns-rows-export-image/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}