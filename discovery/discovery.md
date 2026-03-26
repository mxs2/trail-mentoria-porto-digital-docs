# Documento de Discovery

# Projeto Trail — Documento de Discovery para Briefing de MVP

## 1. Visão Geral do Produto

O **Projeto Trail** é uma plataforma web centralizada para **gestão de trilhas de aprendizagem, desafios técnicos e fluxos de mentoria** voltada a programas de formação em TI, com foco inicial em estudantes de ADS (4º/5º semestre) sob mentoria da Avanade em parceria com o Porto Digital.

Embora o primeiro uso seja em uma **turma piloto**, o produto nasce com **mentalidade de plataforma escalável (multi-programa / multi-tenant)**, visando tornar-se o **padrão de gestão de talentos e formação técnica** no ecossistema Porto Digital + Avanade + empresas parceiras.

### 1.1 Objetivo Estratégico do Produto

- **Curto prazo (MVP – 3 meses)**  
  Validar, com uma turma piloto, um **fluxo mínimo, mas robusto**, que comprove:
  - Entrega full stack funcional (Angular + ASP.NET Core + SQL Server + Azure).
  - Ciclo completo de **entrega de desafios → feedback → atualização de métricas**.
  - Geração de valor mensurável para estudantes, mentores e empresas (via KPIs).

- **Médio prazo**  
  Evoluir a Trail como uma **plataforma multi-tenant** capaz de:
  - Atender **múltiplos programas de formação** (diferentes trilhas, empresas e turmas).
  - Servir como **fonte única de verdade** para dados de performance de talentos.
  - Apoiar decisões de **recrutamento, retenção e upskilling** no ecossistema.

---

## 2. Análise do Problema

### 2.1 Problema Declarado

**Hoje, programas de formação em TI** (como o da turma piloto ADS) sofrem com a **ausência de uma ferramenta centralizada** que conecte:

- A **jornada de aprendizagem** (trilhas, módulos, desafios).
- O **fluxo de mentoria** (feedback estruturado e tempestivo).
- As **métricas de performance** que interessam às empresas parceiras.

Resultado: os programas são mais difíceis de escalar, coordenar e medir.

### 2.2 Problema Real (Sintoma vs. Causa)

**Sintomas observados (AS-IS típico):**
- Trilhas e conteúdos dispersos em PDFs, slides, links soltos, e-mails, Trello, etc.
- Desafios submetidos por múltiplos meios (e-mail, Forms, GitHub isolado) sem padronização.
- Feedbacks de mentoria atrasados, não rastreáveis e sem métrica consolidada.
- Empresas parceiras sem **painel único** para avaliar performance e potencial de contratação.

**Causas raiz:**
1. **Falta de um “sistema de registro” único** para trilhas, desafios e feedbacks.  
2. **Ausência de visão orientada a métricas** sobre a jornada do estudante.  
3. **Processos não digitalizados de ponta a ponta**, dificultando automatização de KPIs.  
4. **Arquiteturas ad-hoc e não escaláveis**, que não suportam multi-programa/empresa.

### 2.3 Como a falta de ferramenta centralizada afeta a escalabilidade

1. **Escala operacional limitada**  
   - Cada novo programa/turma exige reinventar planilhas, formulários, processos de envio e avaliação.
   - Mentores perdem tempo em tarefas operacionais (organizar entregas, buscar links, consolidar dados) em vez de focar em mentoria de valor.

2. **Escala de qualidade de mentoria comprometida**
   - Sem um painel único de pendências, é fácil **perder entregas** ou atrasar feedbacks.
   - Lead time de feedback tende a ser alto, reduzindo o impacto pedagógico e o engajamento.

3. **Escala de parceria com empresas prejudicada**
   - Fica difícil justificar investimento em programas sem métricas claras de:
     - Conclusão de trilhas (throughput).
     - Aderência técnica (desafios entregues vs aprovados).
     - Performance individual dos estudantes (para contratação).

4. **Escala técnica e de evolução de produto**
   - Soluções improvisadas (Forms + planilhas + e-mail) não oferecem:
     - Modelo de dados extensível.
     - Autenticação/Autorização robustas.
     - Observabilidade mínima (logs, erros, auditoria de ações).

### 2.4 Custo de Não Agir

- **Programas pouco previsíveis**: dificuldade em comparar turmas e identificar padrões de sucesso ou risco.
- **Perda de eficiência de mentoria**: mentores gastam energia organizando dados, não desenvolvendo talentos.
- **Perda de oportunidades de contratação**: empresas não enxergam, com clareza, quem são os “top performers”.
- **Risco de retrabalho técnico futuro**: se a primeira solução não for pensada para multi-tenant, a evolução exigirá refatorações profundas.

---

## 3. Público-Alvo e Stakeholders

### 3.1 Personas Principais

1. **Estudante (User final da trilha)**
   - Busca entender claramente:
     - Onde está na jornada (progresso na trilha).
     - O que precisa entregar (desafios/marcos).
     - Como está indo (feedbacks e métricas de performance).
   - Necessidades-chave:
     - Interface simples e clara da trilha.
     - Submissão fácil de desafios (links/arquivos).
     - Feedback rápido e rastreável.

2. **Mentor Avanade (avaliador e facilitador)**
   - Responsável por:
     - Acompanhar entregas dos estudantes.
     - Avaliar desafios (nota, status, comentários).
     - Garantir feedback dentro de um lead time aceitável.
   - Necessidades-chave:
     - Painel de pendências de avaliação.
     - Ferramenta rápida de registro de feedback.
     - Visão de progresso da turma.

3. **Gestor da Empresa Parceira / Porto Digital (tomador de decisão)**
   - Usa o sistema para:
     - Acompanhar performance da turma e dos talentos.
     - Identificar candidatos para contratação.
     - Avaliar eficácia do programa de formação.
   - Necessidades-chave:
     - Dashboard com KPIs consolidados.
     - Snapshot de performance por estudante.
     - Comparação entre trilhas/turmas (no futuro).

### 3.2 Stakeholders Institucionais

- **Porto Digital**
  - Dono do ecossistema, interessado em um padrão reutilizável para múltiplos programas.
  - Necessita **governança multi-empresa** e visão macro de turmas/programas.

- **Avanade**
  - Mentora técnica e referência de boas práticas de engenharia.
  - Foco em:
    - Excelência da arquitetura (stack definida).
    - Qualidade do código e do design.
    - Demonstração de um ciclo de desenvolvimento profissional (DevOps, Azure, etc.).

- **Empresas Parceiras**
  - Cliente final dos talentos.
  - Exigem:
    - Confiabilidade dos dados de performance.
    - Visão rápida de quem contratar.

---

## 4. Escopo de MVP e Limites

### 4.1 Estratégia de Escopo

- **Arquitetura**: projetada desde o início para **multi-tenant** (multi-empresa / multi-programa / multi-turma).
- **Funcionalidade exposta na UI**: fluxo mínimo viável para **uma trilha piloto**, evitando sobrecarga de complexidade para os estudantes.
- **Configuração de novos tenants/programas**: via **scripts/seeding** ou interface administrativa **muito simples**, sem foco em self-service no MVP.

### 4.2 Funcionalidades Core (Obrigatórias no MVP)

1. **Cadastro e Autenticação**
   - Registro/carga de:
     - Estudantes.
     - Mentores.
     - Gestores (Porto Digital e empresas).
   - Login com **autenticação JWT/Identity** e perfis de acesso distintos:
     - Admin (Porto Digital).
     - Gestor de Empresa.
     - Mentor.
     - Estudante.

2. **Gestão de Trilhas e Desafios (para o MVP, via seed ou interface simples)**
   - Estrutura básica:
     - Programa → Trilha → Módulos/Marcos → Desafios.
   - Capacidade de:
     - Visualizar trilha e marcos.
     - Associar desafios a marcos.

3. **Submissão de Desafios (Estudante)**
   - Listagem dos desafios da trilha.
   - Seleção de um desafio.
   - Envio de uma entrega:
     - Link (ex: GitHub, replit).
     - Opcional: upload de arquivo (podendo usar Azure Blob Storage).
   - Armazenamento da submissão com:
     - Estudante, desafio, timestamp, status.

4. **Painel de Feedback (Mentor)**
   - Lista de entregas pendentes de avaliação.
   - Tela de avaliação com:
     - Status (aprovado, reprovado, em revisão).
     - Nota (escala definida).
     - Comentário textual (feedback qualitativo).
   - Registro de data/hora da avaliação para cálculo de **Lead Time de Feedback**.

5. **Dashboard de Métricas (Gestores/Mentores)**
   - Exibição dos **3 KPIs mandatórios**:
     1. **Lead Time de Feedback**:
        - Tempo médio entre submissão e feedback.
        - Visual por turma/trilha.
     2. **Taxa de Conclusão de Trilhas**:
        - % de estudantes que completaram os marcos da trilha dentro do prazo.
     3. **Saúde da Cobertura de Desafios**:
        - Desafios propostos vs desafios entregues com sucesso (aprovados).
   - Atualização **quase em tempo real** após cada avaliação de mentor.

6. **Snapshot de Performance por Estudante**
   - Tela/relatório individual contendo:
     - Progresso na trilha (% de marcos completados).
     - Histórico de desafios:
       - Entregues, aprovados, reprovados, em revisão.
     - Métricas pessoais:
       - Lead time médio de feedback (para suas entregas).
       - Taxa de aprovação em desafios.
     - Sinalização de “aluno pronto para contratação” (campo ou tag definida no futuro).

### 4.3 Fora do MVP (mas previstos na arquitetura)

- Autogestão avançada de empresas (self-service completo).
- Customização visual por marca (white-label).
- Fóruns complexos de discussão, mensagens em tempo real, etc.
- Relatórios avançados interprogramas e comparativos históricos.

---

## 5. Principais Funcionalidades — User Stories de Alto Nível

### 5.1 Estudante

- **US01 – Visualizar trilha**
  - Como **Estudante**, quero visualizar a trilha com seus marcos e desafios, para entender onde estou e o que falta completar.

- **US02 – Submeter desafio**
  - Como **Estudante**, quero submeter minha solução (link/arquivo) para um desafio específico, para que ela seja avaliada pelo mentor.

- **US03 – Acompanhar feedbacks**
  - Como **Estudante**, quero consultar o feedback (nota e comentários) de cada entrega, para entender como melhorar.

- **US04 – Ver meu snapshot de performance**
  - Como **Estudante**, quero ver um painel com minha evolução e métricas, para acompanhar meu crescimento e meu posicionamento na trilha.

### 5.2 Mentor Avanade

- **US05 – Ver desafios pendentes de avaliação**
  - Como **Mentor**, quero ver uma lista consolidada de entregas pendentes, para priorizar e manter o lead time de feedback baixo.

- **US06 – Avaliar uma entrega**
  - Como **Mentor**, quero avaliar uma entrega com status, nota e comentário, para orientar o estudante e alimentar as métricas.

- **US07 – Acompanhar saúde da turma**
  - Como **Mentor**, quero visualizar um painel da turma com KPIs, para ajustar ritmo, conteúdo e foco de mentoria.

### 5.3 Gestor de Empresa Parceira / Porto Digital

- **US08 – Ver dashboard de métricas da trilha**
  - Como **Gestor**, quero um dashboard com os KPIs (lead time, conclusão de trilhas, cobertura de desafios), para avaliar a eficácia do programa.

- **US09 – Consultar snapshot de um estudante**
  - Como **Gestor/Empresa Parceira**, quero acessar o perfil de performance de um estudante, para apoiar decisões de contratação.

### 5.4 Admin / Porto Digital (escopo simples para MVP)

- **US10 – Manter dados principais via interface simples ou seeds**
  - Como **Admin**, quero cadastrar/ajustar empresas, programas, trilhas e usuários (ou carregar via scripts), para preparar o ambiente da turma piloto.

---

## 6. Arquitetura Sugerida (Visão Inicial)

### 6.1 Stack Técnica Obrigatória (Avanade)

- **Frontend**: Angular.
- **Backend**: ASP.NET Core (C#) com Entity Framework Core.
- **Banco de Dados**: SQL Server.
- **Segurança**: Autenticação via JWT + ASP.NET Identity.
- **Cloud & DevOps**:
  - Azure App Service (API).
  - Azure Static Web Apps ou App Service para o frontend Angular.
  - Azure SQL Database.
  - Azure Blob Storage (para arquivos de submissão, se usado).
  - CI/CD via GitHub Actions ou Azure DevOps.

### 6.2 Visão de Arquitetura Lógica (Camadas)

- **Camada de Apresentação (Angular)**
  - SPA organizada por contextos:
    - Área do Estudante.
    - Área do Mentor.
    - Área de Gestão/Dashboard.
  - Comunicação com API via HTTP (REST + JSON).

- **Camada de API (ASP.NET Core)**
  - Endpoints organizados por domínios:
    - Auth/Identity.
    - Tenancy (empresa/programa/turma).
    - Trilhas & Desafios.
    - Submissões & Feedbacks.
    - Métricas & Dashboards.
  - Documentação com **Swagger / OpenAPI**.

- **Camada de Domínio / Aplicação**
  - Serviços de domínio para:
    - Cálculo de KPIs (Lead Time, Conclusão de Trilha, Cobertura de Desafios).
    - Regras de negócio de submissão e avaliação.
    - Respeito à separação multi-tenant.

- **Camada de Persistência (EF Core + SQL Server)**
  - Contexto de dados com mapeamentos multi-tenant (por exemplo: `TenantId` / `EmpresaId` e `ProgramaId` em entidades-chave).
  - Migrations para versionar o esquema.

### 6.3 Multi-Tenancy (Isolamento de Dados)

- **Estratégia sugerida para MVP**:  
  - Um único banco de dados lógico (Azure SQL) com **isolamento por coluna**:
    - Entidades centrais contendo:
      - `EmpresaId` (tenant).
      - `ProgramaId`.
      - `TurmaId` (quando aplicável).
  - Policies de acesso no backend:
    - O token JWT deve embutir o `Tenant/Empresa` e perfis.
    - Filtros globais no EF Core (Global Query Filters) para garantir que um usuário só enxergue dados de sua empresa/programa.

- **Regras de acesso**:
  - Admin Porto Digital: pode ver múltiplas empresas/programas.
  - Gestor de Empresa: vê apenas dados da sua empresa.
  - Mentor: vê apenas turmas/estudantes vinculados aos programas em que atua.
  - Estudante: vê apenas sua trilha/turma.

### 6.4 Visão de Implantação no Azure

- **Front-end Angular**
  - Deploy em:
    - Azure Static Web Apps (preferencial para SPA) ou
    - Azure App Service (servindo conteúdo estático).
- **API ASP.NET Core**
  - Deploy em Azure App Service.
  - Configuração de:
    - Connection string para Azure SQL.
    - Credenciais de Blob Storage (se necessário).
    - Variáveis de ambiente (chaves JWT, etc.).

- **Banco de Dados**
  - Azure SQL Database (uma instância inicial).
  - Uso de migrations EF Core para provisionamento.

- **Armazenamento de Arquivos (Opcional para MVP, mas recomendado)**
  - Azure Blob Storage para submissões de arquivos.
  - Apenas referência (URI) armazenada no SQL.

- **CI/CD**
  - Pipelines com GitHub Actions ou Azure DevOps:
    - Build + testes básicos.
    - Deploy automatizado para ambiente de demonstração.

---

## 7. Critérios de Aceite para o MVP

Um MVP será considerado **“full stack funcional”** para a apresentação final se:

1. **Autenticação & Perfis**
   - Usuários conseguem:
     - Registrar-se (ou serem provisionados).
     - Logar via JWT/Identity.
   - O sistema diferencia perfis (Estudante, Mentor, Gestor/Admin) e restringe o acesso corretamente.

2. **Fluxo Crítico do Ciclo de Feedback Funcional de Ponta a Ponta**
   - Estudante:
     - Acessa a trilha.
     - Visualiza um desafio.
     - Submete uma entrega (link/arquivo).
   - Mentor:
     - Visualiza essa entrega no painel de pendências.
     - Registra avaliação (status, nota, comentário).
   - Sistema:
     - Registra timestamps de submissão e avaliação.
     - Atualiza imediatamente o dashboard de métricas.

3. **Dashboard de Métricas Operando com Dados Reais**
   - O dashboard apresenta, ao menos para a turma piloto:
     - **Lead Time médio de Feedback** calculado dinamicamente.
     - **Taxa de Conclusão de Trilhas** (considerando marcos essenciais).
     - **Saúde da Cobertura de Desafios** (propostos vs aprovados).
   - Ao registrar um novo feedback, as métricas são atualizadas **quase em tempo real** (após refresh controlado da UI).

4. **Snapshot de Performance por Estudante**
   - Tela de perfil de estudante:
     - Mostra progresso na trilha.
     - Lista de desafios e status.
     - KPIs pessoais (pelo menos 1 ou 2 indicadores).
   - Acessível por:
     - Estudante (self-view).
     - Mentor/Gestor (para fins de avaliação/contratação).

5. **Arquitetura Multi-Tenant Preparada**
   - As entidades principais incluem campos de identificação de tenant/programa.
   - As consultas respeitam o isolamento de dados por empresa/programa.
   - É possível, ao menos via seed e configuração mínima, ter **mais de uma empresa/programa cadastrados sem conflito de dados**.

6. **Implantação em Azure**
   - Frontend e backend rodando em Azure (URL acessível).
   - Banco em Azure SQL.
   - Pipeline básico de deploy automatizado (ou minimamente reprodutível).

7. **Qualidade Mínima de Engenharia**
   - Código organizado em camadas.
   - Uso de migrations.
   - Tratamento básico de erros e respostas HTTP adequadas.
   - Documentação mínima da API (Swagger).

---

## 8. Desafios de Aprendizado e Pontos de Mentoria

### 8.1 Desafios Técnicos Prováveis

1. **Modelagem Multi-Tenant com EF Core**
   - Definição de entidades com chaves de tenant (Empresa, Programa).
   - Uso de Global Query Filters.
   - Controle de acesso por perfil e tenant.

2. **Autenticação e Autorização JWT/Identity**
   - Configuração correta de Identity.
   - Geração e validação de tokens JWT.
   - Inclusão de claims (perfil, tenant, programa) no token.
   - Uso de `[Authorize(Roles = ...)]` e policies.

3. **Cálculo e Exposição de Métricas**
   - Queries eficientes para:
     - Médias de tempo entre timestamps.
     - Taxas (%) agregadas por turma/trilha.
   - Considerações de performance (evitar N+1, agregações desnecessárias).

4. **Integração Angular + API**
   - Organização de serviços, interceptors de JWT.
   - Rotas protegidas por perfil.
   - Atualização de dashboards (pull periódico ou triggers de atualização).

5. **Deploy em Azure e CI/CD**
   - Configuração de App Service e Static Web Apps.
   - Connection strings e secrets.
   - Pipeline de build e deploy.

### 8.2 Onde a Mentoria Deve AtuAR Mais Fortemente

- **Design de Domínio e Modelagem de Dados Multi-Tenant**
  - Apoiar na definição de entidades:
    - Empresas, Programas, Trilhas, Turmas, Usuários, Desafios, Submissões, Feedbacks, etc.
  - Evitar acoplamentos desnecessários e “hardcoding” de trilhas.

- **Segurança (JWT/Identity)**
  - Hands-on com:
    - Registro de usuários e roles.
    - Customização de claims.
    - Proteção de endpoints.

- **Cálculo de Métricas e Boas Práticas de Consulta**
  - Orientar uso de LINQ e otimizações.
  - Ajuda em criar métodos de aplicação (Serviços) em vez de lógica espalhada em controllers.

- **DevOps e Azure**
  - Auxiliar na configuração inicial dos recursos Azure.
  - Guiar boas práticas de pipeline (GitHub Actions/Azure DevOps).

- **UX do Fluxo Crítico**
  - Validar se o fluxo Estudante → Mentor → Dashboard está:
    - Claro.
    - Rápido de usar.
    - Resiliente a erros comuns (falha de rede, input inválido, etc.).

---

## 9. Gaps, Riscos e Mitigações

### 9.1 Riscos de Produto

- **Complexidade excessiva para o tempo de 3 meses**
  - Risco: tentar implementar funcionalidades fora do escopo (forums, white-label, etc.).
  - Mitigação: foco radical no fluxo crítico e nos 3 KPIs.

- **Métricas imprecisas por modelagem inadequada**
  - Risco: dados de timestamps ou status incompletos.
  - Mitigação: garantir desde o início os campos de auditoria e estados bem definidos.

### 9.2 Riscos Técnicos

- **Dificuldade com JWT/Identity e roles**
  - Mitigação: mentoria prática, exemplos de código, documentação guiada.

- **Dificuldade com Azure/CI-CD**
  - Mitigação: templates de pipeline, sessões de pair programming com mentores.

---

## 10. Ideias e Oportunidades Futuras (Além do MVP)

1. **Gamificação leve**
   - Badges para conclusão de marcos.
   - Rankings internos (com cuidado pedagógico).

2. **Recomendações de Trilhas**
   - Sugestão de trilhas complementares com base em desempenho.

3. **Relatórios interprogramas (Porto Digital)**
   - Comparar performance de turmas, anos e empresas.

4. **Integrações externas**
   - GitHub, Azure DevOps, plataformas de coding challenges.

5. **Portal da Empresa Parceira**
   - Módulo dedicado para processos seletivos e acompanhamento de contratados.

---

## 11. Perguntas em Aberto (para ciclos futuros)

- Escala temporal das métricas: haverá necessidade, no futuro, de **históricos mais granulares** (por semana/mês)?
- Haverá regras específicas de **LGPD e retenção de dados** a considerar (ex.: exclusão de perfis antigos, anonimização)?
- Quais **templates visuais e guidelines** de UX/UI a Avanade deseja usar para reforçar cultura de excelência em design?

---

## 12. Compliance e Regulamentação

- **Dados tratados**: principalmente dados pessoais básicos (nome, e-mail, desempenho acadêmico/técnico).
- **Riscos potenciais**:
  - Dados de desempenho são sensíveis para a carreira dos estudantes.
- **Boas práticas sugeridas**:
  - Termos de uso e consentimento para utilização dos dados no contexto de empregabilidade.
  - Perfis de acesso bem delimitados (empresa só vê estudantes vinculados àquele programa).
  - Logs de quem acessa snapshots de estudantes (para auditoria futura, se necessário).

---

## 13. Síntese Orientadora

O **Trail** deve ser concebido como:

- **Um produto de educação corporativa orientado a dados**, não apenas uma lista de conteúdos.
- **Uma prova de conceito de arquitetura moderna full stack** (Angular + ASP.NET Core + Azure), com foco em:
  - Multi-tenancy desde a modelagem.
  - Segurança robusta com JWT/Identity.
  - Métricas de valor para o negócio (formação e contratação de talentos).

Se o time estudantil entregar um MVP que **execute sem falhas o Ciclo de Feedback e Visibilidade** (submissão → avaliação → atualização de KPIs) em ambiente Azure com isolamento básico de tenants, o objetivo deste primeiro ciclo de Discovery e mentoria terá sido plenamente alcançado.