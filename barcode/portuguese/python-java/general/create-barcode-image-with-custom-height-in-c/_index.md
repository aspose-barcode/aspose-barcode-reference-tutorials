---
category: general
date: 2026-10-28
description: Crie imagem de código de barras em C# e aprenda como ajustar a altura
  usando a API BarcodeGenerator. Guia passo a passo para altura personalizada do código
  de barras e alteração da altura das barras.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode image
- how to adjust height
- c# barcode generator
- custom barcode height
- change barcode height
language: pt
lastmod: 2026-10-28
og_description: Crie uma imagem de código de barras em C# e veja instantaneamente
  como ajustar a altura. Siga este exemplo completo para definir a altura personalizada
  do código de barras com o BarcodeGenerator.
og_image_alt: Screenshot showing a generated barcode image with a custom height
og_title: Criar imagem de código de barras com altura personalizada em C# – guia completo
schemas:
- author: Aspose
  dateModified: '2026-10-28'
  description: Create barcode image in C# and learn how to adjust height using the
    BarcodeGenerator API. Step‑by‑step guide for custom barcode height and changing
    bar height.
  headline: Create barcode image with custom height in C#
  type: TechArticle
tags:
- barcode
- C#
- image generation
- GS1‑Databar
title: Criar imagem de código de barras com altura personalizada em C#
url: /pt/python-java/general/create-barcode-image-with-custom-height-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Criar imagem de código de barras com altura personalizada em C#

Se você precisa **criar imagem de código de barras** e controlar suas dimensões, este guia mostra exatamente como fazer. Usando a biblioteca Aspose.BarCode .NET, você pode gerar um código de barras GS1‑Databar Omni‑Directional e, em seguida, **como ajustar a altura** para atender a qualquer requisito de layout.

Você percorrerá um programa completo e executável que demonstra um **gerador de código de barras c#**, explica cada propriedade definida e mostra duas saídas diferentes — uma com altura de barra de 30 pixels e outra com altura de barra de 60 pixels. Ao final, você será capaz de **alterar a altura do código de barras** programaticamente para qualquer tipo de código de barras suportado pela biblioteca.

## Pré-requisitos

- .NET 6.0 SDK ou posterior (o código também funciona com .NET Framework 4.6+)
- Visual Studio 2022 ou qualquer editor que possa compilar projetos C#
- Pacote NuGet Aspose.BarCode para .NET (`Install-Package Aspose.BarCode`)
- Familiaridade básica com a sintaxe C#

> **Dica profissional:** Se você estiver usando um pipeline de CI, adicione o pacote NuGet ao seu arquivo `csproj` para que a compilação o restaure automaticamente.

## Etapa 1: Configurar o projeto e importar namespaces

Crie um novo projeto de console e adicione as declarações `using` necessárias. Os namespaces fornecem acesso ao `BarcodeGenerator`, `EncodeTypes` e aos auxiliares de formato de imagem.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace BarcodeHeightDemo
{
    class Program
    {
        static void Main()
        {
            // The rest of the tutorial code lives here.
        }
    }
}
```

> **Por que isso importa:** Importar os namespaces corretos evita erros de compilação e torna a API descobrível no IntelliSense.

## Etapa 2: Inicializar o **gerador de código de barras c#** para um código GS1‑Databar Omni‑Directional

O construtor recebe dois argumentos: o tipo de código de barras (`EncodeTypes.DatabarOmniDirectional`) e a string de dados. A string de dados deve seguir o formato de Identificador de Aplicação GS1, por exemplo, `(01)12345678901231`.

```csharp
// Create a barcode generator for a GS1‑Databar Omni‑Directional code
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.DatabarOmniDirectional,
    "(01)12345678901231");
```

> **Explicação:** O objeto `BarcodeGenerator` é o ponto de entrada para todas as configurações relacionadas a códigos de barras. Depois de ter essa instância, você pode ajustar dimensões, cores e formato de saída.

## Etapa 3: Definir uma X‑dimension comum (largura em pixels da barra mais estreita)

Uma X‑dimension de 2 pixels é um bom ponto de partida para a maioria dos cenários de exibição em tela.

```csharp
// Set a 2‑pixel X‑dimension (width of the smallest bar)
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

> **Por que definir a X‑dimension?** Ela controla a largura total do código de barras. Mantê‑la consistente garante que a alteração da altura da barra não distorça o equilíbrio visual.

## Etapa 4: **Criar imagem de código de barras** com altura de barra de 30 pixels

Agora configuramos a altura da barra, salvamos a primeira imagem e, em seguida, alteramos a altura para a segunda.

```csharp
// Configure a 30‑pixel bar height
barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 30;

// Save the first image
string output30 = "DatabarBarHeight30Pixels.png";
barcodeGenerator.Save(output30, BarCodeImageFormat.Png);
Console.WriteLine($"Saved barcode with 30 px height to {output30}");
```

> **Resultado:** Você obtém um arquivo PNG onde cada barra vertical tem 30 pixels de altura. A X‑dimension permanece em 2 pixels, portanto a largura total permanece inalterada.

## Etapa 5: **Como ajustar a altura** – altere a altura da barra para 60 pixels

Para demonstrar **altura personalizada de código de barras**, basta atribuir um novo valor à mesma propriedade e salvar novamente.

```csharp
// Change the bar height to 60 pixels
barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 60;

// Save the second image
string output60 = "DatabarBarHeight60Pixels.png";
barcodeGenerator.Save(output60, BarCodeImageFormat.Png);
Console.WriteLine($"Saved barcode with 60 px height to {output60}");
```

> **Insight chave:** A propriedade `BarHeight` é mutável; você não precisa recriar a instância `BarcodeGenerator`. Isso torna barato gerar múltiplos tamanhos em um loop ou processo em lote.

## Etapa 6: Verificar a saída

Execute o programa de console (`dotnet run`). Após a execução, você deverá ver dois arquivos PNG na pasta de saída do projeto:

- `DatabarBarHeight30Pixels.png` – barras curtas (30 px)
- `DatabarBarHeight60Pixels.png` – barras altas (60 px)

Ambas as imagens contêm os mesmos dados codificados, mas a altura visual difere, o que é útil ao integrar códigos de barras em formulários, rótulos de produtos ou componentes de UI com diferentes restrições de espaço.

![Criar imagem de código de barras com altura personalizada](barcode-example.png){.align-center width="600" alt="Criar imagem de código de barras com altura personalizada"}

> **Dica:** Abra os arquivos PNG em qualquer visualizador de imagens. O código de barras mais alto deve ser exatamente o dobro do tamanho vertical do mais curto, enquanto o espaçamento horizontal permanece idêntico.

## Etapa 7: Variações comuns e casos de borda

| Situação | Configuração recomendada |
|-----------|--------------------------|
| **Impressão em uma impressora de etiquetas de alta resolução** | Use uma X‑dimension maior (por exemplo, 4 px) e aumente `BarHeight` proporcionalmente. |
| **Exibição em tela de baixa DPI** | Mantenha `XDimension` em 1 px e `BarHeight` entre 20‑40 px para legibilidade. |
| **Geração de códigos QR ou códigos de barras 2‑D** | A propriedade `BarHeight` é ignorada; use `EncodeTypes.QR` e ajuste `ImageHeight` em vez disso. |
| **Geração em lote de várias alturas** | Percorra um array de alturas e chame `Save` dentro do loop; não é necessário recriar o gerador a cada iteração. |

### Lidando com alturas inválidas

A biblioteca lança uma `ArgumentOutOfRangeException` se você definir `BarHeight` com um valor não positivo. Proteja-se contra isso com uma verificação simples:

```csharp
int desiredHeight = 0; // example invalid value
if (desiredHeight <= 0)
{
    throw new ArgumentException("Bar height must be greater than zero.");
}
barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = desiredHeight;
```

## Código-fonte completo (pronto para copiar)

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace BarcodeHeightDemo
{
    class Program
    {
        static void Main()
        {
            // 1️⃣ Create the barcode generator for GS1‑Databar Omni‑Directional
            BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
                EncodeTypes.DatabarOmniDirectional,
                "(01)12345678901231");

            // 2️⃣ Set a common 2‑pixel X‑dimension
            barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;

            // 3️⃣ First image – 30 pixel bar height
            barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 30;
            string path30 = "DatabarBarHeight30Pixels.png";
            barcodeGenerator.Save(path30, BarCodeImageFormat.Png);
            Console.WriteLine($"Saved barcode with 30 px height to {path30}");

            // 4️⃣ Second image – 60 pixel bar height
            barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 60;
            string path60 = "DatabarBarHeight60Pixels.png";
            barcodeGenerator.Save(path60, BarCodeImageFormat.Png);
            Console.WriteLine($"Saved barcode with 60 px height to {path60}");
        }
    }
}
```

> **Por que isso funciona:** Todas as configurações necessárias (`EncodeTypes`, `XDimension`, `BarHeight`) são aplicadas antes de cada chamada `Save`. A mesma instância `BarcodeGenerator` é reutilizada, o que é eficiente em memória e fácil de ler.

## Conclusão

Agora você sabe como **criar arquivos de imagem de código de barras** em C# e alterar **precisamente a altura do código de barras** usando a API `BarcodeGenerator`. Ao ajustar `BarHeight.Pixels` você obtém uma **altura personalizada de código de barras** sem reconstruir o gerador, tornando a solução ideal para criação dinâmica de etiquetas, renderização de UI ou pipelines de processamento em lote.

Em seguida, explore tópicos relacionados, como **como ajustar a largura**, **adicionar texto legível por humanos**, ou **exportar para SVG para uso web escalável**. O mesmo padrão — definir uma propriedade, chamar `Save` — se aplica a esses cenários, permitindo que você amplie este exemplo com confiança.

## O que você deve aprender a seguir?

Os tutoriais a seguir abordam tópicos estreitamente relacionados que se baseiam nas técnicas demonstradas neste guia. Cada recurso inclui exemplos de código completos e funcionais com explicações passo a passo para ajudá‑lo a dominar recursos adicionais da API e explorar abordagens de implementação alternativas em seus próprios projetos.

- [Como mudar a altura do código de barras em C# – Guia completo](/barcode/english/python-java/general/how-to-change-barcode-height-in-c-complete-guide/)
- [Exemplo de gerador de código de barras – criar códigos Planet e RM4SCC com altura personalizada](/barcode/english/python-java/general/barcode-generator-example-create-planet-and-rm4scc-barcodes/)
- [Como criar código de barras rm4scc e controlar sua altura em C#](/barcode/english/python-java/general/how-to-create-rm4scc-barcode-and-control-its-height-in-c/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}