---
category: general
date: 2026-10-21
description: Apprenez à générer des images de codes‑barres en C# et à exporter les
  fichiers de codes‑barres au format PNG en utilisant Aspose.BarCode pour des résultats
  rapides et fiables.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to generate barcode
- how to export barcode
language: fr
lastmod: 2026-10-21
og_description: Comment générer des images de codes-barres en C# et comment exporter
  les fichiers de codes-barres au format PNG. Suivez ce tutoriel complet pour créer
  des codes-barres Planet et RM4SCC avec Aspose.BarCode.
og_image_alt: Screenshot showing how to generate barcode images with C# code
og_title: Comment générer des images de code-barres et les exporter en C# – guide
  étape par étape
schemas:
- author: Aspose
  dateModified: '2026-10-21'
  description: Learn how to generate barcode images in C# and how to export barcode
    files as PNG using Aspose.BarCode for fast, reliable results.
  headline: How to generate barcode images and export them in C#
  type: TechArticle
tags:
- barcode generation
- C#
- Aspose.BarCode
title: Comment générer des images de code-barres et les exporter en C#
url: /fr/python-java/general/how-to-generate-barcode-images-and-export-them-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Comment générer des images de code-barres et les exporter en C#

Si vous avez besoin de **comment générer des codes-barres** dans une application .NET, ce guide vous montre les étapes exactes pour créer des codes-barres Planet et RM4SCC puis **comment exporter les codes-barres** sous forme de fichiers PNG. Vous obtiendrez un exemple de code prêt à l'exécution, une description de chaque paramètre et des conseils pour éviter les pièges courants.

Le tutoriel couvre :

* Ajout du package NuGet Aspose.BarCode
* Configuration de la largeur du module et de la hauteur de barre optionnelle
* Enregistrement des codes-barres générés sur le disque
* Vérification des fichiers de sortie

> **Prérequis** – SDK .NET 6+ , Visual Studio 2022 (ou tout autre IDE), et une connexion Internet pour télécharger le package Aspose.BarCode.

## Ce que vous accomplirez

À la fin de cet article, vous serez capable de :

* Générer un code-barres **Planet** avec hauteur de barre automatique.
* Générer un code-barres **RM4SCC** avec hauteur de barre automatique.
* Remplacer la hauteur par défaut et produire un code-barres de 100 pixels de haut.
* Exporter chaque code-barres vers un fichier PNG dans le dossier de votre choix.

## Étape 1 : Installer Aspose.BarCode

Ouvrez un terminal dans le dossier de votre projet et exécutez :

```bash
dotnet add package Aspose.BarCode
```

Le package fournit la classe `BarcodeGenerator` et l'énumération `EncodeTypes` utilisées dans le code qui suit.

## Étape 2 : Configurer le dossier de sortie

Créez un dossier où les fichiers PNG seront stockés. Le dossier peut être absolu ou relatif à la racine du projet.

```csharp
// Define the folder where barcode images will be saved
string outputFolder = Path.Combine(Environment.CurrentDirectory, "Barcodes");

// Ensure the directory exists
Directory.CreateDirectory(outputFolder);
```

> **Astuce :** Utiliser `Path.Combine` évite les séparateurs de chemin codés en dur et fonctionne sous Windows, macOS et Linux.

## Étape 3 : Générer des codes-barres avec hauteur de barre automatique

Lorsque vous ne spécifiez pas de hauteur de barre, Aspose.BarCode choisit une taille qui s'adapte aux données encodées. Le code suivant crée deux codes-barres — Planet et RM4SCC — en utilisant une largeur de module de 4 pixels.

```csharp
using Aspose.BarCode.Generation;

// Planet barcode, automatic height
var planetAuto = new BarcodeGenerator(EncodeTypes.Planet, "123456");
planetAuto.Parameters.Barcode.XDimension.Pixels = 4; // Set module width
planetAuto.Save(Path.Combine(outputFolder, "PlanetAutoHeight.png"),
                BarCodeImageFormat.Png);

// RM4SCC barcode, automatic height
var rm4sccAuto = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");
rm4sccAuto.Parameters.Barcode.XDimension.Pixels = 4; // Set module width
rm4sccAuto.Save(Path.Combine(outputFolder, "RM4SCCAutoHeight.png"),
                BarCodeImageFormat.Png);
```

**Pourquoi cela fonctionne :**  
* `EncodeTypes.Planet` et `EncodeTypes.RM4SCC` indiquent au générateur la symbologie à utiliser.  
* `XDimension.Pixels` définit la largeur d'un seul module du code-barres ; une valeur de 4 px donne une image claire et lisible.  
* Comme `BarHeight` n’est pas défini, la bibliothèque calcule automatiquement la hauteur optimale.

## Étape 4 : Générer des codes-barres avec une hauteur fixe de 100 pixels

Si votre conception nécessite une hauteur de barre précise, vous pouvez remplacer le calcul automatique :

```csharp
// Planet barcode, fixed 100‑pixel height
var planetFixed = new BarcodeGenerator(EncodeTypes.Planet, "123456");
planetFixed.Parameters.Barcode.XDimension.Pixels = 4;      // Module width
planetFixed.Parameters.Barcode.BarHeight.Pixels = 100;   // Fixed height
planetFixed.Save(Path.Combine(outputFolder, "PlanetHeight100.png"),
                 BarCodeImageFormat.Png);

// RM4SCC barcode, fixed 100‑pixel height
var rm4sccFixed = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");
rm4sccFixed.Parameters.Barcode.XDimension.Pixels = 4;      // Module width
rm4sccFixed.Parameters.Barcode.BarHeight.Pixels = 100;   // Fixed height
rm4sccFixed.Save(Path.Combine(outputFolder, "RM4SCCHeight100.png"),
                 BarCodeImageFormat.Png);
```

**Pourquoi vous pourriez avoir besoin d'une hauteur fixe :**  
Les spécifications de conception pour les étiquettes d'expédition imposent souvent des dimensions de barre exactes afin d'assurer la compatibilité avec les lecteurs de codes-barres. Définir `BarHeight.Pixels` garantit une uniformité sur toutes les images générées.

## Étape 5 : Vérifier les fichiers exportés

Après l'exécution du programme, le dossier `Barcodes` contient quatre fichiers PNG :

* `PlanetAutoHeight.png`
* `RM4SCCAutoHeight.png`
* `PlanetHeight100.png`
* `RM4SCCHeight100.png`

Ouvrez‑les avec un visualiseur d'images ou intégrez‑les dans un PDF pour confirmer qu'ils s'affichent correctement. Si un scanner ne parvient pas à lire un code‑barres, augmentez la valeur de `XDimension.Pixels` ou revérifiez la longueur de la chaîne d'entrée.

```bash
# Example verification command (Linux/macOS)
file Barcodes/*.png
```

Vous devriez voir une sortie similaire à :

```
Barcodes/PlanetAutoHeight.png: PNG image data, 180 x 100, 8-bit/color RGBA, non-interlaced
```

## Questions fréquentes et cas particuliers

| Question | Réponse |
|----------|--------|
| **Puis-je exporter vers d'autres formats que PNG ?** | Oui. Remplacez `BarCodeImageFormat.Png` par `Jpeg`, `Bmp`, `Gif` ou `Tiff`. |
| **Que se passe-t-il si mes données contiennent des caractères non autorisés par la symbologie ?** | Le générateur lève une `ArgumentException`. Validez l'entrée ou passez à une symbologie qui prend en charge le jeu de caractères. |
| **Comment modifier les couleurs de premier plan/arrière‑plan ?** | Définissez `Parameters.Barcode.ForeColor` et `Parameters.Barcode.BackColor` avant d'appeler `Save`. |
| **Existe‑t‑il un moyen de générer les codes‑barres en mémoire plutôt que de les enregistrer sur le disque ?** | Appelez `GenerateBarCodeImage()` pour obtenir un objet `System.Drawing.Image`, puis manipulez‑le ou diffusez‑le selon vos besoins. |

## Astuce pro : traitement par lots

Lorsque vous devez créer de nombreux codes‑barres (par ex., pour une liste de diffusion), encapsulez la logique de génération dans une boucle `foreach` :

```csharp
var values = new[] { "001122", "334455", "667788" };
int index = 0;

foreach (var value in values)
{
    var generator = new BarcodeGenerator(EncodeTypes.Planet, value);
    generator.Parameters.Barcode.XDimension.Pixels = 4;
    generator.Save(Path.Combine(outputFolder, $"Planet_{index++}.png"),
                   BarCodeImageFormat.Png);
}
```

Ce modèle s’adapte à des milliers de codes‑barres tout en restant concis.

## Conclusion

Vous savez maintenant **comment générer des images de code‑barres** en C# et **comment exporter les fichiers de code‑barres** au format PNG en utilisant Aspose.BarCode. L’exemple complet montre à la fois la génération automatique et à hauteur fixe pour les symbologies Planet et RM4SCC, vous offrant une base solide pour tout projet lié aux codes‑barres.

**Étapes suivantes**

* Explorez d’autres symbologies telles que Code128, QR ou DataMatrix.  
* Expérimentez la personnalisation des couleurs (`ForeColor`, `BackColor`).  
* Intégrez les PNG générés dans des factures PDF ou des étiquettes d’expédition à l’aide d’une bibliothèque PDF.  

Bon codage, et que vos codes‑barres soient lus sans problème !

## Que devriez‑vous apprendre ensuite ?

Les tutoriels suivants couvrent des sujets étroitement liés qui s’appuient sur les techniques démontrées dans ce guide. Chaque ressource inclut des exemples de code complets avec des explications pas à pas pour vous aider à maîtriser d’autres fonctionnalités de l’API et à explorer des approches d’implémentation alternatives dans vos propres projets.

- [Comment générer des codes‑barres DataMatrix avec Aspose.BarCode pour .NET – Guide étape par étape](/barcode/english/net/datamatrix-barcode-configuration/)
- [Créer des images de code‑barres GS1 en C# – Comment générer rapidement des codes‑barres C#](/barcode/english/net/gs1-barcode-encoding/create-gs1-barcode-images-in-c-how-to-generate-barcode-c-qui/)
- [Comment générer une image de code‑barres avec Aspose.BarCode en C#](/barcode/english/python-java/general/how-to-generate-barcode-image-with-aspose-barcode-in-c/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}