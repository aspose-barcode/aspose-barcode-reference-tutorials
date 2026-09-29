---
category: general
date: 2026-09-07
description: Tutoriel de générateur de codes-barres C# qui vous montre comment générer
  des fichiers PNG de codes-barres et créer des codes-barres DataBar avec des lignes
  et colonnes personnalisables.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- barcode generator C#
- generate barcode PNG
- create DataBar barcode
language: fr
lastmod: 2026-09-07
og_description: 'tutoriel générateur de codes-barres C# : apprenez à générer des fichiers
  PNG de codes-barres et à créer des codes-barres DataBar avec des lignes et colonnes
  personnalisées en quelques minutes'
og_image_alt: Sample DataBar Expanded Stacked barcode saved as PNG using barcode generator
  C#
og_title: Générateur de codes-barres C# – créer des codes-barres DataBar et images
  PNG
schemas:
- author: Aspose
  dateModified: '2026-09-07'
  description: barcode generator C# tutorial that shows you how to generate barcode
    PNG files and create DataBar barcodes with customizable rows and columns
  headline: How to use a barcode generator C# to create DataBar barcodes
  type: TechArticle
tags:
- barcode
- C#
- DataBar
title: Comment utiliser un générateur de codes-barres C# pour créer des codes-barres
  DataBar
url: /fr/python-java/general/how-to-use-a-barcode-generator-c-to-create-databar-barcodes/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Comment utiliser un barcode generator C# pour créer des codes-barres DataBar

Si vous avez besoin d’un **barcode generator C#** pour créer des codes-barres de haute qualité, ce guide vous montre comment **générer des fichiers PNG de code-barres** et **créer des codes-barres DataBar** avec des lignes et colonnes personnalisées. Que vous construisiez un système d’inventaire de détail ou une plateforme de billetterie, les étapes ci‑dessous vous permettent de produire un code‑barres DataBar Expanded Stacked dans un exemple unique et autonome.

Dans ce tutoriel, vous apprendrez :

* Comment instancier le `BarcodeGenerator` pour la symbologie DataBar Expanded Stacked.  
* Comment ajuster les paramètres de colonnes et de lignes pour répondre aux spécifications ISO / GS1.  
* Comment enregistrer la sortie sous forme d’image PNG pouvant être intégrée dans des pages web ou imprimée sur des étiquettes.  

Aucun service externe n’est requis — il suffit de la bibliothèque Aspose.BarCode for .NET (ou toute bibliothèque compatible qui suit la même API). Le code s’exécute sur .NET 6+ et fonctionne dans Visual Studio, Rider ou tout IDE supportant C#.

## Prérequis

Avant de commencer, assurez‑vous d’avoir :

* .NET 6 SDK ou version ultérieure installé.  
* Une référence au package NuGet `Aspose.BarCode` (ou une bibliothèque équivalente qui fournit `BarcodeGenerator`, `EncodeTypes` et `BarCodeImageFormat`).  
* Une connaissance de base de la syntaxe C# et de la structure d’un projet.  

Vous pouvez ajouter le package via la ligne de commande :

```bash
dotnet add package Aspose.BarCode
```

## Étape 1 : Initialiser le barcode generator C# pour DataBar Expanded Stacked

La première étape consiste à créer une instance de `BarcodeGenerator` qui cible la symbologie **DataBar Expanded Stacked**. Cet objet contient tous les paramètres de rendu, y compris le texte à encoder.

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;

// Step 1: Create a barcode generator for DataBar Expanded Stacked
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.DatabarExpandedStacked,          // Symbology
    "Databar Expanded Stacked long");            // Data to encode
```

**Pourquoi c’est important :** La valeur d’énumération `EncodeTypes.DatabarExpandedStacked` indique à la bibliothèque quel standard de code‑barres appliquer. Utiliser la bonne énumération garantit que l’image générée respecte les spécifications GS1 DataBar.

## Étape 2 : Configurer le nombre de colonnes (les lignes par défaut sont utilisées)

DataBar Expanded Stacked peut être divisé en plusieurs colonnes. Ajuster le nombre de colonnes modifie la densité visuelle et peut aider à faire tenir des chaînes de données plus longues dans un espace limité.

```csharp
// Step 2: Set the number of columns (default rows are used)
barcodeGenerator.Parameters.Barcode.DataBar.Columns = 4;
```

**Astuce :** Le nombre de colonnes par défaut est 1. Le définir à 4 crée quatre colonnes empilées, ce qui est idéal pour des chaînes numériques plus longues tout en gardant la hauteur du code‑barres gérable.

## Étape 3 : Générer un PNG de code‑barres avec le paramètre de colonne appliqué

Enregistrez maintenant le code‑barres sous forme d’image PNG. Le PNG préserve les bords nets nécessaires aux scanners et fonctionne bien tant sur le web que sur les supports imprimés.

```csharp
// Step 3: Save the barcode image with the column setting applied
barcodeGenerator.Save("YOUR_DIRECTORY/DatabarCols4.png", BarCodeImageFormat.Png);
```

Le fichier `DatabarCols4.png` contient un **barcode PNG** que vous pouvez intégrer directement dans du HTML :

```html
<img src="DatabarCols4.png" alt="Sample DataBar Expanded Stacked barcode saved as PNG using barcode generator C#">
```

## Étape 4 : Créer une instance distincte du générateur pour la configuration des lignes

Si vous devez contrôler le nombre de lignes plutôt que de colonnes, instanciez un nouveau `BarcodeGenerator`. Réutiliser la même instance après avoir modifié une dimension peut entraîner des artefacts de mise en page inattendus, donc un nouvel objet est l’approche la plus sûre.

```csharp
// Step 4: Create a new generator instance for the same barcode type
BarcodeGenerator rowBarcodeGenerator = new BarcodeGenerator(
    EncodeTypes.DatabarExpandedStacked,
    "Databar Expanded Stacked long");
```

## Étape 5 : Définir le nombre de lignes (les colonnes par défaut sont utilisées)

Les lignes affectent l’empilement vertical des modules du code‑barres. Augmenter le nombre de lignes peut rendre le code‑barres plus haut, ce qui peut être requis pour certaines tailles d’étiquettes.

```csharp
// Step 5: Set the number of rows (default columns are used)
rowBarcodeGenerator.Parameters.Barcode.DataBar.Rows = 3;
```

**Pourquoi lignes vs. colonnes :** Les colonnes divisent le code‑barres horizontalement, tandis que les lignes l’étendent verticalement. Choisissez l’orientation qui convient le mieux à la mise en page de votre étiquette.

## Étape 6 : Générer un PNG de code‑barres avec le paramètre de ligne appliqué

Enfin, enregistrez le code‑barres ajusté en fonction des lignes sous forme de fichier PNG.

```csharp
// Step 6: Save the barcode image with the row setting applied
rowBarcodeGenerator.Save("YOUR_DIRECTORY/DatabarRows3.png", BarCodeImageFormat.Png);
```

Vous avez maintenant deux fichiers PNG distincts :

* `DatabarCols4.png` – 4 colonnes, 1 ligne.  
* `DatabarRows3.png` – 1 colonne, 3 lignes.

Les deux images sont prêtes à être utilisées immédiatement dans des applications, des rapports ou des étiquettes imprimées.

## Comment générer des fichiers PNG de code‑barres en C# avec des dimensions personnalisées

Le modèle présenté ci‑dessus peut être réutilisé pour n’importe quelle variante DataBar ou d’autres symbologies prises en charge par la bibliothèque. Voici un modèle compact que vous pouvez copier‑coller dans une classe utilitaire :

```csharp
public static void GenerateDatabar(string data, int columns = 1, int rows = 1, string outputPath = "output.png")
{
    BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.DatabarExpandedStacked, data);
    generator.Parameters.Barcode.DataBar.Columns = columns;
    generator.Parameters.Barcode.DataBar.Rows = rows;
    generator.Save(outputPath, BarCodeImageFormat.Png);
}
```

Appelez la méthode ainsi :

```csharp
GenerateDatabar("1234567890123", columns: 4, outputPath: "DatabarCols4.png");
GenerateDatabar("1234567890123", rows: 3, outputPath: "DatabarRows3.png");
```

**Cas limites à considérer**

* **Longueur des données** – DataBar Expanded Stacked peut encoder jusqu’à 74 caractères numériques. Dépasser cette limite génère une exception. Validez la longueur de l’entrée avant d’appeler le générateur.  
* **Dimensions invalides** – La bibliothèque limite les colonnes à 1‑4 et les lignes à 1‑3 pour cette symbologie. Fournir des valeurs en dehors de ces plages sera ignoré ou provoquera une erreur.  
* **DPI de l’image** – Si vous avez besoin d’une résolution supérieure pour l’impression, définissez `generator.Parameters.ImageResolution` avant d’enregistrer.

## Résultat attendu

Lorsque vous ouvrez `DatabarCols4.png` ou `DatabarRows3.png`, vous devez voir un code‑barres DataBar clair et à fort contraste. Scanner l’image avec un lecteur compatible GS1 renvoie le texte original `"Databar Expanded Stacked long"`.

![Sample DataBar Expanded Stacked barcode saved as PNG using barcode generator C#](image.png)

*Texte alternatif : Exemple de code‑barres DataBar Expanded Stacked enregistré en PNG à l’aide du barcode generator C#*

## Conclusion

Ce tutoriel a démontré comment un **barcode generator C#** peut être utilisé pour **créer des codes‑barres DataBar** et **générer des fichiers PNG de code‑barres** avec des paramètres de lignes et de colonnes personnalisés. En suivant les six étapes — initialisation du générateur, configuration des colonnes ou des lignes, et enregistrement en PNG — vous obtenez des images prêtes pour la production, adaptées aux systèmes d’inventaire, à la billetterie ou à tout scénario nécessitant un rendu fiable de code‑barres.

Ensuite, vous pourriez explorer :

* Ajouter de la couleur ou des images d’arrière‑plan au PNG (toujours compatible avec la plupart des scanners).  
* Utiliser d’autres symbologies telles que QR, Code 128 ou PDF417 via la même API `BarcodeGenerator`.  
* Intégrer le PNG généré directement dans les vues ASP.NET Core MVC ou les composants Blazor.  

N’hésitez pas à expérimenter avec différentes chaînes de données, dimensions et formats d’image (par ex., JPEG, BMP). Le même modèle s’applique, faisant du **barcode generator C#** un outil polyvalent dans la boîte à outils de tout développeur .NET. Bon codage !

## Que devriez‑vous apprendre ensuite ?

Les tutoriels suivants couvrent des sujets étroitement liés qui s’appuient sur les techniques démontrées dans ce guide. Chaque ressource comprend des exemples de code complets et fonctionnels avec des explications étape par étape pour vous aider à maîtriser des fonctionnalités API supplémentaires et explorer des approches d’implémentation alternatives dans vos propres projets.

- [Générer un code‑barres C# – Créer un code‑barres DataBar](/barcode/english/python-java/general/generate-barcode-c-create-databar-barcode/)
- [Exemple de Barcode Generator – Construire une image DataBar en C#](/barcode/english/python-java/general/barcode-generator-example-build-databar-image-in-c/)
- [Exemple de Barcode Generator en C# – Définir les colonnes, les lignes et exporter l’image](/barcode/english/python-java/general/barcode-generator-example-in-c-set-columns-rows-export-image/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}