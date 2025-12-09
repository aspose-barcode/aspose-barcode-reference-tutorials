---
date: 2025-12-08
description: Aspose.BarCode を使用して、Java で Code128 バーコードを作成し、バーコード画像を生成する方法を学びましょう。シンプルで再利用可能なコードで、バーコード画像のサイズ単位を正確に設定できます。
linktitle: Setting Size Unit for Barcode Image
second_title: Aspose.BarCode Java API
title: Aspose.BarCode を使用した Java の Code128 バーコード作成
url: /ja/java/advanced-settings-and-optimization/setting-size-unit-barcode-image/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.BarCode を使用した code128 バーコードの作成とサイズ単位の設定（Java）

## Introduction

このステップ‑バイ‑ステップガイドでは、**create code128 barcode java** コードを作成し、バーコード画像を生成するとともに、出力のサイズ単位を制御できます。 在庫システム、出荷ラベルジェネレータ、または信頼性の高いバーコードが必要な任意の Java アプリケーションを構築する場合、Aspose.BarCode for Java がプロセスをシンプルかつ高度にカスタマイズ可能にします。

## Quick Answers
- **What library do I need?** Aspose.BarCode for Java. → 必要なライブラリは何ですか？ Aspose.BarCode for Java。
- **Which barcode type is covered?** CODE_128 (create code128 barcode java). → 対応しているバーコードタイプは何ですか？ CODE_128（**create code128 barcode java**）。
- **How do I set the size unit?** Use the `BarHeight` property with `.setPoint()`. → サイズ単位はどう設定しますか？ `BarHeight` プロパティに `.setPoint()` を使用します。
- **Can I generate barcode image java in other formats?** Yes – PNG, JPEG, BMP, etc. → 他の形式で barcode image java を生成できますか？ はい – PNG、JPEG、BMP など。
- **What are the prerequisites?** JDK installed, Aspose.BarCode library, and a Java IDE. → 前提条件は何ですか？ JDK のインストール、Aspose.BarCode ライブラリ、Java IDE。

## What is **create code128 barcode java**?

Java で CODE_128 バーコードを作成することは、`BarcodeGenerator` クラスを `EncodeTypes.CODE_128` 列挙体とともにインスタンス化し、エンコードしたいデータ文字列を渡すことを意味します。このシンボロジーは、フル ASCII 文字セットをサポートし、データ密度が高いため物流分野で広く使用されています。

## Why use Aspose.BarCode to **generate barcode image java**?

- **Full control over dimensions** – バーの高さ、モジュールサイズ、画像解像度を設定できます。  
- **No external dependencies** – 純粋な Java で、JDK をサポートする任意のプラットフォームで動作します。  
- **Rich customization** – 色、フォント、余白、さらには QR コードまでサポートしています。  
- **High performance** – ミリ秒単位で画像を生成でき、バッチ処理に適しています。

## Prerequisites

開始する前に、以下を用意してください：

1. **Java Development Kit (JDK)** – バージョン 8 以降がインストールされていること。  
2. **Aspose.BarCode for Java library** – Aspose のウェブサイトから最新の JAR をダウンロード（トライアルまたはライセンス版）。  
3. **A Java IDE** – IntelliJ IDEA、Eclipse、または Java 拡張機能付き VS Code など。

## Import Namespaces

Java クラスの先頭に必要なインポートを追加し、Aspose.BarCode の API にアクセスできるようにします:

```java
import java.io.IOException;

import com.aspose.barcode.*;

import com.aspose.barcode.generation.BarcodeGenerator;
```

## How to **generate barcode image java** with Aspose.BarCode?

以下に完全なワークフローを示します。各ステップは平易な言葉で説明しており、元のコードブロックそのまま保持しています。

### Step 1: Define the Resource Directory

```java
// The path to the resource directory.
String dataDir = "Your Document Directory";
```

`"Your Document Directory"` を、バーコード画像を保存したい絶対パスに置き換えてください。

### Step 2: Instantiate the Barcode Object

```java
// Instantiate barcode object, Set the symbology type to code128 and Set the
// Code text for the barcode
BarcodeGenerator bb = new BarcodeGenerator(EncodeTypes.CODE_128, "1234567");
```

ここで `EncodeTypes.CODE_128` とデータ文字列 `"1234567"` を渡すことで、**create code128 barcode java** を実行します。

### Step 3: Set Bar Height (Size Unit)

```java
// Set the bar height to 3 points
bb.getParameters().getBarcode().getBarHeight().setPoint(3.0f);
```

`setPoint()` メソッドはポイント単位で高さを定義します（1 ポイント = 1/72 インチ）。レイアウト要件に合わせてこの値を調整してください。

### Step 4: Save the Image

```java
// Save the image
bb.save(dataDir + "barcode-size-unit.jpg");
```

`save()` 呼び出しにより、指定したフォルダーに生成されたバーコードが書き込まれます。画像形式はファイル拡張子から自動的に判別されます（この例では JPEG）。

## Common Issues and Solutions

| Issue | Reason | Fix |
|-------|--------|-----|
| **Image not created** | `dataDir` パスが間違っている、または書き込み権限がありません。 | フォルダーが存在し、アプリケーションに書き込み権限があることを確認してください。 |
| **Barcode appears too small** | ポイント単位のバー高さが DPI に対して低すぎます。 | `setPoint()` に渡す値を増やすか、`bb.getParameters().getImage().setResolution()` で画像 DPI を調整してください。 |
| **Unsupported characters** | CODE_128 は ASCII のみをサポートし、Unicode が渡されています。 | 非 ASCII データには別のシンボロジー（例：QR_CODE）を使用してください。 |

## Frequently Asked Questions

**Q: Is Aspose.BarCode for Java suitable for both barcode generation and recognition?**  
A: Yes, the library supports both generation and recognition of a wide range of symbologies.  
**Q: Can I customize the appearance of the generated barcode images?**  
A: Absolutely. You can change colors, add captions, modify margins, and even embed logos using the extensive `Parameters` API.  
**Q: How can I obtain a temporary license for Aspose.BarCode for Java?**  
A: Visit [here](https://purchase.aspose.com/temporary-license/) to request a temporary license for evaluation.  
**Q: Where can I find support for Aspose.BarCode for Java?**  
A: The Aspose.BarCode community forum is the best place for help. Check the [forum](https://forum.aspose.com/c/barcode/13) for answers and to ask new questions.  
**Q: What are the supported barcode symbologies in Aspose.BarCode for Java?**  
A: The library supports dozens of symbologies, including CODE_128, QR_CODE, UPC_A, DataMatrix, PDF417, and many more.

---

**Last Updated:** 2025-12-08  
**Tested With:** Aspose.BarCode for Java 24.12 (latest at time of writing)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}