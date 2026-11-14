---
category: general
date: 2026-11-14
description: Aprenda a criar códigos de barras PDF417 em C# rapidamente. Este guia
  também mostra como gerar PDF417 e como personalizar as configurações do PDF417 para
  um controle preciso.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create pdf417 barcode
- how to generate pdf417
- how to customize pdf417
language: pt
lastmod: 2026-11-14
og_description: Crie código de barras PDF417 em C# com instruções passo a passo. Aprenda
  como gerar PDF417 e como personalizar os parâmetros do PDF417 para obter resultados
  precisos.
og_image_alt: Screenshot showing a generated PDF417 barcode created with C# code
og_title: Criar código de barras PDF417 em C# – guia completo com layout personalizado
schemas:
- author: Aspose
  dateModified: '2026-11-14'
  description: Learn how to create PDF417 barcode in C# quickly. This guide also shows
    how to generate PDF417 and how to customize PDF417 settings for precise control.
  headline: How to create PDF417 barcode with custom layout in C#
  type: TechArticle
- description: Learn how to create PDF417 barcode in C# quickly. This guide also shows
    how to generate PDF417 and how to customize PDF417 settings for precise control.
  name: How to create PDF417 barcode with custom layout in C#
  steps:
  - name: '**Check dimensions:** Ensure columns/rows stay within the allowed range.'
    text: '**Check dimensions:** Ensure columns/rows stay within the allowed range.'
  - name: '**Adjust error level:** Increase `ErrorLevel` for damaged media.'
    text: '**Adjust error level:** Increase `ErrorLevel` for damaged media.'
  - name: '**Review image quality:** Save with a higher DPI (`generator.Save(outputPath,
      BarCodeImageFormat.Png, 300)`) if you plan to print.'
    text: '**Review image quality:** Save with a higher DPI (`generator.Save(outputPath,
      BarCodeImageFormat.Png, 300)`) if you plan to print.'
  type: HowTo
tags:
- barcode
- pdf417
- C#
title: Como criar código de barras PDF417 com layout personalizado em C#
url: /pt/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-with-custom-layout-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Como criar código de barras PDF417 com layout personalizado em C#

Se você precisa **criar código de barras pdf417** para um sistema de bilhetagem, etiqueta de inventário ou leitura em aplicativo móvel, este tutorial mostra o processo completo. Você verá como gerar PDF417 rapidamente e como personalizar as configurações do PDF417, como colunas e linhas, para que o código de barras se ajuste às restrições de design.

Gerar um código de barras não requer uma biblioteca gráfica complexa — basta o Aspose.BarCode para .NET (ou qualquer API compatível). Ao final deste guia, você terá um arquivo PNG pronto para uso que pode ser incorporado em PDFs, páginas da web ou impresso diretamente a partir da sua aplicação.

## Pré-requisitos

- .NET 6.0 ou posterior (o código também funciona com .NET Framework 4.7+)
- Aspose.BarCode para .NET (pacote NuGet `Aspose.BarCode`)
- Familiaridade básica com C# e Visual Studio (ou qualquer IDE)

> **Dica profissional:** Se você estiver usando um pipeline CI/CD, adicione a referência ao pacote NuGet no seu arquivo de projeto para que as compilações permaneçam reproduzíveis.

## Etapa 1: Instalar a biblioteca de código de barras

Abra a pasta do seu projeto em um terminal e execute:

```bash
dotnet add package Aspose.BarCode
```

O pacote inclui a classe `BarcodeGenerator` usada ao longo deste tutorial. Nenhuma dependência nativa adicional é necessária.

## Etapa 2: Criar um código de barras PDF417 básico

O primeiro objetivo é **criar código de barras pdf417** com configurações padrão. O programa a seguir configura o gerador, codifica uma string de exemplo e salva o resultado como uma imagem PNG.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Pdf417Demo
{
    static void Main()
    {
        // Step 2.1: Initialise the generator for PDF417 with the desired text
        BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Sample text for PDF417");

        // Step 2.2: Save the barcode as PNG
        string outputPath = "Pdf417Default.png";
        generator.Save(outputPath, BarCodeImageFormat.Png);

        Console.WriteLine($"Barcode saved to {outputPath}");
    }
}
```

**Por que isso funciona:**  
`EncodeTypes.Pdf417` indica à biblioteca que deve usar a simbologia PDF417. O construtor cria automaticamente um objeto `Barcode` com valores padrão de coluna/linha que garantem a legibilidade na maioria dos casos de uso.

Execute o programa (`dotnet run`). Você encontrará `Pdf417Default.png` na pasta do projeto. Ao abrir a imagem, verá um código de barras PDF417 padrão pronto para leitura.

![Exemplo de criação de código de barras PDF417](https://example.com/images/pdf417-default.png){:alt="Exemplo de criação de código de barras PDF417 mostrando layout padrão"}

## Etapa 3: Como gerar PDF417 com dimensões personalizadas

Às vezes, um rótulo de tamanho fixo ou um componente de UI requer uma área de código de barras específica. É aí que **como gerar pdf417** com colunas e linhas personalizadas se torna essencial.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Pdf417CustomDemo
{
    static void Main()
    {
        // Initialise generator with the same text
        BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Custom layout text");

        // ---- Customization begins here ----
        // Set the number of columns (2‑30). Fewer columns make the barcode taller.
        generator.Parameters.Barcode.Pdf417.Columns = 4;

        // Set the number of rows (1‑90). More rows make the barcode wider.
        generator.Parameters.Barcode.Pdf417.Rows = 9;
        // ------------------------------------

        // Save the customized barcode
        string outputPath = "Pdf417CustomLayout.png";
        generator.Save(outputPath, BarCodeImageFormat.Png);

        Console.WriteLine($"Custom barcode saved to {outputPath}");
    }
}
```

**Por que você pode querer isso:**  
- **Largura limitada:** Reduzir colunas e aumentar linhas cria um código de barras mais largo, mas mais curto, perfeito para etiquetas estreitas.  
- **Altura limitada:** Aumentar colunas e diminuir linhas produz um código de barras mais alto e estreito, útil quando há espaço vertical.

Tanto `Columns` quanto `Rows` aceitam apenas valores dentro das faixas documentadas (2‑30 para colunas, 1‑90 para linhas). Fornecer um valor fora do intervalo lança uma `ArgumentOutOfRangeException`, portanto sempre valide a entrada do usuário se você expuser essas configurações em uma UI.

## Etapa 4: Como personalizar ainda mais o PDF417

Além de colunas e linhas, a simbologia PDF417 oferece muitos parâmetros opcionais:

| Propriedade | Propósito | Valores típicos |
|-------------|-----------|-----------------|
| `ErrorLevel` | Controla a capacidade de correção de erros | 0‑8 (higher = more robust) |
| `MacroPdf417` | Habilita macro PDF417 para dados multi‑segmento | `true`/`false` |
| `CompactPdf417` | Produz um código de barras mais compacto ao custo de redução da correção de erros | `true`/`false` |
| `SecurityLevel` | Adiciona um dígito de verificação de segurança | 0‑2 |

Aqui está um exemplo rápido que também define o nível de erro para o máximo (8) em um ambiente ruidoso:

```csharp
generator.Parameters.Barcode.Pdf417.ErrorLevel = 8;
generator.Parameters.Barcode.Pdf417.CompactPdf417 = true;
```

**Por que isso importa:**  
Uma correção de erros mais alta permite que os leitores recuperem dados mesmo que parte do código de barras esteja danificada. No entanto, isso também aumenta o tamanho do código de barras, então equilibre a configuração com as restrições do seu layout.

## Etapa 5: Verificar se o código de barras funciona

Depois de gerar o PNG, teste‑o com qualquer aplicativo de leitura de código de barras (a maioria dos smartphones possui leitores PDF417 gratuitos). Se o leitor retornar o texto original (`Custom layout text`), o código de barras é válido.

Se você encontrar problemas de leitura:

1. **Verifique as dimensões:** Certifique‑se de que colunas/linhas permanecem dentro da faixa permitida.  
2. **Ajuste o nível de erro:** Aumente `ErrorLevel` para mídia danificada.  
3. **Revise a qualidade da imagem:** Salve com DPI mais alto (`generator.Save(outputPath, BarCodeImageFormat.Png, 300)`) se você pretende imprimir.

## Código-fonte completo para um helper reutilizável

Abaixo está uma classe compacta e reutilizável que você pode inserir em qualquer projeto .NET. Ela encapsula **como gerar pdf417** e **como personalizar pdf417** em um único método.

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;

public static class Pdf417Helper
{
    /// <summary>
    /// Creates a PDF417 barcode image with optional layout parameters.
    /// </summary>
    /// <param name="text">The data to encode.</param>
    /// <param name="outputPath">Full file path for the PNG output.</param>
    /// <param name="columns">Number of columns (2‑30). Pass null to use default.</param>
    /// <param name="rows">Number of rows (1‑90). Pass null to use default.</param>
    /// <param name="errorLevel">Error correction level (0‑8). Null = default.</param>
    public static void CreatePdf417(string text, string outputPath,
                                    int? columns = null,
                                    int? rows = null,
                                    int? errorLevel = null)
    {
        var generator = new BarcodeGenerator(EncodeTypes.Pdf417, text);

        // Apply optional customizations
        if (columns.HasValue) generator.Parameters.Barcode.Pdf417.Columns = columns.Value;
        if (rows.HasValue)    generator.Parameters.Barcode.Pdf417.Rows    = rows.Value;
        if (errorLevel.HasValue) generator.Parameters.Barcode.Pdf417.ErrorLevel = errorLevel.Value;

        // Save as high‑resolution PNG (300 DPI) for printing scenarios
        generator.Save(outputPath, BarCodeImageFormat.Png, 300);
    }
}
```

Você pode chamar este helper assim:

```csharp
Pdf417Helper.CreatePdf417(
    text: "Order #12345",
    outputPath: "OrderBarcode.png",
    columns: 5,
    rows: 12,
    errorLevel: 6);
```

O método abstrai a boiler‑plate repetitiva, permitindo que você se concentre na lógica de negócios.

## Armadilhas comuns e como evitá‑las

- **Valores fora do intervalo:** Sempre valide `columns` e `rows` antes de atribuí‑los.  
- **Formato de imagem incorreto:** Alguns leitores legados aceitam apenas BMP ou JPEG. Use `BarCodeImageFormat.Bmp` se necessário.  
- **DPI baixo para impressão:** O DPI padrão é 96. Para impressões de alta qualidade, defina explicitamente um DPI maior (por exemplo, 300) ao chamar `Save`.  
- **Suporte de fonte ausente:** PDF417 codifica dados binários, portanto geralmente você não precisa especificar uma fonte. No entanto, se você sobrepor texto na imagem, certifique‑se de que a fonte esteja instalada na máquina de destino.

## Conclusão

Agora você sabe como **criar código de barras pdf417** do início ao fim, como **gerar pdf417** com configurações personalizadas de coluna/linha, e como **personalizar pdf417** para correção de erros e compactação. Seguindo o padrão de helper reutilizável, você pode gerar códigos de barras sob demanda, adaptá‑los a qualquer restrição de layout e garantir leituras confiáveis em ambientes de produção.

**Próximos passos**

- Explore outras simbologias como QR ou Code128 usando a mesma classe `BarcodeGenerator`.  
- Combine a saída PNG com uma biblioteca de geração de PDF (por exemplo, iText7) para incorporar códigos de barras em faturas.  
- Experimente `MacroPdf417` para transmissão de dados multi‑segmento, um recurso útil em aplicações de logística e transporte.

Feliz codificação, e que seus códigos de barras sempre sejam lidos na primeira tentativa!

## O que você deve aprender a seguir?

Os tutoriais a seguir cobrem tópicos estreitamente relacionados que se baseiam nas técnicas demonstradas neste guia. Cada recurso inclui exemplos de código completos e funcionais com explicações passo a passo para ajudá‑lo a dominar recursos adicionais da API e explorar abordagens de implementação alternativas em seus próprios projetos.

- [Como gerar código de barras PDF417 em C# – guia passo a passo](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-step-by-step-guide/)
- [Como gerar código de barras e personalizar código de barras PDF417 em C#](/barcode/english/net/compact-pdf417-encoding/how-to-generate-barcode-and-customize-pdf417-barcode-in-c/)
- [Como criar código de barras PDF417 e exportar PNG em C#](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-and-export-png-in-c/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}