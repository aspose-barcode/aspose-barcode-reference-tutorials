---
category: general
date: 2026-07-18
description: extcodetextbuilder aspose를 사용하여 일반 ASCII와 UTF‑8 러시아어 텍스트를 결합한 QR 코드를
  생성합니다. Python에서 Aspose.Barcode QR 코드 생성을 배워보세요.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- use extcodetextbuilder aspose
- Aspose.Barcode
- ECI encoding
- QR Code generation
- mixed codetext
language: ko
lastmod: 2026-07-18
og_description: extcodetextbuilder aspose를 사용하면 QR 코드에서 일반 텍스트와 UTF‑8 인코딩된 조각을 혼합할
  수 있습니다. Python용 Aspose.Barcode 단계별 가이드를 따라보세요.
og_image_alt: use extcodetextbuilder aspose QR code example showing mixed ECI text
og_title: extcodetextbuilder aspose 사용 – 혼합 ECI 텍스트로 QR 코드 만들기
schemas:
- author: Aspose
  dateModified: '2026-07-18'
  description: use extcodetextbuilder aspose to create QR codes that combine plain
    ASCII and UTF‑8 Russian text. Learn Aspose.Barcode QR Code generation in Python.
  headline: 'use extcodetextbuilder aspose: Generate QR Codes with Mixed ECI Text'
  type: TechArticle
- description: use extcodetextbuilder aspose to create QR codes that combine plain
    ASCII and UTF‑8 Russian text. Learn Aspose.Barcode QR Code generation in Python.
  name: 'use extcodetextbuilder aspose: Generate QR Codes with Mixed ECI Text'
  steps:
  - name: What if my scanner doesn’t recognize the Cyrillic part?
    text: Make sure the scanning app advertises ECI support. Older hardware may ignore
      the ECI segment and treat the bytes as ISO‑8859‑1, resulting in garbled characters.
  - name: Can I add more than two fragments?
    text: Absolutely. Call `add_plain_codetext` or `add_eci_codetext` as many times
      as you need. The builder will concatenate them in the order you invoke the methods.
  - name: How do I change the QR Code size or foreground color?
    text: 'Use the `qr_generator.parameters` object:'
  - name: Is there a way to embed binary data (e.g., a small file) alongside text?
    text: Yes. Use `add_binary_codetext` with a byte array, and pair it with an appropriate
      ECI if the binary represents a specific character set. The builder will handle
      the necessary mode switches.
  type: HowTo
tags:
- barcode
- Aspose
- Python
- QR Code
- ECI
title: 'extcodetextbuilder aspose 사용: 혼합 ECI 텍스트로 QR 코드 생성'
url: /ko/python/general/use-extcodetextbuilder-aspose-generate-qr-codes-with-mixed-e/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# extcodetextbuilder aspose 사용 – 혼합 ECI 텍스트 QR 코드 만들기

단일 QR 코드에 일반 영어와 키릴 문자 모두를 삽입하려면 **extcodetextbuilder aspose 사용** 방법이 궁금했나요? 당신만 그런 것이 아닙니다. 많은 개발자들이 ASCII와 비‑ASCII 데이터를 혼합해야 할 때, 특히 대상 스캐너가 올바른 ECI(Extended Channel Interpretation) 마커를 기대할 때 벽에 부딪히곤 합니다.  

이 튜토리얼에서는 “HELLO123” **및** 러시아어 단어 “Привет” 를 담은 QR 코드를 Aspose.Barcode의 Python API로 만드는 정확한 단계를 살펴봅니다. 끝까지 진행하면 바로 실행 가능한 스크립트를 얻고, 각 호출이 왜 중요한지 이해하며, 다른 언어나 데이터 형식에 맞게 과정을 조정하는 방법을 알게 됩니다.

## 배울 내용

- **ExtCodetextBuilder**를 초기화하고 일반 텍스트와 ECI‑인코딩 조각을 추가하는 방법.  
- **ECI 인코딩** 값 `3`이 UTF‑8에 해당하는 이유와 스캔에 미치는 영향.  
- Aspose.Barcode를 사용하여 **QR Code 생성기**를 설정하는 정확한 순서.  
- 결과 이미지를 저장하고 혼합된 내용을 확인하는 방법.  

**Prerequisites** – Python 3.8+와 `aspose-barcode` 패키지(`pip install aspose-barcode`)가 설치되어 있어야 하며, 이미지를 쓸 수 있는 폴더가 필요합니다. 그 외는 없습니다.

---

## extcodetextbuilder aspose 사용하여 혼합 코드텍스트 만들기

먼저 `ExtCodetextBuilder` 인스턴스가 필요합니다. 이는 다양한 텍스트 조각을 연결하면서 자동으로 올바른 ECI 마커를 삽입해 주는 빌더 패턴이라고 생각하면 됩니다.

```python
# Step 1: Build an extended codetext that mixes plain and ECI‑encoded fragments
from aspose.barcode import BarcodeGenerator, Symbology
from aspose.barcode.generation import ExtCodetextBuilder

# Create the builder object
ext_builder = ExtCodetextBuilder()

# Add plain ASCII text – this part needs no special handling
ext_builder.add_plain_codetext("HELLO123")                     # Plain ASCII text

# Add UTF‑8 encoded Russian text – ECI value 3 signals UTF‑8 to the scanner
ext_builder.add_eci_codetext(eci_encoding=3, codetext="Привет")  # UTF‑8 encoded Russian text

# Retrieve the combined string that Aspose.Barcode will consume
extended_codetext = ext_builder.get_extended_codetext()
```

**왜 중요한가:**  
- `add_plain_codetext`는 데이터를 그대로 유지하므로 숫자나 영어 문자에 적합합니다.  
- `add_eci_codetext`는 제공된 문자열 앞에 ECI 세그먼트(` [ECI:3]`)를 삽입하여 모든 호환 리더에게 뒤따르는 바이트가 UTF‑8임을 알립니다. 이 없이 스캐너는 키릴 바이트를 잡음으로 해석합니다.

> **Pro tip:** 다른 문자 집합이 필요하면 ECI 표에 따라 `eci_encoding` 값을 변경하세요(예: ISO‑8859‑1은 `26`).  

---

## Aspose.Barcode로 QR 코드 생성 초기화

이제 올바르게 포맷된 `extended_codetext`가 준비되었으니 QR 코드 생성기에 전달할 수 있습니다. Aspose.Barcode는 저수준 QR 매트릭스 생성을 추상화하여 데이터에 집중할 수 있게 해 줍니다.

```python
# Step 2: Initialise a QR Code generator
qr_generator = BarcodeGenerator()
qr_generator.set_symbology(Symbology.QR)   # Choose QR as the symbology
```

**무슨 일이 일어나고 있나요?**  
- `BarcodeGenerator()`는 기본 설정(크기, 해상도 등)으로 새로운 생성기 객체를 만듭니다.  
- `set_symbology`는 엔진에 QR Code를 원한다는 것을 알려줍니다(예: Code128이 아니라).  

더 높은 오류 정정 수준이 필요하면 코드텍스트를 할당하기 전에 `qr_generator.parameters.barcode.qr_error_level = ...` 를 호출하면 됩니다.

---

## 확장된 코드텍스트를 QR 생성기에 할당하기

생성기가 준비되었으니 앞서 만든 혼합 문자열을 그대로 전달하면 됩니다.

```python
# Step 3: Assign the extended codetext to the generator
qr_generator.set_extended_codetext(extended_codetext)
```

**왜 `set_codetext`를 사용하지 않나요?**  
`set_codetext`는 입력을 일반 텍스트로 취급해 모든 ECI 마커를 제거합니다. `set_extended_codetext`는 원시 바이트와 ECI 세그먼트를 그대로 보존하여 스캐너가 올바른 언어 전환을 인식하도록 합니다.

---

## QR 코드 이미지를 저장하고 결과 확인하기

마지막으로 QR 코드를 디스크에 기록합니다. Aspose.Barcode는 PNG, JPEG, BMP 등 다양한 포맷을 지원하는데, PNG는 무손실 데이터를 유지하므로 안전한 기본값입니다.

```python
# Step 4: Save the generated QR Code image
qr_generator.save("YOUR_DIRECTORY/qr_extended.png")
```

지정한 위치에 PNG 파일이 생성됩니다. ECI를 지원하는 QR 스캐너 앱(대부분 최신 스마트폰)으로 열어 보세요. 한 번 스캔하면 “HELLO123”이 보이고, 다시 스캔하거나 원시 데이터를 표시하는 스캐너를 사용하면 “Привет”도 확인할 수 있습니다. 두 조각이 하나의 페이로드로 정확히 결합된 모습을 볼 수 있습니다.

![extcodetextbuilder aspose QR 코드 예시](YOUR_DIRECTORY/qr_extended.png)

*이미지 대체 텍스트: 혼합 ECI 텍스트를 보여주는 extcodetextbuilder aspose QR 코드 예시*

---

## 전체, 바로 실행 가능한 스크립트

모든 내용을 하나로 합치면 `qr_mixed_eci.py` 라는 파일에 복사‑붙여넣기 할 수 있는 완전한 프로그램이 됩니다:

```python
from aspose.barcode import BarcodeGenerator, Symbology
from aspose.barcode.generation import ExtCodetextBuilder

def generate_mixed_eci_qr(output_path: str):
    # Build mixed codetext
    ext_builder = ExtCodetextBuilder()
    ext_builder.add_plain_codetext("HELLO123")
    ext_builder.add_eci_codetext(eci_encoding=3, codetext="Привет")
    extended_codetext = ext_builder.get_extended_codetext()

    # Initialise QR generator
    qr_generator = BarcodeGenerator()
    qr_generator.set_symbology(Symbology.QR)

    # Assign extended codetext
    qr_generator.set_extended_codetext(extended_codetext)

    # Save image
    qr_generator.save(output_path)
    print(f"QR Code saved to {output_path}")

if __name__ == "__main__":
    generate_mixed_eci_qr("qr_extended.png")
```

다음과 같이 실행합니다:

```bash
python qr_mixed_eci.py
```

콘솔에 저장 위치가 확인되는 메시지가 표시되고, PNG 파일이 지정한 경로에 바로 생성됩니다.

---

## 일반적인 질문 및 엣지 케이스

### 스캐너가 키릴어 부분을 인식하지 못한다면?
스캐너 앱이 ECI 지원을 명시하고 있는지 확인하세요. 오래된 하드웨어는 ECI 세그먼트를 무시하고 바이트를 ISO‑8859‑1로 해석해 문자 깨짐이 발생할 수 있습니다.

### 두 개 이상의 조각을 추가할 수 있나요?
물론 가능합니다. `add_plain_codetext` 또는 `add_eci_codetext`를 원하는 만큼 호출하면 됩니다. 빌더는 호출 순서대로 조각을 연결합니다.

### QR 코드 크기나 전경 색을 어떻게 변경하나요?
`qr_generator.parameters` 객체를 사용합니다:

```python
qr_generator.parameters.barcode.x_dimension = 4   # module size in points
qr_generator.parameters.barcode.qr_error_level = qr_generator.parameters.barcode.QrErrorLevel.QR_ECLEVEL_Q
qr_generator.save("qr_custom.png", BarCodeImageFormat.PNG, 300)  # 300 DPI
```

### 텍스트와 함께 바이너리 데이터(예: 작은 파일)를 삽입할 방법이 있나요?
네. `add_binary_codetext`에 바이트 배열을 전달하고, 바이너리가 특정 문자 집합을 나타낸다면 적절한 ECI와 함께 사용하면 됩니다. 빌더가 필요한 모드 전환을 자동으로 처리합니다.

---

## 결론

이제 **extcodetextbuilder aspose 사용**하여 일반 ASCII와 UTF‑8 인코딩된 러시아어 텍스트를 자연스럽게 혼합한 QR 코드를 만들 수 있습니다. `ExtCodetextBuilder`를 활용하고 올바른 **ECI 인코딩**을 설정한 뒤 **Aspose.Barcode QR Code 생성기**에 결과를 전달하면, 현대 스캐너에서 정상 작동하는 단일 표준 준수 이미지를 얻을 수 있습니다.  

앞으로 `eci_encoding=3`을 다른 언어 식별자로 교체하거나, 추가 일반 조각을 넣어 다국어 페이로드를 실험해 보세요. 벡터 그래픽이 필요하면 `BarCodeImageFormat` 옵션을 사용해 SVG나 PDF로 출력할 수도 있습니다.  

코딩을 즐기시고, 문제가 발생하면 언제든 댓글을 남겨 주세요—여러분의 피드백이 이 가이드를 더욱 개선합니다!

## 다음에 배울 내용은?

다음 튜토리얼들은 이 가이드에서 다룬 기술을 기반으로 하여 관련 주제를 깊이 있게 다룹니다. 각 리소스는 완전한 코드 예제와 단계별 설명을 포함하고 있어 추가 API 기능을 마스터하고 프로젝트에 다양한 구현 방식을 적용하는 데 도움이 됩니다.

- [Java 바코드 생성 - Aspose.BarCode를 사용한 코드 텍스트 설정](/barcode/english/java/text-and-styling/setting-code-text/)
- [aspose .net 바코드 생성 - DataMatrix 코드 텍스트 구성](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-extended-code-text-configuration/)
- [.NET용 Aspose.BarCode와 함께하는 Aztec 코드 텍스트 인코딩](/barcode/english/net/aztec-barcode-encoding/aztec-code-text-encoding/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}