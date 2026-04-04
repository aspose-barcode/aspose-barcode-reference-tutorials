---
date: 2026-01-15
description: Aspose.BarCode for .NET를 사용하여 DataMatrix 바코드를 C#으로 읽고 바코드 이미지를 C#으로 생성하는
  단계별 바코드 튜토리얼 가이드.
linktitle: DataMatrix Encoding Mode (Auto)
second_title: Aspose.BarCode .NET API
title: DataMatrix 바코드 읽기 C# – DataMatrix 모드 생성 (자동)
url: /ko/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-auto/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# DataMatrix 바코드 읽기 C# – DataMatrix 모드 (Auto) 생성

오늘날 빠르게 변화하는 디지털 환경에서 **DataMatrix 바코드 C# 읽기**를 빠르고 안정적으로 수행하는 것은 재고 추적부터 보안 문서 처리까지 모든 분야에서 필수적입니다. 이 튜토리얼에서는 Aspose.BarCode for .NET을 사용해 *Auto* 모드로 DataMatrix 바코드를 생성하고, 그 바코드를 C#에서 다시 읽는 방법을 단계별로 안내합니다. **바코드 튜토리얼 가이드**를 따라가든, 실용적인 코드 예제가 필요하든, 이 가이드를 마치면 여러분의 프로젝트에 바로 적용할 수 있는 완전한 솔루션을 얻게 됩니다.

## 빠른 답변
- **“Auto” 모드는 무엇을 하나요?** Aspose.BarCode가 데이터에 가장 적합한 인코딩 방식을 자동으로 선택합니다.  
- **필요한 라이브러리는?** Aspose.BarCode for .NET (무료 체험판 제공).  
- **같은 앱에서 바코드를 읽을 수 있나요?** 예 – `BarCodeReader`와 `DecodeType.DataMatrix`를 사용합니다.  
- **프로덕션에 라이선스가 필요합니까?** 상업적 사용을 위해서는 정식 라이선스가 필요합니다.  
- **지원되는 .NET 버전은?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## DataMatrix 바코드 C# 읽기란?
C#에서 DataMatrix 바코드를 읽는다는 것은 검은색·흰색 모듈로 구성된 2차원 매트릭스를 원본 텍스트 또는 데이터로 디코딩하는 것을 의미합니다. Aspose.BarCode는 저수준 이미지 처리를 추상화한 간단한 API를 제공하므로 비즈니스 로직에 집중할 수 있습니다.

## Aspose.BarCode로 바코드 이미지 C# 생성하는 이유
- **신뢰성:** 모든 DataMatrix 표준을 지원하고 최적의 인코딩을 자동으로 선택합니다.  
- **유연성:** 크기, ECI 인코딩, 이미지 포맷을 완벽히 제어할 수 있습니다.  
- **크로스‑플랫폼:** .NET Framework, .NET Core, .NET 5+ 애플리케이션에서 모두 동작합니다.  

## 사전 준비

1. **.NET 환경** – 최신 .NET 런타임을 [.NET 웹사이트](https://dotnet.microsoft.com/download/dotnet)에서 설치합니다.  
2. **Aspose.BarCode for .NET** – [Aspose.BarCode 웹사이트](https://releases.aspose.com/barcode/net/)에서 라이브러리를 다운로드합니다.  

## 네임스페이스 가져오기

```csharp
using Aspose.BarCode.BarCodeRecognition;
using Aspose.BarCode.Generation;
using System;
using System.Drawing;
```

네임스페이스를 추가했으니 이제 코드를 단계별로 살펴보겠습니다.

## 1단계: 디렉터리 경로 설정

```csharp
string path = "Your Directory Path";
```

`"Your Directory Path"`를 생성된 PNG(또는 다른 포맷)를 저장할 폴더 경로로 교체하세요.

## 2단계: Auto 모드로 DataMatrix 바코드 생성

```csharp
using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.DataMatrix, "Aspose常に先を行く"))
{
    generator.Parameters.Barcode.XDimension.Pixels = 4;
    generator.Parameters.Barcode.DataMatrix.DataMatrixEncodeMode = DataMatrixEncodeMode.Auto;
    generator.Parameters.Barcode.DataMatrix.ECIEncoding = ECIEncodings.UTF8;
    Bitmap bitmap = generator.GenerateBarCodeImage();
}
```

`DataMatrixEncodeMode.Auto` 설정을 사용하면 라이브러리가 제공된 텍스트에 가장 적합한 인코딩을 자동으로 결정합니다. 샘플 텍스트를 여러분이 **바코드 이미지 C# 생성**하고 싶은 문자열로 자유롭게 교체하세요.

## 3단계: 바코드 읽기 (DataMatrix 바코드 C# 읽기)

```csharp
using (BarCodeReader reader = new BarCodeReader(bitmap, DecodeType.DataMatrix))
{
    reader.ReadBarCodes();
    Console.WriteLine(reader.FoundBarCodes[0].CodeText);
}
```

이 스니펫은 방금 생성한 이미지를 디코딩하고 원본 텍스트를 콘솔에 출력합니다. 생성부터 읽기까지 전체 라운드‑트립을 보여줍니다.

## 일반적인 문제와 해결책

| 문제 | 원인 | 해결 방법 |
|------|------|-----------|
| **바코드가 감지되지 않음** | 이미지 해상도가 낮음 | `XDimension.Pixels` 값을 늘리세요(예: 6) |
| **깨진 문자** | 잘못된 ECI 인코딩 | 데이터에 맞는 `ECIEncoding`을 설정하세요(UTF‑8, ASCII 등) |
| **`ReadBarCodes` 호출 시 예외 발생** | 읽기 전에 Bitmap이 해제됨 | 읽기가 끝날 때까지 `Bitmap` 인스턴스를 유지하세요 |

## 자주 묻는 질문

**Q: DataMatrix 인코딩 모드 “Auto”란 무엇인가요?**  
A: 제공된 데이터에 가장 적합한 인코딩 방식을 Aspose.BarCode가 자동으로 선택하도록 하여 **DataMatrix 바코드 생성 방법**을 단순화합니다.

**Q: 생성된 바코드의 크기를 사용자 정의할 수 있나요?**  
A: 예 – `generator.Parameters.Barcode.XDimension.Pixels` 값을 조정하면 모듈 크기를 변경할 수 있습니다.

**Q: Aspose.BarCode for .NET을 상업적으로 사용할 수 있나요?**  
A: 물론입니다. [구매 웹사이트](https://purchase.aspose.com/buy)에서 라이선스를 구매하세요.

**Q: 무료 체험판이 있나요?**  
A: 예, [이 링크](https://releases.aspose.com/)에서 무료 체험판을 이용해 Aspose.BarCode를 살펴볼 수 있습니다.

**Q: DataMatrix 바코드에 사용할 수 있는 인코딩 옵션은 무엇인가요?**  
A: Aspose.BarCode는 UTF‑8, ASCII 등 다양한 ECI 인코딩을 지원합니다; 원하는 값을 `ECIEncoding`을 통해 설정하면 됩니다.

## 결론

이제 **DataMatrix 바코드 C# 읽기**와 Auto 모드로 바코드 생성, 그리고 결과 검증까지 포함된 완전한 프로덕션‑레디 예제를 보유하게 되었습니다. 다양한 텍스트, 크기, ECI 설정을 실험해 보시고, 보다 깊은 커스터마이징이 필요하면 공식 [문서](https://reference.aspose.com/barcode/net/)를 참고하세요.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**마지막 업데이트:** 2026-01-15  
**테스트 환경:** Aspose.BarCode 24.12 for .NET  
**작성자:** Aspose  

---