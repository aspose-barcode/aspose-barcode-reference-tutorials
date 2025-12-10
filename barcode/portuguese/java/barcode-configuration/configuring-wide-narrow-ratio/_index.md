---
date: 2025-12-10
description: Aprenda a gerar códigos de barras com uma proporção personalizada de
  barra larga‑estreita em Java usando Aspose.BarCode e a gerar a imagem do código
  de barras de forma eficiente. Siga nosso guia passo a passo.
linktitle: Configuring Wide-Narrow Ratio
second_title: Aspose.BarCode Java API
title: Como gerar código de barras com proporção larga‑estreita em Java
url: /pt/java/barcode-configuration/configuring-wide-narrow-ratio/
weight: 17
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Como Gerar Código de Barras com Proporção Larga‑Estreita em Java

## Introdução

Se você precisa **gerar código de barras** com proporções visuais precisas, ajustar a proporção larga‑estreita é fundamental. Neste tutorial, vamos percorrer um processo **passo a passo de criação de código de barras** usando Aspose.BarCode para Java, mostrando como configurar a proporção, gerar a imagem do código de barras e **salvar o código de barras png** no disco. Seja para rótulos de inventário, etiquetas de envio ou qualquer aplicação que exija um código de barras CODE_128 com estilo personalizado, você encontrará tudo o que precisa aqui.

## Respostas Rápidas
- **O que é a proporção larga‑estreita?** Ela controla a largura relativa das barras largas em relação às barras estreitas em um código de barras.  
- **Qual simbologia suporta ajuste de proporção?** A maioria das simbologias 1‑D, incluindo CODE_128, permite definir uma proporção personalizada.  
- **Preciso de licença?** Um teste gratuito está disponível, mas uma licença comercial é necessária para uso em produção.  
- **Posso gerar uma imagem de código de barras em formato PNG?** Sim—use `generator.save(...)` para gerar a imagem do código de barras como PNG.  
- **O código é compatível com Java 8+?** Absolutamente; Aspose.BarCode funciona com todas as versões modernas do Java.

## Pré‑requisitos

Antes de mergulharmos no código, certifique‑se de que você tem o seguinte:

- Java Development Kit (JDK) instalado na sua máquina.  
- Biblioteca Aspose.BarCode para Java. Baixe-a a partir do [link de download](https://releases.aspose.com/barcode/java/).

## Importar Pacotes

Para começar, importe a classe essencial do Aspose.BarCode para o seu projeto.

```java
// Import Aspose.BarCode library
import com.aspose.barcode.generation.BarcodeGenerator;
```

## O que é a proporção larga‑estreita e por que ajustá‑la?

A proporção larga‑estreita determina quão espessas as barras “largas” aparecem em comparação com as “estreitas”. Ajustar essa proporção pode melhorar a legibilidade pelos scanners, atender a padrões específicos de impressão ou simplesmente combinar com o estilo visual de uma marca.

## Como gerar código de barras com proporção larga‑estreita em Java

A seguir, um guia **passo a passo de código de barras** que orienta cada etapa do processo.

### Etapa 1: Definir Diretório do Documento

```java
// The path to the resource directory.
String dataDir = "Your Document Directory";
```

Certifique‑se de que o diretório exista e que você tenha permissões de escrita; é aqui que o arquivo **salvar código de barras png** será colocado.

### Etapa 2: Instanciar Objeto Barcode

```java
// Instantiate barcode object
// Create an instance of BarcodeGenerator, specify codetext and symbology in the constructor
BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.CODE_128, "12345678");
```

Aqui nós **criamos um código de barras code_128** passando `EncodeTypes.CODE_128` para o construtor.

### Etapa 3: Definir Proporção Larga‑Estreita

```java
// Set the wide to narrow ratio for the barcode
generator.getParameters().getBarcode().setWideNarrowRatio(3.0f);
```

O método `setWideNarrowRatio` permite ajustar finamente o espaçamento visual. Um valor de `3.0f` significa que a barra larga tem três vezes a largura de uma barra estreita.

### Etapa 4: Salvar Imagem no Disco

```java
// Save the image to disk in PNG format
generator.save(dataDir + "wideNarrowRatio.png");
```

Chamar `save` **gerará a imagem do código de barras** e a armazenará como um arquivo PNG, concluindo a etapa **salvar código de barras png**.

## Problemas Comuns e Soluções

| Problema | Motivo | Solução |
|----------|--------|---------|
| Código de barras parece distorcido | Proporção muito alta/baixa para a impressora | Ajuste o valor passado para `setWideNarrowRatio` (ex.: 2.0‑2.5). |
| Arquivo não foi criado | Caminho `dataDir` inválido ou permissões insuficientes | Verifique o caminho do diretório e assegure que a aplicação tenha acesso de escrita. |
| Scanner não consegue ler o código | Proporção fora da faixa recomendada para a simbologia | Use proporções padrão (2.0‑3.0) ou teste com o scanner alvo. |

## Perguntas Frequentes

**P: Posso usar Aspose.BarCode com outros frameworks Java?**  
R: Sim, Aspose.BarCode foi projetado para funcionar perfeitamente com Spring, Java EE, Android e outros ambientes Java.

**P: Como gerar códigos de barras com diferentes simbologias?**  
R: Basta alterar o tipo de simbologia no construtor `BarcodeGenerator`, por exemplo `EncodeTypes.QR` para códigos QR.

**P: Existe uma versão de avaliação disponível para Aspose.BarCode?**  
R: Sim, você pode acessar a versão de teste gratuita [aqui](https://releases.aspose.com/).

**P: Onde encontrar documentação detalhada do Aspose.BarCode?**  
R: Consulte a documentação [aqui](https://reference.aspose.com/barcode/java/).

**P: Como obter suporte para Aspose.BarCode?**  
R: Visite o fórum do Aspose.BarCode [aqui](https://forum.aspose.com/c/barcode/13) para suporte e discussões da comunidade.

---

**Última atualização:** 2025-12-10  
**Testado com:** Aspose.BarCode para Java 24.11 (mais recente na data de escrita)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}