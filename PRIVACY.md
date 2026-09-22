# Política de Privacidade — MIND

**Última atualização:** 22 de setembro de 2026

Esta Política de Privacidade descreve como a extensão **MIND** trata dados quando você usa seus recursos de notas, organização local, captura de páginas e sincronização online opcional.

## 1. Princípio local-first

O MIND foi projetado para funcionar principalmente de forma **local-first**.

Notas internas, metadados e índices locais podem ser armazenados no navegador usando **IndexedDB**. Preferências e dados temporários da extensão podem ser armazenados com os mecanismos locais do Chrome.

O conteúdo local não é enviado para um servidor apenas por existir no MIND.

## 2. Dados tratados localmente

Dependendo dos recursos utilizados, o MIND pode processar e armazenar localmente:

- conteúdo de notas;
- títulos e caminhos de notas;
- pastas e raízes;
- links internos, backlinks, tags, headings e metadados derivados;
- preferências de interface e organização;
- dados necessários para busca, grafo e mapas mentais.

Esses dados são usados para fornecer as funcionalidades da extensão.

## 3. Captura de páginas e seleções

Quando você solicita explicitamente uma captura, o MIND pode acessar a guia ativa para obter:

- título da página;
- URL;
- descrição da página, quando disponível;
- texto selecionado;
- conteúdo textual da página necessário à captura.

Esse acesso ocorre para executar a ação solicitada pelo usuário, como **Salvar página no MIND** ou **Salvar seleção no MIND**.

O MIND não usa essa permissão para monitorar continuamente a navegação.

## 4. Permissões do Chrome

A extensão pode utilizar permissões como:

- **storage** — armazenar preferências e dados locais necessários ao funcionamento;
- **sidePanel** — exibir o painel lateral;
- **contextMenus** — oferecer ações de captura e abertura do MIND;
- **scripting** — extrair conteúdo da guia ativa quando você solicita uma captura;
- **activeTab** — acessar a guia ativa no contexto de uma ação iniciada pelo usuário;
- **identity** — realizar autenticação opcional com Google;
- permissões opcionais de host — quando necessárias para recursos explicitamente acionados pelo usuário.

As permissões são utilizadas para funcionalidades do MIND e não para publicidade comportamental.

## 5. Autenticação da conta MIND e dados de senha

O MIND oferece autenticação online por meio do **Supabase Auth**.

Quando o usuário cria uma conta ou entra na conta MIND usando autenticação por e-mail e senha, o formulário de autenticação processa:

- endereço de e-mail ou identificador da conta;
- **senha da conta MIND**.

A senha é utilizada exclusivamente para realizar a autenticação junto ao **Supabase Auth**. Durante o processo de login, o MIND pode manter a senha temporariamente em memória para enviá-la ao serviço de autenticação.

**O MIND não usa a senha para outra finalidade e não deve armazená-la em IndexedDB, chrome.storage, arquivos locais, notas, logs ou bancos de dados próprios. O MIND não vende, compartilha ou envia a senha para terceiros além do serviço de autenticação necessário para realizar o login.**

A autenticação e o processamento das credenciais são realizados pelo Supabase Auth. O MIND não possui nem inclui no pacote da extensão uma chave `service_role` do Supabase.

Quando o usuário utiliza autenticação por Google, a autenticação é realizada pelo fluxo correspondente do Google/Chrome e o MIND não recebe a senha da conta Google.

## 6. Conta, sessão e sincronização online

Quando recursos online são utilizados, o MIND pode processar dados relacionados à conta e à sessão, incluindo:

- identificador da conta;
- endereço de e-mail associado à conta, quando fornecido pelo provedor de autenticação;
- tokens ou informações de sessão necessários para manter a autenticação;
- nome da raiz;
- caminhos de pastas;
- caminhos e títulos de notas;
- conteúdo das notas online;
- posição/ordenação;
- datas de criação e atualização.

Esses dados são usados para autenticação, criação/restauração de sessão e sincronização das funcionalidades online solicitadas pelo usuário.

## 7. Sincronização online opcional

Quando você cria ou utiliza uma raiz online, dados relacionados a essa raiz podem ser enviados ao projeto Supabase utilizado pelo MIND. Isso pode incluir os dados de conta e os dados de conteúdo descritos nesta política.

O banco utiliza políticas de **Row Level Security (RLS)** para restringir o acesso aos registros ao usuário autenticado correspondente.

Notas e raízes mantidas apenas localmente não são convertidas automaticamente em conteúdo online.

## 8. Serviços de terceiros

O MIND pode utilizar:

- **Google**, para autenticação opcional;
- **Supabase**, para autenticação, processamento de credenciais e armazenamento/sincronização online opcional;
- **Google Chrome / Chrome Web Store**, para distribuição e execução da extensão.

Esses serviços também podem estar sujeitos às suas próprias políticas de privacidade e práticas de tratamento de dados.

## 9. Analytics, publicidade e venda de dados

A versão descrita nesta política não inclui sistema próprio de publicidade comportamental nem integração de analytics destinada a rastrear o uso do usuário.

O MIND não vende dados pessoais.

## 10. Retenção e exclusão

Dados locais permanecem no dispositivo até serem removidos pelo usuário, pela extensão, pelo navegador ou pela limpeza dos dados da extensão.

Conteúdo online permanece no serviço de nuvem enquanto estiver associado à conta e não for excluído pelo usuário ou por processos administrativos aplicáveis.

**As senhas de autenticação não são armazenadas pelo MIND em seus mecanismos próprios de armazenamento.** O armazenamento e o gerenciamento de credenciais de autenticação seguem o serviço de autenticação utilizado.

## 11. Segurança

O MIND procura aplicar medidas compatíveis com sua arquitetura, incluindo:

- armazenamento local no navegador;
- uso de HTTPS para comunicação com o backend configurado;
- autenticação para recursos online;
- políticas RLS no banco online;
- ausência de segredos administrativos no pacote da extensão;
- não armazenamento da senha da conta MIND nos mecanismos locais próprios da extensão.

Nenhum sistema pode garantir segurança absoluta.

## 12. Crianças

O MIND não é projetado especificamente para coletar dados de crianças nem utiliza recursos direcionados a publicidade infantil.

## 13. Alterações nesta política

Esta política pode ser atualizada quando houver alterações relevantes nas funcionalidades, integrações, permissões ou práticas de tratamento de dados do MIND.

A data de atualização será alterada quando houver uma nova versão desta política.

## 14. Contato

Para dúvidas sobre privacidade ou sobre esta política, utilize o repositório público:

**GitHub:** https://github.com/marcosmurilorodriguesb-alt/MIND-privacy

Você pode abrir uma Issue no repositório para solicitar esclarecimentos.