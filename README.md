# Tradução Automática

## 9.5.7. Exercícios
### Tente valores diferentes do argumento num_examples na função load_data_nmt. Como isso afeta os tamanhos do vocabulário do idioma de origem e do idioma de destino?

O argumento num_examples na função load_data_nmt define a quantidade de frases a serem usadas para construir os vocabulários. Se aumentarmos num_examples, mais frases serão incluídas no processo, o que leva a um vocabulário maior, pois mais palavras únicas serão encontradas no conjunto de dados. Por outro lado, se reduzirmos num_examples, menos frases serão processadas, resultando em um vocabulário menor.

Quando o valor de num_examples é baixo (como 100), o vocabulário de ambos os idiomas (origem e destino) é pequeno, com apenas 40 palavras únicas para cada idioma. À medida que aumentamos o número de exemplos, mais frases são processadas, e o vocabulário cresce, pois mais palavras únicas aparecem. No caso de num_examples=500, o vocabulário aumenta para 159 palavras para o idioma de origem e 163 para o idioma de destino. Com 1000 exemplos, o vocabulário continua a crescer, atingindo 266 palavras para o idioma de origem e 321 para o destino. Quando o número de exemplos é aumentado para 5000, o vocabulário se expande significativamente, chegando a 875 palavras para o idioma de origem e 1231 para o destino. Isso mostra claramente que, com mais exemplos, o vocabulário captura uma maior diversidade de palavras, refletindo o aumento da complexidade e da variedade das frases processadas.

### O texto em alguns idiomas, como chinês e japonês, não tem indicadores de limite de palavras (por exemplo, espaço). A tokenização em nível de palavra ainda é uma boa ideia para esses casos? Por que ou por que não?

Em idiomas como chinês e japonês, que não utilizam espaços para separar palavras, a tokenização em nível de palavra não é a abordagem mais adequada. Nesses casos, é mais eficaz empregar técnicas de tokenização específicas que consideram as particularidades dessas línguas.

A ausência de delimitadores de palavras em chinês e japonês torna a identificação de limites de palavras um desafio significativo. A tokenização em nível de palavra nesses idiomas pode ser problemática, pois não há espaços claros para indicar onde uma palavra termina e outra começa. Para lidar com isso, técnicas como a segmentação baseada em caracteres ou o uso de modelos estatísticos que identificam os limites mais prováveis das palavras são aplicadas. Essas abordagens ajudam a superar as ambiguidades e a complexidade associadas à tokenização nesses idiomas. ​

Além disso, ferramentas como o SentencePiece são frequentemente utilizadas para tokenizar textos em chinês e japonês. O SentencePiece trata o texto como uma sequência de caracteres e aprende subunidades de palavras (subpalavras) durante o treinamento, o que é especialmente útil para idiomas sem espaços. Essa abordagem permite uma tokenização mais eficaz e adequada às características específicas desses idiomas. ​

Portanto, em vez de aplicar a tokenização em nível de palavra, é recomendável utilizar técnicas adaptadas às características linguísticas do chinês e do japonês, garantindo uma segmentação mais precisa e eficiente do texto.
