---
category: general
date: 2026-08-19
description: Aspose.Barcode for Python을 사용하여 ECI가 포함된 바코드를 생성하는 방법. ECI 데이터를 추가하고
  일반 텍스트와 혼합하며 이미지를 저장하는 방법을 한눈에 보기 쉬운 가이드에서 배워보세요.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to generate barcode
- how to add eci
- Aspose.Barcode Python
- extended codetext barcode
- ECI encoding Python
language: ko
lastmod: 2026-08-19
og_description: Aspose.Barcode for Python을 사용하여 ECI가 포함된 바코드를 생성하는 방법. 이 튜토리얼을 따라
  ECI 데이터를 추가하고, 모양을 사용자 정의하며, 결과를 저장하는 방법을 배워보세요.
og_image_alt: Screenshot showing a barcode generated with how to generate barcode
  example
og_title: Aspose.Barcode Python을 사용하여 ECI가 포함된 바코드 생성 방법 – 단계별
schemas:
- author: Aspose
  dateModified: '2026-08-19'
  description: How to generate barcode with ECI using Aspose.Barcode for Python. Learn
    how to add eci data, mix plain text, and save the image in one clear guide.
  headline: How to generate barcode with ECI using Aspose.Barcode Python
  type: TechArticle
- description: How to generate barcode with ECI using Aspose.Barcode for Python. Learn
    how to add eci data, mix plain text, and save the image in one clear guide.
  name: How to generate barcode with ECI using Aspose.Barcode Python
  steps:
  - name: Expected result
    text: When you open `extended_codetext.png`, you should see a Code 128 barcode
      that encodes the numeric string `1234567890` followed by the Chinese characters
      “特殊字符”. Scanning the barcode with a modern scanner that respects ECI will return
      the original mixed string.
  - name: What if I need a different character set?
    text: Choose the appropriate ECI value from the ISO/IEC 18004 table. For example,
      ECI 27 represents ISO‑8859‑1 (Latin‑1). Replace the numeric identifier in `add_eci_codetext`
      accordingly.
  - name: Can I embed more than one ECI block?
    text: Yes. Call `add_eci_codetext` multiple times. The builder inserts the necessary
      ECI switch codes between blocks, preserving the order you add them.
  - name: Does the generator support QR codes with ECI?
    text: Absolutely. Replace `barcode.Symbology.CODE_128` with `barcode.Symbology.QR`
      and adjust any QR‑specific parameters (e.g., error correction level) via `generator.parameters.qr`.
  - name: How to handle very long data strings?
    text: For linear barcodes like Code 128, the maximum length is about 80 characters
      when using extended codetext. If you exceed that, consider switching to a two‑dimensional
      symbology such as QR or Data Matrix, which can store thousands of characters.
  type: HowTo
tags:
- barcode
- Python
- Aspose
title: Aspose.Barcode Python을 사용하여 ECI가 포함된 바코드 생성 방법
url: /ko/python/general/how-to-generate-barcode-with-eci-using-aspose-barcode-python/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# ECI를 사용하여 Aspose.Barcode Python으로 바코드 생성 방법

일반 문자와 ECI‑인코딩된 데이터를 모두 포함하는 **바코드 생성 방법**을 알아야 한다면, 이 가이드는 전체 과정을 보여줍니다. **how to add eci** 섹션을 정확히 어떻게 추가하고, 크기를 조정하며, 단일 실행 가능한 스크립트로 이미지를 디스크에 저장하는지 확인할 수 있습니다.

이 튜토리얼에서는 다음을 다룹니다:

* Aspose.Barcode 라이브러리 버전 확인 (선택 사항이지만 디버깅에 유용)  
* 일반 문자와 ECI‑인코딩된 문자를 혼합한 확장 코드텍스트 문자열 만들기  
* 확장 코드텍스트를 지원하는 심볼로지를 위한 바코드 생성기 생성  
* 바코드 크기 조정 및 최종 PNG 파일 저장

외부 문서를 참조할 필요 없이 코드를 복사해 실행하면, ECI 26(UTF‑8)으로 인코딩된 중국어 문자를 포함한 바코드 이미지를 얻을 수 있습니다.

## Prerequisites

시작하기 전에 다음이 준비되어 있는지 확인하세요:

* Python 3.8 이상이 설치되어 있음  
* `aspose-barcode` 패키지 설치 (`pip install aspose-barcode`)  
* PNG 파일을 저장하려는 폴더에 대한 쓰기 권한

가상 환경을 사용 중이라면, 의존성을 격리하기 위해 먼저 환경을 활성화하세요.

## Step 1: Verify the Aspose.Barcode version (optional)

정확한 라이브러리 버전을 알면 버그를 보고하거나 릴리스 간 기능을 비교할 때 도움이 됩니다.

```python
import aspose.barcode as barcode
from aspose.barcode.generation import BuildVersionInfo

ver = BuildVersionInfo()
print("Assembly version :", ver.ASSEMBLY_VERSION)
print("Product version  :", f"{ver.PRODUCT_MAJOR}.{ver.PRODUCT_MINOR}")
print("Release date     :", ver.RELEASE_DATE)
```

*Why this matters*: 버전 출력은 현재 실행 환경이 참고하고 있는 문서와 일치함을 확인시켜 줍니다. 버전에 따라 지원되는 ECI 값이 다를 수 있으므로 간단한 검증 단계가 됩니다.

## Step 2: Build an extended codetext with plain and ECI‑encoded parts

Aspose.Barcode는 일반 데이터와 ECI‑인코딩된 구간을 연결하기 위해 `ExtCodetextBuilder`를 제공합니다. 이 예제에서는 숫자 문자열과 중국어 문자를 혼합합니다.

```python
from aspose.barcode.generation import ExtCodetextBuilder

builder = ExtCodetextBuilder()
builder.add_plain_codetext("1234567890")          # plain numeric data
builder.add_eci_codetext(26, "特殊字符")          # Chinese characters using ECI 26 (UTF‑8)
extended_codetext = builder.get_extended_codetext()
print("Extended codetext :", extended_codetext)
```

*Explanation*:  
* `add_plain_codetext`는 바코드 심볼로지가 일반 문자로 처리하는 데이터를 삽입합니다.  
* `add_eci_codetext`는 생성기에 ECI 표시자(여기서는 **26**, UTF‑8에 해당)를 제공된 텍스트 앞에 추가하도록 지시합니다. 이는 바로 **how to add eci** 데이터를 바코드에 삽입하는 방법입니다.

`add_eci_codetext`를 여러 번 호출하면 서로 다른 언어 블록을 여러 개 삽입할 수 있습니다. 빌더는 필요한 이스케이프 시퀀스를 자동으로 처리합니다.

## Step 3: Choose a symbology that supports extended codetext

모든 바코드 유형이 ECI 구간을 저장할 수 있는 것은 아닙니다. Code 128, QR, Data Matrix 등이 일반적인 선택입니다. 예제에서는 널리 지원되고 혼합 알파벳-숫자 데이터를 잘 처리하는 Code 128을 사용합니다.

```python
generator = barcode.generator.BarcodeGenerator(
    barcode.Symbology.CODE_128,   # Code128 supports extended codetext
    extended_codetext
)
```

*Why Code 128?*: 전체 ASCII 범위와 빌더가 생성하는 ECI 이스케이프 시퀀스를 모두 허용하므로, 일반 문자와 인코딩된 텍스트를 혼합하는 “how to generate barcode” 시나리오에 이상적입니다.

## Step 4: Adjust barcode appearance

`parameters` 객체를 통해 크기, 높이, 여백 등 다양한 시각적 요소를 제어할 수 있습니다.

```python
# Width of a single module (the smallest bar)
generator.parameters.barcode.x_dimension = 2   # 2 pixels per module

# Height of the bars (for linear barcodes)
generator.parameters.barcode.bar_height = 50  # 50 pixels tall

# Optional: add quiet zone (margin) if required by a scanner
generator.parameters.barcode.is_quiet_zone_visible = True
generator.parameters.barcode.quiet_zone = 10   # 10 pixels margin on each side
```

*Tip*: 바코드를 인쇄할 계획이라면 목표 DPI에서 가독성을 유지하도록 `x_dimension`과 `bar_height`를 비례적으로 늘리세요.

## Step 5: Save the barcode image

마지막으로 생성된 이미지를 파일에 저장합니다. Aspose.Barcode는 PNG, JPEG, BMP 등 여러 포맷을 지원합니다.

```python
output_path = "output/extended_codetext.png"
generator.save(output_path)
print(f"Barcode saved as {output_path}")
```

`save`를 호출하기 전에 `output` 폴더가 존재하는지 확인하거나 `os.makedirs("output", exist_ok=True)`로 생성하세요.

### Expected result

`extended_codetext.png` 파일을 열면 숫자 문자열 `1234567890` 뒤에 중국어 문자 “特殊字符”가 인코딩된 Code 128 바코드가 표시됩니다. ECI를 인식하는 최신 스캐너로 바코드를 스캔하면 원래의 혼합 문자열이 반환됩니다.

![Barcode generated with how to generate barcode example](https://example.com/images/barcode-sample.png){: .align-center alt="바코드 생성 예제와 함께 생성된 바코드"}

## Common questions and edge cases

### What if I need a different character set?

ISO/IEC 18004 표에서 적절한 ECI 값을 선택하세요. 예를 들어, ECI 27은 ISO‑8859‑1(Latin‑1)을 나타냅니다. `add_eci_codetext`의 숫자 식별자를 해당 값으로 교체하면 됩니다.

### Can I embed more than one ECI block?

예. `add_eci_codetext`를 여러 번 호출하면 됩니다. 빌더가 블록 사이에 필요한 ECI 전환 코드를 삽입해 주어, 추가한 순서를 그대로 유지합니다.

### Does the generator support QR codes with ECI?

물론입니다. `barcode.Symbology.CODE_128`을 `barcode.Symbology.QR`로 교체하고, `generator.parameters.qr`를 통해 QR‑전용 매개변수(예: 오류 정정 수준)를 조정하면 됩니다.

```python
generator.parameters.qr.error_correction_level = barcode.QRErrorLevel.H
```

### How to handle very long data strings?

Code 128과 같은 1차원 바코드의 경우, 확장 코드텍스트를 사용할 때 최대 길이는 약 80 문자입니다. 이를 초과하면 QR 또는 Data Matrix와 같은 2차원 심볼로지로 전환하는 것이 좋으며, 수천 문자를 저장할 수 있습니다.

## Full, runnable script

아래는 `generate_extended_barcode.py`라는 파일에 복사‑붙여넣기 한 뒤 바로 실행할 수 있는 전체 프로그램입니다.

```python
import os
import aspose.barcode as barcode
from aspose.barcode.generation import ExtCodetextBuilder, BuildVersionInfo

# ------------------------------------------------------------------
# Optional: print library version – useful for troubleshooting
# ------------------------------------------------------------------
ver = BuildVersionInfo()
print("Assembly version :", ver.ASSEMBLY_VERSION)
print("Product version  :", f"{ver.PRODUCT_MAJOR}.{ver.PRODUCT_MINOR}")
print("Release date     :", ver.RELEASE_DATE)

# ------------------------------------------------------------------
# Build extended codetext: plain numbers + Chinese characters (ECI 26)
# ------------------------------------------------------------------
builder = ExtCodetextBuilder()
builder.add_plain_codetext("1234567890")          # plain numeric data
builder.add_eci_codetext(26, "特殊字符")          # Chinese characters using UTF‑8
extended_codetext = builder.get_extended_codetext()
print("Extended codetext :", extended_codetext)

# ------------------------------------------------------------------
# Create a Code128 generator – supports the extended codetext format
# ------------------------------------------------------------------
generator = barcode.generator.BarcodeGenerator(
    barcode.Symbology.CODE_128,
    extended_codetext
)

# ------------------------------------------------------------------
# Customize appearance (size, quiet zone, etc.)
# ------------------------------------------------------------------
generator.parameters.barcode.x_dimension = 2
generator.parameters.barcode.bar_height = 50
generator.parameters.barcode.is_quiet_zone_visible = True
generator.parameters.barcode.quiet_zone = 10

# ------------------------------------------------------------------
# Ensure output directory exists and save the image
# ------------------------------------------------------------------
output_dir = "output"
os.makedirs(output_dir, exist_ok=True)
output_path = os.path.join(output_dir, "extended


## What Should You Learn Next?

다음 튜토리얼들은 이 가이드에서 시연한 기술을 기반으로 하여 밀접하게 관련된 주제를 다룹니다. 각 자료에는 완전한 동작 코드 예제와 단계별 설명이 포함되어 있어, 추가 API 기능을 마스터하고 프로젝트에 적용할 수 있는 다양한 구현 방식을 탐색하는 데 도움이 됩니다.

- [How to Generate Barcode Image with Supplemental Space Customization using Aspose.BarCode](/barcode/english/net/supplemental-barcode-data/supplemental-barcode-space-customization/)
- [How to Generate Barcode Image in Java with Aspose.BarCode](/barcode/english/java/barcode-rendering-techniques/)
- [How to generate DataMatrix barcode with Aspose.BarCode for .NET](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-macro-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}