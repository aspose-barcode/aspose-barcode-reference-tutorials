---
date: 2026-04-08
description: Apprenez à lire les codes-barres à partir d’un PDF en Java en utilisant
  Aspose.BarCode. Ce guide montre également comment générer une image de code-barres
  en Java et extraire des images d’un PDF en Java.
keywords:
- read barcode from pdf java
- generate barcode image java
- extract images from pdf java
linktitle: Reconnaître les codes-barres à partir d'un PDF
second_title: Aspose.BarCode Java API
title: Comment lire un code‑barres à partir d’un PDF en Java avec Aspose.BarCode
url: /fr/java/document-barcode-recognition/recognizing-barcodes-from-pdf/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# lire le code-barres à partir d'un PDF en Java

## Introduction

Bienvenue dans notre guide pas à pas sur **comment lire un code-barres à partir d'un PDF en Java** en utilisant Aspose.BarCode. Les codes-barres sont essentiels pour automatiser la capture de données, et avec Aspose.BarCode vous pouvez les détecter sans effort à l'intérieur des documents PDF. Dans ce tutoriel, nous vous accompagnerons à travers tout ce dont vous avez besoin — de la configuration des licences à la génération d'une image de code-barres Java, son ajout à un PDF, l'extraction d'images du PDF Java, et enfin la lecture du code-barres.

## Réponses rapides
- **Quelle bibliothèque faut‑il ?** Aspose.BarCode pour Java (plus Aspose.PDF pour la gestion des PDF).  
- **Puis‑je générer une image de code‑barres en Java ?** Oui – la classe `BarcodeGenerator` vous permet de créer des images PNG/JPEG.  
- **Comment les images sont‑elles extraites d'un PDF ?** Utilisez `PdfExtractor` d'Aspose.PDF.  
- **Quel type de code‑barres est démontré ?** CODE‑39 (standard).  
- **Ai‑je besoin d'une licence ?** Une licence valide Aspose.BarCode et Aspose.PDF est requise pour une utilisation en production.

## Pourquoi utiliser Aspose.BarCode pour Java ?
- **Haute précision** – prend en charge des dizaines de symbologies et fonctionne sur des images à basse résolution.  
- **Aucune dépendance externe** – pur Java, sans bibliothèques natives.  
- **Intégration PDF complète** – combinez avec Aspose.PDF pour lire ou intégrer des codes‑barres directement dans les fichiers PDF.

## Prérequis

Avant de plonger dans le code, assurez‑vous d'avoir :

1. **Licence Aspose.BarCode pour Java** – obtenez‑en une sur [Achat Aspose](https://purchase.aspose.com/buy).  
2. **Licence Aspose.PDF** – requise pour la manipulation des PDF ; vous pouvez demander une licence [ici](https://purchase.aspose.com/temporary-license/).  
3. **Bibliothèque Aspose.BarCode** – téléchargez le JAR le plus récent [ici](https://releases.aspose.com/barcode/java/).  

Maintenant que vous avez les prérequis nécessaires, importons les packages requis et commençons à coder.

## Importer les packages

Dans votre projet Java, ajoutez les imports Aspose.BarCode et Aspose.PDF. Ce bloc reste identique à celui du tutoriel original :

```java
import com.aspose.barcode.*;
import com.aspose.barcode.License;
import com.aspose.barcode.barcoderecognition.BarCodeReader;
import com.aspose.barcode.barcoderecognition.BarCodeResult;
import com.aspose.barcode.barcoderecognition.BaseDecodeType;
import com.aspose.barcode.barcoderecognition.DecodeType;
import com.aspose.pdf.*;
import com.aspose.pdf.facades.PdfExtractor;
import java.awt.image.BufferedImage;
import java.io.File;
import javax.imageio.ImageIO;
```

## Étape 1 : Générer une image de code‑barres Java

Tout d'abord, nous créons une image de code‑barres que nous intégrerons plus tard dans un PDF. Cela montre la capacité **générer une image de code‑barres java**.

```java
BarcodeGenerator builder = new BarcodeGenerator(com.aspose.barcode.EncodeTypes.CODE_39_STANDARD);
builder.setCodeText("test123");
String strBarCodeImageSave = dataDir + "input_image1.jpg";
builder.save(strBarCodeImageSave);
```

## Étape 2 : Créer un PDF et ajouter l'image du code‑barres

Ensuite, nous construisons un nouveau document PDF et insérons l'image du code‑barres que nous venons de générer.

```java
Document pdf1 = new Document();
Page page = pdf1.getPages().add();
BufferedImage originalImage = ImageIO.read(new File(strBarCodeImageSave));
page.getResources().getImages().add(originalImage);
pdf1.save(strPdfDoc);
```

## Étape 3 : Extraire les images du PDF Java

Avec le PDF prêt, nous devons récupérer l'image intégrée afin que le code‑barres puisse être lu. Cela utilise **extraire des images du pdf java**.

```java
PdfExtractor extractor = new PdfExtractor();
extractor.bindPdf(strPdfDoc);
extractor.extractImage();
```

## Étape 4 : Reconnaître le code‑barres à partir des images extraites

Enfin, nous transmettons chaque image extraite à `BarCodeReader` pour récupérer le texte encodé.

```java
String suffix = ".jpg";
int imageCount = 1;

while (extractor.hasNextImage()) {
    System.out.println("Extracting image " + imageCount);
    strBarCodeImage = "tmpbarcode" + imageCount + suffix;
    extractor.getNextImage(strBarCodeImage);

    BarCodeReader reader = new BarCodeReader(strBarCodeImage, DecodeType.CODE_39_EXTENDED);

    for (BarCodeResult result : reader.readBarCodes()) {
        System.out.println("CodeText: " + result.getCodeText());
        System.out.println("Symbology type: " + result.getCodeType());
    }

    imageCount++;
}
```

Répétez ces étapes selon vos besoins, en ajustant les noms de fichiers et les chemins pour correspondre à la structure de votre projet.

## Problèmes courants et solutions

| Problème | Raison | Correction |
|----------|--------|------------|
| **Aucun code‑barres détecté** | Qualité de l'image trop basse ou code‑barres trop petit. | Augmentez la résolution de l'image lors de l'enregistrement (`builder.save(..., BarCodeImageFormat.JPEG, 300)`). |
| **`PdfExtractor` lève une exception** | Fichier PDF introuvable ou chemin incorrect. | Vérifiez que `strPdfDoc` pointe vers un fichier existant et que l'application possède les permissions de lecture. |
| **Licence non appliquée** | Les composants Aspose fonctionnent en mode d'évaluation, limitant la sortie. | Chargez les fichiers de licence au démarrage de votre programme : `new License().setLicense("Aspose.BarCode.lic");` et de même pour Aspose.PDF. |

## Questions fréquentes (FAQ)

### Q : Puis‑je utiliser Aspose.BarCode pour Java sans licence ?
Bien que Aspose.BarCode puisse être utilisé sans licence, il est recommandé d'en obtenir une pour profiter de toutes les fonctionnalités et respecter les conditions de licence.

### Q : Comment obtenir une licence temporaire pour Aspose.BarCode pour Java ?
Vous pouvez obtenir une licence temporaire [ici](https://purchase.aspose.com/temporary-license/).

### Q : Existe‑t‑il des limitations sur les types de code‑barres pris en charge par Aspose.BarCode ?
Aspose.BarCode prend en charge un large éventail de types de code‑barres. Consultez la documentation pour la liste complète.

### Q : Une version d'essai est‑elle disponible pour Aspose.BarCode pour Java ?
Oui, vous pouvez télécharger la version d'essai [ici](https://releases.aspose.com/).

### Q : Où puis‑je obtenir du support ou poser des questions sur Aspose.BarCode pour Java ?
Visitez le [forum Aspose.BarCode](https://forum.aspose.com/c/barcode/13) pour le support et les discussions.

## Conclusion

Félicitations ! Vous avez appris comment **lire un code‑barres à partir d'un PDF en Java** en utilisant Aspose.BarCode, comment **générer une image de code‑barres Java**, et comment **extraire des images du PDF Java** pour un traitement ultérieur. N'hésitez pas à explorer des fonctionnalités supplémentaires telles que le traitement par lots, la prise en charge de différentes symbologies de code‑barres, ou l'intégration avec d'autres produits Aspose. Pour plus de détails, consultez la [documentation officielle](https://reference.aspose.com/barcode/java/).

---

**Dernière mise à jour :** 2026-04-08  
**Testé avec :** Aspose.BarCode pour Java 24.12, Aspose.PDF pour Java 24.12  
**Auteur :** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}