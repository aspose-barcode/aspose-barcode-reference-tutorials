---
date: 2026-05-30
description: Aspose.BarCode for .NET를 사용하여 사용자 정의 DataMatrix 종횡비로 바코드 PNG를 만드는 방법을
  배웁니다. 바코드 생성 및 크기 맞춤을 위한 단계별 가이드.
keywords:
- create barcode png
- generate datamatrix barcode
- asp.net barcode generation
- barcode generation visual studio
linktitle: DataMatrix 종횡비 맞춤
schemas:
- author: Aspose
  dateModified: '2026-05-30'
  description: Learn how to create barcode PNG with a custom DataMatrix aspect ratio
    using Aspose.BarCode for .NET. Step-by-step guide for barcode generation and size
    customization.
  headline: Create Barcode PNG – DataMatrix Aspect Ratio – Aspose.BarCode
  type: TechArticle
- description: Learn how to create barcode PNG with a custom DataMatrix aspect ratio
    using Aspose.BarCode for .NET. Step-by-step guide for barcode generation and size
    customization.
  name: Create Barcode PNG – DataMatrix Aspect Ratio – Aspose.BarCode
  steps:
  - name: Set Up Your Project
    text: Create a new console or Windows Forms project in Visual Studio and add a
      reference to the Aspose.BarCode DLL.
  - name: Initialize a Barcode Generator
    text: 'Instantiate it with the DataMatrix symbology and the data you want to encode:
      `BarcodeGenerator` creates a barcode image from the specified symbology and
      data. > This line creates a generator ready to produce a DataMatrix barcode
      that contains the sample text.'
  - name: Customize Aspect Ratio and Save PNG Files
    text: 'Now you can change the **aspect ratio** and save each version as a PNG
      image: `AspectRatio` sets the width‑to‑height proportion of the DataMatrix modules.
      `Save` writes the generated barcode image to a file in the chosen format. -
      The first call creates a square‑proportioned barcode (`AspectRatio = '
  type: HowTo
- questions:
  - answer: Yes, many 2‑D barcodes (e.g., QR, PDF417) support aspect‑ratio adjustments
      through their specific parameter objects.
    question: Can I customize the aspect ratio of other barcode types using Aspose.BarCode
      for .NET?
  - answer: Yes, you can access a free trial of Aspose.BarCode for .NET [here](https://releases.aspose.com/).
    question: Is there a free trial available for Aspose.BarCode for .NET?
  - answer: You can purchase a license on the Aspose website [here](https://purchase.aspose.com/buy).
    question: Where can I purchase a license for Aspose.BarCode for .NET?
  - answer: Yes, it works with .NET Framework 4.x, .NET Core 3.1+, and the latest
      .NET releases.
    question: Is Aspose.BarCode for .NET compatible with different .NET Framework
      versions?
  - answer: Absolutely – PNG, JPEG, BMP, GIF, TIFF, SVG, and PDF are all supported
      out of the box.
    question: Can I generate barcodes in different formats with Aspose.BarCode for
      .NET?
  type: FAQPage
second_title: Aspose.BarCode .NET API
title: 바코드 PNG 만들기 – DataMatrix 종횡비 – Aspose.BarCode
url: /ko/net/datamatrix-barcode-configuration/datamatrix-aspect-ratio-customization/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 바코드 PNG 만들기 – DataMatrix 종횡비 – Aspose.BarCode

맞춤형 DataMatrix 종횡비를 사용하여 **barcode PNG**를 생성하는 것은 특정 레이아웃 제약에 맞는 **barcode PNG** 파일을 만들어야 할 때 흔히 요구되는 작업입니다. 이 튜토리얼에서는 Aspose.BarCode for .NET을 사용하여 **barcode PNG** 파일을 **생성**하는 정확한 단계들을 안내하고, 종횡비를 조정하고 싶은 이유를 설명하며, 애플리케이션에 맞게 출력물을 미세 조정하는 방법을 보여드립니다.

## 빠른 답변
- **“aspect ratio”(종횡비)가 무엇을 제어하나요?** DataMatrix 모듈의 가로‑세로 비율을 정의합니다.  
- **PNG, JPEG, 또는 SVG를 출력할 수 있나요?** 예 – `Save` 메서드는 PNG, JPEG, BMP, GIF, TIFF, SVG 및 PDF를 지원합니다.  
- **이 기능에 라이선스가 필요합니까?** 무료 체험판은 개발에 사용할 수 있지만, 프로덕션에서는 정식 라이선스가 필요합니다.  
- **지원되는 .NET 버전은 무엇인가요?** .NET Framework 4.x, .NET Core 3.1+, .NET 5/6/7.  
- **몇 개의 aspect‑ratio 값이 유효한가요?** 양수 실수이면 모두 가능하며, 일반적인 값은 0.5 – 2.0입니다.

## DataMatrix 바코드란 무엇이며 왜 종횡비를 조정해야 하나요?
DataMatrix 바코드는 큰 양의 데이터를 작은 정사각형에 저장하는 2차원 매트릭스 코드입니다. **aspect ratio**를 조정하면 모듈을 가로로 늘리거나 압축할 수 있어, 스캔 신뢰성을 손상시키지 않으면서 좁은 열이나 넓은 라벨에 바코드를 맞출 때 유용합니다.

## 왜 Aspose.BarCode를 사용하여 barcode PNG를 만들까요?
Aspose.BarCode는 **7가지 이미지 형식** — PNG, JPEG, BMP, GIF, TIFF, SVG, PDF — 을 지원하며, 메모리 내에서 **50개 이상의 입력 및 출력 형식**을 처리하여 전체 파일을 로드하지 않고도 수백 페이지 문서를 다룰 수 있습니다. 이 라이브러리는 한 줄의 코드로 DataMatrix 바코드를 생성할 수 있는 유창한 API를 제공하여 픽셀 단위의 정확한 렌더링과 완전한 .NET 호환성을 보장합니다.

## 사전 요구 사항

DataMatrix 종횡비를 사용자 정의하기 전에, 다음 사전 요구 사항이 준비되어 있는지 확인하십시오:

1. **Visual Studio** – 최신 버전이면 어느 것이든 괜찮습니다.  
2. **Aspose.BarCode for .NET** – [여기](https://releases.aspose.com/barcode/net/)에서 다운로드하십시오.  
3. 다른 Aspose 제품 릴리스를 [여기](https://releases.aspose.com/)에서도 확인할 수 있습니다.  
4. **.NET Framework / .NET Core** – 프로젝트가 지원되는 버전을 대상으로 해야 합니다.

## 네임스페이스 가져오기

먼저 C# 프로젝트에서 필요한 네임스페이스를 가져와야 합니다:

`using Aspose.BarCode.Generation;`은 바코드 생성 클래스를 포함하는 네임스페이스를 가져옵니다.  

```csharp
using Aspose.BarCode.Generation;
```

> **팁:** 이 `using` 구문을 파일 상단에 유지하면 `BarcodeGenerator` 클래스를 언제든 사용할 수 있습니다.

## 사용자 지정 종횡비로 barcode PNG 만들기

`BarcodeGenerator`를 로드하고, DataMatrix 유형을 설정한 뒤, `AspectRatio` 속성을 조정하고 `Save`를 호출합니다. 이 한 줄 패턴은 지정한 비율을 반영한 barcode PNG를 생성하며, 라이브러리는 모듈 스케일링과 quiet zone을 자동으로 처리합니다.

`BarcodeGenerator`는 지정된 심볼과 데이터로 바코드 이미지를 생성합니다.

### 단계 1: 프로젝트 설정
Visual Studio에서 새 콘솔 또는 Windows Forms 프로젝트를 만들고 Aspose.BarCode DLL에 대한 참조를 추가하십시오.

### 단계 2: Barcode Generator 초기화
DataMatrix 심볼과 인코딩하려는 데이터를 사용하여 인스턴스화합니다:

`BarcodeGenerator`는 지정된 심볼과 데이터로 바코드 이미지를 생성합니다.  

```csharp
using (BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.DataMatrix, "Åspóse.Barcóde©"))
```

> 이 라인은 샘플 텍스트를 포함하는 DataMatrix 바코드를 생성할 준비가 된 제너레이터를 만듭니다.

### 단계 3: 종횡비 사용자 지정 및 PNG 파일 저장
이제 **aspect ratio**를 변경하고 각 버전을 PNG 이미지로 저장할 수 있습니다:

`AspectRatio`는 DataMatrix 모듈의 가로‑세로 비율을 설정합니다.  
`Save`는 생성된 바코드 이미지를 선택한 형식의 파일로 저장합니다.  

```csharp
gen.Parameters.Barcode.DataMatrix.AspectRatio = 1;
gen.Save($"{path}DataMatrixAspectRatio1.png", BarCodeImageFormat.Png);

gen.Parameters.Barcode.DataMatrix.AspectRatio = 0.5f;
gen.Save($"{path}DataMatrixAspectRatio0.5.png", BarCodeImageFormat.Png);
```

- 첫 번째 호출은 정사각형 비율의 바코드(`AspectRatio = 1`)를 생성합니다.  
- 두 번째 호출은 바코드를 가로로 압축(`AspectRatio = 0.5`)하여 더 넓은 모습을 제공합니다.

이제 서로 다른 종횡비를 가진 두 개의 **barcode PNG** 파일이 준비되어 보고서, 라벨 또는 UI 요소에 사용할 수 있습니다.

## 일반적인 문제 및 해결책
| 문제 | 해결책 |
|-------|----------|
| **생성된 이미지가 흐릿함** | 저장하기 전에 `Resolution` 매개변수를 증가시킵니다 (`gen.Parameters.ImageResolution = 300`). |
| **바코드가 스캔되지 않음** | 종횡비가 0.5 – 2.0 범위 내에 유지되고 충분한 quiet zone이 있는지 확인합니다 (`gen.Parameters.Barcode.CodeTextParameters.Margin`). |
| **파일 경로 오류** | `Path.Combine`를 사용하여 출력 경로를 만들고 폴더가 존재하는지 확인합니다. |

## 자주 묻는 질문

**Q: Aspose.BarCode for .NET을 사용하여 다른 바코드 유형의 종횡비를 사용자 지정할 수 있나요?**  
A: 예, 많은 2‑D 바코드(예: QR, PDF417)는 해당 파라미터 객체를 통해 종횡비 조정을 지원합니다.

**Q: Aspose.BarCode for .NET의 무료 체험판이 있나요?**  
A: 예, Aspose.BarCode for .NET의 무료 체험판은 [여기](https://releases.aspose.com/)에서 이용할 수 있습니다.

**Q: Aspose.BarCode for .NET 라이선스는 어디서 구매할 수 있나요?**  
A: Aspose 웹사이트에서 라이선스를 구매할 수 있습니다 [여기](https://purchase.aspose.com/buy).

**Q: Aspose.BarCode for .NET은 다양한 .NET Framework 버전과 호환되나요?**  
A: 예, .NET Framework 4.x, .NET Core 3.1+, 최신 .NET 릴리스와 모두 작동합니다.

**Q: Aspose.BarCode for .NET으로 다양한 형식의 바코드를 생성할 수 있나요?**  
A: 물론입니다 – PNG, JPEG, BMP, GIF, TIFF, SVG, PDF 모두 기본적으로 지원됩니다.

## 결론

Aspose.BarCode for .NET을 사용하면 DataMatrix 바코드의 **aspect ratio**를 사용자 지정하고 **barcode PNG** 파일을 만드는 것이 간단합니다. 위 단계들을 따르면 프로젝트의 정확한 레이아웃 요구 사항을 충족하는 완벽한 크기의 바코드를 생성할 수 있습니다. `Resolution`, `Margin`, `Color`와 같은 추가 파라미터를 탐색하여 출력을 더욱 맞춤화하고, Visual Studio에서 스캔 친화적인 애플리케이션을 구축할 때 `generate datamatrix barcode` 기능을 고려하십시오.

더 자세히 살펴보려면 공식 [documentation](https://reference.aspose.com/barcode/net/)을 확인하거나 [Aspose.BarCode 포럼](https://forum.aspose.com/c/barcode/13)에서 커뮤니티에 참여하십시오.

---

**마지막 업데이트:** 2026-05-30  
**테스트 환경:** Aspose.BarCode 24.12 for .NET  
**작성자:** Aspose  

{{< blocks/products/products-backtop-button >}}

## 관련 튜토리얼

- [DataMatrix 바코드 생성 – Aspose.BarCode 전문가 가이드](/barcode/net/datamatrix-barcode-configuration/)
- [Aspose.BarCode for .NET으로 DataMatrix 바코드 (ECC 200) 생성 방법](/barcode/net/datamatrix-barcode-configuration/datamatrix-ecc-200-configuration/)
- [Aspose.BarCode for .NET으로 ASCII에서 DataMatrix 인코딩 마스터](/barcode/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-ascii/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}