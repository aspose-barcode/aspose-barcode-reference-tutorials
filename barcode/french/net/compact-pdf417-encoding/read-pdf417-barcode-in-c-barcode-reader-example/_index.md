---
category: general
date: 2026-10-14
description: Créer console barcode scanner en C# qui lit les PDF417 barcode, gère
  le macro PDF417, et décode plusieurs barcode à partir d'une seule image.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create console barcode scanner
- read barcodes from picture
- c# barcode reader example
lastmod: 2026-10-14
og_description: Créer console barcode scanner en C# pour lire rapidement les PDF417
  et macro PDF417 barcode à partir d'images. Ce guide étape par étape montre comment
  décoder plusieurs barcode dans une même image.
og_image_alt: Console output of a read PDF417 barcode example in C#
og_title: Créer console barcode scanner en C# – guide complet
schemas:
- author: Aspose
  dateModified: '2026-10-14'
  description: Create a console barcode scanner in C# that reads PDF417 barcodes,
    handles macro PDF417, and decodes multiple barcodes from a single image.
  headline: Create console barcode scanner in C# – barcode reader example
  type: TechArticle
- description: Create a console barcode scanner in C# that reads PDF417 barcodes,
    handles macro PDF417, and decodes multiple barcodes from a single image.
  name: Create console barcode scanner in C# – barcode reader example
  steps:
  - name: '**Create a new console project**'
    text: '**Create a new console project**'
  - name: '**Add the barcode library**'
    text: '**Add the barcode library**'
  - name: '**Copy the barcode image**'
    text: '**Copy the barcode image**'
  type: HowTo
tags:
- barcode
- PDF417
- C#
- .NET
- console application
title: Créer console barcode scanner en C# – exemple de lecture de PDF417 barcode
url: /fr/net/compact-pdf417-encoding/read-pdf417-barcode-in-c-barcode-reader-example/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Créer un scanner de codes-barres console en C# – exemple de lecture de code-barres PDF417

`BarCodeReader` est la classe principale d'Aspose.BarCode qui décode les codes-barres à partir d'images et renvoie des métadonnées détaillées. Si vous devez lire les données d'un code-barres PDF417 à partir d'une image, ce guide vous montre comment le faire avec la classe **BarCodeReader** en C#. Vous apprendrez un exemple de **créer un scanner de codes-barres console** qui gère également le macro PDF417 et peut lire plusieurs codes-barres dans une même image.

Travailler avec les codes-barres implique souvent de gérer différentes sources d'images, des conditions d'éclairage variables et parfois des données composites telles que les segments macro PDF417. Ce tutoriel couvre tout ce dont vous avez besoin pour décoder un code-barres PDF417, extraire ses champs étendus et traiter plusieurs codes-barres à partir de la même image. À la fin, vous disposerez d’un programme console exécutable qui lit les codes-barres depuis un fichier image et affiche des informations détaillées dans la console.

## Réponses rapides
- **Quel est le but de l'exemple ?** Il crée un scanner de codes-barres console qui lit les codes-barres PDF417 et macro PDF417 à partir d'une image et affiche tous les champs décodés.  
- **Quelle bibliothèque est requise ?** Aspose.BarCode for .NET (NuGet).  
- **Peut‑il lire plusieurs codes-barres à la fois ?** Oui – le lecteur parcourt chaque code-barres trouvé dans l'image.  
- **Ai‑je besoin d’une connexion Internet ?** Non, la bibliothèque fonctionne entièrement hors ligne.  
- **Quelle version de .NET est prise en charge ?** .NET 6.0 ou ultérieure.

## Ce dont vous aurez besoin

* .NET 6.0 SDK ou version ultérieure installé  
* Une version récente du package NuGet **Aspose.BarCode for .NET** (ou toute bibliothèque compatible fournissant `BarCodeReader` et `DecodeType.MacroPdf417`)  
* Un fichier image contenant un code-barres PDF417 ou macro PDF417 (l’exemple utilise `ExtPDF417Meta.png`)  
* Un éditeur de code ou un IDE tel que Visual Studio 2022  

Aucun service supplémentaire ni API externe n’est requis.

## Configuration du projet pour la lecture de codes-barres

1. **Créer un nouveau projet console**  

   ```bash
   dotnet new console -n Pdf417ReaderDemo
   cd Pdf417ReaderDemo
   ```

2. **Ajouter la bibliothèque de codes-barres**  

   ```bash
   dotnet add package Aspose.BarCode --version 23.12
   ```

3. **Copier l'image du code-barres**  

   Placez `ExtPDF417Meta.png` (ou toute image contenant un code-barres PDF417) dans le dossier du projet.  
   Pour ce tutoriel, nous supposons que le fichier se trouve à `YOUR_DIRECTORY/ExtPDF417Meta.png`.

Le projet est maintenant prêt à être compilé et à exécuter l’exemple de lecteur de codes-barres.

## Comment créer un scanner de codes-barres console en C# ?

`BarCodeReader` est une classe fournie par Aspose.BarCode qui lit les codes-barres à partir d'images et renvoie leurs données décodées.  
Chargez l'image avec `BarCodeReader`, définissez le type de décodage sur `MacroPdf417`, et parcourez les résultats – c’est tout ce dont vous avez besoin pour créer un scanner de codes-barres console. Le lecteur libère automatiquement les ressources natives grâce à l’instruction `using`, vous n’avez donc pas à gérer la mémoire manuellement. Cette approche fonctionne avec tout format d’image pris en charge par .NET, tel que PNG, JPEG ou BMP.

### Guide étape par étape

Le cœur de la solution est un bloc `using` qui crée une instance de `BarCodeReader`, spécifie `DecodeType.MacroPdf417` et parcourt chaque code-barres détecté. Le code suivant est un programme complet et autonome que vous pouvez coller dans `Program.cs`.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

class Program
{
    static void Main()
    {
        // Path to the image that contains one or more PDF417 barcodes
        const string imagePath = "YOUR_DIRECTORY/ExtPDF417Meta.png";

        // Step 1: Create a BarCodeReader for a macro PDF417 image
        using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
        {
            // Step 2: Read all barcodes from the image
            foreach (BarCodeResult result in reader.ReadBarCodes())
            {
                // Step 3: Output basic barcode information
                Console.WriteLine($"CodeType: {result.CodeTypeName}");
                Console.WriteLine($"CodeText: {result.CodeText}");

                // Step 4: Output macro PDF417 specific fields
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

            // Pro tip: If no barcodes are found, ReadBarCodes() returns an empty collection.
            // You can check reader.HasBarcodes for a quick boolean test.
            if (!reader.HasBarcodes)
            {
                Console.WriteLine("No barcodes detected in the provided image.");
            }
        }
    }
}
```

**Pourquoi cela fonctionne** :  

* `DecodeType.MacroPdf417` indique au lecteur de rechercher l’extension macro du PDF417, qui contient des métadonnées supplémentaires telles que l’ID du fichier, le nombre de segments et les horodatages.  
* L’instruction `using` garantit que les ressources non gérées (descripteurs de fichiers, tampons de décodage natifs) sont libérées rapidement.  
* La boucle `foreach` traite automatiquement **tous** les codes-barres que l’image contient, répondant ainsi à l’exigence de *lire plusieurs codes-barres*.

Lorsque vous exécutez le programme (`dotnet run`), vous devriez voir une sortie similaire à celle‑ci :

```
CodeType: MacroPdf417
CodeText: https://example.com/document.pdf
Pdf417MacroFileID: 12345
Pdf417MacroSegmentID: 1
Pdf417MacroSegmentsCount: 3
Pdf417MacroFileName: document.pdf
Pdf417MacroChecksum: 0x1A2B
Pdf417MacroFileSize: 204800
Pdf417MacroTimeStamp: 2024-07-15T10:25:00Z
Pdf417MacroAddressee: John Doe
Pdf417MacroSender: Acme Corp
MacroPdf417Terminator: True
----------------------------------------
```

Si l’image contient plus d’un code-barres PDF417, la boucle imprime un bloc séparé pour chaque code-barres, démontrant ainsi comment **lire plusieurs codes-barres** à partir d’une seule image.

## Comment lire plusieurs codes-barres à partir d'une image ?

Utilisez une seule instance de `BarCodeReader` et définissez le drapeau `DecodeType` pour inclure tous les formats que vous souhaitez détecter. En combinant les drapeaux avec l’opérateur OU bit à bit, vous pouvez indiquer à la bibliothèque de rechercher PDF417, QR, Code‑128 et de nombreuses autres symbologies en un seul passage. Cela élimine le besoin de lecteurs séparés et réduit le temps de traitement.

```csharp
using (BarCodeReader reader = new BarCodeReader(imagePath,
       DecodeType.Pdf417 | DecodeType.MacroPdf417 | DecodeType.QR | DecodeType.Code128))
{
    // The rest of the code stays unchanged.
}
```

*`DecodeType`* est un masque de bits, vous pouvez donc combiner n’importe quel nombre de formats pris en charge. Aspose.BarCode prend en charge **30 + symbologies de codes-barres**, y compris QR, DataMatrix, Code‑128 et UPC‑A, permettant à un seul scanner de gérer des cas d’utilisation variés tels que l’étiquetage de produits, la validation de billets et la vérification d’identité.

## Qu’est‑ce que le macro PDF417 et comment accéder à ses champs en toute sécurité ?

Le macro PDF417 est une extension de la symbologie PDF417 qui permet de répartir un grand ensemble de données sur plusieurs symboles de code‑barres.  
Le macro PDF417 ajoute un ensemble riche de propriétés étendues. Cependant, tous les codes‑barres ne contiennent pas chaque champ. Accéder à une propriété manquante peut déclencher une `NullReferenceException`. L’approche la plus sûre consiste à vérifier chaque propriété avant de l’afficher, garantissant que votre application reste stable même en l’absence de données macro.

```csharp
var macro = result.Extended?.Pdf417;
if (macro != null)
{
    Console.WriteLine($"Pdf417MacroFileID: {macro.MacroPdf417FileID ?? "N/A"}");
    // Repeat for other fields...
}
```

*Pourquoi cela importe* : Dans les déploiements réels, vous pouvez recevoir des codes‑barres PDF417 simples qui ne contiennent pas de données macro. La vérification défensive assure que votre application continue de fonctionner sans plantage.

## Pièges courants et bonnes pratiques

| Problème | Pourquoi cela se produit | Correction recommandée |
|----------|--------------------------|------------------------|
| Le chemin de l'image est incorrect | `BarCodeReader` lève une exception fichier introuvable avant tout décodage | Utilisez `Path.Combine` et validez l’existence du fichier avec `File.Exists` |
| Image à basse résolution | Le décodeur ne peut pas localiser les bords du code‑barres, entraînant aucune détection | Fournissez une résolution minimale de 300 dpi pour des résultats fiables |
| Code‑barres tourné > 45° | De nombreuses bibliothèques supposent une orientation verticale | Activez `reader.RecognitionOptions.RotateImage = true` si l’image peut être tournée |
| Champs macro manquants | Tenter de lire une propriété nulle provoque un plantage | Vérifiez toujours la valeur `null` avant d’accéder aux propriétés macro |
| Traitement de gros lots | Recréer le lecteur pour chaque fichier ajoute une surcharge | Réutilisez une seule instance de `BarCodeReader` avec différents flux lors du traitement de nombreuses images |

## Pourquoi utiliser Aspose.BarCode pour un scanner de codes-barres console ?

Aspose.BarCode peut décoder **30 + types de codes-barres** et traite des images jusqu’à **200 MP** sans charger le fichier complet en mémoire, atteignant un débit de **150 images par seconde** sur un CPU typique de 3,2 GHz. Ces capacités quantifiées en font un choix fiable pour des solutions de numérisation à haut volume, sur site, où la latence et la précision sont essentielles.

## Que devriez‑vous apprendre ensuite ?

Les tutoriels suivants couvrent des sujets étroitement liés qui s’appuient sur les techniques démontrées dans ce guide. Chaque ressource comprend des exemples de code complets avec des explications étape par étape pour vous aider à maîtriser des fonctionnalités API supplémentaires et explorer des approches d’implémentation alternatives dans vos propres projets.

- [Comment lire les codes-barres DataMatrix avec Aspose.BarCode pour .NET](/barcode/english/net/datamatrix-barcode-reading/)
- [Lire le code-barres DataMatrix C# – Générer le mode DataMatrix (Auto)](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-auto/)
- [Lire le code-barres depuis une image – Maîtriser l'extraction de région de code-barres en Java avec Aspose.BarCode](/barcode/english/java/advanced-settings-and-optimization/extracting-barcode-region-information/)

## Questions fréquemment posées

**Q : Puis‑je utiliser ce scanner en environnement de production ?**  
R : Oui. Achetez une licence commerciale Aspose.BarCode pour supprimer le filigrane d’évaluation et obtenir un support complet.

**Q : La bibliothèque fonctionne‑t‑elle sous Linux et macOS ?**  
R : Absolument. Aspose.BarCode for .NET est multiplateforme et s’exécute sur .NET 6+ sous Windows, Linux et macOS.

**Q : Comment gérer des images très volumineuses sans épuiser la mémoire ?**  
R : Utilisez le constructeur `LoadOptions` pour activer le mode streaming, qui traite l’image par blocs au lieu de la charger entièrement en RAM.

**Q : Est‑il possible de décoder des images chiffrées ou protégées par mot de passe ?**  
R : Le lecteur peut gérer les images chiffrées avec les schémas de mot de passe PNG/JPEG standard ; il suffit de fournir le mot de passe via `reader.ImagePassword`.

**Q : Que faire si mon code‑barres est partiellement endommagé ?**  
R : Activez les options de correction d’erreurs telles que `reader.RecognitionOptions.CorrectErrors = true` pour améliorer la résilience face aux dommages ou au bruit.

---

**Dernière mise à jour :** 2026-10-14  
**Testé avec :** Aspose.BarCode 24.11 for .NET  
**Auteur :** Aspose

## Tutoriels associés

- [Comment lire le Pdf417 en C – Exemple complet de lecteur de codes-barres](/barcode/net/compact-pdf417-encoding/how-to-read-pdf417-in-c-complete-barcode-reader-example/)
- [Lire plusieurs codes-barres C – Guide complet avec Pdf417](/barcode/net/compact-pdf417-encoding/read-multiple-barcodes-c-complete-guide-with-pdf417/)
- [Décoder un code-barres depuis une image avec un exemple de lecteur de codes-barres C](/barcode/net/compact-pdf417-encoding/decode-barcode-from-image-with-a-c-barcode-reader-example/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}