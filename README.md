# Gato ou Cachorro?
Esse código é pipeline simples de um classificador de imagens (Aprendizado Supervisionado), desde o tratamento dos dados até a predição. Utilizando especificamente uma técnica avançada de Deep Learning chamada Transfer Learning (Aprendizado por Transferência), aqui estão os processos detalhados:

1. Aquisição e Limpeza: O script baixa um dataset compactado, extrai as imagens e executa uma limpeza rigorosa, removendo arquivos de sistema (.DS_Store) e utilizando a biblioteca PIL para identificar e excluir imagens corrompidas que quebrariam o treinamento.

2. Preparação de Dados: Utiliza o ImageDataGenerator para normalizar os pixels (rescale 1/255) e dividir automaticamente os dados em 80% para treino e 20% para validação.

3. Transfer Learning (VGG16): Carrega o modelo VGG16 pré-treinado na ImageNet, 'congela' suas camadas originais para aproveitar o conhecimento prévio de formas e texturas, e adiciona uma nova 'cabeça' de classificação (camadas Dense e Dropout) no topo.

4. Treinamento: O modelo é compilado com o otimizador Adam e treinado por 10 épocas, buscando minimizar a perda (loss) e maximizar a acurácia na distinção entre gatos e cachorros.

5. Interface de Predição: Define uma função que processa uma imagem enviada pelo usuário, ajustando seu tamanho para 224x224, e utiliza o modelo treinado para retornar o rótulo ('Gato' ou 'Cachorro') com base no limiar de probabilidade.
