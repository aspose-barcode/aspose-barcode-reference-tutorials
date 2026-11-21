---
category: general
date: 2026-11-20
description: Crie imagem de código de barras em C# usando Aspose.BarCode. Aprenda
  como gerar código de barras PDF417 com um layout personalizado e salvá-lo como PNG.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode image
- generate pdf417 barcode
- how to generate pdf417
language: pt
lastmod: 2026-11-20
og_description: Crie imagem de código de barras em C# com Aspose.BarCode. Este guia
  mostra como gerar código de barras PDF417, personalizar o layout e exportar para
  PNG.
og_image_alt: Screenshot of generated barcode image created with PDF417 using C#
og_title: Criar imagem de código de barras com PDF417 em C# – tutorial completo
schemas:
- author: Aspose
  dateModified: '2026-11-20'
  description: Create barcode image in C# using Aspose.BarCode. Learn how to generate
    PDF417 barcode with a custom layout and save it as PNG.
  headline: How to create barcode image with PDF417 in C# – step‑by‑step guide
  type: TechArticle
- description: Create barcode image in C# using Aspose.BarCode. Learn how to generate
    PDF417 barcode with a custom layout and save it as PNG.
  name: How to create barcode image with PDF417 in C# – step‑by‑step guide
  steps:
  - name: Why this code works
    text: '* **`BarcodeGenerator`** is the entry point for all barcode types. By passing
      `EncodeTypes.Pdf417` you tell the library to produce a PDF417 symbol. * **Columns
      and rows** are the primary levers for layout. Fewer columns produce a taller
      barcode; more columns make it wider. Adjust these values to fit'
  - name: Adjusting data length
    text: 'PDF417 can encode up to 1,850 characters. If you need to encode longer
      strings, consider splitting the data across multiple barcodes or using the **compact
      mode**:'
  - name: Controlling image size
    text: 'The default image size is calculated from the module size (the smallest
      square in the barcode). You can explicitly set the DPI or scale the image after
      generation:'
  - name: Handling special characters
    text: 'PDF417 supports the full ASCII set. If your data contains Unicode characters,
      ensure you encode the string as UTF‑8:'
  type: HowTo
tags:
- barcode
- PDF417
- C#
title: Como criar imagem de código de barras PDF417 em C# – guia passo a passo
url: /pt/net/compact-pdf417-encoding/how-to-create-barcode-image-with-pdf417-in-c-step-by-step-gu/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Como criar imagem de código de barras com PDF417 em C# – guia passo a passo

Se você precisa **criar imagem de código de barras** em uma aplicação .NET, este guia mostra exatamente **como gerar código de barras PDF417** com um layout personalizado e salvá‑lo como um arquivo PNG. Você verá o código completo e executável, entenderá por que cada configuração importa e aprenderá armadilhas comuns para que seu código de barras funcione de forma confiável em produção.

Neste tutorial você irá:

* Inicializar o gerador Aspose.BarCode para PDF417.
* Configurar a contagem de colunas e linhas para controlar a forma do código de barras.
* Exportar o resultado como uma imagem PNG de alta qualidade.
* Explorar configurações opcionais para correção de erros e comprimento dos dados.

O único pré‑requisito é um SDK .NET recente (.NET 6 ou posterior) e uma licença ou avaliação gratuita do **Aspose.BarCode for .NET**.

---

## Pré‑requisitos e configuração

Antes de começar, certifique‑se de que você tem:

| Requisito | Por que é importante |
|-----------|----------------------|
| .NET 6 SDK ou mais recente | Fornece o runtime para o aplicativo console C#. |
| Visual Studio 2022 (ou VS Code) | Fornece uma IDE com IntelliSense para a API Aspose. |
| Pacote NuGet Aspose.BarCode for .NET | Fornece `BarcodeGenerator`, `EncodeTypes` e auxiliares de exportação de imagem. |
| Permissão de escrita na pasta de saída | O gerador grava o arquivo PNG no disco. |

Você pode adicionar o pacote NuGet com o seguinte comando:

```bash
dotnet add package Aspose.BarCode
```

---

## Etapa 1: Criar um novo projeto console

Primeiro, crie uma aplicação console simples que hospedará a lógica de geração de código de barras.

```csharp
using System;
using Aspose.BarCode.Generation;

namespace Pdf417Demo
{
    class Program
    {
        static void Main(string[] args)
        {
            // The full barcode generation flow is encapsulated in GeneratePdf417().
            GeneratePdf417();
            Console.WriteLine("Barcode image created successfully.");
        }

        // -----------------------------------------------------------------
        // Generates a PDF417 barcode with a custom layout and saves it as PNG.
        // -----------------------------------------------------------------
        static void GeneratePdf417()
        {
            // -------------------------------------------------------------
            // Step 2: Initialize the barcode generator for PDF417 with text.
            // -------------------------------------------------------------
            var generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Sample data for PDF417 barcode");

            // -------------------------------------------------------------
            // Step 3: Define a custom layout – set the number of columns and rows.
            // -------------------------------------------------------------
            generator.Parameters.Barcode.Pdf417.Columns = 4; // Controls horizontal density.
            generator.Parameters.Barcode.Pdf417.Rows = 9;    // Controls vertical density.

            // Optional: increase error correction level for noisy environments.
            // Values: 0 (no correction) to 8 (maximum correction).
            generator.Parameters.Barcode.Pdf417.ErrorCorrectionLevel = 2;

            // -------------------------------------------------------------
            // Step 4: Save the generated barcode as a PNG image.
            // -------------------------------------------------------------
            string outputPath = System.IO.Path.Combine(
                Environment.CurrentDirectory, "CustomPdf417.png");
            generator.Save(outputPath, BarCodeImageFormat.Png);
        }
    }
}
```

### Por que este código funciona

* **`BarcodeGenerator`** é o ponto de entrada para todos os tipos de código de barras. Ao passar `EncodeTypes.Pdf417` você indica à biblioteca que deve produzir um símbolo PDF417.
* **Colunas e linhas** são os principais alavancas para o layout. Menos colunas produzem um código de barras mais alto; mais colunas o tornam mais largo. Ajuste esses valores para caber no espaço onde a imagem será exibida (por exemplo, uma impressora de etiquetas vs. uma página web).
* **Correção de erros** melhora a confiabilidade da leitura quando o código de barras pode estar borrado ou impresso em mídia de baixa qualidade. O nível padrão é 0; aumentá‑lo levemente (2–4) é um bom compromisso entre tamanho e robustez.
* **`Save`** grava a imagem no disco no formato PNG, que preserva bordas nítidas e funciona em navegadores e dispositivos móveis.

Ao executar o programa (`dotnet run`), ele cria `CustomPdf417.png` na pasta do projeto. O PNG se parece com isto:

![Imagem de código de barras PDF417 gerada](https://example.com/images/pdf417-sample.png "Captura de tela da imagem de código de barras gerada com PDF417 usando C#")

*Texto alternativo:* **criar imagem de código de barras** – código de barras PDF417 gerado em C# e salvo como PNG.

---

## Etapa 2: Ajustar finamente o código de barras para cenários reais

### Ajustando o comprimento dos dados

PDF417 pode codificar até 1.850 caracteres. Se precisar codificar strings mais longas, considere dividir os dados em vários códigos de barras ou usar o **modo compacto**:

```csharp
generator.Parameters.Barcode.Pdf417.CompactMode = true;
```

O modo compacto reduz o número de linhas, mas pode aumentar a densidade visual, portanto teste com seu scanner.

### Controlando o tamanho da imagem

O tamanho padrão da imagem é calculado a partir do tamanho do módulo (o menor quadrado no código de barras). Você pode definir explicitamente o DPI ou redimensionar a imagem após a geração:

```csharp
generator.Parameters.ImageResolution = new Resolution(300); // 300 DPI for printing.
```

Ou, após salvar, redimensione com System.Drawing se precisar de uma miniatura.

### Lidando com caracteres especiais

PDF417 suporta o conjunto completo de ASCII. Se seus dados contêm caracteres Unicode, certifique‑se de codificar a string como UTF‑8:

```csharp
var generator = new BarcodeGenerator(EncodeTypes.Pdf417, System.Text.Encoding.UTF8.GetString(bytes));
```

---

## Etapa 3: Armadilhas comuns e como evitá‑las

| Armadilha | Sintoma | Correção |
|-----------|---------|----------|
| Muitas colunas para os dados fornecidos | O código de barras aparece truncado ou lança uma exceção. | Reduza `Columns` ou deixe a biblioteca dimensionar automaticamente omitindo a configuração. |
| Baixa correção de erros em uma impressora ruidosa | Os scanners falham ao ler o código de barras intermitentemente. | Aumente `ErrorCorrectionLevel` para pelo menos 2. |
| Salvando em um diretório somente leitura | `UnauthorizedAccessException` em tempo de execução. | Use uma pasta gravável como `Environment.CurrentDirectory` ou `Path.GetTempPath()`. |
| Usando uma versão desatualizada do Aspose.BarCode | Propriedades ausentes como `CompactMode`. | Atualize o pacote NuGet para a versão estável mais recente. |

---

## Etapa 4: Verificar o resultado

Para confirmar que o código de barras foi gerado corretamente, você pode:

1. Abra `CustomPdf417.png` em qualquer visualizador de imagens – o código de barras deve estar nítido, com módulos pretos claros sobre fundo branco.
2. Use um aplicativo gratuito de scanner PDF417 (disponível para iOS e Android) para escanear a imagem. O aplicativo deve exibir **“Sample data for PDF417 barcode”**.
3. (Opcional) Carregue a imagem em um teste unitário usando `System.Drawing.Bitmap` e verifique se o pixel em `(0,0)` é preto, confirmando que a imagem não está vazia.

```csharp
using System.Drawing;

Bitmap bmp = new Bitmap("CustomPdf417.png");
bool topLeftIsBlack = bmp.GetPixel(0, 0).R == 0;
Console.WriteLine($"Top‑left pixel black? {topLeftIsBlack}");
```

Se a asserção passar, você conseguiu **criar imagem de código de barras** e **gerar código de barras PDF417** programaticamente.

---

## Conclusão

Agora você sabe como **criar imagem de código de barras** em C# ao **gerar código de barras PDF417** com um layout personalizado, ajustando a correção de erros e exportando para PNG. O exemplo completo demonstra cada passo necessário — desde a inicialização do `BarcodeGenerator` até a gravação da imagem final — para que você possa copiar, colar e executá‑lo em seu próprio projeto.

Em seguida, você pode explorar:

* **Incorporar o PNG em uma API web** para que clientes possam solicitar códigos de barras sob demanda (`generate pdf417` como serviço).
* **Geração em lote** para grandes conjuntos de dados — percorrer uma lista de strings e armazenar cada PNG em um banco de dados.
* **Formatos de saída alternativos** (SVG, JPEG) alterando `BarCodeImageFormat`.

Sinta‑se à vontade para experimentar as proporções de colunas/linhas, níveis de correção de erros e resolução da imagem para atender aos requisitos exatos do seu hardware de scanner ou design de UI. Feliz codificação!

## O que você deve aprender a seguir?

Os tutoriais a seguir abordam tópicos estreitamente relacionados que se baseiam nas técnicas demonstradas neste guia. Cada recurso inclui exemplos de código completos e funcionais com explicações passo a passo para ajudá‑lo a dominar recursos adicionais da API e explorar abordagens de implementação alternativas em seus próprios projetos.

- [Como criar imagem de código de barras PDF417 em C# – guia completo](/barcode/english/net/compact-pdf417-encoding/generate-pdf417-barcode-in-c-complete-guide/)
- [Como criar imagem de código de barras PDF417 em C# com opções Macro PDF417](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-image-in-c-with-macro-pdf417-op/)
- [Como criar código de barras micro PDF417 e gerar PNG em C#](/barcode/english/net/compact-pdf417-encoding/how-to-create-micro-pdf417-barcode-and-generate-png-in-c/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}