---
category: general
date: 2026-10-28
description: ExtCodetextBuilder を使用して Python で拡張コードテキストを作成する方法を学びましょう。プレーンデータと ECI
  エンコードデータを含み、ステップバイステップのコードとベストプラクティスのヒントが提供されます。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create extended codetext
- ExtCodetextBuilder Python
- add plain codetext
- add eci codetext
- extended‑codetext example
language: ja
lastmod: 2026-10-28
og_description: ExtCodetextBuilder を使用して Python で拡張コードテキストを作成します。このチュートリアルでは、プレーンデータと
  ECI エンコードデータの取り扱い、完全に実行可能なコード、そして一般的な落とし穴を示します。
og_image_alt: Diagram showing how to create extended codetext using ExtCodetextBuilder
  in Python
og_title: Pythonで拡張コードテキストを作成する – 完全ガイド
schemas:
- author: Aspose
  dateModified: '2026-10-28'
  description: Learn how to create extended codetext in Python using ExtCodetextBuilder.
    Includes plain and ECI‑encoded data, step‑by‑step code and best‑practice tips.
  headline: How to create extended codetext in Python with ExtCodetextBuilder
  type: TechArticle
- description: Learn how to create extended codetext in Python using ExtCodetextBuilder.
    Includes plain and ECI‑encoded data, step‑by‑step code and best‑practice tips.
  name: How to create extended codetext in Python with ExtCodetextBuilder
  steps:
  - name: Prerequisites
    text: '* Python 3.8 or newer. * The `extcodetext` package (or a similar library
      that provides `ExtCodetextBuilder`). Install it with:'
  - name: Handling other encodings
    text: 'If you need ISO‑8859‑1 (Western European) you would use `add_eci_codetext(4,
      "¡Hola!")`. For Shift‑JIS (Japanese) the ECI value is 20:'
  - name: 'Edge case: Empty strings'
    text: Calling `add_plain_codetext("")` or `add_eci_codetext(3, "")` is harmless;
      the builder simply ignores the empty fragment. However, repeated empty calls
      can lead to unnecessary ECI markers. Guard against this by checking string length
      before adding.
  type: HowTo
tags:
- Python
- encoding
- data‑serialization
title: ExtCodetextBuilder を使用して Python で拡張コードテキストを作成する方法
url: /ja/python/general/how-to-create-extended-codetext-in-python-with-extcodetextbu/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# PythonでExtCodetextBuilderを使用して拡張コードテキストを作成する方法

バーコードやデータマトリックスの用途で **拡張コードテキストを作成** する必要がある場合、このガイドでは Python での具体的な手順を示します。プレーンテキストを組み合わせ、Unicode 文字用に ECI（Extended Channel Interpretation）セクションを追加し、エンコード用に正しくフォーマットされた単一の文字列を取得する方法が分かります。

本チュートリアルは、必要なライブラリのインストールから、サポートされていない ECI 値などのエッジケースの処理まで網羅しています。最後まで読むと、 **拡張コードテキストを作成** するために任意のプロジェクトに組み込める再利用可能なパターンが手に入ります。

## 学習内容

* `ExtCodetextBuilder` が混合エンコーディング文字列を構築する際の役割。  
* 単一のビルダーインスタンスで **プレーンコードテキストを追加** し、 **ECI コードテキストを追加** する方法。  
* 最終出力を検証し、一般的な落とし穴をトラブルシュートする方法。  
* 他の文字セット（例：ISO‑8859‑1、Shift‑JIS）向けのバリエーション。  

### 前提条件

* Python 3.8 以上。  
* `extcodetext` パッケージ（または `ExtCodetextBuilder` を提供する類似ライブラリ）。以下でインストールします：

```bash
pip install extcodetext
```

* Unicode と ECI 値に関する基本的な知識 – ECI 3 は UTF‑8、ECI 4 は ISO‑8859‑1 などに対応します。

> **Pro tip:** ECI 番号のリファレンステーブルを手元に置いておくと便利です。宣言したエンコーディングと実際のバイト列の不一致を防げます。

## ExtCodetextBuilder の理解

`ExtCodetextBuilder` は、複数のテキストフラグメントを連結しながら必要な ECI マーカーを自動的に挿入する小さなユーティリティです。ECI マーカーは、下流のバーコードエンコーダーに対して、続くバイトがどの文字セットで解釈すべきかを指示します。マーカーが無ければ、非 ASCII 文字は誤って解釈されてしまいます。

ビルダーは次の 3 つのシンプルなフェーズで動作します：

1. **Create** ビルダーインスタンスを作成。  
2. **Append** プレーンまたは ECI エンコードされたフラグメントを追加。  
3. **Retrieve** 結合された拡張コードテキスト文字列を取得。

以下では、具体的なコード例とともに各フェーズを順に解説します。

## Step 1: ExtCodetextBuilder インスタンスを作成

最初の行で、すべてのフラグメントを保持するオブジェクトを構築します。この時点で特別な設定は不要です。

```python
from extcodetext import ExtCodetextBuilder

# Step 1: Create an ExtCodetextBuilder instance
codetext_builder = ExtCodetextBuilder()
```

*Why this matters*: ビルダーをインスタンス化すると内部バッファが確保されます。その後のすべての `add_*` 呼び出しはこのバッファ上で動作し、指定した順序が保証されます。

## Step 2: プレーン（エンコードされていない）データを追加

プレーンデータはデフォルト文字セット（通常は ASCII）に属する文字で構成されます。そのようなフラグメントには `add_plain_codetext` を使用します。

```python
# Step 2: Append plain (un‑encoded) data to the builder
codetext_builder.add_plain_codetext("ABC123")
```

*Explanation*: 文字列 `"ABC123"` は ASCII のみで構成されているため、ECI マーカーは不要です。メソッドは単に生バイトを内部バッファに追加します。

## Step 3: ECI が必要なデータを追加

Unicode 文字（例：キリル文字、日本語、絵文字）を埋め込む場合は、エンコーダーに使用すべき文字セットを伝える必要があります。これは `add_eci_codetext(eci, text)` で行います。第1引数が数値の ECI 値、第2引数が実際のテキストです。

```python
# Step 3: Append data that must be preceded by an ECI (e.g., 3 for UTF‑8)
# This ensures the text "Привет" is correctly interpreted as UTF‑8
codetext_builder.add_eci_codetext(3, "Привет")
```

*Why ECI 3*: ISO/IEC 18004 仕様によれば、ECI 3 は UTF‑8 にマッピングされます。このマーカーを挿入することで、バーコードリーダーは続くバイト列を UTF‑8 としてデコードし、キリル文字を正しく保持します。

### 他のエンコーディングの取り扱い

ISO‑8859‑1（西ヨーロッパ）を使用したい場合は `add_eci_codetext(4, "¡Hola!")` とします。Shift‑JIS（日本語）の場合は ECI 値が 20 です：

```python
codetext_builder.add_eci_codetext(20, "こんにちは")
```

選択した ECI 値が対象のバーコードライブラリでサポートされているか必ず確認してください。サポート外の ECI はエンコード失敗の原因となります。

## Step 4: 結合された拡張コードテキスト文字列を取得

すべてのフラグメントを追加し終えたら、`get_extended_codetext()` を呼び出して最終文字列を取得します。この文字列には必要な ECI エスケープシーケンスがすべて含まれます。

```python
# Step 4: Retrieve the combined extended‑codetext string
extended_codetext = codetext_builder.get_extended_codetext()

print("Extended codetext:", extended_codetext)
```

**Expected output**（明瞭さのため Python の `repr` で表示）：

```
Extended codetext: 'ABC123\x1B\x1D\x03Привет'
```

*Breakdown*:

* `ABC123` – プレーン ASCII セグメント。  
* `\x1B\x1D\x03` – UTF‑8 用の ECI エスケープシーケンス（ESC GS 0x03）。  
* `Привет` – UTF‑8 エンコードされたキリル語の単語。

正確なエスケープバイトはライブラリ実装により異なる場合がありますが、論理的な順序は常に *プレーン → ECI マーカー → Unicode テキスト* となります。

## Full runnable example

すべてをまとめた、`create_extended_codetext.py` というファイル名で保存してすぐに実行できる自己完結型スクリプトです。

```python
#!/usr/bin/env python3
"""
Create extended codetext in Python using ExtCodetextBuilder.
Demonstrates plain text, UTF‑8 ECI, and how to retrieve the final string.
"""

from extcodetext import ExtCodetextBuilder

def main() -> None:
    # 1️⃣ Create the builder
    builder = ExtCodetextBuilder()

    # 2️⃣ Add a plain ASCII segment
    builder.add_plain_codetext("ABC123")

    # 3️⃣ Add a UTF‑8 segment (ECI 3) containing Cyrillic characters
    builder.add_eci_codetext(3, "Привет")

    # 4️⃣ Retrieve and display the extended codetext
    result = builder.get_extended_codetext()
    print("Extended codetext:", result)

if __name__ == "__main__":
    main()
```

スクリプトを実行すると、拡張コードテキスト文字列が出力され、拡張コードテキスト入力を受け付ける任意のバーコードエンコーダーにそのまま渡すことができます。

## Common pitfalls and how to avoid them

| 症状 | 考えられる原因 | 対策 |
|---|---|---|
| `UnicodeEncodeError` が `add_eci_codetext` 呼び出し時に発生 | 選択した ECI で表現できない文字を含む文字列を渡した | ECI が文字列の実際のエンコーディングと一致しているか確認（例：UTF‑8 テキストは必ず ECI 3 を使用）。 |
| 最終出力に ECI マーカーが欠落 | 非 ASCII データに対して誤って `add_plain_codetext` を使用した | ASCII 範囲外の文字はすべて `add_eci_codetext` に切り替える。 |
| バーコードスキャナーが文字化け | スキャナーが選択した ECI 値をサポートしていない | 汎用性の高い ECI（UTF‑8 が広くサポート）を選ぶか、対象言語が許容すれば ISO‑8859‑1 にフォールバックする。 |
| `get_extended_codetext` が空文字列を返す | メソッド呼び出し前にフラグメントが一つも追加されていない | 少なくとも一つの `add_*` 呼び出しが実行されていることを確認する。 |

### Edge case: Empty strings

`add_plain_codetext("")` や `add_eci_codetext(3, "")` を呼び出しても問題ありません。ビルダーは空フラグメントを単に無視します。ただし、空呼び出しが多数あると不要な ECI マーカーが生成される可能性があります。追加前に文字列長をチェックして回避しましょう。

```python
text = "data"
if text:
    builder.add_plain_codetext(text)
```

## Extending the pattern for dynamic data

実際のアプリケーションでは、ユーザー入力やデータベースレコードから拡張コードテキストを構築することが多いです。以下のスニペットは、`type` が `"plain"` または `"eci"` の `(type, value)` タプルのリストを処理するループ例です。

```python
fragments = [
    ("plain", "Order#"),
    ("plain", "98765"),
    ("eci", (3, "商品")),   # Japanese word "商品" (product) encoded as UTF‑8
]

for kind, payload in fragments:
    if kind == "plain":
        builder.add_plain_codetext(payload)
    elif kind == "eci":
        eci_val, text = payload
        builder.add_eci_codetext(eci_val, text)
    else:
        raise ValueError(f"Unsupported fragment type: {kind}")

print(builder.get_extended_codetext())
```

このアプローチはスケーラブルです。フラグメント定義を JSON、CSV、あるいは API から読み込んでも、コアロジックを変更する必要はありません。

## Testing the output

簡易ユニットテストでビルダーの挙動を検証できます。`pytest` を使用した例です。

```python
def test_extended_codetext():
    b = ExtCodetextBuilder()
    b.add_plain_codetext("X")
    b.add_eci_codetext(3, "✓")   # Check mark in UTF‑8
    result = b.get_extended_codetext()
    assert result.startswith("X")
    assert "\x1B\x1D\x03".encode() in result.encode()
```

`pytest` を実行してテストがすべてパスすれば、ECI マーカーが期待通りの位置に挿入されていることが確認できます。

## Related concepts you might explore next

* **Barcode encoding libraries** – 例: `python-barcode`、`zxing` バインディングなど、拡張コードテキスト文字列を直接受け取るもの。  
* **ECI table reference** – ISO/IEC 18004 が公開している数値 ECI の完全リストを Python の辞書として保持し、ルックアップに利用できます。  
* **Error correction levels** – QR コード生成時に、拡張コードテキストと適切な誤り訂正レベル（L, M, Q, H）を組み合わせて、スキャン耐性を高めます。  

## Conclusion

これで Python の `ExtCodetextBuilder` を使って **拡張コードテキストを作成** する方法が分かりました。手順はシンプルです：

1. ビルダーをインスタンス化する。  
2. 必要に応じてプレーンフラグメントと ECI エンコードフラグメントを追加する。  
3. 最終文字列を取得し、バーコードジェネレータに渡す。

上記パターンに従えば、ASCII と Unicode の混在データを自在に扱え、一般的なエンコーディングエラーを回避し、幅広いスキャナーで動作するバーコード対応文字列を生成できます。さまざまな ECI を試し、ビルダーをデータパイプラインに統合すれば、拡張コードテキストのすべてのニーズに対応できる堅牢な基盤が手に入ります。

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}