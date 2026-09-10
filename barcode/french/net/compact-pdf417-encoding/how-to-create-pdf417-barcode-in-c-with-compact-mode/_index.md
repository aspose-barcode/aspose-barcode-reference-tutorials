---
category: general
date: 2026-09-10
description: Créez un code‑barres PDF417 en C# rapidement. Apprenez comment activer
  le mode compact, définir les colonnes et générer un PNG avec BarcodeGenerator.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create PDF417 barcode
- enable compact mode
- barcode generator C#
- how to generate barcode
- how to set columns
language: fr
lastmod: 2026-09-10
og_description: Créer un code‑barres PDF417 en C# en activant le mode compact, en
  définissant les colonnes et en l’enregistrant au format PNG. Suivez le guide complet
  étape par étape.
og_image_alt: Screenshot of a compact PDF417 barcode generated with C#
og_title: Créer un code‑barres PDF417 en C# – tutoriel du mode compact
schemas:
- author: Aspose
  dateModified: '2026-09-10'
  description: Create PDF417 barcode in C# quickly. Learn how to enable compact mode,
    set columns, and generate a PNG with BarcodeGenerator.
  headline: How to create PDF417 barcode in C# with compact mode
  type: TechArticle
tags:
- barcode
- C#
- PDF417
title: Comment créer un code‑barres PDF417 en C# en mode compact
url: /fr/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-in-c-with-compact-mode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Comment créer un code‑barres PDF417 en C# avec le mode compact

Si vous devez **créer un code‑barres PDF417** dans une application .NET, ce guide vous montre exactement comment le faire. Vous verrez comment **activer le mode compact**, définir le nombre de colonnes, et enregistrer le résultat sous forme d’image PNG à l’aide de la bibliothèque BarcodeGenerator C#.

Générer un code‑barres est une exigence courante pour le suivi d’inventaire, les systèmes de billetterie et les applications de numérisation mobile. À la fin de ce tutoriel, vous disposerez d’un exemple autonome, exécutable, qui produit un code‑barres PDF417 compact prêt à être utilisé en production.

## Prérequis

Avant de commencer, assurez‑vous d’avoir :

* .NET 6.0 ou version ultérieure installé (le code fonctionne également avec .NET Framework 4.7+)
* Une version récente de la bibliothèque **BarcodeGenerator** (par ex., Aspose.BarCode for .NET)
* Un IDE ou éditeur tel que Visual Studio 2022 ou VS Code
* Le droit d’écriture sur un dossier où le PNG sera enregistré

Aucun package NuGet supplémentaire n’est requis au‑delà de la bibliothèque de code‑barres elle‑même.

## Étape 1 : Créer un générateur de code‑barres PDF417

La première étape consiste à instancier un objet `BarcodeGenerator` avec l’énumération `EncodeTypes.Pdf417` et le texte que vous souhaitez encoder. Cet objet pilote l’ensemble du processus de génération.

```csharp
using Aspose.BarCode.Generation;

// Step 1: Create a PDF417 barcode generator with the desired text
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(EncodeTypes.Pdf417, "Compact mode");
```

*Pourquoi c’est important* : la valeur `EncodeTypes.Pdf417` indique à la bibliothèque d’utiliser la symbologie PDF417, tandis que le deuxième argument fournit la charge utile. Vous pouvez remplacer `"Compact mode"` par n’importe quelle chaîne alphanumérique que vous devez encoder.

## Étape 2 : Définir la dimension X (largeur du module)

La dimension X contrôle la largeur de chaque petit carré (module) du code‑barres. Des valeurs plus petites produisent une image plus serrée, ce qui est utile lorsque l’espace est limité.

```csharp
// Step 2: Set the X dimension (module width) in pixels
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

Une valeur de `2` pixels représente un bon compromis entre lisibilité et compacité pour la plupart des scanners basés sur écran.

## Étape 3 : Définir le nombre de colonnes

PDF417 peut organiser les données dans une grille de lignes et de colonnes. Modifier le nombre de colonnes change le rapport d’aspect du code‑barres.

```csharp
// Step 3: Define the number of columns for the PDF417 barcode
barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 3;
```

Définir **how to set columns** à `3` donne un code‑barres court et large qui s’adapte bien à une étiquette. Vous pouvez expérimenter avec des valeurs de `1` à `30` selon la quantité de données et le scanner cible.

## Étape 4 : Activer le mode compact

Le mode compact supprime les rangées de remplissage inutiles, rendant le code‑barres plus petit sans perdre l’intégrité des données. C’est l’étape clé pour un **PDF417 compact**.

```csharp
// Step 4: Enable compact mode by truncating the barcode
barcodeGenerator.Parameters.Barcode.Pdf417.Truncate = true;
```

Lorsque `Truncate` est `true`, la bibliothèque calcule automatiquement le nombre minimal de rangées nécessaires pour stocker les données, d’où l’aspect « serré » de l’image finale.

## Étape 5 : Enregistrer le code‑barres généré sous forme d’image PNG

Enfin, écrivez le code‑barres dans un fichier. Le PNG préserve les bords nets nécessaires à une numérisation fiable.

```csharp
// Step 5: Save the generated barcode as a PNG image
barcodeGenerator.Save("YOUR_DIRECTORY/CompactPdf417.png", BarCodeImageFormat.Png);
```

Remplacez `YOUR_DIRECTORY` par un chemin absolu ou relatif auquel votre application peut écrire. Après exécution, vous trouverez un fichier `CompactPdf417.png` contenant le code‑barres.

### Code source complet

Assembler toutes les étapes donne un programme unique, prêt à être exécuté :

```csharp
using System;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Create a PDF417 barcode generator with the desired text
        BarcodeGenerator barcodeGenerator = new BarcodeGenerator(EncodeTypes.Pdf417, "Compact mode");

        // Set the X dimension (module width) in pixels
        barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;

        // Define the number of columns for the PDF417 barcode
        barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 3;

        // Enable compact mode by truncating the barcode
        barcodeGenerator.Parameters.Barcode.Pdf417.Truncate = true;

        // Save the generated barcode as a PNG image
        barcodeGenerator.Save("CompactPdf417.png", BarCodeImageFormat.Png);

        Console.WriteLine("PDF417 barcode created successfully.");
    }
}
```

L’exécution de ce programme produit `CompactPdf417.png` dans le même dossier que l’exécutable. Ouvrez l’image avec n’importe quel visualiseur ; vous devriez voir un code‑barres PDF417 dense, à fort contraste, prêt à être scanné.

## Comment activer le mode compact dans d’autres scénarios

* **Génération par lots** – Lors de la création de nombreux codes‑barres, définissez `Truncate` une fois sur le générateur et réutilisez‑le pour chaque nouvelle charge utile.
* **Formats d’image différents** – La même méthode `Save` fonctionne avec `BarCodeImageFormat.Jpeg` ou `BarCodeImageFormat.Bmp` si vous avez besoin d’un autre type de fichier.
* **Nombre de colonnes dynamique** – Si la longueur de la chaîne encodée varie, calculez un nombre optimal de colonnes en fonction de la longueur de la chaîne et de la résolution du scanner.

## Comment définir les colonnes pour des cas d’utilisation spécifiques

* **Impression d’étiquettes** – Utilisez un faible nombre de colonnes (par ex., `2`‑`5`) pour garder le code‑barres suffisamment court pour tenir sur des étiquettes étroites.
* **Numérisation mobile** – Des nombres de colonnes plus élevés (`10`‑`15`) produisent des codes‑barres plus hauts, plus faciles à mettre au point avec les caméras de téléphone.
* **Compromis correction d’erreurs** – Plus de colonnes réduisent le nombre de rangées, ce qui peut affecter la correction d’erreurs intégrée du code‑barres. Testez avec votre scanner cible pour trouver le point optimal.

## Pièges courants et astuces professionnelles

| Problème | Pourquoi cela se produit | Solution |
|----------|--------------------------|----------|
| Le code‑barres est illisible | Dimension X trop faible (ex. : `1` pixel) | Augmentez `XDimension.Pixels` à au moins `2` |
| L’image est trop grande | Colonnes trop nombreuses pour une charge courte | Réduisez `Pdf417.Columns` ou activez `Truncate` |
| Le fichier PNG est vide | Le dossier de sortie n’existe pas ou les droits d’écriture manquent | Assurez‑vous que le répertoire existe et que le processus a les droits d’écriture |
| Le scanner indique « données corrompues » | Truncate désactivé alors que de nombreuses colonnes sont utilisées | Activez `Truncate` ou diminuez le nombre de colonnes |

## Vérification du résultat

Vous pouvez vérifier le code‑barres avec n’importe quelle application de lecture PDF417 (de nombreuses applications gratuites Android/iOS existent). Ouvrez `CompactPdf417.png` dans l’application et confirmez que le texte décodé correspond à la charge utile d’origine (« Compact mode »). Si le texte diffère, revérifiez le drapeau `Truncate` et les paramètres de colonnes.

## Prochaines étapes

* **Intégrer avec ASP.NET Core** – Retournez le PNG directement depuis une action de contrôleur au lieu de l’enregistrer sur disque.
* **Ajouter du texte lisible par l’homme** – Utilisez `barcodeGenerator.Parameters.Barcode.CodeTextParameters` pour afficher la chaîne encodée sous le code‑barres.
* **Explorer d’autres symbologies** – La même classe `BarcodeGenerator` prend en charge QR, Code128, DataMatrix, et plus encore. Changez `EncodeTypes` pour les essayer.

---

### Conclusion

Vous savez maintenant comment **créer un code‑barres PDF417** en C# tout en **activant le mode compact**, en contrôlant **comment définir les colonnes**, et en utilisant l’**API du générateur de code‑barres C#** pour **générer un code‑barres** qui répond aux contraintes de taille du monde réel. Appliquez ces étapes à tout projet .NET nécessitant des codes‑barres compacts et à haute densité, et étendez le modèle à d’autres formats de code‑barres selon vos besoins. Bon codage !

## Que devez‑vous apprendre ensuite ?

Les tutoriels suivants couvrent des sujets étroitement liés qui s’appuient sur les techniques démontrées dans ce guide. Chaque ressource comprend des exemples de code complets avec des explications pas à pas pour vous aider à maîtriser des fonctionnalités API supplémentaires et à explorer des approches d’implémentation alternatives dans vos propres projets.

- [Create PDF417 Barcode in C# – Complete Step‑by‑Step Guide](/barcode/english/net/compact-pdf417-encoding/create-pdf417-barcode-in-c-complete-step-by-step-guide/)
- [How to Set Error Level in PDF417 Barcode – Complete Guide](/barcode/english/net/compact-pdf417-encoding/how-to-set-error-level-in-pdf417-barcode-complete-guide/)
- [How to Save Barcode in C# – Generate PDF417 Barcodes](/barcode/english/net/compact-pdf417-encoding/how-to-save-barcode-in-c-generate-pdf417-barcodes/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}