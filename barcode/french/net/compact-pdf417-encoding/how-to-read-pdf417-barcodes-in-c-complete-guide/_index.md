---
category: general
date: 2026-08-22
description: Comment lire les codes‑barres PDF417 en C# avec un guide étape par étape,
  couvrant la lecture de plusieurs codes‑barres à partir d’une image et l’extraction
  des détails MacroPdf417.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to read pdf417
- read multiple barcodes
- read barcodes image c#
language: fr
lastmod: 2026-08-22
og_description: Comment lire rapidement les codes‑barres PDF417 en C#. Ce tutoriel
  vous montre comment lire plusieurs codes‑barres à partir d’une image et récupérer
  les informations étendues MacroPdf417.
og_image_alt: Developer console displaying MacroPdf417 barcode details extracted by
  C# code
og_title: Comment lire les codes-barres PDF417 en C# – guide complet de programmation
schemas:
- author: Aspose
  dateModified: '2026-08-22'
  description: How to read PDF417 barcodes in C# with a step‑by‑step guide, covering
    how to read multiple barcodes from an image and extract MacroPdf417 details.
  headline: How to read PDF417 barcodes in C# – complete guide
  type: TechArticle
tags:
- barcode
- C#
- Aspose.BarCode
title: Comment lire les codes-barres PDF417 en C# – guide complet
url: /fr/net/compact-pdf417-encoding/how-to-read-pdf417-barcodes-in-c-complete-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Comment lire les codes-barres PDF417 en C# – guide complet

Si vous avez besoin de **comment lire les PDF417** dans une application .NET, ce tutoriel vous fournit une solution prête à l’emploi. Vous apprendrez à lire plusieurs codes-barres à partir d’une seule image, à extraire l’ensemble complet de données MacroPdf417, et à les afficher dans la console. L’approche fonctionne avec la bibliothèque Aspose.BarCode for .NET et ne nécessite que quelques lignes de code.

Lire des codes-barres à partir d’une image est une tâche courante dans les systèmes d’inventaire, la validation de billets et la gestion de documents. À la fin de ce guide, vous serez capable de décoder n’importe quel code-barres PDF417 ou MacroPdf417, de gérer plusieurs codes sur une même image, et de comprendre les champs étendus fournis par MacroPdf417.

## Prérequis

- .NET 6.0 SDK ou version ultérieure (le code compile également avec .NET Framework 4.7+)
- Visual Studio 2022 ou tout éditeur C# de votre choix
- Package NuGet Aspose.BarCode for .NET (`Install-Package Aspose.BarCode`)
- Une image d’exemple contenant un code-barres MacroPdf417 (par ex., `MacroPdf417.png`)

Aucune configuration supplémentaire n’est requise ; la bibliothèque gère le chargement et le décodage de l’image en interne.

## Comment lire les codes-barres PDF417 à partir d’une image en C#

Le cœur de la solution est la classe `BarCodeReader`. Elle ouvre l’image, détecte tous les codes-barres du type spécifié, et renvoie une collection d’objets `BarCodeResult`. Le code suivant montre un programme console complet.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

namespace Pdf417ReaderDemo
{
    class Program
    {
        static void Main()
        {
            // Path to the image that contains one or more MacroPdf417 barcodes
            const string imagePath = @"YOUR_DIRECTORY\MacroPdf417.png";

            // 1️⃣ Initialize the reader for MacroPdf417 barcodes.
            // DecodeType.MacroPdf417 tells the engine to look for the extended PDF417 format.
            using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
            {
                // 2️⃣ Iterate over every barcode found in the image.
                foreach (BarCodeResult result in reader.ReadBarCodes())
                {
                    // 3️⃣ Print basic information.
                    Console.WriteLine($"CodeType: {result.CodeTypeName}");
                    Console.WriteLine($"CodeText: {result.CodeText}");

                    // 4️⃣ Access MacroPdf417 extended fields.
                    // The Extended property contains format‑specific data; for PDF417 it is .Pdf417.
                    var macro = result.Extended.Pdf417;

                    Console.WriteLine($"Pdf417MacroFileID: {macro.MacroPdf417FileID}");
                    Console.WriteLine($"Pdf417MacroSegmentID: {macro.MacroPdf417SegmentID}");
                    Console.WriteLine($"Pdf417MacroSegmentsCount: {macro.MacroPdf417SegmentsCount}");
                    Console.WriteLine($"Pdf417MacroFileName: {macro.MacroPdf417FileName}");
                    Console.WriteLine($"Pdf417MacroChecksum: {macro.MacroPdf417Checksum}");
                    Console.WriteLine($"Pdf417MacroFileSize: {macro.MacroPdf417FileSize}");
                    Console.WriteLine($"Pdf417MacroTimeStamp: {macro.MacroPdf417TimeStamp}");
                    Console.WriteLine($"Pdf417MacroAddressee: {macro.MacroPdf417Addressee}");
                    Console.WriteLine($"Pdf417MacroSender: {macro.MacroPdf417Sender}");
                    Console.WriteLine($"MacroPdf417Terminator: {macro.MacroPdf417Terminator}");

                    Console.WriteLine(new string('-', 40));
                }
            }

            Console.WriteLine("Decoding completed. Press any key to exit.");
            Console.ReadKey();
        }
    }
}
```

### Pourquoi chaque ligne est importante

| Étape | Objectif |
|------|----------|
| **1️⃣ Initialiser** | Crée un `BarCodeReader` lié au fichier image et restreint la détection à la symbologie MacroPdf417, ce qui accélère le traitement. |
| **2️⃣ Itérer** | `ReadBarCodes()` renvoie **tous** les codes-barres correspondant au type demandé, vous permettant de **lire plusieurs codes-barres** sans boucles supplémentaires. |
| **3️⃣ Sortie de base** | Affiche le `CodeTypeName` générique et le `CodeText` lisible par l’homme. Ceci est utile pour la journalisation ou une validation rapide. |
| **4️⃣ Données étendues** | MacroPdf417 transporte des métadonnées supplémentaires (ID de fichier, nombre de segments, horodatages, etc.). L’objet `Extended.Pdf417` expose chaque champ directement, vous permettant de stocker ou de vérifier le paquet de données complet. |

Exécuter le programme avec une image MacroPdf417 valide produit une sortie console similaire à ce qui suit :

```
CodeType: MacroPdf417
CodeText: https://example.com/document.pdf
Pdf417MacroFileID: 12345678
Pdf417MacroSegmentID: 1
Pdf417MacroSegmentsCount: 3
Pdf417MacroFileName: document.pdf
Pdf417MacroChecksum: 0x9A3F
Pdf417MacroFileSize: 245760
Pdf417MacroTimeStamp: 2024-07-15T14:32:00Z
Pdf417MacroAddressee: John Doe
Pdf417MacroSender: Acme Corp.
MacroPdf417Terminator: True
----------------------------------------
```

La sortie confirme que la bibliothèque a correctement lu le code-barres, extrait le texte, et fourni chaque champ MacroPdf417.

## Lire plusieurs codes-barres à partir d’une seule image

De nombreux scénarios réels placent plusieurs symboles PDF417 sur une même étiquette — pensez à un manifeste d’expédition contenant un code transporteur, un numéro de suivi et une déclaration en douane. Le même bloc de code ci‑dessus **lit déjà plusieurs codes-barres** car `ReadBarCodes()` renvoie un énumérable de toutes les correspondances. Aucune configuration supplémentaire n’est nécessaire ; vous devez simplement parcourir les résultats, comme démontré.

Si vous souhaitez limiter le lecteur au PDF417 standard (non‑macro) tout en gérant plusieurs codes, remplacez `DecodeType.MacroPdf417` par `DecodeType.Pdf417`. Le reste de la logique reste inchangé.

## Comprendre les données étendues MacroPdf417

MacroPdf417 est une extension de la spécification PDF417 standard. Il divise les charges utiles importantes en plusieurs segments et ajoute un petit en‑tête décrivant le fichier complet. Les champs les plus pertinents sont :

- **MacroPdf417FileID** – un identifiant unique partagé par tous les segments du même fichier.
- **MacroPdf417SegmentID** – le numéro de séquence du segment actuel.
- **MacroPdf417SegmentsCount** – nombre total de segments attendus.
- **MacroPdf417FileName** – nom de fichier optionnel transmis avec le code-barres.
- **MacroPdf417Checksum** – valeur de contrôle d’erreur pour le fichier complet.
- **MacroPdf417FileSize** – taille de la charge binaire originale.
- **MacroPdf417TimeStamp** – horodatage ISO‑8601 du moment où le code-barres a été généré.
- **MacroPdf417Addressee / Sender** – champs textuels optionnels pour le routage.
- **MacroPdf417Terminator** – indique si ce segment est le dernier.

Lorsque vous avez reçu tous les segments, vous pouvez reconstruire le fichier original en les ordonnant par `MacroPdf417SegmentID` et en concaténant les valeurs `CodeText`. Cette logique est simple à implémenter une fois les champs disponibles.

## Pièges courants et astuces professionnelles

- **La qualité de l’image compte** – les fichiers PNG/JPEG à basse résolution ou fortement compressés peuvent entraîner des détections manquées. Utilisez une résolution d’au moins 300 dpi pour les codes-barres imprimés.
- **Symbologies mixtes** – si l’image contient à la fois MacroPdf417 et PDF417 standard, créez deux lecteurs (un pour chaque `DecodeType`) ou utilisez `DecodeType.AllSupported` et filtrez les résultats par `result.CodeTypeName`.
- **Utilisation de la mémoire** – l’instruction `using` libère rapidement le `BarCodeReader`, empêchant les gros tampons d’image de rester en mémoire.
- **Sécurité des threads** – `BarCodeReader` n’est pas thread‑safe. Créez une instance distincte par thread si vous décodez des images en parallèle.
- **Gestion des erreurs** – encapsulez l’appel `ReadBarCodes()` dans un bloc try/catch pour capturer `BarCodeException` en cas d’images corrompues.

## Récapitulatif de l’exemple complet fonctionnel

Voici le programme complet que vous pouvez copier dans un nouveau projet console. Il inclut toutes les directives `using`, une constante pour le chemin de l’image, et le modèle de libération.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

namespace Pdf417ReaderDemo
{
    class Program
    {
        static void Main()
        {
            const string imagePath = @"YOUR_DIRECTORY\MacroPdf417.png";

            using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
            {
                foreach (BarCodeResult result in reader.ReadBarCodes())
                {
                    Console.WriteLine($"CodeType: {result.CodeTypeName}");
                    Console.WriteLine($"CodeText: {result.CodeText}");

                    var macro = result.Extended.Pdf417;
                    Console.WriteLine($"Pdf417MacroFileID: {macro.MacroPdf417FileID}");
                    Console.WriteLine($"Pdf417MacroSegmentID: {macro.MacroPdf417SegmentID}");
                    Console.WriteLine($"Pdf417MacroSegmentsCount: {macro.MacroPdf417SegmentsCount}");
                    Console.WriteLine($"Pdf417MacroFileName: {macro.MacroPdf417FileName}");
                    Console.WriteLine($"Pdf417MacroChecksum: {macro.MacroPdf417Checksum}");
                    Console.WriteLine($"Pdf417MacroFileSize: {macro.MacroPdf417FileSize}");
                    Console.WriteLine($"Pdf417MacroTimeStamp: {macro.MacroPdf417TimeStamp}");
                    Console.WriteLine($"Pdf417MacroAddressee: {macro.MacroPdf417Addressee}");
                    Console.WriteLine($"Pdf417MacroSender: {macro.MacroPdf417Sender}");
                    Console.WriteLine($"MacroPdf417Terminator: {macro.MacroPdf417Terminator}");
                    Console.WriteLine(new string('-', 40));
                }
            }

            Console.WriteLine("Decoding completed. Press any key to exit.");
            Console.ReadKey();
        }
    }
}
```

Compilez avec `dotnet build` et exécutez avec `dotnet run`. La console affiche les données de base de chaque code-barres ainsi que la charge complète MacroPdf417.

## Prochaines étapes

- **Reconstruire les fichiers multipart** – collectez tous les segments, triez par `MacroPdf417SegmentID`, et concaténez `CodeText` to

## Que devriez‑vous apprendre ensuite ?

Les tutoriels suivants couvrent des sujets étroitement liés qui s’appuient sur les techniques démontrées dans ce guide. Chaque ressource comprend des exemples de code complets et fonctionnels avec des explications étape par étape pour vous aider à maîtriser des fonctionnalités API supplémentaires et explorer des approches d’implémentation alternatives dans vos propres projets.

- [Comment générer un code-barres PDF417 – Encodage Compact PDF417](/barcode/english/net/compact-pdf417-encoding/)
- [Comment lire les codes-barres PDF417 avec des caractères turcs en Java](/barcode/english/java/multilingual-support/recognizing-pdf417-turkish-characters/)
- [Comment utiliser Aspose pour le code-barres PDF417 (Chinois) en Java](/barcode/english/java/multilingual-support/recognizing-pdf417-chinese-characters/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}