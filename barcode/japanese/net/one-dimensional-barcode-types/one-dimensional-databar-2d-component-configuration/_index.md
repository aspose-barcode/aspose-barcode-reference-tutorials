---
date: 2026-02-28
description: .NETで1次元Databarおよび2次元バーコード用のAsposeバーコードジェネレーターの作成方法を学びましょう。設定とカスタマイズのステップバイステップガイドに従ってください。
linktitle: One-Dimensional Databar 2D Component Configuration
second_title: Aspose.BarCode .NET API
title: バーコードジェネレーター Aspose – Databar 2D 設定を作成
url: /ja/net/one-dimensional-barcode-types/one-dimensional-databar-2d-component-configuration/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 一次元データバー 2D コンポーネント構成

## クイック回答
- **2D コンポーネント フラグは何をしますか？** 生成時にデータバー バーコード内に複合 2D シンボルを埋め込むかどうかを指定します。  
- **X‑ディメンションは変更できますか？** はい、`XDimension.Pixels` プロパティでモジュール幅を制御できます。  
- **例で使用されている画像形式は何ですか？** PNG、`BarCodeImageFormat.Png` を使用しています。  
- **開発にライセンスは必要ですか？** テスト用の無料トライアルで動作しますが、本番環境では商用ライセンスが必要です。  
- **.NET Core と互換性がありますか？** 完全に対応しています—Aspose.BarCode は .NET Framework と .NET Core の両方をサポートします。

## 一次元データバー 2D コンポーネントとは？
データバー 2D コンポーネントは、従来の線形バーコードに小さな 2D 複合シンボルを組み合わせたもので、全体のサイズを増やさずに URL や追加データフィールドなどの余分な情報を格納できます。

## なぜ Aspose.BarCode を使うのか？
- **フル .NET 統合** – C# プロジェクトとシームレスに連携します。  
- **豊富な構成 API** – サイズ調整、2D コンポーネントの有効化/無効化、さまざまな出力形式を選択可能です。  
- **外部依存なし** – ライブラリは単体で完結しているため、デプロイが簡単です。

## 前提条件

1. **インストール** – Aspose.BarCode for .NET がインストールされていることを確認してください。ダウンロードは[こちら](https://releases.aspose.com/barcode/net/)から。  
2. **基本知識** – C# と .NET 開発に慣れていると手順がスムーズです。  
3. **開発環境** – Visual Studio、Rider、または任意の C# 対応エディタ。

これらの前提が整ったら、データバー 2D コンポーネントの構成を始めましょう。

## 名前空間のインポート

最初に Aspose.BarCode 名前空間をインポートして、クラスにアクセスできるようにします。

```csharp
using Aspose.BarCode;
```

## 出力パスの定義

生成したバーコード画像を保存するファイルシステム上の場所を指定します。

```csharp
string path = "Your Directory Path";
```

`"Your Directory Path"` を実際のフォルダー パスに置き換えてください。

## バーコードジェネレータの作成

`BarcodeGenerator` をデータバー Expanded タイプでインスタンス化し、エンコードしたいデータを渡します。

```csharp
BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.DatabarExpanded, "(01)12345678901231");
```

サンプル データはご自身の GS1 アプリケーション識別子や他のペイロードに置き換えて構いません。

## One‑Dimensional Databar 2D 用の Aspose バーコードジェネレータ作成手順

次に視覚プロパティと 2D コンポーネント フラグを設定し、画像を保存します。

```csharp
gen.Parameters.Barcode.XDimension.Pixels = 2;

// Disable 2D component flag
gen.Parameters.Barcode.DataBar.Is2DCompositeComponent = false;
gen.Save($"{path}Databar2DComponentDisabled.png", BarCodeImageFormat.Png);

// Enable 2D component flag
gen.Parameters.Barcode.DataBar.Is2DCompositeComponent = true;
gen.Save($"{path}Databar2DComponentEnabled.png", BarCodeImageFormat.Png);
```

- **XDimension** は各バーコードモジュールの幅を制御します。  
- `Is2DCompositeComponent` を **false** に設定すると純粋な線形データバーが生成されます。  
- **true** に設定すると複合 2D シンボルが追加され、余分なデータをエンコードできます。

## よくある問題とヒント

- **パスが無効** – フォルダーが存在し、アプリケーションに書き込み権限があることを確認してください。  
- **ライセンス例外** – ライセンス警告が出た場合は、バーコード生成前に Aspose ライセンスを適用してください。  
- **画像が表示されない** – `BarCodeImageFormat` が使用しているファイル拡張子と一致しているか確認しましょう。

## 結論

これで **一次元データバー 2D コンポーネント用の Aspose バーコードジェネレータ** の作成方法、2D 複合フラグの切り替え、X‑ディメンションの調整が理解できました。この柔軟なアプローチにより、さまざまなビジネスシナリオに合わせてバーコードをカスタマイズできます。さらに高度なカスタマイズは、公式ドキュメントをご覧ください: [Aspose.BarCode for .NET Documentation](https://reference.aspose.com/barcode/net/)。

追加のサンプルが必要な場合や問題が発生した場合は、Aspose コミュニティで質問すると良いでしょう。

## FAQs

### Aspose.BarCode for .NET はさまざまなバーコードタイプに対応していますか？
- はい、Aspose.BarCode for .NET は幅広いバーコードタイプをサポートしており、さまざまな用途に高い汎用性を提供します。

### 生成されたバーコードの外観をカスタマイズできますか？
- もちろんです！サイズ、色、その他多数の視覚プロパティを調整して、要件に合わせたバーコードを作成できます。

### Aspose.BarCode for .NET のライセンス形態はありますか？
- はい、さまざまなニーズに合わせたライセンスオプションが用意されています。詳細は公式サイトでご確認ください。

### Aspose.BarCode は初心者と経験豊富な開発者の両方に適していますか？
- Aspose.BarCode はユーザーフレンドリーに設計されており、初心者から経験豊富な開発者まで幅広く活用できます。

### Aspose.BarCode for .NET のサポートや支援はどこで受けられますか？
- [Aspose.BarCode for .NET support forum](https://forum.aspose.com/c/barcode/13) でコミュニティに参加し、質問や情報交換が可能です。

## Frequently Asked Questions

**Q: PNG 以外の形式でバーコードを生成できますか？**  
A: はい、`Save` メソッドで適切な `BarCodeImageFormat` を指定すれば、BMP、JPEG、GIF、TIFF など多数の形式に対応しています。

**Q: バーコードにカスタムカラーを適用するには？**  
A: `gen.Parameters.Barcode.ForeColor` と `gen.Parameters.Barcode.BackColor` を使用して前景色と背景色を設定できます。

**Q: バーコード画像にロゴを埋め込むことは可能ですか？**  
A: Aspose.BarCode の `Image` プロパティを利用すれば、バーコード生成後にロゴをオーバーレイできます。

**Q: 対応している .NET バージョンは？**  
A: .NET Framework 4.5 以降、.NET Core 3.1 以降、.NET 5 以降、.NET 6 以降で動作します。

**Q: 低解像度印刷時のスキャン信頼性を向上させるには？**  
A: `XDimension` の値を上げ、バーコードと背景のコントラストを十分に確保してください。

---

**最終更新日:** 2026-02-28  
**テスト環境:** Aspose.BarCode 24.12 for .NET  
**作成者:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}