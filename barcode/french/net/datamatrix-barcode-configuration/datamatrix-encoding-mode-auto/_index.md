---
date: 2026-08-02
description: Guide étape par étape sur la façon de lire le code‑barres DataMatrix
  C# et de générer une image de code‑barres C# en utilisant Aspose.BarCode for .NET
  avec auto encoding.
keywords:
- how to read datamatrix
- read barcode from file
- how to generate datamatrix
- datamatrix encoding auto
lastmod: 2026-08-02
linktitle: Mode d'encodage DataMatrix (Auto)
og_description: Apprenez à lire le code‑barres DataMatrix C# et à le générer en mode
  Auto en utilisant Aspose.BarCode for .NET. Ce tutoriel couvre l'installation, le
  code et le dépannage.
og_image_alt: 'Guide: Read and generate DataMatrix barcode in C# with Aspose.BarCode'
og_title: Comment lire le code‑barres DataMatrix C# – Auto mode
schemas:
- author: Aspose
  dateModified: '2026-08-02'
  description: Step‑by‑step guide on how to read DataMatrix barcode C# and generate
    barcode image C# using Aspose.BarCode for .NET with auto encoding.
  headline: How to read DataMatrix barcode C# – Auto mode
  type: TechArticle
- questions:
  - answer: It allows Aspose.BarCode to automatically select the optimal encoding
      method for the provided data, simplifying the **how to generate datamatrix**
      process.
    question: What is DataMatrix encoding mode "Auto"?
  - answer: Yes – adjust `generator.Parameters.Barcode.XDimension.Pixels` to change
      module size.
    question: Can I customize the dimensions of the generated barcode?
  - answer: Absolutely. Purchase a license from the [website](https://purchase.aspose.com/buy).
    question: Is Aspose.BarCode for .NET suitable for commercial use?
  - answer: Yes, you can explore Aspose.BarCode with a free trial from [this link](https://releases.aspose.com/).
    question: Is there a free trial available?
  - answer: Aspose.BarCode supports UTF‑8, ASCII, and other ECI encodings; set the
      desired value via `ECIEncoding`.
    question: What encoding options are available for DataMatrix barcodes?
  type: FAQPage
second_title: Aspose.BarCode .NET API
tags:
- datamatrix barcode
- Aspose.BarCode
- C# barcode generation
title: Comment lire le code‑barres DataMatrix C# – Auto mode
url: /fr/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-auto/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Comment lire le code-barres DataMatrix C# – Mode Auto

Dans le monde numérique d’aujourd’hui, **comment lire le datamatrix** rapidement et de façon fiable est essentiel pour le suivi des stocks, la gestion sécurisée des documents et de nombreux autres scénarios d’entreprise. Ce tutoriel vous guide dans la génération d’un code‑barres DataMatrix en mode *Auto* avec Aspose.BarCode pour .NET, puis montre comment lire ce code‑barres en C#. Que vous suiviez un guide de tutoriel sur les codes‑barres ou que vous ayez besoin d’un exemple de code prêt à l’emploi, vous terminerez avec une solution prête pour la production que vous pourrez intégrer à n’importe quel projet .NET.

## Réponses rapides
- **Que fait le mode “Auto” ?** Il permet à Aspose.BarCode de sélectionner automatiquement le meilleur schéma d’encodage pour vos données.  
- **Quelle bibliothèque est requise ?** Aspose.BarCode for .NET (essai gratuit disponible).  
- **Puis-je lire le code-barres dans la même application ?** Oui – utilisez `BarCodeReader` avec `DecodeType.DataMatrix`.  
- **Ai‑je besoin d’une licence pour la production ?** Une licence commerciale est requise pour une utilisation en production.  
- **Versions .NET prises en charge ?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.  

`BarCodeReader` est la classe d’Aspose.BarCode pour analyser les images et récupérer les informations du code-barres.

## Qu’est‑ce que la lecture d’un code‑barres DataMatrix C# ?
Lire un code‑barres DataMatrix en C# signifie décoder la matrice bidimensionnelle de modules noirs et blancs pour retrouver le texte ou les données d’origine. Aspose.BarCode abstrait le traitement d’image bas‑niveau, vous permettant de vous concentrer sur la logique métier tandis que la bibliothèque gère automatiquement la correction d’erreurs, la sélection de la taille du symbole et la prise en charge Unicode.

## Pourquoi utiliser Aspose.BarCode pour générer une image de code‑barres C# ?
Aspose.BarCode sélectionne automatiquement l’encodage optimal, prend en charge **plus de 30 symbologies de codes‑barres**, et peut générer des symboles DataMatrix jusqu’à **1558 × 1558 modules** – bien plus grands que la plupart des concurrents. Il fonctionne sous Windows, Linux et macOS sans dépendances natives, vous offrant une API unique et multiplateforme pour la génération comme pour la lecture.

## Prérequis

1. **Environnement .NET** – Installez la dernière version du runtime .NET depuis le [.NET website](https://dotnet.microsoft.com/download/dotnet).  
2. **Aspose.BarCode for .NET** – Téléchargez la bibliothèque depuis le [website](https://releases.aspose.com/barcode/net/).  

## Importation des espaces de noms
L’espace de noms `Aspose.BarCode` contient toutes les classes nécessaires à la création et à la lecture de codes‑barres. Importez‑le en haut de votre fichier avant tout autre code.

```csharp
using Aspose.BarCode.BarCodeRecognition;
using Aspose.BarCode.Generation;
using System;
using System.Drawing;
```

Maintenant que les espaces de noms sont en place, parcourons le code étape par étape.

## Étape 1 : Définir le chemin du répertoire
Choisissez un dossier où le PNG généré (ou tout autre format supporté) sera enregistré. Ce chemin peut être absolu ou relatif à votre projet.

```csharp
string path = "Your Directory Path";
```

Remplacez `"Your Directory Path"` par le dossier de votre choix. Garder le dossier de sortie configurable rend le tutoriel réutilisable dans différents environnements.

## Étape 2 : Créer un code‑barres DataMatrix en mode Auto
`DataMatrixEncodeMode.Auto` indique au générateur de sélectionner automatiquement le schéma d’encodage optimal pour les données fournies.

```csharp
using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.DataMatrix, "Aspose常に先を行く"))
{
    generator.Parameters.Barcode.XDimension.Pixels = 4;
    generator.Parameters.Barcode.DataMatrix.DataMatrixEncodeMode = DataMatrixEncodeMode.Auto;
    generator.Parameters.Barcode.DataMatrix.ECIEncoding = ECIEncodings.UTF8;
    Bitmap bitmap = generator.GenerateBarCodeImage();
}
```

N’hésitez pas à remplacer le texte d’exemple par n’importe quelle chaîne dont vous avez besoin pour **comment générer le datamatrix**. Le mode auto basculera automatiquement entre Base‑256, ASCII ou d’autres schémas afin d’obtenir le symbole le plus petit possible.

## Étape 3 : Lire le code‑barres (lecture du code‑barres DataMatrix C#)
`BarCodeReader` est la classe d’Aspose.BarCode pour analyser les images et récupérer les informations du code‑barres. Elle prend en charge la lecture depuis des flux, des fichiers et des objets bitmap, ce qui la rend idéale pour les scénarios de **lire le code‑barres depuis un fichier**.

```csharp
using (BarCodeReader reader = new BarCodeReader(bitmap, DecodeType.DataMatrix))
{
    reader.ReadBarCodes();
    Console.WriteLine(reader.FoundBarCodes[0].CodeText);
}
```

Cet extrait décode l’image que nous venons de générer et affiche le texte original dans la console, démontrant un aller‑retour complet de la génération à la lecture.

## Problèmes courants et solutions

| Problème | Cause | Solution |
|----------|-------|----------|
| **Aucun code‑barres détecté** | Résolution de l’image trop basse | Augmenter `XDimension.Pixels` (par ex., à 6) |
| **Caractères indésirables** | Encodage ECI incorrect | Définir `ECIEncoding` pour correspondre à vos données (UTF‑8, ASCII, etc.) |
| **Exception sur `ReadBarCodes`** | Bitmap libéré avant la lecture | Conserver l’instance `Bitmap` en vie jusqu’après la lecture |

## Questions fréquemment posées

**Q : Qu’est‑ce que le mode d’encodage DataMatrix « Auto » ?**  
R : Il permet à Aspose.BarCode de sélectionner automatiquement la méthode d’encodage optimale pour les données fournies, simplifiant le processus de **comment générer le datamatrix**.

**Q : Puis‑je personnaliser les dimensions du code‑barres généré ?**  
R : Oui – ajustez `generator.Parameters.Barcode.XDimension.Pixels` pour modifier la taille du module.

**Q : Aspose.BarCode for .NET convient‑il à un usage commercial ?**  
R : Absolument. Achetez une licence sur le [website](https://purchase.aspose.com/buy).

**Q : Existe‑t‑il un essai gratuit ?**  
R : Oui, vous pouvez explorer Aspose.BarCode avec un essai gratuit depuis [this link](https://releases.aspose.com/).

**Q : Quelles options d’encodage sont disponibles pour les codes‑barres DataMatrix ?**  
R : Aspose.BarCode prend en charge UTF‑8, ASCII et d’autres encodages ECI ; définissez la valeur souhaitée via `ECIEncoding`.

## Conclusion

Vous disposez maintenant d’un exemple complet, prêt pour la production, qui **lit le code‑barres DataMatrix C#**, génère le code‑barres en mode Auto et vérifie le résultat – le tout avec Aspose.BarCode pour .NET. Expérimentez avec différents textes, tailles et paramètres ECI pour répondre à votre scénario spécifique, et consultez la documentation officielle [documentation](https://reference.aspose.com/barcode/net/) pour des personnalisations plus avancées.

---

**Dernière mise à jour** : 2026-08-02  
**Testé avec** : Aspose.BarCode 24.12 for .NET  
**Auteur** : Aspose

## Tutoriels associés

- [Comment lire les codes‑barres DataMatrix avec Aspose.BarCode pour .NET](/barcode/net/datamatrix-barcode-reading/)
- [Configuration de l’ajout structuré DataMatrix avec Aspose.BarCode pour .NET](/barcode/net/datamatrix-barcode-reading/datamatrix-structured-append-configuration/)
- [Programmation du lecteur DataMatrix avec Aspose.BarCode pour .NET](/barcode/net/datamatrix-barcode-reading/datamatrix-reader-programming/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< blocks/products/products-backtop-button >}}
{{< /blocks/products/pf/main-wrap-class >}}