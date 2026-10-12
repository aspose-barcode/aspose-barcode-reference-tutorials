---
category: general
date: 2026-09-19
description: Comment décoder le PDF417 en C# – apprenez à lire les codes‑barres à
  partir d’une image en utilisant un exemple concis de lecteur de codes‑barres qui
  extrait les données complètes du Macro PDF417.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to decode pdf417
- read barcodes from image
- decode pdf417 barcode
- c# barcode reader example
language: fr
lastmod: 2026-09-19
og_description: Comment décoder le PDF417 en C# avec un exemple de lecteur de code‑barres
  pas à pas. Extraire chaque champ Macro PDF417 d’une image en quelques secondes.
og_image_alt: Screenshot showing how to decode PDF417 in C# using a barcode reader
og_title: Comment décoder le PDF417 en C# – guide complet du lecteur de codes‑barres
schemas:
- author: Aspose
  dateModified: '2026-09-19'
  description: How to decode PDF417 in C# – learn to read barcodes from image using
    a concise barcode reader example that extracts full Macro PDF417 data.
  headline: How to decode PDF417 in C# with a barcode reader example
  type: TechArticle
tags:
- barcode
- pdf417
- csharp
title: Comment décoder le PDF417 en C# avec un exemple de lecteur de code-barres
url: /fr/net/compact-pdf417-encoding/how-to-decode-pdf417-in-c-with-a-barcode-reader-example/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Comment décoder le PDF417 en C# avec un exemple de lecteur de code‑barres

Si vous devez décoder le PDF417 en C#, ce guide vous montre exactement comment décoder le PDF417 à partir d’un fichier image. Vous apprendrez à lire les codes‑barres depuis une image, à accéder aux champs Macro PDF417 étendus, et à intégrer la solution dans n’importe quel projet .NET.

Le décodage des codes‑barres PDF417 est courant dans la logistique, la billetterie et la vérification d’identité. Ce tutoriel couvre tout ce qui est nécessaire pour une implémentation prête pour la production, y compris les bibliothèques prérequises, le code source complet et des astuces pour gérer les cas limites.

## Prérequis

Avant de commencer, assurez‑vous d’avoir :

- .NET 6.0 ou version ultérieure installé  
- Visual Studio 2022 (ou tout IDE supportant C#)  
- Le package NuGet **Aspose.BarCode for .NET** (version 23.11 ou plus récente)  

Vous pouvez ajouter le package avec la commande suivante :

```bash
dotnet add package Aspose.BarCode
```

La classe `BarCodeReader` de cette bibliothèque prend en charge le type de décodage `MacroPdf417` nécessaire pour une extraction complète du PDF417.

## Étape 1 : Comment décoder le PDF417 en C# – initialiser le lecteur

La première étape crée une instance `BarCodeReader` qui cible une image Macro PDF417. Le drapeau `DecodeType.MacroPdf417` indique à la bibliothèque d’analyser les champs Macro étendus.

```csharp
using System;
using Aspose.BarCode;               // Core barcode classes
using Aspose.BarCode.BarCodeRecognition; // Reader and result types

// Path to the Macro PDF417 image
string imagePath = @"YOUR_DIRECTORY\MacroPdf417.png";

// Initialise the reader for Macro PDF417 decoding
using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
{
    // Continue with step 2...
```

**Pourquoi c’est important :** L’initialisation avec `MacroPdf417` active la propriété `Extended.Pdf417` sur chaque `BarCodeResult`, vous donnant accès aux métadonnées de niveau fichier telles que les identifiants de segment et les horodatages.

## Étape 2 : Lire les codes‑barres depuis l’image

Une image PDF417 peut contenir plusieurs segments macro. La méthode `ReadBarCodes()` renvoie un ensemble de tous les codes‑barres détectés, vous permettant de les parcourir en toute sécurité.

```csharp
    // Step 2: Read every barcode present in the image
    foreach (BarCodeResult result in reader.ReadBarCodes())
    {
        // Continue with step 3...
```

**Astuce :** Si vous ne prévoyez qu’un seul code‑barres, vous pouvez sortir de la boucle après la première itération, mais parcourir tous les résultats garantit que vous capturez chaque segment dans les documents multi‑pages.

## Étape 3 : Décoder le code‑barres PDF417 – extraire les données de base et étendues

À l’intérieur de la boucle, affichez à la fois les informations génériques du code‑barres et les champs spécifiques au Macro. L’objet `Extended.Pdf417` contient chaque métadonnée définie par la norme PDF417.

```csharp
        // Basic barcode information
        Console.WriteLine($"CodeType: {result.CodeTypeName}");
        Console.WriteLine($"CodeText: {result.CodeText}");

        // Macro PDF417 extended data
        Console.WriteLine($"Pdf417MacroFileID: {result.Extended.Pdf417.MacroPdf417FileID}");
        Console.WriteLine($"Pdf417MacroSegmentID: {result.Extended.Pdf417.MacroPdf417SegmentID}");
        Console.WriteLine($"Pdf417MacroSegmentsCount: {result.Extended.Pdf417.MacroPdf417SegmentsCount}");
        Console.WriteLine($"Pdf417MacroFileName: {result.Extended.Pdf417.MacroPdf417FileName}");
        Console.WriteLine($"Pdf417MacroChecksum: {result.Extended.Pdf417.MacroPdf417Checksum}");
        Console.WriteLine($"Pdf417MacroFileSize: {result.Extended.Pdf417.MacroPdf417FileSize}");
        Console.WriteLine($"Pdf417MacroTimeStamp: {result.Extended.Pdf417.MacroPdf417TimeStamp}");
        Console.WriteLine($"Pdf417MacroAddressee: {result.Extended.Pdf417.MacroPdf417Addressee}");
        Console.WriteLine($"Pdf417MacroSender: {result.Extended.Pdf417.MacroPdf417Sender}");
        Console.WriteLine($"MacroPdf417Terminator: {result.Extended.Pdf417.MacroPdf417Terminator}");
    }
}
```

**Explication des champs clés**

| Champ | Signification |
|-------|----------------|
| `MacroPdf417FileID` | Identifiant qui regroupe tous les segments appartenant au même fichier logique |
| `MacroPdf417SegmentID` | Index du segment actuel (commence à 0) |
| `MacroPdf417SegmentsCount` | Nombre total de segments attendus pour le fichier |
| `MacroPdf417FileName` | Nom de fichier optionnel intégré dans le macro |
| `MacroPdf417Checksum` | Somme de contrôle CRC‑16 pour l’intégrité des données |
| `MacroPdf417FileSize` | Taille originale du fichier en octets |
| `MacroPdf417TimeStamp` | Horodatage de génération du macro |
| `MacroPdf417Addressee` | Destinataire prévu des données du macro |
| `MacroPdf417Sender` | Émetteur des données du macro |
| `MacroPdf417Terminator` | Indicateur booléen signalant le segment final |

Avoir accès à ces champs vous permet de reconstruire le document original, de vérifier son intégrité ou de router les données en fonction des informations d’expéditeur/récepteur.

## Étape 4 : Exemple complet de lecteur de code‑barres C# – tout assembler

Voici le programme complet et exécutable. Remplacez `YOUR_DIRECTORY` par le dossier contenant votre fichier `MacroPdf417.png`.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

namespace Pdf417Decoder
{
    class Program
    {
        static void Main()
        {
            // Path to the image containing a Macro PDF417 barcode
            string imagePath = @"YOUR_DIRECTORY\MacroPdf417.png";

            // Initialise the reader for Macro PDF417 decoding
            using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
            {
                // Iterate through all detected barcodes
                foreach (BarCodeResult result in reader.ReadBarCodes())
                {
                    // Basic information
                    Console.WriteLine($"CodeType: {result.CodeTypeName}");
                    Console.WriteLine($"CodeText: {result.CodeText}");

                    // Extended Macro PDF417 data
                    Console.WriteLine($"Pdf417MacroFileID: {result.Extended.Pdf417.MacroPdf417FileID}");
                    Console.WriteLine($"Pdf417MacroSegmentID: {result.Extended.Pdf417.MacroPdf417SegmentID}");
                    Console.WriteLine($"Pdf417MacroSegmentsCount: {result.Extended.Pdf417.MacroPdf417SegmentsCount}");
                    Console.WriteLine($"Pdf417MacroFileName: {result.Extended.Pdf417.MacroPdf417FileName}");
                    Console.WriteLine($"Pdf417MacroChecksum: {result.Extended.Pdf417.MacroPdf417Checksum}");
                    Console.WriteLine($"Pdf417MacroFileSize: {result.Extended.Pdf417.MacroPdf417FileSize}");
                    Console.WriteLine($"Pdf417MacroTimeStamp: {result.Extended.Pdf417.MacroPdf417TimeStamp}");
                    Console.WriteLine($"Pdf417MacroAddressee: {result.Extended.Pdf417.MacroPdf417Addressee}");
                    Console.WriteLine($"Pdf417MacroSender: {result.Extended.Pdf417.MacroPdf417Sender}");
                    Console.WriteLine($"MacroPdf417Terminator: {result.Extended.Pdf417.MacroPdf417Terminator}");
                    Console.WriteLine(new string('-', 40));
                }
            }

            Console.WriteLine("Decoding complete.");
        }
    }
}
```

**Sortie console attendue (exemple)**

```
CodeType: MacroPdf417
CodeText: https://example.com/document.pdf
Pdf417MacroFileID: 12
Pdf417MacroSegmentID: 0
Pdf417MacroSegmentsCount: 3
Pdf417MacroFileName: document.pdf
Pdf417MacroChecksum: 0x1A2B
Pdf417MacroFileSize: 452312
Pdf417MacroTimeStamp: 2024-03-15T14:27:00Z
Pdf417MacroAddressee: LogisticsDept
Pdf417MacroSender: Warehouse01
MacroPdf417Terminator: False
----------------------------------------
Decoding complete.
```

Les valeurs exactes varieront en fonction du contenu de votre code‑barres Macro PDF417.

## Gestion des cas limites courants

| Situation | Approche recommandée |
|-----------|----------------------|
| **Aucun code‑barres détecté** | Vérifiez le chemin de l’image, assurez‑vous que le fichier n’est pas corrompu, et confirmez que le code‑barres est visible (contraste suffisant). |
| **Segments macro partiels** | Utilisez `MacroPdf417SegmentsCount` pour détecter les parties manquantes. Vous pouvez demander les segments restants au système source et relancer le décodage. |
| **Images volumineuses entraînant une pression mémoire** | Chargez l’image dans un `System.Drawing.Bitmap` avec une résolution réduite avant de la transmettre à `BarCodeReader`. |
| **PDF417 non‑Macro** | Changez `DecodeType.MacroPdf417` en `DecodeType.Pdf417` si vous n’avez besoin que du texte du code‑barres simple. |

## Astuces pro

- **Traitement par lots :** Encapsulez la logique du lecteur dans une méthode qui accepte une liste de chemins de fichiers. Réutilisez une seule instance `BarCodeReader` par thread pour réduire la surcharge d’allocation.  
- **Performance :** Pour les scénarios à haut débit, activez la propriété `ReaderOptions` `ReadQuality` afin d’équilibrer vitesse et précision.  
- **Sécurité :** Validez `CodeText` avant de l’utiliser dans des opérations système de fichiers afin d’éviter les attaques de traversée de chemin.

## Conclusion

Dans ce tutoriel, vous avez appris à décoder le PDF417 en C# en lisant les codes‑barres depuis une image, en extrayant chaque champ Macro PDF417, et en construisant un exemple complet de lecteur de code‑barres C#. La solution fonctionne avec la dernière version de la bibliothèque Aspose.BarCode, gère les macros multi‑segments et fournit des conseils pratiques pour des projets réels.

Ensuite, explorez des sujets connexes tels que **la lecture de QR codes**, **le traitement par lots de codes‑barres**, et **la génération de codes‑barres PDF417** pour élargir votre boîte à outils d’automatisation documentaire. N’hésitez pas à expérimenter avec différentes sources d’image, à intégrer le code dans des services ASP.NET, ou à l’étendre pour stocker les métadonnées extraites dans une base de données. Bon codage !

## Que devriez‑vous apprendre ensuite ?

Les tutoriels suivants couvrent des sujets étroitement liés qui s’appuient sur les techniques démontrées dans ce guide. Chaque ressource inclut des exemples de code fonctionnels complets avec des explications pas à pas pour vous aider à maîtriser des fonctionnalités API supplémentaires et à explorer des approches d’implémentation alternatives dans vos propres projets.

- [Comment lire le PDF417 en C# – Exemple complet de lecteur de code‑barres](/barcode/english/net/compact-pdf417-encoding/how-to-read-pdf417-in-c-complete-barcode-reader-example/)
- [Comment générer une image de code‑barres PDF417 en C# avec Aspose](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-image-in-c-with-aspose/)
- [Lire un code‑barres depuis une image – Exemple de lecteur de code‑barres C#](/barcode/english/net/one-dimensional-barcode-types/read-barcode-from-image-c-barcode-reader-example/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}