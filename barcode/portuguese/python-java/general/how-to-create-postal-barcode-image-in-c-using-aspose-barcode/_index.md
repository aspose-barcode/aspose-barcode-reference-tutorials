---
category: general
date: 2026-10-02
description: Crie imagem de código de barras postal em C# com Aspose.BarCode. Aprenda
  a gerar códigos de barras Planet e RM4SCC, personalizar as barras preenchidas e
  salvar arquivos PNG.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create postal barcode image
- generate planet barcode
- Aspose.BarCode C#
- postal barcode PNG
- barcode XDimension setting
language: pt
lastmod: 2026-10-02
og_description: Crie imagem de código de barras postal em C# com Aspose.BarCode. Este
  tutorial mostra como gerar códigos de barras Planet e RM4SCC, ajustar o preenchimento
  das barras e exportar arquivos PNG.
og_image_alt: Postal barcode image generated with Aspose.BarCode (filled bars)
og_title: Criar imagem de código de barras postal em C# – guia passo a passo
schemas:
- author: Aspose
  dateModified: '2026-10-02'
  description: Create postal barcode image in C# with Aspose.BarCode. Learn to generate
    Planet and RM4SCC barcodes, customize filled bars, and save PNG files.
  headline: How to create postal barcode image in C# using Aspose.BarCode
  type: TechArticle
- description: Create postal barcode image in C# with Aspose.BarCode. Learn to generate
    Planet and RM4SCC barcodes, customize filled bars, and save PNG files.
  name: How to create postal barcode image in C# using Aspose.BarCode
  steps:
  - name: Why each line matters
    text: '* **`new BarcodeGenerator(EncodeTypes.Planet, "123456")`** – The `EncodeTypes.Planet`
      enum tells Aspose.BarCode to use the *Planet* symbology, which is a standard
      postal barcode in many countries. This is the core of how you **generate planet
      barcode** images. * **`XDimension.Pixels = 4`** – The wid'
  - name: Expected output
    text: 'After running the program, the `YOUR_DIRECTORY` folder contains three PNG
      files:'
  - name: Change image format
    text: If you need a different format (e.g., JPEG for web delivery), replace `BarCodeImageFormat.Png`
      with `BarCodeImageFormat.Jpeg`. Keep in mind that JPEG introduces compression
      artifacts, which can affect scanner performance.
  - name: Adjust image size without scaling
    text: Instead of changing `XDimension`, you can control the overall image dimensions
      via `Parameters.Image.Height` and `Parameters.Image.Width`. This is useful when
      you have a fixed label size.
  - name: Use a different barcode symbology
    text: Aspose.BarCode supports dozens of postal symbologies (e.g., **USPS Intelligent
      Mail**, **Japan Post**). To **generate planet barcode** alternatives, replace
      `EncodeTypes.Planet` with the desired enum value.
  - name: Handling invalid data
    text: Postal barcodes have strict data length rules. If you pass a string that
      does not meet the specification, Aspose.BarCode throws an `ArgumentException`.
      Wrap the generator creation in a `try/catch` block to provide a friendly error
      message.
  type: HowTo
tags:
- barcode
- C#
- Aspose
title: Como criar imagem de código de barras postal em C# usando Aspose.BarCode
url: /pt/python-java/general/how-to-create-postal-barcode-image-in-c-using-aspose-barcode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Como criar imagem de código de barras postal em C# usando Aspose.BarCode

Se você precisa **criar imagem de código de barras postal** em C#, o Aspose.BarCode fornece uma API limpa que cuida do trabalho pesado. Seja você está construindo um sistema de etiquetas de correio ou um serviço de verificação de endereços, este guia mostra exatamente como gerar códigos de barras Planet e RM4SCC, alternar entre barras preenchidas e vazias, e exportar o resultado como arquivos PNG.

Você aprenderá como configurar o tamanho do código de barras, controlar o comportamento de preenchimento das barras e salvar a imagem no disco — tudo em um único programa executável. Nenhuma ferramenta externa é necessária além da biblioteca Aspose.BarCode para .NET.

## Pré-requisitos

Antes de começar, certifique‑se de que você tem:

* .NET 6.0 SDK ou posterior (o código também funciona com .NET Framework 4.7+)
* Visual Studio 2022 ou qualquer IDE compatível com C#
* Uma cópia licenciada ou de avaliação do **Aspose.BarCode for .NET** (disponível via NuGet)

```bash
dotnet add package Aspose.BarCode
```

## Visão geral da solução

O tutorial está dividido em três etapas lógicas:

1. **Criar um código de barras Planet com as barras padrão (preenchidas)** – isso demonstra a aparência típica para serviços postais.  
2. **Criar um código de barras Planet com barras vazias** – útil quando o processo de impressão espera barras não preenchidas.  
3. **Criar um código de barras RM4SCC com barras preenchidas** – outro formato postal comum usado em muitos países.

Cada etapa segue o mesmo padrão: instanciar `BarcodeGenerator`, definir `XDimension` (largura em pixels de uma única barra), opcionalmente ajustar `FilledBars` e chamar `Save` para gravar um arquivo PNG.

---

## Criar imagem de código de barras postal com Aspose.BarCode

Abaixo está o programa completo e autônomo. Salve‑o como `Program.cs` e execute‑o a partir da linha de comando ou da sua IDE.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace PostalBarcodeDemo
{
    class Program
    {
        static void Main(string[] args)
        {
            // Define the output folder – change this to a writable location on your machine
            string outputDir = @"YOUR_DIRECTORY";

            // -------------------------------------------------
            // Step 1: Generate a Planet barcode with filled bars
            // -------------------------------------------------
            var planetFilled = new BarcodeGenerator(EncodeTypes.Planet, "123456")
            {
                // XDimension controls the width of a single bar in pixels.
                // A value of 4 gives a good balance between readability and file size.
                Parameters = { Barcode = { XDimension = { Pixels = 4 } } }
            };
            string planetFilledPath = System.IO.Path.Combine(outputDir, "PostalPlanetFilledBars.png");
            planetFilled.Save(planetFilledPath, BarCodeImageFormat.Png);
            Console.WriteLine($"Filled Planet barcode saved to {planetFilledPath}");

            // -------------------------------------------------
            // Step 2: Generate a Planet barcode with empty bars
            // -------------------------------------------------
            var planetEmpty = new BarcodeGenerator(EncodeTypes.Planet, "123456")
            {
                Parameters = {
                    Barcode = {
                        XDimension = { Pixels = 4 },
                        // Setting FilledBars to false renders the bars as empty outlines.
                        FilledBars = false
                    }
                }
            };
            string planetEmptyPath = System.IO.Path.Combine(outputDir, "PostalPlanetEmptyBars.png");
            planetEmpty.Save(planetEmptyPath, BarCodeImageFormat.Png);
            Console.WriteLine($"Empty Planet barcode saved to {planetEmptyPath}");

            // -------------------------------------------------
            // Step 3: Generate an RM4SCC barcode with filled bars
            // -------------------------------------------------
            var rm4sccFilled = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456")
            {
                Parameters = { Barcode = { XDimension = { Pixels = 4 } } }
            };
            string rm4sccPath = System.IO.Path.Combine(outputDir, "PostalRM4SCCFilledBars.png");
            rm4sccFilled.Save(rm4sccPath, BarCodeImageFormat.Png);
            Console.WriteLine($"Filled RM4SCC barcode saved to {rm4sccPath}");

            // End of demo
            Console.WriteLine("All barcode images have been generated successfully.");
        }
    }
}
```

### Por que cada linha importa

* **`new BarcodeGenerator(EncodeTypes.Planet, "123456")`** – O enum `EncodeTypes.Planet` indica ao Aspose.BarCode para usar a simbologia *Planet*, que é um código de barras postal padrão em muitos países. Este é o núcleo de como você **gera imagens de código de barras planet**.  
* **`XDimension.Pixels = 4`** – A largura de uma única barra influencia tanto a confiabilidade da leitura quanto o tamanho visual. Um valor de 4 px funciona bem para a maioria das impressoras de etiquetas; você pode aumentá‑lo para saídas de alta resolução.  
* **`FilledBars = false`** – Por padrão, as barras são preenchidas. Definir isso como `false` cria o estilo de “barra vazia” exigido por algumas especificações de envio.  
* **`Save(..., BarCodeImageFormat.Png)`** – PNG preserva qualidade sem perdas, tornando‑o ideal para imagens de códigos de barras que precisam ser lidas por scanners.

### Saída esperada

Após executar o programa, a pasta `YOUR_DIRECTORY` contém três arquivos PNG:

| Nome do arquivo                     | Descrição visual                                 |
|-------------------------------------|--------------------------------------------------|
| `PostalPlanetFilledBars.png`        | Código de barras Planet com barras pretas sólidas |
| `PostalPlanetEmptyBars.png`         | Código de barras Planet onde as barras são contornadas (vazias) |
| `PostalRM4SCCFilledBars.png`        | Código de barras RM4SCC com barras sólidas      |

Você pode abrir qualquer uma dessas imagens em um visualizador de imagens ou incorporá‑las diretamente em uma etiqueta PDF/HTML.

---

## Personalizando o código de barras ainda mais (opcional)

### Alterar o formato da imagem

Se você precisar de um formato diferente (por exemplo, JPEG para entrega web), substitua `BarCodeImageFormat.Png` por `BarCodeImageFormat.Jpeg`. Lembre‑se de que JPEG introduz artefatos de compressão, o que pode afetar o desempenho do scanner.

### Ajustar o tamanho da imagem sem redimensionamento

Em vez de mudar `XDimension`, você pode controlar as dimensões gerais da imagem via `Parameters.Image.Height` e `Parameters.Image.Width`. Isso é útil quando você tem um tamanho de etiqueta fixo.

```csharp
planetFilled.Parameters.Image.Height = 150; // pixels
planetFilled.Parameters.Image.Width = 300;  // pixels
```

### Usar uma simbologia de código de barras diferente

Aspose.BarCode suporta dezenas de simbologias postais (por exemplo, **USPS Intelligent Mail**, **Japan Post**). Para **gerar códigos de barras planet** alternativos, substitua `EncodeTypes.Planet` pelo valor enum desejado.

```csharp
var uspsBarcode = new BarcodeGenerator(EncodeTypes.USPSIntelligentMail, "123456789012");
```

### Tratamento de dados inválidos

Códigos de barras postais têm regras estritas de comprimento de dados. Se você passar uma string que não atende à especificação, o Aspose.BarCode lança uma `ArgumentException`. Envolva a criação do gerador em um bloco `try/catch` para fornecer uma mensagem de erro amigável.

```csharp
try
{
    var invalid = new BarcodeGenerator(EncodeTypes.Planet, "ABC");
}
catch (ArgumentException ex)
{
    Console.Error.WriteLine($"Invalid barcode data: {ex.Message}");
}
```

---

## Armadilhas comuns e dicas profissionais

| Armadilha                                 | Por que acontece                                            | Dica profissional                                                                                              |
|-------------------------------------------|-------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------|
| **Usar um XDimension muito pequeno**     | As barras ficam mais finas que a resolução mínima do scanner, causando erros de leitura. | Comece com `Pixels = 4` e teste na impressora alvo; aumente se necessário.                                      |
| **Salvar em uma pasta somente leitura**  | `Save` lança uma `UnauthorizedAccessException`.            | Garanta que `outputDir` aponte para um local gravável, ou use `Environment.GetFolderPath(Environment.SpecialFolder.Desktop)`. |
| **Negligenciar a liberação do gerador**  | Imagens grandes podem manter recursos não gerenciados.      | Envolva o gerador em uma instrução `using` ou chame `Dispose()` após `Save`.                                    |
| **Misturar formatos de código de barras em uma única imagem** | Algumas impressoras esperam uma única simbologia por etiqueta. | Gere cada código de barras separadamente e combine‑os com uma biblioteca gráfica, se necessário.                |

---

## Verificar os códigos de barras gerados

Para confirmar que os códigos de barras são válidos, você pode usar o site gratuito **Aspose.BarCode Demo** ou qualquer aplicativo padrão de scanner de códigos de barras. Carregue os arquivos PNG e escaneie‑os; o valor decodificado deve ser `123456` para ambos os exemplos Planet e RM4SCC.

---

## Conclusão

Neste tutorial você aprendeu como **criar arquivos de imagem de código de barras postal** em C# com Aspose.BarCode. Você viu como **gerar imagens de código de barras planet** com barras preenchidas e vazias, como produzir um código de barras RM4SCC e como personalizar tamanho, formato e tratamento de erros. Com o código completo e executável, você agora pode integrar a geração de códigos de barras postais em qualquer aplicação .NET.

**Próximos passos**

* Explore outras simbologias postais como `EncodeTypes.USPSIntelligentMail` (palavra‑chave secundária: postal barcode PNG).

## O que você deve aprender a seguir?

Os tutoriais a seguir cobrem tópicos estreitamente relacionados que se baseiam nas técnicas demonstradas neste guia. Cada recurso inclui exemplos de código completos e funcionais com explicações passo a passo para ajudá‑lo a dominar recursos adicionais da API e explorar abordagens de implementação alternativas em seus próprios projetos.

- [Criar imagem de código de barras postal em C# – Guia completo passo a passo](/barcode/english/python-java/general/create-postal-barcode-image-in-c-full-step-by-step-guide/)
- [Gerar código de barras postal em C# – Guia completo com código de barras Planet](/barcode/english/python-java/general/generate-postal-barcode-in-c-complete-guide-with-planet-barc/)
- [Como gerar código de barras postal em C# com Aspose.BarCode](/barcode/english/python-java/general/how-to-generate-postal-barcode-in-c-with-aspose-barcode/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}