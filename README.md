---

# Segmentação Morfológica com Watershed

Este repositório contém o Laboratório de Segmentação de Imagens (Lab 8), cujo objetivo é implementar e analisar a técnica de segmentação morfológica utilizando o algoritmo Watershed. O trabalho foi desenvolvido no contexto da disciplina de Processamento Digital de Imagens e inclui aplicações em imagens estáticas, imagens de avatares e processamento em tempo real com webcam.

---

## Autores

* Fabricio da Costa Fernandes (RA: 11202321635)
* Felipe de Lima Major (RA: 11202230321)
* Lilian Gimenez Teixeira (RA: 11202332321)

---

## Datas

* Data de realização dos experimentos: Abril de 2026
* Data de publicação do relatório: Abril de 2026

---

## Introdução

A segmentação de imagens é uma etapa fundamental no Processamento Digital de Imagens, sendo responsável por dividir uma imagem em regiões de interesse que podem ser analisadas separadamente.

Neste trabalho, foi utilizada a técnica de segmentação morfológica Watershed, que interpreta a imagem como uma superfície topográfica. Nessa abordagem, os níveis de intensidade representam elevações, e o algoritmo realiza a separação das regiões como se fossem bacias hidrográficas.

O objetivo deste projeto é aplicar o algoritmo Watershed para segmentar objetos e pessoas em imagens, identificar e rotular cada região segmentada, aplicar a técnica em tempo real com webcam e integrar esse processo ao contexto do projeto final.

---

## Procedimentos Experimentais

O processo de segmentação foi realizado em etapas sequenciais.

Inicialmente, foi feito um pré-processamento das imagens utilizando filtros de suavização, como Gaussian Blur e Median Blur, com o objetivo de reduzir ruídos e melhorar a qualidade da segmentação.

Em seguida, foi aplicada a limiarização utilizando o método de Otsu, que permite determinar automaticamente um valor de limiar para separar o fundo dos objetos.

Após isso, foram utilizadas operações morfológicas, como abertura para remoção de ruídos e dilatação para definição do fundo da imagem.

A transformada de distância foi então aplicada para calcular a distância de cada pixel até o fundo, permitindo identificar os centros das regiões de interesse.

Na etapa seguinte, foi realizada a rotulação dos componentes conectados utilizando a função connectedComponents, atribuindo um identificador único para cada objeto.

Com os marcadores definidos, o algoritmo Watershed foi aplicado para segmentar corretamente os objetos, separando regiões conectadas.

Por fim, foi realizado um pós-processamento com extração de contornos, desenho de caixas delimitadoras e inserção de textos para identificação dos objetos.

Esse pipeline também foi adaptado para execução em tempo real utilizando webcam, processando continuamente os frames capturados.

---

## Análise e Discussão

A limiarização utilizando o método de Otsu apresentou bons resultados em imagens com contraste adequado, porém mostrou sensibilidade a variações de iluminação, o que pode comprometer a qualidade da segmentação.

A transformada de distância foi essencial para identificar corretamente os centros dos objetos, sendo uma etapa fundamental para a separação de regiões conectadas.

A rotulação permitiu distinguir diferentes objetos na imagem, facilitando a identificação individual de cada região segmentada.

O algoritmo Watershed se mostrou eficaz na separação de objetos próximos, porém apresentou limitações em casos onde os objetos estavam muito conectados ou quando havia presença de ruído residual.

Durante a execução em tempo real com webcam, foram observados alguns artefatos, como instabilidade na segmentação devido ao movimento, influência de iluminação variável e detecção incorreta de pequenos objetos.

Na integração com o projeto final, que utiliza segmentação por cor de pele e agrupamento com KMeans, o uso do Watershed contribuiu para melhorar a separação de regiões semelhantes, reduzindo a mistura de clusters e aumentando a precisão da análise de cores dominantes.

---

## Conclusões

O algoritmo Watershed demonstrou ser uma ferramenta eficiente para segmentação de imagens, especialmente na separação de objetos conectados.

Os resultados indicam que a qualidade da segmentação depende fortemente do pré-processamento da imagem, sendo fundamental a aplicação de filtros adequados e operações morfológicas.

A transformada de distância desempenha um papel essencial na definição dos marcadores utilizados pelo Watershed, impactando diretamente o resultado final.

Embora o método funcione bem em imagens estáticas, sua aplicação em tempo real apresenta desafios relacionados a ruído, iluminação e movimento.

A combinação do Watershed com outras técnicas de segmentação, como segmentação por cor, mostrou-se eficaz e ampliou as possibilidades de aplicação prática.

---

## Estrutura do Projeto

```
main.ipynb          # Notebook contendo o relatório e os experimentos
README.md           # Documentação do projeto
static/             # Imagens
```

---

## Como Executar

Para executar o projeto, é necessário ter instalado:

* Python 3.8 ou superior
* Bibliotecas: opencv-python, numpy, matplotlib, scikit-learn
* Ambiente Jupyter Notebook

Instalação das dependências:

```
pip install opencv-python numpy matplotlib scikit-learn
```

Execução:

```
jupyter notebook main.ipynb
```

---

## Referências

* OpenCV Documentation: [https://docs.opencv.org/](https://docs.opencv.org/)
* Gonzalez, R. C.; Woods, R. E. – Digital Image Processing
* Scikit-image Documentation: [https://scikit-image.org/](https://scikit-image.org/)
* Material de aula da disciplina de Processamento Digital de Imagens
