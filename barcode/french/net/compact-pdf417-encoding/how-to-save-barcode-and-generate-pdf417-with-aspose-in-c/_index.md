---
category: general
date: 2026-09-29
description: Comment enregistrer un code‑barres avec Aspose.BarCode en C# et apprendre
  à générer un PDF417 avec des métadonnées macro. Suivez le guide étape par étape.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to save barcode
- how to generate pdf417
- how to set pdf417
- generate barcode with aspose
language: fr
lastmod: 2026-09-29
og_description: Enregistrer un code‑barres avec Aspose.BarCode en C# est simple. Ce
  tutoriel montre comment générer un PDF417 avec des métadonnées macro et définir
  tous les paramètres requis.
og_image_alt: Screenshot showing how to save barcode as PNG with PDF417 macro metadata
og_title: Comment enregistrer un code‑barres avec Aspose – Guide de génération PDF417
schemas:
- author: Aspose
  dateModified: '2026-09-29'
  description: How to save barcode using Aspose.BarCode in C# and learn how to generate
    PDF417 with macro metadata. Follow step‑by‑step guide.
  headline: How to save barcode and generate PDF417 with Aspose in C#
  type: TechArticle
- description: How to save barcode using Aspose.BarCode in C# and learn how to generate
    PDF417 with macro metadata. Follow step‑by‑step guide.
  name: How to save barcode and generate PDF417 with Aspose in C#
  steps:
  - name: '**Creating the generator** – The `BarcodeGenerator` constructor takes the
      barcode type (`EncodeTypes.MacroPdf417`) and the data to encode. Macro PDF417
      is a special variant that carries file‑transfer information, which is why we
      later fill macro fields.'
    text: '**Creating the generator** – The `BarcodeGenerator` constructor takes the
      barcode type (`EncodeTypes.MacroPdf417`) and the data to encode. Macro PDF417
      is a special variant that carries file‑transfer information, which is why we
      later fill macro fields.'
  - name: '**Appearance settings** – `XDimension.Pixels` controls the narrow bar width;
      adjusting it changes the overall image size without affecting data integrity.
      `Pdf417.Columns` defines the layout of the barcode matrix.'
    text: '**Appearance settings** – `XDimension.Pixels` controls the narrow bar width;
      adjusting it changes the overall image size without affecting data integrity.
      `Pdf417.Columns` defines the layout of the barcode matrix.'
  - name: '**Macro metadata** – These properties (`MacroPdf417FileID`, `MacroPdf417SegmentID`,
      etc.) are essential when you need to split a large file into multiple barcode
      segments. Setting them correctly ensures that a scanner can reconstruct the
      original file.'
    text: '**Macro metadata** – These properties (`MacroPdf417FileID`, `MacroPdf417SegmentID`,
      etc.) are essential when you need to split a large file into multiple barcode
      segments. Setting them correctly ensures that a scanner can reconstruct the
      original file.'
  - name: '**Saving the image** – The `Save` method writes the generated barcode to
      disk. You can choose any supported format (`Png`, `Jpeg`, `Bmp`, etc.). This
      line demonstrates the exact **how to save barcode** operation requested.'
    text: '**Saving the image** – The `Save` method writes the generated barcode to
      disk. You can choose any supported format (`Png`, `Jpeg`, `Bmp`, etc.). This
      line demonstrates the exact **how to save barcode** operation requested.'
  type: HowTo
tags:
- barcode
- PDF417
- Aspose
- C#
title: Comment enregistrer le code-barres et générer un PDF417 avec Aspose en C#
url: /fr/net/compact-pdf417-encoding/how-to-save-barcode-and-generate-pdf417-with-aspose-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Comment enregistrer un code-barres et générer du PDF417 avec Aspose en C#

Enregistrer un code-barres à l'aide d'Aspose.BarCode en C# est une exigence courante lorsque vous devez intégrer des données dans un fichier image. Ce guide vous accompagne à travers le processus complet de génération d'un code-barres PDF417 avec des méta‑données macro et d'enregistrement du résultat au format PNG. À la fin, vous saurez **comment générer du PDF417**, **comment configurer les options PDF417**, et, surtout, **comment enregistrer des fichiers de code-barres** de façon programmatique.

Vous verrez un exemple complet et exécutable qui couvre chaque étape — de l'ajout du package NuGet Aspose.BarCode à la configuration des champs macro tels que l'ID de fichier, le nombre de segments et le checksum. Aucune documentation externe n'est requise ; le code peut être copié dans un nouveau projet console et exécuté immédiatement. Le tutoriel suppose que vous avez Visual Studio 2022 (ou une version ultérieure) et .NET 6.0 installés.

## Prérequis

- .NET 6.0 SDK (ou toute version .NET prise en charge par Aspose.BarCode 23.11+)
- Visual Studio 2022, VS Code, ou votre IDE C# préféré
- **Aspose.BarCode for .NET** package NuGet  
  ```bash
  dotnet add package Aspose.BarCode
  ```
- Connaissances de base de la syntaxe C# et des applications console

> **Astuce :** Utilisez la licence d'évaluation gratuite pour développeurs d'Aspose si vous n'avez pas encore de licence commerciale. L'évaluation fonctionne sans modification du code.

## Comment enregistrer un code-barres – exemple complet

Le code suivant crée un code-barres **Macro PDF417**, remplit tous les champs macro et enregistre l'image sous le nom `ExtPDF417Meta.png`. Toutes les directives `using` requises sont incluses afin que vous puissiez coller le fragment directement dans `Program.cs`.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Step 1: Create a barcode generator for Macro PDF417 with sample data
        using (BarcodeGenerator generator = new BarcodeGenerator(
            EncodeTypes.MacroPdf417,          // EncodeTypes enum selects the barcode type
            "Åspóse.Barcóde©"))               // Sample data – Unicode characters are supported
        {
            // Step 2: Define basic barcode appearance
            generator.Parameters.Barcode.XDimension.Pixels = 2;   // narrow bar width (2 px)
            generator.Parameters.Barcode.Pdf417.Columns = 5;    // number of columns per row

            // Step 3: Configure Macro PDF417 metadata
            generator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
            generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;
            generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;
            generator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";
            generator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234; // CCITT‑16 example
            generator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400_000;
            generator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = new DateTime(2019, 11, 1);
            generator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
            generator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
            generator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;

            // Step 4: Save the generated barcode as a PNG image
            // This is the core of **how to save barcode** with Aspose.
            generator.Save("ExtPDF417Meta.png", BarCodeImageFormat.Png);
        }

        Console.WriteLine("Barcode saved as ExtPDF417Meta.png");
    }
}
```

### Pourquoi chaque étape est importante

1. **Création du générateur** – Le constructeur `BarcodeGenerator` prend le type de code‑barres (`EncodeTypes.MacroPdf417`) et les données à encoder. Macro PDF417 est une variante spéciale qui transporte des informations de transfert de fichier, c’est pourquoi nous remplissons ensuite les champs macro.
2. **Paramètres d'apparence** – `XDimension.Pixels` contrôle la largeur de la barre étroite ; le modifier change la taille globale de l'image sans affecter l'intégrité des données. `Pdf417.Columns` définit la disposition de la matrice du code‑barres.
3. **Métadonnées macro** – Ces propriétés (`MacroPdf417FileID`, `MacroPdf417SegmentID`, etc.) sont essentielles lorsque vous devez diviser un gros fichier en plusieurs segments de code‑barres. Les définir correctement garantit qu'un scanner peut reconstruire le fichier original.
4. **Enregistrement de l'image** – La méthode `Save` écrit le code‑barres généré sur le disque. Vous pouvez choisir n'importe quel format supporté (`Png`, `Jpeg`, `Bmp`, etc.). Cette ligne montre l'opération exacte de **comment enregistrer un code‑barres** demandée.

> **Question fréquente :** *Et si j’ai besoin d’un format d’image différent ?*  
> Remplacez `BarCodeImageFormat.Png` par `BarCodeImageFormat.Jpeg` (ou toute autre valeur d’énumération supportée) et ajustez l’extension du fichier en conséquence.

## Comment générer du PDF417 avec des méta‑données macro

Si vous avez seulement besoin d’un PDF417 standard (sans données macro), vous pouvez ignorer la section macro et conserver le générateur de base :

```csharp
using (BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.Pdf417, "Sample data"))
{
    gen.Parameters.Barcode.XDimension.Pixels = 3;
    gen.Save("SimplePdf417.png", BarCodeImageFormat.Png);
}
```

Le code ci‑dessus illustre rapidement **comment générer du PDF417**. Notez que l'énumération `EncodeTypes.Pdf417` sélectionne la version non‑macro.

## Comment configurer PDF417 – options avancées

Aspose.BarCode expose de nombreux paramètres spécifiques à PDF417. En voici quelques-uns qui pourraient vous être utiles :

| Property | Description | Typical values |
|----------|-------------|----------------|
| `Pdf417.Columns` | Nombre de colonnes par ligne | 1‑30 (default 3) |
| `Pdf417.Rows` | Nombre de lignes (calculé automatiquement si 0) | 0‑90 |
| `Pdf417.ErrorLevel` | Niveau de correction d’erreur (0‑8) | 2‑4 pour un équilibre taille/robustesse |
| `Pdf417.RowsPerStrip` | Lignes par bande pour les gros codes‑barres | 0 (auto) |
| `Pdf417.Pdf417MacroFileID` | Identifiant du fichier lors de l’utilisation du macro | Any 32‑bit integer |

La définition de ces valeurs suit le même schéma présenté dans **l’étape 2** de l’exemple principal. Ajustez‑les avant d’appeler `Save`.

## Résultat attendu

L'exécution du programme complet crée `ExtPDF417Meta.png` dans le répertoire de travail de l'exécutable. L'image contient un code‑barres PDF417 haute résolution avec tous les champs macro intégrés. Scanner l'image avec un lecteur compatible PDF417 (ou une application mobile) renverra la chaîne de données originale `"Åspóse.Barcóde©"` ainsi que les méta‑données macro (ID de fichier, ID de segment, etc.).

![Code‑barres enregistré en PNG – exemple de comment enregistrer un code‑barres](ExtPDF417Meta.png "Comment enregistrer un code‑barres en PNG avec des méta‑données macro PDF417")

*Texte alternatif de l’image :* **comment enregistrer un code‑barres en PNG avec des méta‑données macro PDF417** (correspond au mot‑clé principal).

## Conclusion

Dans ce tutoriel, vous avez appris **comment enregistrer un code‑barres** avec Aspose.BarCode, **comment générer du PDF417**, **comment configurer les paramètres PDF417**, et **comment générer un code‑barres avec Aspose** pour les scénarios standard et avec macro activée.

## Que devriez‑vous apprendre ensuite ?

Les tutoriels suivants couvrent des sujets étroitement liés qui s’appuient sur les techniques démontrées dans ce guide. Chaque ressource comprend des exemples de code complets et fonctionnels avec des explications étape par étape pour vous aider à maîtriser des fonctionnalités supplémentaires de l'API et à explorer des approches d'implémentation alternatives dans vos propres projets.

- [Comment générer un code‑barres PDF417 avec Aspose – Guide complet](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-with-aspose-complete-guide/)
- [Comment générer une image de code‑barres PDF417 en C# avec Aspose](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-image-in-c-with-aspose/)
- [Comment générer un code‑barres en C# avec Aspose.BarCode et ajouter des méta‑données](/barcode/english/net/compact-pdf417-encoding/how-to-generate-barcode-in-c-with-aspose-barcode-and-add-met/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}