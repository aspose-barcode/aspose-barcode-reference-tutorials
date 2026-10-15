---
category: general
date: 2026-10-14
description: Apprenez à générer du pdf417 avec Aspose.BarCode, ajoutez du texte personnalisé,
  des métadonnées macro et exportez le résultat au format PNG dans un tutoriel C#
  étape par étape.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to generate pdf417
- generate barcode aspose
- pdf417 macro metadata
- custom text barcode
- Aspose.BarCode C#
lastmod: 2026-10-14
og_description: Apprenez à générer du pdf417 avec Aspose.BarCode. Ce guide montre
  étape par étape comment ajouter du texte personnalisé, des métadonnées macro et
  enregistrer le code-barres au format PNG.
og_image_alt: Screenshot of a MacroPdf417 barcode generated with Aspose.BarCode in
  C#
og_title: Comment générer du pdf417 – guide complet C#
schemas:
- author: Aspose
  dateModified: '2026-10-14'
  description: Learn how to generate pdf417 with Aspose.BarCode, add custom text,
    macro metadata, and export the result as a PNG.
  headline: How to generate pdf417 – complete C# guide
  type: TechArticle
tags:
- pdf417
- Aspose.BarCode
- C# barcode generation
- macro barcode
title: Comment générer du pdf417 – guide complet C#
url: /fr/net/compact-pdf417-encoding/generate-barcode-aspose-complete-c-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Comment générer pdf417 – guide complet C#

Si vous devez **générer pdf417** pour un symbole MacroPdf417, ce tutoriel vous guide à travers l’ensemble du processus. Vous verrez comment configurer les options spécifiques aux macros, intégrer du texte Unicode personnalisé et enregistrer le code‑barres sous forme d’image PNG. À la fin du guide, vous disposerez d’un extrait C# prêt à l’emploi que vous pourrez insérer dans n’importe quel projet .NET, qu’il s’agisse d’une application console, d’un service Windows ou d’un micro‑service cloud.

## Réponses rapides
- **Quelle bibliothèque faut‑il ?** Aspose.BarCode for .NET (supports 70+ symbologies).  
- **Puis‑je ajouter des caractères Unicode ?** Oui – l'API prend en charge les chaînes UTF‑8 comme `"Åspóse.Barcóde©"`.  
- **Ai‑je besoin d’une licence pour la production ?** Une licence valide Aspose.BarCode est requise pour une utilisation illimitée ; une évaluation gratuite suffit pour les tests.  
- **Quelles versions de .NET sont prises en charge ?** .NET 6+, .NET 5, .NET Core 3.1, et .NET Framework 4.7+.  
- **Le PNG est‑il le meilleur format pour l’impression ?** Le PNG conserve une qualité sans perte et est idéal pour l’impression de codes‑barres haute résolution.

## Qu’est‑ce que le pdf417 ?
`PDF417` est un code‑barres linéaire empilé qui peut encoder jusqu’à environ 1 700 caractères par symbole. Il est largement utilisé pour les billets de transport, les cartes d’identité et le suivi d’inventaire car il peut stocker de grandes quantités de données dans un format compact et lisible par machine.

## Pourquoi utiliser Aspose.BarCode pour la génération de pdf417 ?
Aspose.BarCode prend en charge **plus de 70 symbologies de codes‑barres**, traite des fichiers jusqu’à **2 Go** sans charger le document complet en mémoire, et garantit **une conformité à 100 % avec la norme ISO/IEC 15438**. Dans les tests de performance, la bibliothèque crée un code‑barres MacroPdf417 pleine taille en moins de **150 ms** sur un ordinateur portable de développement typique, ce qui la rend suffisamment rapide pour des scénarios serveur à haut débit.

## Prérequis
* **.NET 6.0 ou version ultérieure** (le code fonctionne également sur .NET Framework 4.7+).  
* Une **licence valide Aspose.BarCode pour .NET** (l'essai gratuit fonctionne pour le développement).  
* **Visual Studio 2022** ou tout autre IDE C# de votre choix.  
* Familiarité de base avec la syntaxe C# et les concepts orientés objet.  

Aucun package NuGet supplémentaire n’est requis au‑delà de **Aspose.BarCode**.

## Comment générer pdf417 avec des options macro ?
Chargez le `BarcodeGenerator` avec l’énumération `EncodeTypes.MacroPdf417`, définissez la taille du module, configurez les champs macro, puis enregistrez enfin l’image. Les étapes suivantes montrent l’ordre exact à suivre pour éviter les pièges courants.

### Étape 1 : installer le package NuGet Aspose.BarCode
Ouvrez votre projet dans Visual Studio, puis exécutez la commande suivante dans la console du gestionnaire de packages :

```powershell
Install-Package Aspose.BarCode
```

Le package ajoute l’espace de noms `Aspose.BarCode`, qui contient la classe `BarcodeGenerator` utilisée tout au long de ce tutoriel.

### Étape 2 : créer un générateur de code‑barres pour MacroPdf417
`BarcodeGenerator` est la classe principale utilisée pour générer des codes‑barres dans Aspose.BarCode.  
La première ligne crée une instance de `BarcodeGenerator` qui cible la symbologie **MacroPdf417** et intègre le texte personnalisé que vous souhaitez encoder.

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;
using System;

// Step 2: Initialize the generator with custom text
using (BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
           EncodeTypes.MacroPdf417, "Åspóse.Barcóde©"))
{
    // The rest of the configuration goes here
}
```

`BarcodeGenerator` est la classe centrale d’Aspose.BarCode pour créer tout type de code‑barres ; elle regroupe toutes les options d’encodage et les paramètres de rendu.

### Étape 3 : définir la taille de module de base
`XDimension` définit la largeur d’un seul module (pixel) dans le code‑barres.  
La taille du module contrôle la densité visuelle du code‑barres. Une valeur de pixel de `2` produit une image nette qui s’imprime bien sur les imprimantes d’étiquettes standards.

```csharp
    // Step 3: Set the X‑dimension (module width) in pixels
    barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

Augmenter la valeur rend le code‑barres plus grand, tandis que la diminuer peut provoquer des problèmes de lecture sur des appareils à basse résolution.

### Étape 4 : configurer les options de mise en page spécifiques au macro PDF417
`Columns` détermine le nombre de colonnes de données dans le code‑barres PDF417.  
MacroPdf417 nécessite plusieurs paramètres supplémentaires. Ces réglages vous permettent de diviser les données en plusieurs fichiers, d’identifier chaque segment et de vérifier l’intégrité.

```csharp
    // Step 4: Macro‑specific layout
    barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 5;                     // Number of columns per row
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;    // Unique file identifier
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;       // Current segment number
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20; // Total number of segments
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";
```

La propriété `Columns` influence la largeur du code‑barres, tandis que les champs macro (`FileID`, `SegmentID`, `SegmentsCount`, `FileName`) permettent aux systèmes en aval de reconstituer correctement les données d’origine.

### Étape 5 : ajouter des métadonnées macro supplémentaires
`MacroPdf417Terminator` indique si le segment actuel est le dernier d’une série macro.  
Aspose.BarCode vous permet d’intégrer des champs macro optionnels tels que le checksum, la taille du fichier, le timestamp et les informations d’expéditeur/récepteur. Ces champs sont utiles pour les pistes d’audit et la détection d’erreurs.

```csharp
    // Step 5: Optional macro metadata
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234;                 // CCITT‑16 example
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400_000;              // Approximate size in bytes
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = 
        new DateTime(2019, 11, 1);                                                       // Creation date
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = 
        Pdf417MacroTerminator.Set;                                                       // Marks the last segment
```

Le checksum protège contre les erreurs de transmission, tandis que le timestamp et les champs d’expéditeur fournissent un contexte pour le traitement en aval. Définir `MacroPdf417Terminator` à `Set` signale que c’est le segment final de la série macro.

### Étape 6 : enregistrer le code‑barres en image PNG
`Save` écrit l’image du code‑barres généré dans un fichier au format spécifié.  
Enfin, écrivez le code‑barres généré sur le disque. Le PNG conserve une qualité sans perte, ce qui est idéal pour la lecture.

```csharp
    // Step 6: Export the barcode
    string outputPath = Path.Combine(Environment.CurrentDirectory, "ExtPDF417Meta.png");
    barcodeGenerator.Save(outputPath, BarCodeImageFormat.Png);
}
```

Lorsque le code se termine, le fichier `ExtPDF417Meta.png` contient un code‑barres MacroPdf417 haute résolution qui encode le texte personnalisé et toutes les métadonnées macro.

#### Résultat attendu
Ouvrir `ExtPDF417Meta.png` montre un code‑barres orienté verticalement avec des rangées et colonnes clairement définies. Scanner l’image avec n’importe quel lecteur PDF417 renvoie la chaîne originale **Åspóse.Barcóde©** ainsi que les champs macro que vous avez configurés (ID du fichier, ID du segment, checksum, etc.).

## Comment générer pdf417 sans options macro ?
Pour créer un code‑barres PDF417 standard, il suffit de définir la symbologie sur `EncodeTypes.Pdf417`, fournir le texte à encoder, ajuster éventuellement les paramètres de taille comme `XDimension` et `Columns`, puis appeler `Save`. Cette approche omet toutes les propriétés spécifiques aux macros, produisant un code‑barres à segment unique adapté à la plupart des applications.

```csharp
using (BarcodeGenerator generator = new BarcodeGenerator(
           EncodeTypes.Pdf417, "Standard PDF417 data"))
{
    generator.Parameters.Barcode.XDimension.Pixels = 3;
    generator.Parameters.Barcode.Pdf417.Columns = 6;
    generator.Save("StandardPdf417.png", BarCodeImageFormat.Png);
}
```

Cet extrait montre **comment générer pdf417** rapidement lorsque la fonctionnalité macro n’est pas requise. La réponse directe : créez un `BarcodeGenerator` avec `EncodeTypes.Pdf417`, définissez le `CodeText`, ajustez éventuellement `XDimension` et `Columns`, puis appelez `Save` avec le format d’image souhaité.

## Pièges courants et astuces professionnelles

| Problème | Pourquoi cela se produit | Solution |
|----------|--------------------------|----------|
| Le code‑barres est trop petit pour être scanné | X‑dimension définie à 1 pixel ou colonnes trop nombreuses | Utilisez au moins `2` pixels pour `XDimension` et maintenez les colonnes entre `3` et `9` pour des tailles d’étiquette typiques |
| Les caractères Unicode apparaissent comme � | Incohérence d’encodage dans le fichier du projet | Assurez‑vous que le fichier du projet est enregistré en UTF‑8 et que le fichier source contient le BOM correct |
| Les champs macro sont ignorés par le scanner | `MacroPdf417Terminator` non défini pour le dernier segment | Définissez `MacroPdf417Terminator = Pdf417MacroTerminator.Set` sur le segment final |
| Le fichier image est corrompu | Le flux de sortie n’est pas correctement fermé | Utilisez l’instruction `using` (comme indiqué) pour garantir la libération du générateur |

## Exemple complet et exécutable

`BarcodeGenerator` est la classe qui crée l’image du code‑barres.  
Copiez le code suivant dans une nouvelle application console et exécutez‑le. Le programme crée le code‑barres, l’enregistre et affiche le chemin de sortie dans la console.

```csharp
using System;
using System.IO;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace AsposeBarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // Initialize the generator with custom Unicode text
            using (BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
                       EncodeTypes.MacroPdf417, "Åspóse.Barcóde©"))
            {
                // Basic size
                barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;

                // Macro layout
                barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 5;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";

                // Optional macro metadata
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400_000;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = new DateTime(2019, 11, 1);
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;

                // Save as PNG
                string outputFile = Path.Combine(Environment.CurrentDirectory, "ExtPDF417Meta.png");
                barcodeGenerator.Save(outputFile, BarCodeImageFormat.Png);

                Console.WriteLine($"Barcode saved to: {outputFile}");
            }
        }
    }
}
```

L’exécution du programme affiche une ligne similaire à :

```
Barcode saved to: C:\YourProject\bin\Debug\net6.0\ExtPDF417Meta.png
```

Ouvrez le fichier pour vérifier le rendu visuel.

## Questions fréquemment posées

**Q : Puis‑je utiliser ce code dans une API web ASP.NET Core ?**  
R : Oui. La même classe `BarcodeGenerator` fonctionne dans n’importe quel runtime .NET, y compris ASP.NET Core, tant que l’assembly `Aspose.BarCode` est référencé.

**Q : Aspose.BarCode prend‑il en charge d’autres formats d’image ?**  
R : Absolument. Vous pouvez enregistrer en PNG, JPEG, BMP, TIFF, voire SVG en passant la valeur d’énumération `BarCodeImageFormat` correspondante à la méthode `Save`.

**Q : Quelle est la taille maximale des données encodées ?**  
R : Un symbole PDF417 unique peut contenir jusqu’à 1 700 caractères ; avec MacroPdf417 vous pouvez répartir les données sur plusieurs segments, ce qui permet une longueur illimitée en pratique.

**Q : Existe‑t‑il un moyen d’ajouter de la couleur au code‑barres ?**  
R : Oui. Définissez les propriétés `ForeColor` et `BackColor` du `BarcodeGenerator` avant d’appeler `Save` pour obtenir des codes‑barres colorés.

**Q : Et si je dois intégrer le code‑barres directement dans un PDF ?**  
R : Utilisez Aspose.PDF pour insérer l’image PNG ou SVG générée dans une page PDF, ou servez‑vous de la fonction d’export PDF intégrée d’Aspose.BarCode.

## Conclusion

Vous savez maintenant **comment générer pdf417** pour la symbologie MacroPdf417, intégrer du texte Unicode personnalisé, configurer les métadonnées macro et exporter le résultat sous forme d’image PNG. Le même schéma vous permet de générer un code‑barres PDF417 simple lorsque les options macro ne sont pas nécessaires, et vous pouvez adapter le code à d’autres formats de code‑barres pris en charge par Aspose.BarCode. Expérimentez avec différentes valeurs de `XDimension`, de nombre de colonnes et de combinaisons de champs macro pour affiner le code‑barres selon votre imprimante ou scanner spécifique.

Ensuite, explorez des sujets connexes tels que **create barcode custom text** pour les QR codes, l’ajout de filtres de couleur avec les paramètres `Color`, ou l’intégration directe de codes‑barres dans des documents PDF à l’aide d’Aspose.PDF. La flexibilité d’Aspose.BarCode vous permet de gérer tout, des codes‑barres simples à une ligne aux codes‑barres macro multi‑segments complexes, avec seulement quelques lignes de C#.

## Que devriez‑vous apprendre ensuite ?

Les tutoriels suivants couvrent des sujets étroitement liés qui s’appuient sur les techniques démontrées dans ce guide. Chaque ressource comprend des exemples de code complets et fonctionnels avec des explications pas à pas pour vous aider à maîtriser des fonctionnalités API supplémentaires et explorer des approches d’implémentation alternatives dans vos propres projets.

- [Comment créer un code‑barres – PDF417 compact avec Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [Comment générer un code‑barres DataMatrix avec Aspose.BarCode pour .NET](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-macro-configuration/)
- [Générer un code‑barres Java – définir le texte du code avec Aspose.BarCode](/barcode/english/java/text-and-styling/setting-code-text/)

---

**Dernière mise à jour :** 2026-10-14  
**Testé avec :** Aspose.BarCode 24.11 for .NET  
**Auteur :** Aspose

## Tutoriels associés

- [Créer un code‑barres Macro Pdf417 avec Aspose Barcode C](/barcode/net/compact-pdf417-encoding/create-macro-pdf417-barcode-with-aspose-barcode-c/)
- [Guide d’ajustement de la taille du code‑barres C pour générer des codes‑barres Pdf417](/barcode/net/compact-pdf417-encoding/adjust-barcode-size-c-guide-to-generate-pdf417-barcodes/)
- [Lire un code‑barres depuis une image C – Guide complet avec Macro Pdf417](/barcode/net/compact-pdf417-encoding/read-barcode-from-image-c-complete-guide-with-macro-pdf417/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}