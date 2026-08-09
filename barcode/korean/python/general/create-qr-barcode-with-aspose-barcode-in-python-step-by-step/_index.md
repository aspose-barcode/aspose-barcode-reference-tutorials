---
category: general
date: 2026-08-09
description: Aspose.BarCode를 사용하여 Python에서 QR 바코드를 생성합니다. 확장된 코드텍스트를 만드는 방법, 외관을 조정하는
  방법, 이미지를 저장하는 방법을 모두 한 튜토리얼에서 배워보세요.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create QR barcode
- Aspose.BarCode Python
- extended codetext QR
- QR code generation Python
- barcode visual customization
language: ko
lastmod: 2026-08-09
og_description: Aspose.BarCode를 사용하여 Python에서 QR 바코드를 생성합니다. 이 가이드는 확장된 코드텍스트를 만들고,
  시각적 매개변수를 설정하며, 이미지를 내보내는 방법을 보여줍니다.
og_image_alt: Screenshot of a generated QR barcode created with Aspose.BarCode in
  Python
og_title: Python에서 Aspose.BarCode로 QR 바코드 생성 – 전체 코드 예제
schemas:
- author: Aspose
  dateModified: '2026-08-09'
  description: Create QR barcode in Python using Aspose.BarCode. Learn how to build
    extended codetext, adjust appearance, and save the image—all in one tutorial.
  headline: Create QR barcode with Aspose.BarCode in Python – step‑by‑step guide
  type: TechArticle
- description: Create QR barcode in Python using Aspose.BarCode. Learn how to build
    extended codetext, adjust appearance, and save the image—all in one tutorial.
  name: Create QR barcode with Aspose.BarCode in Python – step‑by‑step guide
  steps:
  - name: Common variations
    text: '- **Multiple ECI segments:** Call `add_eci_codetext` multiple times to
      mix several languages. - **Different ECI identifiers:** Use `27` for ISO‑8859‑1,
      `28` for ISO‑8859‑2, etc., depending on your target encoding.'
  - name: Edge case handling
    text: '- **High‑density data:** If the encoded data is large, you may need to
      increase `x_dimension` or choose a higher error‑correction level (via `qr_generator.parameters.qr.error_correction_level`).
      - **Transparent background:** Set `qr_generator.parameters.barcode.bg_color
      = Color.Transparent` for PNGs'
  - name: Verifying the result
    text: 'Open the saved file in any image viewer. You should see a QR code that,
      when scanned, returns the combined string:'
  type: HowTo
tags:
- QR code
- Python
- Aspose
- Barcode generation
title: Python에서 Aspose.BarCode로 QR 바코드 만들기 – 단계별 가이드
url: /ko/python/general/create-qr-barcode-with-aspose-barcode-in-python-step-by-step/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Python에서 Aspose.BarCode를 사용해 QR 바코드 만들기 – 단계별 가이드

Python에서 **QR 바코드**를 생성해야 할 때, 이 튜토리얼은 Aspose.BarCode 라이브러리를 이용한 전체 과정을 안내합니다. 제품 ID, 다국어 텍스트, 맞춤 데이터 등을 인코딩하는 방법을 확인하고, 확장된 코드텍스트를 구성하고, 시각 설정을 조정하며, 최종 이미지를 단일 실행 가능한 스크립트로 저장하는 방법을 배웁니다.

예제에서는 라이브러리 버전을 표시하는 방법도 보여주며, 이를 통해 호환 가능한 릴리스를 사용하고 있는지 확인할 수 있습니다. 이 가이드를 마치면 바로 사용할 수 있는 QR 바코드 이미지와 각 설정 옵션에 대한 명확한 이해를 얻을 수 있습니다.

## 사전 요구 사항

시작하기 전에 다음을 확인하세요:

- Python 3.8+ 설치
- `aspose-barcode` 패키지 (`pip install aspose-barcode` 로 설치)
- Python 문법에 대한 기본 지식
- PNG 파일이 저장될 출력 디렉터리에 대한 쓰기 권한

> **팁:** 다른 프로젝트와의 버전 충돌을 피하려면 가상 환경을 사용하는 것이 좋습니다.

## 1단계: Aspose.BarCode 라이브러리 버전 확인

라이브러리 버전을 표시하면 확장된 코드텍스트와 QR 인코딩을 지원하는 릴리스를 사용하고 있는지 확인할 수 있습니다.

```python
from asposebarcode import BuildVersionInfo

# Show the current Aspose.BarCode version
version_info = BuildVersionInfo()
print(
    f"Aspose.BarCode version: {version_info.PRODUCT} "
    f"{version_info.PRODUCT_MAJOR}.{version_info.PRODUCT_MINOR} "
    f"(released {version_info.RELEASE_DATE})"
)
```

**이것이 중요한 이유:**  
이전 릴리스에서는 혼합된 일반 텍스트와 ECI 세그먼트를 위한 `ExtCodetextBuilder` 클래스를 제공하지 않을 수 있습니다. 버전을 확인하면 이후 워크플로에서 런타임 오류를 방지할 수 있습니다.

## 2단계: 확장된 코드텍스트 문자열 만들기

확장된 코드텍스트를 사용하면 일반 ASCII 데이터와 유니코드(ECI) 세그먼트를 결합할 수 있어 다국어 QR 코드에 필수적입니다.

```python
from asposebarcode import ExtCodetextBuilder

# Initialize the builder
ext_builder = ExtCodetextBuilder()

# Add a plain segment – typically a product ID or numeric code
ext_builder.add_plain_codetext("ABC12345")

# Add an ECI segment – here we embed Japanese greeting "こんにちは"
# 26 is the ECI identifier for UTF‑8 encoding
ext_builder.add_eci_codetext(26, "こんにちは")

# Retrieve the full extended codetext that the QR generator will use
extended_codetext = ext_builder.get_extended_codetext()
print(f"Generated extended codetext: {extended_codetext}")
```

**이것이 중요한 이유:**  
`add_plain_codetext` 메서드는 데이터를 표준 ASCII로 저장하고, `add_eci_codetext`는 적절한 ECI 지정자를 앞에 붙여 유니코드 블록을 추가합니다. 이 방식은 QR 스캐너가 일본어 텍스트를 올바르게 해석하도록 하여 깨진 문자를 방지합니다.

### 일반적인 변형

- **다중 ECI 세그먼트:** 여러 언어를 혼합하려면 `add_eci_codetext`를 여러 번 호출합니다.
- **다른 ECI 식별자:** 대상 인코딩에 따라 `27`(ISO‑8859‑1), `28`(ISO‑8859‑2) 등을 사용합니다.

## 3단계: 확장된 코드텍스트로 QR 바코드 생성

올바르게 포맷된 문자열이 준비되었으니 QR 코드를 만들 수 있습니다.

```python
from asposebarcode import BarCodeGenerator, EncodeTypes, BarCodeImageFormat

# Create the QR generator with the extended codetext
qr_generator = BarCodeGenerator(EncodeTypes.QR, extended_codetext)
```

**이것이 중요한 이유:**  
`EncodeTypes.QR`은 Aspose.BarCode에 QR 심볼을 사용하도록 지시합니다. `extended_codetext`를 직접 전달하면 혼합된 데이터가 QR 매트릭스에 연결되어 일반 부분과 유니코드 부분이 모두 보존됩니다.

## 4단계: 시각적 외관 조정 (선택 사항이지만 권장)

바코드의 시각적 파라미터를 미세 조정하면 스캔 신뢰성이 향상되고 브랜드 가이드라인에 맞출 수 있습니다.

```python
# Set module (pixel) size – larger values increase overall image size
qr_generator.parameters.barcode.x_dimension = 4      # each module = 4 pixels

# Set border thickness – a thin white border helps scanners isolate the QR code
qr_generator.parameters.barcode.border_width = 2    # 2-pixel border
```

**이것이 중요한 이유:**  
- **`x_dimension`** 은 각 QR 모듈의 크기를 제어합니다. 너무 작으면 저해상도 장치에서 읽기 오류가 발생할 수 있습니다.  
- **`border_width`** 는 여백(quiet zone)을 추가합니다. 일부 스캐너는 최소 4모듈 여백을 요구하는데, 라이브러리가 자동으로 추가하지만 안전을 위해 늘릴 수 있습니다.

### 경계 상황 처리

- **고밀도 데이터:** 인코딩 데이터가 큰 경우 `x_dimension`을 늘리거나 `qr_generator.parameters.qr.error_correction_level`을 통해 더 높은 오류 정정 레벨을 선택해야 할 수 있습니다.  
- **투명 배경:** PNG에 알파 채널이 필요하면 `qr_generator.parameters.barcode.bg_color = Color.Transparent` 로 설정합니다.

## 5단계: QR 바코드 이미지 저장

마지막으로 선호하는 형식으로 디스크에 이미지를 저장합니다.

```python
# Define output path – replace YOUR_DIRECTORY with an actual folder
output_file = "YOUR_DIRECTORY/extended_qr.png"

# Save as PNG; other formats include JPEG, BMP, GIF, TIFF
qr_generator.save(output_file, BarCodeImageFormat.PNG)
print(f"Barcode saved to {output_file}")
```

**이것이 중요한 이유:**  
PNG로 저장하면 손실 없는 품질을 유지할 수 있어 선명한 가장자리가 필요한 QR 코드에 이상적입니다. 웹 애플리케이션에 다른 형식이 필요하면 `BarCodeImageFormat` 열거형을 변경하면 됩니다.

### 결과 확인

이미지 뷰어로 저장된 파일을 열어보세요. 스캔하면 결합된 문자열이 반환됩니다:

```
ABC12345
こんにちは
```

대부분의 최신 QR 스캐너 앱은 일반 세그먼트를 먼저 표시하고, 이어서 일본어 인사말을 올바르게 렌더링합니다.

---

## 전체 실행 가능한 스크립트

아래 전체 블록을 `create_qr_barcode.py` 라는 파일에 복사하고 `python create_qr_barcode.py` 로 실행하세요. `YOUR_DIRECTORY` 를 머신에서 쓰기 가능한 폴더로 변경하십시오.

```python
# create_qr_barcode.py
from asposebarcode import (
    BuildVersionInfo,
    ExtCodetextBuilder,
    BarCodeGenerator,
    EncodeTypes,
    BarCodeImageFormat,
)

# 1️⃣ Display library version
version_info = BuildVersionInfo()
print(
    f"Aspose.BarCode version: {version_info.PRODUCT} "
    f"{version_info.PRODUCT_MAJOR}.{version_info.PRODUCT_MINOR} "
    f"(released {version_info.RELEASE_DATE})"
)

# 2️⃣ Build extended codetext (plain + Japanese Unicode)
ext_builder = ExtCodetextBuilder()
ext_builder.add_plain_codetext("ABC12345")
ext_builder.add_eci_codetext(26, "こんにちは")
extended_codetext = ext_builder.get_extended_codetext()
print(f"Generated extended codetext: {extended_codetext}")

# 3️⃣ Create QR generator
qr_generator = BarCodeGenerator(EncodeTypes.QR, extended_codetext)

# 4️⃣ Optional visual tweaks
qr_generator.parameters.barcode.x_dimension = 4
qr_generator.parameters.barcode.border_width = 2

# 5️⃣ Save image
output_file = "YOUR_DIRECTORY/extended_qr.png"
qr_generator.save(output_file, BarCodeImageFormat.PNG)
print(f"Barcode saved to {output_file}")
```

이 스크립트를 실행하면 버전, 확장된 코드텍스트, PNG 파일 생성 확인 메시지가 출력됩니다.

---

## 결론

이제 Python에서 Aspose.BarCode를 사용해 **QR 바코드** 이미지를 만드는 방법을 알게 되었습니다. 이번 튜토리얼에서는 다음을 다루었습니다:

1. 라이브러리 버전 확인
2. 일반 텍스트와 ECI(유니코드) 세그먼트를 포함한 확장 코드텍스트 구축
3. QR 코드 생성
4. 모듈 크기와 여백 너비 같은 시각 파라미터 맞춤
5. PNG 형식으로 최종 이미지 저장

다음 단계로 탐색할 내용:

- 오류 정정 레벨 변경 (`qr_generator.parameters.qr.error_correction_level`)
- 로고 또는 배경 이미지 추가 (`qr_generator.parameters.qr.logo`)
- SVG와 같은 다른 포맷으로 내보내기(확장 가능한 웹 그래픽)
- Flask 또는 Django 엔드포인트에 통합해 실시간 QR 생성 구현

다양한 데이터 페이로드와 시각 설정을 실험해 애플리케이션의 브랜드와 스캔 요구 사항에 맞추세요. 즐거운 코딩 되세요!

## 다음에 배워야 할 내용

다음 튜토리얼들은 이 가이드에서 다룬 기술을 기반으로 하며, 추가 API 기능을 마스터하고 프로젝트에 다양한 구현 방식을 적용하는 데 도움이 됩니다.

- [Aspose.BarCode for .NET에서 dotcode 확장 코드텍스트 만들기](/barcode/english/net/dotcode-barcode-configuration/dotcode-extended-code-text-configuration/)
- [Aspose.BarCode for .NET에서 DataMatrix 코드 텍스트 구성](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-extended-code-text-configuration/)
- [Aspose.BarCode for .NET에서 ITF-14 바코드 Quiet Zone 설정](/barcode/english/net/itf-14-barcode-customization/itf-14-barcode-quiet-zone-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}