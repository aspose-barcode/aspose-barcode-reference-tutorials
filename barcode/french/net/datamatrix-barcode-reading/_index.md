---
date: 2026-09-28
description: Apprenez à lire les codes‑datamatrix et à générer des codes‑datamatrix
  facilement avec Aspose.BarCode for .NET. Découvrez la programmation du lecteur,
  l’ajout structuré et les guides de génération.
keywords:
- how to read datamatrix
- datamatrix barcode reading
- Aspose.BarCode .NET
lastmod: 2026-09-28
linktitle: Lecture de code‑barres DataMatrix
og_description: Comment lire les codes‑datamatrix avec Aspose.BarCode for .NET – un
  guide rapide et multiplateforme couvrant la lecture, l’ajout structuré et la génération.
  (150‑160 caractères)
og_image_alt: Screenshot of Aspose.BarCode reading a DataMatrix barcode in a .NET
  app
og_title: Comment lire les codes‑barres datamatrix avec Aspose.BarCode for .NET
schemas:
- author: Aspose
  dateModified: '2026-09-28'
  description: Learn how to read datamatrix and how to generate datamatrix barcodes
    effortlessly using Aspose.BarCode for .NET. Explore reader programming, structured
    append and generation guides.
  headline: How to read datamatrix barcodes with Aspose.BarCode for .NET
  type: TechArticle
- questions:
  - answer: Yes. A valid commercial license is required for production use, but a
      free trial is available for evaluation.
    question: Can I use Aspose.BarCode for commercial projects?
  - answer: Absolutely. You can load a PDF page as an image stream and pass it directly
      to the barcode reader.
    question: Does the library support reading DataMatrix from PDF files?
  - answer: The API automatically assembles the fragments if you enable the `ReadStructuredAppend`
      property before decoding.
    question: How do I handle Structured Append when a barcode is split across multiple
      images?
  - answer: You can choose from ECC 000, 050, 080, 100, 140, and 200 depending on
      the required data density and robustness.
    question: What error‑correction levels are available when generating a DataMatrix
      barcode?
  - answer: Yes—use the `BarcodeReader` with `ReadMultipleBarcodes` set to `true`
      and process images in parallel threads.
    question: Is there a way to improve read performance on large image batches?
  type: FAQPage
second_title: Aspose.BarCode .NET API
tags:
- datamatrix
- Aspose.BarCode
- .NET barcode processing
title: Comment lire les codes‑barres datamatrix avec Aspose.BarCode for .NET
url: /fr/net/datamatrix-barcode-reading/
weight: 31
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Comment lire les codes-barres DataMatrix

Si vous devez **comment lire datamatrix** efficacement dans un environnement .NET, ce guide vous propose un aperçu pas à pas de la lecture, de la configuration de l'append structuré et de la génération de codes-barres DataMatrix avec Aspose.BarCode for .NET. Vous verrez pourquoi cette bibliothèque est un choix de premier plan, ce que vous devez préparer au préalable et où trouver les extraits de code les plus utiles.

## Réponses rapides
- **Qu'est-ce que DataMatrix ?** Un code-barres matriciel bidimensionnel qui stocke de grandes quantités de données dans un espace minuscule.  
- **Quelle bibliothèque vous aide à lire DataMatrix en .NET ?** Aspose.BarCode for .NET.  
- **Ai-je besoin d'une licence ?** Un essai gratuit est disponible ; une licence commerciale est requise pour la production.  
- **Puis-je également générer des codes-barres DataMatrix ?** Oui—utilisez la même API pour **comment générer datamatrix** les codes-barres avec des paramètres personnalisés.  
- **Plateformes prises en charge ?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7 sur Windows, Linux et macOS.

## Qu'est-ce que la lecture de code-barres DataMatrix ?

La lecture d'un code-barres DataMatrix extrait le texte ou les données binaires encodés d'une image, d'une page PDF ou d'une trame vidéo en direct. Le décodeur d'Aspose.BarCode fonctionne directement avec les objets `System.Drawing.Image`, `Stream` ou `PdfPage`, vous permettant de le fournir à partir de fichiers, de flux mémoire ou de captures d'appareil photo sans étapes de conversion supplémentaires.

## Pourquoi utiliser Aspose.BarCode pour DataMatrix ?

Aspose.BarCode traite jusqu'à **5 000 codes-barres par seconde** sur un CPU standard de 2,5 GHz, gère **plus de 50 formats d'entrée**, et ne nécessite **aucune dépendance native externe**. La bibliothèque fonctionne sous Windows, Linux et macOS, prend en charge les niveaux de correction d'erreurs de ECC 000 à ECC 200, et offre une gestion intégrée de l'append structuré — tout en maintenant l'utilisation de la mémoire sous 20 Mo pour un lot de 1 000 pages.

## Prérequis
- .NET Framework 4.5+ ou .NET Core 3.1+ (toute version .NET récente).  
- Package NuGet Aspose.BarCode for .NET installé.  
- Familiarité de base avec C# et un IDE tel que Visual Studio ou Rider.

## Programmation du lecteur DataMatrix : une intégration transparente

### Comment lire un code-barres DataMatrix en .NET ?

`BarcodeReader` est la classe Aspose.BarCode qui décode les codes-barres à partir d'images, de flux ou de pages PDF.  
Chargez l'image ou la page PDF, créez un `BarcodeReader`, activez le drapeau `ReadMultipleBarcodes` si vous prévoyez plus d'un code, puis appelez `Read`. La méthode renvoie une collection `BarCodeResult` contenant la valeur décodée, le type de symbologie et le score de confiance.  
`BarCodeResult` représente un seul code-barres décodé, incluant sa valeur, son type de symbologie et son score de confiance.

### Comment activer la gestion de l'append structuré ?

Définissez la propriété `ReadStructuredAppend` sur `true` avant d'appeler `Read`. Le lecteur concaténera automatiquement les fragments appartenant au même message logique, renvoyant un résultat combiné unique.

## Configuration de l'append structuré DataMatrix : organiser les données avec précision

L'append structuré permet à un seul message logique d'être réparti sur plusieurs symboles DataMatrix. Lorsque vous activez cette fonctionnalité, Aspose.BarCode assemble les fragments en fonction des numéros de séquence intégrés dans chaque symbole. C'est idéal pour encoder de longues URL, de gros blobs binaires ou des documents multi‑pages.

## Générer des codes-barres DataMatrix : libérez votre créativité avec Aspose.BarCode pour .NET

`BarcodeGenerator` est la classe Aspose.BarCode utilisée pour générer des images de codes-barres avec des paramètres personnalisables. La même classe `BarcodeGenerator` que vous utilisez pour la lecture crée également des symboles DataMatrix. Vous pouvez contrôler la taille du module, la marge, le niveau ECC, et même intégrer une image de logo. Le générateur produit des fichiers PNG, JPEG, SVG ou PDF, vous offrant une flexibilité totale pour les scénarios web, impression ou mobile.

## Tutoriels de lecture de codes-barres DataMatrix
### [Programmation du lecteur DataMatrix](./datamatrix-reader-programming/)
Explorez la programmation du lecteur DataMatrix avec Aspose.BarCode pour .NET. Apprenez à générer et à lire des codes-barres DataMatrix dans vos applications .NET grâce à ce guide complet.
### [Configuration de l'append structuré DataMatrix](./datamatrix-structured-append-configuration/)
Apprenez à créer et à lire la configuration d'append structuré DataMatrix en .NET en utilisant Aspose.BarCode pour une organisation de données à haute efficacité.
### [Générer des codes-barres DataMatrix](./datamatrix-versions/)
Apprenez à générer des codes-barres DataMatrix en .NET avec Aspose.BarCode pour .NET. Dimensions personnalisées, prise en charge ECC, et plus encore.

## Questions fréquemment posées

**Q : Puis-je utiliser Aspose.BarCode pour des projets commerciaux ?**  
A : Oui. Une licence commerciale valide est requise pour une utilisation en production, mais un essai gratuit est disponible pour l'évaluation.

**Q : La bibliothèque prend‑elle en charge la lecture de DataMatrix à partir de fichiers PDF ?**  
A : Absolument. Vous pouvez charger une page PDF comme flux d'image et la transmettre directement au lecteur de code‑barres.

**Q : Comment gérer l'append structuré lorsqu'un code‑barres est réparti sur plusieurs images ?**  
A : L'API assemble automatiquement les fragments si vous activez la propriété `ReadStructuredAppend` avant le décodage.

**Q : Quels niveaux de correction d'erreurs sont disponibles lors de la génération d'un code‑barres DataMatrix ?**  
A : Vous pouvez choisir parmi ECC 000, 050, 080, 100, 140 et 200 en fonction de la densité de données requise et de la robustesse.

**Q : Existe‑t‑il un moyen d'améliorer les performances de lecture sur de grands lots d'images ?**  
A : Oui—utilisez le `BarcodeReader` avec `ReadMultipleBarcodes` réglé sur `true` et traitez les images dans des threads parallèles.

---

**Dernière mise à jour :** 2026-09-28  
**Testé avec :** Aspose.BarCode for .NET 24.12  
**Auteur :** Aspose

## Tutoriels associés

- [Comment générer des codes-barres DataMatrix avec Aspose.BarCode pour .NET – Guide pas à pas](/barcode/net/datamatrix-barcode-configuration/)
- [Comment lire l'append DataMatrix avec Aspose.BarCode pour .NET](/barcode/net/datamatrix-barcode-reading/datamatrix-structured-append-configuration/)
- [Générer un code-barres DataMatrix en mode ASCII avec Aspose.BarCode pour .NET (C#)](/barcode/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-ascii/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}