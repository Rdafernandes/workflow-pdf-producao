# Workflow 1 — Entrada e validação do PDF

## Visão geral

Este workflow é a camada de entrada da automação.

Sua responsabilidade é receber o evento inicial e decidir, com segurança, se o documento deve ou não seguir para processamento.

Ele atua como um filtro operacional que protege o restante da esteira contra arquivos inválidos, remetentes não autorizados e entradas fora do padrão.

## Objetivo

O objetivo do workflow 1 é garantir que apenas Ordens de Serviço válidas avancem para o workflow principal.

Essa decisão parece simples, mas é estratégica: quando a validação acontece logo no início, o processo evita consumo desnecessário de recursos, reduz erros em cascata e melhora a confiabilidade do sistema.

## Papel na arquitetura

Dentro da arquitetura geral, este workflow funciona como gateway.

Em vez de deixar que qualquer mensagem ou documento chegue diretamente à etapa de processamento, ele centraliza as regras mínimas de elegibilidade da entrada.

Isso torna a solução mais robusta, mais segura e mais fácil de manter.

## O que o workflow faz

### 1. Recebe a requisição inicial

O fluxo começa a partir de um webhook.

Esse webhook captura o payload de entrada e disponibiliza as informações da mensagem recebida para as etapas seguintes.

A partir desse momento, o workflow passa a tratar o conteúdo como um evento operacional que precisa ser validado.

### 2. Extrai os dados relevantes da mensagem

Depois da entrada, o fluxo identifica informações importantes para a triagem, como remetente, chat de origem, nome do arquivo, tipo de anexo e links associados ao documento.

Essa extração inicial organiza o payload bruto e o transforma em um conjunto de campos úteis para decisão.

### 3. Valida o remetente

Uma das regras centrais desta etapa é a validação do remetente contra uma lista de números autorizados.

Com isso, o workflow impede que arquivos enviados por origens não homologadas entrem na esteira principal.

Essa proteção é importante para reduzir ruído e evitar o acionamento indevido do processo.

### 4. Valida o tipo de arquivo

Além da origem, o workflow confirma se a mensagem contém efetivamente um documento PDF.

Essa checagem evita que mensagens de texto, imagens ou anexos incompatíveis avancem indevidamente.

É uma regra simples, mas essencial para manter previsibilidade no fluxo.

### 5. Valida o padrão do nome do arquivo

O fluxo também verifica se o nome do arquivo segue o padrão esperado para Ordens de Serviço.

Essa validação ajuda a separar documentos válidos de anexos genéricos, reduz ambiguidades e melhora a consistência do processo seguinte.

Ao padronizar essa entrada, o sistema ganha previsibilidade para a extração do número da OS e para o restante da automação.

### 6. Encaminha somente entradas válidas

Se as condições de remetente autorizado, documento em PDF e nome compatível forem atendidas, o workflow aciona o segundo fluxo da solução.

Se alguma dessas regras falhar, o documento não segue adiante.

Essa separação mantém a automação enxuta e evita processamento desnecessário.

## Por que este workflow é importante

Em muitos projetos de automação, a maior atenção fica no processamento principal, mas a qualidade da entrada define a qualidade de todo o resultado.

Ao colocar a validação como primeira etapa formal, a solução reduz retrabalho, evita erros encadeados e melhora o nível de confiança nas saídas geradas.

Na prática, este workflow funciona como a portaria técnica do processo.

## Valor técnico demonstrado

Este workflow evidencia algumas competências importantes:

- desenho de automação orientada a eventos;
- aplicação de regras de negócio logo na entrada;
- tratamento de payload externo com normalização de dados;
- separação clara entre validação e processamento;
- integração entre workflows com passagem controlada de contexto.

## Resultado esperado

Ao final desta etapa, o sistema tem uma decisão clara: ou a OS está apta a entrar no processamento principal, ou deve ser barrada ainda na entrada.

Esse comportamento aumenta a robustez da solução e prepara o cenário para que o workflow 2 trabalhe apenas com dados válidos e consistentes.

## Exemplo público

Um exemplo fictício do payload validado por este workflow está disponível em [`samples/entrada/`](../samples/entrada/).

Esse arquivo representa o estado da entrada após validação de remetente, tipo de arquivo e padrão do nome do PDF.
