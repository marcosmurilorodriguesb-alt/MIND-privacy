# Política de Privacidade — MIND

**Última atualização:** 22 de setembro de 2026

Esta Política de Privacidade descreve, de forma específica, quais dados a extensão **MIND** pode tratar, onde são tratados, para que são utilizados, quando são enviados a serviços externos e como são armazenados ou excluídos.

O MIND é um workspace **local-first** para criação, organização e conexão de notas e conhecimento no navegador. A sincronização online é opcional e somente ocorre quando o usuário utiliza os recursos de conta/nuvem correspondentes.

## 1. Princípio local-first

O MIND foi projetado para funcionar principalmente de forma **local-first**.

Notas internas, metadados e índices locais podem ser armazenados no navegador usando **IndexedDB**. Preferências, sessão de autenticação e outros dados necessários ao funcionamento podem ser armazenados pelos mecanismos locais do Chrome.

O conteúdo local não é enviado a um servidor simplesmente por existir no MIND. O envio para a nuvem ocorre quando o usuário utiliza recursos online que exigem comunicação com o serviço configurado.

## 2. Dados tratados localmente

Dependendo dos recursos utilizados, o MIND pode processar e armazenar localmente:

- conteúdo de notas;
- títulos e caminhos de notas;
- pastas e raízes;
- links internos, backlinks, tags, headings e metadados derivados;
- preferências de interface e organização;
- dados necessários para busca, grafo e mapas mentais;
- informações de sessão necessárias para manter uma conta online autenticada;
- tokens de acesso/renovação da sessão online, armazenados localmente para manutenção da sessão;
- Google Client ID, quando o usuário o configura para o fluxo de autenticação Google.

Esses dados são usados para fornecer as funcionalidades solicitadas pelo usuário.

**A senha da conta MIND não é armazenada nesses mecanismos locais pelo MIND.**

## 3. Captura de páginas e seleções

Quando o usuário solicita explicitamente uma captura, o MIND pode acessar a guia ativa para obter:

- título da página;
- URL;
- descrição da página, quando disponível;
- texto selecionado;
- conteúdo textual da página necessário à captura.

Esses dados são utilizados para executar ações iniciadas pelo usuário, como **Salvar página no MIND** ou **Salvar seleção no MIND**.

O MIND não utiliza essa permissão para monitorar continuamente a navegação.

Quando uma captura é salva em uma nota local, os dados passam a ser tratados como conteúdo da nota. Se o usuário posteriormente utilizar um recurso de sincronização online para essa nota, o conteúdo correspondente poderá ser enviado ao serviço de nuvem, conforme descrito nesta política.

## 4. Permissões do Chrome

A versão do MIND descrita nesta política utiliza:

- **storage** — armazenar preferências, sessão e outros dados locais necessários ao funcionamento;
- **sidePanel** — exibir o painel lateral;
- **contextMenus** — oferecer ações de captura e abertura do MIND;
- **scripting** — extrair conteúdo da guia ativa quando o usuário solicita uma captura;
- **activeTab** — acessar a guia ativa no contexto de uma ação iniciada pelo usuário;
- **identity** — realizar o fluxo opcional de autenticação com Google;
- acesso ao host do projeto Supabase configurado — realizar autenticação e sincronização online;
- permissões opcionais de host — permitir recursos de captura quando o usuário concede o acesso correspondente.

As permissões são utilizadas para fornecer as funcionalidades do MIND. Elas não são utilizadas para publicidade comportamental.

## 5. Autenticação da conta MIND e dados de senha

O MIND oferece autenticação online por meio do **Supabase Auth**.

Quando o usuário cria uma conta ou entra na conta MIND usando autenticação por e-mail e senha, o formulário de autenticação processa:

- endereço de e-mail ou identificador da conta;
- **senha da conta MIND**.

A senha é utilizada exclusivamente para autenticação junto ao **Supabase Auth**. Durante o processo de cadastro ou login, o MIND mantém a senha em memória apenas pelo tempo necessário para enviá-la ao serviço de autenticação.

**O MIND não usa a senha para outra finalidade e não a armazena em IndexedDB, chrome.storage, arquivos locais, notas, logs ou bancos de dados próprios.**

A senha é enviada ao endpoint de autenticação do Supabase porque esse serviço é o provedor de autenticação utilizado pelo MIND. O MIND não vende a senha, não a utiliza para publicidade e não a envia a outros destinatários além do serviço de autenticação necessário para processar a autenticação.

A autenticação e o processamento das credenciais são realizados pelo **Supabase Auth**. O MIND não inclui no pacote da extensão uma chave administrativa `service_role`.

Quando o usuário utiliza autenticação por Google, o MIND utiliza o fluxo de autenticação do Google/Chrome e recebe um token de autenticação necessário para concluir a sessão com o Supabase. **O MIND não recebe a senha da conta Google.**

## 6. Conta, sessão e sincronização online

Quando os recursos online são utilizados, o MIND pode processar:

- identificador da conta;
- endereço de e-mail associado à conta, quando fornecido pelo provedor de autenticação;
- informações do usuário retornadas pelo serviço de autenticação, quando necessárias à sessão;
- tokens de acesso e renovação e dados de expiração da sessão;
- nome das raízes online;
- caminhos de pastas;
- caminhos e títulos de notas;
- conteúdo das notas online;
- posição/ordenação;
- datas de criação e atualização.

Esses dados são utilizados para:

1. autenticar o usuário;
2. criar, restaurar e renovar a sessão;
3. identificar os dados pertencentes à conta autenticada;
4. criar, consultar, atualizar ou excluir raízes, pastas e notas online;
5. sincronizar o conteúdo online com o workspace local quando o usuário solicita ou utiliza essa funcionalidade.

## 7. Quando os dados são enviados para serviços externos

O MIND não envia todos os dados locais automaticamente.

Dados podem ser enviados ao **Supabase** quando necessário para:

- criar uma conta por e-mail e senha;
- realizar login por e-mail e senha;
- renovar ou encerrar uma sessão;
- concluir a autenticação por Google;
- consultar dados da conta;
- criar, consultar, atualizar ou excluir raízes, pastas e notas online;
- sincronizar dados de uma raiz online.

Em particular:

- a **senha da conta MIND** é enviada ao Supabase Auth somente para cadastro/autenticação por senha;
- os **tokens de sessão** são enviados ao Supabase quando necessários para autenticar requisições;
- o **conteúdo de notas, títulos, caminhos, pastas, raízes e metadados de sincronização** pode ser enviado ao Supabase quando o usuário utiliza a sincronização online.

Dados mantidos exclusivamente em raízes locais não são enviados para a nuvem apenas por estarem armazenados no MIND.

## 8. Armazenamento online e controle de acesso

Quando o usuário utiliza uma raiz online, os dados correspondentes são armazenados no projeto Supabase utilizado pelo MIND.

O armazenamento online inclui estruturas para raízes, pastas e notas, podendo conter nome, caminhos, posição, datas e conteúdo das notas.

O banco utiliza políticas de **Row Level Security (RLS)** para restringir o acesso aos registros ao usuário autenticado correspondente.

A arquitetura da extensão utiliza somente a URL do projeto e uma chave publicável do Supabase. O pacote da extensão não contém uma chave administrativa `service_role`.

## 9. Serviços de terceiros

O MIND utiliza ou pode utilizar:

- **Supabase**, para autenticação, processamento de credenciais, gerenciamento de sessão e armazenamento/sincronização online opcional;
- **Google**, quando o usuário escolhe autenticação Google;
- **Google Chrome**, para executar a extensão e fornecer APIs do navegador, incluindo armazenamento local, painel lateral, captura e autenticação;
- **Chrome Web Store**, para distribuição da extensão.

Esses serviços são terceiros e podem tratar dados de acordo com suas próprias políticas, termos e práticas de privacidade.

O MIND não utiliza serviços de terceiros para vender dados pessoais ou para publicidade comportamental.

## 10. Analytics, publicidade e venda de dados

A versão descrita nesta política não inclui sistema próprio de publicidade comportamental nem integração própria de analytics destinada a rastrear o uso do usuário.

O MIND não vende dados pessoais.

## 11. Retenção e exclusão

**Dados locais:** permanecem no dispositivo até serem removidos pelo usuário, pela extensão, pelo navegador ou pela limpeza dos dados da extensão.

**Sessão online:** informações de sessão armazenadas localmente permanecem enquanto forem necessárias para manter a autenticação e podem ser removidas quando o usuário encerra a sessão ou limpa os dados da extensão.

**Dados online:** raízes, pastas e notas armazenadas no Supabase permanecem associadas à conta enquanto não forem excluídas pelo usuário ou por processos administrativos aplicáveis.

**Senhas:** a senha da conta MIND não é armazenada pelo MIND em seus mecanismos próprios de armazenamento. O armazenamento e o gerenciamento da credencial de autenticação seguem o serviço de autenticação utilizado.

## 12. Segurança

O MIND aplica medidas compatíveis com sua arquitetura, incluindo:

- armazenamento local no navegador;
- HTTPS para comunicação com o backend configurado;
- autenticação para recursos online;
- políticas RLS no banco online;
- ausência de segredos administrativos no pacote da extensão;
- não armazenamento da senha da conta MIND nos mecanismos locais próprios da extensão.

Nenhum sistema pode garantir segurança absoluta.

## 13. Crianças

O MIND não é projetado especificamente para coletar dados de crianças nem utiliza recursos direcionados a publicidade infantil.

## 14. Alterações nesta política

Esta política pode ser atualizada quando houver alterações relevantes nas funcionalidades, integrações, permissões ou práticas de tratamento de dados do MIND.

A data de atualização será alterada quando houver uma nova versão desta política.

## 15. Contato

Para dúvidas sobre privacidade ou sobre esta política, utilize o repositório público:

**GitHub:** https://github.com/marcosmurilorodriguesb-alt/MIND-privacy

Você pode abrir uma Issue no repositório para solicitar esclarecimentos.
