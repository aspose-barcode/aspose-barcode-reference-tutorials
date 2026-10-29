---
category: general
date: 2026-10-28
description: ExtCodetextBuilder를 사용하여 Python에서 확장 코드텍스트를 만드는 방법을 배웁니다. 일반 데이터와 ECI
  인코딩 데이터, 단계별 코드 및 모범 사례 팁을 포함합니다.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create extended codetext
- ExtCodetextBuilder Python
- add plain codetext
- add eci codetext
- extended‑codetext example
language: ko
lastmod: 2026-10-28
og_description: ExtCodetextBuilder를 사용하여 Python에서 확장 코드텍스트를 생성합니다. 이 튜토리얼에서는 일반 데이터와
  ECI 인코딩 데이터 처리, 완전한 실행 가능한 코드, 그리고 흔히 발생하는 함정을 보여줍니다.
og_image_alt: Diagram showing how to create extended codetext using ExtCodetextBuilder
  in Python
og_title: Python에서 확장된 코드 텍스트 만들기 – 완전 가이드
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
title: ExtCodetextBuilder를 사용해 Python에서 확장 코드 텍스트를 만드는 방법
url: /ko/python/general/how-to-create-extended-codetext-in-python-with-extcodetextbu/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Python에서 ExtCodetextBuilder로 확장된 코드텍스트 생성 방법

바코드 또는 데이터‑매트릭스 애플리케이션을 위해 **확장된 코드텍스트를 생성**해야 한다면, 이 가이드는 Python에서 정확히 어떻게 하는지 보여줍니다. 일반 텍스트를 결합하고, Unicode 문자를 위한 ECI(Extended Channel Interpretation) 섹션을 추가하며, 인코딩에 바로 사용할 수 있는 단일, 올바르게 포맷된 문자열을 얻는 방법을 확인할 수 있습니다.

이 튜토리얼은 필수 라이브러리 설치부터 지원되지 않는 ECI 값과 같은 엣지 케이스 처리까지 모두 다룹니다. 마지막까지 진행하면 **확장된 코드텍스트를 생성**해야 하는 모든 프로젝트에 재사용 가능한 패턴을 얻게 됩니다.

## 배울 내용

* 혼합 인코딩 문자열을 만들 때 `ExtCodetextBuilder`의 역할.  
* 하나의 빌더 인스턴스에서 **일반 코드텍스트 추가**와 **ECI 코드텍스트 추가**를 수행하는 방법.  
* 최종 출력물을 검증하고 흔히 발생하는 문제를 해결하는 방법.  
* 다른 문자 집합에 대한 변형(예: ISO‑8859‑1, Shift‑JIS).  

### 전제 조건

* Python 3.8 이상.  
* `extcodetext` 패키지(또는 `ExtCodetextBuilder`를 제공하는 유사 라이브러리). 다음 명령으로 설치합니다:

```bash
pip install extcodetext
```

* Unicode와 ECI 값에 대한 기본적인 이해 – ECI 3은 UTF‑8, ECI 4는 ISO‑8859‑1 등을 의미합니다.

> **Pro tip:** ECI 번호 표를 손쉽게 참고할 수 있도록 준비해 두세요. 선언된 인코딩과 실제 바이트 시퀀스 간의 불일치를 방지할 수 있습니다.

## ExtCodetextBuilder 이해하기

`ExtCodetextBuilder`는 여러 텍스트 조각을 연결하면서 자동으로 필요한 ECI 마커를 삽입해 주는 작은 유틸리티입니다. ECI 마커는 하위 바코드 인코더에게 뒤따르는 바이트가 어떤 문자 집합을 사용해야 하는지 알려 줍니다. 마커가 없으면 비‑ASCII 문자들이 잘못 해석될 수 있습니다.

빌더는 세 가지 간단한 단계로 동작합니다:

1. **Create** 빌더 인스턴스를 생성합니다.  
2. **Append** 일반 또는 ECI‑인코딩된 조각을 추가합니다.  
3. **Retrieve** 결합된 확장‑코드텍스트 문자열을 가져옵니다.

아래에서는 각 단계를 구체적인 코드와 함께 살펴봅니다.

## Step 1: ExtCodetextBuilder 인스턴스 생성

첫 번째 줄은 모든 조각을 보관할 객체를 구성합니다. 이 시점에서는 별도의 설정이 필요하지 않습니다.

```python
from extcodetext import ExtCodetextBuilder

# Step 1: Create an ExtCodetextBuilder instance
codetext_builder = ExtCodetextBuilder()
```

*왜 중요한가*: 빌더를 인스턴스화하면 내부 버퍼가 할당됩니다. 이후 모든 `add_*` 호출은 이 버퍼에 작용해 지정한 순서를 보장합니다.

## Step 2: 일반(인코딩되지 않은) 데이터 추가

일반 데이터는 기본 문자 집합(보통 ASCII)에 속하는 문자들로 구성됩니다. 이러한 조각에는 `add_plain_codetext`를 사용합니다.

```python
# Step 2: Append plain (un‑encoded) data to the builder
codetext_builder.add_plain_codetext("ABC123")
```

*설명*: 문자열 `"ABC123"`은 ASCII 문자만 포함하므로 ECI 마커가 필요 없습니다. 이 메서드는 단순히 원시 바이트를 내부 버퍼에 추가합니다.

## Step 3: ECI가 앞에 와야 하는 데이터 추가

Unicode 문자(예: 키릴 문자, 일본어, 이모지)를 삽입해야 할 때는 인코더에게 어떤 문자 집합을 사용할지 알려야 합니다. 이는 `add_eci_codetext(eci, text)`로 수행합니다. 첫 번째 인자는 숫자형 ECI 값이며, 두 번째 인자는 실제 텍스트입니다.

```python
# Step 3: Append data that must be preceded by an ECI (e.g., 3 for UTF‑8)
# This ensures the text "Привет" is correctly interpreted as UTF‑8
codetext_builder.add_eci_codetext(3, "Привет")
```

*왜 ECI 3인가*: ISO/IEC 18004 사양에 따르면 ECI 3은 UTF‑8에 매핑됩니다. 이 마커를 삽입하면 바코드 리더가 뒤따르는 바이트를 UTF‑8로 해석해 키릴 문자를 올바르게 표시합니다.

### 다른 인코딩 처리하기

ISO‑8859‑1(서유럽) 문자 집합이 필요하면 `add_eci_codetext(4, "¡Hola!")`를 사용합니다. Shift‑JIS(일본어)의 경우 ECI 값은 20입니다:

```python
codetext_builder.add_eci_codetext(20, "こんにちは")
```

대상 바코드 라이브러리가 선택한 ECI 값을 지원하는지 항상 확인하세요. 지원되지 않는 ECI는 인코딩 실패를 초래합니다.

## Step 4: 결합된 확장‑코드텍스트 문자열 가져오기

모든 조각을 추가한 뒤 `get_extended_codetext()`를 호출해 최종 문자열을 얻습니다. 이 문자열에는 필요한 ECI 이스케이프 시퀀스가 포함됩니다.

```python
# Step 4: Retrieve the combined extended‑codetext string
extended_codetext = codetext_builder.get_extended_codetext()

print("Extended codetext:", extended_codetext)
```

**예상 출력**(가독성을 위해 Python `repr` 형태로 표시):

```
Extended codetext: 'ABC123\x1B\x1D\x03Привет'
```

*구성*:

* `ABC123` – 일반 ASCII 구간.  
* `\x1B\x1D\x03` – UTF‑8용 ECI 이스케이프 시퀀스(ESC GS 0x03).  
* `Привет` – UTF‑8 인코딩된 키릴어 단어.

정확한 이스케이프 바이트는 라이브러리 구현에 따라 다를 수 있지만, 논리적 순서는 항상 *일반 → ECI 마커 → 유니코드 텍스트*가 됩니다.

## Full runnable example

전체 흐름을 하나로 모은 예제로, `create_extended_codetext.py`라는 파일에 복사‑붙여넣기만 하면 바로 실행할 수 있습니다.

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

스크립트를 실행하면 결합된 문자열이 출력되며, 이는 확장‑코드텍스트 입력을 받는 모든 바코드 인코더에 바로 사용할 수 있습니다.

## Common pitfalls and how to avoid them

| 증상 | 가능한 원인 | 해결 방법 |
|---|---|---|
| `add_eci_codetext` 호출 시 `UnicodeEncodeError` 발생 | 선택한 ECI에서 표현할 수 없는 문자를 포함한 문자열을 전달 | ECI가 문자열의 실제 인코딩과 일치하는지 확인(예: 모든 UTF‑8 텍스트에는 ECI 3 사용). |
| 최종 출력에 ECI 마커가 없음 | 비‑ASCII 데이터를 `add_plain_codetext`로 실수로 추가 | ASCII 범위를 벗어나는 모든 문자에 대해 `add_eci_codetext`로 전환. |
| 바코드 스캐너가 문자 깨짐을 표시 | 스캐너가 선택한 ECI 값을 지원하지 않음 | 보편적으로 지원되는 ECI(UTF‑8) 선택하거나, 대상 언어가 허용한다면 ISO‑8859‑1로 대체. |
| `get_extended_codetext`가 빈 문자열 반환 | 메서드 호출 전에 조각을 하나도 추가하지 않음 | 최소 하나 이상의 `add_*` 호출이 실행되었는지 확인. |

### Edge case: 빈 문자열

`add_plain_codetext("")` 또는 `add_eci_codetext(3, "")`를 호출해도 무해합니다; 빌더는 빈 조각을 무시합니다. 그러나 빈 호출을 반복하면 불필요한 ECI 마커가 삽입될 수 있습니다. 문자열 길이를 확인한 뒤 추가하도록 방어 코드를 넣으세요.

```python
text = "data"
if text:
    builder.add_plain_codetext(text)
```

## Extending the pattern for dynamic data

실제 서비스에서는 사용자 입력이나 데이터베이스 레코드에서 확장 코드텍스트를 구축하는 경우가 많습니다. 아래 스니펫은 `(type, value)` 튜플 리스트를 순회하면서 `type`이 `"plain"`인지 `"eci"`인지에 따라 적절히 처리하는 예시입니다.

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

이 접근 방식은 확장성이 뛰어나며, JSON, CSV, API 등에서 조각 정의를 읽어와도 핵심 빌딩 로직을 변경할 필요가 없습니다.

## Testing the output

빠른 단위 테스트로 빌더가 기대대로 동작하는지 확인할 수 있습니다. `pytest`를 사용합니다:

```python
def test_extended_codetext():
    b = ExtCodetextBuilder()
    b.add_plain_codetext("X")
    b.add_eci_codetext(3, "✓")   # Check mark in UTF‑8
    result = b.get_extended_codetext()
    assert result.startswith("X")
    assert "\x1B\x1D\x03".encode() in result.encode()
```

`pytest`를 실행했을 때 모든 테스트가 통과하면 ECI 마커가 정확히 삽입된 것을 확인할 수 있습니다.

## Related concepts you might explore next

* **Barcode encoding libraries** – 예: `python-barcode`, `zxing` 바인딩 등, 확장 코드텍스트 문자열을 직접 받아들입니다.  
* **ECI table reference** – ISO/IEC 18004에서 발표한 전체 ECI 번호 목록을 Python 딕셔너리 형태로 저장해 두면 lookup에 편리합니다.  
* **Error correction levels** – QR 코드를 생성할 때는 적절한 오류 정정 레벨(L, M, Q, H)을 결합해 스캔 안정성을 높일 수 있습니다.

## Conclusion

이제 `ExtCodetextBuilder`를 사용해 Python에서 **확장된 코드텍스트를 생성**하는 방법을 알게 되었습니다. 과정은 간단합니다:

1. 빌더를 인스턴스화한다.  
2. 필요에 따라 일반 및 ECI‑인코딩 조각을 추가한다.  
3. 최종 문자열을 가져와 바코드 생성기에 전달한다.

위 패턴을 따르면 ASCII와 Unicode 데이터를 자유롭게 혼합하고, 흔한 인코딩 오류를 피하며, 다양한 스캐너에서 동작하는 바코드‑준비 문자열을 만들 수 있습니다. 다양한 ECI를 실험하고, 빌더를 데이터 파이프라인에 통합해 보세요. 이제 모든 확장‑코드텍스트 요구 사항에 대한 견고한 기반을 갖추게 되었습니다.

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}