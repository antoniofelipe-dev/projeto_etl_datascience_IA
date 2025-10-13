Projeto: Pipeline Completo de Preparação de Dados para Machine Learning
Análise de Dados Imobiliários com Indicadores Econômicos

📄 Sobre o Projeto
Este repositório contém um projeto de Ciência de Dados de ponta a ponta que demonstra as melhores práticas na preparação de dados para modelagem de Machine Learning. O objetivo é construir um pipeline robusto, modular e bem documentado, cobrindo desde a coleta de dados de múltiplas fontes até a engenharia de atributos e a divisão estratégica dos conjuntos de dados.

Utilizamos um conjunto de dados hipotético de imóveis, que é enriquecido com indicadores macroeconômicos (taxa SELIC) obtidos via API do Banco Central do Brasil, para criar um dataset rico e pronto para ser usado em modelos preditivos de regressão.

🚀 Etapas do Pipeline de Preparação de Dados
O projeto segue rigorosamente uma série de etapas para garantir a qualidade e a consistência dos dados:

1. Coleta e Integração de Dados:

Combinação de um CSV local com dados de imóveis e dados da taxa SELIC obtidos em tempo real da API pública do Banco Central do Brasil.

2. Limpeza e Tratamento:

Valores Ausentes: Comparação entre remoção e imputação, com a escolha final pela imputação por mediana para preservar a integridade do dataset.

Outliers: Detecção via método IQR (Intervalo Interquartil) e remoção de valores discrepantes para evitar distorções no modelo.

Padronização: Uniformização de formatos de texto (caixa baixa, remoção de espaços) e conversão de datas para um tipo padrão (datetime).

3. Codificação de Variáveis Categóricas:

Análise comparativa entre LabelEncoder e OneHotEncoder, selecionando o segundo para converter a variável bairro em formato numérico sem criar uma relação ordinal artificial.

4. Normalização e Padronização:

Teste e visualização do impacto do MinMaxScaler e StandardScaler. A padronização com StandardScaler foi a escolhida por sua robustez e adequação a uma gama maior de algoritmos.

5. Engenharia de Atributos:

Criação de duas novas features (preco_por_m2 e idade_anuncio_dias) para agregar maior poder preditivo e capturar relações de negócio relevantes.

6. Divisão dos Dados:

Particionamento do dataset em conjuntos de Treino (70%), Validação (15%) e Teste (15%).

Discussão sobre as estratégias de Holdout e K-Fold Cross-Validation, recomendando a combinação de ambas para uma avaliação de modelo mais confiável.

🛠️ Tecnologias Utilizadas
Linguagem: Python 3.9+

Bibliotecas Principais:

pandas e numpy para manipulação de dados

scikit-learn para pré-processamento e divisão dos dados

requests para consumo de API

matplotlib e seaborn para visualização de dados

⚙️ Como Executar o Projeto
Clone o repositório:

Bash

git clone https://github.com/seu-usuario/nome-do-repositorio.git
cd nome-do-repositorio
Crie e ative um ambiente virtual (recomendado):

Bash

# Criar ambiente
python -m venv venv

# Ativar no Windows
venv\Scripts\activate

# Ativar no macOS/Linux
source venv/bin/activate
Instale as dependências:

Bash

pip install pandas numpy requests scikit-learn matplotlib seaborn
Execute o script ou notebook:
O código pode ser executado como um script Python (.py) ou dentro de um ambiente interativo como o Jupyter Notebook (.ipynb).

✨ Conclusão Técnica
Este projeto demonstrou um pipeline completo e profissional de preparação de dados. As principais decisões técnicas foram:

Coleta de Dados: Enriquecemos dados locais de imóveis com a taxa SELIC via API do BCB, criando um dataset com contexto micro e macroeconômico.

Limpeza de Dados: Optamos pela imputação pela mediana para tratar valores ausentes, preservando o tamanho do dataset. Outliers de preço foram removidos usando o critério de IQR para evitar distorções.

Codificação Categórica: O OneHotEncoder foi escolhido para a variável bairro, pois evita a criação de uma relação ordinal artificial, o que é crucial para a maioria dos modelos.

Escalonamento: O StandardScaler foi o método selecionado para padronizar as variáveis numéricas, por sua robustez e por ser um pré-requisito comum em muitos algoritmos de Machine Learning.

Engenharia de Atributos: Foram criadas as features preco_por_m2 e idade_anuncio_dias, que agregam valor ao capturar relações de negócio importantes (valor relativo e temporalidade).

Divisão dos Dados: A estratégia recomendada é a combinação de Holdout com K-Fold Cross-Validation. O Holdout isola um conjunto de teste final, enquanto o K-Fold é usado sobre os dados de treino para uma avaliação e otimização de modelo mais confiáveis.

O DataFrame final está limpo, pré-processado e enriquecido, pronto para ser utilizado no treinamento de modelos de regressão para prever preços de imóveis com maior precisão e robustez.

📜 Licença
Este projeto está sob a licença MIT. Veja o arquivo LICENSE para mais detalhes.