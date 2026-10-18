---
category: general
date: 2026-10-18
description: Java を使用して Planet シンボロジーのバーコード画像を生成します。カスタムのバーコード寸法と空白バーで Planet バーコードを作成する方法を学びましょう。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate barcode image
- create planet barcode
- custom barcode dimensions
language: ja
lastmod: 2026-10-18
og_description: JavaでPlanetシンボロジーのバーコード画像を生成します。このチュートリアルでは、カスタムのバーコード寸法とアウトラインバーを使用してPlanetバーコードを作成する方法を示します。
og_image_alt: Generated barcode image showing a Planet barcode with empty outline
  bars
og_title: Planetシンボロジー用バーコード画像の生成 – Javaガイド
schemas:
- author: Aspose
  dateModified: '2026-10-18'
  description: Generate barcode image for Planet symbology using Java. Learn to create
    planet barcode with custom barcode dimensions and empty bars.
  headline: Generate barcode image for Planet symbology in Java
  type: TechArticle
tags:
- barcode
- Java
- imaging
title: JavaでPlanetシンボロジー用のバーコード画像を生成する
url: /ja/python-java/general/generate-barcode-image-for-planet-symbology-in-java/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# JavaでPlanetシンボロジーのバーコード画像を生成する

Planetシンボロジーの**バーコード画像を生成**する必要がある場合、このガイドはプロセス全体を案内します。郵便自動化システムやカスタム追跡ソリューションを構築しているかどうかに関わらず、**カスタムバーコード寸法**とアウトライン（空白）バーを使用した**planetバーコードの作成**方法を学べます。

この例では Aspose.BarCode for Java ライブラリを使用します。このライブラリは主要なすべてのバーコード規格に対して流暢な API を提供します。追加の画像処理ツールは不要で、コードは任意の Java 8+ ランタイム上で実行できます。

## 前提条件

* Java 8 以上がインストールされていること（本チュートリアルは JDK 17 でテストしています）。
* 依存関係管理のための Maven または Gradle。
* Java の構文とバーコードの概念に関する基本的な知識。

Maven が初めての場合は、`mvn archetype:generate` でシンプルなプロジェクトを作成し、以下に示す Aspose.BarCode の依存関係を追加できます。

## Aspose.BarCode の依存関係を追加する

```xml
<!-- pom.xml -->
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-barcode</artifactId>
    <version>23.12</version> <!-- Use the latest version available -->
</dependency>
```

> **プロのコツ:** ライブラリが更新された際の予期せぬ破壊的変更を防ぐため、バージョン番号を固定してください。

## 手順 1: Planetシンボロジー用のバーコードジェネレーターを初期化する

```java
import com.aspose.barcode.BarCodeImageFormat;
import com.aspose.barcode.EncodeTypes;
import com.aspose.barcode.generator.BarcodeGenerator;

public class PlanetBarcodeDemo {
    public static void main(String[] args) {
        // Step 1 – create a generator that encodes data using the Planet symbology
        BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
                EncodeTypes.PLANET,          // Planet is the barcode type
                "123456");                   // Data to encode
```

**この手順が重要な理由:**  
`EncodeTypes.PLANET` はライブラリに Planet バーコード仕様を使用するよう指示します。これは郵便サービスで一般的に使用されます。データ文字列 `"123456"` は生成された画像に表示されるペイロードです。

## 手順 2: カスタムバーコード寸法（X ディメンション）を設定する

```java
        // Step 2 – adjust the X dimension (module width) to 4 pixels.
        // This controls the thickness of each bar.
        barcodeGenerator.getParameters()
                        .getBarcode()
                        .getXDimension()
                        .setPixels(4);
```

**この手順が重要な理由:**  
*X ディメンション* は各バーの幅を定義します。**4 ピクセル**に設定することで、ほとんどのスキャナーで読み取りやすく、標準ラベルにも収まるバーコードが得られます。この値を変更することが **カスタムバーコード寸法** を実現する主な方法です。

## 手順 3: ソリッドバーの代わりに空（アウトライン）バーを使用する

```java
        // Step 3 – configure the generator to draw empty bars (outline only)
        barcodeGenerator.getParameters()
                        .getBarcode()
                        .setFilledBars(false);
```

**この手順が重要な理由:**  
`setFilledBars(false)` はレンダラーにバーのアウトラインのみを描画し、内部を透明にするよう指示します。このスタイルは、背景に他の印刷情報が含まれる可能性がある郵便バーコードでしばしば必要とされます。

## 手順 4: バーコード画像を PNG 形式で保存する

```java
        // Step 4 – save the generated barcode as a PNG file
        String outputPath = "output/PlanetEmptyBars.png";
        barcodeGenerator.save(outputPath, BarCodeImageFormat.Png);

        System.out.println("Barcode image generated at: " + outputPath);
    }
}
```

**この手順が重要な理由:**  
`BarCodeImageFormat.Png` を選択すると、アウトラインバーの鮮明なエッジを保持したロスレス画像が得られます。ファイルパスは書き込み権限のある任意のディレクトリで構いません。例ではプロジェクトルートからの相対パスで `output` フォルダーを使用しています。

### 期待される出力

プログラムを実行すると、以下の画像に似たファイルが作成されます。

![Planetシンボロジーの生成されたバーコード画像](/images/planet-barcode.png){.align-center alt="空のアウトラインバーを持つPlanetバーコードを示す生成されたバーコード画像"}

画像は、薄く空白のバーを持つ **Planet バーコード** を表示し、設定したカスタム寸法と正確に一致しています。

## 一般的なバリエーションとエッジケース

| 状況 | 調整 |
|-----------|------------|
| **データ長が異なる場合** | Planet バーコードは最大 12 桁の数字をサポートします。コンストラクタの第2引数をそれに合わせて変更してください。 |
| **高解像度** | X ディメンション（`setPixels`）を増やすか、`YDimension` を設定してバーの高さを制御します。 |
| **カラー バーコード** | `barcodeGenerator.getParameters().getImageOptions().setForeColor(Color.BLUE);` を使用してバーの色を変更します。 |
| **SVG で保存** | ベクター出力のために `BarCodeImageFormat.Png` を `BarCodeImageFormat.Svg` に置き換えます。 |
| **Android で実行** | Android 対応の Aspose.BarCode for Android を使用し、ファイルシステムパスを `Context.getFilesDir()` に置き換えます。 |

> **注意点:** X ディメンションを低すぎる値（例: 1 ピクセル）に設定すると、低解像度プリンターでバーコードが読めなくなる可能性があります。寸法を変更した後は必ず実際のスキャナーでテストしてください。

## 簡単にコピー＆ペーストできる完全なソースコード

```java
package com.example.barcode;

import com.aspose.barcode.BarCodeImageFormat;
import com.aspose.barcode.EncodeTypes;
import com.aspose.barcode.generator.BarcodeGenerator;

public class PlanetBarcodeDemo {
    public static void main(String[] args) {
        // Create the generator for Planet barcode with sample data
        BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
                EncodeTypes.PLANET,
                "123456");

        // Custom X dimension – 4 pixels per module
        barcodeGenerator.getParameters()
                        .getBarcode()
                        .getXDimension()
                        .setPixels(4);

        // Use outline (empty) bars
        barcodeGenerator.getParameters()
                        .getBarcode()
                        .setFilledBars(false);

        // Save as PNG
        String outputPath = "output/PlanetEmptyBars.png";
        barcodeGenerator.save(outputPath, BarCodeImageFormat.Png);

        System.out.println("Barcode image generated at: " + outputPath);
    }
}
```

`PlanetBarcodeDemo.java` という名前のファイルにコードをコピーし、`src/main/java/com/example/barcode/` 配下に配置して、`mvn compile exec:java` を実行すると、`output` フォルダーに **バーコード画像の生成** 結果が表示されます。

## 結論

これで、Java で Planet シンボロジーの **バーコード画像を生成**する方法、**カスタムバーコード寸法**で **planet バーコードを作成**する方法、そしてソリッドバーから空バーへ切り替えてよりクリーンなビジュアルスタイルにする方法が分かりました。完全な例は、ジェネレーターの初期化から PNG ファイルの保存まで、必要なすべての API 呼び出しを示しています。

**次のステップ** – 他のバーコードタイプ（`EncodeTypes.CODE_128`、`EncodeTypes.QR`）を調査し、背景色、余白、DPI 設定などの追加画像オプションを試してみてください。バーコードを PDF に埋め込む必要がある場合は、Aspose.PDF for Java と組み合わせてシームレスなエンドツーエンドソリューションを構築できます。

コーディングを楽しんでください！

## 次に学ぶべきことは？

以下のチュートリアルは、本ガイドで示した手法を基にした密接に関連するトピックをカバーしています。各リソースには、ステップバイステップの解説付きの完全な動作コード例が含まれており、追加の API 機能を習得し、独自プロジェクトで代替実装アプローチを検討するのに役立ちます。

- [塗りつぶしバーと空バーで planet バーコードを作成する方法](/barcode/english/python-java/general/how-to-create-planet-barcode-with-filled-and-empty-bars/)
- [planet バーコード画像の作成 – ステップバイステップガイド](/barcode/english/python-java/general/create-planet-barcode-image-step-by-step-guide/)
- [Java でバーコードを生成する方法: 正確なバーコード画像の作成](/barcode/english/java/barcode-basics/creating-image-exact-barcode/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}