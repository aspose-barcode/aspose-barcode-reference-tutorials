---
date: 2025-12-19
description: Apprenez à lire les codes-barres Java à partir de documents Word avec
  Aspose.BarCode. Ce guide couvre la génération d'images de codes-barres, leur insertion
  dans Word et l'extraction d'images pour la lecture des codes-barres.
linktitle: read barcode java from Word Documents
second_title: Aspose.BarCode Java API
title: Comment lire un code‑barres Java depuis des documents Word
url: /fr/java/document-barcode-recognition/recognizing-barcodes-from-word/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Comment lire un code-barres java à partir de documents Word

## Introduction

Travailler avec des codes-barres dans les applications Java est un besoin courant, surtout lorsque ces codes-barres sont intégrés dans des fichiers Microsoft Word. Dans ce tutoriel, vous apprendrez **comment lire un code-barres java** à partir d'un document Word en utilisant Aspose.BarCode for Java. Nous parcourrons la génération d'une image de code-barres, l'ajout du code-barres à un fichier Word, l'extraction d'images du document Word, et enfin le décodage du code-barres avec un exemple de lecteur de code-barres Java.

## Réponses rapides
- **Quelle bibliothèque est utilisée ?** Aspose.BarCode for Java (avec Aspose.Words pour la gestion des images)  
- **Puis-je ajouter un code-barres à Word ?** Oui – générez l'image puis insérez‑la avec Aspose.Words  
- **Comment extraire des images de Word ?** Utilisez `Document.getChildNodes(NodeType.SHAPE, true)`  
- **Existe‑t‑il un exemple de lecteur de code-barres Java ?** Le code à l'étape 3 montre un exemple complet  
- **Quelles sont les prérequis ?** JDK, Aspose.BarCode for Java, un IDE (Eclipse/IntelliJ)

## Qu'est-ce que la reconnaissance de code-barres en Java ?

La reconnaissance de code-barres en Java désigne le processus de détection et de décodage des symboles de code-barres à partir d'images ou de documents à l'aide d'une bibliothèque telle qu'Aspose.BarCode. Elle permet aux applications de lire automatiquement les codes produit, les identifiants d'inventaire ou toute donnée encodée sans saisie manuelle.

## Pourquoi lire un code-barres java à partir de documents Word ?

Intégrer des codes-barres directement dans les fichiers Word est utile pour les contrats, les étiquettes d'expédition ou les rapports où une représentation visuelle du code est requise. Pouvoir **extraire des images de Word** et les décoder de manière programmatique élimine le besoin de numérisation manuelle et réduit les erreurs.

## Prérequis

Avant de commencer, assurez-vous d'avoir :

- **Java Development Kit (JDK)** – un JDK récent installé sur votre machine.  
- **Aspose.BarCode for Java** – téléchargez la bibliothèque depuis le site officiel [ici](https://releases.aspose.com/barcode/java/).  
- **Environnement de développement intégré (IDE)** – tel que Eclipse ou IntelliJ IDEA pour écrire et exécuter le code.

## Importer les packages

Dans votre projet Java, importez les packages Aspose.BarCode et Aspose.Words nécessaires :

```java
import java.text.MessageFormat;

import com.aspose.barcode.EncodeTypes;
import com.aspose.barcode.barcoderecognition.BarCodeReader;
import com.aspose.barcode.barcoderecognition.BarCodeResult;
import com.aspose.barcode.barcoderecognition.DecodeType;
import com.aspose.barcode.generation.BarcodeGenerator;
import com.aspose.words.ImageType;
import com.aspose.words.NodeCollection;
import com.aspose.words.NodeType;
```

## Étape 1 : Générer une image de code-barres (generate barcode image java)

Tout d'abord, créez une image de code-barres en utilisant Aspose.BarCode. Cette image sera ensuite **ajoutée au document Word** :

```java
BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.CODE_39_STANDARD);
generator.setCodeText("test-123");
String strBarCodeImageSave = dataDir + "img.jpg";
generator.save(strBarCodeImageSave);
```

## Étape 2 : Insérer l'image du code-barres dans un document Word (insert image into word)

Nous allons maintenant utiliser Aspose.Words pour **insérer l'image dans Word** et enregistrer le document :

```java
Document doc = new Document();
DocumentBuilder docBuilder = new DocumentBuilder(doc);
docBuilder.insertImage(strBarCodeImageSave);
String strWordFile = "docout.doc";
doc.save(dataDir + strWordFile);
```

## Étape 3 : Reconnaître les codes-barres du document Word (java barcode reader example)

Enfin, extrayez chaque image du fichier Word et exécutez l'**exemple de lecteur de code-barres Java** pour décoder le code-barres :

```java
NodeCollection<Shape> shapes = doc.getChildNodes(NodeType.SHAPE, true);
int imageIndex = 0;

for (Shape shape : shapes) {
    if (shape.hasImage()) {
        // Extract image to file
        String extension = ImageTypeToExtension(shape.getImageData().getImageType());
        String imageFileName = MessageFormat.format("Image.ExportImages.{0} Out.{1}", imageIndex, extension);
        String strBarCodeImageExtracted = "" + imageFileName;
        shape.getImageData().save(strBarCodeImageExtracted);

        // Recognize barcode from this image
        BarCodeReader reader = new BarCodeReader(strBarCodeImageSave, DecodeType.CODE_39_STANDARD);
        for (BarCodeResult result : reader.readBarCodes()) {
            System.out.println("CodeText: " + result.getCodeText());
            System.out.println("Symbology type: " + result.getCodeType());
        }
        imageIndex++;
    }
}
```

> **Remarque :** La boucle ci‑dessus montre comment **extraire des images de Word**, enregistre chaque image, puis décodera le code-barres en utilisant le même chemin de fichier image. Ajustez les chemins de fichiers (`dataDir`) selon les besoins de votre environnement.

## Problèmes courants et astuces

- **Incohérences de chemin de fichier** – Assurez‑vous que `dataDir` pointe vers un dossier valide ; sinon le lecteur lèvera une `FileNotFoundException`.  
- **Types de code-barres non pris en charge** – L'exemple utilise `CODE_39_STANDARD`. Si vous avez besoin de QR, DataMatrix, etc., modifiez à la fois `EncodeTypes` et `DecodeType` en conséquence.  
- **Performance** – Pour les gros documents, envisagez de traiter les images en flux parallèles afin d'accélérer la reconnaissance.

## Questions fréquemment posées (FAQ)

### Q : Puis‑je utiliser Aspose.BarCode for Java dans des projets commerciaux ?
Oui, Aspose.BarCode for Java est disponible pour une utilisation commerciale. Vous pouvez trouver les détails de licence [ici](https://purchase.aspose.com/buy).

### Q : Existe‑t‑il une version d'essai gratuite d'Aspose.BarCode for Java ?
Oui, vous pouvez explorer les fonctionnalités d'Aspose.BarCode for Java en téléchargeant la version d'essai gratuite [ici](https://releases.aspose.com/).

### Q : Comment obtenir du support pour Aspose.BarCode for Java ?
Pour toute assistance ou question, visitez le forum Aspose.BarCode [ici](https://forum.aspose.com/c/barcode/13).

### Q : Des licences temporaires sont‑elles disponibles pour Aspose.BarCode for Java ?
Oui, vous pouvez obtenir des licences temporaires [ici](https://purchase.aspose.com/temporary-license/).

### Q : Où puis‑je trouver la documentation d'Aspose.BarCode for Java ?
Reportez‑vous à la documentation complète [ici](https://reference.aspose.com/barcode/java/).

## FAQ supplémentaires

**Q : Puis‑je lire d'autres symbologies de code‑barres que Code 39 ?**  
R : Absolument. Il suffit de changer `EncodeTypes` lors de la génération et `DecodeType` lors de la lecture pour correspondre à la symbologie souhaitée (par ex., `EncodeTypes.QR`, `DecodeType.QR`).

**Q : Cette approche fonctionne‑t‑elle également avec les fichiers .docx ?**  
R : Oui. Aspose.Words gère les formats `.doc` et `.docx` de façon transparente ; le même code fonctionne pour les deux.

**Q : Comment améliorer la précision de reconnaissance pour les images basse résolution ?**  
R : Augmentez le DPI lors de l'enregistrement de l'image du code‑barres (`generator.save(strBarCodeImageSave, BarCodeImageFormat.JPEG, 300)`) ou utilisez un format d'image de meilleure qualité comme PNG.

---

**Dernière mise à jour :** 2025-12-19  
**Testé avec :** Aspose.BarCode for Java 24.11 et Aspose.Words for Java 24.11  
**Auteur :** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}