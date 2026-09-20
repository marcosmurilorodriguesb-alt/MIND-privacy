# Política de Privacidade — MIND

**Última atualização:** 20 de setembro de 2026

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
- conteúdo textual da página, limitado pelo próprio mecanismo de captura.

Esse acesso ocorre para executar a ação solicitada pelo usuário, como **Salvar página no MIND** ou **Salvar seleção no MIND**.

O MIND não usa essa permissão para monitorar continuamente a navegação.

## 4. Permissões do Chrome

A extensão pode solicitar permissões como:

- **storage** — armazenar preferências e dados locais necessários ao funcionamento;
- **sidePanel** — exibir o painel lateral;
- **contextMenus** — oferecer ações de captura e abertura do MIND;
- **scripting** — extrair conteúdo da guia ativa quando você solicita uma captura;
- **activeTab** — acessar a guia ativa no contexto de uma ação iniciada pelo usuário;
- **identity** — realizar autenticação opcional com Google;
- permissões opcionais de host — quando necessárias para recursos explicitamente acionados pelo usuário.

As permissões são utilizadas para funcionalidades do MIND e não para publicidade comportamental.

## 5. Conta Google e autenticação

Se você optar por usar autenticação online com Google, o MIND utiliza o fluxo de autenticação do Chrome e do Google para obter um token de identidade.

Esse token é enviado ao **Supabase Auth** para criar ou restaurar a sessão da sua conta online do MIND.

O pacote da extensão não contém Google Client Secret nem chave `service_role` do Supabase.

## 6. Sincronização online opcional

Os recursos online são opcionais.

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

## 7. Serviços de terceiros

O MIND pode utilizar:

- **Google**, para autenticação opcional;
- **Supabase**, para autenticação e armazenamento/sincronização online opcional;
- **Google Chrome / Chrome Web Store**, para distribuição e execução da extensão.

O uso desses serviços também pode estar sujeito às políticas de privacidade próprias desses fornecedores.

## 8. Analytics, publicidade e venda de dados

A versão descrita nesta política não inclui sistema próprio de publicidade comportamental nem integração de analytics destinada a rastrear o uso do usuário.

O MIND não vende dados pessoais.

## 9. Retenção e exclusão

Dados locais permanecem no dispositivo até serem removidos pelo usuário, pela extensão, pelo navegador ou pela limpeza dos dados da extensão.

Conteúdo online permanece no serviço de nuvem enquanto estiver associado à conta e não for excluído pelo usuário ou por processos administrativos aplicáveis.

A exclusão de raízes, pastas ou notas online utiliza as operações de exclusão correspondentes no serviço de nuvem.

## 10. Segurança

O MIND procura aplicar medidas compatíveis com sua arquitetura, incluindo:

- armazenamento local no navegador;
- uso de HTTPS para comunicação com o backend configurado;
- autenticação para recursos online;
- políticas RLS no banco online;
- ausência de segredos administrativos no pacote da extensão.

Nenhum sistema pode garantir segurança absoluta.

## 11. Crianças

O MIND não é projetado especificamente para coletar dados de crianças nem utiliza recursos direcionados a publicidade infantil.

## 12. Alterações nesta política

Esta política pode ser atualizada quando houver alterações relevantes nas funcionalidades, integrações, permissões ou práticas de tratamento de dados do MIND.

A data de atualização será alterada quando houver uma nova versão desta política.

## 13. Contato

Para dúvidas sobre privacidade ou sobre esta política, utilize o repositório público:

**GitHub:** https://github.com/marcosmurilorodriguesb-alt/MIND-privacy

Você pode abrir uma Issue no repositório para solicitar esclarecimentos.
