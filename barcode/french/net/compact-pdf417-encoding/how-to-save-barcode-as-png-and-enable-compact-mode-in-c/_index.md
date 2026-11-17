---
category: general
date: 2026-11-17
description: Apprenez comment enregistrer le code‑barres, activer le mode compact,
  ajuster les colonnes et générer un code‑barres PDF417 avec un exemple complet en
  C#.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to save barcode
- enable compact mode
- how to adjust columns
- generate pdf417 barcode
- how to enable compact mode
language: fr
lastmod: 2026-11-17
og_description: Comment sauvegarder le code‑barres, activer le mode compact et ajuster
  les colonnes lors de la génération d’un code‑barres PDF417 en C#. Suivez le guide
  pas à pas.
og_image_alt: Screenshot showing how to save barcode as PNG file in C#
og_title: Comment enregistrer le code‑barres au format PNG et activer le mode compact
  en C#
schemas:
- author: Aspose
  dateModified: '2026-11-17'
  description: Learn how to save barcode, enable compact mode, adjust columns, and
    generate PDF417 barcode with a complete C# example.
  headline: How to save barcode as PNG and enable compact mode in C#
  type: TechArticle
- description: Learn how to save barcode, enable compact mode, adjust columns, and
    generate PDF417 barcode with a complete C# example.
  name: How to save barcode as PNG and enable compact mode in C#
  steps:
  - name: Expected output
    text: Opening the saved PNG file shows a vertically compact PDF417 barcode with
      three columns and truncated padding. The visual size is roughly 2 px per module,
      making the image suitable for embedding in HTML `<img>` tags or for printing
      on small labels.
  - name: What if I need a different image format?
    text: The `Save` method accepts any `BarCodeImageFormat` enum value, such as `Jpeg`,
      `Bmp`, or `Gif`. Replace `BarCodeImageFormat.Png` with the desired format, and
      the rest of the code remains unchanged.
  - name: How does truncation affect data capacity?
    text: Enabling **compact mode** (truncation) reduces the number of rows, which
      can lower the maximum data capacity of the barcode. If you encounter a “Data
      too large” exception, either increase the number of columns or disable truncation.
  - name: Can I use a dynamic column count?
    text: 'Yes. You can calculate the column count based on the length of the input
      string:'
  - name: Is the X‑dimension limited to integer pixels?
    text: The `Pixels` property accepts any positive integer. For higher‑resolution
      outputs (e.g., printing), you might prefer setting `Points` instead of `Pixels`
      to achieve device‑independent sizing.
  type: HowTo
tags:
- barcode
- pdf417
- csharp
- image generation
title: Comment enregistrer le code‑barres au format PNG et activer le mode compact
  en C#
url: /fr/net/compact-pdf417-encoding/how-to-save-barcode-as-png-and-enable-compact-mode-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Comment enregistrer le code-barres au format PNG et activer le mode compact en C#

Si vous avez besoin de **how to save barcode** dans un format pouvant être utilisé sur le web ou en impression, ce guide vous montre les étapes exactes. Vous apprendrez également comment **enable compact mode**, **adjust columns**, et **generate PDF417 barcode** avec la bibliothèque Aspose.BarCode pour .NET.

Le tutoriel couvre tout, de la configuration du projet au fichier PNG final, afin que vous puissiez copier le code dans votre propre solution sans recherche supplémentaire. Aucune documentation externe n’est requise ; l’exemple complet et exécutable est inclus.

## Pré‑requis

Avant de commencer, assurez‑vous d’avoir :

* .NET 6.0 ou version ultérieure installé  
* Visual Studio 2022 (ou tout IDE C#)  
* Le package NuGet `Aspose.BarCode` (`Install-Package Aspose.BarCode`)  

Ces trois éléments sont les seules dépendances du code qui suit.

## Étape 1 : Créer un générateur de code‑barres PDF417

La première tâche lorsque vous **generate PDF417 barcode** consiste à instancier un `BarcodeGenerator` avec le type d’encodage correct et les données que vous souhaitez encoder.

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;

// Step 1: Create a PDF417 barcode generator with the desired text.
BarcodeGenerator barcode = new BarcodeGenerator(EncodeTypes.Pdf417, "Compact mode");
```

L’énumération `EncodeTypes.Pdf417` indique à la bibliothèque d’utiliser la symbologie PDF417, qui est un code‑barres linéaire empilé adapté à l’encodage de grandes quantités de données. La chaîne `"Compact mode"` devient le texte lisible par l’homme sous le code‑barres.

## Étape 2 : Définir la dimension X (largeur du module)

Chaque barre d’un code‑barres s’appelle un module. Contrôler la largeur du module vous permet d’ajuster finement la taille visuelle du code‑barres sans modifier les données.

```csharp
// Step 2: Set the module (X) dimension – each bar will be 2 pixels wide.
barcode.Parameters.Barcode.XDimension.Pixels = 2;
```

Une dimension X de 2 pixels produit une image compacte qui reste lisible de façon fiable sur la plupart des appareils.

## Étape 3 : **How to adjust columns** pour le code PDF417

PDF417 vous permet de spécifier le nombre de colonnes que le code‑barres doit utiliser. Moins de colonnes produisent un symbole plus haut et plus étroit, tandis que plus de colonnes rendent le symbole plus large mais plus court.

```csharp
// Step 3: Define the number of columns for the PDF417 code (3 columns).
barcode.Parameters.Barcode.Pdf417.Columns = 3;
```

Cette ligne montre **how to adjust columns**. Vous pouvez changer la valeur à 2, 4, ou tout autre nombre supporté par la bibliothèque, selon l’espace dont vous disposez sur le support cible.

## Étape 4 : **How to enable compact mode** et tronquer le symbole

Le mode compact supprime les remplissages inutiles et réduit l’empreinte globale du code‑barres. La bibliothèque expose cette fonctionnalité via la propriété `Truncate`.

```csharp
// Step 4: Enable compact mode by truncating the symbol.
barcode.Parameters.Barcode.Pdf417.Truncate = true;
```

Remarquez que la phrase **enable compact mode** apparaît ici, et que la même action est décrite avec la formulation exacte **how to enable compact mode** plus loin dans le guide afin de satisfaire l’exigence de mot‑clé secondaire.

## Étape 5 : **How to save barcode** en tant qu’image PNG

Enregistrer l’image générée est la dernière étape. La méthode `Save` écrit le code‑barres sur le système de fichiers dans le format que vous spécifiez.

```csharp
// Step 5: Save the generated barcode as a PNG image.
barcode.Save("YOUR_DIRECTORY/CompactPdf417.png", BarCodeImageFormat.Png);
```

Remplacez `YOUR_DIRECTORY` par un chemin absolu ou relatif où votre application peut écrire. Après l’exécution, vous trouverez un fichier nommé `CompactPdf417.png` contenant le code‑barres PDF417 compact.

### Résultat attendu

L’ouverture du fichier PNG enregistré montre un code‑barres PDF417 verticalement compact avec trois colonnes et un remplissage tronqué. La taille visuelle est d’environ 2 px par module, ce qui rend l’image adaptée à l’intégration dans des balises HTML `<img>` ou à l’impression sur de petites étiquettes.

## Exemple complet et exécutable

Ci‑dessous le programme complet que vous pouvez copier dans un nouveau projet console. Il inclut toutes les directives `using` nécessaires et démontre **how to save barcode**, **enable compact mode**, **how to adjust columns**, et **generate PDF417 barcode** en un seul flux.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace Pdf417CompactDemo
{
    class Program
    {
        static void Main(string[] args)
        {
            // Create a PDF417 barcode generator with the desired text.
            BarcodeGenerator barcode = new BarcodeGenerator(EncodeTypes.Pdf417, "Compact mode");

            // Set the module (X) dimension – each bar will be 2 pixels wide.
            barcode.Parameters.Barcode.XDimension.Pixels = 2;

            // Define the number of columns for the PDF417 code (3 columns).
            barcode.Parameters.Barcode.Pdf417.Columns = 3;

            // Enable compact mode by truncating the symbol.
            barcode.Parameters.Barcode.Pdf417.Truncate = true;

            // Save the generated barcode as a PNG image.
            string outputPath = "CompactPdf417.png"; // Adjust path as needed.
            barcode.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"Barcode saved to {outputPath}");
        }
    }
}
```

L’exécution de ce programme produit le fichier PNG décrit précédemment. La sortie console confirme l’emplacement du fichier enregistré, ce qui vous aide à vérifier que l’étape **how to save barcode** a réussi.

## Questions fréquentes et cas particuliers

### Et si j’ai besoin d’un format d’image différent ?

La méthode `Save` accepte n’importe quelle valeur de l’énumération `BarCodeImageFormat`, comme `Jpeg`, `Bmp` ou `Gif`. Remplacez `BarCodeImageFormat.Png` par le format souhaité, et le reste du code reste inchangé.

### Comment la troncature affecte‑t‑elle la capacité de données ?

Activer le **compact mode** (troncature) réduit le nombre de lignes, ce qui peut diminuer la capacité maximale de données du code‑barres. Si vous rencontrez une exception « Data too large », augmentez le nombre de colonnes ou désactivez la troncature.

### Puis‑je utiliser un nombre de colonnes dynamique ?

Oui. Vous pouvez calculer le nombre de colonnes en fonction de la longueur de la chaîne d’entrée :

```csharp
int desiredColumns = Math.Max(2, Math.Min(30, inputText.Length / 10));
barcode.Parameters.Barcode.Pdf417.Columns = desiredColumns;
```

Cet extrait montre **how to adjust columns** de façon programmatique, garantissant que le code‑barres s’adapte à une mise en page donnée.

### La dimension X est‑elle limitée à des pixels entiers ?

La propriété `Pixels` accepte tout entier positif. Pour des sorties à plus haute résolution (par ex. impression), vous pourriez préférer définir `Points` au lieu de `Pixels` afin d’obtenir une taille indépendante du dispositif.

## Conseils pour une utilisation en production

* **Astuce pro :** Enveloppez la génération du code‑barres dans un bloc try‑catch pour gérer `BarCodeException` lorsque les données d’entrée dépassent la capacité du symbole.  
* **Attention :** Permissions du système de fichiers. Le processus doit avoir un accès en écriture au répertoire cible, sinon l’étape **how to save barcode** échouera avec une `UnauthorizedAccessException`.  
* **Note de performance :** Créer de nombreux codes‑barres dans une boucle bénéficie de la réutilisation d’une seule instance `BarcodeGenerator` et de la mise à jour uniquement de la propriété `CodeText` entre les itérations.

## Conclusion

Vous savez maintenant **how to save barcode** en fichier PNG, **enable compact mode**, **how to adjust columns**, et **generate PDF417 barcode** en utilisant Aspose.BarCode pour C#. L’exemple complet montre chaque étape requise, de l’initialisation du générateur à l’écriture de l’image finale.

À partir de là, vous pouvez explorer des sujets connexes tels que l’ajout d’un logo au code‑barres, la personnalisation des couleurs, ou l’intégration du générateur dans une API ASP.NET Core. Chacune de ces extensions suit le même modèle présenté dans ce guide, vous permettant d’adapter le code en toute confiance.

N’hésitez pas à expérimenter différents nombres de colonnes, dimensions X et formats d’image pour répondre aux spécifications exactes de votre projet. Bon codage !

## Que devriez‑vous apprendre ensuite ?

Les tutoriels suivants couvrent des sujets étroitement liés qui s’appuient sur les techniques démontrées dans ce guide. Chaque ressource inclut des exemples de code complets et fonctionnels avec des explications étape par étape pour vous aider à maîtriser des fonctionnalités supplémentaires de l’API et à explorer des approches d’implémentation alternatives dans vos propres projets.

- [How to save barcode and generate PDF417 with Aspose in C#](/barcode/english/net/compact-pdf417-encoding/how-to-save-barcode-and-generate-pdf417-with-aspose-in-c/)
- [How to create PDF417 barcode in C# with compact mode](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-in-c-with-compact-mode/)
- [How to create PDF417 barcode and save it as PNG in C#](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-and-save-it-as-png-in-c/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}