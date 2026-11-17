---
category: general
date: 2026-11-17
description: Aprenda a criar código de barras PDF417 em C# – um guia completo sobre
  como gerar código de barras a partir de uma string usando um gerador de códigos
  de barras em C#.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create PDF417 barcode
- how to generate barcode
- c# barcode generator
- generate barcode from string
- create gs1 barcode
language: pt
lastmod: 2026-11-17
og_description: Crie código de barras PDF417 em C# rapidamente. Este tutorial mostra
  como gerar o código de barras a partir de uma string usando um gerador de código
  de barras em C# e inclui o código‑fonte completo.
og_image_alt: Screenshot of a generated PDF417 barcode created with a C# barcode generator
og_title: Criar código de barras PDF417 em C# – guia passo a passo
schemas:
- author: Aspose
  dateModified: '2026-11-17'
  description: Learn how to create PDF417 barcode in C# – a complete guide on how
    to generate barcode from string using a C# barcode generator.
  headline: How to create PDF417 barcode in C# with a barcode generator
  type: TechArticle
- description: Learn how to create PDF417 barcode in C# – a complete guide on how
    to generate barcode from string using a C# barcode generator.
  name: How to create PDF417 barcode in C# with a barcode generator
  steps:
  - name: Expected output
    text: '![Generated PDF417 barcode showing the GTIN (01)12345678901234](/images/pdf417-sample.png){:
      .center-image alt="Generated PDF417 barcode created with a C# barcode generator"}'
  - name: Changing the image format
    text: If you prefer JPEG or BMP, just replace `BarCodeImageFormat.Png` with `BarCodeImageFormat.Jpeg`
      or `BarCodeImageFormat.Bmp`. The rest of the code stays identical.
  - name: Adjusting error correction level
    text: PDF417 supports error correction levels 0‑8. Higher levels increase redundancy
      but also enlarge the barcode.
  - name: Generating other GS1 barcodes
    text: 'The same `BarcodeGenerator` can produce **create GS1 barcode** for other
      symbologies, such as `EncodeTypes.Gs1DataMatrix` or `EncodeTypes.Gs1Qr`. Just
      swap the enum value:'
  - name: Handling empty or null data
    text: 'When you **generate barcode from string**, always validate the input:'
  type: HowTo
- questions:
  - answer: Yes. The Aspose.BarCode library targets .NET Standard 2.0, which is compatible
      with .NET Framework 4.6 and later.
    question: Can I use this code on .NET Framework 4.6?
  - answer: 'Set the `Resolution` property before saving: ```csharp generator.Parameters.ImageResolution.DpiX
      = 300; generator.Parameters.ImageResolution.DpiY = 300; ```'
    question: What if I need a higher‑resolution image?
  - answer: 'It will be a standard PDF417 barcode, but it won’t be recognized as a
      GS1‑compliant symbol. Include the `(01)` prefix when you need **create GS1 barcode**
      compliance. ## Conclusion You now know how to **create PDF417 barcode** in C#
      using a robust **c# barcode generator**. The tutorial covered: * In'
    question: Is the barcode still valid without the GS1 Application Identifier?
  type: FAQPage
tags:
- barcode
- C#
- PDF417
- GS1
- code generation
title: Como criar código de barras PDF417 em C# com um gerador de códigos de barras
url: /pt/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-in-c-with-a-barcode-generator/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Como criar código de barras PDF417 em C# com um gerador de códigos de barras

Se você precisa **criar código de barras PDF417** em uma aplicação .NET, este guia mostra exatamente como fazer isso. Você aprenderá **como gerar código de barras** a partir de uma string simples, configurar o tamanho do símbolo e salvar o resultado como um arquivo PNG — tudo usando um gerador de códigos de barras C# confiável.

Gerar códigos de barras programaticamente elimina etapas manuais e garante qualidade consistente. Neste tutorial cobriremos tudo, desde a configuração do projeto até a imagem final, para que você possa integrar a criação de códigos de barras em qualquer solução C# hoje.

## Pré-requisitos

* .NET 6.0 SDK ou posterior (o código funciona com .NET Core e .NET Framework)
* Visual Studio 2022 (ou qualquer IDE que suporte C#)
* Uma licença ou avaliação gratuita do **Aspose.BarCode for .NET** – a biblioteca usada nos exemplos
* Familiaridade básica com a sintaxe C#

Nenhum pacote adicional é necessário; o pacote NuGet `Aspose.BarCode` contém todas as classes que você precisará.

## Etapa 1 – Configurar o gerador de código de barras C#

A primeira coisa que você faz ao **criar código de barras PDF417** é instanciar um objeto `BarcodeGenerator`. Esse objeto representa o **gerador de código de barras c#** que cuidará da codificação, renderização e salvamento.

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Step 1: Create a barcode generator for PDF417 with the data to encode
        // The data string follows the GS1 Application Identifier (01) for a GTIN
        BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
            EncodeTypes.Pdf417, "(01)12345678901234");
```

*Por que isso importa*: O enum `EncodeTypes.Pdf417` indica à biblioteca que deve usar a simbologia PDF417, que é o mesmo padrão usado para cartões de identificação e etiquetas de transporte. A string `"(01)12345678901234"` é um exemplo de **gerar código de barras a partir de string** que também demonstra como **criar código de barras GS1**.

## Etapa 2 – Configurar a dimensão X (largura do módulo)

A dimensão X controla a largura da barra mais fina (módulo). Um valor comum para renderização na tela é 2 pixels.

```csharp
        // Step 2: Set the X‑dimension (module width) to 2 pixels
        barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

Definir a dimensão X explicitamente impede que o gerador use seu padrão, o que pode gerar um código de barras muito pequeno para alguns scanners.

## Etapa 3 – Definir o número de colunas

O PDF417 permite ajustar o número de colunas, afetando tanto a forma do código de barras quanto a capacidade de dados. Para uma etiqueta compacta, quatro colunas funcionam bem.

```csharp
        // Step 3: Define the number of columns (e.g., 4) for a compact barcode
        barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 4;
```

Se precisar de um código de barras mais alto, aumente a contagem de colunas; a biblioteca calculará automaticamente as linhas necessárias.

## Etapa 4 – Salvar o código de barras como imagem

Finalmente, exporte o código de barras para um arquivo PNG. O PNG preserva bordas nítidas e suporta transparência.

```csharp
        // Step 4: Save the generated barcode as a PNG image
        barcodeGenerator.Save("output/Gs1Pdf417.png", BarCodeImageFormat.Png);
    }
}
```

Executar o programa cria `output/Gs1Pdf417.png`. Abra o arquivo em qualquer visualizador de imagens — você verá um **código de barras PDF417** limpo que codifica os dados GS1 fornecidos.

### Saída esperada

![Código de barras PDF417 gerado mostrando o GTIN (01)12345678901234](/images/pdf417-sample.png){: .center-image alt="Código de barras PDF417 criado com um gerador de códigos de barras C#"}

*A imagem acima demonstra o resultado do exemplo de código completo. O código de barras pode ser lido por qualquer leitor compatível com PDF417.*

## Opções adicionais e variações comuns

### Alterando o formato da imagem

Se preferir JPEG ou BMP, basta substituir `BarCodeImageFormat.Png` por `BarCodeImageFormat.Jpeg` ou `BarCodeImageFormat.Bmp`. O restante do código permanece idêntico.

### Ajustando o nível de correção de erro

O PDF417 suporta níveis de correção de erro de 0‑8. Níveis mais altos aumentam a redundância, mas também ampliam o código de barras.

```csharp
barcodeGenerator.Parameters.Barcode.Pdf417.ErrorCorrectionLevel = 5; // medium redundancy
```

### Gerando outros códigos de barras GS1

O mesmo `BarcodeGenerator` pode produzir **criar código de barras GS1** para outras simbologias, como `EncodeTypes.Gs1DataMatrix` ou `EncodeTypes.Gs1Qr`. Basta trocar o valor do enum:

```csharp
BarcodeGenerator gs1Generator = new BarcodeGenerator(
    EncodeTypes.Gs1DataMatrix, "(01)12345678901234");
```

### Tratando dados vazios ou nulos

Ao **gerar código de barras a partir de string**, sempre valide a entrada:

```csharp
string data = GetUserInput();
if (string.IsNullOrWhiteSpace(data))
{
    throw new ArgumentException("Data to encode cannot be null or empty.");
}
BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, data);
```

Isso evita exceções em tempo de execução e garante que o código de barras esteja em conformidade com as regras de formatação GS1.

## Exemplo completo e executável

Abaixo está o programa completo que você pode copiar e colar em um novo projeto de console. Ele inclui todas as diretivas `using` necessárias, criação de pastas e tratamento de erros.

```csharp
using System;
using System.IO;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Input data – GS1 GTIN with Application Identifier (01)
        const string gs1Data = "(01)12345678901234";

        // Validate input
        if (string.IsNullOrWhiteSpace(gs1Data))
        {
            Console.WriteLine("Error: Barcode data cannot be empty.");
            return;
        }

        // Ensure output directory exists
        string outputDir = Path.Combine(Directory.GetCurrentDirectory(), "output");
        Directory.CreateDirectory(outputDir);

        // Create the generator for PDF417 (GS1 optional)
        BarcodeGenerator generator = new BarcodeGenerator(
            EncodeTypes.Pdf417, gs1Data);

        // Configure appearance
        generator.Parameters.Barcode.XDimension.Pixels = 2;   // module width
        generator.Parameters.Barcode.Pdf417.Columns = 4;    // compact layout
        generator.Parameters.Barcode.Pdf417.ErrorCorrectionLevel = 5; // optional

        // Save as PNG
        string outputPath = Path.Combine(outputDir, "Gs1Pdf417.png");
        generator.Save(outputPath, BarCodeImageFormat.Png);

        Console.WriteLine($"Barcode saved to: {outputPath}");
    }
}
```

**Execute o programa** (`dotnet run`) e você encontrará `Gs1Pdf417.png` dentro da pasta *output*. Escaneie-o com qualquer leitor PDF417 para verificar se o GTIN `(01)12345678901234` está codificado corretamente.

## Perguntas frequentes

**Q: Posso usar este código no .NET Framework 4.6?**  
A: Sim. A biblioteca Aspose.BarCode tem como alvo .NET Standard 2.0, que é compatível com .NET Framework 4.6 e posteriores.

**Q: E se eu precisar de uma imagem de alta resolução?**  
A: Defina a propriedade `Resolution` antes de salvar:

```csharp
generator.Parameters.ImageResolution.DpiX = 300;
generator.Parameters.ImageResolution.DpiY = 300;
```

**Q: O código de barras ainda é válido sem o Identificador de Aplicação GS1?**  
A: Será um código de barras PDF417 padrão, mas não será reconhecido como um símbolo compatível com GS1. Inclua o prefixo `(01)` quando precisar de conformidade de **criar código de barras GS1**.

## Conclusão

Agora você sabe como **criar código de barras PDF417** em C# usando um robusto **gerador de código de barras c#**. O tutorial abordou:

* Instanciar `BarcodeGenerator` com dados GS1  
* Configurar a dimensão X e a contagem de colunas  
* Salvar o resultado como imagem PNG  
* Expandir a solução com correção de erro, formatos diferentes e validação de entrada  

Com essa base, você pode gerar qualquer código de barras PDF417 ou GS1 diretamente a partir de uma string, incorporá-lo em relatórios ou enviá-lo para impressoras. Explore a API Aspose.BarCode para adicionar cores, margens ou combinar vários códigos de barras em uma única imagem.

**Próximos passos**: tente gerar um **criar código de barras GS1** para DataMatrix, experimente cálculos dinâmicos de colunas ou integre o gerador em um serviço web ASP.NET Core que retorne imagens de códigos de barras sob demanda.

Boa codificação!

## O que você deve aprender a seguir?

Os tutoriais a seguir abordam tópicos estreitamente relacionados que se baseiam nas técnicas demonstradas neste guia. Cada recurso inclui exemplos de código completos e funcionais com explicações passo a passo para ajudá-lo a dominar recursos adicionais da API e explorar abordagens de implementação alternativas em seus próprios projetos.

- [Como gerar código de barras PDF417 em C# – guia completo](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-complete-guide/)
- [Como criar código de barras micro PDF417 e gerar PNG em C#](/barcode/english/net/compact-pdf417-encoding/how-to-create-micro-pdf417-barcode-and-generate-png-in-c/)
- [Como criar código de barras macro PDF417 em C# usando Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/how-to-create-macro-pdf417-barcode-in-c-using-aspose-barcode/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}