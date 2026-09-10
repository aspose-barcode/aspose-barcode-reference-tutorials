---
category: general
date: 2026-07-27
description: Aspose.BarCode를 사용하여 전방위 바코드 이미지를 생성합니다. Aspose로 바코드를 생성하고, 종횡비를 조정하며,
  PNG 파일로 저장하는 방법을 배웁니다.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create omnidirectional barcode image
- generate barcode with aspose
language: ko
lastmod: 2026-07-27
og_description: Aspose를 사용하여 전방위 바코드 이미지를 생성하세요. 이 가이드를 따라 Aspose로 바코드를 생성하고, 종횡비를
  조정한 뒤 PNG로 내보내세요.
og_image_alt: Screenshot of two omnidirectional barcode images with different aspect
  ratios
og_title: Aspose로 전방위 바코드 이미지 만들기 – 단계별
schemas:
- author: Aspose
  dateModified: '2026-07-27'
  description: Create omnidirectional barcode image using Aspose.BarCode. Learn how
    to generate barcode with Aspose, adjust aspect ratio, and save PNG files.
  headline: Create Omnidirectional Barcode Image with Aspose – Full Guide
  type: TechArticle
- description: Create omnidirectional barcode image using Aspose.BarCode. Learn how
    to generate barcode with Aspose, adjust aspect ratio, and save PNG files.
  name: Create Omnidirectional Barcode Image with Aspose – Full Guide
  steps:
  - name: 1. Different Image Formats
    text: 'Aspose supports BMP, JPEG, TIFF, and SVG in addition to PNG. Swap the enum
      value:'
  - name: 2. Customizing Colors
    text: 'You might need a white barcode on a dark background. Set `ForeColor` and
      `BackColor`:'
  - name: 3. Handling Invalid Aspect Ratios
    text: 'Aspose validates the range (usually 5‑50). If you pass an out‑of‑range
      value, an `ArgumentException` is thrown. Wrap the save call in a try‑catch to
      give a friendly message:'
  - name: 4. Batch Generation
    text: When you have a list of GTINs, loop over them, update `CodeText`, and save
      each file with a unique name. The generator object can be reused, keeping memory
      usage low.
  type: HowTo
tags:
- barcode
- Aspose
- C#
- image-generation
title: Aspose로 전방위 바코드 이미지 만들기 – 전체 가이드
url: /ko/python-java/general/create-omnidirectional-barcode-image-with-aspose-full-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose를 사용한 전방향 바코드 이미지 생성 – 전체 가이드

전방향 바코드 이미지를 **생성**해야 했지만 어떤 라이브러리를 선택해야 할지 몰랐던 적이 있나요? 당신만 그런 것이 아닙니다. 많은 물류 및 소매 프로젝트에서 DataBar Stacked Omnidirectional 형식은 컴팩트하고 고밀도 인코딩을 위한 비밀 소스입니다.  

좋은 소식은? **Aspose.BarCode**를 사용하면 몇 줄의 코드만으로 해당 바코드를 생성하고, 종횡비를 조정하며, PNG 파일을 바로 디스크에 저장할 수 있습니다. 아래에서는 **Aspose로 바코드 생성** 방법, 각 설정이 중요한 이유, 그리고 종횡비를 변경할 때 주의할 점을 정확히 보여드립니다.

---

## 이 튜토리얼에서 다루는 내용

1. 출력 폴더 설정.
2. DataBar Stacked Omnidirectional 생성기 인스턴스화.
3. 픽셀 크기와 종횡비 구성.
4. 바코드를 PNG 파일로 저장.
5. 다른 형식 및 엣지 케이스에 대한 예제 확장.

튜토리얼을 마치면 두 개의 서로 다른 바코드 이미지를 출력하는 실행 가능한 C# 콘솔 앱을 얻게 됩니다. 외부 도구 없이 순수 Aspose 코드만 사용합니다.

**필수 조건**

- .NET 6.0 SDK 이상 (코드는 .NET Framework 4.7.2에서도 작동합니다).
- Aspose.BarCode for .NET NuGet 패키지 (`Install-Package Aspose.BarCode`).
- 이미지를 쓸 수 있는 디스크상의 폴더.

이미 준비되었다면, 시작해봅시다.

---

## 단계 1: 출력 폴더 준비

먼저, 프로그램이 PNG 파일을 저장할 위치를 지정합니다. 경로를 하드코딩하는 것은 데모에서는 동작하지만, 실제 운영에서는 보통 설정 파일에서 읽어옵니다.

```csharp
using System;
using System.IO;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Step 1: Define the folder where the images will be saved
        string outputFolder = Path.Combine(Environment.CurrentDirectory, "Barcodes");
        Directory.CreateDirectory(outputFolder);   // ensures the folder exists
```

*왜 중요한가:* `Directory.CreateDirectory`는 멱등적이며, 폴더가 이미 존재해도 예외를 발생시키지 않아 try‑catch 블록이 필요 없습니다.

---

## 단계 2: DataBar Stacked Omnidirectional 생성기 만들기

이제 특정 인코드 타입과 샘플 데이터를 사용해 생성기를 초기화합니다. 문자열 `"(01)12345678901231"`은 14자리 GTIN에 대한 GS1 애플리케이션 식별자 구문을 따릅니다.

```csharp
        // Step 2: Create a DataBar Stacked Omnidirectional barcode generator with sample data
        BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
            EncodeTypes.DatabarStackedOmniDirectional,
            "(01)12345678901231");
```

*설명:* `EncodeTypes.DatabarStackedOmniDirectional`는 Aspose에 전방향 변형을 사용하도록 지시합니다. 이는 어느 방향에서든 읽을 수 있어 회전될 수 있는 작은 라벨에 적합합니다.

---

## 단계 3: 공통 바코드 매개변수 설정

이미지를 렌더링하기 전에 가장 작은 요소 크기(X‑Dimension)를 정의합니다. **2픽셀** 값은 파일 크기를 크게 늘리지 않으면서 선명한 이미지를 제공합니다.

```csharp
        // Step 3: Set common barcode parameters (pixel size of the smallest element)
        barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

*팁:* 인쇄용으로 해상도가 필요하면 3 또는 4로 올리세요. 단, X‑Dimension이 커지면 너비와 높이가 비례적으로 증가한다는 점을 기억하세요.

---

## 단계 4: 종횡비 15로 생성 및 저장

DataBar 계열은 **종횡비**를 조정할 수 있게 하며, 이는 높이와 너비의 비율을 제어합니다. **15**의 종횡비는 전방향 바코드의 일반적인 기본값입니다.

```csharp
        // Step 4: Generate a barcode with an aspect ratio of 15 and save it as PNG
        barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = 15;
        barcodeGenerator.Save(Path.Combine(outputFolder, "DatabarAspectRatio15.png"),
                              BarCodeImageFormat.Png);
```

*결과:* 2 × 1 cm 라벨에 편안히 들어가는 비교적 높은 바코드가 생성됩니다. PNG 형식은 무손실 품질을 유지해 후속 처리나 인쇄에 이상적입니다.

---

## 단계 5: 종횡비를 30으로 변경하고 다시 저장

더 납작한 바코드가 필요하신가요? `AspectRatio` 속성을 조정하고 `Save`를 다시 호출하면 됩니다. 생성기를 다시 만들 필요가 없습니다.

```csharp
        // Step 5: Change the aspect ratio to 30 and save the new image
        barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = 30;
        barcodeGenerator.Save(Path.Combine(outputFolder, "DatabarAspectRatio30.png"),
                              BarCodeImageFormat.Png);
    }
}
```

*왜 같은 생성기를 재사용하나요?* Aspose 객체는 가볍습니다; 속성을 변경하고 다시 저장하는 것이 새 인스턴스를 만드는 것보다 빠르며, 동일한 인코딩 설정(예: X‑Dimension)이 일관되게 유지됩니다.

---

## 전체 작업 예제

모든 코드를 합치면, 새 콘솔 프로젝트에 복사·붙여넣기 할 수 있는 완전하고 독립적인 프로그램이 아래에 있습니다.

```csharp
using System;
using System.IO;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Define output folder
        string outputFolder = Path.Combine(Environment.CurrentDirectory, "Barcodes");
        Directory.CreateDirectory(outputFolder);

        // Initialize generator with omnidirectional DataBar
        BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
            EncodeTypes.DatabarStackedOmniDirectional,
            "(01)12345678901231");

        // Common settings
        barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;

        // First image – aspect ratio 15
        barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = 15;
        barcodeGenerator.Save(Path.Combine(outputFolder, "DatabarAspectRatio15.png"),
                              BarCodeImageFormat.Png);
        Console.WriteLine("Saved: DatabarAspectRatio15.png");

        // Second image – aspect ratio 30
        barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = 30;
        barcodeGenerator.Save(Path.Combine(outputFolder, "DatabarAspectRatio30.png"),
                              BarCodeImageFormat.Png);
        Console.WriteLine("Saved: DatabarAspectRatio30.png");
    }
}
```

**예상 출력**

프로그램을 실행하면 `Barcodes` 하위 폴더가 생성되고 다음 파일이 포함됩니다:

- `DatabarAspectRatio15.png` – 더 높고 클래식한 모습.
- `DatabarAspectRatio30.png` – 더 납작해 넓은 라벨에 적합.

두 이미지 모두 동일한 GTIN 데이터를 표시하지만 시각적 비율만 다릅니다.

---

## 예제 확장 (엣지 케이스 및 변형)

### 1. 다양한 이미지 형식

Aspose는 PNG 외에도 BMP, JPEG, TIFF, SVG를 지원합니다. 열거형 값을 교체하면 됩니다:

```csharp
barcodeGenerator.Save(Path.Combine(outputFolder, "Databar.svg"),
                      BarCodeImageFormat.Svg);
```

SVG는 벡터 기반이므로 선명도를 잃지 않고 확대·축소할 수 있어 반응형 웹 앱에 유용합니다.

### 2. 색상 사용자 정의

어두운 배경에 흰색 바코드가 필요할 수 있습니다. `ForeColor`와 `BackColor`를 설정하세요:

```csharp
barcodeGenerator.Parameters.Barcode.ForeColor = System.Drawing.Color.White;
barcodeGenerator.Parameters.Barcode.BackColor = System.Drawing.Color.Black;
```

### 3. 잘못된 종횡비 처리

Aspose는 범위(보통 5‑50)를 검증합니다. 범위를 벗어난 값을 전달하면 `ArgumentException`이 발생합니다. 저장 호출을 try‑catch로 감싸 친절한 메시지를 제공하세요:

```csharp
try
{
    barcodeGenerator.Save(...);
}
catch (ArgumentException ex)
{
    Console.WriteLine($"Invalid aspect ratio: {ex.Message}");
}
```

### 4. 배치 생성

GTIN 목록이 있을 때, 반복문으로 각 항목을 처리하고 `CodeText`를 업데이트한 뒤 고유한 이름으로 파일을 저장합니다. 생성기 객체를 재사용하면 메모리 사용량을 낮게 유지할 수 있습니다.

---

## 일반적인 함정 및 전문가 팁

- **저장하기 전에 `XDimension` 설정을 절대 잊지 마세요**; 기본값(0.33 mm)은 저해상도 화면에서 흐릿한 이미지를 만들 수 있습니다.
- **종횡비는 높이 대비 너비**이며, 반대가 아닙니다. 숫자가 클수록 바코드가 세로로 *짧아집니다*.
- **파일 경로:** `Path.Combine`을 사용해 플랫폼별 구분자 문제를 피하세요—특히 코드가 Linux 컨테이너에서 실행될 경우.
- **라이선스:** Aspose.BarCode는 상용 제품입니다. 체험판 모드에서는 이미지에 워터마크가 표시됩니다. 프로덕션에서 놀라움을 방지하려면 초기에 라이선스를 등록하세요.

---

## 결론

이제 Aspose를 사용해 **전방향 바코드 이미지 생성** 방법, 종횡비 조정, PNG 파일 내보내기를 30줄 이하의 C# 코드로 구현하는 방법을 알게 되었습니다. 이 튜토리얼은 단계별 과정을 보여주고 각 설정이 중요한 이유를 설명했으며, 다양한 형식, 색상, 배치 처리와 같은 확장 방법도 다루었습니다.

다음 도전에 준비가 되셨나요? QR 코드를 생성하거나 바코드를 PDF에 삽입하거나 ASP.NET Core API에 출력물을 통합해 보세요. 동일한 **Aspose로 바코드 생성** 원칙이 모든 바코드 유형에 적용되므로 오늘 배운 내용을 재사용할 수 있습니다.

질문이 있거나 직접 만든 팁을 공유하고 싶다면 아래 댓글을 남겨 주세요—코딩 즐겁게!

## 다음에 배워야 할 내용은?

다음 튜토리얼들은 이 가이드에서 보여준 기술을 기반으로 하는 밀접한 주제를 다룹니다. 각 자료는 단계별 설명과 함께 완전한 코드 예제를 제공하여 추가 API 기능을 마스터하고 프로젝트에서 대체 구현 방식을 탐색하도록 돕습니다.

- [Aspose.BarCode for .NET을 사용해 사용자 정의 종횡비로 Aztec 바코드 생성하기](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)
- [Aspose Java로 바코드 생성 - 이미지 품질 조정](/barcode/english/java/image-manipulation/adjusting-image-quality-barcode/)
- [Aspose.BarCode를 사용해 Java에서 바코드 이미지 생성](/barcode/english/java/barcode-rendering-techniques/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}