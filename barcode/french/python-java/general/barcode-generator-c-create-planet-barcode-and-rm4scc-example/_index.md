---
category: general
date: 2026-08-03
description: Tutoriel C# sur le générateur de codes-barres montrant comment créer
  un code-barres Planet avec Aspose.BarCode, définir la dimension X et enregistrer
  en images PNG.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- barcode generator c#
- create planet barcode
language: fr
lastmod: 2026-08-03
og_description: Le tutoriel du générateur de codes‑barres C# vous guide dans la création
  d’un code‑barres Planet, l’ajustement de la dimension X et l’enregistrement au format
  PNG à l’aide d’Aspose.BarCode.
og_image_alt: Screenshot of generated Planet and RM4SCC barcodes in PNG format
og_title: Générateur de code‑barres C# – créer un code‑barres Planet étape par étape
schemas:
- author: Aspose
  dateModified: '2026-08-03'
  description: Barcode generator C# tutorial showing how to create Planet barcode
    with Aspose.BarCode, set X‑dimension, and save as PNG images.
  headline: Barcode generator C# – create Planet barcode and RM4SCC example
  type: TechArticle
tags:
- barcode
- C#
- Aspose.BarCode
title: Générateur de codes-barres C# – créer un code-barres Planet et un exemple RM4SCC
url: /fr/python-java/general/barcode-generator-c-create-planet-barcode-and-rm4scc-example/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Générateur de code-barres C# – créer un code-barres Planet et un exemple RM4SCC

Si vous avez besoin d’un **générateur de code-barres C#** capable de produire des symboles postaux spécifiques, ce guide vous montre exactement comment **créer des images de code-barres Planet** avec Aspose.BarCode. Vous verrez comment configurer la dimension X, générer un code‑barres RM4SCC correspondant, et enregistrer les deux au format PNG — le tout en quelques étapes concises.

Le tutoriel couvre tout ce dont vous avez besoin pour exécuter le code sur .NET 6 ou version ultérieure, explique pourquoi chaque paramètre est important, et signale les pièges courants tels qu’une largeur de module incorrecte ou des permissions de répertoire manquantes. À la fin, vous disposerez de deux images de code‑barres prêtes à imprimer, conformes aux normes Planet et RM4SCC.

## Prérequis

Avant de commencer, assurez‑vous d’avoir :

* SDK .NET 6 (ou toute version .NET prise en charge par Aspose.BarCode)
* Visual Studio 2022 ou tout IDE C# de votre choix
* Une référence NuGet à **Aspose.BarCode** (`Install-Package Aspose.BarCode`)
* Le droit d’écriture sur le dossier où vous prévoyez d’enregistrer les fichiers PNG

Aucun service externe supplémentaire n’est requis ; la bibliothèque gère tout le codage en local.

## Étape 1 : Initialiser l’objet générateur de code‑barres C#

La première tâche consiste à créer une instance de `BarcodeGenerator`. Le constructeur prend la symbologie du code‑barres (`EncodeTypes.Planet`) et les données à encoder.

```csharp
using Aspose.BarCode.Generation;

// Step 1: Create a Planet barcode generator with the data to encode
BarcodeGenerator planetGenerator = new BarcodeGenerator(EncodeTypes.Planet, "123456");
```

*Pourquoi cette étape ?*  
`BarcodeGenerator` est le point d’entrée pour chaque code‑barres que vous générez. Sélectionner `EncodeTypes.Planet` indique à la bibliothèque de suivre la spécification ISO/IEC 24723 utilisée par de nombreux services postaux.

## Étape 2 : Définir la dimension X (largeur du module) pour le code‑barres Planet

La dimension X définit la largeur d’un seul module de code‑barres (la plus petite barre ou espace). Une valeur de **4 pixels** fonctionne bien pour la plupart des imprimantes d’étiquettes.

```csharp
// Step 2: Define the X‑dimension (module width) in pixels
planetGenerator.Parameters.Barcode.XDimension.Pixels = 4;
```

*Pourquoi c’est important*  
Si le module est trop étroit, le code‑barres peut devenir illisible ; s’il est trop large, la taille de l’étiquette augmente inutilement. Ajuster `Pixels` vous permet d’affiner le code‑barres en fonction de la résolution de votre imprimante.

## Étape 3 : Enregistrer le code‑barres Planet en image PNG

Aspose.BarCode calcule automatiquement la hauteur du code‑barres en fonction de la symbologie sélectionnée, vous n’avez donc qu’à spécifier le chemin du fichier et le format.

```csharp
// Step 3: Save the Planet barcode as a PNG image (height is calculated automatically)
planetGenerator.Save("YOUR_DIRECTORY/PostalPlanetBarHeightNone.png", BarCodeImageFormat.Png);
```

*Astuce*  
Remplacez `YOUR_DIRECTORY` par un chemin absolu ou relatif existant sur votre machine. Si le répertoire n’existe pas, la méthode `Save` lève une `DirectoryNotFoundException`.

**Résultat attendu** – un fichier PNG similaire à l’illustration ci‑dessous (l’image réelle n’est pas affichée ici, mais vous verrez un code‑barres Planet classique avec une charge numérique `123456`).

## Étape 4 : Initialiser un second générateur pour le code‑barres RM4SCC

De nombreux systèmes postaux exigent à la fois les symboles Planet et RM4SCC sur le même envoi. Créez une nouvelle instance de `BarcodeGenerator` pour la symbologie RM4SCC.

```csharp
// Step 4: Create an RM4SCC barcode generator with the same data
BarcodeGenerator rm4sccGenerator = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");
```

*Pourquoi une instance séparée ?*  
Chaque symbologie possède son propre jeu de paramètres. Réutiliser le même générateur pourrait transférer involontairement des réglages (comme la dimension X) qui ne sont pas optimaux pour le second code‑barres.

## Étape 5 : Configurer la dimension X pour le code‑barres RM4SCC

RM4SCC respecte également le réglage de la dimension X, nous appliquons donc la même largeur en pixels pour garantir une cohérence visuelle.

```csharp
// Step 5: Set the X‑dimension for the RM4SCC barcode
rm4sccGenerator.Parameters.Barcode.XDimension.Pixels = 4;
```

*Pro tip*  
Si vous avez besoin d’un code‑barres plus haut (par ex., pour des étiquettes plus grandes), vous pouvez également définir `Height.Pixels`. Le laisser non défini permet à la bibliothèque de calculer automatiquement la hauteur idéale.

## Étape 6 : Enregistrer le code‑barres RM4SCC en image PNG

Enfin, persistez le code‑barres RM4SCC sur le disque.

```csharp
// Step 6: Save the RM4SCC barcode as a PNG image (height is calculated automatically)
rm4sccGenerator.Save("YOUR_DIRECTORY/PostalRM4SCCBarHeightNone.png", BarCodeImageFormat.Png);
```

Vous disposez maintenant de deux fichiers PNG — `PostalPlanetBarHeightNone.png` et `PostalRM4SCCBarHeightNone.png` — que vous pouvez intégrer dans des étiquettes postales, imprimer sur des enveloppes, ou envoyer à un service d’impression tiers.

## Optionnel : Ajuster la hauteur ou utiliser d’autres formats d’image

Si votre flux de travail nécessite une hauteur de code‑barres spécifique ou un format d’image différent (par ex., JPEG ou BMP), vous pouvez modifier les paramètres avant d’appeler `Save` :

```csharp
// Example: set a fixed height of 100 pixels and save as JPEG
planetGenerator.Parameters.Barcode.Height.Pixels = 100;
planetGenerator.Save("PostalPlanet.jpg", BarCodeImageFormat.Jpeg);
```

**Cas limite** – Lorsque vous définissez une hauteur personnalisée, assurez‑vous que la valeur respecte la hauteur minimale requise par la norme ISO ; sinon le code‑barres risque d’échouer à la validation.

## Pièges courants et comment les éviter

| Piège | Pourquoi cela se produit | Solution |
|-------|--------------------------|----------|
| `DirectoryNotFoundException` | Le dossier cible n’existe pas ou est mal orthographié. | Créez le dossier au préalable ou utilisez `Path.Combine` avec `Environment.CurrentDirectory`. |
| Code‑barres illisible sur imprimantes basse résolution | Dimension X trop petite pour le DPI de l’imprimante. | Augmentez `XDimension.Pixels` à 5 – 6 pour les imprimantes 203 dpi, ou testez avec une étiquette d’échantillon. |
| Mauvaise symbologie utilisée | Passage de `EncodeTypes.Code128` au lieu de `EncodeTypes.Planet`. | Vérifiez que la valeur de l’énumération `EncodeTypes` correspond à la norme postale requise. |
| Référence nulle sur `Parameters` | Utilisation d’une version plus ancienne d’Aspose.BarCode où l’API diffère. | Mettez à jour vers le dernier package NuGet (v23.12 ou ultérieur). |

## Exemple complet exécutable

Voici le programme complet que vous pouvez copier, coller et exécuter. Il inclut les instructions `using`, la gestion des erreurs, et des commentaires expliquant chaque ligne.

```csharp
using System;
using System.IO;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Define the output directory (change as needed)
        string outputDir = Path.Combine(Environment.CurrentDirectory, "Barcodes");
        Directory.CreateDirectory(outputDir);

        // -------- Planet barcode ----------
        var planetGenerator = new BarcodeGenerator(EncodeTypes.Planet, "123456");
        planetGenerator.Parameters.Barcode.XDimension.Pixels = 4;
        string planetPath = Path.Combine(outputDir, "PostalPlanetBarHeightNone.png");
        planetGenerator.Save(planetPath, BarCodeImageFormat.Png);
        Console.WriteLine($"Planet barcode saved to: {planetPath}");

        // -------- RM4SCC barcode ----------
        var rm4sccGenerator = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");
        rm4sccGenerator.Parameters.Barcode.XDimension.Pixels = 4;
        string rm4sccPath = Path.Combine(outputDir, "PostalRM4SCCBarHeightNone.png");
        rm4sccGenerator.Save(rm4sccPath, BarCodeImageFormat.Png);
        Console.WriteLine($"RM4SCC barcode saved to: {rm4sccPath}");
    }
}
```

L’exécution du programme crée un dossier `Barcodes` à côté de l’exécutable et y place les deux fichiers PNG. Ouvrez‑les avec n’importe quel visualiseur d’image pour vérifier le résultat.

## Conclusion

Vous disposez maintenant d’une solution **générateur de code‑barres C#** capable de **créer des images de code‑barres Planet**, d’ajuster la dimension X pour une impression optimale, et de produire un code‑barres RM4SCC correspondant — le tout en quelques lignes de code. Cette approche fonctionne avec .NET 6+, ne nécessite que le package NuGet Aspose.BarCode, et peut être étendue à d’autres symbologies telles que Code128, QR ou DataMatrix en changeant la valeur `EncodeTypes`.

### Et après ?

* Expérimentez avec différentes valeurs `XDimension.Pixels` pour correspondre au DPI de votre imprimante.  
* Générez des code‑barres dans d’autres formats (PDF, SVG) en modifiant l’énumération `BarCodeImageFormat`.  
* Combinez les deux fichiers PNG en une seule étiquette à l’aide d’une bibliothèque graphique comme **SkiaSharp**.  
* Explorez l’API complète d’Aspose.BarCode pour des fonctionnalités avancées comme la validation de checksum ou les polices personnalisées.

N’hésitez pas à adapter le code pour du traitement par lots ou à l’intégrer dans un service web ASP.NET Core qui renvoie des images de code‑barres à la demande. Bon codage !

## Que devez‑vous apprendre ensuite ?

Les tutoriels suivants couvrent des sujets étroitement liés qui s’appuient sur les techniques démontrées dans ce guide. Chaque ressource comprend des exemples de code fonctionnels complets avec des explications pas à pas pour vous aider à maîtriser d’autres fonctionnalités de l’API et explorer des approches d’implémentation alternatives dans vos propres projets.

- [Create Barcode PNG – DataMatrix Aspect Ratio – Aspose.BarCode](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-aspect-ratio-customization/)
- [How to Save PNG using DataMatrix C40 with Aspose.BarCode](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-c40/)
- [barcode generator tutorial c# – Customize Code 16K Barcode Aspect Ratios with Aspose.BarCode for .NET](/barcode/english/net/code-16k-encoding/code-16k-aspect-ratio-customization/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}