# Workflow 2 — Processamento e estruturação da Ordem de Serviço

## Visão geral

Este é o workflow central da solução.

Ele recebe a OS validada, executa o processamento do PDF, transforma o conteúdo do documento em dados estruturados e prepara o resultado para consumo operacional.

Se o workflow 1 filtra a entrada, o workflow 2 é o motor que converte documento em informação útil.

## Objetivo

O objetivo desta etapa é extrair do PDF tudo o que a operação precisa para trabalhar com a Ordem de Serviço sem depender de leitura manual.

Isso inclui identificar o número da OS, interpretar cabeçalho, segmentar itens, enriquecer o entendimento técnico do conteúdo, classificar os produtos e gerar uma estrutura final consistente em JSON.

## Papel na arquitetura

O workflow 2 ocupa a posição mais crítica da automação porque é nele que ocorre a transformação principal do processo.

Ele conecta entrada documental, extração textual, interpretação por regras, apoio de inteligência e organização final dos dados.

É também a etapa responsável por preparar o arquivo físico e os metadados que serão reutilizados no fechamento operacional do workflow 3.

## Etapas do fluxo

### 1. Extrai o número da OS

Logo no início, o workflow identifica o número da Ordem de Serviço a partir do nome do arquivo.

Esse número é importante porque passa a ser a chave de referência do processo.

Com ele, o fluxo consegue consultar histórico, nomear estruturas e manter rastreabilidade entre documento e operação.

### 2. Verifica se a OS já foi processada

Antes de iniciar o trabalho pesado de leitura e interpretação, o fluxo consulta uma base de controle para identificar se aquela OS já passou anteriormente pela automação.

Se a OS já existir, o sistema pode interromper a esteira principal e retornar uma mensagem informando que o documento já foi tratado.

Essa decisão evita duplicidade, retrabalho e inconsistência operacional.

### 3. Envia confirmação inicial de recebimento

Quando a OS ainda não foi processada, o workflow envia uma confirmação de recebimento para o canal de origem.

Essa mensagem tem papel operacional importante porque sinaliza que o documento foi aceito e que o processamento foi iniciado.

Com isso, o usuário ganha retorno imediato sem precisar acompanhar manualmente a execução técnica do fluxo.

### 4. Faz o download do PDF e extrai o texto

Depois da validação de duplicidade, o fluxo baixa o PDF e executa a extração textual do documento.

Essa etapa converte o conteúdo visual do arquivo em texto manipulável pela automação.

É o ponto de partida para todas as transformações seguintes.

### 5. Limpa e normaliza o conteúdo extraído

O texto bruto extraído de um PDF tende a vir com ruídos, cabeçalhos repetidos, quebras inadequadas e fragmentos que dificultam a interpretação.

Por isso, o workflow aplica rotinas de limpeza e normalização para reorganizar o texto em uma forma mais coerente.

Essa preparação aumenta a qualidade das etapas seguintes de extração estruturada.

### 6. Gera o cabeçalho estruturado da OS

Com o texto já tratado, o fluxo interpreta os dados gerais da Ordem de Serviço e organiza o cabeçalho em formato estruturado.

Nessa camada entram campos como número da OS, cliente, contato, telefone, CNPJ ou CPF, local de instalação, observações, tipo de OS, referência do trabalho, datas e horários, além do responsável associado ao documento.

O resultado é uma leitura muito mais útil do que o simples texto plano do PDF.

### 7. Segmenta os itens do documento

Após tratar o cabeçalho, o workflow identifica e separa os itens da OS.

Essa segmentação é necessária porque a automação não trabalha apenas com o documento inteiro, mas também com as unidades produtivas que compõem a ordem.

Cada item passa a ser tratado individualmente, o que permite extrações muito mais precisas.

### 8. Enriquece tecnicamente os itens

Os itens segmentados passam por uma etapa de apoio técnico com regras, bases auxiliares e hints de processo.

Essa camada ajuda a consolidar produto, modelo, acabamentos, dimensões, matérias-primas e maquinário utilizado com mais consistência.

Na prática, o fluxo combina leitura direta do texto com normalização técnica para tornar o JSON final mais confiável.

### 9. Extrai a estrutura detalhada dos produtos

Depois do enriquecimento, cada item é convertido em uma estrutura mais completa.

Entre os campos organizados estão descrição, produto, modelo, acabamentos, dimensões, quantidade, matérias-primas, maquinário utilizado e contexto de produção.

Esse desenho torna a saída útil não apenas para visualização humana, mas também para integração com outros sistemas.

### 10. Classifica etiquetas operacionais

Além da extração estrutural, o workflow classifica etiquetas produtivas relevantes para cada item.

Essas etiquetas ajudam a identificar rapidamente o tipo de operação envolvida, como impressão, marcenaria, pintura, sublimação, corte ou serralheria.

Esse enriquecimento agrega valor operacional porque aproxima o documento do dia a dia da produção.

### 11. Monta o JSON final consolidado

Ao final do processamento dos itens, o workflow combina cabeçalho, produtos e metadados em um payload final padronizado.

Esse JSON se torna a principal saída do workflow 2.

Ele representa a Ordem de Serviço em um formato pronto para armazenamento, distribuição e integração.

### 12. Cria a pasta do projeto e envia o PDF

Além dos dados estruturados, o fluxo também organiza o ativo físico da OS.

Ele cria a pasta correspondente no Google Drive, converte o arquivo quando necessário e faz o upload do PDF para o diretório final do projeto.

Isso garante que documento e estrutura de dados permaneçam conectados.

### 13. Encaminha o resultado para o workflow 3

Com o JSON pronto e o arquivo armazenado, o workflow envia o resultado consolidado para a etapa de distribuição operacional.

A partir daí, a automação deixa de ser apenas processamento documental e passa a alimentar os sistemas de operação.

## Por que este workflow é o coração do projeto

Este fluxo concentra a parte mais complexa e mais valiosa da solução.

Ele demonstra capacidade de combinar automação, tratamento de texto, normalização de informação, regras de negócio, enriquecimento técnico e integração entre serviços.

Mais do que “extrair texto de PDF”, ele mostra uma abordagem de engenharia aplicada a um processo operacional real.

## Valor técnico demonstrado

Este workflow destaca competências como:

- modelagem de processamento documental;
- tratamento de duplicidade com consulta prévia;
- limpeza e normalização de texto extraído de PDF;
- uso de inteligência para transformar texto em JSON;
- segmentação e enriquecimento técnico de itens;
- organização de arquivo e metadados em ambiente de produção;
- preparação de payload estruturado para integração.

## Resultado esperado

Ao final do workflow 2, a Ordem de Serviço deixa de ser um PDF isolado e passa a existir como um conjunto estruturado de informações utilizáveis.

Essa transformação é o que viabiliza todo o valor do restante da automação.

## Resultado do processamento

Entrada:
- Documento PDF
- Metadados operacionais

Saída:
- Dados estruturados
- Payload consolidado
- Arquivo preparado para distribuição

Objetivo:
Reduzir processamento manual e padronizar o consumo dos dados pelas etapas seguintes.

## Exemplo público

Exemplos fictícios da estrutura gerada por este workflow estão disponíveis em [`samples/processamento/`](../samples/processamento/).

Esses arquivos representam estados arquiteturais relevantes do processamento, como cabeçalho estruturado, itens consolidados e payload de distribuição.
