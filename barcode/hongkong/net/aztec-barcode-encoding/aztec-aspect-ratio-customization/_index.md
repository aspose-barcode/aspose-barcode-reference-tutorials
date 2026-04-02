---
date: 2025-12-30
description: 了解如何使用 Aspose.BarCode for .NET 產生 Aztec 條碼並自訂其長寬比。為您的 .NET 應用程式打造彈性且高品質的條碼。
linktitle: Aztec Aspect Ratio Customization
second_title: Aspose.BarCode .NET API
title: 如何使用 Aspose.BarCode for .NET 生成具有自訂長寬比的 Aztec 條碼
url: /zh-hant/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何使用 Aspose.BarCode for .NET 產生自訂長寬比的 Aztec 條碼

在本教學中，您將學習如何 **產生 Aztec 條碼** 圖片，並微調其長寬比以符合 .NET 應用程式的設計需求。無論您需要完美正方形的條碼，或是用於行動票證的較寬版面，Aspose.BarCode for .NET 都能讓此過程簡單且可靠。

## 快速解答
- **「長寬比」控制什麼？** 它定義條碼的寬度與高度比例。  
- **哪個類別用於建立條碼？** 來自 Aspose.BarCode 函式庫的 `BarcodeGenerator`。  
- **我可以設定任意長寬比值嗎？** 可以，任何正的浮點數皆可（例如 1、0.5、2）。  
- **開發時需要授權嗎？** 測試可使用臨時授權；正式上線則需完整授權。  
- **支援的輸出格式？** PNG、JPEG、BMP、SVG 等，透過 `BarCodeImageFormat` 可取得更多格式。

## 前置條件

在深入自訂 Aztec 條碼長寬比之前，請確保已具備以下前置條件：

1. **Aspose.BarCode for .NET** – 需要先安裝此函式庫。若尚未取得，可從 [download link](https://releases.aspose.com/barcode/net/) 下載。  
2. **.NET 開發環境** – 如 Visual Studio 等可正常使用的 IDE。  
3. **C# 基礎知識** – 本指南假設您已熟悉 C# 語法。

## 匯入命名空間

首先，匯入所需的命名空間，以便存取條碼產生相關類別：

```csharp
using Aspose.BarCode.Generation;
```

## 設定輸出目錄

定義儲存產生條碼圖片的資料夾。將 `"Your Directory Path"` 替換為您機器上的實際路徑：

```csharp
string path = "Your Directory Path";
```

## 建立 BarcodeGenerator 實例

建立 `BarcodeGenerator` 實例，並指定使用 Aztec 條碼。範例文字 `"Åspóse.Barcóde©"` 僅作示範，您可以編碼任何需要的字串：

```csharp
BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.Aztec, "Åspóse.Barcóde©");
```

## 自訂長寬比

`AspectRatio` 屬性讓您控制條碼的形狀。

### 設定長寬比為 1（正方形）

長寬比為 1 時會產生完美正方形的 Aztec 條碼：

```csharp
gen.Parameters.Barcode.Aztec.AspectRatio = 1;
```

儲存正方形條碼：

```csharp
gen.Save($"{path}AztecAspectRatio1.png", BarCodeImageFormat.Png);
```

### 設定長寬比為 0.5（較寬）

如果您希望條碼寬度大於高度，請將長寬比設定為 0.5：

```csharp
gen.Parameters.Barcode.Aztec.AspectRatio = 0.5f;
```

儲存較寬的條碼：

```csharp
gen.Save($"{path}AztecAspectRatio0.5.png", BarCodeImageFormat.Png);
```

## 為何要自訂 Aztec 條碼的長寬比？

- **設計彈性** – 讓條碼符合 UI 元件或印刷標籤。  
- **掃描可靠性** – 某些掃描器在特定比例下表現較佳。  
- **品牌一致性** – 使條碼外觀與您的視覺識別保持一致。

## 常見陷阱與提示

- **不要設定為零或負值的長寬比** – 會拋出例外。  
- **請確保所有 `Save` 呼叫使用相同的 `path` 變數**，否則圖片可能會儲存到意外的位置。  
- **專業提示：** 使用您預計使用的實際掃描器測試產生的條碼，因為極端比例可能影響可讀性。

## 結論

現在您已了解如何使用 Aspose.BarCode for .NET **產生 Aztec 條碼** 圖片並調整其長寬比。只需幾行 C# 程式碼，即可產生符合任何應用情境的正方形或寬版條碼。

如有任何問題，請參閱官方文件或社群論壇：

- [Aspose.BarCode for .NET documentation](https://reference.aspose.com/barcode/net/)  
- [Aspose.BarCode forum](https://forum.aspose.com/c/barcode/13)  

## 常見問答

### Q1: Aztec 條碼的用途是什麼？

A1: Aztec 條碼常用於在各種應用中編碼資料，包括文件管理、票務及交通等。

### Q2: 我可以自訂 Aztec 條碼中編碼的資料嗎？

A2: 可以，您可以自訂 Aztec 條碼的編碼資料，儲存文字、URL 等資訊。

### Q3: Aspose.BarCode for .NET 是否相容於不同的 .NET 版本？

A3: 是的，Aspose.BarCode for .NET 相容於多種 .NET 版本，適用於各類 .NET 開發專案。

### Q4: 如何在 Web 應用程式中使用 Aspose.BarCode 產生 Aztec 條碼？

A4: 您可在 Web 應用程式中使用 Aspose.BarCode for .NET，將其整合至程式碼中，方式類似本教學中提供的桌面應用範例。

### Q5: 從哪裡可以取得 Aspose.BarCode for .NET 的臨時授權？

A5: 若需測試或評估用的臨時授權，可從 [here](https://purchase.aspose.com/temporary-license/) 取得。

## 常見問題

**Q: 更改長寬比會影響掃描速度嗎？**  
A: 通常掃描速度不變，但極端比例可能需要掃描器調整焦距，略微影響效能。

**Q: 我可以使用其他影像格式，如 JPEG 或 SVG 嗎？**  
A: 當然可以，只要將 `BarCodeImageFormat.Png` 替換為想要的格式列舉值即可。

**Q: 開發版需要授權嗎？**  
A: 臨時授權足以用於開發與測試，正式上線建議使用完整授權。

**Q: 如何處理編碼文字中的 Unicode 字元？**  
A: Aspose.BarCode 完全支援 Unicode。範例 `"Åspóse.Barcóde©"` 即展示此功能。

---

**Last Updated:** 2025-12-30  
**Tested With:** Aspose.BarCode 24.11 for .NET  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}