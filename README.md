# a3-calculadora-rendafixa
Sistema: Calculadora de renda fixa\
Integrantes: Bernardo Gomes, Cauã Durante, Renato Nagahama e Argel dos Santos

Funcionalidades:
- Entrada de dados
- Validação da entrada de dados
- Calcular rentabilidade da poupança
- Calcular rentabilidade dos títulos tributáveis (CDB/RDB/LC)
- Calcular rentabilidade dos títulos isentos (LCI/LCA)

Funcionalidades a serem testadas:
- Calcular rentabilidade dos títulos tributáveis
- Calcular rentabilidade dos títulos isentos
- Validação da entrada de dados

Testes manuais:
- Valor da aplicação (Particionamento)
- Taxas percentuais (Valor limite)
- Vencimento em dias (Particionamento)

Requisitos Funcionais\
RF01 - O sistema deve permitir o usuário inserir o valor inicial do investimento em Reais.\
RF02 - O sistema deve permitir o usuários inserir o prazo de vencimento do investimento em dias, meses ou anos.\
RF03 - O sistema deve permitir ao usuário inserir a taxas de base (DI e SELIC).\
RF04 - O sistema deve permitir ao usuário inserir as taxas de rendimentos específicas. (CDB,RDB,LC e LCI,/LCA)\
RF05 - O sistema deve validar os valores de entrada, permitindo apenas números positivos.\
RF06 - O sistema deve calcular o rendimento bruto e líquido e o valor total líquido do investimento na poupança.\
RF07 - O sistema deve calcular o rendimento bruto e líquido dos títulos tributáveis, aplicar dedução de imposto e calcular o valor total líquido.\
RF08 - O sistema deve calcular o rendimento bruto e líquido dos títulos não tributáveis e calcular o valor total líquido.\

Requisitos Não Funcionais\
RNF01 - Os cálculos devem ser executados e exibidos em menos de 1 segundo. (Performance)\
RNF02 - Os resultados devem ser exibidos com 2 casas decimais para manter a exatidão. (Performance)\
RNF03 - Os resultados devem ser exibidos em um painel com cores simbólicas e intuitivas. (Usabilidade)\
RNF04 - Para entradas inválidas o sistema deve fornecer um feedback com o erro em questão. (Usabilidade)\
RNF05 - A entrada de dados e os resultados monetários devem ser formatados no padrão brasileiro - R$. (Usabilidade)\

Casos de uso\
UC01 - Inserir investimento inicial\
UC02 - Inserir taxas de base\
UC03 - Inserir taxas de rendimentos\
UC04 - Calcular rendimento da poupança\
UC05 - Calcular rendimento de títulos tributáveis\
UC06 - Calcular rendimento de títulos não tributáveis\
UC07 - Mostrar resultado\
