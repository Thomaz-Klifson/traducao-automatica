# Tradução Automática

## 9.5.7. Exercícios
### Tente valores diferentes do argumento num_examples na função load_data_nmt. Como isso afeta os tamanhos do vocabulário do idioma de origem e do idioma de destino?

O argumento num_examples na função load_data_nmt define a quantidade de frases a serem usadas para construir os vocabulários. Se aumentarmos num_examples, mais frases serão incluídas no processo, o que leva a um vocabulário maior, pois mais palavras únicas serão encontradas no conjunto de dados. Por outro lado, se reduzirmos num_examples, menos frases serão processadas, resultando em um vocabulário menor.

Quando o valor de num_examples é baixo (como 100), o vocabulário de ambos os idiomas (origem e destino) é pequeno, com apenas 40 palavras únicas para cada idioma. À medida que aumentamos o número de exemplos, mais frases são processadas, e o vocabulário cresce, pois mais palavras únicas aparecem. No caso de num_examples=500, o vocabulário aumenta para 159 palavras para o idioma de origem e 163 para o idioma de destino. Com 1000 exemplos, o vocabulário continua a crescer, atingindo 266 palavras para o idioma de origem e 321 para o destino. Quando o número de exemplos é aumentado para 5000, o vocabulário se expande significativamente, chegando a 875 palavras para o idioma de origem e 1231 para o destino. Isso mostra claramente que, com mais exemplos, o vocabulário captura uma maior diversidade de palavras, refletindo o aumento da complexidade e da variedade das frases processadas.

### O texto em alguns idiomas, como chinês e japonês, não tem indicadores de limite de palavras (por exemplo, espaço). A tokenização em nível de palavra ainda é uma boa ideia para esses casos? Por que ou por que não?

A tokenização de texto em idiomas como chinês e japonês apresenta desafios específicos devido à ausência de delimitadores explícitos de palavras, como espaços. Dessa forma, a tokenização em nível de palavra não é a abordagem mais adequada para esses idiomas (Xue, 2003).

A segmentação de palavras em chinês e japonês é um problema desafiador devido à natureza logográfica dessas línguas. Estudos indicam que abordagens baseadas em aprendizado de máquina, como modelos estatísticos e redes neurais, têm sido amplamente empregadas para identificar os limites mais prováveis das palavras nesses idiomas (Sproat et al., 1996; Zhang et al., 2013). Essas abordagens permitem superar ambiguidades e desafios inerentes à segmentação de palavras, melhorando a precisão dos modelos de tokenização.

Ferramentas como o SentencePiece (Kudo & Richardson, 2018) são frequentemente utilizadas para lidar com a tokenização de idiomas sem espaços. SentencePiece trata o texto como uma sequência contínua de caracteres e aprende subunidades de palavras (subpalavras) durante o treinamento. Essa abordagem é especialmente eficaz para línguas como chinês e japonês, pois permite uma segmentação mais flexível e adaptada às peculiaridades desses sistemas de escrita.

Portanto, em vez de utilizar a tokenização em nível de palavra, é recomendável empregar métodos que considerem as características lingüísticas específicas do chinês e do japonês, como a segmentação baseada em modelos estatísticos e aprendizado de subpalavras. Essas técnicas garantem uma segmentação mais precisa e eficiente do texto, facilitando o processamento automático da linguagem nesses idiomas.

### Referências:

Kudo, T., & Richardson, J. (2018). SentencePiece: A simple and language-independent subword tokenizer and detokenizer for Neural Text Processing. arXiv preprint arXiv:1808.06226.

Sproat, R., Shih, C., Gale, W., & Chang, N. (1996). A stochastic finite-state word-segmentation algorithm for Chinese. Computational Linguistics, 22(3), 377-404.

Xue, N. (2003). Chinese word segmentation as character tagging. Computational Linguistics and Chinese Language Processing, 8(1), 29-48.

Zhang, Y., Zhang, M., & Fu, G. (2013). Exploring representations from unlabeled data with co-training for Chinese word segmentation. Artificial Intelligence, 204, 54-75.
