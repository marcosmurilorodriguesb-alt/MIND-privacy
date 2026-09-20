# Política de Privacidade — MIND

**Última atualização:** 20 de setembro de 2026

Esta Política de Privacidade descreve como a extensão **MIND** trata dados quando você usa notas, organização local, captura de páginas e recursos online opcionais.

## 1. Princípio local-first

O MIND foi projetado para funcionar principalmente de forma **local-first**.

Notas internas, metadados e índices locais podem ser armazenados no navegador usando **IndexedDB**. Preferências, sessões e dados temporários da extensão podem ser armazenados pelos mecanismos locais do Chrome.

O conteúdo mantido apenas em áreas locais não é enviado a um servidor apenas por existir no MIND.

## 2. Dados tratados localmente

Dependendo dos recursos utilizados, o MIND pode processar e armazenar localmente:

- conteúdo, títulos e caminhos de notas;
- pastas e raízes;
- links internos, backlinks, tags, headings e metadados derivados;
- preferências de interface e organização;
- dados necessários para busca, grafo e mapas mentais;
- dados de sessão necessários para recursos online opcionais.

Esses dados são usados para fornecer as funcionalidades declaradas da extensão.

## 3. Captura de páginas e seleções

Quando você solicita explicitamente uma captura, o MIND pode acessar a **guia ativa** para obter:

- título da página;
- URL;
- descrição da página, quando disponível;
- texto selecionado;
- conteúdo textual necessário à captura.

A captura usa acesso temporário à guia ativa e não concede ao MIND acesso persistente a todos os sites. O MIND não monitora continuamente seu histórico de navegação.

Conteúdo capturado permanece local quando salvo em uma área local. Se o usuário escolher uma raiz online como destino, o conteúdo correspondente poderá ser enviado ao Supabase como parte da sincronização solicitada.

## 4. Permissões do Chrome

A extensão utiliza ou pode solicitar:

- **storage** — armazenar preferências, dados locais e sessão necessária ao funcionamento;
- **sidePanel** — exibir o painel lateral;
- **contextMenus** — oferecer ações explícitas de captura e abertura do MIND;
- **scripting** — extrair conteúdo da guia ativa quando o usuário inicia uma captura;
- **activeTab** — conceder acesso temporário à guia ativa após uma ação do usuário;
- **identity** — permissão opcional, solicitada somente quando o usuário inicia autenticação com Google.

O MIND não solicita acesso persistente a todos os sites para realizar a captura Web.

## 5. Conta por e-mail e senha

Se você optar por criar ou acessar uma conta online usando e-mail e senha:

- o endereço de e-mail e a senha informados são transmitidos por HTTPS diretamente ao **Supabase Auth** para autenticação;
- o MIND não grava a senha em IndexedDB nem em `chrome.storage.local`;
- após autenticação, informações de conta e tokens de sessão podem ser armazenados localmente para manter a sessão ativa.

Esses dados são utilizados somente para autenticação e fornecimento dos recursos online solicitados.

## 6. Conta Google

Se você optar por usar autenticação Google, o MIND solicita a permissão opcional `identity` e usa o fluxo de autenticação do Chrome/Google.

O fluxo pode solicitar os escopos `openid`, `email` e `profile`. O Google pode fornecer um ID Token e informações de perfil associadas, como identificador da conta, e-mail e nome.

O ID Token é enviado ao **Supabase Auth** para criar, restaurar ou vincular a sessão da conta online do MIND.

O pacote da extensão não contém Google Client Secret nem chave `service_role` do Supabase.

## 7. Sessão online

Para manter a conta conectada, o MIND pode armazenar localmente em `chrome.storage.local`:

- access token;
- refresh token;
- data de expiração;
- identificador e informações básicas do usuário autenticado;
- provedores/identidades vinculados quando fornecidos pelo serviço de autenticação.

Esses dados são usados para autenticar chamadas ao backend e restaurar a sessão. Sair da conta remove a sessão local mantida pelo MIND.

## 8. Sincronização online opcional

Quando você cria ou utiliza uma raiz online, dados relacionados a essa raiz podem ser enviados ao projeto Supabase utilizado pelo MIND. Isso pode incluir:

- identificador da conta;
- nome da raiz;
- caminhos de pastas;
- caminhos e títulos de notas;
- conteúdo das notas online;
- posição/ordenação;
- datas de criação e atualização.

O banco utiliza políticas de **Row Level Security (RLS)** para restringir o acesso dos registros ao usuário autenticado correspondente.

Notas e raízes mantidas apenas localmente não são convertidas automaticamente em conteúdo online.

## 9. Serviços de terceiros

O MIND pode utilizar:

- **Google**, somente quando o usuário escolhe autenticação Google;
- **Supabase**, para autenticação e armazenamento/sincronização online opcional;
- **Google Chrome / Chrome Web Store**, para execução e distribuição da extensão.

Esses fornecedores também podem tratar dados de acordo com suas próprias políticas de privacidade e termos.

## 10. Analytics, publicidade e venda de dados

A versão descrita nesta política:

- não inclui publicidade comportamental;
- não integra um sistema próprio de analytics destinado a rastrear a atividade do usuário;
- não vende dados pessoais;
- não utiliza conteúdo de notas, capturas, credenciais ou dados de autenticação para publicidade personalizada.

## 11. Uso Limitado de dados

O uso de informações recebidas das APIs do Google pelo MIND cumprirá a **Política de Dados do Usuário dos Serviços de API do Google**, incluindo os requisitos de **Uso Limitado (Limited Use)**.

Os dados são utilizados somente para fornecer ou melhorar funcionalidades do MIND que o usuário iniciou ou habilitou. Eles não são transferidos para terceiros para publicidade, criação de perfis publicitários ou finalidades incompatíveis com a funcionalidade declarada da extensão, exceto quando necessário para prestar o próprio serviço solicitado, cumprir a lei ou proteger contra abuso e incidentes de segurança.

## 12. Retenção e exclusão

Dados locais permanecem no dispositivo até serem removidos pelo usuário, pela extensão, pelo navegador, pela desinstalação/limpeza de dados da extensão ou por operações de exclusão disponíveis no MIND.

Conteúdo online permanece no Supabase enquanto estiver associado à conta e não for excluído pelo usuário ou por processos administrativos aplicáveis.

A exclusão de raízes, pastas ou notas online utiliza as operações de exclusão correspondentes no serviço de nuvem.

**Desinstalar a extensão ou sair da conta não deve ser entendido como exclusão automática da conta online ou de todo conteúdo remoto.**

## 13. Segurança

O MIND procura aplicar medidas compatíveis com sua arquitetura, incluindo:

- armazenamento local no navegador;
- HTTPS para comunicação com o backend e provedores de autenticação;
- autenticação para recursos online;
- políticas RLS no banco online;
- ausência de segredos administrativos no pacote da extensão;
- acesso temporário à guia ativa para captura, em vez de acesso persistente a todos os sites.

Nenhum sistema pode garantir segurança absoluta.

## 14. Crianças

O MIND não é projetado especificamente para coletar dados de crianças e não utiliza recursos direcionados a publicidade infantil.

## 15. Alterações nesta política

Esta política pode ser atualizada quando houver alterações relevantes nas funcionalidades, integrações, permissões ou práticas de tratamento de dados do MIND.

A data de atualização será alterada quando houver uma nova versão desta política.

## 16. Contato

Para dúvidas sobre privacidade ou sobre esta política, utilize o repositório público:

**GitHub:** https://github.com/marcosmurilorodriguesb-alt/MIND-privacy

Você pode abrir uma Issue para solicitar esclarecimentos. **Não publique senhas, tokens, conteúdo privado de notas ou outros dados sensíveis em uma Issue pública.**
