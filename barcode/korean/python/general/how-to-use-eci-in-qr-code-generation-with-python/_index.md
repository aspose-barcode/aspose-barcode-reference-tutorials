---
category: general
date: 2026-11-20
description: Python 바코드 라이브러리를 사용하여 ECI 사용 방법, 텍스트에서 QR 생성, 빌더 초기화, QR 이미지 저장 방법을
  배웁니다.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to use eci
- generate qr from text
- how to clear builder
- save qr image
- clear qr builder
language: ko
lastmod: 2026-11-20
og_description: ECI를 사용하여 텍스트에서 QR을 생성하고, QR 빌더를 초기화하며, QR 이미지를 저장하는 방법 – 완벽한 단계별
  가이드.
og_image_alt: Diagram illustrating how to use ECI to generate a QR code and save the
  QR image
og_title: Python으로 QR 코드 생성 시 ECI 사용 방법
schemas:
- author: Aspose
  dateModified: '2026-11-20'
  description: Learn how to use ECI, generate QR from text, clear the builder, and
    save QR image using the Python barcode library.
  headline: How to use ECI in QR code generation with Python
  type: TechArticle
tags:
- QR code
- Python
- barcode
- ECI
title: Python을 사용한 QR 코드 생성에서 ECI 사용 방법
url: /ko/python/general/how-to-use-eci-in-qr-code-generation-with-python/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Python으로 QR 코드 생성 시 ECI 사용 방법

QR 코드를 생성할 때 **how to use eci**가 필요하다면, 이 가이드는 정확한 단계들을 보여줍니다. 텍스트에서 QR을 생성하고, 빌더를 초기화하며, 마지막으로 QR 이미지를 저장하는 방법을 몇 줄의 Python 코드로 확인할 수 있습니다.

다국어 데이터를 포함하는 QR 코드는 스캐너가 적용할 문자 집합을 알 수 있도록 Extended Channel Interpretation (ECI) 세그먼트가 필요합니다. 이 튜토리얼에서는 확장된 코덱텍스트를 구성하고, 재사용 시 빌더를 초기화하며, 결과를 PNG 파일로 저장하는 과정을 단계별로 안내합니다.

## 사전 요구 사항

시작하기 전에 다음이 준비되어 있어야 합니다:

- Python 3.8+이 설치되어 있어야 합니다.
- Aspose.BarCode for Python via .NET 패키지(또는 `ExtCodetextBuilder`와 `BarcodeGenerator`를 제공하는 호환 가능한 `barcode` 라이브러리).
- QR 코드 개념에 대한 기본적인 이해.

pip으로 라이브러리를 설치합니다:

```bash
pip install aspose-barcode
```

> **Pro tip:** 버전 충돌을 피하기 위해 가상 환경을 사용하세요.

## 1단계: 필요한 클래스 가져오기

주로 사용할 클래스는 확장 코덱텍스트를 구성하는 `ExtCodetextBuilder`와 QR 코드를 렌더링하는 `BarcodeGenerator`입니다.

```python
from aspose.barcode import barcode
from aspose.barcode.generation import ExtCodetextBuilder
```

이러한 임포트를 통해 빌더 메서드(`add_plain_codetext`, `add_eci_codetext` 등)와 생성기의 `set_code_text`, `set_symbology`, `save` 함수를 사용할 수 있습니다.

## 2단계: ExtCodetextBuilder 생성 및 구성

새 빌더 인스턴스를 만드는 것은 **how to use eci**의 첫 번째 구체적인 예시입니다. 필요에 따라 나중에 빌더를 초기화하여 재사용할 수도 있습니다.

```python
# Create an ExtCodetextBuilder instance
extended_text_builder = ExtCodetextBuilder()

# Optional: clear any previous items (useful when reusing the same builder)
extended_text_builder.clear()   # this demonstrates how to clear builder
```

`clear()`를 호출하면 빌더가 깨끗한 상태에서 시작되므로, 루프 내에서 여러 QR 코드를 생성할 때 필수적입니다.

## 3단계: 일반(비‑ECI) 코덱텍스트 추가

일반 텍스트는 ECI 세그먼트가 필요하지 않습니다. ASCII 호환 문자열에는 `add_plain_codetext`를 사용합니다.

```python
# Add plain codetext (e.g., an English phrase)
extended_text_builder.add_plain_codetext("HelloWorld")
```

이제 빌더는 일반 세그먼트 `"HelloWorld"`를 보유하고 있습니다.

## 4단계: ECI‑인코딩 세그먼트 추가

여기가 **how to use eci**의 핵심입니다: ECI 값(UTF‑8은 26)을 지정하고 인코딩하려는 유니코드 문자열을 제공합니다. 이를 통해 QR 코드가 기본 ISO‑8859‑1 집합에 포함되지 않은 러시아어, 중국어 등 다양한 언어를 담을 수 있습니다.

```python
# Add ECI‑encoded codetext (ECI value 26 = UTF‑8, Russian “Hello”)
extended_text_builder.add_eci_codetext(26, "Привет")
```

> **Why this matters:** ECI 표시가 없으면 스캐너가 기본 문자 집합으로 바이트를 해석하여 비‑ASCII 텍스트가 깨진 문자로 표시됩니다.

## 5단계: 결합된 확장 코덱텍스트 문자열 가져오기

필요한 모든 세그먼트를 추가한 후, QR 생성기에 전달할 최종 문자열을 가져옵니다.

```python
combined_extended_text = extended_text_builder.get_extended_codetext()
print("Extended codetext:", combined_extended_text)
```

출력값은 대략 다음과 같습니다:

```
Extended codetext: [ECI26]ПриветHelloWorld
```

정확한 형식은 라이브러리에 따라 다르지만, 중요한 점은 ECI 마커(`[ECI26]`)가 UTF‑8 페이로드 앞에 위치한다는 것입니다.

## 6단계: 결합된 텍스트를 사용해 QR 코드 생성

이제 **generate QR from text**를 수행하려면 확장 코덱텍스트를 `BarcodeGenerator`에 전달하면 됩니다.

```python
# Initialize the QR generator
qr_generator = barcode.generation.BarcodeGenerator()

# Assign the combined extended codetext
qr_generator.set_code_text(combined_extended_text)

# Choose QR symbology (the library supports many, QR is the most common)
qr_generator.set_symbology(barcode.Symbology.QR)

# Save the QR image to disk – this demonstrates how to save QR image
output_path = "qr_extended.png"
qr_generator.save(output_path)

print(f"QR code saved to {output_path}")
```

`qr_extended.png`를 열면 일반 영어 문자열과 러시아어 인사말을 모두 인코딩한 QR 코드가 나타납니다. 최신 QR 스캐너로 스캔하면 “HelloWorld”와 “Привет”가 올바르게 표시됩니다.

### 빌더를 재사용하기 전에 `clear()`를 호출해야 하는 이유

루프에서 여러 QR 코드를 생성할 경우, 빌더를 초기화하지 않으면 이전 세그먼트가 새 세그먼트와 연결되어 잘못된 코드가 만들어집니다. 간단한 패턴은 다음과 같습니다:

```python
for text, eci, unicode_str in data_set:
    extended_text_builder.clear()                       # ensures a fresh start
    extended_text_builder.add_plain_codetext(text)
    extended_text_builder.add_eci_codetext(eci, unicode_str)
    qr_generator.set_code_text(extended_text_builder.get_extended_codetext())
    qr_generator.save(f"qr_{text}.png")
```

이 스니펫은 **how to clear builder**와 **how to generate QR from text**를 반복해서 수행하는 방법을 보여줍니다.

## 엣지 케이스 및 일반적인 함정

| 상황 | 주의할 점 | 대처 방법 |
|-----------|-------------------|---------------|
| **지원되지 않는 ECI 값** | 라이브러리가 `InvalidArgumentException`을 발생시킵니다. | 사양에 명시된 ECI 값만 사용하세요(예: UTF‑8은 26, Shift‑JIS는 20). |
| **매우 긴 결합 텍스트** | QR 버전이 최대 용량을 초과할 수 있습니다. | QR 버전을 자동으로 증가시키세요(`qr_generator.set_qr_version(QRVersion.AUTO)`) 또는 데이터를 여러 QR 코드로 나누세요. |
| **파일 시스템 권한 오류** | `save`가 `IOError`와 함께 실패합니다. | 대상 디렉터리가 존재하고 프로세스에 쓰기 권한이 있는지 확인하세요. |
| **잘못된 문자셋 표시** | 스캐너가 깨진 문자를 표시합니다. | 올바른 ECI 값이 문자열의 실제 인코딩과 일치하는지 확인하세요. |

## 전체 실행 가능한 예제

아래는 복사·붙여넣기만으로 바로 실행할 수 있는 독립형 스크립트입니다. 모든 임포트, 오류 처리, 주석이 포함되어 있어 이해하기 쉽습니다.

```python
# qr_eci_example.py
# Demonstrates how to use ECI, generate QR from text, clear the builder,
# and save QR image using Aspose.BarCode for Python.

from aspose.barcode import barcode
from aspose.barcode.generation import ExtCodetextBuilder
import os

def generate_qr(plain_text: str, eci_value: int, unicode_text: str, out_file: str):
    """
    Creates a QR code that contains both plain and ECI‑encoded text.
    Parameters:
        plain_text – ASCII‑compatible string.
        eci_value  – Numeric ECI identifier (e.g., 26 for UTF‑8).
        unicode_text – Text that requires the specified ECI.
        out_file – Destination file path for the PNG image.
    """
    # Step 1: instantiate and clear the builder
    builder = ExtCodetextBuilder()
    builder.clear()                       # how to clear builder

    # Step 2: add segments
    builder.add_plain_codetext(plain_text)
    builder.add_eci_codetext(eci_value, unicode_text)

    # Step 3: retrieve combined text
    combined = builder.get_extended_codetext()
    print("Combined extended codetext:", combined)

    # Step 4: generate QR code
    generator = barcode.generation.BarcodeGenerator()
    generator.set_code_text(combined)
    generator.set_symbology(barcode.Symbology.QR)

    # Ensure output directory exists
    os.makedirs(os.path.dirname(out_file), exist_ok=True)

    # Step 5: save QR image – how to save QR image
    generator.save(out_file)
    print(f"QR code saved as {out_file}")

if __name__ == "__main__":
    # Example usage
    generate_qr(
        plain_text="HelloWorld",
        eci_value=26,               # UTF‑8
        unicode_text="Привет",      # Russian "Hello"
        out_file="output/qr_extended.png"
    )
```

이 스크립트를 실행하면 `output/qr_extended.png`가 생성되며, 영어와 러시아어 텍스트를 모두 올바르게 인코딩한 QR 코드가 저장됩니다.

## 결론

이제 QR 코드를 만들 때 **how to use eci**를 적용하는 방법, 재사용 전에 **clear the QR builder**를 수행하는 방법, **generate QR from text**를 수행하는 방법, 그리고 Python으로 **save QR image**하는 정확한 단계를 알게 되었습니다. 위 패턴을 따르면 빌더 상태를 예측 가능하게 유지하면서 어떤 유니코드 문자열이든 QR 코드에 삽입할 수 있습니다.

### 다음 단계

- 중국어(ECI 20)나 ISO‑8859‑5와 같은 다른 언어에 대한 ECI 값을 탐색해 보세요.
- 오류 정정 수준(`qr_generator.set_error_correction_level`)을 조정하여 스캔 신뢰성을 향상시키세요.
- 혼합 언어 메시지를 위해 하나의 QR에 여러 ECI 세그먼트를 결합해 보세요.

행복한 코딩 되시고, 다국어 QR 코드를 만드는 즐거움을 누리세요!

## 다음에 배울 내용은?

다음 튜토리얼들은 이 가이드에서 시연한 기술을 기반으로 하는 밀접한 주제를 다룹니다. 각 자료에는 완전한 코드 예제와 단계별 설명이 포함되어 있어 추가 API 기능을 마스터하고 프로젝트에 다양한 구현 방식을 적용하는 데 도움이 됩니다.

- [Aspose.Barcode Python을 사용해 ECI가 포함된 바코드 생성 방법](/barcode/english/python/general/how-to-generate-barcode-with-eci-using-aspose-barcode-python/)
- [Aspose.Barcode을 사용해 Python에서 QR 코드 이미지 생성 – 전체 가이드](/barcode/english/python/general/how-to-generate-qr-code-image-in-python-with-aspose-barcode/)
- [Python에서 바코드 생성 – 완전 단계별 가이드](/barcode/english/python-java/general/how-to-generate-barcode-in-python-complete-step-by-step-guid/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}