# Checklist de publicação

## Objetivo
Este checklist existe para garantir que o projeto só avance para compartilhamento externo quando estiver organizado, compreensível e seguro.

## Regra principal
Se houver qualquer dúvida sobre exposição de dado sensível, a publicação deve ser adiada até revisão completa.

## Checklist do repositório
Antes de pensar em publicação, confirmar:
- [x] O repositório está organizado.
- [x] A estrutura de pastas está finalizada.
- [x] O README está atualizado.
- [x] Os arquivos da pasta `docs` estão preenchidos.
- [x] Não existem arquivos soltos sem função clara.
- [x] Os nomes dos arquivos estão padronizados.

## Checklist de segurança
Confirmar que não existe nenhum destes elementos no repositório:
- [x] Tokens.
- [x] Chaves.
- [x] Headers de autorização.
- [x] URLs privadas.
- [x] IDs reais de integrações.
- [x] Webhooks reais.
- [x] permissões reais de usuários.
- [x] e-mails reais.
- [x] telefones reais.
- [x] documentos reais.
- [x] endereços reais.
- [x] nomes reais de clientes.
- [x] payloads brutos de produção.

## Checklist dos workflows
Antes de subir qualquer workflow:
- [x] O arquivo foi sanitizado.
- [x] Credenciais foram removidas.
- [x] Valores sensíveis foram substituídos por placeholders.
- [x] Nomes internos foram revisados.
- [x] IDs e links foram removidos ou mascarados.
- [x] O arquivo pode ser lido sem depender do ambiente original.
- [x] O objetivo do workflow está descrito na documentação.

## Checklist dos exemplos
Antes de publicar exemplos:
- [x] O PDF de exemplo é fictício ou totalmente anonimizado.
- [x] As saídas de exemplo não contêm dados reais.
- [x] Os nomes usados são genéricos.
- [x] Telefones e documentos foram substituídos.
- [x] Não existe possibilidade de rastrear cliente real.
- [x] O exemplo serve apenas para demonstrar a lógica do fluxo.

## Checklist visual
Antes de publicar imagens, capturas ou diagramas:
- [x] Não há nomes reais visíveis.
- [x] Não há e-mails visíveis.
- [x] Não há links internos visíveis.
- [x] Não há IDs visíveis.
- [x] Não há tokens visíveis.
- [x] Não há dados de cliente visíveis.
- [x] O material visual está limpo e legível.

## Checklist documental
Antes de abrir o repositório:
- [x] A visão geral do projeto está clara.
- [x] A arquitetura está explicada.
- [x] O documento de privacidade está atualizado.
- [x] O objetivo do projeto está descrito com clareza.
- [x] O repositório pode ser entendido por alguém externo sem depender do ambiente real.

## Critério de liberação
O repositório pode avançar para compartilhamento externo quando os itens críticos abaixo estiverem validados:

- segurança;
- privacidade;
- sanitização;
- clareza da documentação;
- coerência dos exemplos públicos.

Nesta versão, os itens críticos foram revisados com foco em publicação pública de portfólio técnico.

## Registro da checagem final
A checagem final de segurança e privacidade também está registrada em [`checagem_final_sem_dados_sensiveis.json`](checagem_final_sem_dados_sensiveis.json).

Esse arquivo resume o escopo revisado, os itens verificados e as regras usadas para publicação pública do case.

## Observação final
Publicar rápido é menos importante do que publicar com segurança.

Uma versão privada e organizada é melhor do que uma versão pública com risco de exposição.
