---
category: general
date: 2026-10-18
description: Crie código de barras Databar expandido em Java com Aspose.BarCode. Aprenda
  como gerar Databar, definir linhas e exportar a imagem do código de barras como
  PNG.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create databar expanded barcode
- how to generate databar
- barcode generator rows
- export barcode image
language: pt
lastmod: 2026-10-18
og_description: Crie código de barras Databar Expanded em Java. Siga este guia para
  aprender como gerar Databar, configurar linhas e exportar a imagem do código de
  barras como PNG.
og_image_alt: Screenshot of a Databar Expanded barcode saved as PNG
og_title: Criar código de barras Databar Expanded em Java – tutorial passo a passo
schemas:
- author: Aspose
  dateModified: '2026-10-18'
  description: Create databar expanded barcode in Java with Aspose.BarCode. Learn
    how to generate databar, set rows, and export barcode image as PNG.
  headline: Create databar expanded barcode in Java – full guide
  type: TechArticle
tags:
- barcode
- Java
- Aspose
title: Criar código de barras Databar Expanded em Java – guia completo
url: /pt/python-java/general/create-databar-expanded-barcode-in-java-full-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Criar código de barras Databar Expanded em Java – guia completo

Se você precisar **criar código de barras databar expanded** em Java, este tutorial mostra exatamente **como gerar imagens databar** usando a biblioteca Aspose.BarCode. Você também aprenderá como configurar **linhas do gerador de código de barras** e **exportar arquivos de imagem de código de barras** no formato PNG.

Nas seções abaixo você encontrará um programa completo e executável, explicações passo a passo de cada chamada de API e dicas para lidar com casos de borda comuns, como caracteres não suportados ou tamanhos de layout personalizados. Ao final deste guia você será capaz de produzir códigos de barras Databar Expanded de 4 colunas e 3 linhas e salvá‑los onde precisar.

## Pré-requisitos

* Java 17 ou posterior (o código compila com qualquer JDK 11+)
* Maven ou Gradle para gerenciar dependências
* Aspose.BarCode para Java – adicione a versão mais recente ao seu `pom.xml` ou `build.gradle`
* Familiaridade básica com o método `main` do Java e conceitos de programação orientada a objetos

```xml
<!-- Maven dependency -->
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-barcode</artifactId>
    <version>23.10</version>
</dependency>
```

> **Dica profissional:** A licença de avaliação gratuita funciona para desenvolvimento; substitua‑a por uma licença adquirida antes de implantar em produção.

## Criar código de barras databar expanded – configuração inicial

O primeiro passo é instanciar um `BarcodeGenerator` com o tipo `EncodeTypes.DatabarExpandedStacked` e uma carga útil de exemplo. Essa carga útil pode ser qualquer string alfanumérica que se ajuste à especificação Databar.

```java
import com.aspose.barcode.*;
import com.aspose.barcode.barcodeimageformat.*;
import com.aspose.barcode.encode.*;

public class DatabarExpandedDemo {

    public static void main(String[] args) throws Exception {
        // Step 1: Create a barcode generator for Databar Expanded Stacked with sample text
        BarcodeGenerator generator = new BarcodeGenerator(
                EncodeTypes.DatabarExpandedStacked,
                "Databar Expanded Stacked long");
```

*Por que isso importa*: `EncodeTypes.DatabarExpandedStacked` indica à biblioteca para usar a simbologia Databar Expanded Stacked, que suporta strings de dados mais longas que o Databar regular.

## Como gerar databar com colunas personalizadas

Databar Expanded permite controlar o número de colunas no layout empilhado. Definir colunas é útil quando você precisa de um código de barras compacto que ainda se ajuste à largura de dados necessária.

```java
        // Step 2: Configure a 4‑column layout for the DataBar
        generator.getParameters().getBarcode().getDataBar().setColumns(4);
```

*Explicação*: `setColumns(4)` força o gerador a dividir o código de barras em quatro seções verticais. A biblioteca ajusta automaticamente a largura do módulo para manter o tamanho geral razoável.

## Exportar imagem de código de barras como PNG – versão de 4 colunas

Depois que o layout é definido, você pode exportar o código de barras para um arquivo. PNG é o formato sem perdas recomendado para a maioria dos cenários de UI.

```java
        // Step 3: Save the 4‑column barcode image
        generator.save("output/DatabarExpandedCols4.png", BarCodeImageFormat.Png);
```

O método `save` grava a imagem no diretório especificado. Se o diretório não existir, o Java o criará automaticamente.

## Configurar linhas do gerador de código de barras

Além das colunas, a simbologia Databar Expanded Stacked suporta um layout baseado em linhas. Alternar de colunas para linhas pode melhorar a legibilidade em impressões de alta resolução.

```java
        // Step 4: Create a new generator for the same data (demonstrates a different layout)
        BarcodeGenerator rowGenerator = new BarcodeGenerator(
                EncodeTypes.DatabarExpandedStacked,
                "Databar Expanded Stacked long");

        // Step 5: Configure a 3‑row layout for the DataBar
        rowGenerator.getParameters().getBarcode().getDataBar().setRows(3);
```

*Por que usar linhas?* Um layout de 3 linhas distribui os dados verticalmente, o que pode ser vantajoso para etiquetas estreitas onde o espaço horizontal é limitado.

## Exportar imagem de código de barras como PNG – versão de 3 linhas

Salvar o segundo layout segue o mesmo padrão de antes. Manter os nomes dos arquivos distintos ajuda a comparar as diferenças visuais.

```java
        // Step 6: Save the 3‑row barcode image
        rowGenerator.save("output/DatabarExpandedRows3.png", BarCodeImageFormat.Png);
    }
}
```

### Saída esperada

Executar o programa produz dois arquivos PNG:

| Nome do arquivo               | Descrição do layout               |
|------------------------------|-----------------------------------|
| `DatabarExpandedCols4.png`   | código de barras empilhado de 4 colunas |
| `DatabarExpandedRows3.png`   | código de barras empilhado de 3 linhas |

Ambas as imagens exibem a mesma string codificada, mas a densidade visual difere de acordo com as configurações de coluna/linha.

## Armadilhas comuns e como evitá‑las

| Problema                               | Causa                                   | Solução |
|----------------------------------------|------------------------------------------|---------|
| Código de barras aparece borrado       | Salvando com DPI baixo                  | Use `generator.getParameters().setResolution(300)` antes de `save`. |
| Texto é truncado                       | Carga útil excede a capacidade do Databar | Reduza a carga útil ou troque para `EncodeTypes.DatabarExpanded` (não empilhado). |
| `NullPointerException` ao chamar `setRows` | Usando uma versão do Aspose.BarCode anterior à 20.12 | Atualize para a versão mais recente da biblioteca. |

## Variações avançadas (opcional)

* **Alterar cores de primeiro plano/fundo** – chame `generator.getParameters().getBarcode().setForeColor(Color.BLUE)` e `setBackColor(Color.WHITE)`.
* **Gerar SVG em vez de PNG** – substitua `BarCodeImageFormat.Png` por `BarCodeImageFormat.Svg`.
* **Incorporar o código de barras em um PDF** – use Aspose.PDF para criar um documento e adicionar o PNG como imagem.

## Conclusão

Agora você sabe como **criar código de barras databar expanded** em Java, **como gerar databar** com configurações de coluna e linha, e como **exportar arquivos de imagem de código de barras** no formato PNG. O código‑fonte completo está pronto para copiar, colar e executar em qualquer projeto Java.

Sinta‑se à vontade para experimentar outros layouts, cores ou formatos de saída. Se você achou este guia útil, considere explorar a documentação do Aspose.BarCode para tópicos como *micro‑PDF417*, *correção de erro de QR code* e *leitura de código de barras*.

Boa codificação!

## O que você deve aprender a seguir?

Os tutoriais a seguir cobrem tópicos estreitamente relacionados que se baseiam nas técnicas demonstradas neste guia. Cada recurso inclui exemplos de código completos e funcionais com explicações passo a passo para ajudá‑lo a dominar recursos adicionais da API e explorar abordagens de implementação alternativas em seus próprios projetos.

- [Como gerar código de barras java: Criar uma Imagem de Código de Barras Exata](/barcode/english/java/barcode-basics/creating-image-exact-barcode/)
- [Guia de código de barras databar expanded stacked – como gerar e dimensionar em C#](/barcode/english/python-java/general/databar-expanded-stacked-barcode-guide-how-to-generate-and-s/)
- [Como criar código de barras Databar omnidirecional em C#](/barcode/english/python-java/general/how-to-create-omnidirectional-databar-barcode-in-c/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}