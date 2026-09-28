---
category: general
date: 2026-08-12
description: Python으로 전방향 데이터바를 생성하고 Aspose.BarCode를 사용하여 Python에서 바코드 이미지를 만드는 방법을
  배워보세요. 완전한 솔루션을 위한 단계별 가이드를 따라하세요.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create omni directional databar
- create barcode image python
language: ko
lastmod: 2026-08-12
og_description: Python으로 전방위 데이터바를 생성하고 몇 분 안에 바코드 이미지를 만들 수 있습니다. 이 튜토리얼은 완전하고 실행
  가능한 예제를 보여줍니다.
og_image_alt: example of create omni directional databar barcode image in Python
og_title: 전방향 데이터바 만들기 – 전체 파이썬 가이드
schemas:
- author: Aspose
  dateModified: '2026-08-12'
  description: Create omni directional databar with Python and learn how to create
    barcode image python using Aspose.BarCode. Follow the step‑by‑step guide for a
    complete solution.
  headline: Create omni directional databar and barcode image in Python
  type: TechArticle
tags:
- barcode
- Python
- Aspose
- DataBar
title: Python에서 전방위 데이터바 및 바코드 이미지 만들기
url: /ko/python-java/general/create-omni-directional-databar-and-barcode-image-in-python/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Python에서 omni directional databar 및 barcode 이미지 만들기

If you need to **create omni directional databar** in a Python project, this guide shows you how to do it and also how to **create barcode image python** using the Aspose.BarCode library. You will get a ready‑to‑run script that produces two PNG files with different aspect ratios.

Python 프로젝트에서 **omni directional databar**를 생성해야 한다면, 이 가이드는 그 방법과 Aspose.BarCode 라이브러리를 사용하여 **barcode image python**을 생성하는 방법을 보여줍니다. 실행 준비가 된 스크립트를 받아 두 개의 PNG 파일을 서로 다른 종횡비로 생성할 수 있습니다.

Generating a DataBar that follows the Omni‑directional specification is a common requirement for retail and logistics applications. The tutorial covers installation, configuration of the X‑dimension, adjustment of the aspect ratio, and saving the final images. No external services are required; everything runs locally.

Omni‑directional 사양을 따르는 DataBar를 생성하는 것은 소매 및 물류 애플리케이션에서 일반적인 요구 사항입니다. 이 튜토리얼에서는 설치, X‑dimension 설정, 종횡비 조정 및 최종 이미지 저장을 다룹니다. 외부 서비스가 필요 없으며 모든 작업이 로컬에서 실행됩니다.

## 필요 사항

Before you start, make sure you have:

* Python 3.8 or newer installed on your machine.
* Access to a terminal or command prompt.
* Write permission to a folder where the barcode images will be saved.

The only third‑party dependency is **Aspose.BarCode for Python via .NET**, which supports the Omni‑directional DataBar type out of the box.

## 단계 1: Aspose.BarCode for Python 설치

Aspose.BarCode provides the `BarcodeGenerator` class used in the example code. Install the package with `pip`:

```bash
pip install aspose-barcode
```

The package includes the necessary .NET runtime bindings, so you do not need to install the .NET SDK separately.

## 단계 2: Import the library and create the generator

The first line of the script creates a generator for a stacked Omni‑directional DataBar. The GTIN‑14 value `(01)12345678901231` is used as sample data.

```python
# Step 2: Import classes and create the generator
from aspose.barcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat

# Create a generator for a stacked Omni‑directional DataBar with the required data
barcode_generator = BarcodeGenerator(
    EncodeTypes.DATABAR_STACKED_OMNIDIRECTIONAL,
    "(01)12345678901231"
)
```

*이 단계가 중요한 이유*: The `EncodeTypes.DATABAR_STACKED_OMNIDIRECTIONAL` constant tells the library to encode the value as an Omni‑directional DataBar, which is the format required by many point‑of‑sale scanners.

## 단계 3: Set the X‑dimension (module width)

The X‑dimension defines the width of the smallest bar module. A value of `2` pixels produces a clear, readable barcode without excessive file size.

```python
# Step 3: Set the basic X‑dimension (width of the smallest module) in pixels
barcode_generator.parameters.barcode.x_dimension.pixels = 2
```

*이 단계가 중요한 이유*: Adjusting the X‑dimension allows you to balance readability and image dimensions. An X‑dimension that is too small may render poorly on low‑resolution printers.

## 단계 4: Configure the aspect ratio and save the first image

The aspect ratio influences the overall height of the DataBar relative to its width. An aspect ratio of `15` creates a compact visual style.

```python
# Step 4: Configure an aspect ratio of 15 and save the first image
barcode_generator.parameters.barcode.data_bar.aspect_ratio = 15
barcode_generator.save("output/StackedAR15.png", BarCodeImageFormat.Png)
```

> **팁**: Use `pathlib.Path` to build the output path, which automatically creates missing directories.

```python
from pathlib import Path

output_dir = Path("output")
output_dir.mkdir(parents=True, exist_ok=True)
barcode_generator.save(output_dir / "StackedAR15.png", BarCodeImageFormat.Png)
```

## 단계 5: Change the aspect ratio for a second visual style and save another image

Switching the aspect ratio to `30` produces a taller barcode that may be required by specific scanner hardware.

```python
# Step 5: Change the aspect ratio to 30 and save the second image
barcode_generator.parameters.barcode.data_bar.aspect_ratio = 30
barcode_generator.save(output_dir / "StackedAR30.png", BarCodeImageFormat.Png)
```

*이 단계가 중요한 이유*: Different retailers and scanning devices have distinct size constraints. Providing both aspect ratios in a single script lets you generate the exact style you need without duplicating code.

## 전체 스크립트 – omni directional databar 및 barcode 이미지 python 생성

Below is the complete, runnable example that incorporates all previous steps. Save it as `generate_databar.py` and run it with `python generate_databar.py`.

```python
#!/usr/bin/env python3
"""
Complete example that creates an omni directional databar
and demonstrates how to create barcode image python using Aspose.BarCode.
"""

# Import required classes
from aspose.barcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat
from pathlib import Path

def main():
    # Define output directory and ensure it exists
    output_dir = Path("output")
    output_dir.mkdir(parents=True, exist_ok=True)

    # Initialize the generator with Omni‑directional DataBar data
    generator = BarcodeGenerator(
        EncodeTypes.DATABAR_STACKED_OMNIDIRECTIONAL,
        "(01)12345678901231"
    )

    # Set X‑dimension to 2 pixels for good readability
    generator.parameters.barcode.x_dimension.pixels = 2

    # First visual style – aspect ratio 15
    generator.parameters.barcode.data_bar.aspect_ratio = 15
    generator.save(output_dir / "StackedAR15.png", BarCodeImageFormat.Png)

    # Second visual style – aspect ratio 30
    generator.parameters.barcode.data_bar.aspect_ratio = 30
    generator.save(output_dir / "StackedAR30.png", BarCodeImageFormat.Png)

    print(f"Images saved to: {output_dir.resolve()}")

if __name__ == "__main__":
    main()
```

### 예상 출력

Running the script creates the following files:

```
output/StackedAR15.png   # DataBar with aspect ratio 15
output/StackedAR30.png   # DataBar with aspect ratio 30
```

Both images display a valid Omni‑directional DataBar that can be scanned by standard retail equipment.

![Python에서 omni directional databar barcode 이미지 생성 예시](example_databar.png "Python에서 omni directional databar barcode 이미지 생성")

*위 이미지는 저장된 두 PNG 파일을 보여주는 자리 표시자입니다.*

## 일반적인 문제 처리

| 문제 | 원인 | 해결 방법 |
|-------|--------|-----|
| `ImportError: No module named aspose` | Aspose.BarCode가 설치되지 않았거나 다른 환경에 설치되었습니다. | 올바른 가상 환경을 활성화하고 `pip install aspose-barcode`를 실행하십시오. |
| `PermissionError` when saving | 스크립트가 대상 폴더에 대한 쓰기 권한이 없습니다. | 자신이 소유한 디렉터리를 선택하거나 적절한 권한으로 스크립트를 실행하십시오. |
| Barcode does not scan | X‑dimension이 너무 낮거나 종횡비가 스캐너와 호환되지 않습니다. | `x_dimension.pixels`를 3 또는 4로 늘리고, 다양한 `aspect_ratio` 값(예: 20, 25)을 테스트하십시오. |
| Missing .NET runtime | Aspose.BarCode는 Windows/Linux에서 .NET 런타임에 의존합니다. | Microsoft 사이트에서 최신 .NET 런타임을 설치하십시오; 패키지 문서에 플랫폼별 가이드가 제공됩니다. |

## 예제 확장하기

You can adapt the script to generate other DataBar variants (e.g., `DATABAR_STACKED`, `DATABAR_EXPANDED`). Replace the `EncodeTypes` constant accordingly:

```python
generator = BarcodeGenerator(EncodeTypes.DATABAR_EXPANDED, "(01)12345678901231")
```

If you need to embed the barcode in a PDF, Aspose.PDF for Python can import the PNG file directly or you can use the `save` method with `BarCodeImageFormat.Pdf`.

## 결론

This tutorial showed how to **create omni directional databar** and how to **create barcode image python** using Aspose.BarCode. You now have a complete, reproducible script that generates two PNG files with different aspect ratios, handles common pitfalls, and can be extended to other barcode formats.

Next, explore generating QR codes, adding the barcode to PDF invoices, or automating batch processing for large product catalogs. Each of those topics builds on the same `BarcodeGenerator` pattern demonstrated here. Happy coding!

## 다음에 배워야 할 내용은?

The following tutorials cover closely related topics that build on the techniques demonstrated in this guide. Each resource includes complete working code examples with step-by-step explanations to help you master additional API features and explore alternative implementation approaches in your own projects.

- [바코드 이미지 생성 – GS1 쿠폰 UPC-A Databar](/barcode/english/net/gs1-barcode-encoding/gs1-coupon-upc-a-databar-configuration/)
- [DotCode 바코드 이미지 생성 – 행 및 열 (Aspose.BarCode)](/barcode/english/net/dotcode-barcode-configuration/dotcode-rows-columns-configuration/)
- [Java에서 바코드 이미지 생성 및 렌더링 방법](/barcode/english/java/barcode-rendering-techniques/rendering-barcode-image-instance/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}