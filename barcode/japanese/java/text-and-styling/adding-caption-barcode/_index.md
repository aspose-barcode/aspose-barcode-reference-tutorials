---
date: 2025-12-27
description: Aspose.BarCode を使用して Java でバーコード画像にキャプションを追加する方法を学びましょう。この Java バーコードジェネレータの例では、簡単にバーコード画像を作成する方法を示しています。
linktitle: Adding Caption to Barcode
second_title: Aspose.BarCode Java API
title: Aspose.BarCode を使用した Java でバーコードにキャプションを追加する方法
url: /ja/java/text-and-styling/adding-caption-barcode/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.BarCode for Java を使用してバーコードにキャプションを追加する方法

## Introduction

バーコードの可読性やブランディングを向上させるために **キャプションの追加方法** が必要な場合は、ここが最適です。このチュートリアルでは、Aspose.BarCode for Java を使用してバーコード画像の上部と下部にキャプションを追加する手順を詳しく解説します。最終的に、データをエンコードするだけでなく、役立つテキストも表示できる完全にスタイルされたバーコードが作成できます。製品ラベル、在庫管理システム、その他ユーザーが追加情報から恩恵を受けるシナリオに最適です。

## Quick Answers
- **必要なライブラリは？** Aspose.BarCode for Java。  
- **フォントや色は変更できる？** はい、キャプションのフォントファミリーとテキストカラーはカスタマイズ可能です。  
- **対応するバーコードタイプは？** Aspose.BarCode がサポートするすべてのシンボロジー（例: CODE_128、QR、DataMatrix）。  
- **テスト用にライセンスは必要？** 無料トライアルが利用可能です。商用利用には製品ライセンスが必要です。  
- **実装にかかる時間は？** ライブラリを追加した後、通常は 10 分未満で完了します。

## What is a caption in a barcode?
キャプションとは、バーコードグラフィックの上部または下部に表示されるプレーンテキストです。製品名、価格、その他エンコードされたデータを補完する情報を伝えることができます。

## Why add captions with Aspose.BarCode?
- **ユーザー体験の向上:** スキャンせずにバーコードの意味を即座に読めます。  
- **ブランドの一貫性:** フォント、カラー、配置を自由に設定し、企業のスタイルガイドに合わせられます。  
- **フルコントロール:** Aspose.BarCode の API で可視性、配置、スタイルを個別に切り替え可能です。

## Prerequisites

開始する前に以下を確認してください。

- Java Development Kit (JDK) がインストールされていること。  
- Aspose.BarCode for Java ライブラリをダウンロードし、プロジェクトに追加済みであること。ダウンロードリンクは [here](https://releases.aspose.com/barcode/java/)。  
- IntelliJ IDEA または Eclipse などの IDE が用意されていること。

## Import Packages

Java ソースファイルで必要な Aspose.BarCode クラスと AWT の `Color` クラスをインポートします。

```java
import com.aspose.barcode.*;
import java.awt.*;
```

## Step 1: Set Up Document and Resource Directories

生成したバーコード画像を保存する場所を指定します。環境に合わせてパスを調整してください。

```java
String path = "Your Directory Path";
String dataDir = "Your Document Directory";
```

## Step 2: Create Barcode Generator Instance

目的のシンボロジー（例: CODE_128）とエンコードしたいコードテキストで `BarcodeGenerator` をインスタンス化します。

```java
BarcodeGenerator bb = new BarcodeGenerator(EncodeTypes.CODE_128, "12345678");
```

## Step 3: Configure Caption Above the Barcode

バーコードの上部に表示するキャプションを設定します。配置、テキスト、可視性、フォントファミリー、サイズ、カラーを制御できます。

```java
bb.getParameters().getCaptionAbove().setAlignment(TextAlignment.LEFT);
bb.getParameters().getCaptionAbove().setText("Aspose.Demo");
bb.getParameters().getCaptionAbove().setVisible(true);
bb.getParameters().getCaptionAbove().getFont().setFamilyName("Pristina");
bb.getParameters().getCaptionAbove().getFont().getSize().setPoint(14);
bb.getParameters().getCaptionAbove().setTextColor(Color.RED);
```

## Step 4: Configure Caption Below the Barcode

同様に、バーコードの下部に表示するキャプションを定義します。必要に応じて異なる配置やスタイルを使用できます。

```java
bb.getParameters().getCaptionBelow().setAlignment(TextAlignment.RIGHT);
bb.getParameters().getCaptionBelow().setText("Aspose.Demo");
bb.getParameters().getCaptionBelow().setVisible(true);
bb.getParameters().getCaptionBelow().getFont().setFamilyName("Pristina");
bb.getParameters().getCaptionBelow().getFont().getSize().setPoint(14);
bb.getParameters().getCaptionBelow().setTextColor(Color.RED);
```

## Step 5: Save the Barcode Image

最後に、キャプション付きバーコードを画像ファイルに書き出します。フォーマットはファイル拡張子から自動的に判別されます。

```java
bb.save(dataDir + "barcodeCaption.jpg");
```

上記手順を繰り返すことで、フォントやカラー、配置を変えて実験したり、ループで複数のバーコード画像を生成したりできます。

## Common Issues & Tips

- **キャプションが表示されない場合:** 表示したいキャプションに対して `setVisible(true)` が呼び出されていることを確認してください。  
- **色が正しくない場合:** `java.awt.Color` の定数を使用するか、`new Color(r, g, b)` でカスタムカラーを作成してください。  
- **パスの問題:** `dataDir` が書き込み可能な既存フォルダーを指しているか確認してください。そうでないと `bb.save()` が `IOException` をスローします。  
- **パフォーマンスのヒント:** 多数のバーコードを生成する場合は、`BarcodeGenerator` インスタンスを再利用し、`EncodeTypes` や `codetext` だけを変更すると効率的です。

## Frequently Asked Questions (FAQs)

### Can I customize the font style of the barcode captions?
はい、上部と下部のキャプションそれぞれのフォントファミリー、サイズ、カラーをカスタマイズできます。

### Is Aspose.BarCode compatible with different barcode symbologies?
もちろんです！Aspose.BarCode は幅広いシンボロジーをサポートしており、柔軟にバーコードを生成できます。

### How can I integrate Aspose.BarCode into my Java project?
統合手順の詳細は [here](https://reference.aspose.com/barcode/java/) にあるステップバイステップガイドをご参照ください。

### Is there a free trial available for Aspose.BarCode for Java?
はい、すべての機能を試せる無料トライアルが [here](https://releases.aspose.com/) から入手可能です。

### Where can I get help if I run into issues?
Aspose.BarCode コミュニティフォーラムはサポートやディスカッションに最適です。フォーラムは [here](https://forum.aspose.com/c/barcode/13) からアクセスできます。

---

**Last Updated:** 2025-12-27  
**Tested With:** Aspose.BarCode for Java 24.11  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}