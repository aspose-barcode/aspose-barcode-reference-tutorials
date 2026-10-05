---
date: 2026-08-17
description: Explorez la programmation du lecteur DataMatrix avec Aspose.BarCode pour
  .NET. Apprenez à générer et lire les codes-barres DataMatrix dans vos applications
  .NET grâce à ce guide complet.
keywords:
- create barcode image .net
- barcode reader guide
- generate datamatrix c#
- c# barcode recognition library
- barcode image handling c#
lastmod: 2026-08-17
linktitle: Programmation du lecteur DataMatrix
og_description: Créer une image de code-barres .NET en utilisant Aspose.BarCode pour
  générer et lire les codes DataMatrix. Ce guide présente une configuration étape
  par étape, des extraits de code et les meilleures pratiques pour la gestion des
  images de code-barres en C#.
og_image_alt: Tutorial image showing DataMatrix barcode generated with Aspose.BarCode
  in a .NET application
og_title: Créer une image de code-barres .NET avec Aspose.BarCode DataMatrix
schemas:
- author: Aspose
  dateModified: '2026-08-17'
  description: Explore DataMatrix reader programming with Aspose.BarCode for .NET.
    Learn how to generate and read DataMatrix barcodes in your .NET applications with
    this comprehensive guide.
  headline: Create barcode image .NET with Aspose.BarCode for DataMatrix
  type: TechArticle
- description: Explore DataMatrix reader programming with Aspose.BarCode for .NET.
    Learn how to generate and read DataMatrix barcodes in your .NET applications with
    this comprehensive guide.
  name: Create barcode image .NET with Aspose.BarCode for DataMatrix
  steps:
  - name: '**Visual Studio** (any recent edition) with a supported .NET runtime installed.'
    text: '**Visual Studio** (any recent edition) with a supported .NET runtime installed.'
  - name: '**Aspose.BarCode for .NET** – download it from the [download page](https://releases.aspose.com/barcode/net/).'
    text: '**Aspose.BarCode for .NET** – download it from the [download page](https://releases.aspose.com/barcode/net/).'
  - name: '**Basic C# knowledge** – you should be comfortable creating a console or
      desktop project.'
    text: '**Basic C# knowledge** – you should be comfortable creating a console or
      desktop project.'
  type: HowTo
- questions:
  - answer: It embeds configuration data in a DataMatrix symbol so a scanner can automatically
      set parameters like illumination or decoding mode.
    question: What is DataMatrix reader programming?
  - answer: The library offers a unified API for over 50 barcode types, high‑performance
      encoding/decoding, and full .NET Core support.
    question: Why choose Aspose.BarCode for .NET?
  - answer: A trial version is available for evaluation; a commercial license is required
      for production deployments.
    question: Can I use Aspose.BarCode for free?
  - answer: You can request a short‑term license from the [temporary license page](https://purchase.aspose.com/temporary-license/).
    question: How do I obtain a temporary license?
  - answer: You can buy a full license from the [Aspose purchase page](https://purchase.aspose.com/buy).
    question: How can I purchase a full license?
  type: FAQPage
second_title: Aspose.BarCode .NET API
tags:
- DataMatrix
- Aspose.BarCode
- barcode generation
- C# barcode
- create barcode image
title: Créer une image de code-barres .NET avec Aspose.BarCode pour DataMatrix
url: /fr/net/datamatrix-barcode-reading/datamatrix-reader-programming/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Créer une image de code-barres .NET avec Aspose.BarCode pour DataMatrix

Dans ce tutoriel, vous apprendrez comment **créer une image de code-barres .NET** d’applications qui génèrent et lisent des codes DataMatrix en utilisant Aspose.BarCode. Que vous ayez besoin d’intégrer des codes-barres dans des étiquettes de fabrication ou d’automatiser le suivi des stocks, ce guide vous accompagne à chaque étape — de la configuration du projet à la lecture du code-barres — afin que vous puissiez mettre en œuvre rapidement une solution fiable.

## Réponses rapides
- **Que signifie « reader programming » ?** Il encode les symboles DataMatrix afin qu’un scanner puisse se configurer automatiquement.  
- **Quelles versions de .NET sont prises en charge ?** Aspose.BarCode fonctionne avec .NET Framework 4.0+, .NET Core 2.0+ et .NET 5/6+.  
- **Ai‑je besoin d’une licence pour le développement ?** Un essai gratuit suffit pour les tests ; une licence commerciale est requise pour la production.  
- **Combien de formats de code‑barres Aspose.BarCode prend‑il en charge ?** Plus de 50 symbologies 1D et 2D, y compris DataMatrix, QR et PDF417.  
- **Puis‑je lire le code‑barres sans enregistrer de fichier image ?** Oui — utilisez un `MemoryStream` pour traiter l’image entièrement en mémoire.

## Qu’est‑ce que la programmation du lecteur de code-barres DataMatrix ?
La programmation du lecteur de code‑barres DataMatrix est la technique consistant à intégrer des données de configuration spéciales à l’intérieur d’un symbole DataMatrix afin qu’un scanner puisse automatiquement ajuster son illumination, son mode de décodage et d’autres paramètres opérationnels lorsqu’il détecte le symbole. Cette approche réduit le besoin de configuration manuelle du scanner et améliore le débit dans les environnements à haut volume tels que les lignes de production ou les systèmes de tri d’entrepôt.

## Pourquoi utiliser Aspose.BarCode pour .NET ?
Aspose.BarCode pour .NET fournit une API unifiée qui prend en charge plus de 50 symbologies de codes‑barres, peut gérer des images de plusieurs mégaoctets sans charger le fichier complet en mémoire, et offre un encodage et décodage en sous‑milliseconde sur du matériel serveur typique, ce qui en fait un choix haute performance tant pour les applications de bureau que pour les solutions cloud nécessitant un traitement fiable des codes‑barres.

## Prérequis

Avant de commencer, assurez‑vous d’avoir :

1. **Visual Studio** (toute édition récente) avec un runtime .NET pris en charge installé.  
2. **Aspose.BarCode for .NET** – téléchargez‑le depuis la [page de téléchargement](https://releases.aspose.com/barcode/net/).  
3. **Connaissances de base en C#** – vous devez être à l’aise pour créer un projet console ou desktop.

## Importer les espaces de noms

`Aspose.BarCode` fournit les classes principales pour la génération et la lecture de codes‑barres, tandis que `System.Drawing` gère la manipulation d’images.

```csharp
using Aspose.BarCode.BarCodeRecognition;
using Aspose.BarCode.Generation;
using System;
using System.Drawing;
```

## Qu’est‑ce que la classe `BarcodeGenerator` ?
La classe `BarcodeGenerator` est l’objet principal d’Aspose.BarCode pour créer des images de code‑barres en mémoire ; elle encapsule tous les paramètres nécessaires pour définir la symbologie, l’apparence visuelle, les options d’encodage et le format de sortie, permettant aux développeurs de générer des codes‑barres de haute qualité avec un seul appel de méthode.

## Comment définir le chemin de votre répertoire

Définissez un dossier où l’image de code‑barres générée sera enregistrée.  

```csharp
string path = "Your Directory Path";
```

Remplacez `"Your Directory Path"` par le dossier réel sur votre machine.

## Comment initialiser le générateur DataMatrix

Créez une instance de `BarcodeGenerator`, définissez la symbologie sur DataMatrix et activez la programmation du lecteur.

```csharp
System.Console.WriteLine("DataMatrixReaderProgramming:");

using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.DataMatrix, "Aspose"))
{
    generator.Parameters.Barcode.XDimension.Pixels = 4;
    // Set a flag that indicates data is encoded for reader programming
    generator.Parameters.Barcode.DataMatrix.IsReaderProgramming = true;
    Bitmap bitmap = generator.GenerateBarCodeImage();
```

Paramètres clés :

- `XDimension = 4` pixels contrôle la taille du module.  
- `IsReaderProgramming = true` indique au scanner que le symbole contient des données de configuration.

## Comment générer l’image du code‑barres

Appelez la méthode `Save` pour écrire l’image vers le chemin choisi.

```csharp
    Bitmap bitmap = generator.GenerateBarCodeImage();
```

L’image est enregistrée au format PNG par défaut, mais vous pouvez choisir JPEG, BMP ou TIFF.

## Comment lire le code‑barres

Utilisez `BarCodeReader` pour décoder l’image enregistrée et vérifier le drapeau de programmation du lecteur. La classe `BarCodeReader` est le composant principal pour le décodage des codes‑barres ; elle lit une image, détecte les symbologies prises en charge et expose des propriétés telles que `IsReaderProgrammable` qui indiquent si le symbole DataMatrix contient des informations de programmation du lecteur.

```csharp
    using (BarCodeReader reader = new BarCodeReader(bitmap, DecodeType.DataMatrix))
    {
        reader.ReadBarCodes();
        Console.WriteLine("Is reader programming: {0}", reader.FoundBarCodes[0].Extended.DataMatrix.IsReaderProgramming);
    }
}
```

Le lecteur renvoie `IsReaderProgrammable` = `true` lorsque le drapeau a été correctement encodé.

## Problèmes courants et dépannage

- **Image non trouvée** – Vérifiez que le chemin du répertoire se termine par une barre oblique inverse (`\`) ou utilisez `Path.Combine`.  
- **Le lecteur renvoie false** – Assurez‑vous que `IsReaderProgramming` est défini **avant** d’appeler `Save`.  
- **Format d’image non pris en charge** – Restez sur PNG ou JPEG ; BMP et TIFF peuvent nécessiter des codecs supplémentaires sur les anciennes versions de Windows.

## Questions fréquemment posées

**Q : Qu’est‑ce que la programmation du lecteur DataMatrix ?**  
R : Elle intègre des données de configuration dans un symbole DataMatrix afin qu’un scanner puisse automatiquement régler des paramètres tels que l’illumination ou le mode de décodage.

**Q : Pourquoi choisir Aspose.BarCode pour .NET ?**  
R : La bibliothèque offre une API unifiée pour plus de 50 types de codes‑barres, un encodage/décodage haute performance et une prise en charge complète de .NET Core.

**Q : Puis‑je utiliser Aspose.BarCode gratuitement ?**  
R : Une version d’essai est disponible pour l’évaluation ; une licence commerciale est requise pour les déploiements en production.

**Q : Comment obtenir une licence temporaire ?**  
R : Vous pouvez demander une licence à court terme depuis la [page de licence temporaire](https://purchase.aspose.com/temporary-license/).

**Q : Comment acheter une licence complète ?**  
R : Vous pouvez acheter une licence complète sur la [page d’achat d’Aspose](https://purchase.aspose.com/buy).

**Q : La bibliothèque est‑elle compatible avec les dernières versions de .NET ?**  
R : Oui, elle prend en charge .NET Framework 4.0+, .NET Core 2.0+ et .NET 5/6+.

## Conclusion

En suivant ce guide, vous savez maintenant comment **créer des solutions d’image de code‑barres .NET** qui génèrent des symboles DataMatrix et les lisent avec Aspose.BarCode. Intégrez ces extraits dans n’importe quel projet C# — desktop, service ou web — pour automatiser les flux de travail de codes‑barres dans les environnements de fabrication, logistique ou santé.

Pour des documents de référence plus approfondis, explorez la [documentation officielle](https://reference.aspose.com/barcode/net/) ou rejoignez la communauté sur le [forum de support Aspose.BarCode](https://forum.aspose.com/c/barcode/13).

---

**Dernière mise à jour :** 2026-08-17  
**Testé avec :** Aspose.BarCode 24.11 for .NET  
**Auteur :** Aspose

## Tutoriels associés

- [Comment lire les codes‑barres DataMatrix avec Aspose.BarCode pour .NET](/barcode/net/datamatrix-barcode-reading/)
- [Comment générer des codes‑barres DataMatrix (ECC 200) avec Aspose.BarCode pour .NET](/barcode/net/datamatrix-barcode-configuration/datamatrix-ecc-200-configuration/)
- [Créer un PNG de code‑barres – Ratio d’aspect DataMatrix – Aspose.BarCode](/barcode/net/datamatrix-barcode-configuration/datamatrix-aspect-ratio-customization/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}