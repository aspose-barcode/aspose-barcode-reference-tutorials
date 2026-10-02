---
category: general
date: 2026-08-12
description: Générez un code‑barres Aspose avec Aspose.BarCode et apprenez à créer
  un PDF417 avec du texte personnalisé en quelques étapes simples.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate barcode aspose
- how to generate pdf417
- create barcode custom text
- Aspose.BarCode macro pdf417
- barcode metadata Aspose
language: fr
lastmod: 2026-08-12
og_description: Générez un code-barres Aspose en utilisant Aspose.BarCode. Ce tutoriel
  montre comment générer un PDF417 avec du texte personnalisé, des métadonnées macro,
  et enregistrer le résultat au format PNG.
og_image_alt: Screenshot of a MacroPdf417 barcode generated with Aspose.BarCode in
  C#
og_title: Générer un code‑barres Aspose – guide étape par étape
schemas:
- author: Aspose
  dateModified: '2026-08-12'
  description: Generate barcode aspose with Aspose.BarCode and learn how to generate
    pdf417 with custom text in a few easy steps.
  headline: Generate barcode aspose – complete C# guide
  type: TechArticle
tags:
- Aspose
- barcode
- pdf417
title: Générer un code-barres Aspose – guide complet C#
url: /fr/net/compact-pdf417-encoding/generate-barcode-aspose-complete-c-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Générer un code-barres aspose – guide complet C# 

Si vous devez **générer un code-barres aspose** pour un symbole MacroPdf417, ce tutoriel vous guide à travers l’ensemble du processus. Vous verrez comment configurer les options spécifiques aux macros, intégrer du texte personnalisé et enregistrer le code-barres en tant qu’image PNG.

Générer un code-barres avec Aspose.BarCode élimine les calculs manuels et garantit la conformité à la spécification PDF417. Dans les étapes ci‑dessous, vous apprendrez également **comment générer pdf417** avec des métadonnées personnalisées telles que l’ID de fichier, le nombre de segments et les horodatages. À la fin du guide, vous disposerez d’un exemple de code prêt à l’emploi que vous pourrez intégrer dans n’importe quel projet .NET.

## Prérequis

* .NET 6.0 ou ultérieur (le code fonctionne également avec .NET Framework 4.7+)
* Une licence valide d’Aspose.BarCode pour .NET (l’évaluation gratuite fonctionne pour les tests)
* Visual Studio 2022 ou tout IDE C# de votre choix
* Familiarité de base avec la syntaxe C# et les concepts orientés objet

Aucun paquet NuGet supplémentaire n’est requis au-delà de **Aspose.BarCode**.

## Étape 1 : Installer le paquet NuGet Aspose.BarCode

Ouvrez votre projet dans Visual Studio, puis exécutez la commande suivante dans la console du Gestionnaire de paquets :

```powershell
Install-Package Aspose.BarCode
```

Le paquet ajoute l’espace de noms `Aspose.BarCode`, qui contient la classe `BarcodeGenerator` utilisée tout au long de ce tutoriel.

## Étape 2 : Créer un générateur de code-barres pour MacroPdf417

La première ligne crée une instance de `BarcodeGenerator` qui cible la symbologie **MacroPdf417** et intègre le texte personnalisé que vous souhaitez encoder.

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;
using System;

// Step 2: Initialize the generator with custom text
using (BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
           EncodeTypes.MacroPdf417, "Åspóse.Barcóde©"))
{
    // The rest of the configuration goes here
}
```

*Pourquoi c’est important* : L’énumération `EncodeTypes.MacroPdf417` indique à Aspose de traiter le code-barres comme un symbole PDF417 activé pour les macros, ce qui permet de diviser de grandes quantités de données en plusieurs segments. La chaîne `"Åspóse.Barcóde©"` montre que le générateur gère correctement les caractères Unicode.

## Étape 3 : Définir la taille de module de base

La taille du module contrôle la densité visuelle du code-barres. Une valeur de pixel de `2` produit une image nette qui s’imprime correctement sur les imprimantes d’étiquettes standard.

```csharp
    // Step 3: Set the X‑dimension (module width) in pixels
    barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

Augmenter la valeur rend le code-barres plus grand, tandis que la diminuer peut entraîner des problèmes de lecture sur les appareils à basse résolution.

## Étape 4 : Configurer les options de mise en page spécifiques aux macros PDF417

MacroPdf417 nécessite plusieurs paramètres supplémentaires. Ces réglages vous permettent de diviser les données en plusieurs fichiers, d’identifier chaque segment et de vérifier l’intégrité.

```csharp
    // Step 4: Macro‑specific layout
    barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 5;                     // Number of columns per row
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;    // Unique file identifier
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;       // Current segment number
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20; // Total number of segments
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";
```

*Pourquoi c’est important* : La propriété `Columns` influence la largeur du code-barres, tandis que les champs macro (`FileID`, `SegmentID`, `SegmentsCount`, `FileName`) permettent aux systèmes en aval de réassembler correctement les données originales.

## Étape 5 : Ajouter des métadonnées macro supplémentaires

Aspose.BarCode vous permet d’intégrer des champs macro optionnels tels que le checksum, la taille du fichier, l’horodatage et les informations d’expéditeur/récepteur. Ces champs sont utiles pour les pistes d’audit et la détection d’erreurs.

```csharp
    // Step 5: Optional macro metadata
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234;                 // CCITT‑16 example
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400_000;              // Approximate size in bytes
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = 
        new DateTime(2019, 11, 1);                                                       // Creation date
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = 
        Pdf417MacroTerminator.Set;                                                       // Marks the last segment
```

*Pourquoi c’est important* : Le checksum protège contre les erreurs de transmission, tandis que l’horodatage et les champs d’expéditeur offrent un contexte pour le traitement en aval. Définir `MacroPdf417Terminator` à `Set` indique que c’est le segment final de la série macro.

## Étape 6 : Enregistrer le code-barres en tant qu’image PNG

Enfin, écrivez le code-barres généré sur le disque. Le format PNG conserve une qualité sans perte, ce qui est idéal pour la lecture.

```csharp
    // Step 6: Export the barcode
    string outputPath = Path.Combine(Environment.CurrentDirectory, "ExtPDF417Meta.png");
    barcodeGenerator.Save(outputPath, BarCodeImageFormat.Png);
}
```

Lorsque le code se termine, le fichier `ExtPDF417Meta.png` contient un code-barres MacroPdf417 haute résolution qui encode le texte personnalisé et toutes les métadonnées macro.

### Résultat attendu

L’ouverture de `ExtPDF417Meta.png` montre un code-barres orienté verticalement avec des lignes et colonnes clairement définies. La lecture de l’image avec n’importe quel lecteur PDF417 renvoie la chaîne originale **Åspóse.Barcóde©** ainsi que les champs macro que vous avez configurés (ID de fichier, ID de segment, checksum, etc.).

## Comment générer pdf417 sans options macro (scénario alternatif)

Si vous avez uniquement besoin d’un code-barres PDF417 standard, omettez les propriétés macro et conservez la configuration de base :

```csharp
using (BarcodeGenerator generator = new BarcodeGenerator(
           EncodeTypes.Pdf417, "Standard PDF417 data"))
{
    generator.Parameters.Barcode.XDimension.Pixels = 3;
    generator.Parameters.Barcode.Pdf417.Columns = 6;
    generator.Save("StandardPdf417.png", BarCodeImageFormat.Png);
}
```

Cet extrait montre **comment générer pdf417** rapidement lorsque la fonctionnalité macro n’est pas requise.

## Pièges courants et astuces professionnelles

| Problème | Pourquoi cela se produit | Solution |
|----------|--------------------------|----------|
| Le code-barres est trop petit pour être scanné | X‑dimension définie à 1 pixel ou colonnes trop élevées | Utilisez au moins `2` pixels pour `XDimension` et maintenez les colonnes entre `3` et `9` pour les tailles d’étiquettes typiques |
| Les caractères Unicode apparaissent comme � | Incohérence d’encodage dans le fichier du projet | Assurez‑vous que le fichier du projet est enregistré en UTF‑8 et que le fichier source contient le BOM correct |
| Les champs macro sont ignorés par le scanner | `MacroPdf417Terminator` non défini pour le dernier segment | Définissez `MacroPdf417Terminator = Pdf417MacroTerminator.Set` sur le segment final |
| Le fichier image est corrompu | Le flux de sortie n’est pas correctement fermé | Utilisez l’instruction `using` (comme indiqué) pour garantir la libération du générateur |

## Exemple complet, exécutable

Copiez le code suivant dans une nouvelle application console et exécutez‑le. Le programme crée le code-barres, l’enregistre et affiche le chemin de sortie dans la console.

```csharp
using System;
using System.IO;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace AsposeBarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // Initialize the generator with custom Unicode text
            using (BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
                       EncodeTypes.MacroPdf417, "Åspóse.Barcóde©"))
            {
                // Basic size
                barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;

                // Macro layout
                barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 5;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";

                // Optional macro metadata
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400_000;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = new DateTime(2019, 11, 1);
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;

                // Save as PNG
                string outputFile = Path.Combine(Environment.CurrentDirectory, "ExtPDF417Meta.png");
                barcodeGenerator.Save(outputFile, BarCodeImageFormat.Png);

                Console.WriteLine($"Barcode saved to: {outputFile}");
            }
        }
    }
}
```

L’exécution du programme affiche une ligne similaire à :

```
Barcode saved to: C:\YourProject\bin\Debug\net6.0\ExtPDF417Meta.png
```

Ouvrez le fichier pour vérifier le rendu visuel.

## Conclusion

Vous savez maintenant comment **générer un code-barres aspose** pour la symbologie MacroPdf417, intégrer du texte Unicode personnalisé, configurer les métadonnées macro et exporter le résultat en image PNG. Le même modèle vous permet **de générer pdf417** sans options macro, et vous pouvez adapter le code à d’autres formats de code‑barres pris en charge par Aspose.BarCode.

Ensuite, explorez des sujets connexes tels que **créer un texte de code‑barres personnalisé** pour les QR codes, ajouter des filtres de couleur avec les paramètres `Color`, ou intégrer des codes‑barres directement dans des documents PDF à l’aide d’Aspose.PDF. Expérimentez avec différentes valeurs `XDimension` et différents nombres de colonnes pour ajuster finement le code‑barres à votre imprimante ou scanner spécifique.

Bon codage, et profitez de la fiabilité qu’Aspose.BarCode apporte à vos solutions de code‑barres .NET !

## Que devriez‑vous apprendre ensuite ?

Les tutoriels suivants couvrent des sujets étroitement liés qui s’appuient sur les techniques démontrées dans ce guide. Chaque ressource comprend des exemples de code complets et fonctionnels avec des explications étape par étape pour vous aider à maîtriser des fonctionnalités API supplémentaires et à explorer des approches d’implémentation alternatives dans vos propres projets.

- [Comment créer un code‑barres – PDF417 compact avec Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [Comment générer un code‑barres DataMatrix avec Aspose.BarCode pour .NET](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-macro-configuration/)
- [Générer un code‑barres Java – définir le texte du code avec Aspose.BarCode](/barcode/english/java/text-and-styling/setting-code-text/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}