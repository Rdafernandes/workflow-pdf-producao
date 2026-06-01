# Workflow 3 — Distribuição operacional e persistência dos dados

## Visão geral

O workflow 3 recebe a saída estruturada do processamento e transforma esse resultado em ações concretas para a operação.

Ele fecha o ciclo da automação, conectando os dados extraídos do PDF com comunicação, controle operacional, acompanhamento visual e persistência em banco.

Se o workflow 2 organiza a informação, o workflow 3 coloca essa informação para trabalhar.

## Objetivo

O objetivo desta etapa é fazer com que a Ordem de Serviço processada deixe de ser apenas um JSON técnico e passe a alimentar os canais realmente usados pela equipe.

Isso inclui comunicação por mensagem, atualização de planilha de controle, criação de cards de acompanhamento e gravação em banco de dados.

## Papel na arquitetura

Dentro da solução, este workflow é a ponte entre processamento e operação.

Ele recebe o resultado consolidado e distribui o conteúdo para diferentes destinos, respeitando o contexto de cada um.

Dessa forma, o mesmo processamento passa a gerar valor para acompanhamento humano, organização operacional e armazenamento estruturado.

## Etapas do fluxo

### 1. Recebe o payload final do processamento

O workflow começa com o recebimento do webhook disparado pela etapa anterior.

Esse payload já contém cabeçalho estruturado, itens da OS, referência da pasta criada e demais dados preparados pelo processamento principal.

A partir daqui, o foco deixa de ser interpretar o documento e passa a ser distribuir a informação.

### 2. Trata descrições para uso operacional

Nem sempre a descrição extraída do documento está no melhor formato para consumo por times de operação.

Por isso, o fluxo executa uma etapa específica de tratamento textual para gerar nomes mais claros e utilizáveis em mensagens e controles.

Essa adaptação melhora a legibilidade sem perder o vínculo com a estrutura original da OS.

### 3. Monta a mensagem operacional

Com os dados já tratados, o workflow monta uma mensagem de registro da Ordem de Serviço.

Essa mensagem reúne informações como número da OS, cliente, referência, prazo, prioridade, responsável e lista resumida dos itens.

O resultado é um texto pronto para comunicação rápida com contexto suficiente para acompanhamento imediato.

### 4. Envia a mensagem por WhatsApp

Depois de montar a comunicação, o fluxo dispara a mensagem para o canal operacional definido.

Essa etapa reduz a dependência de avisos manuais e acelera a circulação da informação dentro da equipe.

Em ambientes de operação intensa, esse tipo de automação diminui atrasos de repasse e melhora visibilidade.

### 5. Prepara a linha da planilha operacional

Além da mensagem, o workflow organiza os dados no formato exigido pela planilha de controle.

Campos como cliente, demanda, horário, categoria, entrega e número da OS são preparados para atualização estruturada.

Alguns campos permanecem intencionalmente sinalizados para definição manual posterior, o que mostra que a automação foi desenhada para conviver com decisões humanas onde necessário.

### 6. Encontra a primeira linha vazia e atualiza a planilha

Em seguida, o fluxo consulta a planilha, identifica a primeira linha disponível e grava os dados da nova OS.

Essa abordagem evita sobreposição, mantém o histórico organizado e permite usar a planilha como ferramenta viva de acompanhamento.

É uma integração simples no conceito, mas muito útil no dia a dia operacional.

### 7. Explode os itens e cria cards no Trello

O workflow também desdobra os itens da OS para acompanhamento visual em Trello.

Cada item pode virar um card com informações importantes como produto, modelo, material, dimensões, quantidade, acabamento, etiquetas e prazo.

Essa etapa aproxima os dados estruturados da rotina de produção, facilitando priorização e acompanhamento do trabalho.

### 8. Prepara o upsert do cabeçalho da OS no banco

Além da camada operacional visível, o fluxo organiza a persistência do cabeçalho da Ordem de Serviço em banco.

Nessa estrutura entram referência, cliente, contato, telefone, endereço, datas, logística, número de itens e demais metadados da OS.

Isso fortalece rastreabilidade, consultas futuras e integrações com outras rotinas.

### 9. Resolve vínculo com cadastro de cliente

O workflow também executa consulta para localizar o cliente a partir do documento cadastral e vincular corretamente a OS à base correspondente.

Essa etapa é importante porque permite relacionar o registro processado com entidades já existentes no banco.

Na prática, isso melhora a integridade dos dados e abre espaço para análises futuras.

### 10. Persiste datas e timestamps padronizados

Antes da gravação final, o fluxo padroniza datas e horários em formato apropriado para banco.

Esse cuidado evita inconsistências entre formatos textuais e timestamps operacionais.

É um detalhe técnico importante para manter qualidade de dados no longo prazo.

### 11. Prepara e grava itens e subitens

Além do cabeçalho, o workflow estrutura também os itens da OS para persistência detalhada.

Cada item pode levar descrição, observações, quantidades, dimensões e subitens associados, preservando o vínculo com a Ordem de Serviço principal.

Com isso, a solução não armazena apenas um resumo da OS, mas também sua decomposição operacional.

## Por que este workflow é importante

Muitas automações param na extração do dado.

Este projeto vai além porque garante que a informação extraída seja de fato distribuída para os lugares onde ela gera uso real.

Isso torna a solução mais completa, mais madura e mais alinhada com contexto de operação.

## Valor técnico demonstrado

Este workflow evidencia competências como:

- distribuição multicanal a partir de um payload único;
- adaptação de dados técnicos para consumo operacional;
- integração com mensageria, planilha, Trello e banco;
- atualização controlada de planilhas com localização de linha;
- persistência estruturada de cabeçalho, itens e subitens;
- desenho de automação com equilíbrio entre regra automática e intervenção humana.

## Resultado esperado

Ao final do workflow 3, a Ordem de Serviço já foi comunicada, registrada, organizada e persistida.

Esse fechamento transforma a automação em uma solução realmente útil para a rotina do negócio, e não apenas em um experimento técnico de leitura de PDF.

## Exemplo público

Exemplos fictícios das saídas preparadas por este workflow estão disponíveis em [`samples/distribuicao/`](../samples/distribuicao/).

Esses arquivos mostram como o payload consolidado pode ser transformado em mensagem operacional, linha de planilha, registro de banco e item de acompanhamento.
