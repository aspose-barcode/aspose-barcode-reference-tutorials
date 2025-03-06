---
title: Word 文書からの簡単なバーコード認識
linktitle: Word 文書からのバーコードの認識
second_title: Aspose.BarCode Java API
description: Aspose.BarCode を使用して、Java アプリケーションへのバーコード認識のシームレスな統合を検討してください。 Word 文書からバーコードを認識するには、このチュートリアルに従ってください。
weight: 12
url: /ja/java/document-barcode-recognition/recognizing-barcodes-from-word/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Word 文書からの簡単なバーコード認識


## 導入

Java プログラミングの動的な世界では、バーコードを効率的に操作する必要性がますます高まっています。 Word 文書からのバーコードを認識することは一般的な要件であり、幸いなことに、Aspose.BarCode for Java は堅牢なソリューションを提供します。このチュートリアルでは、Aspose.BarCode for Java を使用して Word 文書からバーコードを認識するプロセスを説明します。

## 前提条件

チュートリアルに入る前に、次の前提条件を満たしていることを確認してください。

- Java 開発キット (JDK): Aspose.BarCode for Java には Java 開発環境が必要です。システムに最新の JDK がインストールされていることを確認してください。

-  Aspose.BarCode for Java: Aspose.BarCode for Java ライブラリをダウンロードしてインストールします。ダウンロードリンクが見つかります[ここ](https://releases.aspose.com/barcode/java/).

- 統合開発環境 (IDE): Eclipse や IntelliJ など、好みの IDE を選択して例に従ってください。

## パッケージのインポート

Java プロジェクトで、必要な Aspose.BarCode パッケージをインポートして開始します。

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

## ステップ 1: バーコード画像の生成

まず、Aspose.BarCode を使用してバーコード画像を作成します。コードテキストを設定し、画像を保存します。

```java
BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.CODE_39_STANDARD);
generator.setCodeText("test-123");
String strBarCodeImageSave = dataDir + "img.jpg";
generator.save(strBarCodeImageSave);
```

## ステップ 2: Word 文書に画像を追加する

ここで、Aspose.Words を使用して、生成されたバーコード イメージを Word ドキュメントに挿入します。

```java
Document doc = new Document();
DocumentBuilder docBuilder = new DocumentBuilder(doc);
docBuilder.insertImage(strBarCodeImageSave);
String strWordFile = "docout.doc";
doc.save(dataDir + strWordFile);
```

## ステップ 3: Word 文書からバーコードを認識する

次に、Word 文書から画像を抽出し、Aspose.BarCode を使用してバーコードを認識します。

```java
NodeCollection<Shape> shapes = doc.getChildNodes(NodeType.SHAPE, true);
int imageIndex = 0;

for (Shape shape : shapes) {
    if (shape.hasImage()) {
        //画像をファイルに抽出する
        String extension = ImageTypeToExtension(shape.getImageData().getImageType());
        String imageFileName = MessageFormat.format("Image.ExportImages.{0} Out.{1}", imageIndex, extension);
        String strBarCodeImageExtracted = "" + imageFileName;
        shape.getImageData().save(strBarCodeImageExtracted);

        //この画像からバーコードを認識します
        BarCodeReader reader = new BarCodeReader(strBarCodeImageSave, DecodeType.CODE_39_STANDARD);
        for (BarCodeResult result : reader.readBarCodes()) {
            System.out.println("CodeText: " + result.getCodeText());
            System.out.println("Symbology type: " + result.getCodeType());
        }
        imageIndex++;
    }
}
```

これらの手順を繰り返すと、Aspose.BarCode for Java を使用して Word 文書からバーコードを正常に認識できるようになります。

## 結論

結論として、Aspose.BarCode for Java を活用すると、Word 文書からバーコードを認識するプロセスが簡素化されます。上記の手順に従うと、バーコード認識を Java アプリケーションにシームレスに統合できます。

## よくある質問 (FAQ)

### Q: Aspose.BarCode for Java を商用プロジェクトで使用できますか?
はい、Aspose.BarCode for Java は商用利用できます。ライセンスの詳細を確認できます[ここ](https://purchase.aspose.com/buy).

### Q: Aspose.BarCode for Java の無料トライアルはありますか?
はい、無料トライアルをダウンロードすると、Aspose.BarCode for Java の機能を探索できます。[ここ](https://releases.aspose.com/).

### Q: Aspose.BarCode for Java のサポートを受けるにはどうすればよいですか?
サポートや質問がある場合は、Aspose.BarCode フォーラムにアクセスしてください。[ここ](https://forum.aspose.com/c/barcode/13).

### Q: Aspose.BarCode for Java の一時ライセンスは利用できますか?
はい、一時ライセンスを取得できます[ここ](https://purchase.aspose.com/temporary-license/).

### Q: Aspose.BarCode for Java のドキュメントはどこで見つけられますか?
包括的なドキュメントを参照してください[ここ](https://reference.aspose.com/barcode/java/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
