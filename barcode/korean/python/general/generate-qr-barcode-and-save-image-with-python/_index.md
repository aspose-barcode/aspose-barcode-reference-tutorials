---
category: general
date: 2026-11-27
description: Aspose.Barcode를 사용하여 Python에서 QR 바코드를 생성하고 바코드 이미지를 빠르게 디스크에 저장하는 방법을
  배우세요.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate QR barcode
- save barcode image
- Aspose.Barcode Python
- extended codetext QR
- barcode version information
language: ko
lastmod: 2026-11-27
og_description: Aspose.Barcode를 사용하여 Python에서 QR 바코드를 생성하고 즉시 바코드 이미지를 저장합니다. QR 코드를
  만들고, 맞춤화하고, 저장하는 전체 예제를 따라보세요.
og_image_alt: Screenshot of a generated QR barcode created with Python
og_title: Python으로 QR 바코드 생성 및 이미지 저장 – 단계별 가이드
schemas:
- author: Aspose
  dateModified: '2026-11-27'
  description: Generate QR barcode in Python using Aspose.Barcode and learn how to
    save barcode image to disk quickly.
  headline: Generate QR barcode and save image with Python
  type: TechArticle
tags:
- QR code
- Python
- Aspose
- Barcode generation
title: Python으로 QR 바코드 생성 및 이미지 저장
url: /ko/python/general/generate-qr-barcode-and-save-image-with-python/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Python으로 QR 바코드 생성 및 이미지 저장

Python 애플리케이션에서 **QR 바코드 생성**이 필요하다면, 이 가이드는 Aspose.Barcode 라이브러리를 사용하여 수행하는 방법을 보여줍니다. 또한 **바코드 이미지 저장**을 로컬 폴더에 올바르게 하는 방법, 라이브러리 버전 정보를 조회하는 방법, 확장된 코드텍스트 세그먼트를 처리하는 방법을 배울 수 있습니다.

QR 코드를 만드는 것은 티켓팅 시스템, 모바일 결제, 제품 추적 등에서 흔히 요구됩니다. 이 튜토리얼을 마치면 QR 바코드 이미지 파일을 생성하고 디버깅 또는 규정 준수를 위해 버전 정보를 출력하는 준비된 스크립트를 얻게 됩니다.

## 사전 요구 사항

시작하기 전에 다음이 준비되어 있는지 확인하세요:

* Python 3.8 이상이 설치되어 있어야 합니다.
* `aspose-barcode` 패키지. `pip install aspose-barcode` 로 설치합니다.
* 바코드 이미지가 저장될 디렉터리에 대한 쓰기 권한.

추가 외부 서비스는 필요하지 않으며, 전체 과정은 로컬에서 실행됩니다.

## 1단계: `ExtCodetextBuilder` 로 확장된 코드텍스트 구축

확장된 코드텍스트를 사용하면 단일 QR 코드에 일반 텍스트와 ECI(Extended Channel Interpretation) 세그먼트를 혼합할 수 있습니다. 이는 유로 기호와 같이 서로 다른 문자 집합의 문자를 삽입해야 할 때 유용합니다.

```python
import aspose.barcode as bc
from aspose.barcode.generation import ExtCodetextBuilder, BuildVersionInfo

# Create the builder instance
ext_builder = ExtCodetextBuilder()

# Add a plain text segment
ext_builder.add_plain_codetext("ABC123")

# Add an ECI segment that uses ISO‑IEC 8859‑1 (code page 3)
ext_builder.add_eci_codetext(3, "€123")
```

**이 단계가 중요한 이유:**  
`ExtCodetextBuilder`는 QR 인코더가 처리할 최종 문자열을 조립합니다. 확장된 코드텍스트를 구축하지 않으면 바코드에 일반 ASCII 문자만 포함되어 로케일‑특정 기호를 표현할 수 없습니다.

## 2단계: 결합된 확장 코드텍스트 문자열 조회

```python
# Get the final extended codetext that will be encoded
extended_codetext = ext_builder.get_extended_codetext()
print("Extended codetext:", extended_codetext)
```

출력 예시:

```
Extended codetext: ABC123[ECI3]€123
```

대괄호 안의 `[ECI3]` 마커는 QR 인코더에게 뒤따르는 문자에 대해 지정된 문자 집합으로 전환하도록 지시합니다.

## 3단계: 확장된 코드텍스트를 사용해 QR 바코드 생성

```python
# Create a QR barcode generator with the extended codetext
barcode = bc.BarcodeGenerator(bc.EncodeTypes.QR, extended_codetext)
```

**설명:**  
`BarcodeGenerator`는 두 개의 인수를 받습니다: 바코드 유형(`QR`)과 인코딩할 데이터(`extended_codetext`). 생성기는 렌더링에 필요한 모든 내부 구조를 준비합니다.

## 4단계: 생성된 바코드 이미지 저장

```python
# Define the output path – adjust the folder as needed
output_path = "output/qr_extended.png"

# Save the image in PNG format
barcode.save(output_path)
print(f"Barcode image saved to {output_path}")
```

**이 접근 방식을 사용해야 하는 이유:**  
`save` 를 직접 호출하면 파일 확장자를 기반으로 형식을 추론하여 이미지를 디스크에 기록합니다. 이 메서드는 PNG, JPEG, BMP, TIFF 를 지원하므로 다양한 다운스트림 소비자에게 유연성을 제공합니다.

### 저장된 이미지 확인

이미지 뷰어로 `output/qr_extended.png` 파일을 열어보세요. 스캔하면 문자열 `ABC123€123` 이 반환되는 QR 코드를 확인할 수 있습니다. 대부분의 최신 모바일 QR 스캐너는 ECI 세그먼트를 자동으로 처리합니다.

## 5단계: Aspose.BarCode 버전 정보 조회 (선택 사항이지만 유용)

Aspose.BarCode 라이브러리의 정확한 버전을 알면 버그를 보고하거나 호환성을 확인할 때 도움이 됩니다.

```python
# Retrieve version details
version_info = BuildVersionInfo()
print("Aspose.BarCode version:")
print(f"  Assembly version : {version_info.ASSEMBLY_VERSION}")
print(f"  File version     : {version_info.FILE_VERSION}")
print(f"  Product          : {version_info.PRODUCT}")
print(f"  Release date     : {version_info.RELEASE_DATE}")
```

일반적인 출력 예시:

```
Aspose.BarCode version:
  Assembly version : 23.9.0.0
  File version     : 23.9.0
  Product          : Aspose.BarCode for Python via .NET
  Release date     : 2023-09-15
```

## 전체 스크립트 – 복사·붙여넣기 후 실행

```python
import aspose.barcode as bc
from aspose.barcode.generation import ExtCodetextBuilder, BuildVersionInfo

# 1️⃣ Build extended codetext
ext_builder = ExtCodetextBuilder()
ext_builder.add_plain_codetext("ABC123")
ext_builder.add_eci_codetext(3, "€123")
extended_codetext = ext_builder.get_extended_codetext()
print("Extended codetext:", extended_codetext)

# 2️⃣ Generate QR barcode
barcode = bc.BarcodeGenerator(bc.EncodeTypes.QR, extended_codetext)

# 3️⃣ Save barcode image
output_path = "output/qr_extended.png"
barcode.save(output_path)
print(f"Barcode image saved to {output_path}")

# 4️⃣ Display version information
version_info = BuildVersionInfo()
print("Aspose.BarCode version:")
print(f"  Assembly version : {version_info.ASSEMBLY_VERSION}")
print(f"  File version     : {version_info.FILE_VERSION}")
print(f"  Product          : {version_info.PRODUCT}")
print(f"  Release date     : {version_info.RELEASE_DATE}")
```

스크립트를 실행하면 QR 코드 이미지가 생성되고 콘솔에 확장된 코드텍스트와 버전 상세 정보가 모두 출력됩니다.

## 일반적인 변형 및 예외 상황

| 상황 | 권장 조정 |
|-----------|------------------------|
| **다른 문자 집합** | `add_eci_codetext` 에 전달하는 ECI 식별자를 변경합니다. UTF‑8 은 `5` 를 사용합니다. |
| **높은 오류 정정 수준** | `save` 호출 전에 `barcode.parameters.barcode.qr_error_level = bc.QRErrorLevel.H` 로 설정합니다. |
| **맞춤 이미지 크기** | `barcode.parameters.image_width` 와 `barcode.parameters.image_height` 로 픽셀 크기를 제어합니다. |
| **PNG가 아닌 출력** | `output_path` 의 파일 확장자를 `.jpg` 혹은 `.bmp` 로 변경합니다. 라이브러리가 자동으로 올바른 인코더를 선택합니다. |

## 전문가 팁

* **출력 폴더를 프로그래밍 방식으로 생성** (존재하지 않을 경우):

  ```python
  import os
  os.makedirs(os.path.dirname(output_path), exist_ok=True)
  ```

* **생성 후 QR 코드 검증** 은 `aspose.barcode.BarcodeReader` 로 다시 읽어 수행합니다. 이는 특히 ECI 세그먼트를 사용할 때 인코딩된 데이터가 기대와 일치하는지 확인하는 데 도움이 됩니다.

  ```python
  reader = bc.BarcodeReader(output_path, bc.DecodeType.QR)
  for result in reader.read():
      print("Decoded text:", result.code_text)
  ```

* **성능 팁** – 루프에서 다수의 QR 코드를 생성해야 할 경우 단일 `BarcodeGenerator` 인스턴스를 재사용하세요. 각 반복마다 새 객체를 만들지 말고 `code_text` 속성을 재설정합니다.

## 결론

이제 Aspose.Barcode을 사용해 Python에서 **QR 바코드 생성** 방법, 일반 텍스트와 ECI 세그먼트를 혼합한 확장된 코드텍스트 구축 방법, 그리고 **바코드 이미지 저장**을 올바르게 수행하는 방법을 알게 되었습니다. 또한 문제 해결을 위해 라이브러리 버전 정보를 조회하는 방법도 확인했습니다.

다음 단계로 시도해 볼 수 있는 내용:

* QR 코드에 로고 오버레이 또는 맞춤 색상 추가
* Aspose.PDF 를 사용해 QR 바코드를 PDF에 직접 삽입
* 대규모 데이터셋에 대한 배치 생성 자동화

다양한 데이터 페이로드, 오류 정정 수준, 이미지 형식을 실험해 보세요. 즐거운 코딩 되세요!


## 다음에 배워야 할 내용은 무엇인가요?


다음 튜토리얼은 이 가이드에서 시연한 기술을 기반으로 하여 밀접하게 관련된 주제를 다룹니다. 각 리소스는 단계별 설명과 완전한 코드 예제를 포함하고 있어 추가 API 기능을 마스터하고 프로젝트에 적용할 수 있는 다양한 구현 방식을 탐색하는 데 도움이 됩니다.

- [Python에서 Aspose.Barcode으로 QR 코드 이미지 생성 – 전체 가이드](/barcode/english/python/general/how-to-generate-qr-code-image-in-python-with-aspose-barcode/)
- [Code 128 바코드 생성 및 이미지 저장 with Aspose.BarCode](/barcode/english/python/general/how-to-generate-code-128-barcode-and-save-barcode-image-with/)
- [Python에서 Aspose.BarCode으로 DataMatrix 바코드 생성](/barcode/english/python/general/how-to-generate-datamatrix-barcode-in-python-with-aspose-bar/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}