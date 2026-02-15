# Documentação de Estrutura: Dashboard-excel.xlsx

O **Dashboard-excel.xlsx** é uma ferramenta analítica construída sob a arquitetura clássica de dashboards profissionais. Ele separa rigorosamente a entrada de dados, o processamento lógico e a interface visual em abas (planilhas) distintas. 

Essa separação garante que a ferramenta seja rápida, fácil de atualizar e protegida contra exclusões acidentais de fórmulas.

---

## Estrutura das Abas (Arquitetura)

### 1. Aba: `B̳ases` (Banco de Dados / Back-end)
**Objetivo:** É o repositório central de dados brutos ("raw data").
* **Função:** Receber os dados colados, importados ou extraídos de outros sistemas. 
* **Regra de Ouro:** Esta aba não deve conter gráficos ou formatações complexas, apenas dados tabulares puros (linhas e colunas) para maximizar a performance.

### 2. Aba: `C̳álculos` (Processamento / Motor)
**Objetivo:** Atuar como o "motor" analítico da planilha.
* **Função:** É aqui que a mágica acontece. Esta aba puxa os dados da aba `B̳ases` e os resume usando Tabelas Dinâmicas, fórmulas de agregação (como `SOMASES`, `CONT.VALORES`) e lógicas matemáticas.
* **Estrutura:** (Inicia após a 1ª linha) Contém as tabelas auxiliares que alimentam diretamente os gráficos do painel final.

### 3. Aba: `A̳ssets` (Recursos Visuais e Apoio)
**Objetivo:** Armazenar os elementos estruturais e de design.
* **Função:** Guarda paletas de cores, ícones, logotipos, formas personalizadas ou até mesmo pequenas listas de referência (como menus suspensos) que apoiam o visual da ferramenta.
* **Estrutura:** Geralmente possui um layout mais livre (notado pelas 11 linhas em branco antes de qualquer cabeçalho no arquivo).

### 4. Aba: `D̳ashboard` (Painel / Front-end)
**Objetivo:** A interface visual final para o usuário e tomada de decisão.
* **Função:** Exibir os Indicadores-Chave de Desempenho (KPIs), gráficos interativos e Segmentadores de Dados (filtros). 
* **Regra de Ouro:** Não deve conter dados brutos ou cálculos complexos. Tudo o que é exibido aqui é um reflexo visual direto da aba `C̳álculos`.
