---
date: 2026-01-15
description: Guide de tutoriel pas à pas sur les codes-barres pour lire un code DataMatrix
  en C# et générer une image de code-barres en C# en utilisant Aspose.BarCode pour
  .NET.
linktitle: DataMatrix Encoding Mode (Auto)
second_title: Aspose.BarCode .NET API
title: Lire le code‑barres DataMatrix C# – Générer le mode DataMatrix (Auto)
url: /fr/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-auto/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Lire un code‑barres DataMatrix C# – Générer le mode DataMatrix (Auto)

Dans le monde numérique d’aujourd’hui, pouvoir **lire un code‑barres DataMatrix C#** rapidement et de façon fiable est essentiel, que ce soit pour le suivi d’inventaire ou la gestion sécurisée de documents. Ce tutoriel vous guide dans la génération d’un code‑barres DataMatrix en mode *Auto* avec Aspose.BarCode pour .NET, puis montre comment lire ce code‑barres en C#. Que vous suiviez un **guide de tutoriel de code‑barres** ou que vous ayez simplement besoin d’un exemple de code solide, vous terminerez ce guide avec une solution fonctionnelle que vous pourrez intégrer à vos propres projets.

## Réponses rapides
- **Que fait le mode “Auto” ?** Il permet à Aspose.BarCode de sélectionner automatiquement le meilleur schéma d’encodage pour vos données.  
- **Quelle bibliothèque est requise ?** Aspose.BarCode pour .NET (essai gratuit disponible).  
- **Puis‑je lire le code‑barres dans la même application ?** Oui – utilisez `BarCodeReader` avec `DecodeType.DataMatrix`.  
- **Ai‑je besoin d’une licence pour la production ?** Une licence commerciale est requise pour une utilisation en production.  
- **Versions .NET prises en charge ?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## Qu’est‑ce que lire un code‑barres DataMatrix C# ?
Lire un code‑barres DataMatrix en C# signifie décoder la matrice bidimensionnelle de modules noirs et blancs pour retrouver le texte ou les données d’origine. Aspose.BarCode fournit une API simple qui abstrait le traitement d’image de bas niveau, vous permettant de vous concentrer sur votre logique métier.

## Pourquoi utiliser Aspose.BarCode pour générer une image de code‑barres C# ?
- **Fiabilité :** Gère toutes les normes DataMatrix et sélectionne automatiquement l’encodage optimal.  
- **Flexibilité :** Contrôle complet sur les dimensions, l’encodage ECI et le format d’image.  
- **Multiplateforme :** Fonctionne avec .NET Framework, .NET Core et les applications .NET 5+.  

## Prérequis

1. **Environnement .NET** – Installez le dernier runtime .NET depuis le site [.NET](https://dotnet.microsoft.com/download/dotnet).  
2. **Aspose.BarCode pour .NET** – Téléchargez la bibliothèque depuis le [site web](https://releases.aspose.com/barcode/net/).  

## Importation des espaces de noms

```csharp
using Aspose.BarCode.BarCodeRecognition;
using Aspose.BarCode.Generation;
using System;
using System.Drawing;
```

Maintenant que les espaces de noms sont en place, parcourons le code étape par étape.

## Étape 1 : Définir le chemin du répertoire

```csharp
string path = "Your Directory Path";
```

Remplacez `"Your Directory Path"` par le dossier où vous souhaitez enregistrer le PNG (ou autre format) généré.

## Étape 2 : Créer un code‑barres DataMatrix en mode Auto

```csharp
using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.DataMatrix, "Aspose常に先を行く"))
{
    generator.Parameters.Barcode.XDimension.Pixels = 4;
    generator.Parameters.Barcode.DataMatrix.DataMatrixEncodeMode = DataMatrixEncodeMode.Auto;
    generator.Parameters.Barcode.DataMatrix.ECIEncoding = ECIEncodings.UTF8;
    Bitmap bitmap = generator.GenerateBarCodeImage();
}
```

Le paramètre `DataMatrixEncodeMode.Auto` laisse la bibliothèque choisir le meilleur encodage pour le texte fourni. N’hésitez pas à remplacer le texte d’exemple par n’importe quelle chaîne que vous devez **générer une image de code‑barres C#**.

## Étape 3 : Lire le code‑barres (read DataMatrix barcode C#)

```csharp
using (BarCodeReader reader = new BarCodeReader(bitmap, DecodeType.DataMatrix))
{
    reader.ReadBarCodes();
    Console.WriteLine(reader.FoundBarCodes[0].CodeText);
}
```

Cet extrait décode l’image que nous venons de générer et affiche le texte d’origine dans la console, démontrant un aller‑retour complet de la génération à la lecture.

## Problèmes courants et solutions

| Problème | Cause | Solution |
|----------|-------|----------|
| **Aucun code‑barres détecté** | Résolution d’image trop faible | Augmentez `XDimension.Pixels` (par ex., à 6) |
| **Caractères illisibles** | Mauvais encodage ECI | Définissez `ECIEncoding` correspondant à vos données (UTF‑8, ASCII, etc.) |
| **Exception sur `ReadBarCodes`** | Bitmap libéré avant la lecture | Conservez l’instance `Bitmap` vivante jusqu’après la lecture |

## Foire aux questions

**Q : Qu’est‑ce que le mode d’encodage DataMatrix “Auto” ?**  
R : Il permet à Aspose.BarCode de sélectionner automatiquement la méthode d’encodage optimale pour les données fournies, simplifiant le processus **comment générer un code‑barres datamatrix**.

**Q : Puis‑je personnaliser les dimensions du code‑barres généré ?**  
R : Oui – ajustez `generator.Parameters.Barcode.XDimension.Pixels` pour modifier la taille des modules.

**Q : Aspose.BarCode pour .NET convient‑il à un usage commercial ?**  
R : Absolument. Achetez une licence sur le [site web](https://purchase.aspose.com/buy).

**Q : Existe‑t‑il un essai gratuit ?**  
R : Oui, vous pouvez explorer Aspose.BarCode avec un essai gratuit via [ce lien](https://releases.aspose.com/).

**Q : Quelles options d’encodage sont disponibles pour les codes‑barres DataMatrix ?**  
R : Aspose.BarCode prend en charge UTF‑8, ASCII et d’autres encodages ECI ; définissez la valeur souhaitée via `ECIEncoding`.

## Conclusion

Vous disposez maintenant d’un exemple complet, prêt pour la production, qui **lit un code‑barres DataMatrix C#**, génère le code‑barres en mode Auto et vérifie le résultat – le tout avec Aspose.BarCode pour .NET. Expérimentez avec différents textes, tailles et paramètres ECI pour répondre à votre scénario spécifique, et consultez la [documentation officielle](https://reference.aspose.com/barcode/net/) pour des personnalisations plus avancées.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Dernière mise à jour :** 2026-01-15  
**Testé avec :** Aspose.BarCode 24.12 pour .NET  
**Auteur :** Aspose  

---