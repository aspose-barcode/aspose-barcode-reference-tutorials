---
category: general
date: 2026-08-12
description: Créer une image de code‑barres en C# avec BarCodeGenerator. Apprenez
  à générer DataBar, à contrôler la taille de l’image du code‑barres et à créer plusieurs
  codes‑barres efficacement.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode image
- barcode generator c#
- create multiple barcodes
- how to generate databar
- barcode image size
language: fr
lastmod: 2026-08-12
og_description: Créer une image de code‑barres en C# avec BarCodeGenerator. Ce tutoriel
  montre étape par étape comment générer des codes DataBar, ajuster la taille de l’image
  du code‑barres et produire plusieurs codes‑barres.
og_image_alt: Screenshot of a generated DataBar barcode image saved as PNG
og_title: Créer une image de code-barres en C# – guide complet de BarCodeGenerator
schemas:
- author: Aspose
  dateModified: '2026-08-12'
  description: Create barcode image in C# using BarCodeGenerator. Learn how to generate
    DataBar, control barcode image size, and create multiple barcodes efficiently.
  headline: Create barcode image in C# with BarCodeGenerator
  type: TechArticle
- description: Create barcode image in C# using BarCodeGenerator. Learn how to generate
    DataBar, control barcode image size, and create multiple barcodes efficiently.
  name: Create barcode image in C# with BarCodeGenerator
  steps:
  - name: Setting up a **barcode generator c#** instance for DataBar Omni‑directional
      encoding.
    text: Setting up a **barcode generator c#** instance for DataBar Omni‑directional
      encoding.
  - name: Adjusting **barcode image size** by changing X‑dimension and bar height.
    text: Adjusting **barcode image size** by changing X‑dimension and bar height.
  - name: Using a loop to **create multiple barcodes** with different heights.
    text: Using a loop to **create multiple barcodes** with different heights.
  - name: Saving the images as PNG files and verifying the output.
    text: Saving the images as PNG files and verifying the output.
  type: HowTo
tags:
- barcode
- csharp
- barcodegenerator
- databar
- image-processing
title: Créer une image de code-barres en C# avec BarCodeGenerator
url: /fr/python-java/general/create-barcode-image-in-c-with-barcodegenerator/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Créer une image de code-barres en C# avec BarCodeGenerator

Si vous devez **créer une image de code-barres** dans une application .NET, ce guide vous montre exactement comment le faire avec la classe `BarCodeGenerator`. Que vous construisiez un système de point de vente (POS) pour le commerce de détail ou un outil de suivi d'inventaire, vous apprendrez à générer des symboles DataBar, à contrôler la taille de l'image du code-barres et à produire plusieurs codes-barres en une seule exécution.

Vous découvrirez également comment l'API **barcode generator c#** vous permet d'ajuster les dimensions, de changer les formats de sortie et de gérer les cas limites tels que les chaînes de données invalides. À la fin du tutoriel, vous pourrez **créer plusieurs codes-barres** en toute confiance sans écrire de code répétitif.

## Prérequis

- .NET 6.0 ou version ultérieure installé  
- Un environnement de développement (Visual Studio, Rider ou VS Code)  
- Le package NuGet Aspose.BarCode for .NET (ou toute bibliothèque compatible qui fournit `BarCodeGenerator`)  

Vous pouvez ajouter le package avec:

```bash
dotnet add package Aspose.BarCode
```

## Ce que couvre ce tutoriel

1. Configurer une instance **barcode generator c#** pour l'encodage DataBar Omni‑directional.  
2. Ajuster la **taille de l'image du code-barres** en modifiant la X‑dimension et la hauteur des barres.  
3. Utiliser une boucle pour **créer plusieurs codes-barres** avec des hauteurs différentes.  
4. Enregistrer les images au format PNG et vérifier le résultat.  

Tous les extraits de code sont complets et prêts à être copiés‑collés dans un nouveau projet console.

![Exemple de création d'image de code-barres](barcode-example.png){alt="Exemple de création d'image de code-barres"}

## Étape 1 : Initialiser le générateur – bases de la création d'image de code-barres

La première étape consiste à instancier `BarCodeGenerator` avec la symbologie souhaitée. Pour un symbole DataBar Omni‑directional, vous utilisez `EncodeTypes.DatabarOmniDirectional`.

```csharp
using System;
using Aspose.BarCode.Generation;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // Create a barcode generator for DataBar Omni‑directional.
            // The string "(01)12345678901231" follows the GS1 Application Identifier format.
            var generator = new BarCodeGenerator(EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");

            // The rest of the steps are performed below.
        }
    }
}
```

**Pourquoi c'est important :** L'instanciation du générateur définit les règles d'encodage et la charge de données. Si vous omettez la valeur correcte de `EncodeTypes`, la bibliothèque générera un code-barres non pris en charge ou lèvera une exception.

## Étape 2 : Configurer la X‑dimension et la hauteur des barres – contrôler la taille de l'image du code-barres

La taille visuelle d'un code-barres est déterminée par deux paramètres :

| Paramètre | Ce qu'il contrôle | Plage typique |
|-----------|-------------------|----------------|
| `x_dimension.pixels` | Largeur du plus petit module (le « point ») | 1 – 4 px |
| `bar_height.pixels`  | Hauteur des barres verticales                | 30 – 150 px |

```csharp
// Set the module width to 2 px for a crisp, readable image.
generator.Parameters.Barcode.XDimension.Pixels = 2;

// Set an initial bar height of 30 px.
generator.Parameters.Barcode.BarHeight.Pixels = 30;
```

**Astuce :** Une X‑dimension plus petite donne une image à plus haute résolution mais peut être plus difficile à scanner avec des imprimantes de basse qualité. Ajustez la valeur en fonction de votre équipement de numérisation cible.

## Étape 3 : Enregistrer le premier code-barres – créer une image de code-barres pour une hauteur de 30 px

Vous pouvez maintenant générer l'image et l'écrire sur le disque. La méthode `Save` accepte un chemin de fichier et une énumération de format d'image.

```csharp
// Save the 30 px high barcode as a PNG file.
string outputFolder = @"C:\Barcodes";
generator.Save($"{outputFolder}\\Databar30.png", BarCodeImageFormat.Png);
Console.WriteLine("Saved Databar30.png (30 px height)");
```

**Résultat attendu :** Un fichier PNG nommé `Databar30.png` apparaît dans `C:\Barcodes`. L'ouverture du fichier montre un symbole DataBar Omni‑directional avec un motif clair et à fort contraste.

## Étape 4 : Modifier la hauteur et générer des images supplémentaires – créer plusieurs codes-barres

Pour **créer plusieurs codes-barres** avec des dimensions différentes, il suffit de modifier la propriété `BarHeight` et d'appeler à nouveau `Save`. Cela évite de ré‑instancier le générateur, ce qui économise de la mémoire et du temps CPU.

```csharp
// Increase the bar height to 60 px for a larger barcode.
generator.Parameters.Barcode.BarHeight.Pixels = 60;
generator.Save($"{outputFolder}\\Databar60.png", BarCodeImageFormat.Png);
Console.WriteLine("Saved Databar60.png (60 px height)");

// You can repeat the process for any height you need.
int[] heights = { 90, 120 };
foreach (int h in heights)
{
    generator.Parameters.Barcode.BarHeight.Pixels = h;
    generator.Save($"{outputFolder}\\Databar{h}.png", BarCodeImageFormat.Png);
    Console.WriteLine($"Saved Databar{h}.png ({h} px height)");
}
```

**Pourquoi cela fonctionne :** L'objet `BarCodeGenerator` conserve tout l'état de configuration. Modifier une seule propriété met à jour le moteur de rendu pour l'appel suivant de `Save`, vous permettant de **créer plusieurs codes-barres** efficacement.

## Étape 5 : Avancé – comment générer un DataBar avec des données personnalisées

L'exemple ci‑dessus utilise une charge utile GS1 statique. Dans des scénarios réels, vous devez souvent intégrer des identifiants de produit variables. La bibliothèque accepte toute chaîne qui correspond à la spécification DataBar.

```csharp
string[] gtins = { "01234567890123", "98765432109876", "12345678901234" };
foreach (var gtin in gtins)
{
    // GS1 Application Identifier (01) + GTIN
    generator.CodeText = $"(01){gtin}";
    generator.Parameters.Barcode.BarHeight.Pixels = 50; // uniform height
    generator.Save($"{outputFolder}\\Databar_{gtin}.png", BarCodeImageFormat.Png);
    Console.WriteLine($"Saved barcode for GTIN {gtin}");
}
```

**Point clé :** Définir `generator.CodeText` met à jour les données encodées sans recréer l'objet. C'est le modèle recommandé **how to generate databar** lors du traitement de grands ensembles de données.

## Étape 6 : Vérifier et dépanner – garantir la bonne taille de l'image du code-barres

Après avoir généré les images, vous pouvez vouloir confirmer programmétiquement que les dimensions correspondent à vos attentes. La classe `Image` de `System.Drawing` peut lire le fichier et rapporter sa taille.

```csharp
using System.Drawing;

// Verify image dimensions
string[] files = { "Databar30.png", "Databar60.png", "Databar90.png" };
foreach (var file in files)
{
    using var img = Image.FromFile($"{outputFolder}\\{file}");
    Console.WriteLine($"{file}: {img.Width}px × {img.Height}px");
}
```

Si la hauteur ne reflète pas la valeur que vous avez définie, vérifiez :

- **X‑dimension** : Une valeur très petite peut amener le rendu à arrondir la hauteur.  
- **Format d'image** : Certains formats (par ex., JPEG) appliquent une compression qui peut modifier les dimensions en pixels lors de l'enregistrement. PNG préserve les dimensions exactes.

## Étape 7 : Bonnes pratiques pour la taille de l'image du code-barres et les performances

| Recommandation | Raison |
|----------------|--------|
| Conservez `x_dimension.pixels` entre 2 – 3 px pour la plupart des scanners. | Équilibre lisibilité et taille du fichier. |
| Utilisez PNG pour une sortie sans perte lorsque l'image sera imprimée. | Garantit des dimensions exactes et des bords nets. |
| Réutilisez une seule instance de `BarCodeGenerator` lors de la génération de nombreux codes-barres. | Réduit la surcharge d'allocation d'objets. |
| Validez la chaîne d'entrée selon la norme GS1 avant de l'assigner à `CodeText`. | Empêche les exceptions d'exécution et les scans invalides. |
| Stockez les images générées dans un dossier dédié avec une convention de nommage claire (par ex., `Databar_{GTIN}.png`). | Simplifie le traitement en aval et les traces d'audit. |

## Exemple complet fonctionnel

Voici le programme complet qui intègre toutes les étapes, de l'initialisation à la vérification. Copiez le code dans un nouveau projet console et exécutez-le.



## Que devriez‑vous apprendre ensuite ?

Les tutoriels suivants couvrent des sujets étroitement liés qui s'appuient sur les techniques démontrées dans ce guide. Chaque ressource comprend des exemples de code complets et fonctionnels avec des explications étape par étape pour vous aider à maîtriser des fonctionnalités API supplémentaires et explorer des approches d'implémentation alternatives dans vos propres projets.

- [Générer une image de code-barres – GS1 Coupon UPC‑A Databar](/barcode/english/net/gs1-barcode-encoding/gs1-coupon-upc-a-databar-configuration/)
- [Créer une image de code-barres DotCode – lignes & colonnes (Aspose.BarCode)](/barcode/english/net/dotcode-barcode-configuration/dotcode-rows-columns-configuration/)
- [Comment créer une zone silencieuse de code-barres pour ITF‑14 avec Aspose.BarCode pour .NET](/barcode/english/net/itf-14-barcode-customization/itf-14-barcode-quiet-zone-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}