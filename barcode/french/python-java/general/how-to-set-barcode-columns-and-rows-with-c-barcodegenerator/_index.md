---
category: general
date: 2026-09-16
description: Apprenez à définir les colonnes de codes‑barres en C# à l’aide de BarcodeGenerator
  et à définir également les lignes de codes‑barres pour les codes‑barres DataBar
  Expanded Stacked.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- set barcode columns
- set barcode rows
- DataBar Expanded Stacked
- BarcodeGenerator C#
- barcode image format
- configure barcode dimensions
language: fr
lastmod: 2026-09-16
og_description: Définissez rapidement les colonnes de codes-barres en C#. Ce guide
  vous montre comment configurer les colonnes, les lignes et le format d’image avec
  BarcodeGenerator.
og_image_alt: DataBar Expanded Stacked barcode showing custom columns and rows
og_title: Définir les colonnes et les lignes du code-barres en C# – guide complet
  de BarcodeGenerator
schemas:
- author: Aspose
  dateModified: '2026-09-16'
  description: Learn how to set barcode columns in C# using BarcodeGenerator and also
    set barcode rows for DataBar Expanded Stacked barcodes.
  headline: How to set barcode columns and rows with C# BarcodeGenerator
  type: TechArticle
tags:
- barcode
- C#
- Aspose.BarCode
title: Comment définir les colonnes et les lignes du code‑barres avec C# BarcodeGenerator
url: /fr/python-java/general/how-to-set-barcode-columns-and-rows-with-c-barcodegenerator/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Comment définir les colonnes et les lignes d'un code‑barres avec C# BarcodeGenerator

Si vous devez définir les colonnes d'un code‑barres dans une application C#, ce tutoriel montre les étapes exactes requises. Vous verrez comment configurer à la fois les colonnes et les lignes pour un code‑barres DataBar Expanded Stacked, puis enregistrer le résultat sous forme d'image PNG.

Générer des codes‑barres de manière programmatique vous évite le travail de conception manuel et garantit la cohérence entre les rapports, factures et étiquettes produit. L'exemple ci‑dessous couvre le flux complet, depuis l'installation de la bibliothèque jusqu'à la production de deux images — une avec un nombre de colonnes personnalisé et une autre avec un nombre de lignes personnalisé.

## Prérequis

Avant de commencer, assurez‑vous d'avoir :

* .NET 6.0 ou version ultérieure installé.
* Une référence au package NuGet **Aspose.BarCode for .NET**. Installez‑le avec :

```bash
dotnet add package Aspose.BarCode
```

* Un accès en écriture à un dossier où les fichiers PNG générés seront enregistrés.

Ces exigences garantissent que le code se compile et s'exécute sans configuration supplémentaire.

## Comment définir les colonnes d'un code‑barres en C#

La première étape majeure consiste à créer une instance `BarcodeGenerator` pour la symbologie **DataBar Expanded Stacked** et à attribuer le nombre de colonnes souhaité.

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // 1️⃣ Initialize a DataBar Expanded Stacked barcode generator with the target text.
        var barcodeGenerator = new BarcodeGenerator(
            EncodeTypes.DatabarExpandedStacked,
            "Databar Expanded Stacked long");

        // 2️⃣ Configure the number of columns. The DataBar object exposes a Columns property.
        barcodeGenerator.Parameters.Barcode.DataBar.Columns = 4;

        // 3️⃣ Save the image using the PNG format.
        barcodeGenerator.Save(@"C:\Barcodes\DatabarCols4.png", BarCodeImageFormat.Png);
    }
}
```

**Pourquoi cela fonctionne :**  
`EncodeTypes.DatabarExpandedStacked` indique à la bibliothèque quelle symbologie rendre. Le réglage de `Parameters.Barcode.DataBar.Columns` modifie la disposition interne des modules, ce qui influence directement la largeur visuelle du code‑barres. La méthode `Save` écrit l'image sur le disque dans le `BarCodeImageFormat` demandé.

### Résultat attendu
Ouvrez `C:\Barcodes\DatabarCols4.png` avec n'importe quel visualiseur d'images. Vous devriez voir un code‑barres DataBar Expanded Stacked plus large que la valeur par défaut car il utilise quatre colonnes.

## Comment définir les lignes d'un code‑barres en C#

Après avoir enregistré l'image basée sur les colonnes, vous pouvez vouloir un code‑barres dont la hauteur varie en ajustant les lignes. Le processus reflète la configuration des colonnes mais utilise la propriété `Rows` à la place.

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // 4️⃣ Re‑initialize the generator for a fresh configuration.
        var barcodeGenerator = new BarcodeGenerator(
            EncodeTypes.DatabarExpandedStacked,
            "Databar Expanded Stacked long");

        // 5️⃣ Set the number of rows. This property controls the vertical module count.
        barcodeGenerator.Parameters.Barcode.DataBar.Rows = 3;

        // 6️⃣ Save the barcode image with the row configuration.
        barcodeGenerator.Save(@"C:\Barcodes\DatabarRows3.png", BarCodeImageFormat.Png);
    }
}
```

**Pourquoi cela fonctionne :**  
Ré‑initialiser le générateur garantit que le réglage de colonne précédent n'interfère pas avec la configuration des lignes. Modifier `Parameters.Barcode.DataBar.Rows` change la hauteur du code‑barres, produisant une image plus haute lorsque le nombre de lignes dépasse la valeur par défaut.

### Résultat attendu
Ouvrez `C:\Barcodes\DatabarRows3.png`. Le code‑barres apparaîtra plus haut, reflétant la configuration à trois lignes.

## Exemple complet de bout en bout

Voici un programme unique qui crée les deux images en une seule exécution. Regrouper le code dans un même fichier montre comment basculer entre les configurations de colonnes et de lignes sans redémarrer l'application.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Common text for both barcodes.
        const string barcodeText = "Databar Expanded Stacked long";

        // ---------- Column configuration ----------
        var colGenerator = new BarcodeGenerator(EncodeTypes.DatabarExpandedStacked, barcodeText);
        colGenerator.Parameters.Barcode.DataBar.Columns = 4;
        colGenerator.Save(@"C:\Barcodes\DatabarCols4.png", BarCodeImageFormat.Png);
        Console.WriteLine("Saved barcode with 4 columns to DatabarCols4.png");

        // ---------- Row configuration ----------
        var rowGenerator = new BarcodeGenerator(EncodeTypes.DatabarExpandedStacked, barcodeText);
        rowGenerator.Parameters.Barcode.DataBar.Rows = 3;
        rowGenerator.Save(@"C:\Barcodes\DatabarRows3.png", BarCodeImageFormat.Png);
        Console.WriteLine("Saved barcode with 3 rows to DatabarRows3.png");
    }
}
```

L'exécution du programme génère deux fichiers PNG :

* **DatabarCols4.png** – code‑barres avec quatre colonnes.  
* **DatabarRows3.png** – code‑barres avec trois lignes.

Les deux fichiers utilisent le **format d'image de code‑barres** PNG, qui préserve les bords nets et prend en charge la compression sans perte — idéal pour l'impression et l'affichage numérique.

## Questions fréquentes et astuces

| Question | Réponse |
|----------|--------|
| *Puis-je utiliser JPEG au lieu de PNG ?* | Oui. Remplacez `BarCodeImageFormat.Png` par `BarCodeImageFormat.Jpeg`. JPEG est plus petit mais introduit des artefacts de compression, ce qui peut affecter la fiabilité du scanner. |
| *Quel est le nombre maximal de colonnes ou de lignes ?* | La bibliothèque valide les valeurs selon la spécification DataBar. Les valeurs hors de la plage autorisée lèvent une `ArgumentException`. Consultez la documentation Aspose.BarCode pour connaître les limites exactes. |
| *Dois‑je disposer du `BarcodeGenerator` ?* | La classe implémente `IDisposable`. Enveloppez le générateur dans un bloc `using` si vous créez de nombreuses instances dans une boucle afin de libérer rapidement les ressources non gérées. |
| *Comment modifier la taille du code‑barres sans modifier les colonnes/les lignes ?* | Utilisez `barcodeGenerator.Parameters.Image.Width` et `Height` pour mettre à l'échelle l'image de sortie tout en conservant la disposition des modules inchangée. |

**Astuce :** Lorsque vous générez des codes‑barres pour une impression haute résolution, augmentez les dimensions de l'image de sortie (`Width`/`Height`) plutôt que le nombre de colonnes ou de lignes. Cette approche maintient la taille standard du module définie par la symbologie tout en vous offrant une image plus nette.

## Conclusion

Vous savez maintenant comment définir les colonnes et les lignes d'un code‑barres en C# à l'aide de la classe **BarcodeGenerator**. Le guide a couvert l'initialisation du générateur, la configuration des comptes de colonnes et de lignes, l'enregistrement du code‑barres au format PNG, ainsi que la gestion des variations courantes comme le changement de format d'image et la libération des ressources.

Ensuite, explorez des sujets connexes tels que **la personnalisation des couleurs du code‑barres**, **l'ajout de texte lisible par l'homme**, et **l'intégration des codes‑barres dans des documents PDF**. Toutes ces extensions s'appuient sur le même modèle de configuration démontré ici, vous permettant de créer des solutions de code‑barres complètes pour toute application .NET.

## Que devriez‑vous apprendre ensuite ?

Les tutoriels suivants couvrent des sujets étroitement liés qui s'appuient sur les techniques présentées dans ce guide. Chaque ressource inclut des exemples de code fonctionnels complets avec des explications pas à pas pour vous aider à maîtriser des fonctionnalités API supplémentaires et à explorer des approches d'implémentation alternatives dans vos propres projets.

- [Exemple de générateur de code‑barres en C# – Définir les colonnes, les lignes et exporter l'image](/barcode/english/python-java/general/barcode-generator-example-in-c-set-columns-rows-export-image/)
- [Guide du code‑barres DataBar Expanded Stacked – comment le générer et le dimensionner en C#](/barcode/english/python-java/general/databar-expanded-stacked-barcode-guide-how-to-generate-and-s/)
- [Exemple de générateur de code‑barres en C# – définir la largeur et la hauteur](/barcode/english/python-java/general/barcode-generator-example-in-c-set-width-and-height/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}