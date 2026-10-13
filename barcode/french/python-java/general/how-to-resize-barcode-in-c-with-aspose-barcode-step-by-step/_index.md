---
category: general
date: 2026-09-23
description: Comment redimensionner un code‑barres en C# avec Aspose.BarCode. Apprenez
  à générer du code C# pour les codes‑barres, à personnaliser la taille et à exporter
  efficacement l’image du code‑barres.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to resize barcode
- generate barcode c#
- barcode generator example
- create databar barcode
- export barcode image
language: fr
lastmod: 2026-09-23
og_description: Comment redimensionner un code‑barres en C# avec Aspose.BarCode. Suivez
  ce guide pour générer du code C# de code‑barres, ajuster les dimensions et exporter
  l’image du code‑barres.
og_image_alt: Screenshot showing resized DataBar Omni‑directional barcode generated
  in C#
og_title: Comment redimensionner un code‑barres en C# – tutoriel complet Aspose.BarCode
schemas:
- author: Aspose
  dateModified: '2026-09-23'
  description: How to resize barcode in C# using Aspose.BarCode. Learn to generate
    barcode C# code, customize size, and export barcode image efficiently.
  headline: How to resize barcode in C# with Aspose.BarCode – step‑by‑step guide
  type: TechArticle
- description: How to resize barcode in C# using Aspose.BarCode. Learn to generate
    barcode C# code, customize size, and export barcode image efficiently.
  name: How to resize barcode in C# with Aspose.BarCode – step‑by‑step guide
  steps:
  - name: '**Create Databar barcode** objects with custom data.'
    text: '**Create Databar barcode** objects with custom data.'
  - name: Adjust `BarHeight` (the core of resizing).
    text: Adjust `BarHeight` (the core of resizing).
  - name: Export PNG files for any required size.
    text: Export PNG files for any required size.
  type: HowTo
tags:
- barcode
- C#
- Aspose
- image processing
title: Comment redimensionner un code‑barres en C# avec Aspose.BarCode – guide étape
  par étape
url: /fr/python-java/general/how-to-resize-barcode-in-c-with-aspose-barcode-step-by-step/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Comment redimensionner un code‑barres en C# avec Aspose.BarCode – guide étape par étape

Si vous devez **redimensionner un code‑barres** dans une application .NET, ce tutoriel montre le code exact que vous pouvez copier‑coller et exécuter dès aujourd’hui. Vous apprendrez comment **générer du code barcode C#**, ajuster la hauteur des barres et **exporter des images de code‑barres** sans quitter votre IDE.

Créer des codes‑barres est courant dans les systèmes d’inventaire, les étiquettes d’expédition et les terminaux point de vente. À la fin de ce guide, vous serez capable de **créer des images de code‑barres Databar** à n’importe quelle hauteur requise, et vous comprendrez les propriétés clés qui contrôlent la taille, la résolution et le format de fichier.

## Prérequis

- .NET 6 ou version ultérieure (l’exemple fonctionne également avec .NET Framework 4.6+)  
- Package NuGet Aspose.BarCode pour .NET (`Install-Package Aspose.BarCode`)  
- Familiarité de base avec la syntaxe C# et Visual Studio (ou tout IDE C#)  

Aucune bibliothèque supplémentaire n’est nécessaire ; Aspose.BarCode gère le rendu, le redimensionnement et l’exportation d’images en interne.

## Étape 1 : Configurer le projet et importer Aspose.BarCode

Créez un nouveau projet console (ou intégrez‑le dans un projet existant) et ajoutez l’espace de noms Aspose.BarCode :

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;
using System.Drawing.Imaging;   // required for BarCodeImageFormat
```

**Astuce :** Utilisez la dernière version d’Aspose.BarCode (en date de septembre 2026) pour profiter des corrections de bugs et des nouvelles symbologies de codes‑barres.

## Étape 2 : Initialiser un générateur de code‑barres DataBar Omni‑directional

L’**exemple de générateur de code‑barres** commence par spécifier la symbologie (`EncodeTypes.DatabarOmniDirectional`) et la charge de données. La charge suit le format d’identifiant d’application GS1 `(01)12345678901231`.

```csharp
// Step 2: Create a DataBar Omni‑directional barcode generator with the desired data
BarcodeGenerator barcode = new BarcodeGenerator(
    EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");
```

Cet objet contient tous les paramètres que vous modifierez plus tard, tels que la X‑dimension, la hauteur des barres et le format d’image.

## Étape 3 : Définir les paramètres de taille communs

Avant d’exporter, définissez la X‑dimension (la largeur de la barre la plus fine) et une hauteur de barre initiale. La X‑dimension est exprimée en pixels ; une valeur de `2` convient à la plupart des résolutions d’écran.

```csharp
// Step 3: Set common barcode parameters – X‑dimension and initial bar height (30 px)
barcode.Parameters.Barcode.XDimension.Pixels = 2;   // thin bar width
barcode.Parameters.Barcode.BarHeight.Pixels = 30; // initial height
```

**Pourquoi c’est important :** La propriété `BarHeight` influence directement la taille visuelle du code‑barres. La modifier est le cœur du **redimensionnement d’un code‑barres** avec Aspose.BarCode.

## Étape 4 : Exporter la première image de code‑barres (hauteur 30 px)

Vous pouvez maintenant **exporter l’image du code‑barres** vers un fichier PNG. La méthode `Save` rend automatiquement le code‑barres avec les paramètres actuels.

```csharp
// Step 4: Save the barcode image with a 30‑pixel height
barcode.Save("DatabarBarHeight30Pixels.png", BarCodeImageFormat.Png);
```

Le fichier résultant ressemble à ceci :

![How to resize barcode example](https://example.com/images/databar-30px.png){: .align-center alt="Exemple de redimensionnement de code‑barres – hauteur de 30 pixels"}

## Étape 5 : Modifier la hauteur des barres pour créer un code‑barres plus grand

Pour démontrer le **redimensionnement d’un code‑barres** de façon dynamique, ajustez la propriété `BarHeight` et réenregistrez. Cela ne **requiert pas** la création d’une nouvelle instance `BarcodeGenerator` ; vous modifiez simplement l’objet existant.

```csharp
// Step 5: Change the bar height to 60 pixels for a larger barcode
barcode.Parameters.Barcode.BarHeight.Pixels = 60;
```

## Étape 6 : Exporter l’image de code‑barres redimensionnée (hauteur 60 px)

```csharp
// Step 6: Save the barcode image with the new 60‑pixel height
barcode.Save("DatabarBarHeight60Pixels.png", BarCodeImageFormat.Png);
```

Vous avez maintenant deux fichiers PNG — l’un à 30 px et l’autre à 60 px — montrant comment les mêmes données peuvent être rendues à différentes tailles.

### Résultat attendu

| Nom du fichier                     | Hauteur de la barre (px) | Résultat visuel |
|------------------------------------|--------------------------|-----------------|
| `DatabarBarHeight30Pixels.png`| 30 | ![30 px barcode](https://example.com/images/databar-30px.png){: alt="Code‑barres DataBar Omni‑directional de 30 pixels"} |
| `DatabarBarHeight60Pixels.png`| 60 | ![60 px barcode](https://example.com/images/databar-60px.png){: alt="Code‑barres DataBar Omni‑directional de 60 pixels"} |

Les deux images sont des codes‑barres GS1‑128 DataBar valides, prêts à être scannés.

## Étape 7 : Optionnel – Ajuster des paramètres visuels supplémentaires

Bien que l’objectif principal soit le **redimensionnement d’un code‑barres**, vous pourriez également vouloir ajuster :

| Propriété | Description | Valeurs typiques |
|----------|-------------|----------------|
| `XDimension.Pixels` | Largeur de la barre la plus fine | 1–4 |
| `BarHeight.Pixels`  | Hauteur de l’ensemble du code‑barres | 20–200 |
| `Resolution` | DPI pour la sortie raster | 72, 150, 300 |
| `ForeColor` / `BackColor` | Couleurs de premier plan et d’arrière‑plan | `Color.Black`, `Color.White` |

Exemple :

```csharp
barcode.Parameters.Barcode.XDimension.Pixels = 3;
barcode.Parameters.Barcode.ForeColor = Color.DarkBlue;
barcode.Parameters.Barcode.BackColor = Color.White;
barcode.Parameters.ImageResolution.DpiX = 300;
barcode.Parameters.ImageResolution.DpiY = 300;
```

Ces ajustements n’affectent pas la logique de **redimensionnement**, mais vous donnent un contrôle complet sur la qualité finale de l’image.

## Pièges courants et comment les éviter

| Problème | Symptôme | Solution |
|----------|----------|----------|
| Hauteur de la barre ne change pas | Les images enregistrées sont identiques | Assurez‑vous de modifier `barcode.Parameters.Barcode.BarHeight.Pixels` *avant* chaque appel à `Save`. |
| Le code‑barres devient illisible | Le scanner indique « cannot read » | Conservez `XDimension` ≥ 2 px pour DataBar Omni‑directional ; des barres trop fines peuvent empêcher la lecture. |
| Le fichier PNG est flou | Exporté avec un DPI faible | Définissez `barcode.Parameters.ImageResolution.DpiX/Y` à au moins 150 pour des images de qualité impression. |
| Le fichier est écrasé par inadvertance | La nouvelle image remplace l’ancienne | Utilisez des noms de fichiers uniques ou incluez la valeur de hauteur dans le nom de fichier, comme montré ci‑dessus. |

## Exemple complet, exécutable

Copiez l’ensemble du bloc ci‑dessous dans une nouvelle application console (`Program.cs`). Le code compile et s’exécute tel quel, produisant les deux fichiers PNG dans le dossier de sortie du projet.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;
using System.Drawing.Imaging;

class Program
{
    static void Main()
    {
        // 1️⃣ Create a DataBar Omni‑directional barcode generator
        BarcodeGenerator barcode = new BarcodeGenerator(
            EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");

        // 2️⃣ Set common parameters
        barcode.Parameters.Barcode.XDimension.Pixels = 2;   // thin bar width
        barcode.Parameters.Barcode.BarHeight.Pixels = 30; // first height

        // 3️⃣ Export first image (30 px height)
        barcode.Save("DatabarBarHeight30Pixels.png", BarCodeImageFormat.Png);
        Console.WriteLine("Saved 30‑pixel barcode.");

        // 4️⃣ Change height to 60 px
        barcode.Parameters.Barcode.BarHeight.Pixels = 60;

        // 5️⃣ Export second image (60 px height)
        barcode.Save("DatabarBarHeight60Pixels.png", BarCodeImageFormat.Png);
        Console.WriteLine("Saved 60‑pixel barcode.");

        // Optional: tweak additional settings (uncomment if needed)
        // barcode.Parameters.Barcode.ForeColor = System.Drawing.Color.DarkBlue;
        // barcode.Parameters.ImageResolution.DpiX = 300;
        // barcode.Parameters.ImageResolution.DpiY = 300;
    }
}
```

L’exécution du programme produit :

```
Saved 30‑pixel barcode.
Saved 60‑pixel barcode.
```

Vérifiez le dossier de sortie pour les deux fichiers PNG. Les deux sont prêts pour l’impression, l’intégration dans des PDF ou l’envoi à un dispositif distant.

## Conclusion

Dans ce guide, nous avons couvert le **redimensionnement d’un code‑barres** en C# avec Aspose.BarCode, présenté un **exemple complet de générateur de code‑barres**, et montré comment **exporter des images de code‑barres** à différentes hauteurs. Vous savez maintenant comment :

1. **Créer des objets Databar barcode** avec des données personnalisées.  
2. Ajuster `BarHeight` (le cœur du redimensionnement).  
3. Exporter des fichiers PNG à la taille requise.

À partir de là, vous pouvez explorer d’autres personnalisations — différentes symbologies, palettes de couleurs ou formats vectoriels comme SVG. Le même schéma (`barcode.Parameters.Barcode.BarHeight.Pixels = <value>`) fonctionne pour tout type de code‑barres pris en charge par Aspose.BarCode, vous permettant d’appliquer en toute confiance les connaissances de **redimensionnement d’un code‑barres** à l’ensemble de votre application.

---

**Étapes suivantes**

- Essayez de redimensionner d’autres symbologies (QR, Code128) pour voir comment la hauteur et la largeur interagissent.  
- Utilisez `BarCodeImageFormat.Svg` pour générer des graphiques vectoriels évolutifs pour les pages web.  
- Intégrez les images générées dans des rapports PDF avec Aspose.PDF ou iTextSharp.  

Bon codage, et profitez de la flexibilité offerte par la génération programmatique de codes‑barres !

## Que devriez‑vous apprendre ensuite ?

Les tutoriels suivants couvrent des sujets étroitement liés qui s’appuient sur les techniques démontrées dans ce guide. Chaque ressource comprend des exemples de code complets et fonctionnels avec des explications étape par étape pour vous aider à maîtriser des fonctionnalités API supplémentaires et explorer des approches d’implémentation alternatives dans vos propres projets.

- [Comment générer et ajuster la hauteur du code‑barres One‑Dimensional Databar avec Aspose.BarCode pour .NET](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-barcode-height-adjustment/)
- [Comment générer un code‑barres – Configuration Code 39 avec Aspose.BarCode](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-code-39-configuration/)
- [Comment générer des codes‑barres DataMatrix avec Aspose.BarCode pour .NET – Guide étape par étape](/barcode/english/net/datamatrix-barcode-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}