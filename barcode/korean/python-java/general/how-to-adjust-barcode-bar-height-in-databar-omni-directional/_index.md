---
category: general
date: 2026-11-27
description: DataBar Omni‑Directional 바코드 생성기에서 바코드 바 높이를 조정하는 방법을 배웁니다. 단계별 코드에서는
  높이를 30 px와 60 px로 설정하는 것을 보여줍니다.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- adjust barcode bar height
- DataBar Omni‑Directional barcode
- set XDimension
- barcode image format
- BarCodeImageFormat
- barcode generator python
language: ko
lastmod: 2026-11-27
og_description: Python을 사용한 DataBar Omni‑Directional 바코드 생성기에서 바코드 바 높이를 조정하세요. 높이와
  X‑차원을 설정하고 PNG 이미지를 저장하는 전체 가이드를 따라보세요.
og_image_alt: Screenshot of a DataBar Omni‑Directional barcode with adjusted bar height
og_title: DataBar Omni‑Directional 생성기에서 바코드 바 높이 조정
schemas:
- author: GroupDocs
  dateModified: '2026-11-27'
  description: Learn how to adjust barcode bar height in a DataBar Omni‑Directional
    barcode generator. Step‑by‑step code shows setting heights to 30 px and 60 px.
  headline: How to adjust barcode bar height in DataBar Omni‑Directional generator
  type: TechArticle
tags:
- barcode
- python
- DataBar
- imaging
title: DataBar Omni‑Directional 생성기에서 바코드 바 높이 조정 방법
url: /ko/python-java/general/how-to-adjust-barcode-bar-height-in-databar-omni-directional/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# DataBar Omni‑Directional 생성기에서 바코드 바 높이 조정 방법

DataBar Omni‑Directional 바코드의 **바코드 바 높이**를 조정해야 하는 경우, 이 가이드에서 정확히 방법을 보여드립니다. X‑dimension과 이미지 형식을 동일하게 유지하면서 바 높이를 30 px에서 60 px로 변경하는 완전하고 실행 가능한 Python 예제를 확인할 수 있습니다.

바코드의 시각적 크기를 변경하는 것은 바코드가 특정 라벨 크기나 디자인 가이드라인에 맞아야 할 때 흔히 요구되는 작업입니다. 바 높이 외에도 **X‑dimension**(모듈 크기)을 조정하거나 PNG 또는 JPEG와 같은 다른 **바코드 이미지 형식**을 선택하고 싶을 수 있습니다.

이 튜토리얼에서 여러분은:

* 필요한 라이브러리(GroupDocs.Barcode for Python)를 설치합니다
* DataBar Omni‑Directional 바코드 생성기를 만듭니다
* `XDimension`으로 모듈 크기를 설정합니다
* 바 높이 속성을 두 번 조정합니다
* 원하는 **BarCodeImageFormat**으로 결과 이미지를 저장합니다

GroupDocs API에 대한 사전 경험은 필요하지 않으며, 기본적인 Python 지식만 있으면 됩니다.

## 사전 요구 사항

시작하기 전에 다음이 준비되어 있는지 확인하세요:

* Python 3.8 이상 설치
* `groupdocs.barcode` 패키지(`pip install groupdocs-barcode`)
* PNG 파일이 저장될 폴더에 대한 쓰기 권한

**DataBar Omni‑Directional 바코드**에 익숙하지 않다면, 이 바코드는 14자리 GTIN을 인코딩하며 소매업에서 어느 방향에서든 스캔할 수 있도록 널리 사용됩니다.

## Step 1: Set up the DataBar Omni‑Directional barcode generator

먼저 필요한 클래스를 가져오고 인코딩하려는 GTIN 데이터로 생성기를 인스턴스화합니다.

```python
from groupdocs.barcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat

# Create a generator for a DataBar Omni‑Directional barcode
# The string "(01)12345678901231" follows the GS1 Application Identifier syntax
gen = BarcodeGenerator(EncodeTypes.DatabarOmniDirectional, "(01)12345678901231")
```

*왜 중요한가:* `EncodeTypes.DatabarOmniDirectional` 상수는 라이브러리에게 Omni‑Directional 심볼을 생성하도록 지시합니다. 데이터 문자열에는 GTIN‑14 값을 나타내는 AI `(01)`이 포함됩니다.

## Step 2: Define the X‑dimension (module size)

X‑dimension은 가장 좁은 바의 너비를 제어합니다. 화면 렌더링에 일반적으로 사용되는 값은 **모듈당 2 px**입니다.

```python
# Set the module (X‑dimension) size – 2 px per module
gen.parameters.barcode.x_dimension.pixels = 2
```

일관된 **set XDimension**을 사용하면 다양한 프린터와 스캐너에서 바코드가 올바르게 스케일링됩니다.

## Step 3: Adjust the bar height to 30 px and save the image

이제 바 높이 속성을 변경합니다. 첫 번째로 사용할 높이는 **30 px**이며, 작은 라벨에 적합합니다.

```python
# Define the first bar height (30 px)
gen.parameters.barcode.bar_height.pixels = 30

# Save the barcode as a PNG image
gen.save("output/DatabarBarHeight30Pixels.png", BarCodeImageFormat.Png)
```

`BarCodeImageFormat.Png` 상수는 손실 없는 품질을 유지하는 **바코드 이미지 형식** PNG를 선택합니다.

### Expected result

`DatabarBarHeight30Pixels.png` 파일에는 바가 30 px 높이인 DataBar Omni‑Directional 바코드가 포함됩니다. 아래는 자리표시자 미리보기입니다:

![30 px 바 높이를 가진 DataBar 바코드](images/databar_30px.png "30 px 바 높이를 가진 DataBar 바코드")

> **팁:** PNG를 이미지 편집기에서 열면 정확한 바 높이를 확인할 수 있습니다. 좁은 바는 앞서 정의한 대로 2 px 너비입니다.

## Step 4: Change the bar height to 60 px for a taller barcode

시각적 면적이 더 큰 애플리케이션(예: 화물 라벨)에서는 바 높이를 **60 px**로 늘릴 수 있습니다.

```python
# Change the bar height to 60 px for a taller barcode
gen.parameters.barcode.bar_height.pixels = 60
```

`BarHeight` 속성만 변경되며, X‑dimension과 인코딩은 동일하게 유지되므로 바코드는 계속 스캔 가능합니다.

## Step 5: Save the updated barcode image

마지막으로, 더 높은 바코드를 두 번째 PNG 파일에 기록합니다.

```python
# Save the updated barcode image
gen.save("output/DatabarBarHeight60Pixels.png", BarCodeImageFormat.Png)
```

### Expected result

`DatabarBarHeight60Pixels.png` 파일은 동일한 데이터를 인코딩하지만 각 바가 이제 60 px 높이입니다. 시각적 차이는 아래에 나타납니다:

![60 px 바 높이를 가진 DataBar 바코드](images/databar_60px.png "60 px 바 높이를 가진 DataBar 바코드")

## Full, runnable example

모든 내용을 하나로 모아, `adjust_barcode_height.py`라는 파일에 복사‑붙여넣기하고 바로 실행할 수 있는 전체 스크립트를 제공합니다.

```python
# adjust_barcode_height.py
# Demonstrates how to adjust barcode bar height for a DataBar Omni‑Directional barcode

from groupdocs.barcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat
import os

# Ensure the output directory exists
output_dir = "output"
os.makedirs(output_dir, exist_ok=True)

# 1️⃣ Create the generator with GTIN data
gen = BarcodeGenerator(EncodeTypes.DatabarOmniDirectional, "(01)12345678901231")

# 2️⃣ Set module size (X‑dimension) to 2 px
gen.parameters.barcode.x_dimension.pixels = 2

# 3️⃣ First bar height: 30 px
gen.parameters.barcode.bar_height.pixels = 30
gen.save(os.path.join(output_dir, "DatabarBarHeight30Pixels.png"), BarCodeImageFormat.Png)

# 4️⃣ Second bar height: 60 px
gen.parameters.barcode.bar_height.pixels = 60
gen.save(os.path.join(output_dir, "DatabarBarHeight60Pixels.png"), BarCodeImageFormat.Png)

print(f"Barcodes saved to '{output_dir}'")
```

스크립트를 실행합니다:

```bash
python adjust_barcode_height.py
```

`output` 폴더에 두 개의 PNG 파일이 생성되며, 각각 설정한 바 높이를 반영합니다.

## Common questions and edge cases

| 질문 | 답변 |
|----------|--------|
| **PNG 대신 JPEG를 사용할 수 있나요?** | 예. `BarCodeImageFormat.Png`를 `BarCodeImageFormat.Jpeg`로 교체하면 됩니다. JPEG는 손실이 있으므로 정밀 스캔을 위해서는 PNG를 권장합니다. |
| **10의 배수가 아닌 바 높이가 필요하면 어떻게 하나요?** | `BarHeight.Pixels` 속성은 정수값이면 모두 허용합니다. 원하는 픽셀 수(예: `45`)를 할당하면 됩니다. |
| **바 높이를 변경하면 인코딩된 데이터에 영향을 줍니까?** | 아니요. 시각적 표현만 변경되며, 기본 데이터 문자열은 동일하게 유지됩니다. |
| **첫 번째 이미지를 저장한 후 X‑dimension을 어떻게 변경합니까?** | `save()`를 호출하기 전 언제든지 `gen.parameters.barcode.x_dimension.pixels`를 수정할 수 있습니다. 변경은 이후 이미지에 적용됩니다. |
| **생성기가 스레드‑안전한가요?** | `BarcodeGenerator` 인스턴스는 스레드‑안전이 보장되지 않습니다. 동시에 바코드를 생성해야 할 경우 스레드당 별도 인스턴스를 생성하십시오. |

## Conclusion

이제 Python을 사용하여 DataBar Omni‑Directional 바코드 생성기에서 **바코드 바 높이**를 조정하는 방법을 알게 되었습니다. 튜토리얼에서는 생성기 만들기, **X‑dimension** 설정, **바코드 바 높이** 속성 수정, 원하는 **바코드 이미지 형식**으로 이미지 저장까지 다루었습니다.

여기서부터는 다른 높이, 다양한 모듈 크기, JPEG 또는 BMP와 같은 대체 이미지 형식 등을 실험해 볼 수 있습니다. 또한 **barcode generator python**의 추가 기능(예: 인간이 읽을 수 있는 텍스트 추가, 색상 스키마 변경)도 탐색해 보세요.

행복한 코딩 되시고, 바코드를 선명하고 완벽한 크기로 유지하세요!

## What Should You Learn Next?

다음 튜토리얼은 이 가이드에서 시연한 기술을 기반으로 하며, 밀접하게 관련된 주제를 다룹니다. 각 리소스에는 완전한 동작 코드 예제와 단계별 설명이 포함되어 있어 추가 API 기능을 숙달하고 프로젝트에 적용할 수 있는 다양한 구현 방식을 탐색할 수 있습니다.

- [GS1 DataBar Omni‑Directional 바코드의 너비 설정 및 높이 조정 방법](/barcode/english/python-java/general/how-to-set-width-and-adjust-height-for-a-gs1-databar-omni-di/)
- [Python에서 Omni‑Directional Databar 및 바코드 이미지 생성](/barcode/english/python-java/general/create-omni-directional-databar-and-barcode-image-in-python/)
- [.net 바코드 생성기 – 바코드 높이 변경](/barcode/english/python-java/general/net-barcode-generator-change-barcode-height/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}