---
category: general
date: 2026-09-19
description: Exemplo de gerador de código de barras mostrando como alterar a altura,
  criar DataBar Omni‑Directional e ajustar as dimensões do código de barras para saída
  de imagem em C#.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- barcode generator example
- how to change height
- how to create databar
- adjust barcode dimensions
- create barcode image c#
language: pt
lastmod: 2026-09-19
og_description: exemplo de gerador de código de barras que ensina como alterar a altura,
  criar DataBar Omni‑Directional e ajustar as dimensões do código de barras para uma
  imagem PNG em C#
og_image_alt: Screenshot of a DataBar Omni‑Directional barcode generated in C#
og_title: Exemplo de gerador de código de barras em C# – guia passo a passo
schemas:
- author: Aspose
  dateModified: '2026-09-19'
  description: barcode generator example showing how to change height, create DataBar
    Omni‑Directional, and adjust barcode dimensions for C# image output
  headline: How to build a barcode generator example in C#
  type: TechArticle
tags:
- barcode
- C#
- Aspose.BarCode
title: Como criar um exemplo de gerador de código de barras em C#
url: /pt/python-java/general/how-to-build-a-barcode-generator-example-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Exemplo de gerador de código de barras em C# – guia completo de programação

Se você precisa de um **exemplo de gerador de código de barras** para um projeto .NET, este guia mostra exatamente como criar, configurar e salvar um código de barras DataBar Omni‑Directional usando C#. Você aprenderá como alterar a altura, ajustar as dimensões do código de barras e gerar uma imagem PNG de alta qualidade — tudo em uma única aplicação console executável.

As etapas abaixo cobrem tudo, desde a instalação do SDK necessário até o ajuste da X‑dimension e da altura da barra. Ao final do tutorial, você terá um gerador de código de barras pronto para uso que pode ser integrado à emissão de notas, inventário ou qualquer fluxo de trabalho de leitura.

## Pré-requisitos

* .NET 6.0 SDK ou posterior instalado  
* Visual Studio 2022 (ou qualquer IDE que suporte .NET)  
* Uma licença ativa para **Aspose.BarCode for .NET** (a versão de avaliação gratuita funciona para testes)

Se preferir outra biblioteca, os conceitos de ajuste de dimensões e salvamento da imagem permanecem os mesmos; basta substituir as chamadas de API conforme necessário.

## Etapa 1: Configurar o projeto e adicionar o pacote Aspose.BarCode

Crie um novo projeto console e faça referência à biblioteca de código de barras.

```bash
dotnet new console -n BarcodeDemo
cd BarcodeDemo
dotnet add package Aspose.BarCode
```

O comando `dotnet add package` obtém a versão estável mais recente do Aspose.BarCode, que inclui suporte total para símbolos DataBar Omni‑Directional.

## Etapa 2: Escrever o exemplo completo de gerador de código de barras

Abra o **Program.cs** e substitua seu conteúdo pelo código a seguir. Este bloco contém o **exemplo completo de gerador de código de barras** — sem partes ausentes.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // 1️⃣ Create a barcode generator for a DataBar Omni‑Directional symbol
            // The GTIN‑14 value "(01)12345678901231" is encoded as a numeric string.
            BarcodeGenerator generator = new BarcodeGenerator(
                EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");

            // 2️⃣ Adjust barcode dimensions
            // Set the X‑dimension (module width) to 2 pixels – this controls the thin bar width.
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // 3️⃣ How to change height
            // Set the bar height to 30 pixels. Height influences readability on larger scanners.
            generator.Parameters.Barcode.BarHeight.Pixels = 30;

            // 4️⃣ Optional: fine‑tune additional properties (quiet zone, color, etc.)
            generator.Parameters.Barcode.QrCodeErrorLevel = QRErrorLevel.LevelM; // example property
            generator.Parameters.ImageOptions.ForeColor = System.Drawing.Color.Black;
            generator.Parameters.ImageOptions.BackColor = System.Drawing.Color.White;

            // 5️⃣ Create barcode image C#
            // Save the generated barcode as a PNG file in the output folder.
            string outputPath = "DatabarOmniDirectional.png";
            generator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"Barcode saved to {outputPath}");
        }
    }
}
```

### Por que cada linha importa

* **Criar um gerador de código de barras** – O construtor `BarcodeGenerator` vincula o tipo de codificação (`EncodeTypes.DatabarOmniDirectional`) aos dados que você deseja incorporar. Este é o núcleo da etapa **how to create databar**.  
* **Ajustar as dimensões do código de barras** – A propriedade `XDimension.Pixels` define a largura da barra mais estreita. Alterar esse valor influencia o tamanho geral e a confiabilidade da leitura.  
* **Como mudar a altura** – A propriedade `BarHeight.Pixels` controla o tamanho vertical. Aumentar a altura melhora a legibilidade para scanners portáteis, enquanto diminuí‑la economiza espaço em etiquetas pequenas.  
* **Ajustes opcionais** – Definir cores de primeiro plano/fundo ou níveis de correção de erro é opcional, mas demonstra como ampliar o conceito de **adjust barcode dimensions**.  
* **Criar imagem de código de barras C#** – O método `Save` grava o código de barras no disco. Usar `BarCodeImageFormat.Png` garante compressão sem perdas, ideal para a maioria das aplicações.

## Etapa 3: Compilar e executar o exemplo

Compile e execute o programa:

```bash
dotnet run
```

Você deverá ver a saída no console:

```
Barcode saved to DatabarOmniDirectional.png
```

Um arquivo chamado **DatabarOmniDirectional.png** aparece na pasta do projeto. Ao abrir a imagem, você verá um código de barras DataBar Omni‑Directional nítido, pronto para leitura.

## Como mudar a altura depois de criada

Se precisar gerar códigos de barras com alturas variadas, encapsule a atribuição da altura em um método:

```csharp
static void SetBarHeight(BarcodeGenerator gen, int heightPixels)
{
    gen.Parameters.Barcode.BarHeight.Pixels = heightPixels;
}
```

Chame `SetBarHeight(generator, 45);` antes de `Save`. Essa abordagem permite que você **how to change height** dinamicamente com base na entrada do usuário ou em arquivos de configuração.

## Como criar códigos de barras DataBar Omni‑Directional com dados diferentes

A simbologia DataBar Omni‑Directional suporta GTIN‑14, GTIN‑13 e outros identificadores numéricos. Para codificar um valor diferente, basta substituir a string no construtor:

```csharp
new BarcodeGenerator(EncodeTypes.DatabarOmniDirectional, "(01)98765432109876");
```

Lembre‑se de manter os dados numéricos e devidamente formatados; caso contrário, o gerador lançará uma `BarcodeException`.

## Ajustar as dimensões do código de barras para diferentes cenários de impressão

Impressoras e tamanhos de etiquetas diferentes exigem X‑dimensions e alturas distintas. Use a tabela a seguir como referência rápida:

| Cenário                         | X‑Dimension (pixels) | Bar Height (pixels) |
|--------------------------------|----------------------|---------------------|
| Etiqueta pequena (25 mm × 15 mm)  | 1                    | 20                  |
| Etiqueta média (50 mm × 30 mm)   | 2                    | 30                  |
| Etiqueta grande (100 mm × 50 mm) | 3                    | 45                  |

Aplique esses valores definindo `generator.Parameters.Barcode.XDimension.Pixels` e `BarHeight.Pixels` conforme necessário.

## Dica profissional: validar o código de barras gerado

Antes de enviar uma etiqueta, você pode verificar sua legibilidade programaticamente:

```csharp
using Aspose.BarCode.BarCodeRecognition;

// ...

BarCodeReader reader = new BarCodeReader(outputPath, DecodeType.DatabarOmniDirectional);
if (reader.Read())
{
    Console.WriteLine("Validation succeeded: " + reader.GetCodeText());
}
else
{
    Console.WriteLine("Validation failed – barcode may be unreadable.");
}
```

Este trecho demonstra uma verificação rápida de sanidade **adjust barcode dimensions**, garantindo que o código de barras atenda aos requisitos de leitura.

## Armadilhas comuns e como evitá‑las

| Armadilha                              | Por que acontece                              | Correção                                                                 |
|----------------------------------------|-----------------------------------------------|--------------------------------------------------------------------------|
| Usar dados não numéricos para DataBar  | DataBar espera formatos GTIN numéricos        | Garanta que a string corresponda ao padrão `(01)XXXXXXXXXXXXX`.         |
| Definir X‑dimension como 0 ou negativo | A biblioteca lança `ArgumentOutOfRangeException` | Use no mínimo 1 pixel; teste na impressora alvo primeiro.                |
| Salvar em uma pasta somente leitura    | `UnauthorizedAccessException` ao chamar `Save` | Escolha um diretório gravável ou execute o aplicativo com permissões adequadas. |
| Esquecer de descartar `BarCodeReader`  | Vazamento de memória em serviços de longa execução | Envolva o leitor em um bloco `using` ou chame `Dispose()` manualmente.   |

Resolver essas questões antecipadamente economiza tempo de depuração e melhora a estabilidade em produção.

## Recapitulação do código-fonte completo

Abaixo está o programa completo, pronto‑para‑copiar, que implementa o **exemplo de gerador de código de barras** do início ao fim.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;
using Aspose.BarCode.BarCodeRecognition;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // Create generator – how to create databar
            BarcodeGenerator generator = new BarcodeGenerator(
                EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");

            // Adjust barcode dimensions
            generator.Parameters.Barcode.XDimension.Pixels = 2;   // thin bar width
            generator.Parameters.Barcode.BarHeight.Pixels = 30; // how to change height

            // Optional visual tweaks
            generator.Parameters.ImageOptions.ForeColor = System.Drawing.Color.Black;
            generator.Parameters.ImageOptions.BackColor = System.Drawing.Color.White;

            // Save image – create barcode image c#
            string filePath = "DatabarOmniDirectional.png";
            generator.Save(filePath, BarCodeImageFormat.Png);
            Console.WriteLine($"Barcode saved to {filePath}");

            // Validate barcode (optional)
            using (BarCodeReader reader = new BarCodeReader(filePath, DecodeType.DatabarOmniDirectional))
            {
                if (reader.Read())
                    Console.WriteLine($"Validation succeeded: {reader.GetCodeText()}");
                else
                    Console.WriteLine("Validation failed – barcode may be unreadable.");
            }
        }
    }
}
```

Executar este programa gera um arquivo PNG que se parece com isto (ilustração):

![Código de barras DataBar Omni‑Directional gerado em C#](https://example.com/og-image.png "Código de barras DataBar Omni‑Directional gerado em C#")

*Texto alternativo da imagem*: **Código de barras DataBar Omni‑Directional gerado em C#** (corresponde a `og_image_alt`).

## Conclusão

Agora você tem um **exemplo de gerador de código de barras** que demonstra como mudar a altura, como criar símbolos DataBar Omni‑Directional e como **ajustar as dimensões do código de barras** para leitura ideal. O código C# completo salva uma imagem PNG, a valida e pode ser estendido para geração em massa ou integração a serviços web.

Em seguida, explore tópicos relacionados como **criar códigos QR com Aspose.BarCode**, **processamento em lote de múltiplos valores de código de barras**, ou **incorporar códigos de barras em documentos PDF**. Cada um desses se baseia nos mesmos fundamentos abordados neste guia.

Feliz codificação, e que seus códigos de barras estejam sempre legíveis!

## O que você deve aprender a seguir?

Os tutoriais a seguir cobrem tópicos intimamente relacionados que se baseiam nas técnicas demonstradas neste guia. Cada recurso inclui exemplos de código completos e funcionais com explicações passo a passo para ajudá‑lo a dominar recursos adicionais da API e explorar abordagens de implementação alternativas em seus próprios projetos.

- [Exemplo de Gerador de Código de Barras – Construir Imagem DataBar em C#](/barcode/english/python-java/general/barcode-generator-example-build-databar-image-in-c/)
- [Como gerar e ajustar a altura do código de barras para Databar unidimensional usando Aspose.BarCode para .NET](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-barcode-height-adjustment/)
- [Exemplo de gerador de código de barras em C# – definir largura e altura](/barcode/english/python-java/general/barcode-generator-example-in-c-set-width-and-height/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}