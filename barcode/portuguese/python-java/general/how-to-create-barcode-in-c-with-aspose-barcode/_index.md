---
category: general
date: 2026-09-26
description: Aprenda como criar códigos de barras em C# usando Aspose.BarCode. Este
  guia passo a passo inclui um exemplo de gerador de código de barras e mostra como
  ajustar a altura das barras.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode c#
- barcode generator example
- how to adjust bar height
- change barcode height
- generate barcode aspose
language: pt
lastmod: 2026-09-26
og_description: Crie código de barras em C# com Aspose.BarCode. Siga este guia para
  gerar um código de barras, ajustar a altura das barras e salvar imagens PNG.
og_image_alt: Diagram illustrating how to create barcode in C# using Aspose.BarCode
og_title: Criar código de barras em C# com Aspose.BarCode – guia completo
schemas:
- author: Aspose
  dateModified: '2026-09-26'
  description: Learn how to create barcode in C# using Aspose.BarCode. This step‑by‑step
    guide includes a barcode generator example and shows how to adjust bar height.
  headline: How to create barcode in C# with Aspose.BarCode
  type: TechArticle
- description: Learn how to create barcode in C# using Aspose.BarCode. This step‑by‑step
    guide includes a barcode generator example and shows how to adjust bar height.
  name: How to create barcode in C# with Aspose.BarCode
  steps:
  - name: Import required namespaces
    text: '```csharp using System; using Aspose.BarCode.Generation; using Aspose.BarCode;
      ```'
  - name: Initialise the barcode generator
    text: We’ll generate a **Databar Omni‑Directional** symbol that encodes a GTIN‑14
      value. The constructor takes the symbology and the raw data string.
  - name: Set common barcode parameters
    text: 'Two visual parameters are most often tweaked: the X‑dimension (the narrow
      bar width) and the overall bar height.'
  - name: Save the first image (30‑pixel height)
    text: '```csharp // Save the barcode as a 30‑pixel‑high PNG generator.Save("DatabarBarHeight30Pixels.png",
      BarCodeImageFormat.Png); ```'
  - name: Change the bar height to 60 pixels
    text: Now we demonstrate **how to adjust bar height** at runtime. The same `generator`
      instance is reused; only the `BarHeight` property changes.
  - name: Full source code
    text: 'Putting everything together yields a concise, runnable program:'
  - name: Switching to a different symbology
    text: 'If you need a QR code instead of a Databar, replace the `EncodeTypes` value:'
  - name: Using `BarHeight` in millimetres
    text: 'Aspose.BarCode also supports physical units. To set a height of 10 mm:'
  - name: Handling errors
    text: 'If the data string does not conform to the selected symbology, `BarcodeGenerator`
      throws an `ArgumentException`. Wrap the generation logic in a try‑catch block
      to provide a friendly message:'
  type: HowTo
tags:
- barcode
- C#
- Aspose
title: Como criar código de barras em C# com Aspose.BarCode
url: /pt/python-java/general/how-to-create-barcode-in-c-with-aspose-barcode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Como criar barcode em C# com Aspose.BarCode  

Se você precisa **criar barcode c#** projetos rapidamente, Aspose.BarCode fornece uma API fluente que cuida do trabalho pesado. Neste tutorial você verá um **exemplo completo de gerador de barcode**, aprenderá **como ajustar a altura da barra**, e exportará o resultado como arquivos PNG.  

Seja construindo um sistema de checkout de varejo, gerando etiquetas de inventário ou automatizando etiquetas de envio, a capacidade de mudar programaticamente o tamanho visual de um barcode é essencial. Este guia assume que você tem um entendimento básico de C# e um ambiente de desenvolvimento como o Visual Studio 2022.  

## Pré-requisitos  

* .NET 6.0 SDK ou posterior instalado.  
* Visual Studio 2022 (ou qualquer IDE C#).  
* Uma licença ativa do Aspose.BarCode (a versão de avaliação gratuita funciona para aprendizado).  

Você também precisará adicionar o pacote NuGet Aspose.BarCode ao seu projeto:

```bash
dotnet add package Aspose.BarCode
```

> **Dica profissional:** Se você planeja gerar muitos barcodes em um loop, reutilize uma única instância de `BarcodeGenerator` e modifique apenas os parâmetros que mudam. Isso reduz alocações de memória e melhora o desempenho.

## Como criar barcode em C# com Aspose.BarCode  

As seções a seguir percorrem cada passo do **exemplo de gerador de barcode**. O código é autocontido; copie-o para uma nova aplicação console e execute.

### Etapa 1: Importar namespaces necessários  

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;
```

Esses namespaces dão acesso à classe `BarcodeGenerator` e à enumeração `EncodeTypes`.

### Etapa 2: Inicializar o gerador de barcode  

Vamos gerar um símbolo **Databar Omni‑Directional** que codifica um valor GTIN‑14. O construtor recebe a simbologia e a string de dados bruta.

```csharp
// Initialise a generator for Databar Omni‑Directional
BarcodeGenerator generator = new BarcodeGenerator(
    EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");
```

O valor `EncodeTypes.DatabarOmniDirectional` indica ao Aspose.BarCode qual padrão de barcode usar. A string de dados segue o formato GS1 Application Identifier, que é comum para barcodes de varejo.

### Etapa 3: Definir parâmetros comuns do barcode  

Dois parâmetros visuais são os mais frequentemente ajustados: a X‑dimension (largura da barra estreita) e a altura total da barra.  

```csharp
// Set the narrow bar width to 2 pixels
generator.Parameters.Barcode.XDimension.Pixels = 2;

// Set the initial bar height to 30 pixels
generator.Parameters.Barcode.BarHeight.Pixels = 30;
```

A **X‑dimension** controla a densidade do barcode, enquanto **BarHeight** determina o tamanho vertical de cada barra. Ajustar **BarHeight** é exatamente o que você precisa quando deseja **alterar a altura do barcode** para diferentes mídias de impressão.

### Etapa 4: Salvar a primeira imagem (altura de 30 pixels)  

```csharp
// Save the barcode as a 30‑pixel‑high PNG
generator.Save("DatabarBarHeight30Pixels.png", BarCodeImageFormat.Png);
```

O método `Save` grava a imagem renderizada no disco. O nome do arquivo indica claramente a altura usada, o que ajuda ao comparar diferentes resultados.

### Etapa 5: Alterar a altura da barra para 60 pixels  

Agora demonstramos **como ajustar a altura da barra** em tempo de execução. A mesma instância `generator` é reutilizada; apenas a propriedade `BarHeight` é alterada.

```csharp
// Increase the bar height to 60 pixels
generator.Parameters.Barcode.BarHeight.Pixels = 60;

// Save the larger barcode
generator.Save("DatabarBarHeight60Pixels.png", BarCodeImageFormat.Png);
```

Como o gerador mantém todas as outras configurações (simbologia, dados, X‑dimension), a única diferença visual entre os dois arquivos PNG é o tamanho vertical das barras.

### Código-fonte completo  

Juntando tudo resulta em um programa conciso e executável:

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // 1️⃣ Initialise the generator for Databar Omni‑Directional
            BarcodeGenerator generator = new BarcodeGenerator(
                EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");

            // 2️⃣ Configure visual parameters
            generator.Parameters.Barcode.XDimension.Pixels = 2;   // narrow bar width
            generator.Parameters.Barcode.BarHeight.Pixels = 30; // first height

            // 3️⃣ Save the 30‑pixel‑high image
            generator.Save("DatabarBarHeight30Pixels.png", BarCodeImageFormat.Png);
            Console.WriteLine("Saved 30‑pixel barcode.");

            // 4️⃣ Change the bar height to 60 pixels (how to adjust bar height)
            generator.Parameters.Barcode.BarHeight.Pixels = 60;

            // 5️⃣ Save the 60‑pixel‑high image
            generator.Save("DatabarBarHeight60Pixels.png", BarCodeImageFormat.Png);
            Console.WriteLine("Saved 60‑pixel barcode.");

            // Optional: clean up resources
            generator.Dispose();
        }
    }
}
```

**Saída esperada**  

Executar o programa cria dois arquivos PNG no diretório de trabalho do executável:

* `DatabarBarHeight30Pixels.png` – um barcode com altura de barra de 30 px.  
* `DatabarBarHeight60Pixels.png` – o mesmo barcode, mas cada barra tem o dobro da altura.

Abra as imagens em qualquer visualizador; você verá que o padrão geral permanece idêntico enquanto a dimensão vertical muda, confirmando que a operação de **alterar a altura do barcode** foi bem-sucedida.

## Variações avançadas  

### Alterando para uma simbologia diferente  

Se você precisar de um QR code em vez de um Databar, substitua o valor `EncodeTypes`:

```csharp
generator = new BarcodeGenerator(EncodeTypes.QR, "https://example.com");
```

Todas as outras configurações de parâmetros (X‑dimension, BarHeight) ainda se aplicam onde fizer sentido.

### Usando `BarHeight` em milímetros  

Aspose.BarCode também suporta unidades físicas. Para definir uma altura de 10 mm:

```csharp
generator.Parameters.Barcode.BarHeight.Millimeters = 10;
```

Isso é útil quando você gera barcodes para layouts de impressão que exigem medidas exatas.

### Tratamento de erros  

Se a string de dados não estiver em conformidade com a simbologia selecionada, `BarcodeGenerator` lança uma `ArgumentException`. Envolva a lógica de geração em um bloco try‑catch para fornecer uma mensagem amigável:

```csharp
try
{
    generator.Save("output.png", BarCodeImageFormat.Png);
}
catch (ArgumentException ex)
{
    Console.Error.WriteLine($"Invalid barcode data: {ex.Message}");
}
```

## Perguntas frequentes respondidas  

* **Alterar BarHeight afeta a capacidade de leitura?**  
  O barcode permanece legível enquanto a X‑dimension e a zona silenciosa geral atendem às especificações da simbologia. Aumentar a altura apenas torna as barras mais longas; nunca reduz o contraste.

* **Posso definir alturas diferentes para barras individuais?**  
  Não. A propriedade `BarHeight` se aplica uniformemente a todo o símbolo. Para designs de altura variável, seria necessário uma rotina de renderização personalizada fora do escopo do Aspose.BarCode.

* **O PNG é o melhor formato para impressão?**  
  PNG preserva dados de pixel sem perdas, tornando‑o ideal para exibição em tela. Para trabalhos de impressão de alta resolução, considere `BarCodeImageFormat.Tiff` ou `Pdf` para manter informações vetoriais.

## Conclusão  

Agora você sabe como **criar barcode c#** aplicações com Aspose.BarCode, viu um **exemplo completo de gerador de barcode** e entende **como ajustar a altura da barra** para atender a diferentes requisitos de layout. Reutilizando a mesma instância do gerador e modificando apenas `BarHeight`, você pode eficientemente **alterar a altura do barcode** sem reconstruir o objeto inteiro.

A partir daqui você pode explorar:

* Gerar outras simbologias (`EncodeTypes.Code128`, `EncodeTypes.EAN13`).  
* Exportar para SVG ou PDF para gráficos escaláveis.  
* Incorporar barcodes diretamente em documentos Word ou Excel usando Aspose.Words ou Aspose.Cells.

Feliz codificação, e aproveite a flexibilidade que o Aspose.BarCode traz para seus projetos de barcode em C#!

## O que você deve aprender a seguir?

Os tutoriais a seguir cobrem tópicos intimamente relacionados que se baseiam nas técnicas demonstradas neste guia. Cada recurso inclui exemplos de código completos e funcionais com explicações passo a passo para ajudá-lo a dominar recursos adicionais da API e explorar abordagens de implementação alternativas em seus próprios projetos.

- [Como gerar e ajustar a altura do barcode para Databar unidimensional usando Aspose.BarCode para .NET](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-barcode-height-adjustment/)
- [Como criar um arquivo PNG de barcode com altura ajustável em C#](/barcode/english/python-java/general/how-to-create-a-barcode-png-file-with-adjustable-height-in-c/)
- [Como gerar barcode em C# – Guia completo do Aspose.BarCode](/barcode/english/python-java/general/how-to-generate-barcode-in-c-complete-aspose-barcode-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}