---
category: general
date: 2026-07-18
description: Aprenda a gerar imagem de código de barras em C# usando o formato MicroPdf417.
  Configuração passo a passo das dimensões e salvamento como PNG.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to generate barcode image
- micro pdf417 barcode
- BarcodeGenerator class
- set barcode dimensions
- save barcode as png
language: pt
lastmod: 2026-07-18
og_description: Como gerar imagem de código de barras em C#? Siga este guia para criar
  um código de barras MicroPdf417, ajustar seu tamanho e exportá-lo como um arquivo
  PNG.
og_image_alt: Screenshot of a MicroPdf417 barcode image generated in C#
og_title: Como gerar imagem de código de barras em C# – Tutorial completo de MicroPdf417
schemas:
- author: Aspose
  dateModified: '2026-07-18'
  description: Learn how to generate barcode image in C# using the MicroPdf417 format.
    Step‑by‑step setup for dimensions and saving as PNG.
  headline: How to Generate Barcode Image in C# – MicroPdf417 Guide
  type: TechArticle
- description: Learn how to generate barcode image in C# using the MicroPdf417 format.
    Step‑by‑step setup for dimensions and saving as PNG.
  name: How to Generate Barcode Image in C# – MicroPdf417 Guide
  steps:
  - name: Change Image Format
    text: 'You aren’t limited to PNG. Switch to JPEG or BMP by adjusting the second
      argument of `Save`:'
  - name: Increase DPI for Print
    text: 'For high‑resolution prints, bump the `Resolution` property:'
  - name: Add Quiet Zone (Margin)
    text: 'A quiet zone helps scanners differentiate the barcode from surrounding
      graphics:'
  - name: Encode Different Data Types
    text: 'MicroPdf417 works with numeric, alphanumeric, and binary data. If you need
      to embed a URL, just replace the text:'
  type: HowTo
tags:
- barcode
- C#
- image generation
title: Como gerar imagem de código de barras em C# – Guia MicroPdf417
url: /pt/net/compact-pdf417-encoding/how-to-generate-barcode-image-in-c-micropdf417-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Como Gerar Imagem de Código de Barras em C# – Guia MicroPdf417

Já se perguntou **como gerar imagem de código de barras** em C# sem vasculhar documentos intermináveis? Você não está sozinho. Seja construindo um sistema de bilhetagem, um catálogo de produtos ou apenas precisando de um código estilo QR rápido, dominar a criação de códigos de barras pode economizar tempo e dores de cabeça.

Neste tutorial vamos percorrer os passos exatos para gerar uma **imagem de código de barras MicroPdf417** usando a classe `BarcodeGenerator`, ajustar suas dimensões e salvar o resultado como PNG. Sem enrolação—apenas um exemplo completo e executável que você pode copiar‑colar em seu projeto hoje.

## O Que Você Vai Aprender

- Configurar o `BarcodeGenerator` para o formato MicroPdf417  
- **Definir dimensões do código de barras** como largura do módulo e contagem de colunas  
- **Salvar código de barras como PNG** em uma pasta de sua escolha  
- Ajustes opcionais para saída de alta resolução e tratamento de erros  

Ao final, você será capaz de responder à pergunta *“como gerar imagem de código de barras”* com confiança, e terá uma base sólida para criar outros tipos de códigos de barras também.

---

## Pré-requisitos

Antes de mergulharmos, certifique‑se de que você tem:

1. **.NET 6.0 ou posterior** (o código também funciona no .NET Framework 4.5+)  
2. Uma referência à biblioteca **Aspose.BarCode** (ou qualquer biblioteca que forneça `BarcodeGenerator`). Você pode obtê‑la via NuGet:  

   ```bash
   dotnet add package Aspose.BarCode
   ```

3. Uma IDE decente—Visual Studio, Rider ou VS Code serve.  
4. Permissões de escrita no diretório onde você salvará o arquivo PNG.

> **Dica profissional:** Se você estiver usando uma biblioteca de código de barras diferente, os nomes das classes podem variar, mas o fluxo geral permanece o mesmo.

---

## Etapa 1: Criar um Gerador de Código de Barras MicroPdf417

A primeira coisa que você precisa é uma instância de `BarcodeGenerator` configurada para o formato de **código de barras MicroPdf417**. Esse objeto é o motor que transforma seu texto em um código visual.

```csharp
using Aspose.BarCode.Generation;

// Step 1: Initialise the generator with MicroPdf417 and the desired text
BarcodeGenerator generator = new BarcodeGenerator(
    EncodeTypes.MicroPdf417,          // Choose the MicroPdf417 format
    "Åspóse.Barcóde©");               // The data you want to encode
```

**Por que isso importa:**  
`EncodeTypes.MicroPdf417` indica à biblioteca para usar a variante compacta do PDF417, que é perfeita para strings curtas e espaço limitado. O texto pode conter caracteres Unicode, como mostrado acima, então você não está limitado ao ASCII simples.

---

## Etapa 2: Definir Dimensões do Código de Barras

Agora que o gerador existe, você provavelmente desejará controlar o tamanho de cada módulo (o quadradinho) e quantas colunas o código de barras abrange. É aqui que a palavra‑chave **definir dimensões do código de barras** entra em ação.

```csharp
// Step 2: Adjust appearance – module width and column count
generator.Parameters.Barcode.XDimension.Pixels = 2;   // Module width in pixels
generator.Parameters.Barcode.Pdf417.Columns = 4;    // Number of columns (affects height)
```

- **`XDimension.Pixels`** – Valores maiores facilitam a leitura do código de barras, mas aumentam o tamanho do arquivo.  
- **`Pdf417.Columns`** – Menos colunas comprimem o código de barras verticalmente; mais colunas o esticam horizontalmente.

> **Atenção:** Definir a largura do módulo muito baixa (por exemplo, 1 pixel) pode produzir uma imagem borrada em telas de alta DPI. Um valor entre 2‑4 pixels funciona bem para a maioria das impressoras.

---

## Etapa 3: Salvar a Imagem do Código de Barras como PNG

Com o gerador configurado, a peça final é gravar o gráfico no disco. Isso satisfaz o requisito de **salvar código de barras como png**.

```csharp
// Step 3: Export the barcode to a PNG file
string outputPath = Path.Combine(
    Environment.GetFolderPath(Environment.SpecialFolder.Desktop),
    "MicroPdf417.png");

generator.Save(outputPath, BarCodeImageFormat.Png);
Console.WriteLine($"Barcode saved to {outputPath}");
```

**O que acontece nos bastidores?**  
`Save` renderiza o código de barras em um bitmap, o codifica como PNG (compressão sem perdas) e grava os bytes no local especificado. Se o diretório não existir, `Save` lançará uma exceção—portanto, pode ser interessante envolver isso em um bloco `try/catch` para código de produção.

---

## Exemplo Completo Funcional

Juntando tudo, aqui está um aplicativo console autônomo que você pode executar imediatamente:

```csharp
using System;
using System.IO;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // 1️⃣ Initialise the generator
        BarcodeGenerator generator = new BarcodeGenerator(
            EncodeTypes.MicroPdf417,
            "Åspóse.Barcóde©");

        // 2️⃣ Set dimensions
        generator.Parameters.Barcode.XDimension.Pixels = 2;
        generator.Parameters.Barcode.Pdf417.Columns = 4;

        // 3️⃣ Define output path
        string outputPath = Path.Combine(
            Environment.GetFolderPath(Environment.SpecialFolder.Desktop),
            "MicroPdf417.png");

        // 4️⃣ Save as PNG
        try
        {
            generator.Save(outputPath, BarCodeImageFormat.Png);
            Console.WriteLine($"✅ Barcode saved to {outputPath}");
        }
        catch (Exception ex)
        {
            Console.Error.WriteLine($"❌ Failed to save barcode: {ex.Message}");
        }
    }
}
```

**Saída esperada:** Um arquivo `MicroPdf417.png` nítido na sua área de trabalho, exibindo a string codificada `Åspóse.Barcóde©`. Abra‑o com qualquer visualizador de imagens para verificar se o código de barras está claro e legível.

---

## Opções Avançadas (Opcional)

Se você deseja estender o fluxo básico, considere esses ajustes—cada um está alinhado com uma palavra‑chave secundária da nossa lista.

### Alterar Formato da Imagem

Você não está limitado a PNG. Troque para JPEG ou BMP ajustando o segundo argumento de `Save`:

```csharp
generator.Save(outputPath.Replace(".png", ".jpg"), BarCodeImageFormat.Jpeg);
```

### Aumentar DPI para Impressão

Para impressões de alta resolução, aumente a propriedade `Resolution`:

```csharp
generator.Parameters.ImageResolution.DpiX = 300;
generator.Parameters.ImageResolution.DpiY = 300;
```

### Adicionar Zona Silenciosa (Margem)

Uma zona silenciosa ajuda os scanners a diferenciar o código de barras dos gráficos ao redor:

```csharp
generator.Parameters.Barcode.QR.QrQuietZone = 4; // 4 modules of margin
```

### Codificar Diferentes Tipos de Dados

MicroPdf417 funciona com dados numéricos, alfanuméricos e binários. Se precisar incorporar uma URL, basta substituir o texto:

```csharp
generator.CodeText = "https://example.com";
```

---

## Armadilhas Comuns & Como Evitá‑las

| Sintoma | Causa Provável | Correção |
|---------|----------------|----------|
| Código de barras aparece borrado | `XDimension.Pixels` definido como 1 ou imagem redimensionada após salvar | Use no mínimo 2 pixels e evite redimensionamento pós‑processamento |
| Scanner não consegue ler o código | Muitas colunas para o comprimento de dados fornecido | Reduza `Pdf417.Columns` ou deixe a biblioteca dimensionar automaticamente (`Columns = 0`) |
| Caracteres Unicode aparecem como � | Versão da biblioteca desatualizada ou falta de suporte a fontes | Atualize Aspose.BarCode para a versão mais recente e garanta a codificação correta |
| `Save` lança `DirectoryNotFoundException` | Pasta de saída não existe | Crie o diretório antes ou use `Path.Combine` com pastas conhecidas |

---

## Testando Seu Código de Barras

Depois de gerar a imagem, você pode verificá‑la com qualquer aplicativo de leitura de códigos de barras (a maioria das câmeras de smartphones agora inclui leitores de códigos de barras embutidos). Aponte a câmera para o arquivo PNG na sua tela ou imprima‑o—se o aplicativo ler `Åspóse.Barcóde©`, você respondeu com sucesso **como gerar imagem de código de barras**.

---

## Conclusão

Cobremos tudo o que você precisa saber para **como gerar imagem de código de barras** usando C# e o formato MicroPdf417:

1. **Criar** um `BarcodeGenerator` com seus dados.  
2. **Definir dimensões do código de barras** para controlar tamanho e legibilidade.  
3. **Salvar código de barras como PNG** (ou qualquer outro formato suportado).  

A partir daqui você pode experimentar diferentes tipos de códigos de barras, ajustar DPI para impressão ou incorporar a imagem diretamente em PDFs ou relatórios. Os blocos de construção são os mesmos, então sinta‑se à vontade para trocar `EncodeTypes.MicroPdf417` por `EncodeTypes.QR` ou `EncodeTypes.Code128` e repetir os passos.

Tem perguntas sobre outros padrões de códigos de barras ou precisa de ajuda para ajustar a aparência? Deixe um comentário abaixo, e feliz codificação!

## O Que Você Deve Aprender a Seguir?

Os tutoriais a seguir abordam tópicos estreitamente relacionados que se baseiam nas técnicas demonstradas neste guia. Cada recurso inclui exemplos de código completos e funcionais com explicações passo a passo para ajudá‑lo a dominar recursos adicionais da API e explorar abordagens de implementação alternativas em seus próprios projetos.

- [Como gerar código de barras Aztec com proporção personalizada usando Aspose.BarCode para .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)
- [Como Gerar Código de Barras - Tipos Unidimensionais](/barcode/english/net/one-dimensional-barcode-types/)
- [Como Gerar Códigos DataMatrix (ECC 200) com Aspose.BarCode para .NET](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-ecc-200-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}