## 🎬 Sistema de Recomendação de Filmes em python 🎬 
![Banner](imgs/banner.jpeg)

# Recomendações Cinematográficas
Este projeto implementa um sistema de recomendação de filmes utilizando o dataset MovieLens 100k. O sistema é baseado em técnicas de filtragem colaborativa e recomendação híbrida, permitindo a sugestão de filmes personalizados aos usuários. Ele analisa avaliações de filmes feitas por usuários, combinando informações sobre preferências individuais e características dos filmes para fornecer recomendações relevantes.

### Objetivo
O principal objetivo deste projeto é oferecer recomendações precisas e relevantes de filmes para os usuários, combinando as avaliações que eles fazem com a similaridade entre outros usuários e os gêneros de filmes.

## Funcionalidades
- **Filtragem Colaborativa:** Utiliza as avaliações dos usuários para recomendar filmes com base em preferências de usuários semelhantes.
- **Recomendação Híbrida:** Integra informações sobre a similaridade dos filmes, levando em conta seus gêneros e características, para refinar as recomendações.
- **Métricas de Similaridade:** Implementa cálculo de similaridade usando similaridade do cosseno e a técnica TF-IDF para vetorização de texto.
- **Interação do Usuário:** Permite ao usuário obter recomendações personalizadas com base em suas avaliações.

## Principais Componentes
### Dataset de Filmes e Avaliações:
- O dataset MovieLens 100k é usado, onde:
    1. u.data contém as avaliações dos filmes feitas por usuários.
    2. u.item contém a lista de filmes e seus títulos.

### Redução de Dimensionalidade com SVD:
A técnica Truncated SVD é utilizada para reduzir a dimensionalidade da matriz usuário-filme, permitindo o cálculo eficiente de similaridades entre os usuários.

### Cálculo de Similaridade:
- **Similaridade entre Usuários:** Calculada com base nas avaliações dos filmes.
- **Similaridade entre Filmes:** Baseada nos gêneros de filmes, processados pelo modelo TF-IDF.

### Funções de Recomendação:
- **recomendar_filmes_usuario:** Gera recomendações com base em usuários semelhantes.
- **recomendar_filmes_hibrido:** Combina recomendações colaborativas com informações sobre a similaridade de filmes.

## Estrutura do Código
### 1. Carregamento dos Dados
Os dados de avaliações e filmes são carregados a partir dos arquivos fornecidos no dataset MovieLens. Uma coluna de gênero é gerada aleatoriamente para os filmes, representando categorias como "Ação", "Drama", "Comédia", entre outras.

###  2. Preprocessamento dos Dados
- **Remoção de Duplicatas:** As avaliações duplicadas são agregadas com base na média das notas.
- **Matriz Usuário-Filme:** Uma matriz é construída onde as linhas representam os usuários e as colunas os filmes, preenchida com as avaliações feitas.

### 3. Redução de Dimensionalidade
Utilizando Truncated SVD para reduzir a matriz de avaliações, diminuindo sua complexidade sem perder a essência das informações.

###  4. Cálculo de Similaridade
- **Usuários:** A similaridade entre usuários é calculada usando similaridade do cosseno, permitindo encontrar usuários com gostos similares.
- **Filmes:** A similaridade entre os filmes é calculada com base nos gêneros, através de uma matriz vetorizada pelo método TF-IDF.

### 5. Recomendação
A recomendação é realizada através de duas abordagens:
- **Filtragem Colaborativa:** Recomendação baseada no comportamento de usuários semelhantes.
- **Híbrida:** Combina as preferências de usuários semelhantes com a similaridade entre os gêneros dos filmes.

## Requisitos
### Python 3.x
### Bibliotecas:
- pandas
- scikit-learn
- random

## Como Rodar o Projeto
### 1. Clone este repositório.

### 2. Certifique-se de ter as bibliotecas mencionadas instaladas:
```bash
pip install pandas scikit-learn
```

### 3. Execute o script para gerar recomendações:
```bash
python recomendacao_filmes.py
```

### 4. Exemplo de saída
```plaintext
Recomendações colaborativas: ['Star Wars', 'Jurassic Park', 'The Matrix', 'Titanic', 'The Lion King']
Recomendações híbridas: ['The Godfather', 'Pulp Fiction', 'Schindler's List', 'Forrest Gump', 'Inception']
```

## Referências
- [MovieLens Dataset](https://grouplens.org/datasets/movielens/)
- [Scikit-learn Documentation](https://scikit-learn.org/stable/)
- [Truncated SVD](https://scikit-learn.org/dev/modules/generated/sklearn.decomposition.TruncatedSVD.html)
- [TF-IDF](https://pt.wikipedia.org/wiki/Tf–idf)

## Licença
Este projeto está licenciado sob a [MIT License](LICENSE).
