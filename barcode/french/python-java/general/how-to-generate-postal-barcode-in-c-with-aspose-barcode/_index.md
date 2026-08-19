---
category: general
date: 2026-08-19
description: Apprenez à générer un code‑barres postal en C# avec Aspere.BarCode. Ce
  guide étape par étape montre comment créer un code‑barres pour les formats Planet
  et RM4SCC.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate postal barcode
- how to generate barcode
language: fr
lastmod: 2026-08-19
og_description: Générez un code‑barres postal en C# avec Aspose.BarCode. Suivez ce
  guide pour apprendre comment créer un code‑barres pour Planet et RM4SCC avec des
  dimensions personnalisées.
og_image_alt: Generated postal barcode image using Aspose.BarCode
og_title: Générer un code‑barres postal en C# – guide complet d’Aspose.BarCode
schemas:
- author: Aspose
  dateModified: '2026-08-19'
  description: Learn how to generate postal barcode in C# using Aspere.BarCode. This
    step‑by‑step guide shows how to generate barcode for Planet and RM4SCC formats.
  headline: How to generate postal barcode in C# with Aspose.BarCode
  type: TechArticle
- description: Learn how to generate postal barcode in C# using Aspere.BarCode. This
    step‑by‑step guide shows how to generate barcode for Planet and RM4SCC formats.
  name: How to generate postal barcode in C# with Aspose.BarCode
  steps:
  - name: Create a Planet barcode (automatic height)
    text: Planet is a postal barcode used in many countries for mail sorting. When
      you create a Planet barcode, the library automatically determines the optimal
      bar height based on the encoded data.
  - name: Create an RM4SCC barcode with explicit height
    text: RM4SCC is another postal symbology that often requires a specific bar height
      for scanner compatibility. The following code shows how to set that height manually.
  - name: Verify the output
    text: 'After running the program, open the two PNG files located in `YOUR_DIRECTORY`.
      You should see two distinct barcodes:'
  type: HowTo
tags:
- barcode
- Aspose.BarCode
- C#
title: Comment générer un code‑barres postal en C# avec Aspose.BarCode
url: /fr/python-java/general/how-to-generate-postal-barcode-in-c-with-aspose-barcode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Comment générer un code‑barres postal en C# avec Aspose.BarCode

Si vous devez **générer un code‑barres postal** pour des applications d'envoi, ce guide vous montre exactement comment générer un code‑barres en utilisant la bibliothèque Aspose.BarCode. Vous verrez un exemple complet et exécutable qui crée à la fois un code‑barres Planet (hauteur calculée automatiquement) et un code‑barres RM4SCC avec une hauteur de barre explicite.

La génération de code‑barres postal est une exigence courante pour les logiciels logistiques, les imprimantes d'étiquettes automatisées et les systèmes d'envoi en masse. À la fin de ce tutoriel, vous serez capable d'intégrer la génération de code‑barres dans n'importe quel projet .NET, de personnaliser la X‑dimension et de contrôler la hauteur des barres lorsque le format standard le permet.

**Ce que vous apprendrez**

* Comment configurer Aspose.BarCode dans un projet C#.
* Comment générer les codes‑barres postaux Planet et RM4SCC.
* Comment ajuster la X‑dimension (largeur du module) et la hauteur des barres.
* Comment enregistrer le résultat sous forme d'image PNG.

Aucun service externe n'est requis — tout s'exécute localement après avoir référencé le package NuGet Aspose.BarCode.

## Prérequis

* .NET 6.0 SDK ou version ultérieure (le code fonctionne également avec .NET Framework 4.7+).  
* Visual Studio 2022, Visual Studio Code, ou tout IDE C# de votre choix.  
* Package Aspose.BarCode for .NET – installez-le via NuGet :

```bash
dotnet add package Aspose.BarCode
```

## Générer un code‑barres postal avec Aspose.BarCode

Les sections suivantes vous guident à travers chaque étape, de la création des objets générateurs à l'enregistrement des fichiers PNG finaux.

### Étape 1 : Créer un code‑barres Planet (hauteur automatique)

Planet est un code‑barres postal utilisé dans de nombreux pays pour le tri du courrier. Lorsque vous créez un code‑barres Planet, la bibliothèque détermine automatiquement la hauteur optimale des barres en fonction des données encodées.

```csharp
using Aspose.BarCode.Generation;

// Create a Planet barcode generator with the data you want to encode.
BarcodeGenerator planetGenerator = new BarcodeGenerator(EncodeTypes.Planet, "123456");

// Define the X‑dimension (module width) in pixels. A value of 4 pixels is a good default.
planetGenerator.Parameters.Barcode.XDimension.Pixels = 4;

// Save the barcode as a PNG image. The height is calculated automatically.
planetGenerator.Save("YOUR_DIRECTORY/PostalPlanetBarHeightNone.png", BarCodeImageFormat.Png);
```

**Pourquoi cela fonctionne** – `EncodeTypes.Planet` indique à Aspose.BarCode d'utiliser la symbologie Planet. La propriété `XDimension` contrôle la largeur de la plus petite barre (le module). Comme Planet ne nécessite pas de hauteur de barre fixe, la bibliothèque calcule automatiquement une hauteur adaptée, ce qui simplifie le code.

### Étape 2 : Créer un code‑barres RM4SCC avec hauteur explicite

RM4SCC est une autre symbologie postale qui nécessite souvent une hauteur de barre spécifique pour la compatibilité avec les scanners. Le code suivant montre comment définir cette hauteur manuellement.

```csharp
// Create an RM4SCC barcode generator.
BarcodeGenerator rm4sccGenerator = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");

// Set the X‑dimension (module width) and the desired bar height in pixels.
rm4sccGenerator.Parameters.Barcode.XDimension.Pixels = 4;
rm4sccGenerator.Parameters.Barcode.BarHeight.Pixels = 100;

// Save the barcode as a PNG image.
rm4sccGenerator.Save("YOUR_DIRECTORY/PostalRM4SCCBarHeight100Pixels.png", BarCodeImageFormat.Png);
```

**Pourquoi vous définissez la hauteur** – Certains scanners postaux attendent une hauteur de barre minimale. En assignant `BarHeight.Pixels = 100`, vous garantissez que l'image générée répond à ces exigences. La X‑dimension reste cohérente avec le code‑barres Planet afin que les deux images partagent la même densité visuelle.

### Étape 3 : Vérifier la sortie

Après avoir exécuté le programme, ouvrez les deux fichiers PNG situés dans `YOUR_DIRECTORY`. Vous devriez voir deux codes‑barres distincts :

* `PostalPlanetBarHeightNone.png` – un code‑barres Planet avec hauteur calculée automatiquement.  
* `PostalRM4SCCBarHeight100Pixels.png` – un code‑barres RM4SCC avec une hauteur de barre de 100 pixels.

Les deux images peuvent être directement envoyées aux imprimantes d'étiquettes ou affichées dans une application web.

![Generated postal barcode image using Aspose.BarCode](generated-postal-barcode.png)

*Texte alternatif de l'image :* **Code‑barres postal généré** image using Aspose.BarCode (démontre comment générer un code‑barres postal).

## Comment générer un code‑barres avec des dimensions personnalisées (avancé)

Si vous devez affiner d'autres paramètres — tels que les marges, le placement du texte ou la couleur — Aspose.BarCode fournit un objet `Parameters` riche. Voici un exemple rapide qui ajoute un arrière‑plan blanc et désactive le texte lisible par l'homme.

```csharp
planetGenerator.Parameters.Barcode.BackColor = System.Drawing.Color.White;
planetGenerator.Parameters.Barcode.CodeTextVisible = false;
planetGenerator.Save("YOUR_DIRECTORY/PostalPlanetNoText.png", BarCodeImageFormat.Png);
```

**Quand l'utiliser** – Désactiver le texte lisible par l'homme est courant pour le tri automatisé où seul le motif lisible par la machine importe. Définir une couleur d'arrière‑plan garantit que le code‑barres s'imprime correctement sur un support transparent.

## Pièges courants et astuces pro

| Problème | Pourquoi cela se produit | Solution |
|----------|--------------------------|----------|
| Le code‑barres apparaît étiré | La X‑dimension est trop grande par rapport à la taille de l'image | Conservez `XDimension.Pixels` entre 2 et 5 pour la plupart des codes‑barres postaux |
| Le scanner rejette l'image | La hauteur de la barre est inférieure au minimum requis par le service postal | Utilisez `BarHeight.Pixels` ≥ 80 pour RM4SCC sauf si la spécification indique le contraire |
| La taille du fichier PNG est grande | La résolution de l'image est supérieure à ce qui est nécessaire | Enregistrez en PNG‑8 (`BarCodeImageFormat.Png8`) ou réduisez les dimensions en pixels |

**Astuce pro :** Testez toujours le code‑barres généré avec un vrai scanner avant de le déployer en production. De petites différences visuelles peuvent affecter la lisibilité.

## Code source complet

Copiez le bloc complet ci‑dessus dans une nouvelle application console (`Program.cs`). Ajustez les chemins de sortie vers un dossier dans lequel votre processus peut écrire.

```csharp
using System;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // ------------------------------
        // Generate Planet barcode (auto height)
        // ------------------------------
        BarcodeGenerator planetGenerator = new BarcodeGenerator(EncodeTypes.Planet, "123456");
        planetGenerator.Parameters.Barcode.XDimension.Pixels = 4;
        planetGenerator.Save("PostalPlanetBarHeightNone.png", BarCodeImageFormat.Png);

        // ------------------------------
        // Generate RM4SCC barcode (explicit height)
        // ------------------------------
        BarcodeGenerator rm4sccGenerator = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");
        rm4sccGenerator.Parameters.Barcode.XDimension.Pixels = 4;
        rm4sccGenerator.Parameters.Barcode.BarHeight.Pixels = 100;
        rm4sccGenerator.Save("PostalRM4SCCBarHeight100Pixels.png", BarCodeImageFormat.Png);

        Console.WriteLine("Barcodes generated successfully.");
    }
}
```

L'exécution du programme affiche *« Barcodes generated successfully. »* et crée les deux fichiers PNG dans le répertoire de travail de l'exécutable.

## Conclusion

Vous savez maintenant comment **générer un code‑barres postal** en C# avec Aspose.BarCode, couvrant à la fois les codes‑barres Planet à hauteur automatique et les codes‑barres RM4SCC à hauteur fixe. Le guide a également montré **comment générer un code‑barres** avec une X‑dimension personnalisée, une hauteur de barre et des options visuelles, offrant une base solide pour tout projet d'automatisation d'envoi.

Les prochaines étapes que vous pourriez explorer :

* Intégrer les PNG générés dans une facture PDF à l'aide d'Aspose.PDF.  
* Passer le format de sortie à SVG pour des graphiques vectoriels évolutifs.  
* Utiliser la classe `BarcodeReader` pour vérifier les données encodées programmatiquement.

N'hésitez pas à expérimenter différentes symbologies (par ex., `EncodeTypes.Postnet`) et à partager vos résultats avec la communauté. Bon codage !

## Que devriez‑vous apprendre ensuite ?

Les tutoriels suivants couvrent des sujets étroitement liés qui s'appuient sur les techniques démontrées dans ce guide. Chaque ressource comprend des exemples de code complets et fonctionnels avec des explications étape par étape pour vous aider à maîtriser des fonctionnalités API supplémentaires et explorer des approches d'implémentation alternatives dans vos propres projets.

- [Comment générer une image de code‑barres avec personnalisation de l'espace supplémentaire en utilisant Aspose.BarCode](/barcode/english/net/supplemental-barcode-data/supplemental-barcode-space-customization/)
- [Comment générer un code‑barres – Configuration Code 39 avec Aspose.BarCode](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-code-39-configuration/)
- [Comment générer des codes‑barres DataMatrix (ECC 200) avec Aspose.BarCode pour .NET](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-ecc-200-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}