---
date: 2026-06-14
description: Apprenez à lire les DataMatrix et à générer des codes-barres à ajout
  structuré en .NET avec Aspose.BarCode, la bibliothèque de codes-barres rapide et
  fiable.
keywords:
- how to read datamatrix
- DataMatrix structured append
- Aspose.BarCode .NET
linktitle: Configuration de l'ajout structuré DataMatrix
schemas:
- author: Aspose
  dateModified: '2026-06-14'
  description: Learn how to read datamatrix and generate structured append barcodes
    in .NET using Aspose.BarCode, the fast and reliable barcode library.
  headline: How to Read DataMatrix Append with Aspose.BarCode for .NET
  type: TechArticle
- description: Learn how to read datamatrix and generate structured append barcodes
    in .NET using Aspose.BarCode, the fast and reliable barcode library.
  name: How to Read DataMatrix Append with Aspose.BarCode for .NET
  steps:
  - name: Aspose.BarCode for .NET Library – download it from [here](https://releases.aspose.com/barcode/net/).
    text: Aspose.BarCode for .NET Library – download it from [here](https://releases.aspose.com/barcode/net/).
  - name: You can also browse other Aspose products [here](https://releases.aspose.com/).
    text: You can also browse other Aspose products [here](https://releases.aspose.com/).
  - name: A .NET development environment such as Visual Studio 2022 or Visual Studio
      Code with the C# extension.
    text: A .NET development environment such as Visual Studio 2022 or Visual Studio
      Code with the C# extension.
  type: HowTo
- questions:
  - answer: Aspose.BarCode for .NET.
    question: What library handles DataMatrix structured append?
  - answer: Up to 16 DataMatrix symbols.
    question: How many symbols can a single structured append sequence contain?
  - answer: A free trial works for development and testing.
    question: Do I need a license for development?
  - answer: .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.
    question: Which .NET versions are supported?
  - answer: Yes, you can decode from a byte array or stream.
    question: Can I read the barcode without an image file?
  type: FAQPage
second_title: Aspose.BarCode .NET API
title: Comment lire le DataMatrix Append avec Aspose.BarCode pour .NET
url: /fr/net/datamatrix-barcode-reading/datamatrix-structured-append-configuration/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Configuration d'appendice structuré DataMatrix avec Aspose.BarCode pour .NET

Si vous êtes développeur et que vous cherchez **how to read datamatrix** en utilisant l'appendice structuré dans vos applications .NET, Aspose.BarCode pour .NET est votre solution de référence. Dans ce guide étape par étape, nous parcourrons la génération et le décodage des codes-barres DataMatrix répartis sur plusieurs symboles. À la fin de ce tutoriel, vous serez à l'aise pour créer, configurer et lire les codes-barres DataMatrix à appendice structuré avec Aspose.BarCode pour .NET.

## Réponses rapides
- **Quelle bibliothèque gère l'appendice structuré DataMatrix ?** Aspose.BarCode for .NET.
- **Combien de symboles une séquence d'appendice structuré peut‑elle contenir ?** Jusqu'à 16 symboles DataMatrix.
- **Ai‑je besoin d'une licence pour le développement ?** Une version d'essai gratuite suffit pour le développement et les tests.
- **Quelles versions de .NET sont prises en charge ?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.
- **Puis‑je lire le code‑barres sans fichier image ?** Oui, vous pouvez décoder à partir d'un tableau d'octets ou d'un flux.

## Qu'est‑ce que how to read datamatrix ?
**how to read datamatrix** désigne le processus de décodage des symboles DataMatrix et, le cas échéant, d'assemblage des morceaux d'une séquence d'appendice structuré afin de récupérer la charge de données originale. Aspose.BarCode offre un support intégré pour ce flux de travail, gérant automatiquement l'ordre des symboles et la concaténation des données.

## Pourquoi utiliser Aspose.BarCode pour l'appendice structuré DataMatrix ?
Aspose.BarCode prend en charge **plus de 30 symbologies de codes‑barres** et peut décoder des images jusqu'à **10 000 × 10 000 px** en moins de **200 ms** sur du matériel serveur typique. La bibliothèque offre également un **déploiement sans dépendance**, ce qui signifie que vous n'avez pas besoin de DLL natives supplémentaires, et elle fonctionne sur les runtimes .NET Windows, Linux et macOS.

## Prérequis

1. Bibliothèque Aspose.BarCode pour .NET – téléchargez‑la depuis [ici](https://releases.aspose.com/barcode/net/).
2. Vous pouvez également parcourir les autres produits Aspose [ici](https://releases.aspose.com/).
3. Un environnement de développement .NET tel que Visual Studio 2022 ou Visual Studio Code avec l'extension C#.

Maintenant, commençons à créer et à lire les codes‑barres DataMatrix à appendice structuré.

## Importer les espaces de noms

La première étape consiste à importer les espaces de noms qui exposent l'API du code‑barres.

La classe `BarCodeWriter` est le point d'entrée d'Aspose.BarCode pour créer des codes‑barres, tandis que `BarCodeReader` gère le décodage.

```csharp
using Aspose.BarCode.BarCodeRecognition;
using Aspose.BarCode.Generation;
using System;
using System.Drawing;
```

Maintenant que vous avez importé les espaces de noms requis, créons un code‑barres à appendice structuré.

## Comment lire les codes‑barres DataMatrix à appendice structuré ?

Chargez l'image générée (ou le flux) dans un `BarCodeReader`, activez l'option `ReadStructuredAppend` et appelez `ReadBarcode`. Le lecteur renverra automatiquement les données combinées et exposera les détails de la séquence tels que `StructuredAppendFileId`, `StructuredAppendTotalCount` et `StructuredAppendSegmentId`. Le résultat combiné est renvoyé sous forme d'une chaîne unique, et vous pouvez également récupérer les identifiants de segment individuels via la propriété `StructuredAppendSegmentId` du lecteur pour un traitement personnalisé.

```csharp
    using (BarCodeReader reader = new BarCodeReader(bitmap, DecodeType.DataMatrix))
    {
        reader.ReadBarCodes();

        Console.WriteLine("Barcode ID: {0}", reader.FoundBarCodes[0].Extended.DataMatrix.StructuredAppendBarcodeId);
        Console.WriteLine("Barcodes count: {0}", reader.FoundBarCodes[0].Extended.DataMatrix.StructuredAppendBarcodesCount);
        Console.WriteLine("File ID: {0}", reader.FoundBarCodes[0].Extended.DataMatrix.StructuredAppendFileId);
    }
}
```

Dans cette étape, nous utilisons le lecteur pour extraire l'ID du code‑barres, le nombre total et l'ID du fichier, confirmant que la configuration d'appendice structuré a été correctement interprétée.

## Étape 1 : Configurer l'appendice structuré DataMatrix

Pour créer un code‑barres DataMatrix à appendice structuré, vous devez configurer ses paramètres. Cela comprend la définition du chemin du répertoire, de l'ID du code‑barres, du nombre de codes‑barres et de l'ID du fichier.

```csharp
string path = "Your Directory Path";

using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.DataMatrix, "Aspose"))
{
    generator.Parameters.Barcode.XDimension.Pixels = 4;

    // Set DataMatrix structured append mode
    generator.Parameters.Barcode.DataMatrix.StructuredAppendBarcodeId = 3;
    generator.Parameters.Barcode.DataMatrix.StructuredAppendBarcodesCount = 5;
    generator.Parameters.Barcode.DataMatrix.StructuredAppendFileId = 150;

    // Generate the barcode image
    Bitmap bitmap = generator.GenerateBarCodeImage();
```

Dans cette étape, nous avons configuré le code‑barres DataMatrix avec les paramètres souhaités.

## Problèmes courants et solutions

- **Ordre de segment incorrect :** Assurez‑vous que les valeurs `StructuredAppendSegmentId` sont séquentielles à partir de 0 ; sinon le lecteur ne pourra pas réassembler les données correctement.
- **Nombre total incohérent :** `StructuredAppendTotalCount` doit être identique sur tous les symboles ; une discordance entraînera le traitement de la séquence comme incomplète par le lecteur.
- **Qualité de l'image :** Les images à basse résolution peuvent entraîner des échecs de décodage. Visez au moins **300 dpi** lors du rendu du code‑barres en bitmap.

## Questions fréquemment posées

### Q1 : Qu'est‑ce que l'appendice structuré DataMatrix, et pourquoi l'utilise‑t‑on ?
R1 : L'appendice structuré DataMatrix est une fonctionnalité qui permet de diviser une grande quantité de données en plusieurs codes‑barres plus petits. Cela est particulièrement utile lorsque l'espace disponible pour un seul code‑barres est limité ou que vous devez organiser les données de manière efficace. Elle est couramment utilisée dans la logistique, la santé et la fabrication.

### Q2 : Puis‑je utiliser Aspose.BarCode pour .NET dans mon projet open‑source ?
R2 : Oui, Aspose.BarCode pour .NET propose une version d'essai gratuite que vous pouvez utiliser dans des projets open‑source. Vous pouvez trouver la version d'essai [ici](https://releases.aspose.com/).

### Q3 : Existe‑t‑il un support communautaire pour Aspose.BarCode pour .NET ?
R3 : Oui, vous pouvez rechercher du support communautaire et interagir avec d'autres utilisateurs sur le forum Aspose.BarCode [ici](https://forum.aspose.com/c/barcode/13).

### Q4 : Comment obtenir une licence temporaire pour Aspose.BarCode pour .NET ?
R4 : Si vous avez besoin d'une licence temporaire pour l'évaluation ou les tests, vous pouvez en obtenir une [ici](https://purchase.aspose.com/temporary-license/).

### Q5 : Aspose.BarCode pour .NET prend‑il en charge d'autres types de codes‑barres ?
R5 : Oui, Aspose.BarCode pour .NET prend en charge un large éventail de types de codes‑barres, y compris les QR codes, Code 128, EAN‑13, et bien d'autres. Vous pouvez explorer la documentation complète [ici](https://reference.aspose.com/barcode/net/) pour voir la liste complète des types de codes‑barres pris en charge.

---

**Dernière mise à jour :** 2026-06-14  
**Testé avec :** Aspose.BarCode 24.11 pour .NET  
**Auteur :** Aspose

## Tutoriels associés

- [Programmation du lecteur DataMatrix avec Aspose.BarCode pour .NET](/barcode/net/datamatrix-barcode-reading/datamatrix-reader-programming/)
- [Générer des codes‑barres DataMatrix avec Aspose.BarCode pour .NET](/barcode/net/datamatrix-barcode-reading/datamatrix-versions/)
- [Maîtriser la configuration macro DataMatrix avec Aspose.BarCode pour .NET](/barcode/net/datamatrix-barcode-configuration/datamatrix-macro-configuration/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< blocks/products/products-backtop-button >}}
{{< /blocks/products/pf/main-wrap-class >}}