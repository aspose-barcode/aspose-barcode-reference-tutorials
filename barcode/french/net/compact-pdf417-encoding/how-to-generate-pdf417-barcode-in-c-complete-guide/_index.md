---
category: general
date: 2026-09-26
description: Générez un code‑barres PDF417 en C# avec Aspose.BarCode. Suivez ce tutoriel
  pas à pas pour configurer les colonnes, activer le mode compact et enregistrer au
  format PNG.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate pdf417 barcode
- pdf417 barcode generator c#
- Aspose.BarCode C#
- barcode image format PNG
- compact PDF417 mode
language: fr
lastmod: 2026-09-26
og_description: Générez un code‑barres PDF417 en C# avec Aspose.BarCode. Ce guide
  vous montre comment définir les colonnes, activer le mode compact et exporter le
  résultat sous forme d’image PNG.
og_image_alt: Screenshot of a generated PDF417 barcode saved as PNG
og_title: Générer un code‑barres PDF417 en C# – tutoriel étape par étape
schemas:
- author: Aspose
  dateModified: '2026-09-26'
  description: Generate PDF417 barcode in C# with Aspose.BarCode. Follow this step‑by‑step
    tutorial to configure columns, enable compact mode, and save as PNG.
  headline: How to generate PDF417 barcode in C# – complete guide
  type: TechArticle
tags:
- C#
- barcode
- Aspose
- PDF417
title: Comment générer un code‑barres PDF417 en C# – guide complet
url: /fr/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-complete-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Comment générer un code-barres PDF417 en C# – guide complet

Si vous devez **générer un code-barres PDF417** dans une application .NET, ce tutoriel vous montre une solution prête à l’emploi. Vous verrez comment configurer la taille du code-barres, le nombre de colonnes et le mode compact, puis enregistrer le résultat sous forme de fichier PNG de haute qualité.

Générer un code-barres est une exigence courante pour les systèmes d’inventaire, les plateformes de billetterie et le codage de documents. À la fin de ce guide, vous disposerez d’un programme C# autonome qui produit un code-barres PDF417 compact en utilisant la bibliothèque **pdf417 barcode generator C#** d’Aspose.

## Ce dont vous avez besoin

- .NET 6.0 SDK ou version ultérieure (le code fonctionne également avec .NET Framework 4.7+)
- Une licence valide d’Aspose.BarCode pour .NET (l’évaluation gratuite fonctionne pour les tests)
- Un IDE ou éditeur tel que Visual Studio 2022, Rider ou VS Code
- Une connaissance de base des projets console C#

> **Astuce :** Si vous utilisez l’évaluation gratuite, l’image générée contiendra un petit filigrane Aspose. Une licence achetée supprime le filigrane et débloque l’ensemble complet des fonctionnalités.

## Étape 1 : Configurer la bibliothèque Aspose.BarCode

Créez un nouveau projet console et ajoutez le package NuGet Aspose.BarCode.

```bash
dotnet new console -n Pdf417Demo
cd Pdf417Demo
dotnet add package Aspose.BarCode
```

Le package fournit la classe `BarcodeGenerator`, qui constitue le cœur du flux de travail **pdf417 barcode generator C#**.

## Étape 2 : Écrire le programme complet de génération de code-barres

Ouvrez `Program.cs` et remplacez son contenu par le code suivant. Le programme montre chaque étape requise, de l’initialisation du générateur à l’enregistrement de l’image.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode.BarCodeImageFormat;

namespace Pdf417Demo
{
    internal class Program
    {
        private static void Main()
        {
            // Step 2.1: Create a generator for PDF417 with Unicode text.
            // The text contains special characters to prove Unicode handling.
            var generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Åspóse.Barcóde©");

            // Step 2.2: Define the module (pixel) size of each barcode element.
            // XDimension controls the width of a single bar; 2 pixels gives a clear image.
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // Step 2.3: Set the number of columns.
            // PDF417 can automatically choose columns, but fixing it to 3 produces a compact layout.
            generator.Parameters.Barcode.Pdf417.Columns = 3;

            // Step 2.4: Enable compact mode.
            // Truncate reduces the amount of data stored, making the barcode smaller.
            generator.Parameters.Barcode.Pdf417.Truncate = true;

            // Step 2.5: Choose the output format and file path.
            // PNG preserves the exact pixel dimensions without compression artifacts.
            string outputPath = "CompactPdf417.png";
            generator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"PDF417 barcode saved to {outputPath}");
        }
    }
}
```

### Pourquoi chaque ligne est importante

| Ligne | Objectif |
|------|----------|
| `new BarcodeGenerator(EncodeTypes.Pdf417, "...")` | Instancie un générateur PDF417 et définit le texte encodé. PDF417 prend en charge de grands ensembles de données et l’Unicode, ce qui le rend adapté aux identifiants complexes. |
| `XDimension.Pixels = 2` | Contrôle la densité visuelle. Des valeurs plus petites produisent des barres plus fines ; des valeurs plus grandes améliorent la lisibilité sur les écrans à basse résolution. |
| `Pdf417.Columns = 3` | Remplace le calcul automatique du nombre de colonnes. Des colonnes fixes sont utiles lorsque vous devez adapter le code-barres à un espace prédéfini. |
| `Pdf417.Truncate = true` | Active le mode compact, qui supprime les remplissages inutiles et réduit la taille globale. |
| `Save(..., BarCodeImageFormat.Png)` | Enregistre le code-barres dans un fichier PNG, un format sans perte idéal pour un traitement ultérieur ou l’intégration dans des PDF. |

## Étape 3 : Exécuter le programme et vérifier la sortie

Compilez et exécutez le projet :

```bash
dotnet run
```

Vous devriez voir un message dans la console confirmant l’emplacement du fichier, et un fichier nommé **CompactPdf417.png** apparaîtra dans le dossier du projet.

![Exemple de code-barres PDF417 généré](images/compact-pdf417.png){.img-responsive alt="Exemple de code-barres PDF417 généré"}

*L’image montre un code-barres PDF417 compact qui encode la chaîne “Åspóse.Barcóde©”.*  

Si vous ouvrez le PNG dans un visualiseur d’images, vous remarquerez trois colonnes de blocs de données empilés, chaque barre ayant une largeur de 2 pixels. Scanner le code-barres avec un lecteur PDF417 standard renvoie le texte original, confirmant que le générateur fonctionne comme prévu.

## Pièges courants et comment les éviter

| Problème | Raison | Solution |
|----------|--------|----------|
| Le code-barres apparaît flou | XDimension réglé trop bas pour le DPI cible | Augmentez `XDimension.Pixels` à 3 ou 4, ou rendez à une résolution supérieure en utilisant `generator.Save(..., BarCodeImageFormat.Tiff)` |
| Les caractères Unicode sont perdus | La chaîne d’entrée n’est pas encodée en UTF‑8 | Assurez‑vous que le fichier source est enregistré avec l’encodage UTF‑8 ; le générateur gère automatiquement l’Unicode lorsque le type de la chaîne est `string`. |
| Truncate génère une exception | La taille des données dépasse le maximum pour le nombre de colonnes choisi | Augmentez `Pdf417.Columns` ou définissez `Pdf417.Truncate = false` pour laisser le générateur allouer suffisamment d’espace. |
| Licence non appliquée | La version d’évaluation ajoute un filigrane | Appliquez un fichier de licence valide via `Aspose.BarCode.License` avant de créer le générateur. |

## Étendre la solution

Une fois que vous avez le flux de base **generate PDF417 barcode**, vous pouvez explorer des fonctionnalités supplémentaires :

- **Niveau de correction d’erreurs** – Ajustez `generator.Parameters.Barcode.Pdf417.ErrorCorrectionLevel` pour augmenter la résilience face aux dommages.
- **Personnalisation des couleurs** – Utilisez `generator.Parameters.Barcode.ForegroundColor` et `BackgroundColor` pour correspondre aux directives de marque.
- **Intégration dans les PDF** – Combinez Aspose.PDF avec Aspose.BarCode pour placer le code-barres directement dans un document PDF.
- **Génération par lots** – Parcourez une collection d’identifiants pour produire plusieurs fichiers PNG en une seule exécution.

Toutes ces options sont documentées dans la référence de l’API Aspose.BarCode et suivent le même schéma démontré ci‑dessus.

## Conclusion

Vous savez maintenant comment **générer un code-barres PDF417** en C# en utilisant Aspose.BarCode, configurer les colonnes, activer le mode compact et exporter le résultat sous forme d’image PNG. L’exemple complet fonctionne immédiatement et peut être adapté à des projets plus importants, tels que les systèmes de billetterie, les étiquettes d’inventaire ou le codage sécurisé de documents.

Ensuite, essayez les paramètres avancés du **pdf417 barcode generator C#** comme la correction d’erreurs et la personnalisation des couleurs, ou intégrez le code-barres dans un rapport PDF avec Aspose.PDF. Expérimentez avec différentes valeurs de `XDimension` et différents nombres de colonnes pour trouver le compromis optimal entre taille et fiabilité du scan pour votre cas d’utilisation spécifique. Bon codage !

## Que devriez‑vous apprendre ensuite ?

Les tutoriels suivants couvrent des sujets étroitement liés qui s’appuient sur les techniques démontrées dans ce guide. Chaque ressource comprend des exemples de code complets et fonctionnels avec des explications étape par étape pour vous aider à maîtriser des fonctionnalités d’API supplémentaires et explorer des approches d’implémentation alternatives dans vos propres projets.

- [Générer un code-barres PDF417 en C# – guide complet avec mise en page compacte](/barcode/english/net/compact-pdf417-encoding/generate-pdf417-barcode-in-c-complete-guide-with-compact-lay/)
- [Exemple de code-barres Aspose : générer Macro PDF417 en C#](/barcode/english/net/compact-pdf417-encoding/aspose-barcode-example-generate-macro-pdf417-in-c/)
- [Comment enregistrer un code-barres en C# – générer des codes-barres PDF417](/barcode/english/net/compact-pdf417-encoding/how-to-save-barcode-in-c-generate-pdf417-barcodes/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}