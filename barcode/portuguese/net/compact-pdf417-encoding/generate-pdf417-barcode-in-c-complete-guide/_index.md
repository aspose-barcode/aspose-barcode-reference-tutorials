---
category: general
date: 2026-09-18
description: Aprenda a criar imagem de código de barras PDF417 em C# rapidamente e
  definir colunas para um código de barras compacto.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create pdf417 barcode image
- compact pdf417 barcode
- Aspose.BarCode PDF417
- C# barcode generation
- set barcode columns
lastmod: 2026-09-18
og_description: Aprenda a criar imagem de código de barras PDF417 em C# rapidamente
  e definir colunas para um código de barras compacto. Aspose.BarCode facilita.
og_image_alt: Developer guide showing a compact PDF417 barcode PNG generated with
  Aspose.BarCode
og_title: Criar imagem de código de barras PDF417 – guia passo a passo em C#
schemas:
- author: Aspose
  dateModified: '2026-09-18'
  description: Learn how to create PDF417 barcode image in C# quickly and set columns
    for a compact barcode.
  headline: Create PDF417 barcode image – complete guide
  type: TechArticle
tags:
- barcode
- C#
- PDF417
- Aspose.BarCode
title: Como criar imagem de código de barras PDF417 em C# – guia completo
url: /pt/net/compact-pdf417-encoding/generate-pdf417-barcode-in-c-complete-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Como criar imagem de código de barras PDF417 em C# – guia completo

Se você precisa **criar imagem de código de barras PDF417** em uma aplicação .NET, está no lugar certo. Seja imprimindo etiquetas de cartão de embarque, codificando dados de inventário ou construindo um sistema de bilhetagem móvel, o PDF417 oferece códigos de barras bidimensionais de alta capacidade. Este guia mostra como gerar a imagem com Aspose.BarCode e como definir colunas para que o código de barras permaneça o mais compacto possível.

## Respostas rápidas
- **Qual biblioteca cria códigos de barras PDF417?** Aspose.BarCode for .NET.
- **Quantas linhas de código são necessárias?** Cerca de 10 linhas em um aplicativo de console.
- **Posso controlar a largura do código de barras?** Sim, definindo a propriedade `Columns`.
- **Qual formato de imagem é recomendado?** PNG para qualidade sem perdas.
- **O .NET 6 é suportado?** Sim – a biblioteca funciona com .NET 6, .NET 7 e versões posteriores.

## O que é imagem de código de barras PDF417?
A imagem de código de barras PDF417 é uma matriz bidimensional que armazena até 1 700 caracteres por linha, usando linhas e colunas para compactar os dados densamente. Aspose.BarCode renderiza essa matriz em formatos de imagem padrão como PNG, JPEG ou BMP. Ela pode ser salva em vários formatos e é adequada para impressão em etiquetas, ingressos ou telas móveis.

## Por que definir colunas para uma imagem de código de barras PDF417 compacta?
Definir colunas permite reduzir a largura do código de barras, o que é essencial para etiquetas estreitas ou elementos de interface com espaço limitado. Aspose.BarCode suporta de 1 a 30 colunas, e escolher um número menor reduz a largura total da imagem em até 40 % enquanto preserva a integridade dos dados. Esse ajuste ajuda a encaixar códigos de barras em etiquetas pequenas sem sacrificar a legibilidade.

## Como criar imagem de código de barras PDF417 em C#?
Carregue a biblioteca `Aspose.BarCode`, configure um `BarcodeGenerator` com `EncodeTypes.Pdf417`, defina `Columns` e `Truncate`, e então salve o resultado como PNG. Todo o processo requer duas chamadas de método e produz um arquivo de imagem pronto para uso. Você também pode personalizar dimensões, cores e adicionar texto legível para atender às necessidades da sua aplicação.

### Pré-requisitos
- .NET 6+ SDK (ou mais recente)
- Visual Studio 2022 ou qualquer editor C#
- Pacote NuGet `Aspose.BarCode`

### Implementação passo a passo

## Etapa 1: Instalar o pacote NuGet Aspose.BarCode
`Aspose.BarCode` é uma biblioteca .NET para gerar e ler várias simbologias de códigos de barras.

```bash
dotnet add package Aspose.BarCode
```

Essa única linha traz todos os tipos que você precisará, incluindo `BarcodeGenerator`, `EncodeTypes` e o enum `BarCodeImageFormat`.

> **Dica profissional:** Se você direcionar o .NET Framework em vez do .NET 6, use o comando clássico `Install-Package Aspose.BarCode` no PowerShell dentro do Console do Gerenciador de Pacotes.

## Etapa 2: Criar um aplicativo de console mínimo
`BarcodeGenerator` cria imagens de códigos de barras com base nas configurações especificadas. `EncodeTypes` enumera as simbologias de códigos de barras suportadas. `BarCodeImageFormat` enumera os formatos de imagem.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace Pdf417Demo
{
    class Program
    {
        static void Main(string[] args)
        {
            // 1️⃣ Define the data you want to encode.
            string data = "SampleBarcode©";

            // 2️⃣ Instantiate the generator for PDF417.
            BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, data);

            // 3️⃣ Set the size of a single barcode module (pixel dimension).
            //    This is the “X‑Dimension” – smaller values yield a finer image.
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // 4️⃣ **How to set columns** – configure the matrix layout.
            //    Fewer columns = taller barcode; more columns = wider barcode.
            generator.Parameters.Barcode.Pdf417.Columns = 3;   // 👈 primary levers
            generator.Parameters.Barcode.Pdf417.Truncate = true; // compact mode

            // 5️⃣ Choose where the PNG will be saved.
            string outputPath = @"./CompactPdf417.png";

            // 6️⃣ Save the generated barcode as a PNG image.
            generator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"✅ Barcode saved to {outputPath}");
        }
    }
}
```

**Por que isso importa:**  
- `EncodeTypes.Pdf417` indica à biblioteca que queremos um código de barras PDF417, não QR ou Code128.  
- `XDimension.Pixels` controla a resolução de cada pequeno módulo preto ou branco.  
- O bloco **como definir colunas** influencia diretamente a forma da **imagem de código de barras PDF417**.  
- `Truncate = true` elimina quaisquer linhas vazias desnecessárias, proporcionando o visual “compacto” que muitos leitores apreciam.

## Etapa 3: Aprofundar – entendendo colunas e truncamento

### Como definir colunas
PDF417 arranja os dados em uma matriz de *linhas* × *colunas*. A biblioteca tem como padrão 5 colunas, o que funciona na maioria dos casos. Contudo, você pode precisar de um código de barras mais estreito para caber em uma etiqueta ou de um mais largo para melhorar a confiabilidade da leitura. A propriedade:

```csharp
generator.Parameters.Barcode.Pdf417.Columns = <desiredColumnCount>;
```

aceita valores de **1** até **30** (o limite exato depende do tamanho dos dados). Aqui está um rápido cheat sheet:

| Colunas | Largura aprox. (mm) | Quando usar |
|---------|-------------------|-------------|
| 1‑3     | Muito estreita    | Etiqueta pequena, espaço limitado |
| 4‑6     | Padrão            | A maioria dos recibos, ingressos |
| 7‑10    | Mais larga        | Dados de alta densidade, melhor legibilidade |

### Truncate (modo compacto)
Definir `Truncate = true` indica ao codificador que corte quaisquer linhas em branco desnecessárias na parte inferior. O resultado é uma **imagem de código de barras PDF417 compacta** que ocupa a menor área possível enquanto ainda contém todos os dados. Se você receber erros como “código de barras muito grande para a etiqueta”, altere essa flag.

## Etapa 4: Executar o aplicativo e verificar a saída
Compile e execute:

```bash
dotnet run
```

Você deverá ver a mensagem no console confirmando o local de salvamento. Navegue até a pasta e abra `CompactPdf417.png`. A imagem terá a seguinte aparência:

![Imagem de código de barras PDF417 gerada](./CompactPdf417.png "Imagem de código de barras PDF417 gerada – PNG compacto criado por Aspose.BarCode")

[Imagem de código de barras PDF417 gerada](./CompactPdf417.png "Imagem de código de barras PDF417 gerada – PNG compacto criado por Aspose.BarCode")

*Texto alternativo da imagem:* **Imagem de código de barras PDF417 gerada** – um arquivo PNG compacto produzido pelo código do tutorial.

Se o seu leitor conseguir lê‑la, parabéns—você **gerou o código de barras PDF417** com sucesso e dominou **como definir colunas** para uma **imagem de código de barras PDF417** organizada.

## Etapa 5: Armadilhas comuns e como corrigi‑las

| Sintoma | Causa provável | Correção rápida |
|---------|----------------|-----------------|
| O código de barras aparece borrado | `XDimension.Pixels` muito baixo (ex.: 1) | Aumente para 2‑3 pixels para uma imagem mais nítida. |
| O leitor não consegue ler | Muitas colunas para os dados fornecidos | Reduza `Columns` ou habilite `Truncate`. |
| Formato de arquivo errado | Salvo com `BarCodeImageFormat.Jpeg` por engano | Use `BarCodeImageFormat.Png` para resultados sem perdas. |
| Exceção `ArgumentOutOfRangeException` | Contagem de colunas excede o intervalo permitido | Mantenha colunas entre 1‑30 e assegure que os dados caibam. |

## Etapa 6: Avançando – personalizando cores e adicionando texto

Se você quiser que o código de barras combine com a paleta da marca, pode ajustar as cores de primeiro plano e fundo:

```csharp
generator.Parameters.Barcode.BarcodeColor = System.Drawing.Color.DarkBlue;
generator.Parameters.Barcode.BackColor = System.Drawing.Color.White;
```

Ou sobrepor texto legível sob o código de barras:

```csharp
generator.Parameters.Barcode.CodeText = data; // shows the raw string
generator.Parameters.Barcode.CodeLocation = CodeLocation.Below;
```

Essas adições são opcionais, mas ilustram quão flexível o fluxo de trabalho de **gerar código de barras PDF417** pode ser.

## Conclusão
Percorremos um exemplo completo, de ponta a ponta, que **gera código de barras PDF417** usando Aspose.BarCode, explicamos **como definir colunas** para controlar as dimensões do código de barras e salvamos o resultado como uma nítida **imagem de código de barras PDF417** em formato PNG. O código é autônomo, funciona com .NET 6+ e pode ser inserido em qualquer projeto existente com mínima complicação.

O que vem a seguir? Experimente codificar cargas maiores (por exemplo, strings JSON), teste diferentes formatos de imagem ou integre o gerador em uma API web que forneça códigos de barras sob demanda. O céu é o limite, e agora você tem uma base sólida para construir.

Feliz codificação, e que seus códigos de barras sempre sejam lidos na primeira tentativa!

## O que você deve aprender a seguir?
Os tutoriais a seguir abordam tópicos estreitamente relacionados que se baseiam nas técnicas demonstradas neste guia. Cada recurso inclui exemplos de código completos e funcionais com explicações passo a passo para ajudá‑lo a dominar recursos adicionais da API e explorar abordagens alternativas de implementação em seus próprios projetos.

- [Como criar código de barras – PDF417 compacto com Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [Como gerar imagem de código de barras em Java com Aspose.BarCode](/barcode/english/java/barcode-rendering-techniques/)
- [Gerar código de barras Java – Definir resolução de imagem com Aspose.BarCode](/barcode/english/java/advanced-settings-and-optimization/setting-image-resolution-barcode/)

## Perguntas frequentes

**Q: Posso usar o PNG gerado em uma página web sem conversão adicional?**  
A: Sim, PNG é suportado nativamente por todos os navegadores modernos, portanto você pode incorporar o arquivo diretamente com a tag `<img>`.

**Q: Quantos caracteres um código de barras PDF417 pode armazenar?**  
A: Até 1 700 caracteres por linha e até 30 linhas, oferecendo um máximo teórico de cerca de 51 000 caracteres, embora limites práticos dependam das capacidades do leitor.

**Q: O Aspose.BarCode requer licença para desenvolvimento?**  
A: Uma licença de avaliação gratuita está disponível para testes; uma licença comercial é necessária para implantações em produção.

**Q: É possível gerar códigos de barras PDF417 em um serviço em segundo plano?**  
A: Absolutamente. A biblioteca é segura para uso em múltiplas threads em operações somente leitura, portanto você pode gerar códigos de barras em ASP.NET Core ou serviços Windows sem interação de UI.

**Q: Quais formatos de imagem além de PNG são suportados?**  
A: BMP, JPEG, GIF, TIFF e SVG são todos suportados via a enumeração `BarCodeImageFormat`.

---

**Última atualização:** 2026-09-18  
**Testado com:** Aspose.BarCode 24.11 for .NET  
**Autor:** Aspose  

```bash
dotnet add package Aspose.BarCode
```

## Tutoriais Relacionados

- [Criar código de barras Pdf417 com Aspose Guia Completa](/barcode/net/compact-pdf417-encoding/create-pdf417-barcode-with-aspose-complete-guide/)
- [Como gerar imagem de código de barras Pdf417 em C com Aspose](/barcode/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-image-in-c-with-aspose/)
- [Criar código de barras Pdf417 em C Guia passo a passo](/barcode/net/compact-pdf417-encoding/create-pdf417-barcode-in-c-step-by-step-guide/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}