---
category: general
date: 2026-07-30
description: Python에서 Databar Stacked Omnidirectional 바코드를 생성하세요. 단계별 가이드를 따라 종횡비와
  XDimension을 설정하고, 파이썬 바코드 생성기를 사용해 PNG로 내보내세요.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create databar stacked omnidirectional
- python barcode generator
- databar aspect ratio
- xdimension pixel size
- barcodeimageformat png
language: ko
lastmod: 2026-07-30
og_description: Python에서 Databar Stacked Omnidirectional 바코드를 생성합니다. 이 튜토리얼에서는 XDimension을
  설정하고 DataBar 종횡비를 조정한 뒤 BarCodeImageFormat으로 PNG를 저장하는 방법을 보여줍니다.
og_image_alt: Screenshot of a Databar Stacked Omnidirectional barcode saved as a PNG
  file
og_title: Databar Stacked Omnidirectional 바코드 만들기 – 파이썬 튜토리얼
schemas:
- author: Aspose
  dateModified: '2026-07-30'
  description: Create Databar Stacked Omnidirectional barcode in Python. Follow this
    step‑by‑step guide to configure aspect ratio, XDimension, and export PNG using
    a python barcode generator.
  headline: Create Databar Stacked Omnidirectional Barcode in Python
  type: TechArticle
tags:
- barcode
- python
- databar
title: Python으로 Databar Stacked Omnidirectional 바코드 생성
url: /ko/python-java/general/create-databar-stacked-omnidirectional-barcode-in-python/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Python에서 Databar Stacked Omnidirectional 바코드 만들기

Python에서 **databar stacked omnidirectional** 바코드를 생성해야 했지만 어디서 시작해야 할지 몰랐던 적이 있나요? 당신만 그런 것이 아닙니다—많은 개발자들이 `BarcodeGenerator` 클래스를 처음 사용할 때 이 장벽에 부딪힙니다. 핵심 속성을 이해하면 전체 과정이 꽤 간단하다는 좋은 소식이 있습니다.

이 가이드에서는 **python barcode generator**를 사용하여 XDimension을 설정하고 DataBar 종횡비를 조정한 뒤 두 개의 PNG 파일을 내보내는 완전하고 실행 가능한 예제를 단계별로 살펴보겠습니다. 끝까지 읽으면 재고 또는 물류 프로젝트에 사용할 고품질 stacked omnidirectional 심볼을 생성하는 방법을 확실히 이해하게 될 것입니다.

## 배울 내용

- GTIN‑14 페이로드를 사용하여 **databar stacked omnidirectional** 생성기를 인스턴스화하는 방법.  
- **XDimension 픽셀 크기**가 스캔 신뢰성에 중요한 이유.  
- **DataBar 종횡비**가 행 너비와 높이에 미치는 영향.  
- 결과를 **BarCodeImageFormat PNG** 파일로 저장하는 방법.  
- 동일한 생성기 객체를 재사용하여 메모리 오버헤드 없이 여러 변형을 만드는 팁.

### 사전 요구 사항

- Python 3.8+ (사용하는 라이브러리는 순수 Python이며, 컴파일된 휠이 필요 없습니다).  
- `barcode-generator` 패키지 (`pip install barcode-generator` 로 설치).  
- 쓰기 가능한 폴더 – 스크립트가 두 개의 PNG 이미지를 해당 폴더에 저장합니다.

기본적인 Python import와 객체 지향 코드를 다루는 데 익숙하다면 바로 시작할 준비가 된 것입니다.

## Databar Stacked Omnidirectional 바코드 생성 – 단계 개요

아래에서는 워크플로를 여섯 개의 작은 단계로 나눕니다. 각 단계는 REPL이나 스크립트 파일에 복사‑붙여넣기 할 수 있는 독립적인 코드 조각입니다. 자유롭게 실험해 보세요—종횡비나 XDimension을 변경하면 즉시 다른 시각적 스타일을 얻을 수 있습니다.

---

## Step 1: Databar Stacked Omnidirectional 생성기 만들기

먼저 **databar stacked omnidirectional** 생성기 인스턴스를 만들고, 적절한 `EncodeTypes` 열거형과 데이터 문자열을 전달합니다.

```python
from barcode_generator import BarcodeGenerator, EncodeTypes, BarCodeImageFormat

# Step 1 – initialize the generator with a GTIN‑14 payload
barcode_generator = BarcodeGenerator(
    EncodeTypes.DatabarStackedOmniDirectional,
    "(01)12345678901231"
)
```

> **왜 중요한가:** `EncodeTypes.DatabarStackedOmniDirectional` 플래그는 라이브러리에게 stacked omnidirectional 심볼을 생성하도록 지시합니다. 이는 14자리까지 인코딩하면서도 모든 각도에서 읽을 수 있는 유일한 DataBar 변형입니다.

---

## XDimension 픽셀 크기 설정

**XDimension 픽셀 크기**는 가장 작은 모듈(가장 얇은 검은 막대)을 제어합니다. `2` 픽셀 값은 대부분의 화면 표시 상황에 잘 맞습니다.

```python
# Step 2 – set the smallest module to 2 pixels
barcode_generator.Parameters.Barcode.XDimension.Pixels = 2
```

> **프로 팁:** 고 DPI로 바코드를 인쇄할 계획이라면 흐릿한 가장자리를 방지하기 위해 값을 3 또는 4로 올리세요.

---

## DataBar 종횡비 조정 (15)

**DataBar 종횡비**는 각 행의 너비가 높이에 비해 얼마나 넓은지를 결정합니다. `15`의 종횡비는 더 넓은 행을 만들며, 많은 스캐너가 빠른 움직임 캡처를 위해 선호합니다.

```python
# Step 3 – make rows wider (aspect ratio = 15)
barcode_generator.Parameters.Barcode.DataBar.AspectRatio = 15
```

> **왜 15인가?** 공식 GS1 사양은 stacked omnidirectional 심볼에 대해 10에서 20 사이의 비율을 권장합니다. 우리는 균형 잡힌 기본값으로 `15`를 선택했습니다.

---

## BarCodeImageFormat을 사용해 PNG로 바코드 내보내기

이제 생성기가 설정되었으니 이미지를 저장합니다. `BarCodeImageFormat.Png` 열거형은 무손실 출력을 보장하여 후속 처리에 적합합니다.

```python
# Step 4 – save the first PNG with the 15 aspect ratio
barcode_generator.Save(
    "YOUR_DIRECTORY/DatabarStackedAR15.png",
    BarCodeImageFormat.Png
)
```

> **보게 될 내용:** 생성된 PNG를 열면 비교적 넓은 행을 가진 깨끗하고 고대비의 바코드를 확인할 수 있습니다.

---

## DataBar 종횡비를 30으로 변경

때때로 넓은 행보다 더 높은 행이 필요할 수 있습니다—예를 들어 좁은 라벨에 맞추기 위해서입니다. **DataBar 종횡비**를 `30`으로 바꾸면 각 행이 더 높아집니다.

```python
# Step 5 – increase the aspect ratio to make rows taller
barcode_generator.Parameters.Barcode.DataBar.AspectRatio = 30
```

> **예외 상황:** 매우 높은 비율(예: 40 초과)은 바코드가 일반 라벨 높이를 초과하게 할 수 있으므로 적용하기 전에 실제 프린터에서 테스트하세요.

---

## 새로운 종횡비로 바코드 다시 내보내기

마지막으로 동일한 `barcode_generator` 객체를 재사용하여 두 번째 PNG를 작성합니다. 생성기를 다시 만들 필요 없이 속성을 변경하고 `Save`를 다시 호출하면 됩니다.

```python
# Step 6 – save the second PNG with the 30 aspect ratio
barcode_generator.Save(
    "YOUR_DIRECTORY/DatabarStackedAR30.png",
    BarCodeImageFormat.Png
)
```

> **결과:** 이제 두 개의 PNG 파일이 있습니다—넓은 행(`AR15`)을 가진 파일과 높은 행(`AR30`)을 가진 파일. 나란히 비교하여 스캐너 설정에 가장 적합한 것을 선택하세요.

---

## 전체 작업 예제

모두 합치면 즉시 실행할 수 있는 전체 스크립트가 아래에 있습니다. `YOUR_DIRECTORY`를 여러분 컴퓨터의 절대 경로로 바꾸세요.

```python
from barcode_generator import BarcodeGenerator, EncodeTypes, BarCodeImageFormat

# 1️⃣ Initialize generator
barcode_generator = BarcodeGenerator(
    EncodeTypes.DatabarStackedOmniDirectional,
    "(01)12345678901231"
)

# 2️⃣ Set smallest module (XDimension)
barcode_generator.Parameters.Barcode.XDimension.Pixels = 2

# 3️⃣ First aspect ratio – wider rows
barcode_generator.Parameters.Barcode.DataBar.AspectRatio = 15
barcode_generator.Save("YOUR_DIRECTORY/DatabarStackedAR15.png", BarCodeImageFormat.Png)

# 4️⃣ Second aspect ratio – taller rows
barcode_generator.Parameters.Barcode.DataBar.AspectRatio = 30
barcode_generator.Save("YOUR_DIRECTORY/DatabarStackedAR30.png", BarCodeImageFormat.Png)

print("✅ Two PNG files created – AR15 and AR30")
```

**예상 출력** (콘솔에 표시):

```
✅ Two PNG files created – AR15 and AR30
```

그리고 대상 폴더에 두 개의 이미지 파일이 생성되어 스캔 테스트를 할 준비가 됩니다.

---

## 결론

우리는 방금 Python에서 **databar stacked omnidirectional** 바코드를 **생성**하고, **XDimension 픽셀 크기**를 조정했으며, 두 가지 다른 **DataBar 종횡비** 설정을 실험하고, 결과를 **BarCodeImageFormat PNG** 파일로 내보냈습니다. 전체 워크플로는 몇 줄에 불과하지만 스캐너에 가장 중요한 시각적 특성을 완전히 제어할 수 있습니다.

다음은? 페이로드를 다른 GTIN으로 교체하거나, PNG를 팔레트 기반 이미지로 변환해 색상을 조정하거나, 두 PNG를 나란히 삽입한 PDF 보고서를 생성해 보세요. `BarcodeGenerator` 클래스는 이러한 모든 시나리오를 처리할 만큼 유연하니 자유롭게 실험해 보세요.

특정 사용 사례에 대한 질문이 있거나 오류가 발생했나요? 아래에 댓글을 남겨 주세요. 기꺼이 도와드리겠습니다. 즐거운 코딩 되세요!

## 다음에 배울 내용은?

다음 튜토리얼들은 이 가이드에서 시연한 기술을 기반으로 하는 밀접한 관련 주제를 다룹니다. 각 자료는 단계별 설명과 함께 완전한 코드 예제를 제공하여 추가 API 기능을 마스터하고 프로젝트에서 대체 구현 방식을 탐색할 수 있도록 돕습니다.

- [바코드 이미지 생성 – GS1 쿠폰 UPC-A Databar](/barcode/english/net/gs1-barcode-encoding/gs1-coupon-upc-a-databar-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}