# Análise Orçamentária do Governo de São Paulo
Os critérios para análise orçamentária do Governo do Estado de São Paulo, usando o Oracle Business Intelligence Enterprise Edition (OBIEE)

### Linguagem do Código

O código fornecido está em XML (Extensible Markup Language). XML é uma linguagem de marcação utilizada para definir documentos com uma estrutura que pode ser lida tanto por humanos quanto por máquinas. Ela é amplamente utilizada para a troca de dados entre sistemas diferentes.

### Função do Código

O código XML fornecido parece ser um relatório gerado por uma ferramenta de Business Intelligence (BI) chamada Oracle Business Intelligence (OBI), especificamente Oracle BI Answers. Esta ferramenta é usada para criar relatórios e dashboards a partir de dados armazenados em um banco de dados.

### Análise Detalhada do Código

O código define um relatório que busca informações orçamentárias do estado, extraídas do sistema SIGEO, um sistema da Secretaria da Fazenda, hospedado em um banco de dados Oracle.

#### Estrutura do Código

1. **Elemento `<saw:report>`**:
   - É o elemento raiz do documento XML do relatório.
   - Define namespaces (espaços de nomes) usados no relatório, como `saw`, `xsi`, `xsd`, e `sawx`.

2. **Elemento `<saw:criteria>`**:
   - Define os critérios para a busca de dados.
   - Atributos importantes:
     - `subjectArea`: Especifica a área temática do relatório. Neste caso, "SIGEO - Despesas Elemento".

3. **Elemento `<saw:columns>`**:
   - Lista as colunas que serão incluídas no relatório.
   - Cada coluna é definida por um elemento `<saw:column>`, que inclui:
     - `columnID`: Um identificador único para a coluna.
     - `<saw:columnFormula>`: Define a fórmula da coluna, que é uma expressão SQL.
     - `<saw:displayFormat>` (opcional): Especifica o formato de exibição da coluna.

4. **Elemento `<saw:filter>`**:
   - Define os filtros aplicados aos dados.
   - Exemplo de filtro:
     ```xml
     <sawx:expr xsi:type="sawx:comparison" op="equal">
       <sawx:expr xsi:type="sawx:sqlExpression">"Gestões"."Código Nome Gestão"</sawx:expr>
       <sawx:expr xsi:type="xsd:string">08046 - FUNDACAO PARA O DESENVOLVIMENTO DA EDUCACAO</sawx:expr>
     </sawx:expr>
     ```
     Este filtro seleciona registros onde a coluna "Código Nome Gestão" é igual a "08046 - FUNDACAO PARA O DESENVOLVIMENTO DA EDUCACAO".

5. **Elemento `<saw:views>`**:
   - Define as visualizações do relatório.
   - Exemplos de visualizações:
     - `<saw:compoundView>`: Uma visualização composta.
     - `<saw:titleView>`: Define o título do relatório.
     - `<saw:tableView>`: Define a visualização em tabela.

6. **Elemento `<saw:prompts>`**:
   - Define os prompts (filtros interativos) para o relatório.

### Conclusão

Esse XML é um relatório configurado para buscar e exibir informações orçamentárias específicas do sistema SIGEO. Ele utiliza expressões SQL para definir as colunas e filtros, e organiza a exibição dos dados em uma tabela. O relatório é voltado para a gestão de despesas orçamentárias, detalhando informações como "Dot Inic no Mês", "Cred Emp no Mês", "Liquidado no Mês", entre outros.
