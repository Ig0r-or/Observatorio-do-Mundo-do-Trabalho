# 🌐 Observatório do Mundo do Trabalho
 
**Plataforma de conexão entre estudantes e empregadores, com arquitetura de dados institucional para o IFSULDEMINAS**
 
![Status](https://img.shields.io/badge/status-em%20produção-brightgreen)
![Stack](https://img.shields.io/badge/stack-Google%20Cloud%20Ecosystem-blue)
 
---
 
## 📌 Contexto do Problema
 
O IFSULDEMINAS possui 9 campi (Carmo de Minas, Inconfidentes, Machado, Muzambinho,
Poços de Caldas, Pouso Alegre, Passos e Três Corações, Itajuba), oferecendo mais de 159 cursos
técnicos. Antes deste projeto, não havia um canal centralizado que conectasse:
 
- **Estudantes/egressos** buscando estágio, emprego ou Jovem Aprendiz
- **Empresas empregadoras** buscando talentos qualificados
- **Gestão institucional** precisando de indicadores de empregabilidade para tomada de decisão
**Objetivo do projeto:** projetar e implementar uma plataforma digital que resolvesse
essas três necessidades simultaneamente, com transparência jurídica e dados
estruturados para análise institucional.
 
---
 
## 🏗️ Arquitetura da Solução
 
```
┌─────────────────┐     ┌──────────────────┐     ┌─────────────────────┐
│  Google Forms    │ --> │  Google Sheets    │ --> │   Google Data Studio   │
│  (Coleta)         │     │  (Armazenamento)   │     │   (BI/Visualização)  │
└─────────────────┘     └──────────────────┘     └─────────────────────┘
      │                         │                          │
 Currículos,              Banco de dados               Indicadores de
 cadastro de vagas,       principal (planilhas          egressos e
 preferências de          estruturadas)                  empregabilidade
 empresas
```
 
**Por que essa stack?**
Optei pelo ecossistema Google por três razões práticas: (1) infraestrutura já
disponível e sem custo adicional para a instituição pública, (2) baixa barreira
de adoção para usuários não-técnicos (equipe da Pró-Reitoria), e (3) integração
nativa entre Forms → Sheets → Looker sem necessidade de ETL customizado.
 
**Limitação conhecida e evolução proposta:**
Google Sheets como banco de dados principal não escala bem para volumes grandes
de dados nem garante integridade referencial. Uma evolução natural seria migrar
a camada de armazenamento para BigQuery, mantendo Looker como camada de
visualização (troca direta, sem re-arquitetar todo o pipeline).
 
---
 
## 👥 Funcionalidades por Usuário
 
### Para o Estudante
- Cadastro de currículo e visibilidade para empresas parceiras
- Modelos de currículo para download
- FAQ e orientação sobre o mercado de trabalho
- Transparência sobre normas jurídicas de estágio (Estágio, Jovem Aprendiz, Trainee)
### Para o Empregador
- Acesso ao Banco de Talentos com filtro por preferências
- Publicação individual de vagas
- Transparência sobre legislação aplicável ao estágio
### Para a Gestão (Pró-Reitoria de Extensão)
- Dashboards de indicadores de empregabilidade e egressos via Looker
- Visão consolidada dos 9 campi
- Dados brutos transformados em relatórios acionáveis
---
 
## 🛠️ Meu Papel no Projeto
 
- Arquitetei o fluxo de dados ponta a ponta (coleta → armazenamento → BI),
  aplicando princípios de Data Warehouse em um ambiente de baixo custo.
- Estruturei o modelo de dados no Google Sheets para suportar as consultas
  necessárias no Looker sem retrabalho manual.
- Construí os dashboards de indicadores estratégicos (egressos, empregabilidade)
  no Google Data Studio (antigo Looker Studio).
- Documentei as normas jurídicas de estágio para garantir conformidade e
  transparência entre as partes.
---
 
## 📊 Resultados / Impacto Esperados
 
- Atender estudantes de **9 campi** do Sul de Minas
- Cobertura de mais de **159 cursos técnicos**
- Centralizar dados que antes eram dispersos entre campi
---
 
## 🧠 Aprendizados Técnicos
 
- Como aplicar conceitos de arquitetura de dados (Data Warehouse) mesmo sem
  infraestrutura de banco de dados tradicional
- Trade-offs entre velocidade de implementação (Google ecosystem) vs.
  escalabilidade de longo prazo (necessidade futura de BigQuery)
- Design de pipeline pensando em múltiplos públicos (estudante, empresa, gestor)
  com necessidades de dados diferentes
---
 
## 🔗 Links Relacionados
 
- [Veja Tabela de Conveniências de Empresas - Instituto Federal no Data Studio](https://lookerstudio.google.com/embed/reporting/2f9b555c-7f38-472f-9a86-a0cb6005059d/page/A)
- [Veja Banco de Talentos-Instituto Federal no Data Studio](https://lookerstudio.google.com/reporting/c4ba7233-ec65-49ed-b70e-c0268d60215b)
---
 
## 📁 Stack Técnica
 
`Google Forms` `Google Sheets` `Google Looker Studio` `Arquitetura de Dados` `Data Warehouse`
