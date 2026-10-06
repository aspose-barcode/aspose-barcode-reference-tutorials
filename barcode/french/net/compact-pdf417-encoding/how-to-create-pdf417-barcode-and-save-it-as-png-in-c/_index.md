---
category: general
date: 2026-10-05
description: Apprenez à créer un code‑barres PDF417 en C# et à générer un PNG de code‑barres
  avec du code étape par étape et des conseils de bonnes pratiques.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create PDF417 barcode
- generate barcode PNG
- how to generate PDF417
language: fr
lastmod: 2026-10-05
og_description: Créez un code‑barres PDF417 en C# et générez instantanément un PNG
  du code‑barres. Suivez ce tutoriel complet pour une solution prête à la production.
og_image_alt: Example of a compact PDF417 barcode created with C#
og_title: Créer un code-barres PDF417 en C# – guide complet pour générer un PNG
schemas:
- author: Aspose
  dateModified: '2026-10-05'
  description: Learn how to create PDF417 barcode in C# and generate barcode PNG with
    step‑by‑step code and best‑practice tips.
  headline: How to create PDF417 barcode and save it as PNG in C#
  type: TechArticle
- description: Learn how to create PDF417 barcode in C# and generate barcode PNG with
    step‑by‑step code and best‑practice tips.
  name: How to create PDF417 barcode and save it as PNG in C#
  steps:
  - name: Expected output
    text: When you open `CompactPdf417.png`, you should see a vertical, high‑density
      barcode that encodes the string *Åspóse.Barcóde©*. Scanning the image with any
      PDF417 reader returns the original text.
  - name: Generating other image formats
    text: 'If you prefer JPEG or BMP, change the `BarCodeImageFormat` enum:'
  - name: Adjusting error correction
    text: 'For harsh environments (e.g., outdoor signage), increase the error‑correction
      level:'
  - name: Encoding binary data
    text: 'PDF417 can encode binary payloads. Pass a `byte[]` instead of a string:'
  - name: Handling very long strings
    text: 'When the data exceeds the default capacity, the generator automatically
      creates additional rows. You can limit the row count to avoid oversized images:'
  type: HowTo
tags:
- barcode
- PDF417
- C#
- image generation
title: Comment créer un code‑barres PDF417 et l’enregistrer au format PNG en C#
url: /fr/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-and-save-it-as-png-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Comment créer un code-barres PDF417 et l'enregistrer au format PNG en C#

Si vous devez **créer un code-barres PDF417** dans une application .NET, ce guide vous montre exactement comment le faire. Vous obtiendrez un extrait C# prêt à l'emploi qui génère un fichier **PNG de code-barres** de haute qualité, et vous comprendrez chaque paramètre qui influence le résultat.

La génération de codes-barres est une exigence courante pour les systèmes de billetterie, le suivi d'inventaire et le codage de documents sécurisés. À la fin de ce tutoriel, vous pourrez répondre à la question « **comment générer PDF417** » avec un exemple complet et exécutable.

## Prérequis

* SDK .NET 6.0 ou version ultérieure installé  
* Un environnement de développement tel que Visual Studio 2022 ou VS Code  
* Le package NuGet **Aspose.BarCode for .NET** (ou toute bibliothèque compatible qui prend en charge PDF417)  

Vous pouvez ajouter le package avec la commande suivante :

```bash
dotnet add package Aspose.BarCode
```

Le code ci‑dessous utilise l'API Aspose car elle offre un contrôle granulaire sur les paramètres PDF417 et prend en charge l'exportation PNG prête à l'emploi.

## Étape 1 : Configurer le projet et importer les espaces de noms

Créez un nouveau projet console et importez les espaces de noms requis :

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;
```

L'espace de noms `Aspose.BarCode.Generation` contient la classe `BarcodeGenerator`, qui est le point d'entrée pour **créer des images de code-barres PDF417**.

## Étape 2 : Créer un code-barres PDF417 avec le texte souhaité

Instanciez le générateur avec l'énumération `EncodeTypes.Pdf417` et les données que vous souhaitez encoder. L'exemple utilise une chaîne contenant des caractères spéciaux pour démontrer la gestion Unicode :

```csharp
// Step 2: Create a PDF417 barcode generator with the desired text
var generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Åspóse.Barcóde©");
```

Le générateur possède maintenant un objet code-barres que vous pouvez configurer avant le rendu.

## Étape 3 : Configurer les paramètres visuels

L'ajustement fin du code-barres améliore la lisibilité et réduit la taille de l'image. Les paramètres les plus souvent modifiés sont **X‑dimension**, **colonnes** et **mode compact**.

```csharp
// Step 3: Set the X‑dimension (module width) in pixels
generator.Parameters.Barcode.XDimension.Pixels = 2;

// Step 4: Define the number of columns for the PDF417 code
generator.Parameters.Barcode.Pdf417.Columns = 3;

// Step 5: Enable compact (truncated) mode to reduce the barcode size
generator.Parameters.Barcode.Pdf417.Truncate = true;
```

* **X‑dimension** contrôle la largeur de chaque module ; une valeur de `2` pixels donne un code-barres compact mais lisible.  
* **Columns** (colonnes) détermine le nombre de colonnes de données utilisées par le code. Moins de colonnes rendent le code-barres plus étroit mais plus haut.  
* **Truncate** active le mode « compact » défini par la spécification PDF417, qui supprime les lignes de remplissage inutiles.  

Vous pouvez expérimenter avec `Rows` et `ErrorCorrectionLevel` si votre cas d'utilisation nécessite une plus grande résilience aux dommages.

## Étape 4 : Enregistrer le code-barres en tant qu'image PNG

Enfin, exportez le code-barres vers un fichier PNG. Le PNG conserve les bords nets et prend en charge la transparence, ce qui le rend idéal pour les scénarios web et impression.

```csharp
// Step 6: Save the generated barcode as a PNG image
string outputPath = @"C:\Barcodes\CompactPdf417.png";
generator.Save(outputPath, BarCodeImageFormat.Png);
Console.WriteLine($"Barcode saved to {outputPath}");
```

L'exécution du programme crée `CompactPdf417.png` dans le répertoire spécifié. L'image ressemble à ceci :

![Code-barres PDF417 compact créé avec C#](compact-pdf417.png "Exemple d'un code-barres PDF417 compact créé avec C#")

*Le texte alternatif ci‑dessus contient le mot‑clé principal, répondant aux exigences SEO et d'accessibilité.*

## Exemple complet et exécutable

En assemblant tous les éléments, voici un programme autonome que vous pouvez copier, coller et exécuter :

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Program
{
    static void Main()
    {
        // 1. Initialize the generator with PDF417 type and sample data
        var generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Åspóse.Barcóde©");

        // 2. Configure size and compactness
        generator.Parameters.Barcode.XDimension.Pixels = 2;          // module width
        generator.Parameters.Barcode.Pdf417.Columns = 3;           // number of columns
        generator.Parameters.Barcode.Pdf417.Truncate = true;       // enable compact mode

        // 3. Optional: increase error correction for damaged prints
        // generator.Parameters.Barcode.Pdf417.ErrorCorrectionLevel = 5;

        // 4. Export to PNG
        string outputPath = @"C:\Barcodes\CompactPdf417.png";
        generator.Save(outputPath, BarCodeImageFormat.Png);

        Console.WriteLine($"Barcode saved to {outputPath}");
    }
}
```

### Résultat attendu

Lorsque vous ouvrez `CompactPdf417.png`, vous devriez voir un code-barres vertical à haute densité qui encode la chaîne *Åspóse.Barcóde©*. Scanner l'image avec n'importe quel lecteur PDF417 renvoie le texte original.

## Pourquoi ces paramètres sont importants

* **X‑dimension** influence à la fois la taille physique et la vitesse de lecture. Des modules plus petits augmentent la densité des données mais peuvent nécessiter des lecteurs à plus haute résolution.  
* **Columns** (colonnes) affectent le rapport d'aspect. Pour les reçus mobiles, un faible nombre de colonnes maintient le code-barres suffisamment étroit pour tenir sur du papier étroit.  
* **Truncate** réduit le nombre de lignes, économisant de l'encre et de l'espace sans sacrifier l'intégrité des données, car PDF417 inclut déjà des mots de correction d'erreur.  

Comprendre ces paramètres vous permet d'adapter le code-barres aux contraintes de votre support cible—qu'il s'agisse d'une imprimante d'étiquettes, d'une page web ou d'une application mobile.

## Variantes courantes et cas limites

### Générer d'autres formats d'image

Si vous préférez JPEG ou BMP, modifiez l'énumération `BarCodeImageFormat` :

```csharp
generator.Save(@"C:\Barcodes\Pdf417.jpg", BarCodeImageFormat.Jpeg);
```

JPEG compresse l'image mais peut introduire des artefacts qui affectent la lecture à petite taille.

### Ajuster la correction d'erreur

Pour des environnements difficiles (par ex., signalisation extérieure), augmentez le niveau de correction d'erreur :

```csharp
generator.Parameters.Barcode.Pdf417.ErrorCorrectionLevel = 8; // max is 8
```

Des niveaux plus élevés ajoutent plus de redondance, rendant le code-barres plus grand mais plus robuste.

### Encoder des données binaires

PDF417 peut encoder des charges binaires. Passez un `byte[]` au lieu d'une chaîne :

```csharp
byte[] binaryData = new byte[] { 0x01, 0xFF, 0xA5 };
generator = new BarcodeGenerator(EncodeTypes.Pdf417, binaryData);
```

La bibliothèque bascule automatiquement en mode binaire.

### Gérer des chaînes très longues

Lorsque les données dépassent la capacité par défaut, le générateur crée automatiquement des lignes supplémentaires. Vous pouvez limiter le nombre de lignes pour éviter des images surdimensionnées :

```csharp
generator.Parameters.Barcode.Pdf417.Rows = 30; // max rows
```

Si le contenu ne tient toujours pas, envisagez de le diviser en plusieurs codes-barres.

## Astuces professionnelles

* **Mettez en cache le générateur** si vous devez créer de nombreux codes-barres avec les mêmes paramètres. Réutiliser l'objet évite des allocations répétées de ressources internes.  
* **Définissez `Resolution`** sur les `ImageOptions` si vous avez besoin d'une résolution DPI spécifique pour l'impression :

  ```csharp
  generator.Parameters.ImageResolution = 300; // DPI
  ```

* **Validez la sortie** programmatique avec `BarCodeReader` pour vous assurer que le PNG généré peut être décodé avant de le distribuer aux utilisateurs.

## Conclusion

Vous savez maintenant comment **créer un code-barres PDF417** en C# et **générer des fichiers PNG de code-barres** avec un contrôle complet sur la taille, les colonnes et le mode compact. L'exemple complet montre l'approche standard, explique pourquoi chaque paramètre est important et couvre les variantes telles que la correction d'erreur, les formats alternatifs et les données binaires. Utilisez les astuces ci‑dessus pour adapter la solution à votre flux de travail spécifique, que vous construisiez un système de billetterie, un générateur d'étiquettes logistiques ou un encodeur de documents sécurisés.

---

**Prochaines étapes**

* Explorez d'autres symbologies 2D (DataMatrix, QR) en utilisant la même classe `BarcodeGenerator`.  
* Intégrez la création de code-barres dans une API ASP.NET Core pour fournir des PNG à la demande.  
* Combinez l'image du code-barres avec des bibliothèques de génération de PDF pour l'intégrer directement aux rapports.

Bon codage !

## Que devriez‑vous apprendre ensuite ?

Les tutoriels suivants couvrent des sujets étroitement liés qui s'appuient sur les techniques démontrées dans ce guide. Chaque ressource comprend des exemples de code complets et fonctionnels avec des explications étape par étape pour vous aider à maîtriser des fonctionnalités supplémentaires de l'API et explorer des approches d'implémentation alternatives dans vos propres projets.

- [Comment créer un code-barres pdf417 en C# – guide étape par étape](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-in-c-step-by-step-guide/)
- [Comment générer un code-barres micro pdf417 en C# – guide étape par étape](/barcode/english/net/compact-pdf417-encoding/how-to-generate-micro-pdf417-barcode-in-c-step-by-step-guide/)
- [Comment créer un code-barres PDF417 en C# avec le mode compact](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-in-c-with-compact-mode/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}