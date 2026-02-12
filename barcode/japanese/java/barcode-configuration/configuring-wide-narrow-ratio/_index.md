---
date: 2026-02-12
description: Aspose.BarCode を使用して Java でカスタムのワイド‑ナロー比率を持つ Code128 バーコードを作成し、バーコード
  PNG 画像を効率的に生成する方法を学びましょう。ステップバイステップのガイドに従ってください。
linktitle: Configuring Wide-Narrow Ratio
second_title: Aspose.BarCode Java API
title: Javaでワイド‑ナロウ比率のCODE_128バーコードを作成する方法
url: /ja/java/barcode-configuration/configuring-wide-narrow-ratio/
weight: 17
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# JavaでWide‑Narrow比率を使用してCODE_128バーコードを作成する方法

## Introduction

正確な視覚的比率で **code128バーコードを作成** したい場合、Wide‑Narrow比率の調整が鍵となります。このチュートリアルでは、Aspose.BarCode for Java を使用した **ステップバイステップのバーコード** 作成プロセスを解説し、比率の設定方法、**バーコードPNG画像の生成**、および **バーコード画像のディスクへの保存** 方法を示します。在庫ラベル、出荷タグ、またはカスタムスタイルのCODE_128バーコードが必要なあらゆるアプリケーションに、必要な情報がすべて揃っています。

## Quick Answers
- **Wide‑Narrow比率とは何か？** バーコードの太いバー（wide）と細いバー（narrow）の相対的な幅を制御します。  
- **どのシンボロジーが比率調整に対応しているか？** CODE_128 を含むほとんどの1次元シンボロジーでカスタム比率を設定できます。  
- **ライセンスは必要か？** 無料トライアルは利用可能ですが、商用利用には製品ライセンスが必要です。  
- **PNG形式でバーコード画像を生成できるか？** はい、`generator.save(...)` を使用して PNG 画像を生成できます。  
- **コードは Java 8 以降に対応しているか？** 完全に対応しています。Aspose.BarCode はすべての最新 Java バージョンで動作します。

## Prerequisites

コードに入る前に、以下が揃っていることを確認してください。

- Java Development Kit (JDK) がマシンにインストールされていること。  
- Aspose.BarCode for Java ライブラリ。[ダウンロードリンク](https://releases.aspose.com/barcode/java/) から取得してください。

## Import Packages

まず、プロジェクトに必須の Aspose.BarCode クラスをインポートします。

```java
// Import Aspose.BarCode library
import com.aspose.barcode.generation.BarcodeGenerator;
```

## What is the wide‑narrow ratio and why adjust it?

Wide‑Narrow比率は、バーコード内の「wide」バーが「narrow」バーに対してどれだけ太く表示されるかを決定します。この比率を調整することで、スキャナーの読み取り性を向上させたり、特定の印刷基準を満たしたり、ブランドのビジュアルスタイルに合わせたりできます。

## How to create code128 barcode with wide‑narrow ratio in Java

以下は、プロセス全体を段階的に案内する **ステップバイステップのバーコード** ガイドです。

### Step 1: Set Document Directory

```java
// The path to the resource directory.
String dataDir = "Your Document Directory";
```

ディレクトリが存在し、書き込み権限があることを確認してください。ここに **バーコード画像の保存** ファイルが配置されます。

### Step 2: Instantiate Barcode Object

```java
// Instantiate barcode object
// Create an instance of BarcodeGenerator, specify codetext and symbology in the constructor
BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.CODE_128, "12345678");
```

`EncodeTypes.CODE_128` をコンストラクタに渡すことで、**code128バーコードを作成** します。

### Step 3: Set Wide‑Narrow Ratio

```java
// Set the wide to narrow ratio for the barcode
generator.getParameters().getBarcode().setWideNarrowRatio(3.0f);
```

`setWideNarrowRatio` メソッドで視覚的な間隔を微調整できます。`3.0f` の値は、wideバーがnarrowバーの幅の3倍であることを意味します。

### Step 4: Save Image to Disk

```java
// Save the image to disk in PNG format
generator.save(dataDir + "wideNarrowRatio.png");
```

`save` を呼び出すと **バーコード画像が生成** され、PNG ファイルとして保存され、**バーコード画像の保存** 手順が完了します。

## Why adjust the wide‑narrow ratio?

- **スキャナー互換性:** 最適な読み取り率を得るために、2.0〜3.0 の比率を好むスキャナーがあります。  
- **印刷品質:** 比率を調整することで、プリンターの DPI 制限を補正し、バーの歪みを防げます。  
- **ブランド一貫性:** 企業によっては、バーコードを社色やデザインガイドラインに合わせたい場合があります。

## Common Issues and Solutions

| 問題 | 原因 | 対策 |
|------|------|------|
| バーコードが歪んで見える | プリンターに対して比率が高すぎる/低すぎる | `setWideNarrowRatio` に渡す値を調整してください（例: 2.0‑2.5）。 |
| ファイルが作成されない | 無効な `dataDir` パスまたは権限不足 | ディレクトリパスを確認し、アプリケーションに書き込み権限があることを確認してください。 |
| スキャナーがバーコードを読み取れない | シンボロジーの推奨範囲外の比率 | 標準の比率（2.0‑3.0）を使用するか、対象スキャナーでテストしてください。 |

## Frequently Asked Questions

**Q: Aspose.BarCodeを他のJavaフレームワークと併用できますか？**  
A: はい、Aspose.BarCodeはSpring、Java EE、Android、その他のJava環境とシームレスに連携できるよう設計されています。

**Q: 異なるシンボロジーのバーコードを生成するにはどうすればよいですか？**  
A: `BarcodeGenerator` のコンストラクタでシンボロジータイプを変更するだけです。例: QRコードの場合は `EncodeTypes.QR`。

**Q: Aspose.BarCodeのトライアル版はありますか？**  
A: はい、無料トライアル版は[こちら](https://releases.aspose.com/)から入手できます。

**Q: Aspose.BarCodeの詳細なドキュメントはどこで見つけられますか？**  
A: ドキュメントは[こちら](https://reference.aspose.com/barcode/java/)をご参照ください。

**Q: Aspose.BarCodeのサポートはどのように受けられますか？**  
A: サポートやコミュニティの議論は、Aspose.BarCodeフォーラム[こちら](https://forum.aspose.com/c/barcode/13)をご利用ください。

---

**最終更新日:** 2026-02-12  
**テスト環境:** Aspose.BarCode for Java 24.11 (執筆時点での最新バージョン)  
**作者:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}