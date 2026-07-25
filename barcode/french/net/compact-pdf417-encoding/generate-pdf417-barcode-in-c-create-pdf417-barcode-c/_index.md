---
category: general
date: 2026-07-24
description: Générez un code‑barres PDF417 en C# avec Aspose.BarCode. Apprenez à créer
  un code‑barres PDF417 en C# en mode compact en quelques minutes.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate pdf417 barcode
- create pdf417 barcode c#
- c# barcode generator pdf417
- how to generate pdf417 barcode
language: fr
lastmod: 2026-07-24
og_description: Générez rapidement un code‑barres PDF417 en C# avec Aspose.BarCode.
  Ce tutoriel vous montre comment créer un code‑barres PDF417 en C# en mode compact,
  en couvrant la configuration, le code et la vérification.
og_image_alt: Screenshot of generated compact PDF417 barcode saved as PNG using C#
  code
og_title: Générer un code-barres PDF417 en C# – Guide rapide
schemas:
- author: Aspose
  dateModified: '2026-07-24'
  description: Generate PDF417 barcode in C# using Aspose.BarCode. Learn how to create
    PDF417 barcode C# with compact mode in minutes.
  headline: Generate PDF417 Barcode in C# – Create PDF417 Barcode C#
  type: TechArticle
- description: Generate PDF417 barcode in C# using Aspose.BarCode. Learn how to create
    PDF417 barcode C# with compact mode in minutes.
  name: Generate PDF417 Barcode in C# – Create PDF417 Barcode C#
  steps:
  - name: '**Data definition** – PDF417 can store up to ~1850 characters, but we keep
      it short for the demo. Unicode support means those accented characters won’t
      break anything.'
    text: '**Data definition** – PDF417 can store up to ~1850 characters, but we keep
      it short for the demo. Unicode support means those accented characters won’t
      break anything.'
  - name: '**Generator construction** – The `EncodeTypes.Pdf417` enum value tells
      Aspose which symbology to use; swapping it for `EncodeTypes.QR` would give you
      a QR code instead.'
    text: '**Generator construction** – The `EncodeTypes.Pdf417` enum value tells
      Aspose which symbology to use; swapping it for `EncodeTypes.QR` would give you
      a QR code instead.'
  - name: '**X‑dimension** – This controls the width of each module (the tiny squares
      that make up the barcode). A value of `2` pixels yields a crisp image that’s
      still readable when printed at 300 dpi.'
    text: '**X‑dimension** – This controls the width of each module (the tiny squares
      that make up the barcode). A value of `2` pixels yields a crisp image that’s
      still readable when printed at 300 dpi.'
  - name: '**PDF417 options** – `Columns` influences the barcode’s aspect ratio; fewer
      columns make the image taller, which can be useful for receipts. `Truncate`
      (also called *Compact mode*) removes the start/stop pattern padding, reducing
      file size without sacrificing data integrity.'
    text: '**PDF417 options** – `Columns` influences the barcode’s aspect ratio; fewer
      columns make the image taller, which can be useful for receipts. `Truncate`
      (also called *Compact mode*) removes the start/stop pattern padding, reducing
      file size without sacrificing data integrity.'
  - name: '**Output path** – Using `Environment.CurrentDirectory` ensures the image
      lands next to the executable, making it easy to locate during development.'
    text: '**Output path** – Using `Environment.CurrentDirectory` ensures the image
      lands next to the executable, making it easy to locate during development.'
  - name: '**Saving** – `BarCodeImageFormat.Png` gives lossless quality, perfect for
      further processing or embedding in PDFs.'
    text: '**Saving** – `BarCodeImageFormat.Png` gives lossless quality, perfect for
      further processing or embedding in PDFs.'
  type: HowTo
tags:
- barcode
- pdf417
- csharp
title: Générer un code‑barres PDF417 en C# – Créer un code‑barres PDF417 en C#
url: /fr/net/compact-pdf417-encoding/generate-pdf417-barcode-in-c-create-pdf417-barcode-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Générer un code‑barres PDF417 en C# – Guide complet de programmation

Vous vous êtes déjà demandé comment **générer un code‑barres PDF417** dans une application C# sans parcourir d'innombrables fils de discussion ? Vous n'êtes pas le seul. Que vous construisiez un système de billetterie, une carte d'identité sécurisée, ou que vous ayez simplement besoin d'un moyen rapide d'intégrer des données dans un format imprimable, maîtriser le format PDF417 peut vous faire gagner des heures d'essais et d'erreurs.

Dans ce guide, nous parcourrons un **exemple complet, prêt à l'exécution** qui vous montre exactement comment **créer un code‑barres PDF417 en C#** en utilisant la populaire bibliothèque Aspose.BarCode. Nous couvrirons tout, de l'installation du package NuGet à l'ajustement du mode compact, afin que vous puissiez copier‑coller le code et voir les résultats immédiatement.

## Ce que vous allez apprendre

- Comment configurer la bibliothèque Aspose.BarCode dans un projet .NET.  
- Les instructions C# exactes nécessaires pour **générer un code‑barres PDF417** avec du texte personnalisé, une taille de module et un nombre de colonnes.  
- Pourquoi activer l'option *Compact* (Truncate) est important pour les données denses.  
- Comment enregistrer le code‑barres au format PNG et vérifier le résultat.  

Aucune expérience préalable en codes‑barres n'est requise ; il suffit d'une compréhension de base de C# et de Visual Studio (ou de tout IDE de votre choix). À la fin, vous disposerez d'une méthode réutilisable que vous pourrez intégrer à n'importe quel projet nécessitant une image PDF417.

## Prérequis

| Requirement | Why it matters |
|-------------|----------------|
| .NET 6.0 or later (or .NET Framework 4.7+) | Aspose.BarCode prend en charge les deux ; les environnements d'exécution plus récents offrent de meilleures performances. |
| Visual Studio 2022 (or VS Code with C# extensions) | Fournit IntelliSense et un débogage facile. |
| Internet connection (for the first NuGet restore) | La bibliothèque est récupérée depuis NuGet.org. |
| Basic C# knowledge | Nécessaire pour comprendre les structures de classe et les appels de méthodes. |

Si vous avez déjà tout cela, super—plongeons‑nous.

## Installer le package NuGet Aspose.BarCode

Ouvrez le dossier de votre projet dans un terminal et exécutez :

```bash
dotnet add package Aspose.BarCode
```

Ou, dans Visual Studio, faites un clic droit sur **Dependencies → Manage NuGet Packages**, recherchez *Aspose.BarCode*, puis cliquez sur **Install**. Cette seule ligne ajoute tous les types que nous utiliserons, y compris `BarcodeGenerator`, `EncodeTypes` et `BarCodeImageFormat`.

> **Astuce :** Après l'installation, nettoyez et reconstruisez la solution pour vous assurer que l'assembly est correctement référencé.

## Générer le code‑barres PDF417 – Configuration et dépendances

Première chose à faire : nous avons besoin d'un bloc `using` qui importe les espaces de noms pertinents.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;
```

Ces espaces de noms nous donnent accès à la classe du générateur et à l'énumération des types de codes‑barres. Rien de compliqué—juste trois lignes, et nous sommes prêts à commencer à créer le code‑barres.

## Créer un code‑barres PDF417 en C# – Implémentation étape par étape

Ci-dessous se trouve un **programme console autonome** qui crée un code‑barres PDF417 compact à partir de la chaîne `"Åspóse.Barcóde©"` et l'enregistre sous le nom `CompactPdf417.png`. N'hésitez pas à remplacer le texte par ce que vous voulez ; le générateur gère les caractères Unicode dès le départ.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

namespace Pdf417Demo
{
    class Program
    {
        static void Main(string[] args)
        {
            // 1️⃣ Define the data you want to encode.
            string data = "Åspóse.Barcóde©";

            // 2️⃣ Initialise the generator for PDF417.
            //    EncodeTypes.Pdf417 tells Aspose we want a PDF417 barcode.
            BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, data);

            // 3️⃣ Adjust the module (X‑dimension) size.
            //    Smaller values give a tighter image; 2 pixels works well for most screens.
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // 4️⃣ Configure PDF417‑specific options.
            //    • Columns = 3 → fewer columns, taller barcode.
            //    • Truncate = true → enables Compact mode, which removes unnecessary padding.
            generator.Parameters.Barcode.Pdf417.Columns = 3;
            generator.Parameters.Barcode.Pdf417.Truncate = true;

            // 5️⃣ Choose the output folder – adjust as needed.
            string outputPath = System.IO.Path.Combine(
                Environment.CurrentDirectory, "CompactPdf417.png");

            // 6️⃣ Save the image as PNG.
            generator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"✅ PDF417 barcode saved to: {outputPath}");
        }
    }
}
```

### Pourquoi chaque étape est importante

1. **Définition des données** – PDF417 peut stocker jusqu'à ~1850 caractères, mais nous le gardons court pour la démo. La prise en charge Unicode signifie que ces caractères accentués ne casseront rien.  
2. **Construction du générateur** – La valeur d'énumération `EncodeTypes.Pdf417` indique à Aspose quelle symbologie utiliser ; la remplacer par `EncodeTypes.QR` vous donnerait un code QR à la place.  
3. **X‑dimension** – Cela contrôle la largeur de chaque module (les petits carrés qui composent le code‑barres). Une valeur de `2` pixels donne une image nette qui reste lisible lorsqu'elle est imprimée à 300 dpi.  
4. **Options PDF417** – `Columns` influence le ratio d'aspect du code‑barres ; moins de colonnes rendent l'image plus haute, ce qui peut être utile pour les reçus. `Truncate` (également appelé *mode Compact*) supprime le remplissage du motif de début/fin, réduisant la taille du fichier sans sacrifier l'intégrité des données.  
5. **Chemin de sortie** – Utiliser `Environment.CurrentDirectory` garantit que l'image se trouve à côté de l'exécutable, ce qui facilite son localisation pendant le développement.  
6. **Enregistrement** – `BarCodeImageFormat.Png` offre une qualité sans perte, parfaite pour un traitement ultérieur ou l'intégration dans des PDF.  

Exécutez le programme (`dotnet run` ou appuyez sur **F5** dans Visual Studio). Après quelques secondes, vous devriez voir un message console confirmant l'emplacement du fichier, et le PNG apparaîtra dans le dossier de votre projet.

![exemple de génération de code‑barres PDF417 – image PNG d'un code‑barres PDF417 compact créé avec C#](generated-pdf417.png)

*Texte alternatif de l'image : exemple de génération de code‑barres PDF417 – image PNG d'un code‑barres PDF417 compact créé avec C#.*

## Configurer le mode Compact – Options du générateur de code‑barres PDF417 en C#

Si vous avez besoin d'un code‑barres plus grand (peut-être pour une lecture à distance), ajustez les propriétés `Columns` et `Rows`. Voici un extrait rapide qui montre des configurations alternatives :

```csharp
// Increase columns for a wider, shorter barcode.
generator.Parameters.Barcode.Pdf417.Columns = 6;

// Disable Compact mode if the scanning hardware struggles with it.
generator.Parameters.Barcode.Pdf417.Truncate = false;

// Optionally set error correction level (0–8). Higher values increase redundancy.
generator.Parameters.Barcode.Pdf417.ErrorCorrectionLevel = 5;
```

> **Question fréquente :** *La désactivation de Truncate casse-t-elle les scanners existants ?*  
> Généralement non. La plupart des scanners modernes comprennent à la fois le PDF417 plein format et le compact. Cependant, si vous ciblez du matériel hérité, laissez `Truncate` à `false`.

## Enregistrer et vérifier – comment générer la sortie du code‑barres PDF417

Après l'enregistrement, vous pouvez ouvrir le PNG avec n'importe quel visualiseur d'images. Pour vérifier que le code‑barres encode les données prévues, utilisez le `BarCodeReader` d'Aspose :



## Que devriez‑vous apprendre ensuite ?

Les tutoriels suivants couvrent des sujets étroitement liés qui s'appuient sur les techniques démontrées dans ce guide. Chaque ressource comprend des exemples de code complets et fonctionnels avec des explications étape par étape pour vous aider à maîtriser des fonctionnalités API supplémentaires et explorer des approches d'implémentation alternatives dans vos propres projets.

- [Comment créer un code‑barres – PDF417 compact avec Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [Comment générer un code‑barres Aztec avec un ratio d'aspect personnalisé en utilisant Aspose.BarCode pour .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)
- [Bibliothèque de code‑barres Java – Ajouter un code‑barres à un PDF avec Aspose](/barcode/english/java/barcode-basics/adding-barcode-to-pdf-document/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}