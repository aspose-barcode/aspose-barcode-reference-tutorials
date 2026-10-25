---
category: general
date: 2026-10-24
description: Python を使用して Planet バーコードを作成し、バーコードの高さを設定する方法を示すバーコードジェネレータの例です。ステップバイステップのガイドに従ってください。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- barcode generator example
- how to create planet barcode
- how to set barcode height
language: ja
lastmod: 2026-10-24
og_description: PythonでPlanetバーコードを作成し、バーコードの高さを設定する方法を示すバーコードジェネレータの例です。完全な実行可能なソリューションが手に入ります。
og_image_alt: Barcode generator example showing Planet and RM4SCC barcodes with different
  heights
og_title: バーコードジェネレーターの例 – Planet と RM4SCC バーコードを作成
schemas:
- author: Aspose
  dateModified: '2026-10-24'
  description: Barcode generator example that shows how to create Planet barcode and
    how to set barcode height using Python. Follow the step‑by‑step guide.
  headline: Barcode generator example – create Planet and RM4SCC barcodes with custom
    height
  type: TechArticle
- description: Barcode generator example that shows how to create Planet barcode and
    how to set barcode height using Python. Follow the step‑by‑step guide.
  name: Barcode generator example – create Planet and RM4SCC barcodes with custom
    height
  steps:
  - name: '**Instantiate** a `BarcodeGenerator` with the desired `EncodeTypes` value
      and the data string.'
    text: '**Instantiate** a `BarcodeGenerator` with the desired `EncodeTypes` value
      and the data string.'
  - name: '**Configure** the X‑dimension (module width) and, when needed, the barcode
      height.'
    text: '**Configure** the X‑dimension (module width) and, when needed, the barcode
      height.'
  - name: '**Save** the image to disk in PNG format.'
    text: '**Save** the image to disk in PNG format.'
  type: HowTo
tags:
- barcode
- Python
- image generation
title: バーコードジェネレーターの例 – カスタム高さでPlanetとRM4SCCバーコードを作成
url: /ja/python-java/general/barcode-generator-example-create-planet-and-rm4scc-barcodes/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# バーコードジェネレータ例 – カスタム高さでPlanetとRM4SCCバーコードを作成

**バーコードジェネレータ例** をお探しなら、このガイドは完全に実行可能なソリューションを提供します。**Planet バーコード** の画像作成方法、**バーコードの高さの設定方法**、自動サイズと手動サイズの微妙な違いを学びます。

チュートリアルでは、デフォルト（自動）高さを使用する Planet バーコードと、高さを 100 px に固定した RM4SCC バーコードという、2 つの実践的シナリオを順に解説します。最後まで読めば、単一の一貫した API で任意のサポート対象バーコードタイプの PNG ファイルを生成できるようになります。

## 前提条件

開始する前に、以下が揃っていることを確認してください。

* Python 3.8 以上がインストールされていること。
* `aspose-barcode` パッケージ（または `BarcodeGenerator`、`EncodeTypes`、`BarCodeImageFormat` を提供する任意のライブラリ）。以下でインストールできます  

  ```bash
  pip install aspose-barcode
  ```
* PNG ファイルを保存するフォルダーへの書き込み権限。

追加のシステム依存関係は不要です。

## ソリューションの概要

**バーコードジェネレータ例** のコアは、再利用可能な 3 つのステップで構成されています。

1. **Instantiate**: 目的の `EncodeTypes` 値とデータ文字列で `BarcodeGenerator` を生成する。
2. **Configure**: X‑ディメンション（モジュール幅）と、必要に応じてバーコードの高さを設定する。
3. **Save**: 画像を PNG 形式でディスクに保存する。

両例はステップ 1 と 3 を共有し、ステップ 2 だけが異なります。Planet バーコードはライブラリの自動高さ計算に任せ、RM4SCC バーコードは **バーコードの高さの設定方法** を手動で示します。

以下はフローを示すハイレベルな図です。

![バーコードジェネレータ例 – Planet と RM4SCC バーコードを異なる高さで表示](barcode-example.png)

*Alt text: バーコードジェネレータ例 – Planet と RM4SCC バーコードを異なる高さで表示*

## Planet バーコードの作成 – 自動高さ

Planet バーコードは多くの国の郵便サービスで使用されている郵便系統の一部です。ほとんどの場合、SDK に高さの決定を任せることで、データ長に応じた視覚的比率が保たれます。

```python
# Step 1: Create a generator for the Planet barcode with the data "123456"
from aspose.barcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat

planet_gen = BarcodeGenerator(EncodeTypes.Planet, "123456")

# Step 2: Define the X‑dimension (module width) as 4 pixels
planet_gen.parameters.barcode.x_dimension.pixels = 4

# Step 3: Save the barcode image as a PNG file
planet_gen.save("PostalPlanetBarHeightAuto.png", BarCodeImageFormat.Png)
```

**動作の理由**

* `EncodeTypes.Planet` はライブラリに Planet シンボロジーを使用させます。
* `x_dimension.pixels` を 4 に設定すると、各モジュールの幅が 4 px になり、印刷ラベルのデフォルトとして一般的です。
* 高さは明示的に設定せず、SDK がデータと X‑ディメンションに基づいて最適な高さを計算します。これが郵便コード向けの最もシンプルな **バーコードジェネレータ例** です。

**期待される結果**

`PostalPlanetBarHeightAuto.png` という名前の 2‑D PNG ファイルが生成され、鮮明な Planet バーコードが含まれます。高さは約 30 px（ライブラリのバージョンに依存）で、幅は 4 px × モジュール数となります。

## バーコードの高さを設定 – カスタム RM4SCC 例

RM4SCC は別の郵便バーコードで、ラベルテンプレートに合わせて固定高さが必要になることが多いです。このセクションでは **バーコードの高さの設定方法** を正確なピクセル数で示します。

```python
# Step 1: Create a generator for the RM4SCC barcode with the data "123456"
rm4scc_gen = BarcodeGenerator(EncodeTypes.RM4SCC, "123456")

# Step 2: Set the X‑dimension to 4 pixels (same as the Planet example)
rm4scc_gen.parameters.barcode.x_dimension.pixels = 4

# Step 3: Specify the barcode height as 100 pixels
rm4scc_gen.parameters.barcode.bar_height.pixels = 100

# Step 4: Save the barcode image as a PNG file
rm4scc_gen.save("PostalRM4SCCBarHeight100Pixels.png", BarCodeImageFormat.Png)
```

**動作の理由**

* `EncodeTypes.RM4SCC` が RM4SCC シンボロジーを選択します。
* X‑ディメンションは 4 px のままで、両バーコードでモジュールサイズを統一します。
* `bar_height.pixels = 100` により、バーコードの高さが正確に 100 px に強制され、自動計算が上書きされます。レイアウトで特定サイズが必要な場合に推奨される **バーコードの高さの設定方法** です。

**期待される結果**

`PostalRM4SCCBarHeight100Pixels.png` という名前の PNG ファイルが生成され、縦長の RM4SCC バーコードが表示されます。幅は X‑ディメンションに依存し続けますが、高さは 100 px に固定され、高解像度ラベルプリンターに適しています。

## 完全スクリプト – 両例を統合

両方の画像を同時に生成したい場合は、以下のコードを `generate_barcodes.py` にコピーして実行してください。

```python
"""
Full barcode generator example that creates:
* a Planet barcode with automatic height
* an RM4SCC barcode with a custom 100 px height
"""

from aspose.barcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat

def create_planet_barcode(data: str, x_dim: int, out_path: str):
    """Generate a Planet barcode using the default height."""
    gen = BarcodeGenerator(EncodeTypes.Planet, data)
    gen.parameters.barcode.x_dimension.pixels = x_dim
    gen.save(out_path, BarCodeImageFormat.Png)

def create_rm4scc_barcode(data: str, x_dim: int, height_px: int, out_path: str):
    """Generate an RM4SCC barcode with a fixed height."""
    gen = BarcodeGenerator(EncodeTypes.RM4SCC, data)
    gen.parameters.barcode.x_dimension.pixels = x_dim
    gen.parameters.barcode.bar_height.pixels = height_px
    gen.save(out_path, BarCodeImageFormat.Png)

if __name__ == "__main__":
    # Planet barcode – auto height
    create_planet_barcode(
        data="123456",
        x_dim=4,
        out_path="PostalPlanetBarHeightAuto.png"
    )

    # RM4SCC barcode – custom 100 px height
    create_rm4scc_barcode(
        data="123456",
        x_dim=4,
        height_px=100,
        out_path="PostalRM4SCCBarHeight100Pixels.png"
    )
```

**スクリプトの解説**

* 2 つのヘルパー関数でコードの DRY（Don’t Repeat Yourself）を実現し、他のシンボロジーへの拡張を容易にしています。
* `if __name__ == "__main__":` ガードにより、モジュールとしてインポートした際に生成ロジックが自動実行されず、ユニットテストに便利です。
* すべてのパラメータ（データ文字列、X‑ディメンション、高さ）が明示的に指定されているため、将来のプロジェクトの参照用 **バーコードジェネレータ例** として機能します。

## よくある質問とエッジケース

| 質問 | 回答 |
|----------|--------|
| *別の X‑ディメンションが必要な場合は？* | `x_dimension.pixels` を希望のモジュール幅に変更してください。値を大きくすると全体のバーコードサイズが比例して大きくなります。 |
| *他の画像形式も生成できますか？* | はい。`BarCodeImageFormat.Png` を `Jpg`、`Bmp`、`Gif` など、ライブラリの列挙型に合わせて置き換えてください。 |
| *データ文字列に無効な文字が含まれていたらどうなりますか？* | ジェネレータは `ArgumentException` をスローします。コンストラクタ呼び出し前にシンボロジーの文字セットに対してデータを検証してください。 |
| *自動スケーリングを保ちつつ最小高さを設定できますか？* | SDK が `min_pixels` プロパティを公開している場合は `gen.parameters.barcode.bar_height.min_pixels = <value>` を使用します。これにより読み取り可能な最小サイズ以下に縮小されません。 |
| *ジェネレータを破棄する必要がありますか？* | .NET では `BarcodeGenerator` クラスが `IDisposable` を実装していますが、Python ではガベージコレクタが処理します。多数のインスタンスをループで生成する場合は `gen.dispose()` を呼び出すことも可能です。 |

## 本番環境での利用時のポイント

* **プロのコツ:** X‑ディメンションと高さの値を設定ファイルに保存し、再コンパイルせずに調整できるようにする。
* **注意点:** 選択したシンボロジーに対して高さが小さすぎると、スキャナが読み取れなくなる可能性があります。
* **パフォーマンスのヒント:** 大量のバーコードを生成する場合、`BarcodeGenerator` インスタンスを再利用し、`code_text` プロパティだけを変更して保存する方が高速です。

## 結論

この **バーコードジェネレータ例** は、**Planet バーコードの自動サイズ生成** と **RM4SCC コードの手動高さ設定** の両方を実演しています。ステップバイステップのガイドに従うことで、任意の Python アプリケーションにバーコード作成機能を組み込み、寸法をカスタマイズし、印刷やデジタル表示に適した PNG ファイルを生成できます。

### 次のステップ

* `EncodeTypes.Postnet` や `EncodeTypes.Code128` など、他のシンボロジーを調査してください – 同じパターンが適用できます。
* QR コードや DataMatrix シンボル向けに **バーコードの高さの設定方法** を試してみてください。多くのライブラリで同様の `bar_height` プロパティが提供されています。
* バーコードジェネレータを PDF ライブラリと組み合わせ、請求書や出荷ラベルに直接埋め込む方法を検討してください。

スクリプトを自由にカスタマイズし、結果を共有し、次に追加したいバーコードタイプをぜひ教えてください！

### 次に学ぶべきこと

以下のチュートリアルは、本ガイドで示したテクニックを基にした、密接に関連するトピックを扱っています。各リソースには、ステップバイステップの解説付きの完全なコード例が含まれており、API の追加機能をマスターしたり、独自プロジェクトで代替実装アプローチを探求したりするのに役立ちます。

- [How to save PNG from a barcode generator example in Python](/barcode/english/python-java/general/how-to-save-png-from-a-barcode-generator-example-in-python/)
- [How to create planet barcode PNG with Python](/barcode/english/python-java/general/how-to-create-planet-barcode-png-with-python/)
- [How to use a C# barcode generator to create a Planet barcode](/barcode/english/python-java/general/how-to-use-a-c-barcode-generator-to-create-a-planet-barcode/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}