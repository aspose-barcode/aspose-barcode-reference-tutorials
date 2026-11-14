---
category: general
date: 2026-11-14
description: Apprenez à créer une image de code‑barres en C# avec Aspose.BarCode.
  Ce guide étape par étape couvre la configuration du générateur de code‑barres en
  C#, le formatage GS1 et l’exportation PNG.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode image
- how to generate barcode
- barcode generator c#
- create gs1 barcode
- barcode image from data
language: fr
lastmod: 2026-11-14
og_description: Créez rapidement une image de code-barres en C#. Suivez ce guide pour
  apprendre à générer un code-barres, utiliser le générateur de code-barres C# et
  exporter un PNG GS1 MicroPDF417.
og_image_alt: Screenshot of a GS1 MicroPDF417 barcode generated in C#
og_title: Créer une image de code-barres en C# – guide complet pour GS1 MicroPDF417
schemas:
- author: Aspose
  dateModified: '2026-11-14'
  description: Learn how to create barcode image in C# using Aspose.BarCode. This
    step‑by‑step guide covers barcode generator c# setup, GS1 formatting and PNG export.
  headline: How to create barcode image in C# with GS1 MicroPDF417
  type: TechArticle
tags:
- barcode
- C#
- Aspose
title: Comment créer une image de code‑barres en C# avec GS1 MicroPDF417
url: /fr/net/gs1-barcode-encoding/how-to-create-barcode-image-in-c-with-gs1-micropdf417/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Comment créer une image de code-barres en C# avec GS1 MicroPDF417

Si vous devez **créer une image de code-barres** en C#, ce guide vous présente une solution complète, prête à l’emploi. Vous verrez **comment générer des données de code-barres** conformes à la norme GS1, configurer le générateur et exporter un fichier PNG de haute qualité.

Le tutoriel couvre tout, de l’installation de la bibliothèque requise à la gestion des pièges courants de format de données. À la fin, vous serez capable de produire une **image de code-barres à partir de données** en quelques lignes de code seulement, et vous comprendrez pourquoi chaque paramètre est important.

## Prérequis

* .NET 6.0 ou une version ultérieure installé (le code fonctionne également avec .NET Framework 4.7+).
* Un IDE tel que Visual Studio 2022 ou Visual Studio Code.
* Le package NuGet **Aspose.BarCode for .NET**. Installez-le avec :

```bash
dotnet add package Aspose.BarCode
```

* Connaissance de base de la syntaxe C# et du format GS1 Application Identifier (AI).

> **Astuce :** Gardez la version de la bibliothèque à jour ; la dernière version ajoute la prise en charge de nouvelles symbologies de codes-barres et des améliorations de performances.

## Créer une image de code-barres avec BarcodeGenerator

Cette section contient l’implémentation principale. Le code crée une instance de **barcode generator c#**, configure la X‑dimension pour la lisibilité et enregistre le résultat sous forme de fichier PNG.

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;

// Step 1: Initialise the generator with the GS1 MicroPDF417 symbology
// The data string follows the GS1 syntax: (01)GTIN(21)SerialNumber
BarcodeGenerator generator = new BarcodeGenerator(
    EncodeTypes.MicroPdf417,
    "(01)12345678901234(21)ABC123");

// Step 2: Adjust the module width (X‑dimension) to improve scan reliability
// A value of 2 pixels works well for most screen‑displayed barcodes.
generator.Parameters.Barcode.XDimension.Pixels = 2;

// Step 3: Export the barcode as a PNG image
string outputPath = Path.Combine(
    Environment.GetFolderPath(Environment.SpecialFolder.Desktop),
    "GS1MicroPdf417.png");
generator.Save(outputPath, BarCodeImageFormat.Png);
```

### Pourquoi chaque ligne est importante

* **EncodeTypes.MicroPdf417** indique à la bibliothèque d’utiliser la symbologie GS1 MicroPDF417, qui est compacte et idéale pour le scan mobile.
* La **data string** doit commencer par le AI GS1 `(01)` pour le Global Trade Item Number (GTIN) suivi de `(21)` pour le numéro de série. Si le format est incorrect, le générateur lève une exception.
* **XDimension.Pixels** contrôle la largeur de la barre la plus petite. Une valeur plus grande augmente la lisibilité sur les écrans à basse résolution, tandis qu’une valeur plus petite réduit la taille de l’image.
* **BarCodeImageFormat.Png** produit une image sans perte, préservant les bords nets requis pour un scan fiable.

L’exécution du programme crée `GS1MicroPdf417.png` sur votre bureau. L’ouverture du fichier montre un code-barres dense, noir sur blanc, qui encode le GTIN `12345678901234` et le numéro de série `ABC123`.

## Comment générer un code-barres avec GS1 MicroPDF417

Si vous êtes novice en formatage GS1, voici les règles essentielles :

| GS1 AI | Signification                     | Exemple               |
|--------|-----------------------------------|-----------------------|
| (01)   | Numéro d'article commercial mondial | 12345678901234        |
| (21)   | Numéro de série (optionnel)        | ABC123                |

Lorsque vous concaténez les AI avec leurs valeurs, encadrez chaque AI entre parenthèses et placez les valeurs directement après. La chaîne résultante peut être transmise au **barcode generator c#** sans encodage supplémentaire.

### Pièges courants

* **Parenthèses manquantes** – Le générateur traite la chaîne comme des données brutes et n’appliquera pas les vérifications GS1.
* **Dépassement des limites de longueur** – MicroPDF417 prend en charge jusqu’à 155 caractères. Supprimez les espaces inutiles.
* **Caractères invalides** – Seuls les caractères numériques sont autorisés pour le GTIN ; le numéro de série peut inclure des lettres majuscules et des chiffres.

## Personnaliser l'image du code-barres à partir des données

Au-delà de la X‑dimension de base, Aspose.BarCode propose de nombreux ajustements visuels. Vous trouverez ci‑dessous quelques réglages que vous pourriez appliquer selon les exigences de votre projet.

```csharp
// Set background to transparent (useful for overlaying on UI)
generator.Parameters.ImageBackgroundColor = Color.Transparent;

// Change foreground color to dark blue for branding
generator.Parameters.Barcode.BarColor = Color.FromArgb(0, 0, 139);

// Increase image resolution to 300 dpi for print‑ready output
generator.Parameters.ImageResolution = 300;
```

Chaque paramètre est optionnel ; les valeurs par défaut produisent déjà une **barcode image** propre et lisible. Expérimentez avec les couleurs et les résolutions uniquement après avoir confirmé que les scanners peuvent toujours lire le code.

## Enregistrer le code-barres dans d'autres formats

Bien que le PNG soit le format le plus courant pour le web et le mobile, vous pouvez avoir besoin de JPEG, BMP ou SVG. La méthode `Save` accepte n’importe quelle valeur `BarCodeImageFormat`.

```csharp
generator.Save("barcode.jpg", BarCodeImageFormat.Jpeg);
generator.Save("barcode.svg", BarCodeImageFormat.Svg);
```

* JPEG réduit la taille du fichier mais introduit des artefacts de compression pouvant affecter la lisibilité.
* SVG préserve la qualité vectorielle et est idéal pour les conceptions web réactives.

## Vérifier le code-barres généré

Une façon rapide de confirmer que l’étape **create barcode image** a réussi est d’utiliser une application de scanner mobile qui prend en charge GS1 MicroPDF417. Scannez le PNG enregistré ; l’application devrait afficher :

```
GTIN: 12345678901234
Serial: ABC123
```

Si le scanner signale une erreur, revérifiez le formatage des AI et la valeur de la X‑dimension.

## Exemple complet – un programme console autonome

Voici un programme complet que vous pouvez copier, coller et exécuter sans modification (à l’exception de l’étape d’installation du package NuGet).

```csharp
using System;
using System.IO;
using System.Drawing;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // Initialise the generator with GS1 MicroPDF417 and sample data
            BarcodeGenerator generator = new BarcodeGenerator(
                EncodeTypes.MicroPdf417,
                "(01)12345678901234(21)ABC123");

            // Improve readability by setting module width
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // Optional visual customisation
            generator.Parameters.ImageBackgroundColor = Color.Transparent;
            generator.Parameters.Barcode.BarColor = Color.FromArgb(0, 0, 139);
            generator.Parameters.ImageResolution = 300;

            // Define output path (Desktop folder)
            string outputPath = Path.Combine(
                Environment.GetFolderPath(Environment.SpecialFolder.Desktop),
                "GS1MicroPdf417.png");

            // Save the barcode as PNG
            generator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"Barcode image saved to: {outputPath}");
        }
    }
}
```

Lorsque vous exécutez le programme, la console affiche le chemin complet du fichier, et le PNG apparaît sur votre bureau. Cet exemple montre **how to generate barcode** data, customise appearance, et exporter une **barcode image from data** dans un flux de travail unique et cohérent.

## Questions fréquentes

| Question | Réponse |
|----------|--------|
| *Puis-je générer d'autres symbologies GS1 ?* | Oui. Remplacez `EncodeTypes.MicroPdf417` par `EncodeTypes.Pdf417`, `EncodeTypes.DataMatrix`, etc., et ajustez la chaîne de données en conséquence. |
| *Que faire si mes données dépassent la capacité du MicroPDF417 ?* | Passez à la symbologie PDF417 standard, qui prend en charge des charges utiles plus longues. |
| *Ai-je besoin d’une licence pour Aspose.BarCode ?* | Une licence d’évaluation gratuite suffit pour le développement. En production, achetez une licence pour supprimer le filigrane d’évaluation. |
| *Le PNG est-il adapté à l’impression d’étiquettes ?* | Augmentez `ImageResolution` à 300 dpi ou plus, et envisagez d’enregistrer en TIFF pour les imprimantes industrielles. |

## Conclusion

Vous savez maintenant comment **create barcode image** en C# en utilisant l’approche **barcode generator c#**, formater les données pour un scénario **create gs1 barcode**, et exporter le résultat en PNG ou autre type d’image. L’exemple complet montre chaque étape — de la préparation des données à la personnalisation visuelle — afin que vous puissiez intégrer la création de codes-barres dans n’importe quelle application .NET.

Ensuite, explorez des sujets connexes tels que **barcode image from data** pour les QR codes, l’ajout de plusieurs codes-barres à un même PDF, ou l’automatisation de la génération par lots pour les systèmes d’inventaire. Expérimentez avec différentes valeurs de X‑dimension et formats d’image pour trouver le compromis idéal pour votre environnement de scan spécifique.

Bon codage, et laissez vos applications commencer à **creating barcode images** qui fonctionnent de manière fiable dans le monde réel !

## Que devriez‑vous apprendre ensuite ?

Les tutoriels suivants couvrent des sujets étroitement liés qui s’appuient sur les techniques démontrées dans ce guide. Chaque ressource comprend des exemples de code complets et fonctionnels avec des explications étape par étape pour vous aider à maîtriser des fonctionnalités d’API supplémentaires et explorer des approches d’implémentation alternatives dans vos propres projets.

- [Comment créer une image de code-barres avec Aspose.Barcode en C#](/barcode/english/python-java/general/how-to-create-barcode-image-with-aspose-barcode-in-c/)
- [Comment créer une image de code-barres postal en C# avec Aspose.BarCode](/barcode/english/python-java/general/how-to-create-postal-barcode-image-in-c-using-aspose-barcode/)
- [Comment créer une image de code-barres PDF417 en C# – guide complet](/barcode/english/net/compact-pdf417-encoding/generate-pdf417-barcode-in-c-complete-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}