---
category: general
date: 2026-09-22
description: Créer un code‑barres macro PDF417 avec Aspose.BarCode en C#. Apprenez
  étape par étape comment générer le code‑barres avec Aspose, configurer les métadonnées
  et l’enregistrer au format PNG.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create macro PDF417 barcode
- generate barcode with Aspose
- Aspose.BarCode PDF417
- C# barcode generation
- barcode metadata configuration
language: fr
lastmod: 2026-09-22
og_description: Créer un code‑barres macro PDF417 avec Aspose.BarCode en C#. Ce guide
  vous montre comment générer le code‑barres avec Aspose, définir les métadonnées
  macro et exporter l’image.
og_image_alt: Screenshot of a created macro PDF417 barcode using Aspose.BarCode in
  C#
og_title: Créer un code‑barres macro PDF417 avec Aspose.BarCode (C#) – guide étape
  par étape
schemas:
- author: Aspose
  dateModified: '2026-09-22'
  description: Create macro PDF417 barcode using Aspose.BarCode in C#. Learn step‑by‑step
    how to generate barcode with Aspose, configure metadata, and save as PNG.
  headline: Create macro PDF417 barcode with Aspose.BarCode (C#)
  type: TechArticle
tags:
- Aspose
- PDF417
- C#
- Barcode
title: Créer un code-barres macro PDF417 avec Aspose.BarCode (C#)
url: /fr/net/compact-pdf417-encoding/create-macro-pdf417-barcode-with-aspose-barcode-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Créer un code-barres macro PDF417 avec Aspose.BarCode (C#)

Si vous devez **créer un code-barres macro PDF417** dans une application .NET, ce tutoriel vous montre exactement comment le faire avec Aspose.BarCode. Vous verrez un exemple complet et exécutable qui **génère un code-barres avec Aspose**, configure tous les champs spécifiques aux macros et enregistre le résultat sous forme d'image PNG.

Les codes-barres sont souvent utilisés pour l'inventaire, l'expédition ou le suivi de documents, et la variante Macro PDF417 vous permet d'intégrer des métadonnées supplémentaires au niveau du fichier directement dans le code-barres. À la fin de ce guide, vous serez capable de générer un code-barres macro PDF417 complet qui respecte la norme ISO/IEC 15438.

## Ce dont vous avez besoin

Avant de commencer, assurez‑vous d'avoir :

* .NET 6.0 SDK ou version ultérieure (le code fonctionne avec .NET Core et .NET Framework)
* Visual Studio 2022 (ou tout IDE C#)
* Une connexion Internet compatible NuGet pour récupérer le package Aspose.BarCode
* Une connaissance de base de la syntaxe C#

Ces prérequis garantissent que le code se compile sans configuration supplémentaire.

## Étape 1 : Installer le package NuGet Aspose.BarCode

La bibliothèque Aspose.BarCode fournit la classe `BarcodeGenerator` utilisée tout au long de ce tutoriel.

```bash
dotnet add package Aspose.BarCode
```

L'exécution de la commande ajoute la dernière version stable à votre fichier de projet (`*.csproj`). Le package inclut la prise en charge de PDF417, Macro PDF417 et de nombreuses autres symbologies.

## Étape 2 : Créer un nouveau projet console (optionnel)

Si vous préférez repartir de zéro, générez une application console :

```bash
dotnet new console -n MacroPdf417Demo
cd MacroPdf417Demo
```

Le fichier `Program.cs` généré contiendra le code de génération du code‑barres.

## Étape 3 : Initialiser le générateur de code‑barres

Le générateur est créé avec la valeur d'énumération `EncodeTypes.MacroPdf417` et le texte que vous souhaitez encoder. Aspose.BarCode gère automatiquement les caractères Unicode, vous pouvez donc inclure directement des lettres accentuées ou des symboles.

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;
using System;

class Program
{
    static void Main()
    {
        // Step 3: Create a Macro PDF417 barcode generator with the desired text
        using (var barcodeGenerator = new BarcodeGenerator(EncodeTypes.MacroPdf417, "Åspóse.Barcóde©"))
        {
            // The rest of the configuration follows...
```

### Pourquoi c’est important
`EncodeTypes.MacroPdf417` indique à la bibliothèque d'utiliser la version macro de PDF417, ce qui ajoute la capacité d'incorporer des métadonnées au niveau du fichier (ID du fichier, nombre de segments, etc.). Le texte `"Åspóse.Barcóde©"` montre que le générateur encode correctement les caractères UTF‑8.

## Étape 4 : Définir les dimensions de base du code‑barres

PDF417 vous permet de contrôler le nombre de colonnes et la dimension X (la largeur d'un module unique). Ajuster ces valeurs influence la taille physique du code‑barres et la fiabilité de la lecture.

```csharp
            // Step 4: Set basic barcode dimensions
            barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;   // module width in pixels
            barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 5;    // number of columns
```

* **XDimension** – Des valeurs plus petites produisent un code‑barres plus dense ; des valeurs plus grandes facilitent la lecture avec des scanners basse résolution.
* **Columns** – Contrôle le nombre de colonnes de données ; les valeurs typiques vont de 1 à 30.

## Étape 5 : Configurer les métadonnées Macro PDF417

Macro PDF417 comporte des champs supplémentaires qui décrivent le fichier que représente le code‑barres. Chaque champ est optionnel, mais les définir améliore l'interopérabilité avec les scanners qui comprennent le format macro.

```csharp
            // Step 5: Configure Macro PDF417 metadata
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234; // demo checksum
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400_000; // bytes
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = new DateTime(2019, 11, 1);
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;
```

### Explication de chaque champ

| Propriété | Objectif | Plage typique |
|-----------|----------|---------------|
| **MacroPdf417FileID** | Identifiant unique du fichier logique qui peut être réparti sur plusieurs codes‑barres. | 0‑2³²‑1 |
| **MacroPdf417SegmentID** | Indice du segment actuel (commence à 0). | 0‑(SegmentsCount‑1) |
| **MacroPdf417SegmentsCount** | Nombre total de segments qui composent le fichier complet. | 1‑99 |
| **MacroPdf417FileName** | Nom du fichier lisible par l'homme. | Up to 255 characters |
| **MacroPdf417Checksum** | Somme de contrôle optionnelle pour la détection d'erreurs. | 0‑65535 |
| **MacroPdf417FileSize** | Taille du fichier original en octets. | 0‑2³²‑1 |
| **MacroPdf417TimeStamp** | Horodatage de la création ou de la modification du fichier. | Any `DateTime` |
| **MacroPdf417Addressee** | Identifiant du destinataire (par ex., service ou machine). | Free‑form string |
| **MacroPdf417Sender** | Identifiant de l'origine (par ex., nom de l'entreprise). | Free‑form string |
| **MacroPdf417Terminator** | Indique si ce segment est le dernier. | `Set` or `Unset` |

**Astuce :** Si vous divisez un gros fichier en plusieurs codes‑barres, assurez‑vous que le `SegmentID` de chaque segment soit séquentiel et que le `SegmentsCount` reste constant pour tous les segments. Les scanners s’appuient sur ces valeurs pour reconstruire le fichier original.

## Étape 6 : Enregistrer l’image du code‑barres

Aspose.BarCode prend en charge de nombreux formats de sortie (PNG, JPEG, BMP, SVG, etc.). PNG offre une qualité sans perte, idéale pour les tests et la documentation.

```csharp
            // Step 6: Save the barcode image as PNG
            barcodeGenerator.Save("ExtPDF417Meta.png", BarCodeImageFormat.Png);
        }
    }
}
```

L'exécution du programme crée un fichier nommé `ExtPDF417Meta.png` dans le répertoire de sortie du projet (`bin/Debug/net6.0/`). Ouvrez l'image avec n'importe quel visualiseur pour vérifier que le code‑barres s'affiche correctement.

## Étape 7 : Vérifier le code‑barres généré (optionnel)

Si vous disposez d'une application de lecture PDF417 (mobile ou de bureau), scannez le PNG enregistré. Le scanner doit renvoyer :

* Le texte encodé `"Åspóse.Barcóde©`
* Tous les champs macro que vous avez configurés (ID du fichier, ID du segment, etc.)

Pour une vérification automatisée, Aspose.BarCode propose également la classe `BarCodeReader` :

```csharp
using Aspose.BarCode.BarCodeRecognition;

// ...

using (var reader = new BarCodeReader("ExtPDF417Meta.png", DecodeType.Pdf417))
{
    foreach (BarCodeResult result in reader.ReadBarCodes())
    {
        Console.WriteLine($"Text: {result.CodeText}");
        Console.WriteLine($"Macro File ID: {result.GetMacroPdf417FileID()}");
        // Access other macro properties similarly
    }
}
```

Cet extrait montre comment lire les métadonnées macro programmatiquement, confirmant que **générer un code‑barres avec Aspose** fonctionne de bout en bout.

## Cas limites et bonnes pratiques

| Situation | Gestion recommandée |
|-----------|----------------------|
| **Unicode characters** | Assurez‑vous que la chaîne source est en UTF‑8 (défaut dans .NET). Aspose.BarCode encode automatiquement l'Unicode, mais vérifiez le jeu de caractères du scanner. |
| **Large file size** | Macro PDF417 divise les fichiers en jusqu'à 99 segments. Si le fichier dépasse 400 KB, augmentez `SegmentsCount` et générez plusieurs codes‑barres, chacun avec un `SegmentID` séquentiel. |
| **Timestamp precision** | Utilisez `DateTime.UtcNow` pour le temps universel ; certains scanners attendent l'UTC. |
| **Checksum validation** | Fournissez une somme de contrôle correcte si vous prévoyez de valider l'intégrité côté réception. |
| **Different image formats** | Utilisez `BarCodeImageFormat.Svg` pour les graphiques vectoriels lorsque vous avez besoin de codes‑barres évolutifs à l'infini. |
| **Performance** | Réutilisez une seule instance de `BarcodeGenerator` lors de la génération de nombreux codes‑barres ; ne modifiez que les `Parameters` entre les itérations. |

## Exemple complet et exécutable

Voici le programme complet que vous pouvez copier, coller et exécuter sans modification (en supposant que le package NuGet est installé).



## Que devriez‑vous apprendre ensuite ?

Les tutoriels suivants couvrent des sujets étroitement liés qui s'appuient sur les techniques démontrées dans ce guide. Chaque ressource comprend des exemples de code complets et fonctionnels avec des explications étape par étape pour vous aider à maîtriser des fonctionnalités API supplémentaires et explorer des approches d'implémentation alternatives dans vos propres projets.

- [Exemple de code‑barres Aspose : générer Macro PDF417 en C#](/barcode/english/net/compact-pdf417-encoding/aspose-barcode-example-generate-macro-pdf417-in-c/)
- [Créer des métadonnées de code‑barres PDF417 en C# – Guide complet étape par étape](/barcode/english/net/compact-pdf417-encoding/create-pdf417-barcode-metadata-in-c-complete-step-by-step-gu/)
- [Comment générer une image de code‑barres PDF417 en C# avec Aspose](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-image-in-c-with-aspose/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}