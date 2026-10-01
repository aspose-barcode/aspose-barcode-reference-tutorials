---
category: general
date: 2026-09-10
description: 비 ASCII 문자를 QR 코드에 인코딩하고 간단한 파이썬 빌더로 QR 코드 이미지를 저장하세요. ExtCodetextBuilder와
  BarcodeGenerator를 사용한 단계별 가이드를 따라보세요.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- encode non ascii characters
- save qr code image
- extended codetext builder
- eci encoding python
- barcode generation python
language: ko
lastmod: 2026-09-10
og_description: Python을 사용하여 QR 코드에 비 ASCII 문자를 인코딩하고 QR 코드 이미지를 저장합니다. 이 튜토리얼에서는
  확장된 코드 텍스트를 만들고, QR 코드를 생성하며, 이미지를 저장하는 방법을 보여줍니다.
og_image_alt: Diagram showing encode non ASCII characters in QR code and save QR code
  image workflow
og_title: QR 코드에 비 ASCII 문자 인코딩하고 QR 코드 이미지를 저장하는 단계별 파이썬 가이드
schemas:
- author: Aspose
  dateModified: '2026-09-10'
  description: Encode non ASCII characters in a QR code and save QR code image with
    a simple Python builder. Follow a step‑by‑step guide using ExtCodetextBuilder
    and BarcodeGenerator.
  headline: Encode non ASCII characters in QR code and save QR code image
  type: TechArticle
tags:
- barcode
- QR code
- Python
title: QR 코드에 비 ASCII 문자를 인코딩하고 QR 코드 이미지를 저장
url: /ko/python/general/encode-non-ascii-characters-in-qr-code-and-save-qr-code-imag/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# QR 코드에서 비 ASCII 문자 인코딩 및 QR 코드 이미지 저장

QR 코드에서 **비 ASCII 문자 인코딩**이 필요하다면, 이 가이드는 정확히 어떻게 수행하고 **QR 코드 이미지 저장**을 디스크에 하는지 보여줍니다. 러시아어, 중국어, 이모지 데이터를 다루든, ExtCodetextBuilder를 사용하면 수동으로 바이트를 조작하지 않고도 일반 텍스트와 ECI‑인코딩 세그먼트를 혼합할 수 있습니다.

확장 코덱텍스트 문자열을 생성하고, 해당 문자열을 이해하는 QR 코드를 생성하며, 마지막으로 바코드 이미지를 파일에 쓰는 방법을 배우게 됩니다. 이 튜토리얼은 기본적인 Python 지식과 `barcode` SDK가 설치되어 있다고 가정합니다.

## 전제 조건

* Python 3.8+ 설치.
* `barcode` Python 패키지(또는 해당 SDK)로 `ExtCodetextBuilder`, `CodetextEncodingType`, `BarcodeGenerator`를 제공합니다.
* **QR 코드 이미지 저장**을 원하는 디렉터리에 대한 쓰기 권한.

pip으로 SDK를 설치할 수 있습니다(`barcode-sdk`를 실제 패키지 이름으로 교체하세요):

```bash
pip install barcode-sdk
```

## 단계 1: 확장 코덱텍스트 빌더 생성

첫 번째 단계는 `ExtCodetextBuilder`를 인스턴스화하는 것입니다. 이 객체는 여러 텍스트 세그먼트를 수집하여 QR 코드 심볼이 해석할 수 있는 단일 문자열을 생성합니다.

```python
from barcode import ExtCodetextBuilder, CodetextEncodingType, BarcodeGenerator, Symbology

# Initialize the builder that will hold all text parts
ext_builder = ExtCodetextBuilder()
```

*Why this matters*: QR 코드는 **확장 코덱텍스트**를 지원하므로 하나의 바코드에 여러 인코딩 모드(일반, ECI 등)를 삽입할 수 있습니다. 빌더는 QR 사양에서 요구되는 저수준 포맷팅을 추상화합니다.

## 단계 2: 일반 텍스트 세그먼트 추가

일반 텍스트는 기본 모드이며 ASCII 문자에 대해 작동합니다. 먼저 추가하면 ECI를 무시하는 스캐너에 대해 읽을 수 있는 대체 텍스트를 제공합니다.

```python
# Add simple ASCII text
ext_builder.add_plain_codetext("HelloWorld")
```

이 단계를 생략하면 QR 코드에 ECI 세그먼트만 포함되며, 일부 오래된 리더기가 올바르게 디코딩하지 못할 수 있습니다.

## 단계 3: 비‑ASCII 문자를 위한 ECI‑인코딩 세그먼트 추가

ASCII 범위를 벗어나는 문자(예: 키릴 문자, 중국어, 이모지)를 포함하려면 ECI(Extended Channel Interpretation) 인코딩을 지정해야 합니다. 여기서는 러시아어 단어 “Привет”에 UTF‑8을 사용합니다.

```python
# Add a UTF‑8 encoded segment containing non‑ASCII characters
ext_builder.add_eci_codetext(CodetextEncodingType.UTF_8, "Привет")  # Russian “Hi”
```

*Why this works*: QR 사양은 스캐너에 적용할 문자 집합을 알려주는 ECI 값을 정의합니다. ECI 마커가 없으면 원시 바이트가 ISO‑8859‑1로 해석되어 깨진 출력이 발생합니다.

## 단계 4: 결합된 확장 코덱텍스트 문자열 가져오기

원하는 모든 세그먼트를 추가한 후 `get_extended_codetext()`를 호출하여 바코드 생성기가 기대하는 최종 문자열을 얻습니다.

```python
# Combine all parts into one extended codetext string
extended_codetext = ext_builder.get_extended_codetext()
print("Extended codetext:", extended_codetext)
```

출력된 값은 실제 텍스트 앞에 일련의 제어 문자들이 붙어 있는 형태이지만, 이를 수동으로 파싱할 필요는 없습니다.

## 단계 5: 확장 코덱텍스트를 사용해 QR 코드 생성

이제 `BarcodeGenerator`를 생성하고, 심볼을 QR로 설정한 뒤(확장 코덱텍스트를 지원하는 유일한 일반 2‑D 심볼), 결합된 문자열을 전달합니다.

```python
# Initialize the QR generator
qr_generator = BarcodeGenerator()
qr_generator.set_symbology(Symbology.QR)          # QR supports extended codetext
qr_generator.set_code_text(extended_codetext)
```

*Tip*: 같은 과정을 Code‑128이나 DataMatrix에 적용하면, 해당 포맷이 ECI 마커를 해석할 수 없으므로 SDK가 예외를 발생시킵니다.

## 단계 6: QR 코드 이미지 저장

마지막으로 바코드를 PNG 파일로 저장합니다. 여기서 **QR 코드 이미지 저장**을 수행합니다.

```python
output_path = "output/qr_extended.png"
qr_generator.save(output_path)

print(f"QR code saved to {output_path}")
```

`save`를 호출하기 전에 `output` 폴더가 존재하는지 확인하거나 `os.makedirs('output', exist_ok=True)`로 생성하세요.

### 전체 실행 가능한 예제

모든 단계를 합치면 즉시 실행할 수 있는 독립형 스크립트를 얻을 수 있습니다:

```python
import os
from barcode import ExtCodetextBuilder, CodetextEncodingType, BarcodeGenerator, Symbology

# Ensure the output directory exists
os.makedirs("output", exist_ok=True)

# 1️⃣ Create the builder
ext_builder = ExtCodetextBuilder()

# 2️⃣ Add plain ASCII text
ext_builder.add_plain_codetext("HelloWorld")

# 3️⃣ Add UTF‑8 encoded non‑ASCII text (Russian)
ext_builder.add_eci_codetext(CodetextEncodingType.UTF_8, "Привет")

# 4️⃣ Retrieve the combined string
extended_codetext = ext_builder.get_extended_codetext()
print("Extended codetext:", extended_codetext)

# 5️⃣ Generate QR code
qr_generator = BarcodeGenerator()
qr_generator.set_symbology(Symbology.QR)
qr_generator.set_code_text(extended_codetext)

# 6️⃣ Save the image
output_file = "output/qr_extended.png"
qr_generator.save(output_file)
print(f"QR code saved to {output_file}")
```

**예상 출력** (콘솔):

```
Extended codetext: <binary representation showing ECI markers>
QR code saved to output/qr_extended.png
```

`qr_extended.png`를 어떤 QR 스캐너로 열어도 `HelloWorldПривет`가 표시됩니다. ECI를 이해하는 스캐너는 키릴 문자를 올바르게 렌더링하고, 그렇지 않은 경우 ASCII 부분만 표시합니다.

## 일반적인 질문 및 엣지 케이스

| Question | Answer |
|----------|--------|
| *Shift‑JIS와 같은 다른 인코딩을 사용할 수 있나요?* | 예. `CodetextEncodingType.UTF_8`을 `CodetextEncodingType.SHIFT_JIS`로 교체하고 해당 텍스트를 제공하면 됩니다. |
| *결합된 데이터가 QR 용량을 초과하면 어떻게 하나요?* | QR 코드는 버전 제한이 있으며(최대 177 × 177 모듈) 빌더가 크기 예외를 발생시키면 오류 정정 레벨을 높이거나 데이터를 여러 QR 코드로 나누어야 합니다. |
| *특정 QR 버전을 설정해야 하나요?* | SDK는 데이터에 맞는 가장 작은 버전을 자동으로 선택합니다. 필요하다면 `qr_generator.set_qr_version(10)`으로 버전을 강제 지정할 수 있습니다. |
| *이미지가 투명하게 되나요?* | 기본적으로 SDK는 흰 배경의 PNG를 작성합니다. 투명이 필요하면 `save` 전에 `qr_generator.set_background_color(Color.Transparent)`를 사용하세요. |

## 결론

이 튜토리얼에서는 `ExtCodetextBuilder`를 사용해 QR 코드에 **비 ASCII 문자 인코딩**을 수행하고, `BarcodeGenerator`로 **QR 코드 이미지 저장**하는 방법을 배웠습니다. 이 과정은 확장 코덱텍스트 문자열을 만들고, 일반 및 ECI‑인코딩 세그먼트를 추가한 뒤, QR 심볼을 생성하고 최종적으로 이미지 파일을 쓰는 단계로 이루어집니다.

여기서부터 다음을 탐색할 수 있습니다:

* 더 많은 ECI 세그먼트 추가(다른 언어 또는 이모지).
* 높은 신뢰성을 위한 QR 오류 정정 레벨 조정.
* 생성된 PNG를 PDF나 웹 페이지에 삽입.

코딩을 즐기시고 다국어 QR 코드를 만드는 재미를 느끼세요!

## 다음에 배울 내용은?

다음 튜토리얼들은 이 가이드에서 시연한 기술을 기반으로 하는 밀접한 주제를 다룹니다. 각 자료는 단계별 설명과 함께 완전한 코드 예제를 제공하여 추가 API 기능을 숙달하고 프로젝트에서 대체 구현 방식을 탐색하도록 돕습니다.

- [Python에서 Aspose.Barcode으로 QR 코드 이미지 생성 방법 – 전체 가이드](/barcode/english/python/general/how-to-generate-qr-code-image-in-python-with-aspose-barcode/)
- [Aspose.Barcode Python으로 Code128 바코드 생성 – 전체 가이드](/barcode/english/python/general/generate-code128-barcode-with-aspose-barcode-python-full-gui/)
- [Python 바코드 라이브러리로 제품 이름 표시 – 단계별 가이드](/barcode/english/python/general/display-product-name-using-python-barcode-library-step-by-st/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}