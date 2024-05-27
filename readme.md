# Análise de Dados de Funcionários

Este projeto realiza análises de dados univariadas e bivariadas sobre um dataset de funcionários utilizando as bibliotecas `matplotlib`, `pandas`, `seaborn` e `numpy`. O objetivo é explorar e visualizar as distribuições de diversas variáveis, bem como as relações entre elas.

## Pré-requisitos

Para rodar este projeto, você precisará do Python 3.x e das bibliotecas mencionadas acima. Para facilitar a instalação e o gerenciamento de dependências, você pode utilizar o `pipenv`.

## Instalação

1. Certifique-se de ter o `pipenv` instalado. Se não tiver, você pode instalá-lo usando o seguinte comando:
    ```bash
    pip install pipenv
    ```

2. Clone este repositório:
    ```bash
    git clone https://github.com/seu_usuario/seu_repositorio.git
    cd seu_repositorio
    ```

3. Instale as dependências do projeto:
    ```bash
    pipenv install
    ```

4. Ative o ambiente virtual:
    ```bash
    pipenv shell
    ```

## Uso

Além de rodar todos os cenários utilizando o .ipynb, você pode rodar os scripts de análise diretamente após ativar o ambiente virtual. Aqui estão alguns exemplos de análise que você pode executar:

### Análise Univariada

- **Distribuição dos Salários Mínimos**
    ```python
    import seaborn as sns
    import matplotlib.pyplot as plt
    import pandas as pd

    df = pd.read_csv('dados_funcionarios.csv')
    sns.histplot(df['salarios_minimos'], kde=True)
    plt.axvline(df['salarios_minimos'].mean(), color='r', linestyle='--', label=f'Média: {df['salarios_minimos'].mean():.2f}')
    plt.axvline(df['salarios_minimos'].median(), color='g', linestyle=':', label=f'Mediana: {df['salarios_minimos'].median():.2f}')
    plt.title('Distribuição dos Salários Mínimos')
    plt.xlabel('Salários Mínimos')
    plt.ylabel('Frequência')
    plt.legend()
    plt.show()
    ```

### Análise Bivariada

- **Relação entre Salários Mínimos e Idade com Médias e Medianas**
    ```python
    sns.scatterplot(x='idade', y='salarios_minimos', data=df)
    plt.axhline(df['salarios_minimos'].mean(), color='r', linestyle='--', label=f'Média Salários Mínimos: {df['salarios_minimos'].mean():.2f}')
    plt.axvline(df['idade'].mean(), color='g', linestyle='--', label=f'Média Idade: {df['idade'].mean():.2f}')
    plt.axhline(df['salarios_minimos'].median(), color='r', linestyle=':', label=f'Mediana Salários Mínimos: {df['salarios_minimos'].median():.2f}')
    plt.axvline(df['idade'].median(), color='g', linestyle=':', label=f'Mediana Idade: {df['idade'].median():.2f}')
    plt.title('Relação entre Idade e Salários Mínimos')
    plt.xlabel('Idade')
    plt.ylabel('Salários Mínimos')
    plt.legend()
    plt.show()
    ```

## Contribuindo

Contribuições são bem-vindas! Se você tiver sugestões ou melhorias, sinta-se à vontade para abrir uma issue ou um pull request.