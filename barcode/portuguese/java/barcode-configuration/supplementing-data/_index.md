---
date: 2025-12-17
description: Aprenda a gerar códigos de barras em Java usando Aspose.BarCode, abordando
  a geração dinâmica de códigos de barras, a criação de códigos de barras EAN‑13 e
  a gravação de imagens de códigos de barras com dados suplementares.
linktitle: Supplementing Data
second_title: Aspose.BarCode Java API
title: Como gerar código de barras com dados suplementares em Java
url: /pt/java/barcode-configuration/supplementing-data/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Como Gerar Código de Barras com Dados Suplementares em Java

## Introdução

No ecossistema digital acelerado de hoje, **como gerar código de barras** de forma eficiente é uma questão que muitos desenvolvedores Java enfrentam. Aspose.BarCode for Java oferece uma API poderosa e fácil de usar que suporta **geração dinâmica de códigos de barras**, incluindo a criação de **códigos de barras EAN‑13** com dados suplementares. Seja você quem esteja construindo sistemas de inventário, aplicações POS de varejo ou rastreadores logísticos, este tutorial o guiará por um **exemplo de gerador de código de barras java** que salva a imagem do código de barras no disco e permite personalizar a parte suplementar.

## Respostas Rápidas
- **Qual biblioteca é a melhor para gerar códigos de barras em Java?** Aspose.BarCode for Java.  
- **Qual simbologia cria um código de barras numérico de 13 dígitos?** EAN‑13.  
- **Posso adicionar dados suplementares a um código de barras EAN‑13?** Sim, usando a API `Supplement`.  
- **Como salvo o código de barras gerado como imagem?** Chame `generator.save("caminho/arquivo.jpg")`.  
- **É necessária licença para uso em produção?** Sim, é necessária uma licença comercial; uma versão de avaliação gratuita está disponível.

## O que é geração de código de barras em Java?

Geração de código de barras significa converter dados—números, letras ou uma mistura—em um padrão visual que scanners podem ler. Com Aspose.BarCode você pode produzir **imagens de código de barras em alta resolução** sob demanda, tornando-a ideal para cenários de **geração dinâmica de código de barras** como bilhetagem em tempo real ou cumprimento de pedidos.

## Por que usar Aspose.BarCode para geração dinâmica de código de barras?

- **Controle total** sobre simbologia, tamanho, cores e dados suplementares.  
- **Sem dependências externas** – puro Java, funciona em qualquer plataforma.  
- **Suporte interno** para dezenas de tipos de código de barras, incluindo **criar código de barras ean13**.  
- **API simples** que permite **salvar imagem do código de barras** com uma única linha de código.

## Pré‑requisitos

Antes de começar, certifique‑se de que você tem:

- **Java Development Kit (JDK)** – qualquer versão recente (8 ou superior).  
- **IDE** – IntelliJ IDEA, Eclipse ou seu editor favorito.  
- **Aspose.BarCode for Java** – faça o download da biblioteca no site oficial **[aqui](https://releases.aspose.com/barcode/java/)** e adicione o JAR ao classpath do seu projeto.

## Importar Pacotes

Depois que a biblioteca for referenciada, importe a classe principal que controla a criação do código de barras.

```java
// Import Aspose.BarCode for Java
import com.aspose.barcode.generation.BarcodeGenerator;
```

## Guia Passo a Passo

### Passo 1: Defina o Diretório do Seu Documento

Defina a pasta onde a imagem gerada será armazenada.

```java
String dataDir = "Your Document Directory";
```

### Passo 2: Crie a Instância do Gerador de Código de Barras

Instancie `BarcodeGenerator` com o **codetext** e a **simbologia** desejados. Aqui nós **criamos código de barras ean13** usando a string numérica `"123456789123"`.

```java
BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.EAN_13, "123456789123");
```

### Passo 3: Defina os Dados Suplementares

Adicione uma string suplementar de 5 dígitos. Isso é útil para revistas, periódicos ou qualquer caso em que informações extras seguem o código de barras principal.

```java
generator.getParameters().getBarcode().getSupplement().setSupplementData("12345");
```

### Passo 4: Defina o Espaço do Suplemento

Ajuste o espaço entre o código de barras principal e seu suplemento. O valor é expresso em pontos.

```java
generator.getParameters().getBarcode().getSupplement().getSupplementSpace().setPoint(2.0f);
```

### Passo 5: Salve a Imagem do Código de Barras

Por fim, grave a imagem no disco. O formato é inferido a partir da extensão do arquivo (JPEG neste exemplo).

```java
generator.save(dataDir + "supplementData.jpg");
```

> **Dica profissional:** Você pode mudar a extensão do arquivo para `.png` ou `.bmp` para obter um formato de imagem diferente sem código extra.

## Problemas Comuns e Soluções

| Problema | Causa | Solução |
|----------|-------|----------|
| **Imagem não salva** | `dataDir` aponta para uma pasta inexistente | Garanta que o diretório exista ou crie‑o programaticamente (`new File(dataDir).mkdirs();`). |
| **Comprimento do suplemento inválido** | Suplementos EAN‑13 devem ter 2 ou 5 dígitos | Forneça exatamente 2 ou 5 caracteres; caso contrário, uma exceção será lançada. |
| **Caracteres não suportados** | Caracteres não numéricos no codetext EAN‑13 | Use apenas dígitos 0‑9 para EAN‑13; troque para outra simbologia se precisar de alfanuméricos. |

## Perguntas Frequentes

### O Aspose.BarCode é compatível com todas as versões do Java?
Aspose.BarCode for Java foi projetado para ser compatível com uma ampla gama de versões do Java. Consulte a **[documentação](https://reference.aspose.com/barcode/java/)** para detalhes específicos.

### Posso personalizar a aparência dos códigos de barras gerados?
Sim, Aspose.BarCode fornece vários parâmetros e configurações para personalizar a aparência dos códigos de barras. Explore a documentação para informações detalhadas.

### Existe uma versão de avaliação disponível?
Sim, você pode acessar uma versão de avaliação gratuita **[aqui](https://releases.aspose.com/)**.

### Como posso obter suporte para o Aspose.BarCode?
Visite o **[fórum Aspose.BarCode](https://forum.aspose.com/c/barcode/13)** para obter assistência da comunidade e de especialistas.

### Onde posso comprar o Aspose.BarCode for Java?
Você pode comprar o Aspose.BarCode for Java **[aqui](https://purchase.aspose.com/buy)**.

---

**Última atualização:** 2025-12-17  
**Testado com:** Aspose.BarCode for Java 24.11  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}