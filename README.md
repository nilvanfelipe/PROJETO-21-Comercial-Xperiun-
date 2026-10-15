# Dashboard Comercial — Xperiun (Power BI)

> Projeto de portfólio de análise de dados comerciais, desenvolvido em Power BI a partir de um business case educacional da Xperiun/Data Expert.

**Status:** concluído.

---

## 1. Problema de negócios

### Contexto

A Xperiun é uma empresa de consultoria em software, BI, Dados e IA que atende empresas de todos os portes. A gestão comercial precisava de uma visão consolidada do desempenho de vendas para responder a perguntas como:

- A receita está atingindo as metas definidas?
- Qual é a margem de lucro da operação?
- Quais vendedores e produtos se destacam?
- Qual é o perfil de clientes ativos e inativos?
- Onde estão as maiores oportunidades de crescimento?

Sem um painel centralizado, essas respostas dependiam de planilhas manuais, dificultando a tomada de decisão em tempo hábil.

### Objetivo

Criar um relatório de performance comercial que permita à liderança acompanhar receita, custos, margem, metas e desempenho da equipe de vendas de forma visual e interativa.

---

## 2. Planejamento da solução

### Fontes de dados

| Fonte | Conteúdo |
|---|---|
| `Base de Dados.xlsx` | Registros de vendas, clientes, produtos e vendedores |
| `Base_de_Dados_com_Metas.xlsx` | Metas comerciais por período |

### KPIs definidos

| Indicador | Descrição |
|---|---|
| Receita Total vs Meta | Comparação entre o realizado e o planejado |
| Custo Total | Soma dos custos operacionais do período |
| Margem de Lucro | (Receita − Custo) / Receita |
| Ticket Médio | Receita / Número de vendas |
| Número de Clientes | Contagem distinta de clientes no período |
| % Clientes Ativos | Clientes com compra no período / total de clientes |

### Páginas do relatório

| Página | Pergunta que responde |
|---|---|
| Performance Comercial | Qual o panorama geral de receita, custo e margem? |
| Análise de Vendedores | Quem são os vendedores com melhor e pior desempenho? |
| Análise de Desempenho | Como os resultados evoluem ao longo do tempo? |

### Design

O dashboard foi desenvolvido com duas versões de tema (light e dark), seguindo uma identidade visual com cards de KPI em gradiente (azul, coral e verde) e filtros por Ano, Mês e Gerente. Os planos de fundo foram criados em PowerPoint e exportados como imagem.

### Ferramentas

- Microsoft Power BI Desktop
- Power Query (ETL e transformações)
- DAX (medidas e cálculos)
- PowerPoint (design dos planos de fundo)

---

## 3. Execução

### ETL (Power Query)

- Importação e limpeza das duas bases Excel.
- Tratamento de tipos de dados (datas, moeda, texto).
- Remoção de registros inconsistentes ou duplicados.
- Criação de tabela calendário para análise temporal.
- Estruturação do modelo dimensional (fato e dimensões).

### Modelagem

Modelo em estrela com tabela fato de vendas conectada às dimensões de clientes, produtos, vendedores e calendário, além de uma tabela de metas para comparação.

### Medidas DAX

Medidas calculadas para os seis KPIs principais, além de medidas auxiliares para comparações temporais (variação mês a mês, acumulado no ano) e formatação condicional de resultados acima ou abaixo da meta.

### Visual

- Três cards de KPI no topo com ícones e gradientes de cor.
- Gráficos de barras e linhas para evolução temporal e comparações.
- Filtros interativos por Ano, Mês e Gerente.
- Layout responsivo com fundo customizado em versões light e dark.

---

## 4. Geração de Insights

### Principais descobertas

1. **Produtos mais vendidos:** identificação dos produtos com maior volume e receita, permitindo direcionar esforços comerciais para itens de maior retorno.

2. **Desempenho por vendedor:** ranking de vendedores por receita, margem e atingimento de meta, evidenciando quem precisa de suporte e quem pode servir de referência.

3. **Clientes com maior potencial:** segmentação entre clientes ativos e inativos, com destaque para aqueles com histórico de alto ticket médio que reduziram a frequência de compra.

4. **Tendências temporais:** análise da sazonalidade e evolução das vendas ao longo dos meses, identificando períodos de pico e queda.

5. **Oportunidades de crescimento:** cruzamento entre metas não atingidas e regiões ou categorias com potencial de expansão.

---

## 5. Resultado Final

### Entregáveis

- Arquivo `PROJETO 21 - Vendas.pbix` com ETL, modelo, medidas e dashboard funcional.
- Três páginas de análise: Performance Comercial, Análise de Vendedores e Análise de Desempenho.
- Planos de fundo customizados (light e dark) na pasta `Design/`.
- Filtros interativos por Ano, Mês e Gerente.

### Estrutura do projeto

```text
.
├── README.md
├── PROJETO 21 - Vendas.pbix              # dashboard autoral
├── Dashboard Vendas-Gabarito.pbix        # solução de referência (não redistribuído)
├── Base de Dados/
│   └── Base de Dados.xlsx                # dados de vendas e metas
├── Design/
│   ├── Fundo de Tela Editável.pptx       # template editável
│   ├── Fundo de Tela Editável1 - Light.png
│   ├── Fundo de Tela Editável2.png
│   ├── Fundo de Tela Editável - Dark.png
│   └── Tela de Fundo.png
└── .gitignore
```

### Como abrir

1. Abra `PROJETO 21 - Vendas.pbix` no Power BI Desktop.
2. Caso o Power BI solicite novos caminhos, remapeie a fonte de dados em **Transformar dados → Configurações da fonte de dados** para a pasta `Base de Dados/` local.
3. Para aplicar o plano de fundo, acesse **Formatar página → Tela de fundo** e importe a imagem desejada da pasta `Design/`.

---

## 6. Retorno sobre o investimento

### Benefícios obtidos com o dashboard

| Benefício | Impacto estimado |
|---|---|
| Redução do tempo de análise | De horas em planilhas para minutos no dashboard |
| Visibilidade sobre metas | Acompanhamento em tempo real de receita vs meta |
| Gestão de equipe | Identificação rápida de vendedores abaixo da meta |
| Retenção de clientes | Detecção de clientes inativos para ações de reativação |
| Decisões baseadas em dados | Substituição de percepções por evidências quantificáveis |

### Configuração de atualização

- Atualização programada a cada 15 dias via Power BI Service.
- Possibilidade de automação com script Python para atualizar os dados e disparar e-mail com o relatório para o cliente.

> **Nota:** por se tratar de um case de portfólio com dados educacionais, o ROI financeiro não foi mensurado. Os benefícios listados representam o valor que a solução entrega quando aplicada a um cenário real.

---

## 7. Próximos Passos

| Prioridade | Ação | Benefício esperado |
|---|---|---|
| Alta | Publicar no Power BI Service e configurar gateway | Acesso via web e mobile para a equipe |
| Alta | Implementar atualização automática a cada 15 dias | Dados sempre atualizados sem intervenção manual |
| Média | Adicionar análise de rentabilidade por produto | Identificar quais produtos geram mais margem |
| Média | Incluir segmentação geográfica | Mapear regiões com maior potencial de vendas |
| Baixa | Criar alertas automáticos de meta | Notificar gestores quando a meta estiver em risco |
| Baixa | Integrar com CRM para dados em tempo real | Eliminar dependência de exportação manual de planilhas |

---

## Créditos

Projeto de estudo baseado em material da [Xperiun](https://xperiun.com/) / Data Expert.

**Autor:** Nilvan Felipe — [github.com/nilvanfelipe](https://github.com/nilvanfelipe)
