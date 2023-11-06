---
title: GS1 Coupon UPC-A Databar Configuration
linktitle: GS1 Coupon UPC-A Databar Configuration
second_title: Aspose.BarCode .NET API
description: 
type: docs
weight: 13
url: /net/gs1-barcode-encoding/gs1-coupon-upc-a-databar-configuration/
---

## Complete Source Code
```csharp
//Copyright(c) 2001-2021 Aspose Pty Ltd.All rights reserved.
//https://github.com/aspose-barcode/Aspose.BarCode-for-.NET
using Aspose.BarCode.Generation;

namespace Aspose.BarCode.Examples.CSharp.BarcodeGeneration
{
    internal class Gs1CouponUpcaDatabar : OneDBase
    {
		public static void Run()
        {
            string path = "Your Directory Path";
            System.Console.WriteLine("Gs1CouponUpcaDatabar:");

            BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.UpcaGs1DatabarCoupon, "123456789012(8110)ASPOSE");
            gen.Parameters.Barcode.XDimension.Pixels = 2;
            gen.Save($"{path}Gs1CouponUpcaDatabar.png", BarCodeImageFormat.Png);
        }
	}
}
```
