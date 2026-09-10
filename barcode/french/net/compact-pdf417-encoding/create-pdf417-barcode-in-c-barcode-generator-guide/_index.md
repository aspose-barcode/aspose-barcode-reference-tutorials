---
category: general
date: 2026-07-18
description: Créer un code‑barres PDF417 en C# à l'aide du générateur de code‑barres
  PDF417 en C#. Suivez un tutoriel étape par étape pour générer un texte de code étendu,
  définir l'apparence et enregistrer l'image.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create pdf417 barcode
- c# pdf417 barcode generator
language: fr
lastmod: 2026-07-18
og_description: Créez un code‑barres PDF417 en C# instantanément. Ce guide montre
  comment utiliser le générateur de code‑barres PDF417 en C#, configurer le mode étendu
  et exporter un PNG.
og_image_alt: Generated PDF417 barcode image created with C# PDF417 barcode generator
og_title: Créer un code‑barres PDF417 en C# – Guide complet du générateur
schemas:
- author: Aspose
  dateModified: '2026-07-18'
  description: Create PDF417 barcode in C# using the C# PDF417 barcode generator.
    Follow a step‑by‑step tutorial to build extended codetext, set appearance, and
    save the image.
  headline: Create PDF417 Barcode in C# – Barcode Generator Guide
  type: TechArticle
- description: Create PDF417 barcode in C# using the C# PDF417 barcode generator.
    Follow a step‑by‑step tutorial to build extended codetext, set appearance, and
    save the image.
  name: Create PDF417 Barcode in C# – Barcode Generator Guide
  steps:
  - name: 1. Install the barcode library
    text: 'Open your terminal in the project folder and run:'
  - name: 2. Build the extended codetext
    text: 'PDF417 supports **extended encoding**, allowing you to mix different character
      sets in a single barcode. Below we create three segments:'
  - name: 3. Initialise the **C# PDF417 barcode generator**
    text: Now that we have a valid codetext string, we hand it to the generator. The
      `using` statement ensures the underlying resources are released automatically.
  - name: 4. Configure appearance and encoding mode
    text: 'The default settings give you a tiny barcode that might be hard to read.
      Let’s tweak a few parameters:'
  - name: 5. Save the barcode image
    text: Finally, write the image to disk. The library supports PNG, JPEG, BMP, and
      several vector formats—PNG is a safe default because it preserves crisp edges.
  - name: Handling Unicode and special characters
    text: When you feed Unicode symbols directly into a plain‑text barcode, the generator
      may fall back to a fallback encoding, resulting in garbled output. By using
      `AddECICodetext` you explicitly tell the encoder which character set to apply,
      eliminating guesswork. If you ever need to support **Arabic**, **
  - name: Adjusting error correction level
    text: 'PDF417 offers four error‑correction levels (0‑8). Higher levels increase
      resilience but also enlarge the barcode. Adjust it via:'
  - name: Scaling for print vs. screen
    text: 'For on‑screen display you might keep the default 96 dpi. For high‑resolution
      printing (300 dpi or more), set:'
  - name: Common pitfalls
    text: '- **Missing `using` directive** – Forgetting `using Aspose.BarCode.Encoding;`
      will cause `ECIEncodings` to be undefined. - **Directory not found** – The `Save`
      method won’t create intermediate folders; create them beforehand or use `Path.Combine`
      with `Environment.CurrentDirectory`. - **Wrong encode'
  type: HowTo
tags:
- barcode
- pdf417
- csharp
title: Créer un code‑barres PDF417 en C# – Guide du générateur de codes‑barres
url: /fr/net/compact-pdf417-encoding/create-pdf417-barcode-in-c-barcode-generator-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Créer un code-barres PDF417 en C# – Guide du générateur de code-barres

Vous avez déjà eu besoin de **créer un code-barres PDF417** dans une application C# mais vous ne saviez pas par où commencer ? Vous n'êtes pas seul—de nombreux développeurs rencontrent le même obstacle lorsqu'ils abordent pour la première fois les codes-barres bidimensionnels. Bonne nouvelle ? Avec le **générateur de code-barres PDF417 C#** intégré, vous pouvez générer un code-barres complet en quelques lignes seulement.

Dans ce tutoriel, nous parcourrons l’ensemble du processus : construire un texte de code étendu qui mélange différents jeux de caractères, configurer le générateur pour le style visuel approprié, et enfin enregistrer le code-barres sous forme de fichier PNG. À la fin, vous disposerez d’un extrait prêt à l’emploi que vous pourrez intégrer à n’importe quel projet .NET, ainsi que de conseils pour gérer les cas limites comme les caractères Unicode ou les largeurs de module personnalisées.

---

## Ce dont vous avez besoin

- **.NET 6.0** ou version ultérieure (l’exemple fonctionne également avec .NET Framework 4.6+)
- **Aspose.BarCode for .NET** (ou toute bibliothèque compatible exposant `BarcodeGenerator`, `EncodeTypes.Pdf417`, etc.)
- Un éditeur de code — Visual Studio, Rider, ou même VS Code convient
- Un dossier dans lequel vous pouvez écrire, car le générateur enregistrera le PNG à cet endroit

C’est tout—aucun package NuGet supplémentaire en dehors de la bibliothèque de code-barres elle‑même.

## Guide étape par étape pour **créer un code-barres PDF417**

### 1. Installer la bibliothèque de code-barres

Ouvrez votre terminal dans le dossier du projet et exécutez :

```bash
dotnet add package Aspose.BarCode
```

Le package ajoute l’espace de noms `Aspose.BarCode`, qui contient la classe `BarcodeGenerator` que nous utiliserons tout au long du tutoriel.

### 2. Construire le texte de code étendu

PDF417 prend en charge **l’encodage étendu**, vous permettant de mélanger différents jeux de caractères dans un même code-barres. Ci‑dessous, nous créons trois segments :

- Un segment Windows‑1251 (cyrillique)
- Un segment UTF‑8 contenant des caractères Unicode (les kanjis japonais pour « dog » et « right »)
- Un segment texte brut

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode.Encoding;

// Step 1: Build the extended codetext for the PDF417 barcode
Pdf417ExtCodetextBuilder builder = new Pdf417ExtCodetextBuilder();

// Add a Win1251‑encoded segment
builder.AddECICodetext(ECIEncodings.Win1251, "Will");

// Add a UTF‑8 segment with Unicode characters
builder.AddECICodetext(ECIEncodings.UTF8, "犬Right狗");

// Add a plain‑text segment
builder.AddPlainCodetext("Plain text");

// Retrieve the combined codetext string
string extendedCodetext = builder.GetExtendedCodetext();
```

**Pourquoi c’est important :**  
Si vous n’utilisez que du texte brut, vous êtes limité au sous‑ensemble ASCII par défaut. En déclarant explicitement des segments ECI (Extended Channel Interpretation), vous garantissez que les lecteurs interprètent chaque partie correctement, quelle que soit la langue ou les symboles utilisés.

### 3. Initialiser le **générateur de code-barres PDF417 C#**

Maintenant que nous disposons d’une chaîne de texte de code valide, nous la transmettons au générateur. L’instruction `using` garantit que les ressources sous‑jacentes sont libérées automatiquement.

```csharp
// Step 2: Create a PDF417 barcode generator using the extended codetext
using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, extendedCodetext))
{
    // Configuration goes here (see next step)
}
```

### 4. Configurer l’apparence et le mode d’encodage

Les paramètres par défaut vous donnent un code-barres minuscule qui peut être difficile à lire. Ajustons quelques paramètres :

- **X‑Dimension** – contrôle la largeur de chaque module (taille du pixel)
- **EncodeMode** – indique au moteur de traiter l’entrée en mode étendu
- **TwoDDisplayText** – texte lisible par l’homme affiché sous le code-barres (optionnel)

```csharp
    // Step 3: Configure barcode appearance and encoding mode
    generator.Parameters.Barcode.XDimension.Pixels = 15; // Wider modules for better scannability
    generator.Parameters.Barcode.Pdf417.EncodeMode = Pdf417EncodeMode.Extended; // Activate extended encoding
    generator.Parameters.Barcode.CodeTextParameters.TwoDDisplayText = "Extended mode"; // Display text under the symbol
```

**Astuce pro :** Si vous imprimez le code-barres sur une imprimante d’étiquettes, augmentez le `XDimension` à 20 px ou plus ; la plupart des lecteurs apprécient un peu d’espace supplémentaire.

### 5. Enregistrer l’image du code-barres

Enfin, écrivez l’image sur le disque. La bibliothèque prend en charge PNG, JPEG, BMP et plusieurs formats vectoriels—PNG est une valeur sûre car il conserve des bords nets.

```csharp
    // Step 4: Save the generated barcode image
    generator.Save("YOUR_DIRECTORY/Pdf417Extended.png", BarCodeImageFormat.Png);
}
```

Assurez‑vous que `YOUR_DIRECTORY` existe et est accessible en écriture. Après l’exécution du programme, vous devriez voir un fichier similaire à la capture d’écran ci‑dessous.

![Code-barres PDF417 généré avec le générateur de code-barres PDF417 C#](https://example.com/images/pdf417-extended.png "Code-barres PDF417 généré avec le générateur de code-barres PDF417 C#")

---

## Utiliser le **générateur de code-barres PDF417 C#** – approfondissement

### Gestion des caractères Unicode et spéciaux

Lorsque vous insérez directement des symboles Unicode dans un code-barres texte brut, le générateur peut recourir à un encodage de secours, ce qui entraîne une sortie illisible. En utilisant `AddECICodetext`, vous indiquez explicitement à l’encodeur quel jeu de caractères appliquer, éliminant ainsi les suppositions. Si vous devez prendre en charge **Arabic**, **Hebrew**, ou **emoji**, choisissez simplement la valeur `ECIEncodings` appropriée.

### Ajustement du niveau de correction d’erreurs

PDF417 propose quatre niveaux de correction d’erreurs (0‑8). Des niveaux plus élevés augmentent la résilience mais agrandissent également le code-barres. Ajustez-le via :

```csharp
generator.Parameters.Barcode.Pdf417.ErrorCorrectionLevel = 5; // Balanced level
```

### Mise à l’échelle pour l’impression vs. l’écran

Pour l’affichage à l’écran, vous pouvez conserver la valeur par défaut de 96 dpi. Pour une impression haute résolution (300 dpi ou plus), définissez :

```csharp
generator.Parameters.ImageResolution = 300;
```

Cela garantit que le PNG enregistré conserve suffisamment de détails pour les imprimantes laser.

### Pièges courants

- **Missing `using` directive** – Oublier `using Aspose.BarCode.Encoding;` entraînera l’indéfinition de `ECIEncodings`.
- **Directory not found** – La méthode `Save` ne créera pas les dossiers intermédiaires ; créez‑les au préalable ou utilisez `Path.Combine` avec `Environment.CurrentDirectory`.
- **Wrong encode mode** – Si vous laissez `EncodeMode` à `Pdf417EncodeMode.Auto`, la bibliothèque peut traiter votre texte de code étendu comme du texte brut, en supprimant les marqueurs ECI.

---

## Exemple complet, prêt à l’exécution

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode.Encoding;

class Program
{
    static void Main()
    {
        // 1️⃣ Build extended codetext
        Pdf417ExtCodetextBuilder builder = new Pdf417ExtCodetextBuilder();
        builder.AddECICodetext(ECIEncodings.Win1251, "Will");
        builder.AddECICodetext(ECIEncodings.UTF8, "犬Right狗");
        builder.AddPlainCodetext("Plain text");
        string extendedCodetext = builder.GetExtendedCodetext();

        // 2️⃣ Initialise generator with the extended codetext
        using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, extendedCodetext))
        {
            // 3️⃣ Configure appearance
            generator.Parameters.Barcode.XDimension.Pixels = 15;
            generator.Parameters.Barcode.Pdf417.EncodeMode = Pdf417EncodeMode.Extended;
            generator.Parameters.Barcode.Pdf417.ErrorCorrectionLevel = 5;
            generator.Parameters.Barcode.CodeTextParameters.TwoDDisplayText = "Extended mode";

            // 4️⃣ Save to PNG (ensure the folder exists)
            string outputPath = System.IO.Path.Combine(
                Environment.CurrentDirectory, "Pdf417Extended.png");
            generator.Save(outputPath, BarCodeImageFormat.Png);
        }

        Console.WriteLine("PDF417 barcode generated successfully!");
    }
}
```

## Que devriez‑vous apprendre ensuite ?

Les tutoriels suivants couvrent des sujets étroitement liés qui s’appuient sur les techniques démontrées dans ce guide. Chaque ressource comprend des exemples de code complets et fonctionnels avec des explications étape par étape pour vous aider à maîtriser des fonctionnalités API supplémentaires et explorer des approches d’implémentation alternatives dans vos propres projets.

- [How to Create Barcode – Compact PDF417 with Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [How to create dotcode extended codetext with Aspose.BarCode for .NET](/barcode/english/net/dotcode-barcode-configuration/dotcode-extended-code-text-configuration/)
- [Create barcode image c# – Configure Codablock F Rows & Columns](/barcode/english/net/codablock-f-encoding/codablock-f-row-column-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}