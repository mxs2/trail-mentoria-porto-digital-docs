# Encontro 02 — Problema Real e Requisitos do MVP

> **Status:** Encontro realizado  
> **Contexto:** Continuação do Kickoff (Encontro 01)  
> **Frequência:** Encontros semanais  

---

## 🎯 Objetivo do Encontro

Transformar o **Documento de Briefing do Projeto Trail** em um **problema bem definido e validado**, estabelecendo **requisitos claros para o MVP**, com foco absoluto em:

- Resolver uma dor real (não apenas construir software)
- Criar alinhamento entre todos os participantes
- Evitar escopo inflado e soluções vagas

Ao final deste encontro, todos devem responder com clareza:

> **“Que problema exatamente estamos resolvendo, para quem, e qual é o mínimo que precisamos entregar para gerar valor?”**

---

## 📄 Documento de Referência — Fonte Única da Verdade

Este encontro é fundamentado no **Documento de Briefing / Discovery do Projeto Trail**.

📌 **Regra essencial do projeto:**

> O documento de briefing é a **fonte única da verdade** para entendimento do problema, visão do produto e objetivos do projeto.

Todas as decisões deste encontro devem:
- Partir do briefing
- Estar alinhadas ao briefing
- Ou justificar explicitamente qualquer recorte ou adaptação feita

⚠️ O objetivo **não é reescrever o briefing**, mas **interpretá‑lo criticamente** para definir o MVP.

---

## 🧠 Conceito‑chave do Encontro

> **Não existe MVP sem problema bem formulado.**

Um MVP:
- Não é uma versão pequena do produto final
- É uma **hipótese de valor**
- Validada com o **mínimo de funcionalidade possível**
- Para um **público específico**

---

## 🔍 Problema no Briefing vs. Problema a Ser Resolvido no MVP

O briefing descreve contexto, visão e objetivos amplos.  
A partir dele, o time deve responder:

> **“Qual é o problema central que PRECISA ser resolvido primeiro?”**

Nem tudo que está no briefing é MVP.  
Nem tudo que é desejável é essencial agora.

---

### Problema Declarado (superficial)

> “Não existe uma ferramenta centralizada para gerenciar trilhas, desafios e mentorias.”

✅ Verdadeiro, porém **genérico**.

---

### Problema Real (extraído do briefing)

Hoje, programas de formação em TI sofrem porque:

- Não existe **visibilidade clara do progresso dos estudantes**
- Feedbacks de mentoria são **tardios, não rastreáveis e não mensuráveis**
- Empresas parceiras **não conseguem avaliar performance real**
- Mentores gastam tempo organizando informações, não mentorando

👉 O problema **não é apenas falta de ferramenta**  
👉 O problema é **falta de fluxo, métricas e governança**

---

## 🧭 Leitura Crítica do Briefing (Responsabilidade do Time)

O briefing deve ser analisado sob três lentes:

1. **Problema real**
2. **Soluções propostas**
3. **Visão futura**

Durante a mentoria:
- Problemas reais alimentam o MVP
- Soluções propostas podem ser adaptadas
- Visão futura **não define escopo imediato**

📌 Tudo que entra no MVP deve estar ancorado no briefing  
📌 Nem tudo que está no briefing entra no MVP

---

## 👥 Personas Envolvidas

### 1️⃣ Estudante

**Busca:**
- Entender sua jornada
- Saber o que entregar
- Receber feedback rápido

**Dor principal:**
> “Entrego atividades, mas não sei se estou indo bem nem onde melhorar.”

---

### 2️⃣ Mentor

**Busca:**
- Visualizar pendências
- Avaliar entregas rapidamente
- Acompanhar evolução

**Dor principal:**
> “Perco tempo organizando entregas em vez de orientar tecnicamente.”

---

### 3️⃣ Gestor / Empresa Parceira

**Busca:**
- Avaliar desempenho
- Identificar talentos
- Medir eficácia do programa

**Dor principal:**
> “Não tenho dados confiáveis para tomar decisões.”

---

## 🧩 O Que NÃO é o MVP (Delimitação Clara)

🚫 Não faz parte do MVP:

- Chat em tempo real ou fórum
- Gamificação avançada
- Customização visual por empresa
- Funcionalidades administrativas complexas

👉 Tudo isso pode existir no futuro, **não agora**

---

## ✅ Requisitos Funcionais do MVP

### RF‑01 — Autenticação e Perfis
- Autenticação de usuários
- Perfis: Estudante, Mentor, Gestor/Admin

---

### RF‑02 — Visualização da Trilha
- Visualização da trilha
- Módulos/marcos
- Desafios associados

---

### RF‑03 — Submissão de Desafios
- Seleção de desafio
- Submissão de entrega (link ou arquivo)
- Status visível da entrega

---

### RF‑04 — Avaliação e Feedback
- Visualização de entregas pendentes
- Avaliação com:
  - Status
  - Nota
  - Comentário
  - Data/hora

---

### RF‑05 — Métricas e Indicadores
- Lead Time de Feedback
- Taxa de Conclusão da Trilha
- Cobertura de Desafios

---

### RF‑06 — Snapshot do Estudante
- Progresso na trilha
- Histórico de desafios
- Métricas básicas

---

## ⚙️ Requisitos Não Funcionais Essenciais

- Preparação para multi‑tenant
- Perfis e permissões bem definidos
- Auditoria mínima (timestamps)
- Código versionado
- Documentação obrigatória

---

## 🏠 Atividades ENTRE ENCONTROS (Entrega Obrigatória)

Estas atividades devem ser realizadas **até o próximo encontro**  
e utilizam o **Documento de Briefing como fonte principal**.

---

### ✅ Atividade 01 — Extração do Problema a partir do Briefing

**Entrega:**
- Problema central identificado
- Público‑alvo principal
- Dor mais crítica
- Evidência no briefing

---

### ✅ Atividade 02 — Derivação de Requisitos do MVP

Tabela:

| Requisito derivado do briefing | É MVP? | Justificativa |
|------------------------------|:--------:|---------------|
| Autenticação e controle de acesso por perfil | ✅ Sim | Sem autenticação não há separação de papéis nem segurança básica |
| Chat em tempo real entre mentor e estudante | 🚫 Não | Comunicação pode ocorrer por outros canais; adiciona complexidade sem ser core |

---

### ✅ Atividade 03 — Requisito → Persona → Valor

Tabela:

| Requisito | Persona impactada | Problema que resolve |
|----------|:-----------------:|----------------------|
| Autenticação com perfis (Estudante, Mentor, Gestor) | Todos | Garante que cada ator acesse apenas o que é relevante para seu papel |

---

### 📦 Formato da Entrega

- Arquivo único em Markdown
- Nome sugerido:
    `atividade-02-requisitos-mvp.md`


---

### ✅ Critério de Aceite

- Briefing corretamente interpretado
- MVP claramente delimitado
- Nenhum requisito sem problema associado

---

## 🔗 Próximo Encontro

➡️ **Encontro 03 — Backlog e Priorização**  
Os artefatos deste encontro serão **insumo direto** para o backlog.

---

> **Lembrete:**  
> Bons produtos começam com bons problemas.  
> MVP é foco, não volume.