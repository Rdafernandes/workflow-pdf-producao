# Privacidade e segurança

## Objetivo
Definir regras mínimas para armazenar, revisar e publicar este projeto sem expor dados sensíveis, operacionais ou pessoais.

## Situação atual
Este repositório contém apenas a versão sanitizada e documentada da automação.

Os workflows originais utilizados em ambiente real não fazem parte da publicação pública, pois podem conter dados operacionais, identificadores internos, credenciais, payloads de execução e informações sensíveis.

## Tipos de dados sensíveis identificados
Durante a análise inicial, foram identificados os seguintes tipos de informação que não devem ser publicados:

- Tokens de autenticação.
- Credenciais e cabeçalhos de autorização.
- Números de telefone e listas de remetentes autorizados.
- IDs e links reais de armazenamento.
- E-mails de usuários e permissões de acesso.
- Dados de clientes, contatos e documentos.
- Endereços, observações operacionais e detalhes de entrega.
- IDs internos de webhook, banco e integrações.

## Regras obrigatórias
### 1. Publicar apenas material sanitizado
Somente arquivos revisados, anonimizados e preparados para portfólio devem compor a versão pública do repositório.

### 2. Não publicar originais
Arquivos exportados diretamente do ambiente de produção não devem ser enviados ao GitHub sem tratamento.

### 3. Sanitização antes de compartilhar
Todo material que entrar no repositório deve passar por limpeza prévia.

### 4. Uso de placeholders
Sempre substituir valores reais por exemplos neutros, como:
- `SEU_TOKEN_AQUI`
- `EMAIL_EXEMPLO@DOMINIO.COM`
- `ID_PASTA_EXEMPLO`
- `CLIENTE_EXEMPLO`
- `5511999999999`

### 5. Remoção de metadados operacionais
Sempre remover:
- IDs de execução;
- nomes internos de ambiente;
- URLs privadas;
- nomes de contas;
- permissões reais;
- identificadores de instância.

## O que não pode subir
Não publicar:
- JSON bruto de workflow com credenciais embutidas;
- payloads reais recebidos em webhook;
- PDFs reais de clientes;
- prints com dados visíveis;
- links reais de armazenamento, gestão, banco ou mensageria;
- nomes completos, e-mails, telefones ou documentos de pessoas;
- dados de OS reais com endereço, contato ou observações.

## O que pode subir
Pode publicar, após revisão:
- documentação escrita;
- fluxos explicados em linguagem descritiva;
- JSON sanitizado;
- exemplos fictícios em `samples/`;
- diagramas sem identificadores reais;
- capturas editadas e anonimizadas.

## Processo de revisão
Antes de subir qualquer arquivo:
1. Verificar se há nomes reais.
2. Verificar se há telefones, e-mails ou documentos.
3. Verificar se há links ou IDs reais.
4. Verificar se há tokens, credenciais ou headers.
5. Confirmar se o exemplo é fictício.
6. Confirmar se o arquivo pode ser entendido sem depender do original bruto.
7. Confirmar se exemplos em `samples/` representam estados arquiteturais, e não payloads reais ou outputs brutos de execução.

## Publicação pública
O repositório só poderá ser tornado público quando:
- não houver credenciais expostas;
- não houver dados pessoais identificáveis;
- não houver referências operacionais sensíveis;
- os exemplos forem totalmente fictícios;
- os workflows disponíveis forem versões sanitizadas.

## Responsabilidade
A segurança do repositório depende de revisão manual antes de cada envio.

A regra principal é simples: se existir dúvida sobre exposição, o arquivo não deve ser publicado.
