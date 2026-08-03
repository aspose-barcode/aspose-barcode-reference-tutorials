---
category: general
date: 2026-08-03
description: Générez un code‑barres PDF417 en C# avec Aspose.BarCode. Apprenez étape
  par étape comment ajouter des métadonnées Macro PDF417 et enregistrer en PNG.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate PDF417 barcode C#
- Macro PDF417 barcode
- Aspose.BarCode
- C# barcode generation
- PDF417 metadata
- barcode image PNG
language: fr
lastmod: 2026-08-03
og_description: Générez un code‑barres PDF417 en C# avec Aspose.BarCode. Ce tutoriel
  montre comment intégrer les métadonnées Macro PDF417 et exporter le résultat sous
  forme d’image PNG.
og_image_alt: Screenshot of a generated PDF417 barcode created with C#
og_title: Générer un code‑barres PDF417 C# – tutoriel pas à pas Aspose.BarCode
schemas:
- author: Aspose
  dateModified: '2026-08-03'
  description: Generate PDF417 barcode C# using Aspose.BarCode. Learn step‑by‑step
    how to add Macro PDF417 metadata and save as PNG.
  headline: Generate PDF417 barcode C# – complete guide with Aspose.BarCode
  type: TechArticle
- description: Generate PDF417 barcode C# using Aspose.BarCode. Learn step‑by‑step
    how to add Macro PDF417 metadata and save as PNG.
  name: Generate PDF417 barcode C# – complete guide with Aspose.BarCode
  steps:
  - name: Create a Macro PDF417 barcode generator
    text: First, instantiate `BarcodeGenerator` with the `EncodeTypes.MacroPdf417`
      enum. The constructor also accepts the text you want to encode – in this example
      we use a string that contains Unicode characters to demonstrate full‑width support.
  - name: Adjust basic barcode appearance
    text: Next, define the visual size of the barcode. `XDimension.Pixels` controls
      the width of a single module (the smallest black/white square), while `Pdf417.Columns`
      influences the overall shape by setting the number of columns.
  - name: Populate Macro PDF417 metadata
    text: Macro PDF417 allows you to embed file‑level information that many back‑office
      systems rely on (e.g., file ID, segment ID, timestamp). The following properties
      illustrate the most common fields.
  - name: Save the barcode image as PNG
    text: Finally, call `Save` to write the barcode to disk. PNG is lossless, making
      it ideal for high‑quality scanning.
  - name: How to verify the result
    text: 1. Open `ExtPDF417Meta.png` in any image viewer. 2. Use a PDF417 scanner
      app (e.g., *Zebra Scanner* or *BarCode Reader* on Android/iOS). 3. Confirm that
      the decoded payload includes the original text and a JSON‑like block with the
      macro fields you set.
  - name: Next steps
    text: '- Experiment with other barcode formats (e.g., QR, Code128) by changing
      `EncodeTypes`. - Explore `Pdf417.ErrorCorrectionLevel` to improve scan reliability
      under poor lighting. - Integrate the generated image into a PDF report using
      Aspose.PDF for end‑to‑end document automation.'
  type: HowTo
tags:
- PDF417
- C#
- Barcode
title: Générer un code‑barres PDF417 C# – guide complet avec Aspose.BarCode
url: /fr/net/compact-pdf417-encoding/generate-pdf417-barcode-c-complete-guide-with-aspose-barcode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Générer un code‑barres PDF417 C# – guide complet

Si vous devez **générer un code‑barres PDF417 C#** pour un système logistique ou de gestion de documents, ce tutoriel vous montre exactement comment le faire avec Aspose.BarCode. Vous verrez comment configurer le code‑barres, intégrer les métadonnées Macro PDF417, et enregistrer le résultat sous forme d’image PNG en quelques lignes de code.

Générer un code‑barres PDF417 en C# implique souvent de gérer des informations supplémentaires telles que les identifiants de fichier, les numéros de segment ou les horodatages. Ce guide couvre ces détails, afin que vous n'ayez pas à chercher dans une documentation dispersée. À la fin de l'article, vous disposerez d'un programme prêt à l'emploi qui produit une image de code‑barres Macro PDF417 conforme.

## Ce dont vous avez besoin

- .NET 6.0 ou ultérieur (le code fonctionne également avec .NET Framework 4.7+)
- Aspose.BarCode pour .NET (v23.9 ou plus récent) – installer via NuGet `Install-Package Aspose.BarCode`
- Un environnement de développement tel que Visual Studio 2022 ou Visual Studio Code
- Familiarité de base avec la syntaxe C#

> **Astuce :** Utilisez la dernière version d’Aspose.BarCode pour profiter des corrections de bugs et du support des dernières spécifications PDF417.

## Comment générer un code‑barres PDF417 C# avec Aspose.BarCode

Le processus se compose de quatre étapes logiques. Chaque étape est encapsulée dans un bloc de code clair afin que vous puissiez copier, coller et l’exécuter immédiatement.

### Étape 1 : Créer un générateur de code‑barres Macro PDF417

Tout d'abord, instanciez `BarcodeGenerator` avec l'énumération `EncodeTypes.MacroPdf417`. Le constructeur accepte également le texte que vous souhaitez encoder – dans cet exemple nous utilisons une chaîne contenant des caractères Unicode pour démontrer la prise en charge des largeurs complètes.

```csharp
using System;
using Aspose.BarCode.Generation;

// Create a Macro PDF417 barcode generator with the desired text
using (BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
           EncodeTypes.MacroPdf417,
           "Åspóse.Barcóde©"))
{
    // Subsequent steps go inside this using block
```

*Pourquoi c’est important* : Le type `MacroPdf417` indique à Aspose.BarCode de traiter le symbole comme un code‑barres macro, qui peut contenir des métadonnées supplémentaires au niveau du fichier. Sans ce drapeau, les champs supplémentaires que vous définissez plus tard seraient ignorés.

### Étape 2 : Ajuster l’apparence de base du code‑barres

Ensuite, définissez la taille visuelle du code‑barres. `XDimension.Pixels` contrôle la largeur d’un seul module (le plus petit carré noir/blanc), tandis que `Pdf417.Columns` influence la forme globale en définissant le nombre de colonnes.

```csharp
    // Adjust basic barcode appearance
    barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;   // size of a single module
    barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 5;    // number of columns in the symbol
```

*Pourquoi c’est important* : Un `XDimension` plus petit produit une image à plus haute résolution, ce qui est utile lorsque le code‑barres doit être scanné depuis un écran. Modifier le nombre de colonnes peut aider à adapter le code‑barres à un espace limité sans sacrifier la capacité de données.

### Étape 3 : Remplir les métadonnées Macro PDF417

Macro PDF417 vous permet d’intégrer des informations au niveau du fichier dont de nombreux systèmes back‑office dépendent (par ex., ID de fichier, ID de segment, horodatage). Les propriétés suivantes illustrent les champs les plus courants.

```csharp
    // Populate Macro PDF417 metadata
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234;          // CCITT‑16 example
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400_000;
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = new DateTime(2019, 11, 1);
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;
```

*Pourquoi c’est important* : Chaque champ correspond directement à un segment de la spécification du code‑barres macro. Par exemple, `MacroPdf417FileID` identifie de façon unique le fichier logique, tandis que `MacroPdf417SegmentsCount` indique au lecteur combien de parties attendre. Fournir des métadonnées précises garantit que les systèmes en aval peuvent reconstruire le document original sans erreur.

### Étape 4 : Enregistrer l’image du code‑barres au format PNG

Enfin, appelez `Save` pour écrire le code‑barres sur le disque. PNG est sans perte, ce qui le rend idéal pour une numérisation de haute qualité.

```csharp
    // Save the barcode image as PNG
    barcodeGenerator.Save("YOUR_DIRECTORY/ExtPDF417Meta.png", BarCodeImageFormat.Png);
}
```

*Pourquoi c’est important* : L’énumération `BarCodeImageFormat.Png` garantit que le fichier de sortie contient exactement les données de pixels que vous avez configurées. Si vous avez besoin d’un format vectoriel pour le redimensionnement, remplacez `Png` par `Svg` – Aspose.BarCode le prend en charge nativement.

#### Résultat attendu

L’exécution du programme complet crée un fichier nommé **ExtPDF417Meta.png**. L’image montre un symbole PDF417 dense et multi‑lignes qui inclut le texte « Åspóse.Barcóde© » ainsi que les métadonnées macro que vous avez fournies. Scanner le code‑barres avec un lecteur compatible PDF417 renvoie le texte original plus un bloc de données structuré contenant l’ID du fichier, l’ID du segment, l’horodatage et d’autres champs.

![Capture d’écran du code‑barres PDF417 généré](/images/pdf417-example.png){: .center-image alt="exemple de sortie de génération de code‑barres PDF417 C#"}

## Code source complet (prêt à copier‑coller)

```csharp
using System;
using Aspose.BarCode.Generation;

namespace Pdf417MacroDemo
{
    class Program
    {
        static void Main()
        {
            // Step 1: Create a Macro PDF417 barcode generator with the desired text
            using (BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
                       EncodeTypes.MacroPdf417,
                       "Åspóse.Barcóde©"))
            {
                // Step 2: Adjust basic barcode appearance
                barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;   // size of a single module
                barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 5;    // number of columns in the symbol

                // Step 3: Populate Macro PDF417 metadata
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234;          // CCITT‑16 example
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400_000;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = new DateTime(2019, 11, 1);
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;

                // Step 4: Save the barcode image as PNG
                barcodeGenerator.Save("YOUR_DIRECTORY/ExtPDF417Meta.png", BarCodeImageFormat.Png);
            }

            Console.WriteLine("Macro PDF417 barcode generated successfully.");
        }
    }
}
```

### Comment vérifier le résultat

1. Ouvrez `ExtPDF417Meta.png` dans n’importe quel visualiseur d’images.  
2. Utilisez une application de scanner PDF417 (par ex., *Zebra Scanner* ou *BarCode Reader* sur Android/iOS).  
3. Confirmez que la charge décodée comprend le texte original et un bloc de type JSON contenant les champs macro que vous avez définis.

## Questions fréquentes et gestion des cas limites

| Question | Réponse |
|----------|--------|
| **Puis‑je générer une image vectorielle au lieu de PNG ?** | Oui. Remplacez `BarCodeImageFormat.Png` par `BarCodeImageFormat.Svg`. Le reste du code reste inchangé. |
| **Que faire si mes données dépassent la capacité par défaut ?** | Augmentez `Pdf417.Columns` ou définissez `Pdf417.Rows` manuellement. Des valeurs plus grandes permettent plus de codewords par segment. |
| **Le texte encodé prend‑t‑il en charge Unicode ?** | Absolument. L’exemple utilise « Åspóse.Barcóde© ». Aspose.BarCode passe automatiquement à l’encodage UTF‑8 lorsque nécessaire. |
| **Dois‑je obtenir une licence pour Aspose.BarCode ?** | En production, vous devez appliquer une licence pour éviter le filigrane d’évaluation. Appelez `License license = new License(); license.SetLicense("Aspose.BarCode.lic");` avant de créer le générateur. |
| **Comment gérer les erreurs lors de l’enregistrement du fichier ?** | Enveloppez l’appel `Save` dans un bloc try/catch et consignez `IOException` ou `BarCodeException` pour le dépannage. |

## Conclusion

Vous savez maintenant comment **générer un code‑barres PDF417 C#** en utilisant Aspose.BarCode, intégrer des métadonnées complètes Macro PDF417, et exporter le résultat sous forme d’image PNG de haute qualité. Les étapes — création du générateur, ajustement de l’apparence, remplissage des métadonnées et enregistrement de l’image — constituent un modèle réutilisable que vous pouvez adapter pour les factures, les étiquettes d’expédition ou tout scénario nécessitant des données de code‑barres riches.

### Prochaines étapes

- Expérimentez d’autres formats de code‑barres (par ex., QR, Code128) en modifiant `EncodeTypes`.  
- Explorez `Pdf417.ErrorCorrectionLevel` pour améliorer la fiabilité du scan sous un éclairage faible.  
- Intégrez l’image générée dans un rapport PDF en utilisant Aspose.PDF pour une automatisation de documents de bout en bout.

N’hésitez pas à modifier les champs de métadonnées pour qu’ils correspondent à vos règles métier, et laissez la génération de code‑barres devenir une partie fluide de vos applications C#. Bon codage !

## Que devriez‑vous apprendre ensuite ?

Les tutoriels suivants couvrent des sujets étroitement liés qui s’appuient sur les techniques démontrées dans ce guide. Chaque ressource comprend des exemples de code complets et fonctionnels avec des explications étape par étape pour vous aider à maîtriser des fonctionnalités API supplémentaires et explorer des approches d’implémentation alternatives dans vos propres projets.

- [Comment créer un code‑barres – PDF417 compact avec Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [Comment créer un code‑barres – PDF417 compact avec Aspose.BarCode (allemand)](/barcode/german/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [Bibliothèque de code‑barres Java – Ajouter un code‑barres à un PDF avec Aspose](/barcode/english/java/barcode-basics/adding-barcode-to-pdf-document/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}