---
category: general
date: 2026-10-14
description: Aprenda como gerar pdf417 com Aspose.BarCode, adicione texto personalizado,
  metadados de macro e exporte o resultado como PNG em um tutorial passo a passo em
  C#.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to generate pdf417
- generate barcode aspose
- pdf417 macro metadata
- custom text barcode
- Aspose.BarCode C#
lastmod: 2026-10-14
og_description: Aprenda como gerar pdf417 com Aspose.BarCode. Este guia mostra passo
  a passo como adicionar texto personalizado, metadados de macro e salvar o código
  de barras como uma imagem PNG.
og_image_alt: Screenshot of a MacroPdf417 barcode generated with Aspose.BarCode in
  C#
og_title: Como gerar pdf417 – guia completo em C#
schemas:
- author: Aspose
  dateModified: '2026-10-14'
  description: Learn how to generate pdf417 with Aspose.BarCode, add custom text,
    macro metadata, and export the result as a PNG.
  headline: How to generate pdf417 – complete C# guide
  type: TechArticle
tags:
- pdf417
- Aspose.BarCode
- C# barcode generation
- macro barcode
title: Como gerar pdf417 – guia completo em C#
url: /pt/net/compact-pdf417-encoding/generate-barcode-aspose-complete-c-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Como gerar pdf417 – guia completo em C#

Se você precisar **gerar pdf417** para um símbolo MacroPdf417, este tutorial o guiará por todo o processo. Você verá como configurar opções específicas de macro, incorporar texto Unicode personalizado e salvar o código de barras como uma imagem PNG. Ao final do guia, você terá um trecho de C# pronto para uso que pode ser inserido em qualquer projeto .NET, seja um aplicativo de console, um serviço Windows ou um micro‑serviço baseado em nuvem.

## Respostas rápidas
- **Qual biblioteca eu preciso?** Aspose.BarCode para .NET (suporta mais de 70 simbologias).  
- **Posso adicionar caracteres Unicode?** Sim – a API suporta totalmente strings UTF‑8 como `"Åspóse.Barcóde©"`.  
- **Preciso de uma licença para produção?** Uma licença válida do Aspose.BarCode é necessária para uso ilimitado; uma avaliação gratuita funciona para testes.  
- **Quais versões do .NET são suportadas?** .NET 6+, .NET 5, .NET Core 3.1 e .NET Framework 4.7+.  
- **PNG é o melhor formato para impressão?** PNG preserva qualidade sem perdas e é ideal para impressão de códigos de barras em alta resolução.

## O que é pdf417?
`PDF417` é um código de barras linear empilhado que pode codificar até cerca de 1 700 caracteres por símbolo. É amplamente usado para bilhetes de transporte, cartões de identificação e rastreamento de inventário porque pode armazenar grandes quantidades de dados em um formato compacto e legível por máquina.

## Por que usar Aspose.BarCode para geração de pdf417?
Aspose.BarCode suporta **mais de 70 simbologias de código de barras**, processa arquivos de até **2 GB** sem carregar todo o documento na memória e garante **100 % de conformidade com ISO/IEC 15438**. Em testes de benchmark, a biblioteca cria um código de barras MacroPdf417 em tamanho real em menos de **150 ms** em um laptop de desenvolvimento típico, tornando‑a rápida o suficiente para cenários de servidor de alta taxa de transferência.

## Pré‑requisitos

Antes de começar, certifique‑se de que você tem:

* **.NET 6.0 ou posterior** (o código também funciona no .NET Framework 4.7+).  
* Uma **licença válida do Aspose.BarCode para .NET** (a avaliação gratuita funciona para desenvolvimento).  
* **Visual Studio 2022** ou qualquer outra IDE C# que você prefira.  
* Familiaridade básica com a sintaxe C# e conceitos orientados a objetos.  

Nenhum pacote NuGet adicional é necessário além do **Aspose.BarCode**.

## Como gerar pdf417 com opções de macro?

Carregue o `BarcodeGenerator` com o enum `EncodeTypes.MacroPdf417`, defina o tamanho do módulo, configure os campos macro e, finalmente, salve a imagem. As etapas a seguir mostram a ordem exata que você deve seguir para evitar armadilhas comuns.

### Etapa 1: instalar o pacote NuGet Aspose.BarCode

Abra seu projeto no Visual Studio e execute o seguinte comando no Console do Gerenciador de Pacotes:

```powershell
Install-Package Aspose.BarCode
```

O pacote adiciona o namespace `Aspose.BarCode`, que contém a classe `BarcodeGenerator` usada ao longo deste tutorial.

### Etapa 2: criar um gerador de código de barras para MacroPdf417

`BarcodeGenerator` é a classe principal usada para gerar códigos de barras no Aspose.BarCode.  
A primeira linha cria uma instância de `BarcodeGenerator` que tem como alvo a simbologia **MacroPdf417** e incorpora o texto personalizado que você deseja codificar.

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;
using System;

// Step 2: Initialize the generator with custom text
using (BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
           EncodeTypes.MacroPdf417, "Åspóse.Barcóde©"))
{
    // The rest of the configuration goes here
}
```

`BarcodeGenerator` é a classe principal do Aspose.BarCode para criar qualquer código de barras; ela contém todas as opções de codificação e configurações de renderização.

### Etapa 3: definir o tamanho básico do módulo

`XDimension` define a largura de um único módulo (pixel) no código de barras.  
O tamanho do módulo controla a densidade visual do código de barras. Um valor de pixel `2` produz uma imagem nítida que imprime bem em impressoras de etiquetas padrão.

```csharp
    // Step 3: Set the X‑dimension (module width) in pixels
    barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

Aumentar o valor torna o código de barras maior, enquanto diminuí‑lo pode causar problemas de leitura em dispositivos de baixa resolução.

### Etapa 4: configurar opções de layout específicas de macro PDF417

`Columns` determina o número de colunas de dados no código de barras PDF417.  
MacroPdf417 requer vários parâmetros adicionais. Essas configurações permitem dividir os dados em múltiplos arquivos, identificar cada segmento e verificar a integridade.

```csharp
    // Step 4: Macro‑specific layout
    barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 5;                     // Number of columns per row
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;    // Unique file identifier
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;       // Current segment number
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20; // Total number of segments
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";
```

A propriedade `Columns` influencia a largura do código de barras, enquanto os campos macro (`FileID`, `SegmentID`, `SegmentsCount`, `FileName`) permitem que sistemas downstream re‑montem os dados originais corretamente.

### Etapa 5: adicionar metadados macro adicionais

`MacroPdf417Terminator` indica se o segmento atual é o final em uma série macro.  
Aspose.BarCode permite incorporar campos macro opcionais como checksum, tamanho do arquivo, timestamp e informações de remetente/destinatário. Esses campos são úteis para trilhas de auditoria e detecção de erros.

```csharp
    // Step 5: Optional macro metadata
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234;                 // CCITT‑16 example
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400_000;              // Approximate size in bytes
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = 
        new DateTime(2019, 11, 1);                                                       // Creation date
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = 
        Pdf417MacroTerminator.Set;                                                       // Marks the last segment
```

O checksum protege contra erros de transmissão, enquanto o timestamp e os campos de remetente fornecem contexto para o processamento downstream. Definir `MacroPdf417Terminator` como `Set` sinaliza que este é o segmento final na série macro.

### Etapa 6: salvar o código de barras como imagem PNG

`Save` grava a imagem do código de barras gerado em um arquivo no formato especificado.  
Finalmente, escreva o código de barras gerado no disco. PNG preserva qualidade sem perdas, o que é ideal para leitura.

```csharp
    // Step 6: Export the barcode
    string outputPath = Path.Combine(Environment.CurrentDirectory, "ExtPDF417Meta.png");
    barcodeGenerator.Save(outputPath, BarCodeImageFormat.Png);
}
```

Quando o código termina, o arquivo `ExtPDF417Meta.png` contém um código de barras MacroPdf417 de alta resolução que codifica o texto personalizado e todos os metadados macro.

#### Saída esperada

Abrir `ExtPDF417Meta.png` mostra um código de barras orientado verticalmente com linhas e colunas claramente definidas. Ler a imagem com qualquer leitor PDF417 retorna a string original **Åspóse.Barcóde©** e os campos macro que você configurou (file ID, segment ID, checksum, etc.).

## Como gerar pdf417 sem opções de macro?

Para criar um código de barras PDF417 padrão, você só precisa definir a simbologia para `EncodeTypes.Pdf417`, fornecer o texto a ser codificado, opcionalmente ajustar parâmetros de tamanho como `XDimension` e `Columns`, e então chamar `Save`. Esta abordagem omite todas as propriedades específicas de macro, produzindo um código de barras de segmento único adequado para a maioria das aplicações.

```csharp
using (BarcodeGenerator generator = new BarcodeGenerator(
           EncodeTypes.Pdf417, "Standard PDF417 data"))
{
    generator.Parameters.Barcode.XDimension.Pixels = 3;
    generator.Parameters.Barcode.Pdf417.Columns = 6;
    generator.Save("StandardPdf417.png", BarCodeImageFormat.Png);
}
```

Este trecho demonstra **como gerar pdf417** rapidamente quando a funcionalidade de macro não é necessária. A resposta direta: crie um `BarcodeGenerator` com `EncodeTypes.Pdf417`, defina o `CodeText`, opcionalmente ajuste `XDimension` e `Columns`, então chame `Save` com o formato de imagem desejado.

## Armadilhas comuns e dicas profissionais

| Problema | Por que acontece | Solução |
|----------|------------------|---------|
| O código de barras está muito pequeno para leitura | X‑dimension definido como 1 pixel ou colunas muito altas | Use pelo menos `2` pixels para `XDimension` e mantenha colunas entre `3` e `9` para tamanhos típicos de etiqueta |
| Caracteres Unicode aparecem como � | Incompatibilidade de codificação no arquivo do projeto | Certifique-se de que o arquivo do projeto está salvo como UTF‑8 e o arquivo fonte contém o BOM correto |
| Campos macro são ignorados pelo scanner | `MacroPdf417Terminator` não definido para o último segmento | Defina `MacroPdf417Terminator = Pdf417MacroTerminator.Set` no segmento final |
| Arquivo de imagem está corrompido | Fluxo de saída não fechado corretamente | Use a instrução `using` (como mostrado) para garantir a liberação do gerador |

## Exemplo completo e executável

`BarcodeGenerator` é a classe que cria a imagem do código de barras.  
Copie o código a seguir em uma nova aplicação console e execute‑o. O programa cria o código de barras, salva‑o e imprime o caminho de saída no console.

```csharp
using System;
using System.IO;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace AsposeBarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // Initialize the generator with custom Unicode text
            using (BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
                       EncodeTypes.MacroPdf417, "Åspóse.Barcóde©"))
            {
                // Basic size
                barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;

                // Macro layout
                barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 5;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";

                // Optional macro metadata
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400_000;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = new DateTime(2019, 11, 1);
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;

                // Save as PNG
                string outputFile = Path.Combine(Environment.CurrentDirectory, "ExtPDF417Meta.png");
                barcodeGenerator.Save(outputFile, BarCodeImageFormat.Png);

                Console.WriteLine($"Barcode saved to: {outputFile}");
            }
        }
    }
}
```

Executar o programa imprime uma linha semelhante a:

```
Barcode saved to: C:\YourProject\bin\Debug\net6.0\ExtPDF417Meta.png
```

Abra o arquivo para verificar a saída visual.

## Perguntas frequentes

**Q: Posso usar este código em uma API web ASP.NET Core?**  
A: Sim. A mesma classe `BarcodeGenerator` funciona em qualquer runtime .NET, incluindo ASP.NET Core, desde que o assembly `Aspose.BarCode` esteja referenciado.

**Q: O Aspose.BarCode suporta outros formatos de imagem?**  
A: Absolutamente. Você pode salvar em PNG, JPEG, BMP, TIFF e até SVG passando o valor enum correspondente `BarCodeImageFormat` ao método `Save`.

**Q: Quão grande pode ser o dado codificado?**  
A: Um único símbolo PDF417 pode conter até 1 700 caracteres; com MacroPdf417 você pode dividir os dados em múltiplos segmentos, suportando efetivamente comprimento ilimitado.

**Q: Existe uma maneira de adicionar cor ao código de barras?**  
A: Sim. Defina as propriedades `ForeColor` e `BackColor` do `BarcodeGenerator` antes de chamar `Save` para produzir códigos de barras coloridos.

**Q: E se eu precisar incorporar o código de barras diretamente em um PDF?**  
A: Use o Aspose.PDF para inserir a imagem PNG ou SVG gerada em uma página PDF, ou use o recurso de exportação PDF integrado do Aspose.BarCode.

## Conclusão

Agora você sabe **como gerar pdf417** para a simbologia MacroPdf417, incorporar texto Unicode personalizado, configurar metadados macro e exportar o resultado como uma imagem PNG. O mesmo padrão permite gerar um código de barras PDF417 simples quando as opções de macro não são necessárias, e você pode adaptar o código para outros formatos de código de barras suportados pelo Aspose.BarCode. Experimente diferentes valores de `XDimension`, contagens de colunas e combinações de campos macro para ajustar finamente o código de barras ao seu impressor ou scanner específico.

Em seguida, explore tópicos relacionados como **criar texto personalizado de código de barras** para QR codes, adicionar filtros de cor com parâmetros `Color`, ou incorporar códigos de barras diretamente em documentos PDF usando Aspose.PDF. A flexibilidade do Aspose.BarCode permite lidar com tudo, desde códigos de barras simples de uma linha até complexos códigos de barras macro de múltiplos segmentos com apenas algumas linhas de C#.

Feliz codificação, e aproveite a confiabilidade que o Aspose.BarCode traz para suas soluções de código de barras .NET!

## O que você deve aprender a seguir?

Os tutoriais a seguir cobrem tópicos estreitamente relacionados que se baseiam nas técnicas demonstradas neste guia. Cada recurso inclui exemplos de código completos e funcionais com explicações passo a passo para ajudá‑lo a dominar recursos adicionais da API e explorar abordagens alternativas de implementação em seus próprios projetos.

- [Como criar código de barras – PDF417 compacto com Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [Como gerar código de barras DataMatrix com Aspose.BarCode para .NET](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-macro-configuration/)
- [Gerar código de barras Java - Definir texto do código usando Aspose.BarCode](/barcode/english/java/text-and-styling/setting-code-text/)

---

**Última atualização:** 2026-10-14  
**Testado com:** Aspose.BarCode 24.11 para .NET  
**Autor:** Aspose

## Tutoriais Relacionados

- [Criar código de barras Macro Pdf417 com Aspose Barcode C](/barcode/net/compact-pdf417-encoding/create-macro-pdf417-barcode-with-aspose-barcode-c/)
- [Ajustar tamanho do código de barras C Guia para gerar códigos de barras Pdf417](/barcode/net/compact-pdf417-encoding/adjust-barcode-size-c-guide-to-generate-pdf417-barcodes/)
- [Ler código de barras de imagem C Guia completo com Macro Pdf417](/barcode/net/compact-pdf417-encoding/read-barcode-from-image-c-complete-guide-with-macro-pdf417/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}