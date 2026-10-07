---
category: general
date: 2026-09-23
description: Como redimensionar código de barras em C# usando Aspose.BarCode. Aprenda
  a gerar código de barras em C#, personalizar o tamanho e exportar a imagem do código
  de barras de forma eficiente.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to resize barcode
- generate barcode c#
- barcode generator example
- create databar barcode
- export barcode image
language: pt
lastmod: 2026-09-23
og_description: Como redimensionar código de barras em C# com Aspose.BarCode. Siga
  este guia para gerar código de barras em C#, ajustar dimensões e exportar a imagem
  do código de barras.
og_image_alt: Screenshot showing resized DataBar Omni‑directional barcode generated
  in C#
og_title: Como redimensionar código de barras em C# – tutorial completo do Aspose.BarCode
schemas:
- author: Aspose
  dateModified: '2026-09-23'
  description: How to resize barcode in C# using Aspose.BarCode. Learn to generate
    barcode C# code, customize size, and export barcode image efficiently.
  headline: How to resize barcode in C# with Aspose.BarCode – step‑by‑step guide
  type: TechArticle
- description: How to resize barcode in C# using Aspose.BarCode. Learn to generate
    barcode C# code, customize size, and export barcode image efficiently.
  name: How to resize barcode in C# with Aspose.BarCode – step‑by‑step guide
  steps:
  - name: '**Create Databar barcode** objects with custom data.'
    text: '**Create Databar barcode** objects with custom data.'
  - name: Adjust `BarHeight` (the core of resizing).
    text: Adjust `BarHeight` (the core of resizing).
  - name: Export PNG files for any required size.
    text: Export PNG files for any required size.
  type: HowTo
tags:
- barcode
- C#
- Aspose
- image processing
title: Como redimensionar código de barras em C# com Aspose.BarCode – guia passo a
  passo
url: /pt/python-java/general/how-to-resize-barcode-in-c-with-aspose-barcode-step-by-step/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Como redimensionar código de barras em C# com Aspose.BarCode – guia passo a passo

Se você precisa **redimensionar código de barras** em uma aplicação .NET, este tutorial mostra o código exato que você pode copiar‑colar e executar hoje. Você aprenderá como **gerar código de barras C#**, ajustar a altura das barras e **exportar arquivos de imagem de código de barras** sem sair do seu IDE.

Criar códigos de barras é comum em sistemas de inventário, etiquetas de envio e terminais de ponto de venda. Ao final deste guia você será capaz de **criar imagens de código de barras Databar** em qualquer altura que precisar, e entenderá as propriedades principais que controlam tamanho, resolução e formato de arquivo.

## Pré‑requisitos

- .NET 6 ou superior (o exemplo também funciona com .NET Framework 4.6+)
- Pacote NuGet Aspose.BarCode for .NET (`Install-Package Aspose.BarCode`)
- Familiaridade básica com a sintaxe C# e Visual Studio (ou qualquer IDE C#)

Nenhuma biblioteca adicional é necessária; o Aspose.BarCode cuida da renderização, escala e exportação de imagens internamente.

## Etapa 1: Configurar o projeto e importar Aspose.BarCode

Crie um novo projeto de console (ou integre em um existente) e adicione o namespace Aspose.BarCode:

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;
using System.Drawing.Imaging;   // required for BarCodeImageFormat
```

> **Dica profissional:** Use a versão mais recente do Aspose.BarCode (a partir de setembro 2026) para aproveitar correções de bugs e novas simbologias de código de barras.

## Etapa 2: Inicializar um gerador de código de barras DataBar Omni‑directional

O **exemplo de gerador de código de barras** começa especificando a simbologia (`EncodeTypes.DatabarOmniDirectional`) e o payload de dados. O payload segue o formato do Identificador de Aplicação GS1 `(01)12345678901231`.

```csharp
// Step 2: Create a DataBar Omni‑directional barcode generator with the desired data
BarcodeGenerator barcode = new BarcodeGenerator(
    EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");
```

Este objeto contém todos os parâmetros que você modificará posteriormente, como X‑dimension, altura da barra e formato da imagem.

## Etapa 3: Definir parâmetros comuns de tamanho

Antes de exportar, defina a X‑dimension (largura da barra mais estreita) e uma altura inicial da barra. A X‑dimension é expressa em pixels; um valor de `2` funciona bem na maioria das resoluções de tela.

```csharp
// Step 3: Set common barcode parameters – X‑dimension and initial bar height (30 px)
barcode.Parameters.Barcode.XDimension.Pixels = 2;   // thin bar width
barcode.Parameters.Barcode.BarHeight.Pixels = 30; // initial height
```

> **Por que isso importa:** A propriedade `BarHeight` influencia diretamente o tamanho visual do código de barras. Alterá‑la é o núcleo de **como redimensionar código de barras** no Aspose.BarCode.

## Etapa 4: Exportar a primeira imagem de código de barras (altura de 30 px)

Agora você pode **exportar imagem de código de barras** para um arquivo PNG. O método `Save` renderiza automaticamente o código de barras com os parâmetros atuais.

```csharp
// Step 4: Save the barcode image with a 30‑pixel height
barcode.Save("DatabarBarHeight30Pixels.png", BarCodeImageFormat.Png);
```

O arquivo resultante se parece com isto:

![Exemplo de redimensionamento de código de barras](https://example.com/images/databar-30px.png){: .align-center alt="Exemplo de redimensionamento de código de barras – altura de 30 pixels"}

## Etapa 5: Alterar a altura da barra para criar um código de barras maior

Para demonstrar **como redimensionar código de barras** dinamicamente, ajuste a propriedade `BarHeight` e salve novamente. Isso **não** requer a criação de uma nova instância `BarcodeGenerator`; basta modificar o objeto existente.

```csharp
// Step 5: Change the bar height to 60 pixels for a larger barcode
barcode.Parameters.Barcode.BarHeight.Pixels = 60;
```

## Etapa 6: Exportar a imagem de código de barras redimensionada (altura de 60 px)

```csharp
// Step 6: Save the barcode image with the new 60‑pixel height
barcode.Save("DatabarBarHeight60Pixels.png", BarCodeImageFormat.Png);
```

Agora você tem dois arquivos PNG—um com 30 px e outro com 60 px—mostrando como os mesmos dados podem ser renderizados em tamanhos diferentes.

### Saída esperada

| Nome do arquivo                     | Altura da barra (px) | Resultado visual |
|-------------------------------------|----------------------|------------------|
| `DatabarBarHeight30Pixels.png`      | 30                   | ![código de barras 30 px](https://example.com/images/databar-30px.png){: alt="Código de barras DataBar Omni‑directional de 30 pixels"} |
| `DatabarBarHeight60Pixels.png`      | 60                   | ![código de barras 60 px](https://example.com/images/databar-60px.png){: alt="Código de barras DataBar Omni‑directional de 60 pixels"} |

Ambas as imagens são códigos de barras GS1‑128 DataBar válidos e prontos para leitura.

## Etapa 7: Opcional – Ajustar configurações visuais adicionais

Embora o objetivo principal seja **como redimensionar código de barras**, você também pode querer ajustar:

| Propriedade | Descrição | Valores típicos |
|-------------|-----------|-----------------|
| `XDimension.Pixels` | Largura da barra mais estreita | 1–4 |
| `BarHeight.Pixels`  | Altura total do código de barras | 20–200 |
| `Resolution` | DPI para saída raster | 72, 150, 300 |
| `ForeColor` / `BackColor` | Cores de primeiro plano e fundo | `Color.Black`, `Color.White` |

Exemplo:

```csharp
barcode.Parameters.Barcode.XDimension.Pixels = 3;
barcode.Parameters.Barcode.ForeColor = Color.DarkBlue;
barcode.Parameters.Barcode.BackColor = Color.White;
barcode.Parameters.ImageResolution.DpiX = 300;
barcode.Parameters.ImageResolution.DpiY = 300;
```

Esses ajustes não afetam a lógica de **redimensionamento**, mas dão controle total sobre a qualidade final da imagem.

## Problemas comuns e como evitá‑los

| Problema | Sintoma | Correção |
|----------|---------|----------|
| Altura da barra não muda | Imagens salvas parecem idênticas | Certifique‑se de modificar `barcode.Parameters.Barcode.BarHeight.Pixels` *antes* de cada chamada ao `Save`. |
| Código de barras ilegível | O scanner relata “não pode ler” | Mantenha `XDimension` ≥ 2 px para DataBar Omni‑directional; barras muito finas podem impedir a leitura. |
| Arquivo PNG está borrado | Exportado com DPI baixo | Defina `barcode.Parameters.ImageResolution.DpiX/Y` para pelo menos 150 para imagens com qualidade de impressão. |
| Arquivo sobrescrito acidentalmente | Nova imagem substitui a antiga | Use nomes de arquivo únicos ou inclua o valor da altura no nome, como mostrado acima. |

## Exemplo completo e executável

Copie todo o bloco abaixo para um novo aplicativo de console (`Program.cs`). O código compila e executa como‑está, gerando os dois arquivos PNG na pasta de saída do projeto.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;
using System.Drawing.Imaging;

class Program
{
    static void Main()
    {
        // 1️⃣ Create a DataBar Omni‑directional barcode generator
        BarcodeGenerator barcode = new BarcodeGenerator(
            EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");

        // 2️⃣ Set common parameters
        barcode.Parameters.Barcode.XDimension.Pixels = 2;   // thin bar width
        barcode.Parameters.Barcode.BarHeight.Pixels = 30; // first height

        // 3️⃣ Export first image (30 px height)
        barcode.Save("DatabarBarHeight30Pixels.png", BarCodeImageFormat.Png);
        Console.WriteLine("Saved 30‑pixel barcode.");

        // 4️⃣ Change height to 60 px
        barcode.Parameters.Barcode.BarHeight.Pixels = 60;

        // 5️⃣ Export second image (60 px height)
        barcode.Save("DatabarBarHeight60Pixels.png", BarCodeImageFormat.Png);
        Console.WriteLine("Saved 60‑pixel barcode.");

        // Optional: tweak additional settings (uncomment if needed)
        // barcode.Parameters.Barcode.ForeColor = System.Drawing.Color.DarkBlue;
        // barcode.Parameters.ImageResolution.DpiX = 300;
        // barcode.Parameters.ImageResolution.DpiY = 300;
    }
}
```

Executando o programa produz:

```
Saved 30‑pixel barcode.
Saved 60‑pixel barcode.
```

Verifique a pasta de saída para os dois arquivos PNG. Ambos estão prontos para impressão, incorporação em PDFs ou envio a um dispositivo remoto.

## Conclusão

Neste guia abordamos **como redimensionar código de barras** em C# usando Aspose.BarCode, demonstramos um **exemplo completo de gerador de código de barras** e mostramos como **exportar arquivos de imagem de código de barras** em diferentes alturas. Agora você sabe como:

1. **Criar objetos Databar barcode** com dados personalizados.  
2. Ajustar `BarHeight` (o núcleo do redimensionamento).  
3. Exportar arquivos PNG em qualquer tamanho necessário.  

A partir daqui você pode explorar personalizações adicionais—outras simbologias, esquemas de cores ou formatos vetoriais como SVG. O mesmo padrão (`barcode.Parameters.Barcode.BarHeight.Pixels = <valor>`) funciona para qualquer tipo de código de barras suportado pelo Aspose.BarCode, permitindo que você aplique com confiança o conhecimento de **como redimensionar código de barras** em toda a sua aplicação.

---

**Próximos passos**

- Experimente redimensionar outras simbologias (QR, Code128) para ver como altura e largura interagem.  
- Use `BarCodeImageFormat.Svg` para gerar gráficos vetoriais escaláveis para páginas web.  
- Integre as imagens geradas em relatórios PDF com Aspose.PDF ou iTextSharp.  

Feliz codificação, e aproveite a flexibilidade que a geração programática de códigos de barras oferece!

## O que você deve aprender a seguir?

Os tutoriais a seguir abordam tópicos intimamente relacionados que ampliam as técnicas demonstradas neste guia. Cada recurso inclui exemplos de código completos e explicações passo a passo para ajudá‑lo a dominar recursos adicionais da API e explorar abordagens alternativas em seus próprios projetos.

- [How to Generate and Adjust Barcode Height for One-Dimensional Databar using Aspose.BarCode for .NET](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-barcode-height-adjustment/)
- [How to Generate Barcode – Code 39 Configuration with Aspose.BarCode](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-code-39-configuration/)
- [How to Generate DataMatrix Barcodes Using Aspose.BarCode for .NET – Step‑by‑Step Guide](/barcode/english/net/datamatrix-barcode-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}