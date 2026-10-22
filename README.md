# Pesquisa de Satisfação de Funcionários — Acme Corp

## Sobre o projeto

Este projeto foi desenvolvido como exercício de análise de dados. A empresa fictícia Acme Corp realiza uma pesquisa anual de satisfação dos funcionários. Como uma mesma pessoa pode responder em anos diferentes, a análise considera somente a resposta mais recente de cada funcionário.

## Objetivos

1. Identificar a resposta mais recente de cada funcionário usando o e-mail como identificador.
2. Contar os funcionários em cada nível de satisfação, de 1 a 5.
3. Calcular a porcentagem de cada nota.
4. Calcular a nota média e identificar se predominam funcionários satisfeitos, neutros ou insatisfeitos.
5. Gerar uma tabela-resumo e um gráfico de barras.

## Ferramentas utilizadas

- Python
- Pandas para limpeza e análise dos dados
- Matplotlib para criação do gráfico
- CSV para os dados de entrada e resultados

## Estrutura do repositório

```text
pesquisa-satisfacao-funcionarios/
├── employee_satisfaction_survey.csv
├── analise_satisfacao.py
├── requirements.txt
├── README.md
└── resultados/
    ├── resumo_satisfacao.csv
    ├── ultimas_respostas_por_funcionario.csv
    └── grafico_distribuicao_satisfacao.png
```

## Como executar

É necessário ter Python instalado.

1. Baixe ou clone este repositório.
2. Abra um terminal dentro da pasta do projeto.
3. Instale as dependências:

```bash
pip install -r requirements.txt
```

4. Execute o script:

```bash
python analise_satisfacao.py
```

O script lê `employee_satisfaction_survey.csv` e gera os arquivos na pasta `resultados/`.

## Método de análise

- A coluna `Email` identifica cada funcionário.
- A coluna `Timestamp` é convertida para data e hora.
- Os registros são ordenados cronologicamente.
- Para cada e-mail, é mantido somente o registro com o timestamp mais recente.
- As notas válidas são de 1 a 5.
- O percentual de cada nota é calculado dividindo a quantidade daquela nota pelo total de funcionários únicos e multiplicando por 100.
- A nota média é calculada usando somente as respostas mais recentes.

## Resultados encontrados

A base original contém **901 registros**. Após manter apenas a resposta mais recente de cada e-mail, foram analisados **277 funcionários únicos**.

| Nota | Nível de satisfação | Funcionários | Percentual |
|---:|---|---:|---:|
| 1 | Muito insatisfeito | 19 | 6.86% |
| 2 | Insatisfeito | 34 | 12.27% |
| 3 | Neutro | 52 | 18.77% |
| 4 | Satisfeito | 83 | 29.96% |
| 5 | Muito satisfeito | 89 | 32.13% |
| **Total** |  | **277** | **100.00%** |

- **Nota média:** 3.68/5
- **Satisfeitos (notas 4 e 5):** 172 (62.09%)
- **Neutros (nota 3):** 52 (18.77%)
- **Insatisfeitos (notas 1 e 2):** 53 (19.13%)

## Conclusão de negócio

A nota média foi de **3.68 em 5**. A maioria dos funcionários está satisfeita ou muito satisfeita, representando **62.09%** dos funcionários analisados. Ainda assim, **53 funcionários (19.13%)** estão insatisfeitos ou muito insatisfeitos, o que indica uma oportunidade para investigar os motivos e propor melhorias no ambiente de trabalho.

## Comprovação técnica

O arquivo `analise_satisfacao.py` documenta e executa o tratamento de dados. Os arquivos na pasta `resultados/` apresentam a tabela-resumo, a lista das respostas mais recentes e o gráfico de distribuição.
