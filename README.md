# Detecção de objetos YOLO com OpenCV e Python

## O que é YOLO exatamente?
YOLO (You Only Look Once) é um método/maneira de fazer a detecção de objetos. É o algoritmo/estratégia por trás de como o código vai detectar objetos na imagem.<br>
A implementação oficial desta ideia está disponível através da DarkNet (implementação da rede neural desde o início em C do autor). Está disponível no github para as pessoas usarem.<br>
Estruturas de detecção anteriores examinavam diferentes partes da imagem várias vezes em diferentes escalas e redefiniam a técnica de classificação de imagem para detectar objetos. Essa abordagem é lenta e ineficiente.<br>
YOLO adota uma abordagem totalmente diferente. Ele examina a imagem inteira apenas uma vez, passa pela rede uma vez e detecta objetos. Daí o nome. É muito rápido. Essa é a razão pela qual se tornou tão popular.<br>
Existem outras estruturas populares de detecção de objetos, como Faster R-CNN e SSD, que também são amplamente utilizadas.<br>
Nesta postagem, veremos como usar um modelo YOLO pré-treinado com OpenCV e começar a detectar objetos imediatamente.<br>

## Módulo OpenCV dnn
O módulo DNN (Rede Neural Profunda) fazia inicialmente parte do repositório opencv_contrib. Ele foi movido para o branch master do opencv repo no ano passado, dando aos usuários a capacidade de executar inferência em modelos de aprendizado profundo pré-treinados dentro do próprio OpenCV.<br>
(Uma coisa a observar aqui é que o módulo dnn não deve ser usado para treinamento. É apenas para executar inferência em imagens/vídeos.)
Inicialmente, apenas os modelos Caffe e Torch eram suportados. Ao longo do período, o suporte para diferentes estruturas/bibliotecas, como o TensorFlow, está sendo adicionado.<br>
O suporte para YOLO/DarkNet foi adicionado recentemente. Vamos usar o módulo OpenCV dnn com um modelo YOLO pré-treinado para detectar objetos comuns.