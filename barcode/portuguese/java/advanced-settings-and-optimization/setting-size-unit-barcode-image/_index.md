---
date: 2025-12-08
description: Aprenda como criar código de barras Code128 em Java e gerar imagem de
  código de barras em Java usando Aspose.BarCode. Defina unidades de tamanho precisas
  para imagens de códigos de barras com código simples e reutilizável.
language: pt
linktitle: Setting Size Unit for Barcode Image
second_title: Aspose.BarCode Java API
title: Criar código de barras Code128 em Java com Aspose.BarCode
url: /java/advanced-settings-and-optimization/setting-size-unit-barcode-image/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Criar código de barras code128 em Java e definir unidade de tamanho com Aspose.BarCode

## Introdução

Neste guia passo a passo você **criará código de barras code128 java** que gera uma imagem de código de barras e permite controlar a unidade de tamanho da saída. Seja você quem esteja construindo um sistema de inventário, um gerador de etiquetas de envio ou qualquer aplicação Java que precise de um código de barras confiável, o Aspose.BarCode para Java torna o processo simples e altamente personalizável.

## Respostas rápidas
- **Qual biblioteca eu preciso?** Aspose.BarCode para Java.  
- **Qual tipo de código de barras é abordado?** CODE_128 (criar code128 barcode java).  
- **Como defino a unidade de tamanho?** Use a propriedade `BarHeight` com `.setPoint()`.  
- **Posso gerar imagem de código de barras java em outros formatos?** Sim – PNG, JPEG, BMP, etc.  
- **Quais são os pré‑requisitos?** JDK instalado, biblioteca Aspose.BarCode e uma IDE Java.

## O que é **criar code128 barcode java**?

Criar um código de barras CODE_128 em Java significa instanciar a classe `BarcodeGenerator` com o enum `EncodeTypes.CODE_128` e fornecer a string de dados que você deseja codificar. Essa simbologia é amplamente usada em logística porque suporta todo o conjunto de caracteres ASCII e oferece alta densidade de dados.

## Por que usar Aspose.BarCode para **gerar imagem de código de barras java**?

- **Controle total sobre as dimensões** – você pode definir a altura das barras, o tamanho do módulo e a resolução da imagem.  
- **Sem dependências externas** – puro Java, funciona em qualquer plataforma que suporte o JDK.  
- **Personalização rica** – cores, fontes, margens e até códigos QR são suportados.  
- **Alto desempenho** – gera imagens em milissegundos, adequado para processamento em lote.

## Pré‑requisitos

Antes de começar, certifique‑se de que você tem:

1. **Java Development Kit (JDK)** – versão 8 ou superior instalada em sua máquina.  
2. **Aspose.BarCode para Java** – baixe o JAR mais recente no site da Aspose (versão de avaliação ou licenciada).  
3. **Uma IDE Java** – como IntelliJ IDEA, Eclipse ou VS Code com extensões Java.  

## Importar namespaces

Adicione as importações necessárias no topo da sua classe Java para acessar a API do Aspose.BarCode:

```java
import java.io.IOException;

import com.aspose.barcode.*;

import com.aspose.barcode.generation.BarcodeGenerator;
```

## Como **gerar imagem de código de barras java** com Aspose.BarCode?

A seguir está o fluxo completo. Cada etapa é explicada em linguagem simples, e os blocos de código originais são mantidos exatamente como estavam.

### Etapa 1: Definir o diretório de recursos

```java
// The path to the resource directory.
String dataDir = "Your Document Directory";
```

Substitua `"Your Document Directory"` pelo caminho absoluto onde você deseja salvar a imagem do código de barras.

### Etapa 2: Instanciar o objeto Barcode

```java
// Instantiate barcode object, Set the symbology type to code128 and Set the
// Code text for the barcode
BarcodeGenerator bb = new BarcodeGenerator(EncodeTypes.CODE_128, "1234567");
```

Aqui nós **criamos code128 barcode java** passando `EncodeTypes.CODE_128` e a string de dados `"1234567"`.

### Etapa 3: Definir a altura da barra (unidade de tamanho)

```java
// Set the bar height to 3 points
bb.getParameters().getBarcode().getBarHeight().setPoint(3.0f);
```

O método `setPoint()` define a altura em pontos (1 ponto = 1/72 polegada). Ajuste esse valor para atender aos requisitos do seu layout.

### Etapa 4: Salvar a imagem

```java
// Save the image
bb.save(dataDir + "barcode-size-unit.jpg");
```

A chamada `save()` grava o código de barras gerado na pasta especificada. O formato da imagem é inferido a partir da extensão do arquivo (JPEG neste caso).

## Problemas comuns e soluções

| Problema | Motivo | Solução |
|----------|--------|---------|
| **Imagem não criada** | O caminho `dataDir` está incorreto ou faltam permissões de gravação. | Verifique se a pasta existe e se sua aplicação tem acesso de escrita. |
| **Código de barras aparece muito pequeno** | A altura da barra em pontos está muito baixa para o DPI escolhido. | Aumente o valor passado para `setPoint()` ou ajuste o DPI da imagem via `bb.getParameters().getImage().setResolution()`. |
| **Caracteres não suportados** | CODE_128 suporta apenas ASCII; você enviou Unicode. | Use outra simbologia (por exemplo, QR_CODE) para dados não‑ASCII. |

## Perguntas frequentes

**P: O Aspose.BarCode para Java é adequado tanto para geração quanto para reconhecimento de códigos de barras?**  
R: Sim, a biblioteca suporta geração e reconhecimento de uma ampla variedade de simbologias.

**P: Posso personalizar a aparência das imagens de código de barras geradas?**  
R: Absolutamente. Você pode mudar cores, adicionar legendas, modificar margens e até incorporar logotipos usando a extensa API `Parameters`.

**P: Como obtenho uma licença temporária para o Aspose.BarCode para Java?**  
R: Visite [aqui](https://purchase.aspose.com/temporary-license/) para solicitar uma licença temporária para avaliação.

**P: Onde encontro suporte para o Aspose.BarCode para Java?**  
R: O fórum da comunidade Aspose.BarCode é o melhor lugar para ajuda. Consulte o [forum](https://forum.aspose.com/c/barcode/13) para respostas e para fazer novas perguntas.

**P: Quais são as simbologias de código de barras suportadas no Aspose.BarCode para Java?**  
R: A biblioteca suporta dezenas de simbologias, incluindo CODE_128, QR_CODE, UPC_A, DataMatrix, PDF417 e muitas outras.

---

**Última atualização:** 2025-12-08  
**Testado com:** Aspose.BarCode para Java 24.12 (mais recente na data da escrita)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}