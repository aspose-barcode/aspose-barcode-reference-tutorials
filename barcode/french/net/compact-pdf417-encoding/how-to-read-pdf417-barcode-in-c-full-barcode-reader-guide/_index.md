---
category: general
date: 2026-10-21
description: Comment lire un code‑barres PDF417 en C# à l’aide d’un lecteur de code‑barres
  depuis une image. Suivez cet exemple de lecteur de code‑barres C# étape par étape
  pour un décodage fiable.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to read pdf417 barcode
- read barcode from image c#
- c# barcode reader example
- macro pdf417 decoding
- barcode extended fields c#
language: fr
lastmod: 2026-10-21
og_description: Comment lire le code‑barcode PDF417 en C# avec un exemple complet
  de lecteur de code‑barcode. Apprenez à décoder les images Macro PDF417 et à accéder
  à tous les champs étendus.
og_image_alt: Console output showing decoded PDF417 barcode fields in a C# application
og_title: Comment lire le code‑barres PDF417 en C# – guide détaillé
schemas:
- author: Aspose
  dateModified: '2026-10-21'
  description: How to read PDF417 barcode in C# using a barcode reader from image.
    Follow this step‑by‑step C# barcode reader example for reliable decoding.
  headline: How to read PDF417 barcode in C# – full barcode reader guide
  type: TechArticle
- description: How to read PDF417 barcode in C# using a barcode reader from image.
    Follow this step‑by‑step C# barcode reader example for reliable decoding.
  name: How to read PDF417 barcode in C# – full barcode reader guide
  steps:
  - name: Initialise the `BarCodeReader` for the specific `DecodeType`.
    text: Initialise the `BarCodeReader` for the specific `DecodeType`.
  - name: Iterate through the returned `BarCodeResult` collection.
    text: Iterate through the returned `BarCodeResult` collection.
  - name: Access both basic and extended PDF417 fields.
    text: Access both basic and extended PDF417 fields.
  - name: '**Create a new console project**'
    text: '**Create a new console project**'
  - name: '**Add the Aspose.BarCode package** (as shown earlier).'
    text: '**Add the Aspose.BarCode package** (as shown earlier).'
  - name: '**Copy the image file** into the project folder or reference it with an
      absolute path.'
    text: '**Copy the image file** into the project folder or reference it with an
      absolute path.'
  - name: '**Build and run**'
    text: '**Build and run**'
  type: HowTo
tags:
- barcode
- C#
- PDF417
title: Comment lire le code‑barres PDF417 en C# – guide complet du lecteur de codes‑barres
url: /fr/net/compact-pdf417-encoding/how-to-read-pdf417-barcode-in-c-full-barcode-reader-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Comment lire un code‑barres PDF417 en C# – guide complet du lecteur de code‑barres

Si vous avez besoin de **comment lire un code‑barres PDF417** dans une application .NET, ce guide vous montre une solution prête à l’emploi. Vous verrez comment **read barcode from image C#** en utilisant une bibliothèque de code‑barres populaire et obtenir chaque attribut Macro PDF417 sans outil supplémentaire.

Le tutoriel couvre tout ce qui est nécessaire pour un **exemple de lecteur de code‑barres C#** : configuration du projet, explication du code et astuces pour gérer les cas limites. À la fin, vous pourrez coller le code dans un projet console et commencer à décoder des images PDF417 instantanément.

## Ce dont vous avez besoin

Avant de commencer, confirmez les prérequis suivants :

| Prérequis | Raison |
|--------------|--------|
| .NET 6.0 SDK ou version ultérieure | Fournit le runtime pour l’application console C# |
| Visual Studio 2022 (ou tout IDE C#) | Permet une création de projet et un débogage faciles |
| Aspose.BarCode for .NET (package NuGet) | Fournit les classes `BarCodeReader` et `DecodeType` |
| Un fichier image Macro PDF417 (p. ex., `MacroPdf417.png`) | Sert d’entrée pour le décodage |

Vous pouvez installer la bibliothèque avec le CLI dotnet :

```bash
dotnet add package Aspose.BarCode
```

## Comment lire le code‑barres PDF417 à partir d’une image en C#

Le cœur du workflow **read barcode from image C#** se compose de trois actions :

1. Initialiser le `BarCodeReader` pour le `DecodeType` spécifique.  
2. Parcourir la collection `BarCodeResult` retournée.  
3. Accéder aux champs PDF417 de base et étendus.

Voici le code complet, exécutable. Enregistrez‑le sous le nom `Program.cs` dans un projet console.

```csharp
using System;
using Aspose.BarCode;               // Provides BarCodeReader, DecodeType, BarCodeResult
using Aspose.BarCode.BarCodeRecognition; // Contains extended PDF417 structures

class Program
{
    static void Main()
    {
        // Step 1: Initialise a BarCodeReader for a Macro PDF417 image
        // Replace the path with the location of your MacroPdf417.png file
        string imagePath = @"YOUR_DIRECTORY\MacroPdf417.png";

        using (BarCodeReader barcodeReader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
        {
            // Step 2: Read all barcodes present in the image
            foreach (BarCodeResult barcodeResult in barcodeReader.ReadBarCodes())
            {
                // Step 3: Display basic barcode information
                Console.WriteLine($"CodeType: {barcodeResult.CodeTypeName}");
                Console.WriteLine($"CodeText: {barcodeResult.CodeText}");

                // Step 4: Show Macro PDF417 specific extended fields
                Console.WriteLine($"File ID: {barcodeResult.Extended.Pdf417.MacroPdf417FileID}");
                Console.WriteLine($"Segment ID: {barcodeResult.Extended.Pdf417.MacroPdf417SegmentID}");
                Console.WriteLine($"Segments Count: {barcodeResult.Extended.Pdf417.MacroPdf417SegmentsCount}");
                Console.WriteLine($"File Name: {barcodeResult.Extended.Pdf417.MacroPdf417FileName}");
                Console.WriteLine($"Checksum: {barcodeResult.Extended.Pdf417.MacroPdf417Checksum}");
                Console.WriteLine($"File Size: {barcodeResult.Extended.Pdf417.MacroPdf417FileSize}");
                Console.WriteLine($"TimeStamp: {barcodeResult.Extended.Pdf417.MacroPdf417TimeStamp}");
                Console.WriteLine($"Addressee: {barcodeResult.Extended.Pdf417.MacroPdf417Addressee}");
                Console.WriteLine($"Sender: {barcodeResult.Extended.Pdf417.MacroPdf417Sender}");
                Console.WriteLine($"Terminator: {barcodeResult.Extended.Pdf417.MacroPdf417Terminator}");
                Console.WriteLine(new string('-', 40));
            }
        }
    }
}
```

### Explication de chaque étape

* **Étape 1 – Initialiser le lecteur**  
  Le constructeur `BarCodeReader` reçoit le chemin du fichier image et un `DecodeType`. `DecodeType.MacroPdf417` indique à la bibliothèque de rechercher les symboles Macro PDF417, qui contiennent des métadonnées supplémentaires au-delà des codes‑barres PDF417 ordinaires.

* **Étape 2 – ReadBarCodes()**  
  Cette méthode renvoie un `IEnumerable<BarCodeResult>` qui peut contenir plusieurs codes‑barres si l’image en comporte plusieurs. La boucle `foreach` garantit que chaque symbole détecté est traité.

* **Étape 3 – Informations de base**  
  `CodeTypeName` identifie le format du code‑barres (p. ex., “MacroPDF417”). `CodeText` contient la chaîne de données brute encodée dans le symbole.

* **Étape 4 – Champs étendus**  
  Macro PDF417 ajoute un ensemble de propriétés étendues sous `barcodeResult.Extended.Pdf417`. Ces champs exposent des données au niveau du fichier telles que `FileID`, `SegmentID` et `FileName`. Les accéder directement vous permet de reconstruire des documents multi‑segments ou de vérifier l’intégrité.

#### Sortie console attendue

```
CodeType: MacroPDF417
CodeText: 1234567890
File ID: 5
Segment ID: 1
Segments Count: 3
File Name: invoice_2024.pdf
Checksum: 0A3F
File Size: 254321
TimeStamp: 2024-03-15T10:45:12Z
Addressee: Acme Corp.
Sender: Warehouse 12
Terminator: END
----------------------------------------
```

Les valeurs exactes reflètent le contenu encodé dans votre `MacroPdf417.png`. Si l’image ne contient qu’un seul segment, `SegmentsCount` sera 1 et `SegmentID` sera 0.

## Configurer l’environnement du lecteur de code‑barres C#

Un **exemple de lecteur de code‑barres C#** fiable dépend d’une configuration de projet propre :

1. **Créer un nouveau projet console**  
   ```bash
   dotnet new console -n Pdf417ReaderDemo
   cd Pdf417ReaderDemo
   ```
2. **Ajouter le package Aspose.BarCode** (comme montré précédemment).  
3. **Copier le fichier image** dans le dossier du projet ou le référencer avec un chemin absolu.  
4. **Construire et exécuter**  
   ```bash
   dotnet run
   ```

Si la compilation échoue avec une erreur de référence manquante, vérifiez que les instructions `using Aspose.BarCode;` correspondent à la version du package installé. L’API de la bibliothèque est stable entre .NET 6 et .NET 8, vous pouvez donc mettre à jour le runtime sans modifier le code.

## Décoder le code‑barres Macro PDF417

Lorsque vous appelez `ReadBarCodes()`, la bibliothèque exécute les étapes suivantes en interne :

* **Prétraitement de l’image** – convertit le bitmap en matrice binaire, corrige la rotation et le bruit.  
* **Détection de motif** – recherche les motifs de début/fin PDF417 et extrait la largeur du module.  
* **Correction d’erreurs** – applique les codes Reed‑Solomon pour récupérer les mots de code endommagés.  
* **Extraction Macro** – analyse l’en‑tête de segment PDF417 étendu et remplit l’objet `Extended.Pdf417`.

Comprendre ce pipeline vous aide à décider quand ajuster les options du décodeur. Par exemple, si vos images sont à faible contraste, vous pouvez activer la propriété `ReadQuality` du `BarCodeReader` (disponible dans les versions récentes) pour améliorer les taux de détection.

## Interpréter les champs PDF417 étendus

Les champs étendus correspondent directement à la spécification Macro PDF417 :

| Champ | Signification |
|-------|----------------|
| `MacroPdf417FileID` | Identifiant unique du fichier complet à travers tous les segments |
| `MacroPdf417SegmentID` | Index basé sur zéro du segment actuel |
| `MacroPdf417SegmentsCount` | Nombre total de segments composant le fichier |
| `MacroPdf417FileName` | Nom de fichier original stocké lors de l’encodage |
| `MacroPdf417Checksum` | Somme de contrôle 16 bits pour la vérification d’intégrité |
| `MacroPdf417FileSize` | Taille du fichier original en octets |
| `MacroPdf417TimeStamp` | Horodatage UTC au moment de la génération du code‑barres |
| `MacroPdf417Addressee` | Destinataire prévu du document |
| `MacroPdf417Sender` | Expéditeur du document |
| `MacroPdf417Terminator` | Chaîne littérale “END” marquant le dernier segment |

Vous pouvez utiliser ces valeurs pour reconstruire un PDF multi‑segment, vérifier qu’aucun segment ne manque, ou consigner des informations d’audit à des fins de conformité.

## Pièges courants et dépannage

| Symptôme | Cause probable | Solution |
|----------|----------------|----------|
| Aucun résultat affiché | Chemin d’image incorrect ou format non pris en charge | Utilisez un chemin absolu et assurez‑vous que le fichier est un PNG/JPEG supporté par Aspose.BarCode |
| `CodeType` indique “PDF417” au lieu de “MacroPDF417” | L’image contient un symbole PDF417 standard, pas une variante macro | Vérifiez que le code‑barres source est encodé avec les extensions Macro PDF417 |
| Certains champs sont vides | Le code‑barres a été généré sans ces champs macro | Encodez le code‑barres avec une charge macro complète, ou gérez les valeurs null dans le code |
| Le décodeur lève `ArgumentException` | `DecodeType` incorrect | Changez `DecodeType.MacroPdf417` en `DecodeType.Pdf417` si vous n’avez besoin que des données PDF417 standard |

**Astuce :** Enveloppez l’accès aux champs dans des vérifications de null si vous prévoyez des code‑barres non macro. L’objet `Extended.Pdf417` renvoie des valeurs par défaut (p. ex., `0` pour les champs numériques) lorsque les données sont absentes.

```csharp
int fileId = barcodeResult.Extended?.Pdf417?.MacroPdf417FileID ?? -1;
```

## Récapitulatif de l’exemple complet

En rassemblant tous les éléments, le programme final comprend les directives `using`, la méthode `Main` et la boucle en quatre étapes présentée précédemment. Aucun fichier de configuration supplémentaire n’est requis. Compilez et exécutez le projet pour voir la sortie console avec toutes les propriétés Macro PDF417.

## Conclusion

Vous savez maintenant **comment lire un code‑barres PDF417** en C# grâce à un **exemple concis de lecteur de code‑barres C#**. Le guide vous a accompagné à travers la configuration de l’environnement, l’implémentation du code et l’interprétation de chaque champ Macro PDF417 étendu. Avec cette base, vous pouvez intégrer la lecture de code‑barres dans des systèmes d’inventaire, des flux de gestion documentaire ou des back‑ends mobiles.

### Suivant


## Que devriez‑vous apprendre ensuite ?


Les tutoriels suivants couvrent des sujets étroitement liés qui s’appuient sur les techniques démontrées dans ce guide. Chaque ressource inclut des exemples de code complets avec des explications pas à pas pour vous aider à maîtriser des fonctionnalités API supplémentaires et explorer des approches d’implémentation alternatives dans vos propres projets.

- [How to read PDF417 in C# – complete barcode reader guide](/barcode/english/net/compact-pdf417-encoding/how-to-read-pdf417-in-c-complete-barcode-reader-guide/)
- [How to decode PDF417 in C# with a barcode reader example](/barcode/english/net/compact-pdf417-encoding/how-to-decode-pdf417-in-c-with-a-barcode-reader-example/)
- [How to create PDF417 barcode image in C# with Macro PDF417 options](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-image-in-c-with-macro-pdf417-op/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}