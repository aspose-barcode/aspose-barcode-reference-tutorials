---
category: general
date: 2026-08-12
description: Exemple de générateur de code-barres montrant comment créer un code-barres
  avec une taille de pixel précise. Apprenez à définir la largeur du module, la hauteur
  des barres et à créer des codes-barres Planet.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- barcode generator example
- how to generate barcode
- barcode pixel size
- generate planet barcode
- barcode height setting
language: fr
lastmod: 2026-08-12
og_description: L'exemple de générateur de code-barres montre comment créer un code-barres
  avec des dimensions de pixel exactes. Suivez ce guide pour contrôler la largeur
  du module et la hauteur des barres pour les codes Planet et RM4SCC.
og_image_alt: Screenshot of a barcode generator example showing a Planet barcode with
  custom pixel size
og_title: exemple de générateur de code-barres – personnaliser la taille des pixels
  en C#
schemas:
- author: Aspose
  dateModified: '2026-08-12'
  description: barcode generator example that shows how to generate barcode with precise
    pixel size. Learn to set module width, bar height and create Planet barcodes.
  headline: barcode generator example – step‑by‑step guide for custom pixel sizes
  type: TechArticle
- description: barcode generator example that shows how to generate barcode with precise
    pixel size. Learn to set module width, bar height and create Planet barcodes.
  name: barcode generator example – step‑by‑step guide for custom pixel sizes
  steps:
  - name: Install the Aspose.BarCode package
    text: 'Open a terminal in your project folder and run:'
  - name: Add the necessary `using` directives
    text: '```csharp using Aspose.BarCode.Generation; using Aspose.BarCode.BarCodeImageFormat;
      ```'
  - name: – generate a Planet barcode with automatically calculated height
    text: '```csharp // Step 1: Generate a Planet barcode with automatically calculated
      height BarcodeGenerator planetAuto = new BarcodeGenerator(EncodeTypes.Planet,
      "123456");'
  - name: – generate a Planet barcode with an explicit 100‑pixel height
    text: '```csharp // Step 2: Generate a Planet barcode with an explicit 100‑pixel
      height BarcodeGenerator planetFixed = new BarcodeGenerator(EncodeTypes.Planet,
      "123456");'
  - name: – generate an RM4SCC barcode with the same explicit height
    text: '```csharp // Step 3: Generate an RM4SCC barcode with the same explicit
      height BarcodeGenerator rm4sccFixed = new BarcodeGenerator(EncodeTypes.RM4SCC,
      "123456");'
  - name: What is **barcode pixel size**?
    text: '*Pixel size* refers to the physical number of screen or printer pixels
      that represent a single module (`XDimension`). A larger pixel size yields a
      bigger barcode, which can be easier for low‑resolution scanners but consumes
      more label real‑estate.'
  - name: How does `BarHeight` affect readability?
    text: The `BarHeight` property controls the vertical length of the bars. Standards
      for most 1‑D barcodes (including Planet and RM4SCC) recommend a minimum height
      of 10 mm when printed at 300 dpi, which translates to roughly 118 pixels. Setting
      a height below that can cause read errors, especially on mobil
  - name: When should you let the library calculate height automatically?
    text: If you’re generating barcodes for on‑screen display only, the automatic
      calculation keeps the aspect ratio consistent and reduces the amount of manual
      tweaking needed. For printed labels that must meet strict ISO specifications,
      you should **explicitly set the bar height**.
  - name: Pro tip on performance
    text: When generating thousands of barcodes in a batch job, reuse a single `BarcodeGenerator`
      instance and only change the `CodeText` and size parameters between saves. This
      avoids repeated allocation of internal rendering objects and can cut execution
      time by up to 30 %.
  type: HowTo
tags:
- barcode
- C#
- Aspose.BarCode
title: exemple de générateur de code‑barres – guide étape par étape pour des tailles
  de pixel personnalisées
url: /fr/python-java/general/barcode-generator-example-step-by-step-guide-for-custom-pixe/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# exemple de générateur de code-barres – guide étape par étape pour des tailles de pixel personnalisées

Si vous avez besoin d'un **exemple de générateur de code-barres** qui vous permet de contrôler chaque pixel, ce guide montre exactement comment le faire. Vous apprendrez à définir la largeur du module, à spécifier une hauteur de barre fixe, et à générer des codes-barres Planet et RM4SCC avec des dimensions prévisibles.

La plupart des développeurs ont du mal à créer des images « comment générer un code-barres » qui ont le même aspect sur chaque écran ou imprimante. Les extraits de code ci‑dessous résolvent ce problème en exposant les paramètres au niveau du pixel de la bibliothèque Aspose.BarCode pour .NET, afin que vous puissiez produire une sortie cohérente sans conjecture.

## Ce que vous apprendrez

* Comment installer le package NuGet requis.
* Comment générer un code-barres Planet avec une hauteur calculée automatiquement.
* Comment générer un code-barres Planet avec une hauteur explicite de 100 pixels.
* Comment générer un code-barres RM4SCC en utilisant la même hauteur explicite.
* Pourquoi la **taille de pixel du code-barres** est importante pour la fiabilité du scan.
* Conseils pour dépanner les problèmes courants lors de la génération d'images de code-barres Planet.

Vous avez seulement besoin de .NET 6 ou supérieur, d'un environnement de développement C# basique, et d'une connexion Internet pour récupérer le package NuGet.

---

## exemple de générateur de code-barres – configurer l'environnement de développement

Avant d'écrire du code, assurez-vous que la bibliothèque Aspose.BarCode est disponible pour votre projet.

### Installer le package Aspose.BarCode

Ouvrez un terminal dans le dossier de votre projet et exécutez :

```bash
dotnet add package Aspose.BarCode
```

La commande ajoute la dernière version stable de **Aspose.BarCode** à votre `csproj`. Après la fin de la restauration, vous pouvez commencer à utiliser la classe `BarcodeGenerator`.

> **Astuce :** Ciblez .NET 6 ou .NET 7 pour profiter des dernières améliorations de performances et de la gestion UTF‑8 par défaut.

### Ajouter les directives `using` nécessaires

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode.BarCodeImageFormat;
```

Ces espaces de noms exposent la classe `BarcodeGenerator` et l'énumération `BarCodeImageFormat` utilisées plus tard dans le tutoriel.

---

## Comment générer un code-barres avec une taille de pixel personnalisée

Les trois étapes suivantes illustrent l'**exemple complet de générateur de code-barres**. Chaque étape s'appuie sur la précédente, de sorte que vous pouvez copier‑coller le bloc entier dans une application console et l'exécuter tel quel.

### Étape 1 – générer un code-barres Planet avec une hauteur calculée automatiquement

```csharp
// Step 1: Generate a Planet barcode with automatically calculated height
BarcodeGenerator planetAuto = new BarcodeGenerator(EncodeTypes.Planet, "123456");

// Set module width (x‑dimension) to 4 pixels
planetAuto.Parameters.Barcode.XDimension.Pixels = 4;

// Save the image as PNG
planetAuto.Save("PlanetAuto.png", BarCodeImageFormat.Png);
```

**Pourquoi cela fonctionne :**  
*La propriété `XDimension` définit la largeur d'un seul module de code-barres (l'élément noir ou blanc le plus petit). Lorsque vous omettez `BarHeight`, la bibliothèque calcule une hauteur qui maintient le rapport d'aspect standard pour les codes Planet.*

**Sortie attendue :** Un fichier PNG nommé `PlanetAuto.png` contenant un code-barres Planet propre. Sa hauteur s'adapte à la largeur de module de 4 pixels, généralement autour de 60 pixels pour une charge utile de six caractères.

### Étape 2 – générer un code-barres Planet avec une hauteur explicite de 100 pixels

```csharp
// Step 2: Generate a Planet barcode with an explicit 100‑pixel height
BarcodeGenerator planetFixed = new BarcodeGenerator(EncodeTypes.Planet, "123456");

// Keep the same module width
planetFixed.Parameters.Barcode.XDimension.Pixels = 4;

// Force the bar height to 100 pixels
planetFixed.Parameters.Barcode.BarHeight.Pixels = 100;

// Save the image
planetFixed.Save("PlanetHeight100.png", BarCodeImageFormat.Png);
```

**Pourquoi vous pourriez en avoir besoin :**  
Parfois, l'équipement de numérisation attend une hauteur de barre minimale pour une détection fiable. En définissant `BarHeight.Pixels`, vous garantissez que chaque image générée satisfait cette exigence, quel que soit la longueur des données encodées.

**Sortie attendue :** `PlanetHeight100.png` montre les mêmes données qu'auparavant, mais les barres font exactement 100 pixels de haut, vous donnant un contrôle total sur la taille visuelle.

### Étape 3 – générer un code-barres RM4SCC avec la même hauteur explicite

```csharp
// Step 3: Generate an RM4SCC barcode with the same explicit height
BarcodeGenerator rm4sccFixed = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");

// Use the same module width for consistency
rm4sccFixed.Parameters.Barcode.XDimension.Pixels = 4;

// Apply the 100‑pixel bar height
rm4sccFixed.Parameters.Barcode.BarHeight.Pixels = 100;

// Save the image
rm4sccFixed.Save("RM4SCCHeight100.png", BarCodeImageFormat.Png);
```

**Pourquoi c'est important :**  
`EncodeTypes.RM4SCC` est un code-barres linéaire empilé utilisé en logistique. Aligner sa hauteur de barre avec le code-barres Planet simplifie le traitement par lots lorsque les deux symbologies apparaissent sur la même étiquette.

**Sortie attendue :** `RM4SCCHeight100.png` affiche un code-barres RM4SCC parfaitement dimensionné, correspondant à la hauteur de 100 pixels que vous avez définie pour le code Planet.

> **Vérification du résultat :** Ouvrez chaque PNG dans un visualiseur d'images et confirmez que les barres noires font exactement 4 pixels de large et, là où vous l'avez spécifié, 100 pixels de haut. Vous pouvez également envoyer les fichiers à une application de lecture de code-barres pour vous assurer qu'ils décodent « 123456 ».

---

## Comprendre la taille de pixel du code-barres et la hauteur des barres

### Qu'est-ce que la **taille de pixel du code-barres** ?

*La taille de pixel* désigne le nombre physique de pixels d'écran ou d'imprimante qui représentent un seul module (`XDimension`). Une taille de pixel plus grande produit un code-barres plus grand, ce qui peut être plus facile pour les scanners à basse résolution mais consomme plus d'espace sur l'étiquette.

### Comment `BarHeight` affecte-t-il la lisibilité ?

La propriété `BarHeight` contrôle la longueur verticale des barres. Les normes pour la plupart des codes-barres 1‑D (y compris Planet et RM4SCC) recommandent une hauteur minimale de 10 mm lorsqu'ils sont imprimés à 300 dpi, ce qui correspond à environ 118 pixels. Définir une hauteur inférieure peut entraîner des erreurs de lecture, notamment avec les caméras mobiles.

### Quand faut‑il laisser la bibliothèque calculer automatiquement la hauteur ?

Si vous générez des codes-barres uniquement pour un affichage à l'écran, le calcul automatique maintient le rapport d'aspect constant et réduit le nombre d'ajustements manuels nécessaires. Pour les étiquettes imprimées qui doivent respecter des spécifications ISO strictes, vous devez **définir explicitement la hauteur des barres**.

---

## Pièges courants et bonnes pratiques lors de la génération d'un code-barres Planet

| Problème | Pourquoi cela se produit | Solution |
|----------|--------------------------|----------|
| Les barres apparaissent trop fines ou trop épaisses | `XDimension` laissé à la valeur par défaut (1 pixel) sur les écrans haute résolution | Définissez `XDimension.Pixels` à au moins 3‑4 pour une clarté visuelle |
| Le scanner ne peut pas lire le code | `BarHeight` est trop petite pour la focale du scanner | Utilisez `BarHeight.Pixels` ≥ 100 pour la plupart des scanners mobiles |
| L'image est floue après mise à l'échelle | Enregistrer en JPEG introduit des artefacts de compression | Enregistrez en PNG (`BarCodeImageFormat.Png`) pour une sortie sans perte |
| Type de code-barres inattendu | Valeur d'énumération `EncodeTypes` incorrecte | Vérifiez que vous utilisez `EncodeTypes.Planet` pour la symbologie Planet |

### Astuce de performance

Lors de la génération de milliers de codes-barres dans un travail par lots, réutilisez une seule instance de `BarcodeGenerator` et ne modifiez que le `CodeText` et les paramètres de taille entre les sauvegardes. Cela évite l'allocation répétée d'objets de rendu internes et peut réduire le temps d'exécution jusqu'à 30 %.

---

## Exemple complet fonctionnel – assembler le tout

Créez un nouveau projet console (`dotnet new console -n BarcodeDemo`) et remplacez le contenu de `Program.cs` par ce qui suit :

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode.BarCodeImageFormat;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // Directory where PNG files will be saved
            string outputDir = Environment.CurrentDirectory;

            // ---------- Planet barcode – automatic height ----------
            var planetAuto = new BarcodeGenerator(EncodeTypes.Planet, "123456");
            planetAuto.Parameters.Barcode.XDimension.Pixels = 4;
            planetAuto.Save($"{outputDir}/PlanetAuto.png", BarCodeImageFormat.Png);
            Console.WriteLine("PlanetAuto.png generated.");

            // ---------- Planet barcode – fixed 100‑pixel height ----------
            var planetFixed = new BarcodeGenerator(EncodeTypes.Planet, "123456");
            planetFixed.Parameters.Barcode.XDimension.Pixels = 4;
            planetFixed.Parameters.Barcode.BarHeight.Pixels = 100;
            planetFixed.Save($"{outputDir}/PlanetHeight100.png", BarCodeImageFormat.Png);
            Console.WriteLine("PlanetHeight100.png generated.");

            // ---------- RM4SCC barcode – same fixed height ----------
            var rm4sccFixed = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");
            rm4sccFixed.Parameters.Barcode.XDimension.Pixels = 4;
            rm4sccFixed.Parameters.Barcode.BarHeight.Pixels = 100;
            rm4sccFixed.Save($"{outputDir}/RM4SCCHeight100.png", BarCodeImageFormat.Png);
            Console.WriteLine("RM4SCCHeight100.png generated.");

            Console.WriteLine("All barcodes created successfully.");
        }
    }
}
```

Exécutez le programme avec `dotnet run`. Après l'exécution, vous trouverez trois fichiers PNG dans le dossier du projet, chacun illustrant un scénario différent d'**exemple de générateur de code-barres**.

---

## Prochaines étapes et sujets associés

* **Comment générer un code-barres dans d'autres formats** – explorez `EncodeTypes.Code128`, `EncodeTypes.QR` et `EncodeTypes.DataMatrix` pour les besoins 2‑D.
* **Intégrer des codes-barres dans des PDF** – combinez Aspose.BarCode avec Aspose.PDF pour placer les codes-barres directement sur les modèles de factures.
* **Taille dynamique du code-barres basée sur l'entrée utilisateur** – calculer

## Que devriez‑vous apprendre ensuite ?

Les tutoriels suivants couvrent des sujets étroitement liés qui s'appuient sur les techniques démontrées dans ce guide. Chaque ressource comprend des exemples de code complets avec des explications étape par étape pour vous aider à maîtriser des fonctionnalités d'API supplémentaires et explorer des approches d'implémentation alternatives dans vos propres projets.

- [Comment générer un code-barres java : créer une image de code-barres exacte](/barcode/english/java/barcode-basics/creating-image-exact-barcode/)
- [Comment générer un code-barres en Java créer et définir la taille pour l'image complète](/barcode/english/java/barcode-basics/creating-setting-size-whole-picture-barcode/)
- [Comment créer un code-barres code128 en Java et définir la hauteur des barres](/barcode/english/java/barcode-configuration/setting-bars-height/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}