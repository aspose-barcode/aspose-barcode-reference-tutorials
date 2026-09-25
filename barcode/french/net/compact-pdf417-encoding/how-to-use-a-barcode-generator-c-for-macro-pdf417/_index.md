---
category: general
date: 2026-08-22
description: Le tutoriel du générateur de codes-barres C# montre comment créer un
  code-barres Macro PDF417 avec des métadonnées et l’enregistrer au format PNG à l’aide
  d’Aspose.BarCode.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- barcode generator C#
- Macro PDF417
- Aspose.BarCode
- C# barcode library
- PDF417 barcode
- barcode metadata
language: fr
lastmod: 2026-08-22
og_description: Le générateur de code‑barres C# vous permet de créer un code‑barres
  Macro PDF417 avec des métadonnées complètes au niveau du fichier et de l’exporter
  au format PNG. Suivez ce guide pour mettre en œuvre la solution.
og_image_alt: Screenshot of a Macro PDF417 barcode generated with C#
og_title: générateur de code-barres C# – créer des codes-barres Macro PDF417 étape
  par étape
schemas:
- author: Aspose
  dateModified: '2026-08-22'
  description: barcode generator C# tutorial shows how to create a Macro PDF417 barcode
    with metadata and save it as PNG using Aspose.BarCode.
  headline: How to use a barcode generator C# for Macro PDF417
  type: TechArticle
tags:
- barcode
- C#
- PDF417
title: Comment utiliser un générateur de code‑barres C# pour Macro PDF417
url: /fr/net/compact-pdf417-encoding/how-to-use-a-barcode-generator-c-for-macro-pdf417/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Comment utiliser un générateur de code-barres C# pour Macro PDF417

Si vous avez besoin d'un **barcode generator C#** capable d'émettre un symbole Macro PDF417 avec des métadonnées au niveau du fichier, ce guide fournit une solution complète, prête à l'emploi. Vous verrez comment configurer l'apparence du code-barres, intégrer les informations macro telles que l'ID du fichier et le nombre de segments, puis enregistrer le résultat sous forme d'image PNG.

L'exemple utilise la bibliothèque Aspose.BarCode, une **C# barcode library** largement adoptée qui prend en charge l'ensemble complet des fonctionnalités PDF417. Aucun service externe n'est requis, et le code fonctionne avec .NET 6 ou une version ultérieure.

## Prérequis

* .NET 6 SDK (ou toute version ultérieure) installé.
* Visual Studio 2022, VS Code, ou un autre IDE C#.
* Une référence NuGet à **Aspose.BarCode** (`dotnet add package Aspose.BarCode`).

Comprendre la syntaxe de base du C# et le concept des codes-barres PDF417 vous aidera à suivre les étapes, mais le tutoriel explique chaque option de configuration en détail.

## Ce que couvre le tutoriel

* Initialisation d'une instance de **barcode generator C#** pour le format Macro PDF417.  
* Ajustement des paramètres visuels tels que la dimension X et le nombre de colonnes.  
* Fourniture des champs de niveau fichier Macro PDF417 : ID du fichier, ID du segment, nombre de segments, nom du fichier, somme de contrôle, taille du fichier, horodatage, destinataire, expéditeur et indicateur de terminaison.  
* Enregistrement du symbole généré sous forme de fichier PNG.  
* Conseils pour gérer les cas limites comme les tailles de fichier importantes ou les horodatages personnalisés.

À la fin de cet article, vous disposerez d'un programme autonome qui génère un code-barres Macro PDF417 entièrement conforme.

## Étape 1 : Créer l'instance du barcode generator C#

La première opération consiste à instancier `BarcodeGenerator` avec la valeur d'énumération `EncodeTypes.MacroPdf417` et le texte que vous souhaitez encoder. Le constructeur accepte également la chaîne de charge utile, qui devient la partie données du code-barres macro.

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;

// Step 1: Create a barcode generator for Macro PDF417
using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.MacroPdf417, "Sample text"))
{
    // Subsequent configuration goes here
}
```

**Pourquoi c'est important** – Le drapeau `EncodeTypes.MacroPdf417` indique à Aspose.BarCode de traiter le symbole comme un code-barres macro, activant les champs supplémentaires qui suivent. Sans ce drapeau, la bibliothèque générerait un code-barres PDF417 ordinaire sans métadonnées au niveau du fichier.

## Étape 2 : Ajuster l'apparence de base du code-barres (paramètres visuels PDF417)

La clarté visuelle est cruciale pour une lecture fiable. Deux paramètres courants sont la largeur du module (`XDimension`) et le nombre de colonnes. Le réglage de ces valeurs équilibre la taille et la lisibilité.

```csharp
    // Step 2: Adjust basic barcode appearance
    generator.Parameters.Barcode.XDimension.Pixels = 2;   // width of a single module
    generator.Parameters.Barcode.Pdf417.Columns = 5;    // number of columns in the symbol
```

- `XDimension.Pixels` contrôle la largeur de chaque barre noire/blanche. Une valeur de **2** fonctionne bien pour la plupart des imprimantes d'étiquettes.
- `Pdf417.Columns` définit le nombre de colonnes utilisées par le code-barres. Cinq colonnes produisent un symbole compact sans sacrifier la capacité de données.

## Étape 3 : Définir les informations de niveau fichier Macro PDF417

Macro PDF417 étend le format PDF417 standard avec des champs décrivant comment un gros fichier est découpé en plusieurs segments de code-barres. Fournir ces champs garantit que les lecteurs en aval peuvent reconstruire le fichier original.

```csharp
    // Step 3: Define Macro PDF417 file‑level information
    generator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;          // unique file identifier
    generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;            // current segment number (0‑indexed)
    generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;       // total number of segments
    generator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";      // optional logical file name
```

- `MacroPdf417FileID` doit être identique pour chaque segment appartenant au même fichier logique.
- `MacroPdf417SegmentID` s'incrémente de **0** à `SegmentsCount‑1`.
- `MacroPdf417SegmentsCount` indique au décodeur combien de pièces attendre.
- `MacroPdf417FileName` est optionnel mais utile pour une identification lisible par l'homme.

## Étape 4 : Définir les métadonnées macro supplémentaires

Au-delà des informations de base du fichier, la spécification autorise des champs supplémentaires tels que la somme de contrôle, la taille du fichier, l'horodatage, le destinataire, l'expéditeur et un indicateur de terminaison. Remplir ces champs améliore l'intégrité des données et la traçabilité.

```csharp
    // Step 4: Set additional macro metadata
    generator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234;                     // CCITT‑16 checksum
    generator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400_000;                  // file size in bytes
    generator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = new DateTime(2024, 4, 1);
    generator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
    generator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
    generator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;
```

- `MacroPdf417Checksum` fournit une somme de contrôle CCITT de 16 bits pour l'ensemble du fichier ; le décodeur peut vérifier l'intégrité après reconstruction.
- `MacroPdf417FileSize` doit refléter le nombre exact d'octets du fichier original ; les valeurs supérieures à `2^31‑1` nécessitent un champ de 64 bits, que Aspose gère automatiquement.
- `MacroPdf417TimeStamp` enregistre le moment où le code-barres a été généré. Utilisez l'UTC pour éviter toute ambiguïté de fuseau horaire.
- `MacroPdf417Addressee` et `MacroPdf417Sender` sont des chaînes libres pouvant stocker des informations de routage.
- `MacroPdf417Terminator` indique qu'il s'agit du segment final ; réglez-le sur `Set` pour le dernier morceau, sinon laissez la valeur par défaut (`NotSet`).

**Astuce pour les cas limites** – Si la taille de votre fichier dépasse 4 Go, divisez le contenu en plusieurs segments macro et ajustez `SegmentsCount` en conséquence. La bibliothèque gérera le champ de grande taille sans débordement.

## Étape 5 : Enregistrer le code-barres en image PNG

La dernière étape écrit le symbole généré sur le disque. PNG préserve les dimensions exactes des pixels et est largement supporté par le matériel de lecture.

```csharp
    // Step 5: Save the generated barcode as a PNG image
    generator.Save("YOUR_DIRECTORY/MacroPdf417.png", BarCodeImageFormat.Png);
}
```

Remplacez `YOUR_DIRECTORY` par un chemin absolu ou relatif auquel le processus d'exécution peut écrire. L'énumération `BarCodeImageFormat.Png` garantit une sortie sans perte.

**Pourquoi PNG ?** – Les formats raster comme PNG conservent les bords des modules nets, ce qui est essentiel pour les lecteurs qui s'appuient sur des bords à fort contraste. Si vous avez besoin d'un format vectoriel, Aspose prend également en charge `Pdf` et `Svg`.

## Exemple complet exécutable

Voici le programme complet que vous pouvez copier dans une application console. Il inclut les directives `using` nécessaires et une méthode `Main`.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace MacroPdf417Demo
{
    class Program
    {
        static void Main()
        {
            // Create a barcode generator for Macro PDF417 with sample payload
            using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.MacroPdf417, "Sample text"))
            {
                // Adjust visual appearance
                generator.Parameters.Barcode.XDimension.Pixels = 2;
                generator.Parameters.Barcode.Pdf417.Columns = 5;

                // Define macro file‑level fields
                generator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
                generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;
                generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;
                generator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";

                // Add optional metadata
                generator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234;
                generator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400_000;
                generator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = new DateTime(2024, 4, 1);
                generator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
                generator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
                generator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;

                // Export to PNG
                generator.Save("MacroPdf417.png", BarCodeImageFormat.Png);
            }

            Console.WriteLine("Macro PDF417 barcode generated successfully.");
        }
    }
}
```

### Résultat attendu

L'exécution du programme crée un fichier nommé **MacroPdf417.png** dans le répertoire de travail du projet. L'ouverture de l'image montre un code-barres PDF417 compact avec les champs macro intégrés. Scanner l'image avec un lecteur compatible PDF417 (par ex., ZXing, le décodeur Aspose.BarCode) renvoie la charge utile originale `"Sample text"` ainsi que les métadonnées macro.

## Questions fréquentes et dépannage

| Question | Réponse |
|----------|--------|
| *Et si le code-barres est trop grand pour l'étiquette cible ?* | Réduisez `XDimension.Pixels` ou augmentez `Pdf417.Columns`. Les deux paramètres influent sur la taille globale. |
| *Puis-je générer une image vectorielle au lieu de PNG ?* | Oui. Appelez `generator.Save("MacroPdf417.svg", BarCodeImageFormat.Svg);` pour une sortie évolutive. |
| *Comment vérifier la somme de contrôle après le scan ?* | Le décodeur Aspose.BarCode valide automatiquement `MacroPdf417Checksum` et signale les incohérences dans l'objet `MacroPdf417Result`. |
| *La bibliothèque est‑elle compatible avec .NET Core ?* | Le package NuGet prend en charge .NET Standard 2.0+, qui couvre .NET Core, .NET 5, .NET 6 et les versions ultérieures. |
| *Et si je dois intégrer des données binaires au lieu de texte ?* | Convertissez la charge binaire en Base64 ou utilisez la surcharge `EncodeTypes.MacroPdf417` qui accepte un tableau d'octets. |

## Astuces professionnelles pour la production

* **Mettre en cache le générateur** –

## Que devriez‑vous apprendre ensuite ?

Les tutoriels suivants couvrent des sujets étroitement liés qui s'appuient sur les techniques démontrées dans ce guide. Chaque ressource comprend des exemples de code complets et fonctionnels avec des explications étape par étape pour vous aider à maîtriser des fonctionnalités API supplémentaires et explorer des approches d'implémentation alternatives dans vos propres projets.

- [Comment créer un code-barres – PDF417 compact avec Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [Comment lire un code-barres depuis un PDF en Java avec Aspose.BarCode](/barcode/english/java/document-barcode-recognition/recognizing-barcodes-from-pdf/)
- [Créer un code-barres Codabar avec Aspose.Barcode – API Générateur & Lecteur](/barcode/english/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}