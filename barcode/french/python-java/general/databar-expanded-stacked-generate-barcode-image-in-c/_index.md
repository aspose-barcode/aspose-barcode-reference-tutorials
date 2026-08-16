---
category: general
date: 2026-08-15
description: Génération de codes-barres empilés étendus Databar en C#. Apprenez à
  générer une image de code-barres, à définir les colonnes et les lignes pour les
  mises en page DataBar.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- databar expanded stacked
- generate barcode image
- how to generate barcode
- how to set columns
- how to set rows
language: fr
lastmod: 2026-08-15
og_description: Génération de codes-barres empilés étendue avec Databar en C#. Suivez
  ce guide étape par étape pour générer des images de codes-barres, définir les colonnes
  et les lignes efficacement.
og_image_alt: Screenshot of a databar expanded stacked barcode generated with C#
og_title: Databar étendu empilé – générer une image de code‑barres en C#
schemas:
- author: Aspose
  dateModified: '2026-08-15'
  description: Databar expanded stacked barcode generation in C#. Learn how to generate
    barcode image, set columns and rows for DataBar layouts.
  headline: 'Databar expanded stacked: generate barcode image in C#'
  type: TechArticle
- description: Databar expanded stacked barcode generation in C#. Learn how to generate
    barcode image, set columns and rows for DataBar layouts.
  name: 'Databar expanded stacked: generate barcode image in C#'
  steps:
  - name: 1. Install the Aspose.BarCode library
    text: 'The code uses the **Aspose.BarCode for .NET** library, which provides the
      `BarcodeGenerator` class. Install the NuGet package with the following command:'
  - name: 2. Create a barcode generator for **databar expanded stacked**
    text: The generator is the entry point for all barcode operations. You must specify
      the symbology (`EncodeTypes.DatabarExpandedStacked`) and the text to encode.
  - name: 3. How to set columns for DataBar
    text: The `Columns` property controls how many vertical modules appear in the
      stacked barcode. Valid values are 2, 3, or 4. Setting columns influences the
      barcode’s width and the amount of data it can store.
  - name: 4. Save the 4‑column barcode image
    text: Saving the image produces a file that you can embed in reports, invoices,
      or mobile apps. The `Save` method accepts a file path and an image format.
  - name: 5. How to set rows for DataBar
    text: Rows add a second dimension to the stacked layout, allowing more data to
      be encoded without widening the barcode. The `Rows` property defaults to 1;
      you can increase it up to 3 for the expanded stacked variant.
  - name: 6. Save the 3‑row barcode image
    text: '```csharp // Step 5: Save the 3‑row barcode image barcode.Save("YOUR_DIRECTORY/DatabarRows3.png",
      BarCodeImageFormat.Png); ```'
  - name: 7. Complete C# example to generate barcode image
    text: 'Putting all steps together yields a self‑contained program you can copy
      into a console application:'
  type: HowTo
tags:
- barcode
- C#
- Aspose.BarCode
title: 'Databar étendu empilé : générer une image de code-barres en C#'
url: /fr/python-java/general/databar-expanded-stacked-generate-barcode-image-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Databar expanded stacked : générer une image de code‑barres en C#

Si vous devez générer une image de code‑barres **databar expanded stacked** en C#, ce guide vous montre exactement **comment générer des code‑barres** avec des dispositions personnalisées de colonnes et de lignes. Vous verrez comment définir les colonnes, comment définir les lignes, et comment enregistrer les images résultantes sans quitter l’IDE.

Le tutoriel couvre :

* Créer un générateur de code‑barres pour la symbologie **databar expanded stacked**.  
* Configurer une disposition à 4 colonnes et à 3 lignes.  
* Enregistrer chaque configuration sous forme de fichier PNG.  
* Astuces pour gérer les cas limites tels que des nombres de colonnes invalides.

Aucune documentation externe n’est requise ; l’exemple complet et exécutable est inclus.

![Databar expanded stacked barcode example](YOUR_DIRECTORY/DatabarCols4.png){: .center alt="code‑barres databar expanded stacked généré avec C#" }

## Étapes de génération du code‑barres Databar expanded stacked

### 1. Installer la bibliothèque Aspose.BarCode

Le code utilise la bibliothèque **Aspose.BarCode for .NET**, qui fournit la classe `BarcodeGenerator`. Installez le package NuGet avec la commande suivante :

```bash
dotnet add package Aspose.BarCode
```

Après l’installation du package, ajoutez l’espace de noms requis en haut de votre fichier :

```csharp
using Aspose.BarCode.Generation;
```

### 2. Créer un générateur de code‑barres pour **databar expanded stacked**

Le générateur est le point d’entrée pour toutes les opérations de code‑barres. Vous devez spécifier la symbologie (`EncodeTypes.DatabarExpandedStacked`) et le texte à encoder.

```csharp
// Step 1: Create a barcode generator for Databar Expanded Stacked
BarcodeGenerator barcode = new BarcodeGenerator(
    EncodeTypes.DatabarExpandedStacked,
    "Databar Expanded Stacked long");
```

*Pourquoi c’est important :* L’énumération `EncodeTypes` indique à la bibliothèque quel format de code‑barres produire. Utiliser **databar expanded stacked** garantit que l’image résultante suit la spécification GS1 DataBar pour les dispositions empilées.

### 3. Comment définir les colonnes pour DataBar

La propriété `Columns` contrôle le nombre de modules verticaux apparaissant dans le code‑barres empilé. Les valeurs valides sont 2, 3 ou 4. Le réglage des colonnes influence la largeur du code‑barres et la quantité de données qu’il peut stocker.

```csharp
// Step 2: Configure a 4‑column layout
barcode.Parameters.Barcode.DataBar.Columns = 4;
```

**Conseil :** Si vous essayez d’attribuer une valeur en dehors de la plage autorisée, la bibliothèque lève une `ArgumentException`. Validez toujours l’entrée lorsqu’elle est exposée aux utilisateurs.

### 4. Enregistrer l’image de code‑barres à 4 colonnes

Enregistrer l’image crée un fichier que vous pouvez intégrer dans des rapports, factures ou applications mobiles. La méthode `Save` accepte un chemin de fichier et un format d’image.

```csharp
// Step 3: Save the 4‑column barcode image
barcode.Save("YOUR_DIRECTORY/DatabarCols4.png", BarCodeImageFormat.Png);
```

Lorsque le fichier est écrit, vous pouvez l’ouvrir avec n’importe quel visualiseur d’images pour vérifier que le motif **databar expanded stacked** apparaît correctement.

### 5. Comment définir les lignes pour DataBar

Les lignes ajoutent une seconde dimension à la disposition empilée, permettant d’encoder plus de données sans élargir le code‑barres. La propriété `Rows` vaut 1 par défaut ; vous pouvez l’augmenter jusqu’à 3 pour la variante empilée étendue.

```csharp
// Step 4: Switch to a 3‑row layout (columns remain unchanged)
barcode.Parameters.Barcode.DataBar.Rows = 3;
```

*Pourquoi les lignes sont importantes :* Augmenter le nombre de lignes réduit la largeur globale tout en préservant la capacité de données, ce qui est utile pour les étiquettes étroites ou les écrans mobiles.

### 6. Enregistrer l’image de code‑barres à 3 lignes

```csharp
// Step 5: Save the 3‑row barcode image
barcode.Save("YOUR_DIRECTORY/DatabarRows3.png", BarCodeImageFormat.Png);
```

Vous disposez maintenant de deux fichiers PNG — l’un avec une disposition à 4 colonnes et l’autre avec une disposition à 3 lignes — tous deux utilisant la symbologie **databar expanded stacked**.

### 7. Exemple complet en C# pour générer une image de code‑barres

Assembler toutes les étapes donne un programme autonome que vous pouvez copier dans une application console :

```csharp
using System;
using Aspose.BarCode.Generation;

namespace DatabarExpandedStackedDemo
{
    class Program
    {
        static void Main()
        {
            // Create the generator for Databar Expanded Stacked
            BarcodeGenerator barcode = new BarcodeGenerator(
                EncodeTypes.DatabarExpandedStacked,
                "Databar Expanded Stacked long");

            // Configure a 4‑column layout and save
            barcode.Parameters.Barcode.DataBar.Columns = 4;
            barcode.Save("YOUR_DIRECTORY/DatabarCols4.png", BarCodeImageFormat.Png);
            Console.WriteLine("4‑column barcode saved.");

            // Change to a 3‑row layout (columns stay at 4) and save
            barcode.Parameters.Barcode.DataBar.Rows = 3;
            barcode.Save("YOUR_DIRECTORY/DatabarRows3.png", BarCodeImageFormat.Png);
            Console.WriteLine("3‑row barcode saved.");
        }
    }
}
```

**Sortie attendue**

L’exécution du programme affiche :

```
4‑column barcode saved.
3‑row barcode saved.
```

et crée deux fichiers PNG dans `YOUR_DIRECTORY`. Ouvrez les fichiers pour vérifier que chaque image affiche un code‑barres **databar expanded stacked** valide.

## Problèmes courants et astuces pratiques

* **Existence du répertoire** – `Save` ne crée pas les dossiers manquants. Assurez‑vous que `YOUR_DIRECTORY` existe ou utilisez `Directory.CreateDirectory` avant d’enregistrer.
* **Limites de colonnes** – Des valeurs autres que 2, 3 ou 4 déclenchent une exception. Protégez les entrées utilisateur avec une simple vérification de plage :

  ```csharp
  int columns = 4;
  if (columns < 2 || columns > 4) throw new ArgumentOutOfRangeException(nameof(columns));
  barcode.Parameters.Barcode.DataBar.Columns = columns;
  ```

* **Limites de lignes** – La variante empilée étendue prend en charge jusqu’à 3 lignes. Définir `Rows` à 0 ou à une valeur supérieure à 3 lève également une exception.
* **Format d’image** – `BarCodeImageFormat.Png` offre une qualité sans perte, idéale pour l’impression. N’utilisez `Jpeg` que lorsque la taille du fichier est une préoccupation principale.

## Prochaines étapes

Maintenant que vous savez **comment générer des code‑barres** avec des configurations personnalisées de colonnes et de lignes, vous pouvez :

* Intégrer le générateur dans une API web pour fournir des images de code‑barres à la demande.  
* Combiner le code‑barres avec des bibliothèques de génération PDF pour l’intégrer dans des factures.  
* Expérimenter d’autres variantes DataBar (`DatabarExpanded`, `DatabarLimited`) en utilisant le même objet `Parameters.Barcode.DataBar`.

Pour une personnalisation plus poussée—comme changer la couleur des barres, ajouter du texte lisible par l’homme, ou appliquer des superpositions de QR‑code—référez‑vous à la documentation Aspose.BarCode sur les propriétés de `BarcodeGenerator`.

---

En suivant ce guide, vous avez maîtrisé le flux de travail **databar expanded stacked**, appris **comment définir les colonnes**, **comment définir les lignes**, et produit deux images de code‑barres distinctes prêtes pour une utilisation en production. Bon codage !

## Que devriez‑vous apprendre ensuite ?

Les tutoriels suivants couvrent des sujets étroitement liés qui s’appuient sur les techniques démontrées dans ce guide. Chaque ressource inclut des exemples de code complets avec des explications étape par étape pour vous aider à maîtriser des fonctionnalités API supplémentaires et explorer des approches d’implémentation alternatives dans vos propres projets.

- [Générer une image de code‑barres – GS1 Coupon UPC‑A Databar](/barcode/english/net/gs1-barcode-encoding/gs1-coupon-upc-a-databar-configuration/)
- [Créer une image de code‑barres DotCode – lignes & colonnes (Aspose.BarCode)](/barcode/english/net/dotcode-barcode-configuration/dotcode-rows-columns-configuration/)
- [Comment générer un code‑barres – Types de codes‑barres unidimensionnels](/barcode/english/net/one-dimensional-barcode-types/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}