---
category: general
date: 2026-07-18
description: Crie código de barras GS1 em C# e aprenda como gerar imagens de código
  de barras, definir colunas e usar o Barcode Generator C# para resultados impecáveis.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create gs1 barcode
- how to generate barcode
- how to set columns
- barcode generator c#
- create barcode image
language: pt
lastmod: 2026-07-18
og_description: Crie códigos de barras GS1 em C# rapidamente. Aprenda a gerar imagens
  de códigos de barras, configurar colunas e dominar o Gerador de Código de Barras
  C# em minutos.
og_image_alt: Screenshot showing a generated GS1 Micro PDF417 barcode image
og_title: Crie um código de barras GS1 em C# – Guia completo de programação
schemas:
- author: Aspose
  dateModified: '2026-07-18'
  description: Create GS1 barcode in C# and learn how to generate barcode images,
    set columns, and use Barcode Generator C# for flawless results.
  headline: Create GS1 Barcode in C# – Complete Step‑by‑Step Guide
  type: TechArticle
- description: Create GS1 barcode in C# and learn how to generate barcode images,
    set columns, and use Barcode Generator C# for flawless results.
  name: Create GS1 Barcode in C# – Complete Step‑by‑Step Guide
  steps:
  - name: What if I need a different image format?
    text: Just replace `BarCodeImageFormat.Png` with `BarCodeImageFormat.Jpeg`, `Bmp`,
      or `Gif`. The library handles the conversion automatically.
  - name: Can I generate multiple barcodes in a loop?
    text: Absolutely. Wrap the generator creation and `Save` call inside a `foreach`
      that iterates over your data set. Remember to reset or create a fresh `BarcodeGenerator`
      instance for each unique data string to avoid parameter bleed‑over.
  - name: How does error handling work?
    text: 'If the data string violates GS1 rules (e.g., missing mandatory AI), the
      library throws a `BarcodeException`. Catch it and log the problematic input:'
  - name: What about DPI settings for printing?
    text: 'You can control the output resolution via `barcodeGenerator.Parameters.ImageResolution`.
      For high‑quality printouts, set it to 300 dpi:'
  type: HowTo
tags:
- barcode
- C#
- GS1
title: Criar código de barras GS1 em C# – Guia completo passo a passo
url: /pt/net/gs1-barcode-encoding/create-gs1-barcode-in-c-complete-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Criar Código de Barras GS1 em C# – Guia Completo Passo a Passo

Já se perguntou como **criar código de barras GS1** usando C# sem perder a cabeça? Você não está sozinho. Seja construindo um sistema de leitura de armazém ou precisando incorporar dados de produto em um aplicativo móvel, dominar a criação de um código de barras GS1 é uma habilidade valiosa para qualquer desenvolvedor .NET.

Neste tutorial vamos percorrer os passos exatos para **criar código de barras GS1** em imagens, explicar **como gerar código de barras** com configurações finamente ajustadas e mostrar os pequenos truques que tornam todo o processo indolor. Ao final, você terá um arquivo PNG pronto para uso e uma compreensão clara da API subjacente.

## Pré-requisitos

Antes de começarmos, certifique‑se de que você tem:

- .NET 6.0 ou posterior instalado (o código também funciona com .NET Framework 4.7+).
- Uma referência à biblioteca **Barcode Generator C#** (por exemplo, Aspose.BarCode for .NET ou qualquer pacote NuGet compatível).
- Uma pasta no disco onde você possa gravar a imagem de saída (o exemplo usa `YOUR_DIRECTORY` – substitua‑a por um caminho real).

Nenhuma outra ferramenta externa é necessária.

## Como Criar Código de Barras GS1 em C# – Visão Geral

Dividiremos a solução em quatro partes lógicas:

1. **Instanciar o gerador de código de barras** com a simbologia GS1 Micro PDF417 e a string de dados bruta.
2. **Configurar parâmetros visuais** como a X‑dimension (largura do módulo) para renderização mais nítida.
3. **Definir a contagem de colunas** para controlar o layout da matriz – é aqui que **como definir colunas** se torna crucial.
4. **Salvar o resultado** como um arquivo PNG, completando a etapa de **criar imagem de código de barras**.

Cada parte corresponde a um pequeno trecho de código testável, para que você possa copiar‑colar e executar imediatamente.

---

## Etapa 1: Instanciar o Gerador de Código de Barras (Criar Código de Barras GS1)

A primeira coisa que você precisa fazer é criar uma instância de `BarcodeGenerator`. Este objeto armazenará todas as configurações e dados necessários para **criar código de barras GS1**.

```csharp
using Aspose.BarCode.Generation;

// Step 1: Create a barcode generator for GS1 Micro PDF417 with the required data
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.GS1MicroPdf417,
    "(01)12345678901231(240)ABCD123456789012345");
```

> **Por que isso importa:** O enum `EncodeTypes.GS1MicroPdf417` informa à biblioteca que você deseja um símbolo Micro PDF417 compatível com GS1, e a string de dados segue a sintaxe do Identificador de Aplicação (AI) da GS1. Obter o formato AI correto é a base de uma operação válida de **criar código de barras GS1**.

---

## Etapa 2: Ajustar a X‑Dimension (Como Gerar Código de Barras com Mais Detalhe)

A legibilidade de um código de barras frequentemente depende da largura do módulo, conhecida como X‑dimension. Definir um valor menor em pixels produz detalhes mais finos, o que pode ser importante para rótulos pequenos.

```csharp
// Step 2: Set the X‑dimension (module width) to 2 pixels for finer detail
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

> **Dica de especialista:** Se você planeja imprimir o código de barras em uma impressora de alta resolução, 2 pixels é um padrão seguro. Para telas de baixa resolução, talvez seja melhor aumentá‑lo para 3 ou 4 pixels para evitar bordas borradas.

---

## Etapa 3: Como Definir Colunas – Controlando a Matriz PDF417

A família PDF417 permite especificar o número de colunas em sua matriz. Isso influencia tanto o tamanho físico quanto o desempenho de leitura. Aqui está o trecho que responde **como definir colunas** para um código de barras GS1 Micro PDF417.

```csharp
// Step 3: Define the number of columns in the PDF417 matrix (4 columns)
barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 4;
```

> **Quando mudar:** Se o espaço horizontal do seu rótulo for limitado, reduza a contagem de colunas. Por outro lado, aumente as colunas para obter uma pegada vertical mais compacta. A biblioteca ajustará automaticamente a contagem de linhas para acomodar os dados.

---

## Etapa 4: Salvar o Código de Barras – Criar Imagem do Código de Barras

Agora que o gerador está totalmente configurado, você pode finalmente **criar imagem de código de barras** salvando‑a no disco. A linha a seguir grava um arquivo PNG, mas você também pode escolher JPEG, BMP ou GIF.

```csharp
// Step 4: Save the generated barcode as a PNG image
barcodeGenerator.Save("YOUR_DIRECTORY/GS1MicroPdf417_903to905.png", BarCodeImageFormat.Png);
```

> **Saída esperada:** Após executar o programa, `GS1MicroPdf417_903to905.png` aparecerá na pasta de destino. Abra‑o com qualquer visualizador de imagens e você deverá ver um símbolo GS1 Micro PDF417 limpo e legível.

---

## Exemplo Completo Funcional

Abaixo está o programa completo e executável que une as quatro etapas. Copie‑o para um novo projeto de console e pressione **F5**.

```csharp
using System;
using Aspose.BarCode.Generation;

namespace Gs1BarcodeDemo
{
    class Program
    {
        static void Main(string[] args)
        {
            // 1️⃣ Create a barcode generator for GS1 Micro PDF417 with the required data
            BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
                EncodeTypes.GS1MicroPdf417,
                "(01)12345678901231(240)ABCD123456789012345");

            // 2️⃣ Set the X‑dimension (module width) to 2 pixels for finer detail
            barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;

            // 3️⃣ Define the number of columns in the PDF417 matrix (4 columns)
            barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 4;

            // 4️⃣ Save the generated barcode as a PNG image
            const string outputPath = @"C:\Temp\GS1MicroPdf417_903to905.png";
            barcodeGenerator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"GS1 barcode created successfully at: {outputPath}");
        }
    }
}
```

**Executar este código** produzirá um arquivo PNG que você pode incorporar em relatórios, imprimir na embalagem do produto ou enviar para um aplicativo móvel de leitura. A mensagem no console confirma o local, o que é útil para depuração rápida.

---

## Perguntas Frequentes & Casos Limite

### E se eu precisar de um formato de imagem diferente?

Basta substituir `BarCodeImageFormat.Png` por `BarCodeImageFormat.Jpeg`, `Bmp` ou `Gif`. A biblioteca lida com a conversão automaticamente.

### Posso gerar múltiplos códigos de barras em um loop?

Absolutamente. Envolva a criação do gerador e a chamada `Save` dentro de um `foreach` que itere sobre seu conjunto de dados. Lembre‑se de redefinir ou criar uma nova instância de `BarcodeGenerator` para cada string de dados única, a fim de evitar que parâmetros se misturem.

### Como funciona o tratamento de erros?

Se a string de dados violar as regras da GS1 (por exemplo, AI obrigatório ausente), a biblioteca lança uma `BarcodeException`. Capture‑a e registre a entrada problemática:

```csharp
try
{
    // generator code here
}
catch (BarcodeException ex)
{
    Console.Error.WriteLine($"Invalid GS1 data: {ex.Message}");
}
```

### E quanto às configurações de DPI para impressão?

Você pode controlar a resolução de saída via `barcodeGenerator.Parameters.ImageResolution`. Para impressões de alta qualidade, defina‑a para 300 dpi:

```csharp
barcodeGenerator.Parameters.ImageResolution = 300;
```

---

## Resultado Visual

Abaixo está uma imagem de espaço reservado ilustrando como o resultado final de **criar código de barras GS1** se parece. Substitua a URL pelo caminho real do seu PNG gerado ao publicar o tutorial.

![GS1 Micro PDF417 barcode generated by C# code – create barcode image](https://example.com/gs1-micro-pdf417-sample.png)

*Texto alternativo:* **Código de Barras GS1 Micro PDF417 gerado por código C# – criar imagem de código de barras**

---

## Recapitulação: O Que Conquistamos

- **Criar código de barras GS1** usando a biblioteca Aspose.BarCode.
- Aprendeu **como gerar código de barras** com X‑dimension personalizada para renderização nítida.
- Dominou **como definir colunas** para se adequar às restrições do seu rótulo.
- Utilizou **barcode generator c#** para configurar e exportar uma **create barcode image** em formato PNG.

Tudo isso foi condensado em um fluxo de quatro etapas que você pode adaptar a qualquer projeto .NET.

---

## Próximos Passos & Tópicos Relacionados

Agora que você pode **criar código de barras GS1** em imagens, considere explorar:

- **Incorporar códigos de barras em relatórios PDF** (procure “barcode generator c# PDF export”).
- **Vinculação de dados dinâmica** para geração de código de barras em tempo real em aplicativos web ASP.NET Core.
- **Verificação de leitura** usando um SDK móvel para garantir que o código de barras gerado atenda aos padrões da indústria.

Se encontrar algum obstáculo, sinta‑se à vontade para deixar um comentário — feliz codificação!

---

## O Que Você Deve Aprender a Seguir?

Os tutoriais a seguir abordam tópicos intimamente relacionados que ampliam as técnicas demonstradas neste guia. Cada recurso inclui exemplos de código completos com explicações passo a passo para ajudá‑lo a dominar recursos adicionais da API e explorar abordagens alternativas de implementação em seus próprios projetos.

- [Criar imagem de código de barras c# – Configurar Linhas & Colunas Codablock F](/barcode/english/net/codablock-f-encoding/codablock-f-row-column-configuration/)
- [Criar imagem de código de barras DotCode – linhas & colunas (Aspose.BarCode)](/barcode/english/net/dotcode-barcode-configuration/dotcode-rows-columns-configuration/)
- [Como Criar Zona Silenciosa de Código de Barras para ITF-14 Usando Aspose.BarCode para .NET](/barcode/english/net/itf-14-barcode-customization/itf-14-barcode-quiet-zone-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}