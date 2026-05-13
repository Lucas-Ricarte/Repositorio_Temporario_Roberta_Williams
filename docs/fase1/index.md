# Fase 1: Planejamento da Avaliação

Esta página unifica todos os tópicos da Fase 1, fornecendo uma visão completa e contínua do planejamento da avaliação de qualidade. Utilize o menu de navegação lateral para pular rapidamente para qualquer seção (âncoras).

---

## 1. Requisitante e partes interessadas
[Inserir texto aqui]

---

## 2. Descrição estruturada do software
[Inserir texto aqui]

---

## 3. Classificação do tipo de produto
[Inserir texto aqui]

---

## 4. Propósito da avaliação e uso pretendido dos resultados

**Propósito da avaliação:**
O principal propósito desta avaliação é essencialmente didático e pedagógico, focado na aplicação prática das técnicas de avaliação de qualidade de produto de software estabelecidas pelos modelos e normas da família SQuaRE. Por meio dessa execução, a equipe avaliadora busca desenvolver e aprimorar suas capacidades críticas e analíticas ao analisar um sistema real. A avaliação visa não apenas evidenciar os pontos fortes da arquitetura do sistema , mas também mapear e expor suas vulnerabilidades atuais.

**Uso pretendido dos resultados:**
Os dados e diagnósticos obtidos com a avaliação serão utilizados em duas frentes principais. Primeiramente, servirão para que a própria equipe de avaliação consolide seu aprendizado prático em engenharia de software, adquirindo proficiência na condução de avaliações de qualidade formais. Em segundo lugar, os resultados fornecerão um diagnóstico claro e acionável para a equipe de desenvolvimento do Mural UnB, servindo como um roteiro de melhoria contínua para futuros colaboradores do projeto. A expectativa é que essas descobertas permitam reforçar as boas práticas já existentes e mitigar as falhas identificadas, fazendo com que o projeto vá além do seu fim puramente didático e contribua ativamente para a evolução do Mural UnB como uma ferramenta open source útil, segura e sustentável para a comunidade acadêmica da universidade.

---

## 5. Modelo de Qualidade e Escopo

### 5.1 Modelo de Qualidade e Escopo

O modelo adotado é o **Modelo de Qualidade de Produto SQuaRE (ISO/IEC 25010)**. O escopo desta avaliação concentra-se na plataforma **Mural UnB**, um sistema voltado para a centralização e disseminação de informações acadêmicas. O objetivo é garantir que a plataforma seja tecnicamente robusta e segura para os estudantes.

### 5.2 Introdução e Seleção de Características

A qualidade é definida como grau em que o sistema satisfaz requisitos especificados e as necessidades dos usuários. Para esta avaliação foram selecionadas as seguintes características:

1. **Confiabilidade (Reliability)**: Define o grau em que o sistema executa funções específicas sob condições estabelecidas por um período de tempo.
2. **Segurança (Security)**: Fundamental para proteger os dados e as informações contra acessos e modificações não autorizadas.

**Nota**: A característica "Usabilidade" foi excluída conforme solicitado, apesar de sua importância em sistemas de mural, para focar na integridade e disponibilidade dos dados.

### 5.3 Diagrama e Justificativa de Priorização
O diagrama abaixo foca na hierarquia das qualidades selecionadas para o Mural UnB:

![diagrama](../imagem/Diagrama.jpeg)

> Qualidade de Produto SQuaRE (ISO/IEC 25010) com as duas características prioritárias para a Fase 1

* **SQuaRE (ISO/IEC 25010)**

    * **Confiabilidade**
        * Subcaracterísticas: Maturidade, Disponibilidade, Tolerância a Falhas, Recuperabilidade.

    * **Segurança**
        * Subcaracterísticas: Confidencialidade, Integridade, Não-repúdio, Responsabilidade, Autenticidade.

A justificativa de priorização reside no fato de o Mural UnB lidar com avisos oficiais e horários. A **Confiabilidade** é prioritária para garantir que o serviço não fique indisponível durante períodos críticos (como a matrícula). Enquanto a **Segurança** é essencial para evitar que usuários não autorizados alterem informações públicas, o quê causaria desinformação na comunidade acadêmica. A Usabilidade foi excluída para focar na base técnica.

### 5.4 Escopo da Avaliação

A avaliação será limitada ao backend (API), que gerencia o feed de notícias e a persistência dos dados no banco de dados. Ao passo que a profundidade será o Nível 3 (Análise detalhada das subcaracterísticas por meio de métricas derivadas e propriedades mensuráveis). Ressalte-se que fora de escopo existe a interface do usuário (Front-end), performance em dispositivos móveis específicos e portabilidade para outros sistemas operacionais, porque o foco inicial é a estabilidade do núcleo da informação antes de validar a experiência estética.

### 5.5 Adaptação do Modelo

O modelo SQuaRE (ISO/IEC 25010) original foi adaptado para ignorar as visões de "Manufatura" (concentrada em processos internos de codificação) e pela ideia de focar estritamente na **Visão do Produto** e **Visão do Usuário** no que tange à confiança na informação. A qualidade é um conceito complexo e altamente dependente do domínio e contexto de uso. As características são selecionadas por meio da fórmula: **Prioridade = Peso × (Impacto × Risco)**. Isso permite focar nos riscos críticos da persona, evitando avaliações exaustivas de subcaracterísticas de baixo valor para o objetivo específico. A seleção considera que a melhoria de um fator (como usabilidade ou flexibilidade) pode reduzir outros (como a eficiência do software) (Trade-offs – compromissos -).

#### Escopo, Artefatos e Profundidade

**Breve Escopo:**
A avaliação concentra-se nos módulos de backend e persistência do **Mural UnB**, especificamente a API que gerencia o feed de notícias e a lógica de autenticação de usuários. O objetivo é garantir a robustez técnica e a proteção contra falhas críticas que possam comprometer a disseminação de informações acadêmicas oficiais.

**Tipos de Arquivo e Artefatos de Evidência:**
Para fundamentar a avaliação, são utilizados artefatos que comprovam o atendimento aos requisitos:

* **Documentação Técnica**: Arquivos em **.pdf** e **.md** contendo diagramas BPMN, tabelas 5W2H e diagramas de classe UML.
* **Código-Fonte e Scripts (.cpp, .py)**: Scripts **Python** de comunicação e arquivos C++ para algoritmos de processamento. Algoritmos de ordenação de notícias e scripts de comunicação serial para hardware integrado (Raspberry Pi).
* **Planejamento de Testes (.xlsx)**: Planilhas de medição baseadas no método **GQM (Goal Question Metric)** e Abstraction Sheets, Matrizes de Rastreabilidade.
* **Registros de Execução**: Logs de monitoramento de servidor e relatórios de vulnerabilidades.

**Níveis de Profundidade da Avaliação:** A profundidade segue a estrutura de variáveis identificadoras da qualidade proposta pela SQuaRE:

* **Nível 1 (Identificação)**: Identificação do conjunto de propriedades, juntas, que cobrem a subcaracterística (ex: contagem de bugs por linha de código).
* **Nível 2 (Medição)**: Obtenção de medidas de qualidade específicas para cada propriedade identificada por meio de testes e métricas estáticas.
* **Nível 3 (Integração)**: Combinação computacional das medidas anteriores para chegar a uma medida de qualidade derivada correspondente à subcaracterística avaliada (ex: índice final de disponibilidade).

### 5.6 Classificação de Subcaracterísticas (Escala 1 a 5)

#### Confiabilidade (Reliability)

**Definição**: Mede o grau em que um sistema, componente ou processo executa funções específicas sob condições estabelecidas por um período de tempo determinado.

**Classificação das Subcaracterísticas do modelo SQuaRE (ISO/IEC 25010):**

| Subcaracterística | Ênfase (1-5) | Definição Breve | Justificativa Curta |
| :--- | :---: | :--- | :--- |
| **Disponibilidade** | 5 | Grau em que o sistema está operacional e acessível. | Vital para que o Mural UnB esteja acessível em períodos críticos de matrícula. |
| **Maturidade** | 3 | Atendimento das necessidades de confiabilidade em operação normal. | Relevante para estabilidade a longo prazo após a fase inicial de lançamento. |
| **Tolerância a Falhas** | 4 | Capacidade de manter a operação pretendida mesmo com falhas de HW/SW. | Importante para evitar quedas totais por erros pontuais no backend. |
| **Recuperabilidade** | 4 | Capacidade de recuperar dados e o estado operacional após interrupção. | Essencial para garantir a persistência das notícias após quedas de servidor. |

#### Segurança (Security)

**Definição**: A segurança foca na proteção das informações e dados para garantir que apenas pessoas autorizadas acessem os dados.

**Classificação das Subcaracterísticas do modelo SQuaRE (ISO/IEC 25010):**

| Subcaracterística | Ênfase (1-5) | Definição Breve | Justificativa Curta |
| :--- | :---: | :--- | :--- |
| **Integridade** | 5 | Prevenção de acesso ou modificação não autorizada de dados. | Crítica para impedir que notícias falsas sejam publicadas por terceiros. |
| **Autenticidade** | 5 | Identidade de um sujeito ou recurso pode ser provada como tal. | Garante que apenas administradores autorizados enviem feeds ao mural. |
| **Confidencialidade** | 3 | Garante que os dados sejam acessíveis apenas por quem tem autorização. | Menos prioritária, pois a maioria das notícias acadêmicas são públicas. |
| **Responsabilidade** | 4 | Ações de uma entidade podem ser rastreadas exclusivamente àquela entidade. | Necessária para auditoria interna de quem publicou cada aviso. |
| **Não-repúdio** | 3 | Prova de que um evento ou ação ocorreu, para que não seja negado posteriormente. | Importante para validade jurídica de editais e avisos oficiais. |

No tocante aos Níveis de Profundidade, as Subcaracterísticas com nível 5 exigirão testes de estresse (Disponibilidade) e testes de invasão/SQL Injection (Integridade). As de Níveis 3 e 4 envolverão apenas análise documental e revisões de código. Este método avalia dois eixos fundamentais, quais sejam, o de impacto, que é a magnitude das consequências negativas para o Mural  UnB e seus usuários caso a subcaracterística falhe (exemplo: desinformação em massa) e o de risco (probabilidade), que é  a chance de uma ameaça explorar uma vulnerabilidade do sistema, considerando o ambiente de uso e histórico de falhas.

### 5.7 Matriz de Priorização (Ponderada)

A priorização utiliza uma escala de 0 a 5 para Impacto e Risco, multiplicada pelo peso da característica.

| Subcaracterística | Peso | Impacto | Risco | Total (P×I×R) | Prioridade |
| :--- | :---: | :---: | :---: | :---: | :--- |
| **Integridade** | 9 | 5 | 5 | 225 | **Crítica** |
| **Disponibilidade** | 10 | 5 | 4 | 200 | **Alta** |
| **Autenticidade** | 9 | 4 | 4 | 144 | **Alta** |
| **Recuperabilidade** | 10 | 3 | 3 | 90 | **Média** |
| **Confidencialidade** | 9 | 2 | 2 | 36 | **Baixa** |

### 5.8 Método de Priorização

O método adotado é a Priorização Quantitativa Ponderada. Este método calcula a relevância de cada subcaracterística através da fórmula:

    Prioridade = Peso da Característica X (Impacto X Risco)

O peso define a importância estratégica da característica para o negócio (Confiabilidade = 10; Segurança = 9). Enquanto o impacto (0-5) avalia a gravidade da falha para o usuário final. E o risco (0-5) avalia a probabilidade de ocorrência de falhas ou vulnerabilidades no contexto atual do sistema. Essa abordagem permite um critério de Go/No-Go fundamentado, focando os esforços de teste nos pontos de maior risco sistêmico.

---

## 6. Seleção de características de qualidade (SQuaRE)
- **Característica 1:** [Inserir nome da Característica, ex: Segurança]
- **Característica 2:** [Inserir nome da Característica, ex: Desempenho]

---

## 7. Escopo, profundidade e objetos de avaliação
[Inserir texto aqui]

---

## 8. Sustentabilidade (ODS e metas)
[Inserir texto aqui]

---

## 9. Referências de rastreabilidade (entregas e auditoria)
Links importantes para validação do professor.

- **Link da GitPage:** [Inserir link]
- **Link do Repositório Git:** [Inserir link]
- **Link da Release (EU1):** [Inserir link da tag/release]
- **Link para Dados Brutos/Gravações:** [Inserir link do repositório onde estão as entrevistas/dados auditáveis, se aplicável]

---

## 10. Tabela de contribuição da equipe

| Nome / ID do integrante | Papel / atividades realizadas na fase 1 | Esforço/participação |
| :--- | :--- | :--- |
| XXX | XXX | XXX |
| XXX | XXX | XXX |
| XXX | XXX | XXX |
| XXX | XXX | XXX |
| XXX | XXX | XXX |
| XXX | XXX | XXX |
