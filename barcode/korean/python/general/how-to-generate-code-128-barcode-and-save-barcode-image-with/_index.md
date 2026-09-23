---
category: general
date: 2026-09-23
description: Python에서 Aspose.BarCode를 사용하여 Code 128 바코드를 생성하고 바코드 이미지를 저장하는 방법을 단계별로
  배워보세요.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate code 128 barcode
- save barcode image
- Aspose.BarCode Python
- extended codetext builder
- barcode PNG export
language: ko
lastmod: 2026-09-23
og_description: Python에서 Aspose.BarCode를 사용해 Code 128 바코드를 생성하고 바코드 이미지를 저장합니다. 이
  완전한 예제를 따라 바코드를 만들고, 맞춤 설정한 뒤 PNG 파일로 내보내세요.
og_image_alt: Python-generated Code 128 barcode saved as PNG image
og_title: Code 128 바코드 생성 및 바코드 이미지 저장 – Python 가이드
schemas:
- author: Aspose
  dateModified: '2026-09-23'
  description: Learn how to generate Code 128 barcode and save barcode image using
    Aspose.BarCode in Python – step‑by‑step guide.
  headline: How to generate Code 128 barcode and save barcode image with Aspose.BarCode
  type: TechArticle
tags:
- barcode
- Code 128
- Python
- Aspose
title: Aspose.BarCode를 사용하여 Code 128 바코드를 생성하고 바코드 이미지를 저장하는 방법
url: /ko/python/general/how-to-generate-code-128-barcode-and-save-barcode-image-with/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Code 128 바코드 생성 및 Aspose.BarCode으로 바코드 이미지 저장 방법

Python 프로젝트에서 **Code 128 바코드 생성** 및 **바코드 이미지 저장**이 필요하다면, 이 튜토리얼에서 정확한 단계들을 보여줍니다. Aspose.BarCode의 `ExtCodetextBuilder`를 사용하면 일반 텍스트와 유니코드 세그먼트를 하나의 페이로드에 삽입하고, 결과를 PNG 파일로 렌더링할 수 있습니다.

전체 실행 가능한 스크립트와 각 라인에 대한 설명, ECI 인코딩 처리나 올바른 출력 폴더 선택과 같은 일반적인 함정에 대한 팁을 확인할 수 있습니다. 외부 문서는 필요하지 않으며, 복사·붙여넣기만 하면 바로 실행할 수 있습니다.

## 사전 요구 사항

* Python 3.8+이 설치되어 있어야 합니다.
* `aspose.barcode` 패키지(`pip install aspose-barcode`로 설치).
* PNG가 저장될 디렉터리에 대한 쓰기 권한.

이 코드는 Aspose.BarCode이 지원하는 모든 심볼에 대해 작동하지만, 예제는 **Code 128**에 중점을 둡니다. 이는 알파벳·숫자 데이터를 효율적으로 인코딩하고 확장 문자 집합을 지원하기 때문입니다.

## 1단계: 필요한 클래스 가져오기

```python
import barcode                     # Core Aspose.BarCode namespace
from barcode import BarCodeWriter, BarCodeEncodeMode, BarCodeImageFormat
from barcode import ExtCodetextBuilder, BuildVersionInfo
```

*왜 이 단계인가?* 클래스를 가져오면 확장 코덱텍스트용 빌더, 이미지를 생성하는 라이터, 그리고 라이브러리 업데이트 디버깅에 유용할 수 있는 버전 헬퍼에 접근할 수 있습니다.

## 2단계: 확장 코덱텍스트 구축

```python
# Create a builder for extended codetext
builder = ExtCodetextBuilder()

# Add plain text (no ECI) – this part is simple ASCII
builder.add_plain_codetext("ABC123")

# Add a Unicode segment with ECI 0x03 (UTF‑8). The word “Пример” means “Example” in Russian.
builder.add_eci_codetext(0x03, "Пример")

# Retrieve the full extended codetext string
extended_codetext = builder.get_extended_codetext()
print("Extended codetext:", extended_codetext)
```

`ExtCodetextBuilder`를 사용하면 일반 ASCII와 유니코드 데이터를 하나의 바코드 페이로드에 혼합할 수 있습니다. ECI(Extended Channel Interpretation) 바이트 `0x03`은 스캐너에 뒤따르는 바이트가 UTF‑8 인코딩임을 알려주며, 이는 러시아어, 중국어, 아랍어와 같은 언어에 필수적입니다.

## 3단계: Code 128용 바코드 라이터 구성

```python
writer = BarCodeWriter()
writer.encode_type = BarCodeEncodeMode.CODE_128   # Choose Code 128 symbology
writer.code_text = extended_codetext
```

`encode_type`을 `CODE_128`으로 설정하면 라이터가 **Code 128 바코드**를 렌더링하도록 지시합니다. `code_text` 속성은 이전 단계에서 만든 확장 문자열을 받습니다.

## 4단계: 바코드 이미지를 PNG로 저장

```python
output_path = "YOUR_DIRECTORY/extended_codetext.png"
writer.save(output_path, BarCodeImageFormat.PNG)
print(f"Barcode image saved to {output_path}")
```

`save` 메서드는 바코드를 파일에 기록합니다. `BarCodeImageFormat.PNG`를 사용하면 무손실 압축과 웹·모바일 애플리케이션에서의 폭넓은 호환성을 보장합니다.

## 5단계 (선택): Aspose.BarCode 라이브러리 버전 확인

```python
version_info = BuildVersionInfo()
print("Assembly version :", version_info.ASSEMBLY_VERSION)
print("Product version   :", f"{version_info.PRODUCT_MAJOR}.{version_info.PRODUCT_MINOR}")
print("Release date      :", version_info.RELEASE_DATE)
```

정확한 라이브러리 버전을 알면 버그를 보고하거나 릴리즈 간 동작을 비교할 때 도움이 됩니다.

## 예상 출력

스크립트를 실행하면 다음과 같은 콘솔 출력이 나타납니다:

```
Extended codetext: ABC123[ECI=03]Пример
Assembly version : 23.12.0.0
Product version   : 23.12
Release date      : 2023-12-01
Barcode image saved to YOUR_DIRECTORY/extended_codetext.png
```

생성된 PNG(`extended_codetext.png`)는 다음과 같습니다:

![Python으로 생성된 Code 128 바코드 PNG 이미지](images/code128_extended.png)

*이미지는 ASCII 문자열 `ABC123`와 러시아어 단어 “Пример”를 모두 인코딩한 Code 128 바코드를 보여줍니다.*

## 일반적인 질문 및 엣지 케이스 처리

| Question | Answer |
|----------|--------|
| **다른 심볼을 사용할 수 있나요?** | 예. `BarCodeEncodeMode.CODE_128`을 `QR`, `EAN_13`, `PDF_417` 등 지원되는 다른 모드로 교체하면 됩니다. |
| **Unicode 텍스트에 이모지가 포함되어 있으면 어떻게 하나요?** | 이모지도 UTF‑8 문자이므로 동일한 `add_eci_codetext` 호출이 작동합니다. 대상 스캐너가 사용한 ECI를 지원하는지 확인하세요. |
| **이미지 크기를 어떻게 변경하나요?** | `save` 호출 전에 `writer.x_dimension` 및 `writer.bar_height`를 설정합니다. |
| **`output_path`에 어떤 폴더를 사용해야 하나요?** | Python 프로세스가 쓸 수 있는 모든 폴더면 됩니다. `os.makedirs`에 `exist_ok=True`를 지정해 자동으로 생성하도록 하세요. |

## 전문가 팁

* **경로를 하드코딩하지 마세요.** `os.path.join`과 `pathlib` 모듈의 `Path`를 사용해 크로스 플랫폼 호환성을 확보하세요.
* **바코드를 검증하세요.** 저장 후 `barcode.BarCodeReader`로 이미지를 다시 읽어 인코딩된 텍스트가 `extended_codetext`와 일치하는지 확인할 수 있습니다.
* **성능 팁.** 루프에서 많은 바코드를 생성할 경우, 하나의 `BarCodeWriter` 인스턴스를 재사용하고 각 반복마다 `code_text`만 업데이트하세요.

## 결론

이제 Python에서 Aspose.BarCode을 사용해 ASCII와 Unicode 데이터를 혼합한 **Code 128 바코드 생성** 및 **바코드 이미지를 PNG로 저장**하는 방법을 알게 되었습니다. 전체 스크립트는 확장 코덱텍스트 구축, 라이터 구성, 이미지 내보내기, 라이브러리 버전 확인을 포함합니다.

여기서부터는 다음을 탐색할 수 있습니다:

* 전경/배경 색상 추가(`writer.back_color`, `writer.fore_color`).
* `Aspose.PDF`를 사용해 PDF에 바코드 삽입.
* `BarCodeReader` 클래스를 사용해 저장된 이미지를 디코딩하고 내용을 자동으로 검증.

코딩을 즐기세요, 그리고 다른 심볼 및 이미지 포맷을 자유롭게 실험해 보세요!

## 다음에 배울 내용은?

다음 튜토리얼은 이 가이드에서 시연한 기술을 기반으로 하는 밀접한 관련 주제를 다룹니다. 각 자료는 단계별 설명과 함께 완전한 동작 코드를 제공하여 추가 API 기능을 마스터하고 프로젝트에서 대체 구현 방식을 탐색하도록 돕습니다.

- [Aspose.Barcode Python으로 Code128 바코드 생성 – 전체 가이드](/barcode/english/python/general/generate-code128-barcode-with-aspose-barcode-python-full-gui/)
- [Python에서 바코드 생성 방법 – 완전 단계별 가이드](/barcode/english/python-java/general/how-to-generate-barcode-in-python-complete-step-by-step-guid/)
- [Aspose.Barcode를 사용한 Python QR 코드 이미지 생성 – 전체 가이드](/barcode/english/python/general/how-to-generate-qr-code-image-in-python-with-aspose-barcode/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}