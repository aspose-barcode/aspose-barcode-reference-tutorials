---
date: 2025-12-19
description: Apprenez comment désactiver la validation du checksum en Java avec Aspose.BarCode.
  Ce guide étape par étape vous montre comment lire les codes‑barres, désactiver le
  checksum et garantir une gestion fiable des données.
linktitle: How to Disable Checksum Validation
second_title: Aspose.BarCode Java API
title: Comment désactiver la validation de la somme de contrôle en Java
url: /fr/java/checksum-and-validation/applying-checksum-validation/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Comment désactiver la validation du checksum en Java

Dans les applications modernes d'inventaire et de logistique, **comment désactiver le checksum** peut être la clé pour lire des codes-barres hérités qui n'incluent pas de chiffre de checksum. Aspose.BarCode for Java rend facile la désactivation de la validation du checksum tout en extrayant les données encodées. Ce tutoriel vous guide à travers l'ensemble du processus — depuis la configuration du projet jusqu'à la lecture d'un code-barres ONE‑CODE sans vérification du checksum.

## Réponses rapides
- **Que fait la désactivation du checksum ?** Elle indique au lecteur d'ignorer le champ checksum, permettant le traitement des codes-barres sans checksum valide.  
- **Quand devez‑vous désactiver le checksum ?** Lorsqu'on travaille avec des systèmes hérités ou des codes-barres non standard qui omettent ou corrompent le checksum.  
- **Quelle classe contrôle la validation du checksum ?** `BarCodeReader.setChecksumValidation(ChecksumValidation)`  
- **La désactivation du checksum est‑elle sûre ?** Seulement si vous faites confiance à la source du code-barres ; sinon, la validation aide à détecter les erreurs.  
- **Cela affecte‑t‑il d'autres types de codes‑barres ?** Le paramètre s'applique uniquement à l'instance actuelle de `BarCodeReader`.

## Qu'est‑ce que la validation du checksum ?
La validation du checksum est une vérification d'intégrité des données qui calcule une petite valeur à partir du contenu du code‑barres et la compare au checksum intégré. Si elles ne correspondent pas, le code‑barres est considéré comme illisible. Désactiver cette vérification indique à Aspose.BarCode d'ignorer la comparaison.

## Pourquoi désactiver le checksum avec Aspose.BarCode ?
- **Support hérité :** Les scanners plus anciens généraient souvent des codes‑barres sans checksum.  
- **Performance :** Sauter le calcul peut accélérer les lectures en masse.  
- **Flexibilité :** Vous pouvez décider, pour chaque instance de lecteur, d'appliquer ou non la validation.

## Prérequis
- **Java Development Kit (JDK) :** Assurez‑vous d'avoir la dernière version du JDK installée.  
- **Bibliothèque Aspose.BarCode :** Téléchargez la bibliothèque depuis le site officiel [here](https://releases.aspose.com/barcode/java/).  

## Importer les packages
Dans votre projet Java, importez les classes Aspose.BarCode nécessaires pour travailler avec la reconnaissance de codes‑barres.

```java
// Import Aspose.BarCode classes
import com.aspose.barcode.barcoderecognition.BarCodeReader;
import com.aspose.barcode.barcoderecognition.BarCodeResult;
import com.aspose.barcode.barcoderecognition.ChecksumValidation;
import com.aspose.barcode.barcoderecognition.DecodeType;
```

## Guide étape par étape

### Étape 1 : Configurer votre projet
Créez un nouveau projet Java (IDE de votre choix) et ajoutez le JAR Aspose.BarCode au classpath du projet.

### Étape 2 : Initialiser `BarCodeReader`
Chargez l'image contenant le code‑barres ONE‑CODE que vous souhaitez lire.

```java
String dataDir = "Your Document Directory";
BarCodeReader reader = new BarCodeReader(dataDir + "onecode.png", DecodeType.ONE_CODE);
```

### Étape 3 : Comment désactiver le checksum
Indiquez au lecteur d'ignorer la validation du checksum en définissant la propriété sur `OFF`.

```java
reader.setChecksumValidation(ChecksumValidation.OFF);
```

### Étape 4 : Lire les codes‑barres
Itérez sur les résultats et affichez le texte décodé ainsi que le type de symbologie.

```java
for (BarCodeResult result : reader.readBarCodes()) {
    System.out.println("CodeText: " + result.getCodeText());
    System.out.println("Symbology type: " + result.getCodeType());
}
```

**Résultat :** Le texte du code‑barres est affiché même si l'image originale ne possède pas de checksum valide.

## Problèmes courants et astuces
- **Chemin de fichier incorrect :** Vérifiez que `dataDir` pointe vers le bon dossier ; utilisez des chemins absolus pour les tests.  
- **Type de code‑barres non pris en charge :** Assurez‑vous que le `DecodeType` correspond au code‑barres que vous lisez.  
- **Performance :** Désactiver le checksum sur de gros lots peut améliorer le débit, mais réactivez‑le toujours pour les données critiques.

## Questions fréquemment posées

### Aspose.BarCode est‑il compatible avec différents types de codes‑barres ?
Oui, Aspose.BarCode prend en charge un large éventail de symbologies de codes‑barres, des QR et DataMatrix aux codes linéaires traditionnels.

### Puis‑je utiliser Aspose.BarCode à des fins commerciales ?
Absolument. Des licences commerciales sont disponibles pour les entreprises qui ont besoin de fonctionnalités prêtes pour la production.

### Comment obtenir du support pour Aspose.BarCode ?
Visitez le [forum Aspose.BarCode](https://forum.aspose.com/c/barcode/13) pour rejoindre la communauté et recevoir de l'aide de l'équipe produit.

### Existe‑t‑il un essai gratuit ?
Oui, vous pouvez explorer l'ensemble des fonctionnalités en téléchargeant l'[essai gratuit](https://releases.aspose.com/).

### Où puis‑je trouver une documentation détaillée ?
Référez‑vous à la [documentation](https://reference.aspose.com/barcode/java/) complète pour les détails de l'API, des exemples de code et les meilleures pratiques.

---

**Dernière mise à jour :** 2025-12-19  
**Testé avec :** Aspose.BarCode for Java (dernière version)  
**Auteur :** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}