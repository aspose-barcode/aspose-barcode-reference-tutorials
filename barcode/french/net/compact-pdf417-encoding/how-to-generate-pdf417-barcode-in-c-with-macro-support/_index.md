---
category: general
date: 2026-10-21
description: Apprenez à générer un code‑barres PDF417 en C# avec Aspose.BarCode. Les
  étapes détaillées couvrent les paramètres du code‑barres PDF417, la création d’un
  code‑barres macro PDF417 et l’enregistrement au format PNG.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to generate PDF417 barcode
- PDF417 barcode settings
- Macro PDF417 barcode
- barcode generator C#
- BarCodeImageFormat PNG
- EncodeTypes.MacroPdf417
language: fr
lastmod: 2026-10-21
og_description: Comment générer un code‑barres PDF417 en C# avec Aspose.BarCode. Suivez
  ce tutoriel étape par étape pour configurer les paramètres du code‑barres PDF417,
  créer un code‑barres PDF417 macro et l’exporter au format PNG.
og_image_alt: Screenshot of a Macro PDF417 barcode generated with C# code
og_title: Comment générer un code‑barres PDF417 en C# – guide complet
schemas:
- author: Aspose
  dateModified: '2026-10-21'
  description: Learn how to generate PDF417 barcode in C# using Aspose.BarCode. Detailed
    steps cover PDF417 barcode settings, macro PDF417 barcode creation, and saving
    as PNG.
  headline: How to generate PDF417 barcode in C# with macro support
  type: TechArticle
- description: Learn how to generate PDF417 barcode in C# using Aspose.BarCode. Detailed
    steps cover PDF417 barcode settings, macro PDF417 barcode creation, and saving
    as PNG.
  name: How to generate PDF417 barcode in C# with macro support
  steps:
  - name: '**Create a `BarcodeGenerator` instance** using `EncodeTypes.MacroPdf417`.'
    text: '**Create a `BarcodeGenerator` instance** using `EncodeTypes.MacroPdf417`.'
  - name: '**Adjust basic barcode appearance** (module size, colors, etc.).'
    text: '**Adjust basic barcode appearance** (module size, colors, etc.).'
  - name: '**Configure PDF417‑specific settings**, including macro‑related fields.'
    text: '**Configure PDF417‑specific settings**, including macro‑related fields.'
  - name: '**Save the generated barcode image** with `BarCodeImageFormat PNG`.'
    text: '**Save the generated barcode image** with `BarCodeImageFormat PNG`.'
  type: HowTo
tags:
- PDF417
- barcode
- C#
- Aspose.BarCode
title: Comment générer un code‑barres PDF417 en C# avec prise en charge des macros
url: /fr/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-with-macro-support/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Comment générer un code‑barres PDF417 en C# avec prise en charge des macros

Si vous devez générer un code‑barres PDF417 en C#, ce guide vous montre une solution complète, prête à l’emploi. Que vous construisiez un système d’étiquetage logistique ou que vous codiez de gros blocs de données, vous verrez comment configurer les paramètres du code‑barres PDF417, créer un code‑barres Macro PDF417, et enregistrer le résultat sous forme d’image PNG.

Générer un code‑barres PDF417 ne nécessite pas de manipulation de bits de bas niveau. En utilisant la classe **barcode generator C#** d’Aspose.BarCode, vous pouvez vous concentrer sur la logique métier tandis que la bibliothèque gère l’encodage, la correction d’erreurs et le rendu de l’image.

## Ce dont vous avez besoin

Avant de commencer, assurez‑vous d’avoir :

- **.NET 6.0** ou version ultérieure (le code fonctionne également avec .NET Framework 4.6+)
- **Aspose.BarCode for .NET** package NuGet (`Install-Package Aspose.BarCode`)
- Un environnement de développement tel que Visual Studio 2022 ou Visual Studio Code
- Le droit d’écriture sur un dossier où l’image PNG sera enregistrée

Ces prérequis garantissent que l’exemple se compile et s’exécute sans configuration supplémentaire.

## Comment générer un code‑barres PDF417 – aperçu étape par étape

Voici une feuille de route concise du processus :

1. **Créer une instance `BarcodeGenerator`** en utilisant `EncodeTypes.MacroPdf417`.
2. **Ajuster l’apparence de base du code‑barres** (taille du module, couleurs, etc.).
3. **Configurer les paramètres spécifiques à PDF417**, y compris les champs liés aux macros.
4. **Enregistrer l’image du code‑barres généré** avec `BarCodeImageFormat PNG`.

Chaque étape est détaillée, avec des extraits de code complets que vous pouvez copier directement dans une application console.

## Étape 1 : Configurer l’environnement de développement

Créez un nouveau projet console et ajoutez la référence Aspose.BarCode :

```bash
dotnet new console -n Pdf417Demo
cd Pdf417Demo
dotnet add package Aspose.BarCode
```

Ouvrez `Program.cs` et ajoutez les espaces de noms requis :

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;
```

Ces importations vous donnent accès à `BarcodeGenerator`, `EncodeTypes` et `BarCodeImageFormat`.

## Étape 2 : Créer le générateur de code‑barres Macro PDF417

La première ligne de l’implémentation crée l’objet **Macro PDF417 barcode**. L’énumération `EncodeTypes.MacroPdf417` indique à la bibliothèque d’utiliser la variante macro du PDF417.

```csharp
// Step 1: Create a Macro PDF417 barcode generator with the desired text
using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.MacroPdf417, "Sample Text"))
{
    // Subsequent configuration goes here
}
```

> **Pourquoi c’est important :** Utiliser `EncodeTypes.MacroPdf417` active les champs macro (`FileID`, `SegmentID`, etc.) qui vous permettent de répartir une charge utile importante sur plusieurs images de code‑barres tout en préservant l’ordre.

## Étape 3 : Ajuster l’apparence de base du code‑barres

Avant de modifier les paramètres spécifiques à PDF417, définissez la largeur du module (pixel). Une valeur de `2` donne une image claire et lisible sans taille de fichier excessive.

```csharp
// Step 2: Adjust basic barcode appearance
generator.Parameters.Barcode.XDimension.Pixels = 2;   // pixel width of a single module
```

Vous pouvez également changer les couleurs de premier plan/arrière‑plan ici si votre interface nécessite une palette différente.

## Étape 4 : Configurer les paramètres spécifiques à PDF417

Les **paramètres du code‑barres PDF417** sont exposés via `generator.Parameters.Barcode.Pdf417`. Les champs macro les plus importants sont présentés ci‑dessous :

```csharp
// Step 3: Configure PDF417‑specific settings
generator.Parameters.Barcode.Pdf417.Columns = 5;                     // number of columns (affects width)
generator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;     // unique file identifier
generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;       // segment number within the file
generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;  // total number of segments
generator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";  // optional human‑readable name
```

### Comprendre chaque propriété

| Propriété | Objectif | Plage typique |
|-----------|----------|---------------|
| `Columns` | Contrôle le nombre de colonnes de données par ligne. Plus de colonnes réduisent le nombre de lignes mais augmentent la largeur. | 1 – 30 |
| `MacroPdf417FileID` | Identifiant 32 bits qui regroupe tous les segments du même fichier logique. Doit être identique pour chaque segment. | Tout entier positif |
| `MacroPdf417SegmentID` | Index de base zéro du segment actuel. Incrémentez pour chaque code‑barres suivant. | 0 – `SegmentsCount`‑1 |
| `MacroPdf417SegmentsCount` | Nombre total de segments qui composent le fichier complet. Tous les segments doivent être générés. | ≥ 1 |
| `MacroPdf417FileName` | Nom descriptif optionnel (max 255 caractères). Utile pour le débogage. | Chaîne alphanumérique |

> **Astuce :** Gardez `Columns` entre 3 et 7 pour la plupart des imprimantes d’étiquettes. Des valeurs plus élevées peuvent dépasser la largeur imprimable sur des appareils à basse résolution.

## Étape 5 : Enregistrer le code‑barres sous forme d’image PNG

Enfin, écrivez le code‑barres sur le disque en utilisant `BarCodeImageFormat PNG`. PNG conserve une qualité sans perte, ce qui est essentiel pour un décodage fiable.

```csharp
// Step 4: Save the generated barcode image
string outputPath = Path.Combine(Environment.CurrentDirectory, "MacroPdf417.png");
generator.Save(outputPath, BarCodeImageFormat.Png);
```

Lorsque le programme se termine, vous trouverez `MacroPdf417.png` dans le dossier du projet. L’ouverture du fichier montre un code‑barres Macro PDF417 propre, prêt à être imprimé.

### Résultat attendu

L’image générée ressemble à l’exemple ci‑dessous (illustratif uniquement) :

![Macro PDF417 barcode example](macro-pdf417-barcode.png "Macro PDF417 barcode generated by C# code")

*Le texte alternatif de l’image est « Macro PDF417 barcode generated with C# code », répondant aux exigences d’accessibilité et de SEO.*

## Problèmes courants et dépannage

| Problème | Symptom | Solution |
|----------|---------|----------|
| **EncodeTypes incorrect** | Le code‑barres s’affiche comme un QR code ou du texte brut. | Assurez‑vous d’utiliser `EncodeTypes.MacroPdf417` (et non `EncodeTypes.Pdf417`). |
| **IDs de segment incohérents** | Le scanner signale « segment manquant ». | Incrémentez `MacroPdf417SegmentID` séquentiellement et maintenez `SegmentsCount` cohérent entre tous les fichiers. |
| **Taille de module trop grande** | Le code‑barres devient trop large pour l’étiquette. | Réduisez `XDimension.Pixels` ou diminuez `Columns`. |
| **Erreurs de chemin de fichier** | `UnauthorizedAccessException` lors de l’enregistrement. | Écrivez dans un dossier dont vous êtes propriétaire, par ex. `Environment.CurrentDirectory`. |
| **Package NuGet manquant** | Erreur de compilation : `BarcodeGenerator` introuvable. | Exécutez `dotnet add package Aspose.BarCode` avant de construire. |

Résoudre ces problèmes dès le départ vous fait gagner du temps lors de l’intégration de la génération de code‑barres dans des flux de travail plus larges.

## Extension de l’exemple

Maintenant que vous pouvez générer un seul code‑barres Macro PDF417, envisagez les étapes suivantes :

- **Génération en lot** : Parcourez une collection de fragments de données, en mettant à jour `MacroPdf417SegmentID` à chaque itération.
- **Formats d’image différents** : Remplacez `BarCodeImageFormat.Png` par `Jpeg` ou `Bmp` si votre système en aval préfère ceux‑ci.
- **Intégration dans des PDF** : Utilisez Aspose.PDF pour placer le PNG dans un rapport PDF à distribuer.
- **Vérification du scan** : Testez les codes‑barres générés avec un scanner matériel ou une application mobile qui prend en charge Macro PDF417.

Ces variantes conservent les **paramètres du code‑barres PDF417** de base tout en adaptant la sortie aux besoins de votre projet.

## Conclusion

Vous savez maintenant **comment générer un code‑barres PDF417** en C# avec Aspose.BarCode, depuis la création d’un `BarcodeGenerator` avec `EncodeTypes.MacroPdf417` jusqu’à la configuration des champs macro et l’enregistrement du résultat en `BarCodeImageFormat PNG`. Le code complet et exécutable montre l’approche recommandée, explique pourquoi chaque paramètre est important, et met en évidence les pièges courants que vous pourriez rencontrer.

N’hésitez pas à expérimenter avec le nombre de colonnes, les couleurs ou les formats de sortie, et à intégrer le générateur dans vos propres applications pour un encodage fiable de données à haute densité.


## Que devriez‑vous apprendre ensuite ?


Les tutoriels suivants couvrent des sujets étroitement liés qui s’appuient sur les techniques démontrées dans ce guide. Chaque ressource inclut des exemples de code complets et fonctionnels avec des explications étape par étape pour vous aider à maîtriser des fonctionnalités API supplémentaires et explorer des approches d’implémentation alternatives dans vos propres projets.

- [How to generate PDF417 barcodes in C# with Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcodes-in-c-with-aspose-barcode/)
- [How to create macro PDF417 barcode in C# using Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/how-to-create-macro-pdf417-barcode-in-c-using-aspose-barcode/)
- [How to save barcode and generate PDF417 with Aspose in C#](/barcode/english/net/compact-pdf417-encoding/how-to-save-barcode-and-generate-pdf417-with-aspose-in-c/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}