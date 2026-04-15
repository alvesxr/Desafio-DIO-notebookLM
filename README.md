# 📊 Guia de Programabilidade SQL com IA Ativa

Este repositório foi desenvolvido para o desafio de projeto da **DIO**, demonstrando como utilizei o **NotebookLM** para potencializar meus estudos em Banco de Dados Relacional. O foco aqui é a "aprendizagem ativa": usar a IA para investigar erros, comparar lógicas e criar materiais de revisão personalizados.

---

## 🚀 Contexto e Objetivos

O projeto consolida os conceitos de programabilidade *server-side* em SQL. Saí das consultas simples para entender como o banco de dados pode automatizar processos e garantir a integridade dos dados através de lógica avançada.

**Meus principais objetivos foram:**
- Dominar a **Teoria dos Conjuntos** aplicada às junções (`JOINs`).
- Entender a fundo o funcionamento de **Functions** e **Stored Procedures**.
- Aprender a resolver erros comuns de execução no SGBD (MariaDB/MySQL).

---

## 📚 Curadoria de Fontes

Utilizei como base os materiais técnicos da FATEC Araras (Prof. Nilton), focando nos seguintes pilares:
1. **Junções Relacionais**: Teoria de conjuntos e Diagramas de Venn.
2. **Subconsultas**: Consultas aninhadas e operadores lógicos (`EXISTS`, `IN`).
3. **Functions (UDF)**: Criação de funções de valor único.
4. **Stored Procedures**: Automação de rotinas e uso de parâmetros `IN`, `OUT` e `INOUT`.

---

## 🛠️ Engenharia de Prompts e "Cicatrizes"

O diferencial deste projeto é a documentação do raciocínio técnico e a resolução de problemas reais encontrados durante o estudo.

### 🔍 Investigação: Lógica de Exclusão
**Desafio:** Entender como remover a interseção entre duas tabelas.
- **Resultado:** Através da IA, entendi que o SQL não possui um comando `LEFT EXCLUDING`. A solução é usar um `LEFT JOIN` com um filtro `WHERE b.Chave IS NULL`. Isso "limpa" o resultado, deixando apenas o que é exclusivo da tabela à esquerda.

### 🔍 Troubleshooting: O Erro 1242
**Desafio:** Por que minha Function travava ao retornar dados?
- **Resultado:** A IA identificou que subconsultas dentro de Functions precisam retornar um valor escalar único. O Erro 1242 acontece quando a query retorna várias linhas. A solução foi aplicar o `LIMIT 1` para garantir que a função receba exatamente o que precisa.

### 🔍 Comparação Técnica: EXISTS vs IN
**Desafio:** Qual operador usar para performance?
- **Resultado:** Documentei que o `EXISTS` é um verificador booleano (para assim que acha um resultado), enquanto o `IN` compara valores contra uma lista. Essa distinção é crucial para otimizar queries em grandes volumes de dados.

---

## 📖 Miniguia de Estudo (Resultado Final)

### 1. Resumo Técnico
- **Joins**: Conectam dados baseados em relacionamentos.
- **Functions**: Processam dados e retornam um resultado (utilizadas em `SELECT`).
- **Procedures**: Executam sequências de comandos no servidor, economizando tráfego de rede.

### 2. Glossário de Especialista
- **Deterministic**: Funções que sempre dão o mesmo retorno para a mesma entrada.
- **Delimiter**: Comando para trocar o finalizador de instruções, permitindo criar Procedures sem erros de sintaxe.
- **INOUT**: Parâmetro que entra com um valor, é processado e devolve um novo resultado na mesma variável.

### 3. Ferramentas de Revisão Geradas
Para fixar o conteúdo, utilizei os recursos do NotebookLM para criar:
- **SQL Flashcards**: Para memorização de sintaxe.
- **Quiz Técnico**: Testes de múltipla escolha para validar o aprendizado sobre parâmetros e subconsultas.

---
Desenvolvido por **João Rafael Alves Recco**
*Junior Full-Stack Developer & Estudante de ADS (FATEC Araras)*
