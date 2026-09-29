---
category: general
date: 2026-09-29
description: Crie código de barras planetário em C# com barras preenchidas e vazias
  – guia passo a passo usando Aspose.Barcode.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create planet barcode
- Planet barcode XDimension
- filled bars
- empty bars
- Aspose.Barcode C#
language: pt
lastmod: 2026-09-29
og_description: Crie códigos de barras planetários em C# rapidamente. Aprenda a renderizar
  barras preenchidas, alternar para barras vazias e ajustar a dimensão X com Aspose.Barcode.
og_image_alt: 'Screenshot of two Planet barcodes: one with filled bars, one with empty
  bars'
og_title: Criar código de barras planetário com barras preenchidas e vazias – tutorial
  C#
schemas:
- author: Aspose
  dateModified: '2026-09-29'
  description: Create planet barcode in C# with both filled and empty bars – step‑by‑step
    guide using Aspose.Barcode.
  headline: How to create planet barcode with filled and empty bars
  type: TechArticle
- description: Create planet barcode in C# with both filled and empty bars – step‑by‑step
    guide using Aspose.Barcode.
  name: How to create planet barcode with filled and empty bars
  steps:
  - name: Changing the bar width
    text: If your label printer expects a different bar width, modify the `XDimension.Pixels`
      value. For high‑resolution printers, a value of **2** or **3** pixels may be
      preferable; for low‑resolution printers, **5** or **6** pixels can improve scan
      reliability.
  - name: Using a different image format
    text: Aspose.Barcode supports PNG, JPEG, BMP, GIF, and TIFF. Swap `BarCodeImageFormat.Png`
      with another enum value to match your downstream workflow.
  - name: Generating multiple barcodes in a loop
    text: When you need a batch of Planet barcodes (e.g., for a mailing list), wrap
      the generator logic in a `foreach` loop and change the data string each iteration.
  - name: Handling invalid input
    text: The Planet symbology accepts only numeric strings of **5‑8** digits. Supplying
      an invalid value throws an `ArgumentException`. Guard against this with a simple
      validation method.
  type: HowTo
tags:
- barcode
- C#
- Aspose
title: Como criar um código de barras planetário com barras preenchidas e vazias
url: /pt/python-java/general/how-to-create-planet-barcode-with-filled-and-empty-bars/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Como criar planet barcode com barras preenchidas e vazias

Se você precisa **criar planet barcode** imagens em C#, este guia mostra exatamente como gerar versões com barra preenchida e barra vazia. Você verá como definir a largura da barra (X‑dimension), alternar a propriedade `FilledBars` e salvar os resultados como arquivos PNG — tudo com a biblioteca Aspose.Barcode.

Gerar códigos de barras postais é uma necessidade comum para sistemas de envio, aplicações de listas de correspondência e painéis de logística. Ao final deste tutorial você terá dois arquivos PNG prontos para uso que podem ser incorporados em relatórios, e‑mails ou impressões.

## Pré-requisitos

| Requisito | Por que é importante |
|-------------|----------------|
| .NET 6.0 ou posterior | Fornece o runtime para o exemplo em C#. |
| Visual Studio 2022 (ou qualquer IDE C#) | Permite compilar e executar o código. |
| **Aspose.Barcode for .NET** NuGet package | Fornece a classe `BarcodeGenerator` e `EncodeTypes.Planet`. Instale com `dotnet add package Aspose.Barcode`. |
| Permissão de gravação em uma pasta no disco | O método `Save` grava arquivos PNG no caminho especificado. |

## Etapa 1: Configurar o projeto e importar namespaces

Crie um novo projeto de console (ou adicione o código a um existente) e faça referência ao namespace Aspose.Barcode.

```csharp
using System;
using Aspose.Barcode;
using Aspose.Barcode.Generation;
```

Essas diretivas `using` dão acesso às classes `BarcodeGenerator`, `EncodeTypes` e aos enums de formatos de imagem necessários para o tutorial.

## Etapa 2: Criar um Planet barcode com barras padrão (preenchidas)

O primeiro código de barras usa a renderização padrão da biblioteca, que preenche as barras.

```csharp
// Initialise a generator for the Planet (postal) barcode with sample data.
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(EncodeTypes.Planet, "123456");

// Optional: adjust the bar width (X dimension) to 4 pixels for clearer printing.
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 4;

// Save the image with filled bars.
string filledPath = @"C:\Barcodes\PlanetFilledBars.png";
barcodeGenerator.Save(filledPath, BarCodeImageFormat.Png);

Console.WriteLine($"Filled Planet barcode saved to: {filledPath}");
```

**Por que isso funciona:**  
`EncodeTypes.Planet` indica ao Aspose.Barcode para usar a simbologia **Planet**, que é um código de barras postal usado pelo United States Postal Service. A propriedade `XDimension` controla a largura de cada barra; definir para 4 pixels produz um código de barras que imprime bem em impressoras de etiquetas padrão. Por padrão, `FilledBars` é `true`, então as barras aparecem sólidas.

## Etapa 3: Criar um Planet barcode com barras vazias

Para gerar os mesmos dados com barras *vazias*, basta inverter a flag `FilledBars` mantendo as demais configurações idênticas.

```csharp
// Re‑use the same variable for clarity.
barcodeGenerator = new BarcodeGenerator(EncodeTypes.Planet, "123456");

// Keep the same X‑dimension for visual consistency.
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 4;

// Render empty bars instead of filled ones.
barcodeGenerator.Parameters.Barcode.FilledBars = false;

// Save the image with empty bars.
string emptyPath = @"C:\Barcodes\PlanetEmptyBars.png";
barcodeGenerator.Save(emptyPath, BarCodeImageFormat.Png);

Console.WriteLine($"Empty Planet barcode saved to: {emptyPath}");
```

**Por que isso importa:**  
Alguns sistemas de correspondência exigem o estilo de **barras vazias** para melhorar a legibilidade quando o código de barras é impresso em fundos escuros ou quando um esquema de cores contrastante é usado. Definindo `FilledBars = false`, o gerador desenha apenas os contornos das barras, deixando o interior transparente.

## Saída esperada

Após executar o programa, a pasta `C:\Barcodes` (ou o caminho que você escolheu) contém dois arquivos PNG:

| Arquivo | Descrição visual |
|------|---------------------|
| `PlanetFilledBars.png` | As barras são retângulos pretos sólidos sobre fundo branco. |
| `PlanetEmptyBars.png`  | As barras são contornos pretos; o interior de cada barra é transparente (mostra o fundo). |

Ambas as imagens codificam a mesma string numérica `"123456"` e compartilham uma largura de barra de 4 pixels, garantindo que tenham aparência consistente, exceto pelo estilo de preenchimento.

## Variações comuns e casos de borda

### Alterando a largura da barra

Se sua impressora de etiquetas espera uma largura de barra diferente, modifique o valor `XDimension.Pixels`. Para impressoras de alta resolução, um valor de **2** ou **3** pixels pode ser preferível; para impressoras de baixa resolução, **5** ou **6** pixels podem melhorar a confiabilidade da leitura.

```csharp
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 5; // example for coarse printers
```

### Usando um formato de imagem diferente

Aspose.Barcode suporta PNG, JPEG, BMP, GIF e TIFF. Troque `BarCodeImageFormat.Png` por outro valor de enum para adequar ao seu fluxo de trabalho posterior.

```csharp
barcodeGenerator.Save("Planet.tiff", BarCodeImageFormat.Tiff);
```

### Gerando múltiplos códigos de barras em um loop

Quando precisar de um lote de Planet barcodes (por exemplo, para uma lista de correspondência), envolva a lógica do gerador em um loop `foreach` e altere a string de dados a cada iteração.

```csharp
string[] postalCodes = { "123456", "654321", "112233" };
int index = 1;
foreach (var code in postalCodes)
{
    var gen = new BarcodeGenerator(EncodeTypes.Planet, code);
    gen.Parameters.Barcode.XDimension.Pixels = 4;
    gen.Save($@"C:\Barcodes\Planet_{index}_filled.png", BarCodeImageFormat.Png);
    gen.Parameters.Barcode.FilledBars = false;
    gen.Save($@"C:\Barcodes\Planet_{index}_empty.png", BarCodeImageFormat.Png);
    index++;
}
```

### Tratando entrada inválida

A simbologia Planet aceita apenas strings numéricas de **5‑8** dígitos. Fornecer um valor inválido lança uma `ArgumentException`. Proteja-se contra isso com um método simples de validação.

```csharp
bool IsValidPlanet(string value) => System.Text.RegularExpressions.Regex.IsMatch(value, @"^\d{5,8}$");

string data = "ABC123";
if (!IsValidPlanet(data))
{
    Console.WriteLine("Invalid Planet data – must be 5 to 8 digits.");
    return;
}
```

## Dica profissional: Verifique o código de barras com um emulador de scanner

Aspose.Barcode inclui a classe `BarcodeReader` que você pode usar para confirmar que a imagem gerada decodifica de volta para os dados originais.

```csharp
using Aspose.Barcode.Reader;

// Verify filled barcode
using (BarCodeReader reader = new BarCodeReader(filledPath, DecodeType.Planet))
{
    if (reader.Read())
        Console.WriteLine($"Decoded from filled image: {reader.GetCodeText()}");
}

// Verify empty barcode
using (BarCodeReader reader = new BarCodeReader(emptyPath, DecodeType.Planet))
{
    if (reader.Read())
        Console.WriteLine($"Decoded from empty image: {reader.GetCodeText()}");
}
```

Se a saída mostrar `"123456"` para ambos os arquivos, o código de barras foi gerado corretamente.

## Conclusão

Agora você sabe como **criar planet barcode** imagens em C# com estilos de barra preenchida e vazia, controlar o **Planet barcode XDimension** e salvar os resultados em formato PNG usando a biblioteca **Aspose.Barcode**. Ajuste a largura da barra, troque os formatos de imagem ou faça loop sobre uma coleção de valores para atender a qualquer fluxo de trabalho de código postal.

Em seguida, você pode explorar:

* **Adicionar texto legível por humanos** abaixo do código de barras (`barcodeGenerator.Parameters.Caption.Show = true`).
* **Incorporar códigos de barras em documentos PDF** com Aspose.PDF.
* **Gerar outras simbologias postais** como **USPS POSTNET** ou **Intelligent Mail**.

Sinta-se à vontade para experimentar os parâmetros e integrar o código ao seu sistema de envio ou correspondência. Feliz codificação!

## O que você deve aprender a seguir?

Os tutoriais a seguir abordam tópicos intimamente relacionados que se baseiam nas técnicas demonstradas neste guia. Cada recurso inclui exemplos de código completos e funcionais com explicações passo a passo para ajudá‑lo a dominar recursos adicionais da API e explorar abordagens de implementação alternativas em seus próprios projetos.

- [Criar Planet Barcode em C# – Guia completo passo a passo](/barcode/english/python-java/general/create-planet-barcode-in-c-full-step-by-step-guide/)
- [Criar planet barcode em C# – guia completo de programação](/barcode/english/python-java/general/create-planet-barcode-in-c-complete-programming-guide/)
- [Gerador de código de barras C# – exemplo de criação de Planet barcode e RM4SCC](/barcode/english/python-java/general/barcode-generator-c-create-planet-barcode-and-rm4scc-example/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}