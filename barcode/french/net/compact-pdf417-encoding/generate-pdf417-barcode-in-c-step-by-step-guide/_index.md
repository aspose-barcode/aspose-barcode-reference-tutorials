---
category: general
date: 2026-08-09
description: Générez un code‑barres PDF417 en C# rapidement. Apprenez à générer du
  PDF417 en mode compact, avec contrôle des colonnes et sortie PNG en utilisant l’API
  BarcodeGenerator.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate pdf417 barcode
- how to generate pdf417
- create pdf417 barcode c#
- barcode generator c#
- compact pdf417 settings
- pdf417 png output
language: fr
lastmod: 2026-08-09
og_description: Générez un code‑barres PDF417 en C# avec un exemple concis. Ce guide
  vous montre comment configurer le mode compact, définir les colonnes et enregistrer
  le résultat en tant qu’image PNG.
og_image_alt: Generated PDF417 barcode image saved as PNG
og_title: Générer un code‑barres PDF417 en C# – tutoriel complet
schemas:
- author: Aspose
  dateModified: '2026-08-09'
  description: Generate PDF417 barcode in C# quickly. Learn how to generate PDF417
    with compact mode, column control, and PNG output using the BarcodeGenerator API.
  headline: Generate PDF417 barcode in C# – step‑by‑step guide
  type: TechArticle
tags:
- barcode
- pdf417
- C#
- Aspose.BarCode
title: Générer un code‑barres PDF417 en C# – guide pas à pas
url: /fr/net/compact-pdf417-encoding/generate-pdf417-barcode-in-c-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Générer un code‑barres PDF417 en C# – guide étape par étape

Si vous devez **générer un code‑barres PDF417** dans une application .NET, ce tutoriel vous montre exactement comment le faire. Vous verrez un programme complet et exécutable qui crée un code‑barres PDF417 compact, personnalise sa taille et enregistre l'image au format PNG.

La génération d'un code‑barres PDF417 est une exigence courante pour la billetterie mobile, le suivi d'inventaire et la sécurité des documents. Ce guide couvre les options de configuration essentielles, explique pourquoi chaque paramètre est important et fournit des conseils pratiques pour une utilisation en conditions réelles.

## Prérequis

* SDK .NET 6.0 ou version ultérieure installé  
* Un IDE C# tel que Visual Studio 2022 ou Visual Studio Code  
* Le package NuGet **Aspose.BarCode for .NET** (version 23.10 ou plus récente)  

Vous pouvez installer le package avec la commande CLI suivante :

```bash
dotnet add package Aspose.BarCode
```

Le code ci‑dessous suppose que le package est référencé et que vous disposez des droits d’écriture sur le répertoire de sortie.

## Étape 1 : Configurer le projet et importer les espaces de noms

Créez un nouveau projet console et ajoutez les directives `using` requises. Ces espaces de noms exposent la classe `BarcodeGenerator` et l’énumération des formats d’image.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;
using Aspose.BarCode.Image;
```

**Pourquoi c’est important :** Importer les bons espaces de noms garantit que le compilateur peut localiser le type `BarcodeGenerator` et l’énumération `BarCodeImageFormat`. L’absence d’un espace de noms entraîne une erreur de compilation, ce qui interrompt le processus de génération du code‑barres.

## Étape 2 : Initialiser le `BarcodeGenerator` avec l’encodage PDF417

Le constructeur `BarcodeGenerator` reçoit deux arguments : la symbologie du code‑barres (`EncodeTypes.Pdf417`) et le texte que vous souhaitez encoder. PDF417 prend en charge un large éventail de caractères, y compris les symboles Unicode.

```csharp
// Step 2: Create a PDF417 barcode generator with the desired text
var generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Åspóse.Barcóde©");
```

**Explication :**  
* `EncodeTypes.Pdf417` indique à la bibliothèque d’utiliser la norme PDF417.  
* Le texte d’exemple contient des caractères accentués et un symbole de copyright pour démontrer la prise en charge d’Unicode.  

Si vous devez encoder uniquement des données numériques, vous pouvez passer une chaîne simple comme `"1234567890"`.

## Étape 3 : Ajuster la X‑dimension pour une résolution plus fine

La X‑dimension contrôle la largeur d’un seul module du code‑barres (l’élément noir ou blanc le plus petit). Définir une valeur en pixels plus petite produit une image à plus haute résolution.

```csharp
// Step 3: Adjust the module (X) dimension for finer resolution
generator.Parameters.Barcode.XDimension.Pixels = 2;
```

**Pourquoi l’ajuster ?** Une X‑dimension par défaut de 3–4 pixels peut produire un code‑barres qui paraît grossier sur des écrans haute‑DPI. La réduire à **2 pixels** équilibre lisibilité et taille du fichier, surtout lorsque vous activez ensuite le mode compact.

## Étape 4 : Configurer le nombre de colonnes

PDF417 vous permet de spécifier le nombre de colonnes que le code‑barres doit contenir. Moins de colonnes rendent le code‑barres plus étroit mais plus haut, tandis que davantage de colonnes produisent un code‑barres plus large et plus court.

```csharp
// Step 4: Set the number of columns to control the barcode width
generator.Parameters.Barcode.Pdf417.Columns = 3;
```

**Conseil pratique :** Pour les billets mobiles qui doivent tenir sur une étiquette étroite, un nombre de colonnes de **3–5** fonctionne bien. Augmentez le nombre si vous avez beaucoup de données et souhaitez un code‑barres plus court.

## Étape 5 : Activer le mode compact pour tronquer les rangées vides

Le mode compact supprime les rangées inutiles de la matrice du code‑barres, réduisant la taille globale de l’image sans perdre les données encodées.

```csharp
// Step 5: Enable compact mode to truncate the barcode and reduce size
generator.Parameters.Barcode.Pdf417.Truncate = true;
```

**Quand l’utiliser :** Si vous générez des codes‑barres pour le stockage ou la transmission réseau, le mode compact peut réduire le fichier PNG jusqu’à 30 %. Cependant, certains lecteurs anciens peuvent ne pas prendre en charge le PDF417 tronqué ; testez avec votre matériel cible.

## Étape 6 : Enregistrer le code‑barres en image PNG

Choisissez un chemin de sortie et appelez `Save`. L’énumération `BarCodeImageFormat.Png` produit une image sans perte adaptée à la plupart des applications.

```csharp
// Step 6: Save the generated barcode as a PNG image
string outputPath = @"C:\Barcodes\CompactPdf417.png";
generator.Save(outputPath, BarCodeImageFormat.Png);
Console.WriteLine($"Barcode saved to {outputPath}");
```

**Vérification du résultat :** Ouvrez le fichier PNG dans n’importe quel visualiseur d’image. Vous devriez voir un code‑barres dense et à fort contraste qui correspond au texte d’exemple. Scanner l’image avec un lecteur PDF417 (par ex., ZXing ou une application smartphone) renvoie la chaîne originale `"Åspóse.Barcóde©"`.

![Image du code‑barres PDF417 généré enregistrée au format PNG](compact-pdf417.png "Code‑barres PDF417 généré en C#")

*L’image ci‑dessus montre le résultat final du code du tutoriel.*

## Exemple complet, exécutable

En assemblant tous les éléments, voici un programme console complet que vous pouvez copier, coller et exécuter.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;
using Aspose.BarCode.Image;

namespace Pdf417GeneratorDemo
{
    class Program
    {
        static void Main()
        {
            // 1️⃣ Create the generator with PDF417 encoding
            var generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Åspóse.Barcóde©");

            // 2️⃣ Fine‑tune module size for sharper output
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // 3️⃣ Set a narrow column count to keep the barcode slim
            generator.Parameters.Barcode.Pdf417.Columns = 3;

            // 4️⃣ Activate compact mode to drop empty rows
            generator.Parameters.Barcode.Pdf417.Truncate = true;

            // 5️⃣ Define where the PNG will be written
            string outputPath = @"C:\Barcodes\CompactPdf417.png";

            // 6️⃣ Save the image
            generator.Save(outputPath, BarCodeImageFormat.Png);
            Console.WriteLine($"Barcode saved to {outputPath}");
        }
    }
}
```

### Sortie attendue

L’exécution du programme affiche :

```
Barcode saved to C:\Barcodes\CompactPdf417.png
```

Le fichier `CompactPdf417.png` contient un code‑barres PDF417 compact qui encode la chaîne Unicode fournie. Scanner l’image avec un lecteur PDF417 standard renvoie le texte exact.

## Variantes courantes et cas limites

| Situation | Ajustement | Raison |
|-----------|------------|--------|
| **Charge de données plus longue** (p. ex., > 150 caractères) | Augmenter `generator.Parameters.Barcode.Pdf417.Columns` à 6‑8 | Plus de colonnes évitent que le code‑barres ne devienne excessivement haut. |
| **Besoin d’un arrière‑plan transparent** | Utiliser `generator.Save(outputPath, BarCodeImageFormat.Png, new ImageSaveOptions { BackgroundColor = Color.Transparent })` | Un PNG transparent s’intègre mieux aux superpositions d’interface. |
| **Générer du JPEG pour le web** | Modifier le format en `BarCodeImageFormat.Jpeg` et éventuellement définir `ImageQuality` | Le JPEG réduit la taille du fichier au prix d’une perte de fidélité sans perte. |
| **Gestion d’une entrée nulle ou vide** | Protéger l’entrée avant de créer le générateur : `if (string.IsNullOrEmpty(text)) throw new ArgumentException("Text cannot be empty.");` | Empêche les exceptions d’exécution et garantit des codes‑barres significatifs. |

## Conseils pour la mise en production

* **Gestion des exceptions :** Encapsulez la logique de génération dans un bloc `try/catch` pour consigner les erreurs telles que l’espace disque insuffisant ou des paramètres invalides.  
* **Performance :** Réutilisez une seule instance de `BarcodeGenerator` lors de la génération de nombreux codes‑barres avec les mêmes paramètres ; mettez simplement à jour la propriété `CodeText` entre les sauvegardes.  
* **Sécurité :** Lorsque le texte encodé contient des informations sensibles, envisagez de le chiffrer avant de le transmettre au générateur et de le déchiffrer après le scan.  

## Conclusion

Vous savez maintenant comment **générer un code‑barres PDF417** en C# en utilisant la bibliothèque Aspose.BarCode, configurer le mode compact, contrôler le nombre de colonnes et exporter le résultat sous forme d’image PNG. Ce tutoriel a couvert chaque étape, de la configuration du projet à la gestion des cas limites, vous offrant une solution prête à l’emploi pour les applications basées sur les codes‑barres.

Ensuite, explorez des sujets connexes tels que **la création de QR codes en C#**, **la génération de lots de codes‑barres**, et **l’intégration du scan de codes‑barres avec des applications mobiles**. Chacun de ces sujets repose sur les mêmes fondamentaux du `BarcodeGenerator` que vous venez de maîtriser.

Bon codage !

## Que devriez‑vous apprendre ensuite ?

Les tutoriels suivants couvrent des sujets étroitement liés qui s’appuient sur les techniques démontrées dans ce guide. Chaque ressource comprend des exemples de code complets et fonctionnels avec des explications étape par étape pour vous aider à maîtriser des fonctionnalités API supplémentaires et explorer des approches d’implémentation alternatives dans vos propres projets.

- [Comment générer des codes‑barres PDF417 – Encodage PDF417 compact](/barcode/english/net/compact-pdf417-encoding/)
- [Comment créer un code‑barres – PDF417 compact avec Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [Comment générer un code‑barres Aztec avec un rapport d’aspect personnalisé en utilisant Aspose.BarCode pour .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}