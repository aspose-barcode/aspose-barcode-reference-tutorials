---
category: general
date: 2026-08-09
description: Créez une image de code‑barres en C# avec ce guide étape par étape. Apprenez
  à générer un code‑barres, à ajuster la hauteur du code‑barres en pixels et à créer
  plusieurs codes‑barres efficacement.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode image
- how to generate barcode
- barcode generator c#
- create multiple barcodes
- barcode height pixels
language: fr
lastmod: 2026-08-09
og_description: Créez rapidement une image de code‑barres en C#. Suivez ce tutoriel
  pour apprendre à générer un code‑barres, définir la hauteur du code‑barres en pixels
  et produire plusieurs codes‑barres.
og_image_alt: Screenshot of barcode images generated with C# code showing different
  heights
og_title: Créer une image de code-barres en C# – guide complet pour les développeurs
schemas:
- author: Aspose
  dateModified: '2026-08-09'
  description: Create barcode image in C# with this step-by-step guide. Learn how
    to generate barcode, adjust barcode height pixels, and create multiple barcodes
    efficiently.
  headline: Create barcode image in C# – complete programming guide
  type: TechArticle
- description: Create barcode image in C# with this step-by-step guide. Learn how
    to generate barcode, adjust barcode height pixels, and create multiple barcodes
    efficiently.
  name: Create barcode image in C# – complete programming guide
  steps:
  - name: Define the output folder
    text: Choose a folder where the generated PNG files will be stored. Using an absolute
      path avoids permission surprises.
  - name: Instantiate the barcode generator
    text: For a DataBar Omnidirectional barcode, pass `EncodeTypes.DatabarOmniDirectional`
      and the GS1‑128 data string.
  - name: Set common barcode parameters
    text: The most common visual tweaks are the X‑dimension (module width) and the
      bar height. Both are expressed in pixels.
  - name: Save the first barcode image
    text: '```csharp // Step 4: Save the barcode image with a 30 px height string
      file30 = Path.Combine(outputFolder, "DatabarBarHeight30Pixels.png"); barcode.Save(file30,
      BarCodeImageFormat.Png); ```'
  - name: Adjust the barcode height pixels
    text: Changing the height does not require a new `BarcodeGenerator` instance—just
      modify the parameter.
  - name: Save the second barcode image
    text: '```csharp // Step 6: Save the barcode image with the new 60 px height string
      file60 = Path.Combine(outputFolder, "DatabarBarHeight60Pixels.png"); barcode.Save(file60,
      BarCodeImageFormat.Png); ```'
  - name: Expected output
    text: 'After running the full sample, the `Barcodes` folder contains:'
  type: HowTo
tags:
- barcode
- C#
- image generation
title: Créer une image de code-barres en C# – guide complet de programmation
url: /fr/python-java/general/create-barcode-image-in-c-complete-programming-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Créer une image de code-barres en C# – guide complet de programmation

Si vous devez **créer une image de code-barres** dans une application .NET, ce guide vous montre exactement **comment générer un code-barres** en utilisant la bibliothèque Aspose.BarCode. Vous verrez comment contrôler les **pixels de hauteur du code-barres**, enregistrer l'image et produire **plusieurs codes-barres** sans dupliquer le code.

Le tutoriel couvre tout, de l'installation du package à la personnalisation des dimensions, afin que vous puissiez copier‑coller un exemple prêt à l'emploi dans votre projet dès aujourd'hui.

## Prérequis

* SDK .NET 6.0 ou version ultérieure installé  
* Visual Studio 2022 (ou tout IDE C#)  
* Package NuGet `Aspose.BarCode` – installer avec  

```bash
dotnet add package Aspose.BarCode
```

Aucune dépendance supplémentaire n'est requise.

## Comment générer une image de code-barres avec BarcodeGenerator C#

La classe principale pour créer une image de code-barres est `BarcodeGenerator`. Elle encapsule le type d'encodage, la chaîne de données et tous les paramètres de rendu.

### Étape 1 : Définir le dossier de sortie

Choisissez un dossier où les fichiers PNG générés seront stockés. Utiliser un chemin absolu évite les surprises liées aux permissions.

```csharp
// Step 1: Define the output folder
string outputFolder = Path.Combine(Environment.CurrentDirectory, "Barcodes");
Directory.CreateDirectory(outputFolder);
```

> **Pourquoi ?** Créer le dossier de manière programmatique garantit que les appels `Save` suivants réussissent même sur une machine neuve.

### Étape 2 : Instancier le générateur de code-barres

Pour un code-barres DataBar Omnidirectional, passez `EncodeTypes.DatabarOmniDirectional` et la chaîne de données GS1‑128.

```csharp
// Step 2: Create a DataBar Omnidirectional barcode generator with the data to encode
var barcode = new BarcodeGenerator(
    EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");
```

> **Remarque :** L'objet `BarcodeGenerator` est réutilisable ; vous pouvez modifier ses paramètres entre les enregistrements pour **créer plusieurs codes-barres** à partir des mêmes données.

### Étape 3 : Définir les paramètres communs du code-barres

Les ajustements visuels les plus courants sont la X‑dimension (largeur du module) et la hauteur des barres. Les deux sont exprimés en pixels.

```csharp
// Step 3: Set common barcode parameters (X‑dimension and initial height)
barcode.Parameters.Barcode.XDimension.Pixels = 2;   // thin modules for sharper output
barcode.Parameters.Barcode.BarHeight.Pixels = 30;  // initial height – 30 px
```

> **Pourquoi définir la X‑dimension ?** Une X‑dimension plus petite donne une résolution plus élevée, ce qui est important lorsque l'image sera imprimée ou affichée sur des écrans à haute densité de pixels (DPI).

### Étape 4 : Enregistrer la première image de code-barres

```csharp
// Step 4: Save the barcode image with a 30 px height
string file30 = Path.Combine(outputFolder, "DatabarBarHeight30Pixels.png");
barcode.Save(file30, BarCodeImageFormat.Png);
```

Le fichier `DatabarBarHeight30Pixels.png` contient maintenant un code-barres DataBar Omnidirectional de 30 pixels de hauteur.

### Étape 5 : Ajuster la hauteur du code-barres en pixels

Modifier la hauteur ne nécessite pas une nouvelle instance de `BarcodeGenerator` — il suffit de modifier le paramètre.

```csharp
// Step 5: Change the bar height to 60 px for the same barcode
barcode.Parameters.Barcode.BarHeight.Pixels = 60;
```

### Étape 6 : Enregistrer la deuxième image de code-barres

```csharp
// Step 6: Save the barcode image with the new 60 px height
string file60 = Path.Combine(outputFolder, "DatabarBarHeight60Pixels.png");
barcode.Save(file60, BarCodeImageFormat.Png);
```

Vous avez maintenant deux fichiers PNG avec des **pixels de hauteur de code-barres** différents, démontrant la facilité de créer des variantes d'**image de code-barres**.

## Définir dynamiquement les pixels de hauteur du code-barres

Souvent, vous avez besoin d'une série de codes-barres avec des hauteurs correspondant aux éléments d'interface ou aux étiquettes imprimées. La méthode d'assistance suivante abstrait le changement de hauteur :

```csharp
/// <summary>
/// Saves a barcode image with a custom height.
/// </summary>
/// <param name="generator">Configured BarcodeGenerator instance.</param>
/// <param name="heightPx">Desired bar height in pixels.</param>
/// <param name="fileName">Target file name (including path).</param>
void SaveBarcodeWithHeight(BarcodeGenerator generator, int heightPx, string fileName)
{
    generator.Parameters.Barcode.BarHeight.Pixels = heightPx;
    generator.Save(fileName, BarCodeImageFormat.Png);
}
```

Vous pouvez maintenant appeler `SaveBarcodeWithHeight(barcode, 45, "BarHeight45.png");` pour **créer une image de code-barres** avec une hauteur de 45 pixels en une seule ligne.

## Créer plusieurs codes-barres dans une boucle

Lorsque vous avez une collection d'identifiants de produits, une boucle `foreach` élimine le code répétitif. Cet exemple montre comment **créer plusieurs codes-barres** à partir d'un tableau de GTIN.

```csharp
string[] gtins = { "01234567890123", "09876543210987", "12345098765432" };
int[] heights = { 30, 45, 60 }; // different heights for visual variety

for (int i = 0; i < gtins.Length; i++)
{
    // Encode each GTIN as a DataBar Omnidirectional barcode
    var gen = new BarcodeGenerator(EncodeTypes.DatabarOmniDirectional,
                                   $"(01){gtins[i]}");

    // Reuse the X‑dimension setting for consistency
    gen.Parameters.Barcode.XDimension.Pixels = 2;

    // Choose a height from the heights array (or calculate dynamically)
    int height = heights[i % heights.Length];
    string filePath = Path.Combine(outputFolder,
        $"Databar_{gtins[i]}_Height{height}px.png");

    SaveBarcodeWithHeight(gen, height, filePath);
}
```

La boucle génère trois fichiers PNG, chacun avec une valeur distincte de **pixels de hauteur du code-barres**. Comme la fonction d'assistance `SaveBarcodeWithHeight` encapsule le changement de hauteur, la boucle principale reste propre et centrée sur les données.

### Résultat attendu

Après avoir exécuté l'exemple complet, le dossier `Barcodes` contient :

```
DatabarBarHeight30Pixels.png
DatabarBarHeight60Pixels.png
Databar_01234567890123_Height30px.png
Databar_09876543210987_Height45px.png
Databar_12345098765432_Height60px.png
```

Ouvrir n'importe quel PNG montre un code-barres DataBar Omnidirectional net qui peut être scanné par des applications mobiles standard.

## Pièges courants et astuces pro

| Problème | Pourquoi cela se produit | Comment l'éviter |
|----------|--------------------------|------------------|
| **EncodeTypes incorrects** | Utiliser un type 1D pour un DataBar produira une image illisible. | Toujours choisir `EncodeTypes.DatabarOmniDirectional` (ou une autre variante DataBar) pour les charges utiles GS1‑128. |
| **X‑dimension insuffisante** | Une X‑dimension très faible peut faire disparaître les barres fines sur des moniteurs à faible résolution. | Conservez `XDimension.Pixels` ≥ 2 pour l'affichage à l'écran ; augmentez à 3‑4 pour l'impression. |
| **Erreurs de chemin de fichier** | Les chemins relatifs peuvent se résoudre vers des répertoires inattendus. | Utilisez `Path.Combine` et `Environment.CurrentDirectory` pour construire des chemins absolus. |
| **Écrasement d'images** | Réutiliser le même nom de fichier dans une boucle écrase les résultats précédents. | Incluez des identifiants uniques (par ex., GTIN ou horodatage) dans le nom de fichier. |
| **Package NuGet manquant** | Le code compile mais lève une `FileNotFoundException` à l'exécution. | Vérifiez que `Aspose.BarCode` est installé et que le projet le référence. |

## Exemple complet fonctionnel

Voici le programme complet que vous pouvez copier dans une application console. Il inclut toutes les étapes, les méthodes d'assistance et la gestion des erreurs.

```csharp
using System;
using System.IO;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Prepare output folder
        string outputFolder = Path.Combine(Environment.CurrentDirectory, "Barcodes");
        Directory.CreateDirectory(outputFolder);

        // ---------- Single barcode with two heights ----------
        var barcode = new BarcodeGenerator(
            EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");

        barcode.Parameters.Barcode.XDimension.Pixels = 2;
        barcode.Parameters.Barcode.BarHeight.Pixels = 30;
        barcode.Save(Path.Combine(outputFolder, "DatabarBarHeight30Pixels.png"),
                     BarCodeImageFormat.Png);

        barcode.Parameters.Barcode.BarHeight.Pixels = 60;
        barcode.Save(Path.Combine(outputFolder, "DatabarBarHeight60Pixels.png"),
                     BarCodeImageFormat.Png);

        // ---------- Helper for dynamic heights ----------
        void SaveBarcodeWithHeight(BarcodeGenerator gen, int heightPx, string fileName)
        {
            gen.Parameters.Barcode.BarHeight.Pixels = heightPx;
            gen.Save(fileName, BarCodeImageFormat.Png);
        }

        // ---------- Multiple barcodes ----------
        string[] gtins = { "01234567890123", "09876543210987", "12345098765432" };
        int[] heights = { 30, 45, 60 };

        for (int i = 0; i < gtins.Length; i++)
        {
            var gen = new BarcodeGenerator(EncodeTypes.DatabarOmniDirectional,
                                           $"(01){gtins[i]}");
            gen.Parameters.Barcode.XDimension.Pixels = 2;

            int height = heights[i % heights.Length];
            string filePath = Path.Combine(outputFolder,
                $"Databar_{gtins[i]}_Height{height}px.png");

            SaveBarcodeWithHeight(gen, height, filePath);
        }

        Console.WriteLine($"Barcode images created in: {outputFolder}");
    }
}
```

Exécution de ce programme

## Que devriez‑vous apprendre ensuite ?

Les tutoriels suivants couvrent des sujets étroitement liés qui s'appuient sur les techniques démontrées dans ce guide. Chaque ressource inclut des exemples de code complets avec des explications étape par étape pour vous aider à maîtriser des fonctionnalités supplémentaires de l'API et à explorer des approches d'implémentation alternatives dans vos propres projets.

- [Créer un code-barres hauteur personnalisée – Codes-barres unidimensionnels](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-barcode-height-adjustment/)
- [Créer une image de code-barres C# – Exemple GS1 DataMatrix](/barcode/english/net/gs1-barcode-encoding/gs1-datamatrix-example/)
- [Créer une image de code-barres DotCode – lignes & colonnes (Aspose.BarCode)](/barcode/english/net/dotcode-barcode-configuration/dotcode-rows-columns-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}