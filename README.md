# Relatório de Modelagem de Dados no Power BI

Este documento descreve a modelagem de dados utilizada no projeto Power BI, detalhando as tabelas, seus atributos e os relacionamentos estabelecidos entre elas. O objetivo é fornecer uma compreensão clara da estrutura de dados para facilitar a análise e manutenção do projeto.

## Tabelas e Descrições

### 1. **D_Produtos**
- **Contagem**: Quantidade de produtos.
- **Índice**: Índice do produto.
- **Média de mano fatura**: Valor médio das faturas de mao.
- **Média de valor de vendas**: Valor médio das vendas.
- **Mediana no valor de vendas**: Mediana do valor de vendas.
- **Product**: Nome do produto.
- **Valor máximo de venda**: Valor máximo registrado nas vendas.
- **Valor mínimo de venda**: Valor mínimo registrado nas vendas.

### 2. **D_Produtos_Detalhes**
- **Discount Band**: Faixa de desconto aplicada.
- **Índice**: Índice de detalhes do produto.
- **Manufacturing Price**: Preço de fabricação.
- **Personalizar**: Atributo personalizável.
- **Product**: Nome do produto.
- **Sale Price**: Preço de venda.
- **Units Sold**: Unidades vendidas.

### 3. **F_Vendas**
- **Sales**: Vendas totais.
- **Country**: País onde a venda foi realizada.
- **Date**: Data da venda.
- **Discount Band**: Faixa de desconto aplicada.
- **ID_vendas**: Identificação única da venda.
- **Índice**: Índice da venda.
- **Month Name**: Nome do mês.
- **Product**: Nome do produto vendido.
- **Profit**: Lucro obtido.

### 4. **D_Calendário**
- **Date**: Datas dentro do período especificado. Esta tabela foi criada usando o seguinte comando DAX:
```dax
D_Calendário = CALENDAR(DATE(2013, 09, 1), DATE(2014, 12, 1))
```

### 5. **D_Descontos**
- **Discounts**: Valor total dos descontos aplicados.
- **ID_Produto**: Identificação do produto.
- **Sale Price**: Preço de venda após desconto.

### 6. **financials_origem**
- **Sales**: Vendas totais.
- **COGS**: Custo dos bens vendidos.
- **Country**: País.
- **Date**: Data.
- **Discount Band**: Faixa de desconto.
- **Discounts**: Descontos aplicados.
- **Gross Sales**: Vendas brutas.
- **Manufacturing Price**: Preço de fabricação.
- **Month Name**: Nome do mês.

## Relacionamentos
- **D_Produtos** está relacionado a **D_Produtos_Detalhes** através do campo **Product**.
- **F_Vendas** está relacionado a **D_Calendário** pelo campo **Date**, a **D_Produtos** pelo campo **Product** e a **D_Descontos** pelo campo **ID_Produto**.
- **financials_origem** fornece dados financeiros complementares usados para enriquecer as análises.

Este modelo de dados está estruturado para maximizar a eficiência na análise de vendas, lucros e descontos, proporcionando insights valiosos para a tomada de decisões.

