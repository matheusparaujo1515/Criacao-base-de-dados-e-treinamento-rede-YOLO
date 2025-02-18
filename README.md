# Treinamento da Rede YOLOv5 para Classificacao de Residuos de Bebidas

## Contexto
Este projeto fez parte do desafio proposto no **Bootcamp BairesDev - Machine Learning Practitioner**, cujo objetivo foi desenvolver um modelo de classificacao de residuos de bebidas utilizando a rede neural YOLOv5. O modelo foi treinado para detectar e classificar objetos de interesse, auxiliando no gerenciamento de residuos reciclaveis.

## Objetivo
O desafio envolveu a criacao de uma base de dados e o treinamento da rede YOLOv5, abrangendo as seguintes etapas:
- Coleta e rotulacao de imagens.
- Formato de anotacoes para deteccao de objetos.
- Treinamento do modelo YOLOv5.
- Validacao e avaliacao de desempenho.
- Implementacao pratica para otimizacao da reciclagem de residuos.

## Tecnologias e Bibliotecas Utilizadas
- Python
- YOLOv5 (You Only Look Once - versao 5)
- LabelImg (Ferramenta de anotacao de imagens)
- PyTorch (Treinamento do modelo)
- OpenCV (Manipulacao e pre-processamento de imagens)
- Matplotlib (Visualizacao de resultados)

## Como Funciona
1. **Criacao da Base de Dados**: Foram coletadas imagens de garrafas e latas, organizadas em duas classes principais: aluminio e vidro.
2. **Anotacao dos Dados**: As imagens foram rotuladas utilizando a ferramenta `LabelImg`, gerando arquivos `.txt` no formato YOLO.
3. **Treinamento da Rede YOLOv5**: O modelo foi treinado com os dados rotulados para detectar e classificar os residuos corretamente.
4. **Avaliacao do Modelo**: Foram realizados testes de validacao para medir acuracia e precisao do modelo.
5. **Aplicacao Pratica**: O modelo treinado pode ser integrado a sistemas de coleta seletiva para melhorar a eficiencia da separacao de residuos reciclaveis.

## Como Executar o Codigo
1. Clone o repositório do YOLOv5:
   ```bash
   git clone https://github.com/ultralytics/yolov5
   cd yolov5
   pip install -r requirements.txt
   ```
2. Baixe e organize o dataset do Kaggle (Drink Waste Classification).
3. Configure o arquivo `data.yaml` para definir os caminhos da base de dados e classes.
4. Inicie o treinamento do modelo:
   ```bash
   python train.py --img 640 --batch 16 --epochs 50 --data data.yaml --weights yolov5m.pt --device 0 --cache --workers 8
   ```
5. Realize a validacao do modelo:
   ```bash
   python val.py --data data.yaml --weights runs/train/exp3/weights/best.pt --img 640 --conf 0.25
   ```

## Resultados e Impacto
O modelo treinado apresentou boa acuracia na deteccao das classes aluminio e vidro. Algumas aplicacoes praticas incluem:
- Alertar a presenca de garrafas de vidro no lixo comum.
- Melhorar a eficiencia na coleta de latas de aluminio.
- Reducao do desperdicio e maior incentivo a reciclagem.

## Melhorias Futuras
- Ajuste fino de hiperparametros para melhorar a deteccao.
- Integracao com sistemas de automacao de coleta seletiva.
- Ampliacao do dataset com mais categorias de residuos reciclaveis.

## Documentacao das Bibliotecas
- YOLOv5: https://github.com/ultralytics/yolov5
- PyTorch: https://pytorch.org/docs/stable/index.html
- LabelImg: https://github.com/HumanSignal/labelImg
- OpenCV: https://docs.opencv.org/
- Matplotlib: https://matplotlib.org/stable/contents.html
