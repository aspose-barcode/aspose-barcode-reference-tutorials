---
date: 2026-06-09
description: Aspose.BarCode for .NET을 사용하여 ASCII 모드에서 DataMatrix 바코드를 생성하는 방법을 배웁니다.
  이 가이드는 C#으로 바코드를 빠르게 생성하는 방법을 보여줍니다.
keywords:
- create datamatrix barcode
- generate barcode c#
- how to encode barcode
- barcode generator example
linktitle: DataMatrix 인코딩 모드 (ASCII)
schemas:
- author: Aspose
  dateModified: '2026-06-09'
  description: Learn how to create DataMatrix barcode in ASCII mode using Aspose.BarCode
    for .NET. This guide shows how to generate barcode C# quickly.
  headline: Create DataMatrix barcode in ASCII mode with Aspose.BarCode for .NET
  type: TechArticle
- description: Learn how to create DataMatrix barcode in ASCII mode using Aspose.BarCode
    for .NET. This guide shows how to generate barcode C# quickly.
  name: Create DataMatrix barcode in ASCII mode with Aspose.BarCode for .NET
  steps:
  - name: '**Development Environment** – Visual Studio, Rider, or any C#‑compatible
      IDE.'
    text: '**Development Environment** – Visual Studio, Rider, or any C#‑compatible
      IDE.'
  - name: '**Aspose.BarCode for .NET** – Download the latest package from [here](https://releases.aspose.com/barcode/net/).'
    text: '**Aspose.BarCode for .NET** – Download the latest package from [here](https://releases.aspose.com/barcode/net/).'
  - name: '**Basic C# knowledge** – Familiarity with .NET project structure will help
      you follow the steps quickly.'
    text: '**Basic C# knowledge** – Familiarity with .NET project structure will help
      you follow the steps quickly.'
  - name: '**Other Aspose products** can be found [here](https://releases.aspose.com/).'
    text: '**Other Aspose products** can be found [here](https://releases.aspose.com/).'
  type: HowTo
- questions:
  - answer: Yes, a valid Aspose license is required for production use; a free trial
      is available for evaluation.
    question: Can I use this in a commercial application?
  - answer: Absolutely – Aspose.BarCode fully supports .NET Core 3.1+, .NET 5, .NET
      6, and later versions.
    question: Does the library work with .NET Core?
  - answer: Up to 2,335 alphanumeric characters fit in a single DataMatrix symbol
      when using ASCII encoding.
    question: How many characters can I encode in ASCII mode?
  - answer: Yes, adjust `generator.Parameters.Image.ForeColor` and `BackColor` to
      any `System.Drawing.Color` value.
    question: Can I change the barcode’s foreground or background color?
  - answer: The official documentation contains dozens of samples covering custom
      sizes, colors, and error‑correction levels.
    question: Where can I find more advanced examples?
  type: FAQPage
second_title: Aspose.BarCode .NET API
title: Aspose.BarCode for .NET을 사용하여 ASCII 모드에서 DataMatrix 바코드 생성
url: /ko/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-ascii/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.BarCode for .NET를 사용하여 ASCII 모드에서 DataMatrix 바코드 생성

## 소개

효율적인 ASCII 인코딩을 사용하는 **DataMatrix 바코드** 이미지를 만들 준비가 되셨나요? 이 튜토리얼에서는 Aspose.BarCode for .NET을 사용하여 ASCII 모드에서 DataMatrix 바코드를 생성하는 방법을 배웁니다. 프로젝트 설정부터 최종 이미지를 저장하는 단계까지 모두 안내하므로 C# 애플리케이션에 몇 분 만에 바코드 생성을 추가할 수 있습니다.

## 빠른 답변
- **.NET에서 DataMatrix에 가장 적합한 라이브러리는 무엇인가요?** Aspose.BarCode for .NET  
- **코드 라인은 몇 줄 정도 필요합니까?** 기본 ASCII 바코드의 경우 약 5‑7줄  
- **라이선스가 필요합니까?** 개발용으로는 무료 체험판으로 충분하지만, 운영 환경에서는 라이선스가 필요합니다  
- **지원되는 플랫폼은?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7  
- **크기나 색상을 변경할 수 있나요?** 예, Aspose.BarCode는 치수와 전경/배경 색상을 설정할 수 있는 속성을 제공합니다  

## DataMatrix 바코드란?
DataMatrix는 텍스트와 바이너리 데이터를 컴팩트한 정사각형 패턴에 저장하는 2차원 바코드입니다.  
DataMatrix 바코드는 검은색과 흰색 모듈의 격자에 정보를 인코딩하며, 하나의 심볼에 최대 2,335개의 영숫자 문자를 담을 수 있습니다. 제조, 물류, 의료 분야에서 널리 사용되며, 매우 작은 크기로 인쇄해도 높은 스캔 가능성을 유지합니다.

## ASCII 모드에서 DataMatrix 바코드 만드는 방법
Aspose.BarCode 네임스페이스를 로드하고 `BarcodeGenerator`를 인스턴스화한 뒤, `EncodeMode`를 **EncodeMode.ASCII** 로 설정하고 데이터 문자열을 할당한 뒤 `Save`를 호출해 이미지 파일을 저장합니다. 이 방법으로 몇 줄의 C# 코드만으로 ASCII 전용 인코딩을 적용한 완벽히 규격에 맞는 DataMatrix 바코드를 만들 수 있습니다.

## DataMatrix에 ASCII 인코딩을 사용하는 이유
ASCII 모드는 일반 텍스트 데이터에 가장 효율적인 기본 인코딩으로, 영숫자 문자열에 대해 가능한 가장 작은 심볼 크기를 제공합니다. 128개의 ASCII 문자 전체를 지원하며, 확장 모드보다 데이터 처리 속도가 빠르고, 표준 ASCII 심볼을 기대하는 레거시 스캐너와의 호환성이 최상입니다.

## 사전 요구 사항

1. **Development Environment** – Visual Studio, Rider, 또는 C#을 지원하는 모든 IDE.  
2. **Aspose.BarCode for .NET** – 최신 패키지를 [여기](https://releases.aspose.com/barcode/net/)에서 다운로드합니다.  
   - Documentation: [Aspose.BarCode for .NET 문서](https://reference.aspose.com/barcode/net/)  
   - Community help: [Aspose.BarCode 포럼](https://forum.aspose.com/c/barcode/13)  
3. **Basic C# knowledge** – .NET 프로젝트 구조에 익숙하면 단계 진행이 수월합니다.  
4. **Other Aspose products** can be found [여기](https://releases.aspose.com/).

## 네임스페이스 가져오기

To start, add the required `using` directives at the top of your C# file:

```csharp
using Aspose.BarCode.Generation;
using System.Drawing;
```

These namespaces give you access to the `BarcodeGenerator` class and the image‑related types needed for saving the output.

## 단계 1: 디렉터리 만들기

Choose a folder where the generated barcode images will be stored. Replace `"Your Directory Path"` with an absolute or relative path that exists on your machine.

```csharp
string outputDir = @"C:\Barcodes";
if (!System.IO.Directory.Exists(outputDir))
{
    System.IO.Directory.CreateDirectory(outputDir);
}
```

The code ensures the directory exists before attempting to write any files, preventing runtime errors.

## 단계 2: ASCII 모드로 데이터 인코딩

The `BarcodeGenerator` class creates and configures barcode images. The `DataMatrixEncodeMode` enumeration selects the encoding algorithm for DataMatrix symbols.

```csharp
// Initialise the generator with the data you want to encode
BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.DataMatrix, "1234567890");

// Set the encoding mode to ASCII for optimal size
generator.Parameters.Barcode.DataMatrixEncodeMode = DataMatrixEncodeMode.ASCII;

// Optional: adjust image dimensions or colors here
generator.Parameters.Image.Width = 200;
generator.Parameters.Image.Height = 200;

// Save the barcode as a PNG file
string filePath = System.IO.Path.Combine(outputDir, "datamatrix_ascii.png");
generator.Save(filePath, BarCodeImageFormat.Png);
```

After running the code, you’ll find `datamatrix_ascii.png` in the folder you specified. The image contains a DataMatrix barcode that encodes the string `"1234567890"` using the compact ASCII mode.

## 일반적인 문제 및 해결책

- **File‑access errors** – Ensure the application has write permissions to the target folder. Running Visual Studio as Administrator can resolve permission issues on Windows.  
- **Incorrect symbol size** – If the barcode appears too large or too small, tweak `generator.Parameters.Image.Width` and `Height` or let Aspose automatically calculate the optimal size by omitting those properties.  
- **Unsupported characters** – ASCII mode only accepts characters in the 0‑127 range. For Unicode data, switch to `DataMatrixEncodeMode.Base256` or another suitable mode.

## 자주 묻는 질문

**Q: Can I use this in a commercial application?**  
A: Yes, a valid Aspose license is required for production use; a free trial is available for evaluation.

**Q: Does the library work with .NET Core?**  
A: Absolutely – Aspose.BarCode fully supports .NET Core 3.1+, .NET 5, .NET 6, and later versions.

**Q: How many characters can I encode in ASCII mode?**  
A: Up to 2,335 alphanumeric characters fit in a single DataMatrix symbol when using ASCII encoding.

**Q: Can I change the barcode’s foreground or background color?**  
A: Yes, adjust `generator.Parameters.Image.ForeColor` and `BackColor` to any `System.Drawing.Color` value.

**Q: Where can I find more advanced examples?**  
A: The official documentation contains dozens of samples covering custom sizes, colors, and error‑correction levels.

## FAQ

### Q1: C# 외의 다른 프로그래밍 언어와 함께 Aspose.BarCode for .NET을 사용할 수 있나요?
A1: Aspose.BarCode는 여러 프로그래밍 언어를 지원하지만, 이 튜토리얼은 C#에 초점을 맞추고 있습니다.

### Q2: DataMatrix 바코드에서 사용할 수 있는 다양한 인코딩 모드는 무엇인가요?
A2: DataMatrix 바코드는 ASCII, C40, Text, Base256 등 다양한 인코딩 모드를 지원합니다. 각 모드는 데이터 유형에 따라 최적화됩니다.

### Q3: 생성된 바코드의 크기와 색상 등 외관을 맞춤 설정할 수 있나요?
A3: 예, Aspose.BarCode는 크기, 색상 및 기타 외관을 맞춤 설정할 수 있는 다양한 매개변수를 제공합니다.

### Q4: Aspose.BarCode for .NET의 무료 체험 버전이 있나요?
A4: 예, [여기](https://releases.aspose.com/)에서 무료 체험판을 이용해 볼 수 있습니다.

### Q5: Aspose.BarCode for .NET 라이선스는 어디서 구매할 수 있나요?
A5: Aspose 웹사이트 [여기](https://purchase.aspose.com/buy)에서 라이선스를 구매할 수 있습니다.

---

**마지막 업데이트:** 2026-06-09  
**테스트 환경:** Aspose.BarCode 24.11 for .NET  
**작성자:** Aspose

## 관련 튜토리얼

- [Aspose.BarCode for .NET를 사용한 바이트 단위 DataMatrix 인코딩](/barcode/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-bytes/)
- [DataMatrix 바코드 읽기 C# – DataMatrix 모드 자동 생성](/barcode/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-auto/)
- [Aspose.BarCode for .NET를 사용한 DataMatrix 바코드 (ECC 200) 생성 방법](/barcode/net/datamatrix-barcode-configuration/datamatrix-ecc-200-configuration/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< blocks/products/products-backtop-button >}}

```csharp
using Aspose.BarCode.Generation;
```

```csharp
string path = "Your Directory Path";
```

```csharp
System.Console.WriteLine("DataMatrixEncodeModeASCII:");

using (BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.DataMatrix, "Aspose"))
{
    // Set the X-dimension (size) of the barcode in pixels
    gen.Parameters.Barcode.XDimension.Pixels = 4;
    
    // Set the encoding mode to ASCII
    gen.Parameters.Barcode.DataMatrix.DataMatrixEncodeMode = DataMatrixEncodeMode.ASCII;
    
    // Save the barcode as a PNG image
    gen.Save($"{path}DataMatrixEncodeModeASCII.png", BarCodeImageFormat.Png);
}
```

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}