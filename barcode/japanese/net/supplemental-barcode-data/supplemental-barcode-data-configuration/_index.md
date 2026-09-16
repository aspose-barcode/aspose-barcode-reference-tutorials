---
date: 2026-03-07
description: Aspose.BarCode for .NET を使用して C# で補足データ付きの EAN-13 バーコードの作成方法を学び、バーコード
  PNG を素早く生成します。
linktitle: Supplemental Barcode Data Configuration
second_title: Aspose.BarCode .NET API
title: 補足データ付きEAN-13バーコードの作成 – Aspose.BarCode
url: /ja/net/supplemental-barcode-data/supplemental-barcode-data-configuration/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 補足データ付きEAN-13バーコードの作成 – Aspose.BarCode for .NET

このハンズオンチュートリアルでは、**EAN-13バーコード**を作成し、補足のEAN‑2またはEAN‑5データを含め、数行のC#コードで**バーコードPNG**ファイルを生成する方法を示します。小売レジシステム、物流アプリケーション、またはシンプルな在庫管理ツールを構築する場合でも、補足情報を追加できることでバーコードの有用性が大幅に向上します。

## クイック回答
- **“補足データ”とは何ですか？** メインバーコードの横に印刷される余分な数字（EAN‑2/EAN‑5）で、価格や号数などに使用されます。  
- **使用されるバーコードタイプは？** 主シンボルとしてEAN‑13を使用し、オプションでEAN‑2またはEAN‑5の補足を付加できます。  
- **PNG画像を出力できますか？** はい – `Save` メソッドで直接PNGにエクスポートできます。  
- **開発にライセンスは必要ですか？** テスト用には無料トライアルで動作しますが、本番環境では商用ライセンスが必要です。  
- **.NET Core / .NET 6 と互換性がありますか？** 完全に対応しています – Aspose.BarCode はすべての最新 .NET ランタイムをサポートしています。

## 前提条件

コードに入る前に、以下が揃っていることを確認してください：

- Visual Studio（または任意の .NET 対応 IDE）。  
- Aspose.BarCode for .NET のコピー – **[こちら](https://releases.aspose.com/barcode/net/)** からダウンロードしてください。  
- 基本的な C# の知識。  
- 生成された PNG ファイルを保存できる書き込み可能なフォルダー。

## 名前空間のインポート

まず、Aspose.BarCode 名前空間を追加して、ジェネレータクラスにアクセスできるようにします：

```csharp
using Aspose.BarCode.Generation;
```

> **プロのコツ:** .NET Core を使用している場合は、DLL を手動で参照する代わりに NuGet パッケージ `Aspose.BarCode` をプロジェクトに追加してください。

## 補足バーコードとは何ですか？

補足バーコードは、メインバーコードの横に印刷される補助的な数字列です。

- **EAN‑2** – 2 桁の補足で、主に雑誌の号数に使用されます。  
- **EAN‑5** – 5 桁の補足で、小売品の価格拡張に一般的に使用されます。

これらの補足を追加しても、主たる EAN‑13 データは変更されません。スキャナーが読み取れる追加情報を提供するだけです。

## 補足データに Aspose.BarCode を使用する理由は？

- **ワンライン API** – メインバーコードとその補足を単一オブジェクトで設定できます。  
- **寸法の完全制御** – X ディメンション、補足の間隔、画像フォーマットを調整できます。  
- **クロスプラットフォーム** – .NET Framework、.NET Core、.NET 5/6+ で動作します。

## ステップバイステップガイド

### ステップ 1: 出力ディレクトリの設定

PNG ファイルの保存先を定義します。プレースホルダーを実際のパスに置き換えてください。

```csharp
string path = "Your Directory Path";
```

### ステップ 2: バーコードジェネレータの初期化 (Barcode Generator C#)

`BarcodeGenerator` インスタンスを作成し、メインタイプとして **EAN‑13** を指定し、13 桁のペイロードを提供します。

```csharp
BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.EAN13, "1234567890128");
```

### ステップ 3: バーコードの寸法調整

バーコードの視覚的サイズと補足用に確保されたスペースを微調整します。

```csharp
gen.Parameters.Barcode.XDimension.Pixels = 2;
gen.Parameters.Barcode.Supplement.SupplementSpace.Pixels = 20;
```

### ステップ 4: EAN‑2 補足の追加

補足データを 2 桁の値（例: “12”）に設定します。これがメインバーコードの右側に表示されます。

```csharp
gen.Parameters.Barcode.Supplement.SupplementData = "12";
```

### ステップ 5: EAN‑2 バーコードを PNG として保存

画像をエクスポートします。`BarCodeImageFormat.Png` 引数により高品質な PNG ファイルが保証されます。

```csharp
gen.Save($"{path}SupplementEAN2.png", BarCodeImageFormat.Png);
```

### ステップ 6: EAN‑5 補足に切り替える

価格拡張用に `SupplementData` を 5 桁の文字列に変更します。

```csharp
gen.Parameters.Barcode.Supplement.SupplementData = "12345";
```

### ステップ 7: EAN‑5 バーコードを PNG として保存

```csharp
gen.Save($"{path}SupplementEAN5.png", BarCodeImageFormat.Png);
```

> **この動作の理由:** 同じ `BarcodeGenerator` インスタンスを再利用するため、各 `Save` 呼び出しの前に `SupplementData` プロパティを変更するだけで済みます。これによりコードが簡潔になり、不要なオブジェクト生成を回避できます。

## よくある問題とヒント

- **無効なディレクトリパス** – フォルダーが存在し、アプリケーションに書き込み権限があることを確認してください。  
- **補足の長さが不正** – EAN‑2 は正確に 2 桁、EAN‑5 は 5 桁が必要です。条件を満たさない場合は例外がスローされます。  
- **画像が表示されない** – `BarCodeImageFormat.Png` が使用されていることを確認してください。JPEG など他の形式は圧縮アーティファクトが発生し、スキャナーの読み取り性に影響する可能性があります。  

## よくある質問

### .NET Core プロジェクトで Aspose.BarCode for .NET を使用できますか？

はい、Aspose.BarCode for .NET は .NET Core、.NET 5、.NET 6 と完全に互換性があります。

### Aspose.BarCode for .NET の無料トライアルは利用できますか？

はい、**[このリンク](https://releases.aspose.com/)** から無料でお試しいただけます。

### Aspose.BarCode for .NET の一時ライセンスはどこで取得できますか？

**[このリンク](https://purchase.aspose.com/temporary-license/)** から一時ライセンスを取得できます。

### Aspose.BarCode は幅広いバーコードタイプをサポートしていますか？

もちろんです – EAN‑13、QR Code、Code 128、DataMatrix、PDF‑417 など多数のバーコードタイプをサポートしています。

### 生成されたバーコードの外観をカスタマイズできますか？

はい、`Parameters` API を使用して色、フォント、余白、さらには背景画像まで変更できます。

## 結論

これで、補足の EAN‑2 または EAN‑5 データを含む **EAN-13 バーコード**の作成方法と、Aspose.BarCode for .NET を使用した **バーコード PNG** ファイルの生成方法が分かりました。この手法により、バーコードの寸法、補足の間隔、出力フォーマットを完全に制御でき、小売、物流、その他数値情報の追加が必要なシナリオに最適です。

さらに詳しく学びたい方は、完全なリファレンスガイドをご覧ください: **[Aspose.BarCode for .NET documentation](https://reference.aspose.com/barcode/net/)**。

---

**最終更新日：** 2026-03-07  
**テスト環境：** Aspose.BarCode 24.11 for .NET  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}