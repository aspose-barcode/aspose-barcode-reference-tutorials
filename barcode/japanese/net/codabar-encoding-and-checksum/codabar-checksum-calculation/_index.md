---
date: 2026-01-04
description: Aspose.BarCode for .NET を使用して Codabar バーコードを生成する際にチェックサムを追加する方法を学びましょう。Mod10
  と Mod16 のチェックサムモードをカバーしたステップバイステップガイドです。
linktitle: Codabar Checksum Calculation
second_title: Aspose.BarCode .NET API
title: Aspose.BarCode for .NET を使用して Codabar バーコードにチェックサムを追加する方法
url: /ja/net/codabar-encoding-and-checksum/codabar-checksum-calculation/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.BarCode for .NET を使用した Codabar バーコードへのチェックサムの追加方法

Codabar は、物流、図書館、医療などで特に広く採用されている線形バーコードシンボルです。Codabar バーコードにチェックサムを追加すると、転記エラーを問題になる前に検出でき、データの完全性が大幅に向上します。このチュートリアルでは、Aspose.BarCode for .NET で Codabar バーコードを生成する際に **チェックサムを追加する方法** を学び、Mod10 と Mod16 の両方のチェックサムモードを実際に確認できます。

## 簡単な回答
- **Codabar における「チェックサムを追加する」とは何ですか？** エンコードされたデータを検証するエラーディジットを有効にします。  
- **サポートされているチェックサムモードはどれですか？** Mod10（一般的）と Mod16（高精度シナリオ向け）。  
- **この機能を使用するのにライセンスは必要ですか？** はい、商用利用には有効な Aspose.BarCode for .NET ライセンスが必要です。  
- **対応している .NET バージョンはどれですか？** .NET Framework 4.5 以降、.NET Core 3.1 以降、.NET 5/6/7。  
- **生成された画像はどこに保存されますか？** `path` 変数で指定したフォルダーに保存されます。

## Codabar で「チェックサムを追加する」とは？
チェックサムを追加するとは、バーコードジェネレータに対して、提供したデータに基づいて余分な桁（または複数桁）を計算し、付加するよう設定することです。この情報はスキャナによって検証され、誤読の可能性が低減されます。

## なぜチェックサム付きの Codabar バーコードを生成するのか？
- **信頼性の向上:** 1 文字エラーや多くの転置エラーを検出します。  
- **コンプライアンス:** 血液バンクなど特定の業界ではチェックサム付きバーコードが必須です。  
- **柔軟性:** Aspose.BarCode ではプロパティを一つ変更するだけで Mod10 と Mod16 を切り替えられます。

## 前提条件

作業を始める前に、以下を用意してください。

1. **Aspose.BarCode for .NET** – 最新バージョンを [here](https://releases.aspose.com/barcode/net/) からダウンロード。  
2. **C# 開発環境** – Visual Studio、VS Code、または .NET 開発をサポートする任意の IDE。

準備が整ったら、実装手順に進みましょう。

## 名前空間のインポート

C# ファイルの先頭に必要な名前空間を追加し、バーコード生成クラスにアクセスできるようにします。

```csharp
using Aspose.BarCode.Generation;
```

## 手順 1: バーコードジェネレータの初期化

`BarcodeGenerator` インスタンスを作成し、Codabar シンボルを指定してエンコードしたいデータを設定します。画像を保存したいフォルダーは `"Your Directory Path"` を実際のパスに置き換えてください。

```csharp
string path = "Your Directory Path";
System.Console.WriteLine("CodabarChecksum:");

BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.Codabar, "-12345-");
```

## 手順 2: チェックサムなしで Codabar バーコードを生成

プレーンなバーコード（チェックサムなし）が必要な場合は、チェックサムオプションを `Default` に設定します。これはチェックサム桁を期待しないレガシーシステム向けです。

```csharp
gen.Parameters.Barcode.XDimension.Pixels = 2;
gen.Parameters.Barcode.IsChecksumEnabled = EnableChecksum.Default;
gen.Save($"{path}CodabarChecksumNone.png", BarCodeImageFormat.Png);
```

## 手順 3: **Mod10** チェックサム付き Codabar バーコードを生成

チェックサムを有効にし、アルゴリズムとして Mod10 を選択します。これは Codabar で最も一般的なチェックサムモードです。

```csharp
gen.Parameters.Barcode.IsChecksumEnabled = EnableChecksum.Yes;
gen.Parameters.Barcode.Codabar.CodabarChecksumMode = CodabarChecksumMode.Mod10;
gen.Save($"{path}CodabarChecksumMod10.png", BarCodeImageFormat.Png);
```

## 手順 4: **Mod16** チェックサム付き Codabar バーコードを生成

より高いエラー検出能力が求められる場合は、Mod16 に切り替えます。コードの変更は最小限で、`CodabarChecksumMode` を更新するだけです。

```csharp
gen.Parameters.Barcode.IsChecksumEnabled = EnableChecksum.Yes;
gen.Parameters.Barcode.Codabar.CodabarChecksumMode = CodabarChecksumMode.Mod16;
gen.Save($"{path}CodabarChecksumMod16.png", BarCodeImageFormat.Png);
```

これら 4 つのシンプルな手順で、Aspose.BarCode for .NET を使用して Codabar バーコードに **チェックサムを追加する方法** と、Mod10 と Mod16 の切り替え方を習得しました。

## よくある問題と解決策

| Issue | Reason | Fix |
|-------|--------|-----|
| 生成された画像が空白 | `path` が存在しないフォルダーを指している | ディレクトリーが存在することを確認するか、保存前に `Directory.CreateDirectory(path)` を使用 |
| チェックサムが適用されない | `IsChecksumEnabled` が `Default` のまま | 保存前に `IsChecksumEnabled = EnableChecksum.Yes` を設定 |
| 間違ったチェックサムモード | 列挙値を誤って使用 | 必要に応じて `CodabarChecksumMode.Mod10` または `CodabarChecksumMode.Mod16` を使用 |

## 結論

本ガイドでは、Aspose.BarCode for .NET を使用して Codabar バーコードを生成する際の **チェックサム追加方法** を解説し、Mod10 と Mod16 の両チェックサムモードを実演しました。チェックサム付きバーコードはデータ完全性に不可欠です。さまざまなデータ文字列で試したり、Aspose が提供する豊富なカスタマイズオプションを探索したりしてみてください。

問題が発生した場合は、[Aspose.BarCode フォーラム](https://forum.aspose.com/c/barcode/13) でコミュニティに相談できます。

## よくある質問

**Q: 図書館の書籍バーコードに Mod16 チェックサムを使用できますか？**  
A: もちろんです。Mod16 はエラー検出が強化されているため、図書館のような高スループット環境に適しています。

**Q: チェックサムを有効にするとスキャン速度に影響しますか？**  
A: 追加の桁による処理時間はごくわずかで、ほとんどのスキャナは遅延を感じません。

**Q: プログラムでチェックサムを検証するにはどうすればよいですか？**  
A: バーコード生成後、同じ `CodabarChecksumMode` を使用してチェックサムを再計算し、エンコード文字列の最終文字と比較します。

**Q: チェックサム桁の外観をカスタマイズできますか？**  
A: はい。`BarcodeGenerator` の外観設定（例: `BarHeight`、`ForeColor`）でチェックサム桁を含む全体のバーコードのスタイルを調整できます。

**Q: ループ内で複数のバーコードを生成したい場合は？**  
A: `BarcodeGenerator` を一度インスタンス化し、各イテレーションで `CodeText` プロパティを更新し、ユニークなファイル名で `Save` を呼び出します。

---

**最終更新日:** 2026-01-04  
**テスト環境:** Aspose.BarCode 24.11 for .NET  
**作者:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}