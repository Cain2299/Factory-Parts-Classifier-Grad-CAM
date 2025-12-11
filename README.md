🔧 Factory Parts Classifier + Grad-CAM

Classificação de peças industriais (OK vs Defeito) com explicabilidade visual

Este projeto demonstra como aplicar Visão Computacional e Explainable AI (XAI) para inspeção automática de qualidade de peças industriais.
O modelo identifica se uma peça está OK ou possui defeito, e utiliza Grad-CAM para mostrar exatamente onde a rede olhou ao tomar a decisão.

O objetivo é apresentar um pipeline completo, simples e funcional, ideal para aplicações industriais reais e para demonstrar domínio de IA aplicada.


---

🚀 Principais Destaques

✔️ Classificação de peças industriais usando ResNet18 pré-treinada (Transfer Learning).

✔️ Dataset estruturado em train/ e val/ com classes como ok e defeito.

✔️ Implementação completa do Grad-CAM para explicabilidade.

✔️ Visualização da atenção da rede sobre regiões com defeito.

✔️ Código limpo, modular e pronto para produção.



---

📂 Estrutura do Projeto

factory-parts-gradcam/
├── data/
│   ├── train/
│   │   ├── ok/
│   │   └── defeito/
│   └── val/
│       ├── ok/
│       └── defeito/
├── main.ipynb
├── requirements.txt
└── README.md

Você pode adicionar quantas classes desejar (parafuso_ok, parafuso_defeito, rolamento_ok etc.).


---

🧰 Tecnologias Utilizadas

Python 3.9+

PyTorch

Torchvision

Grad-CAM (Explainable AI)

OpenCV

PIL / Matplotlib



---

📦 Instalação

1. Clone o repositório

git clone ******https://github.com/seu-usuario/factory-parts-gradcam.git******
cd factory-parts-gradcam

2. Instale as dependências

pip install -r requirements.txt

3. Coloque seu dataset em:

data/train/<classe>/
data/val/<classe>/


---

🏭 Como Funciona o Pipeline

1️⃣ Dataset Industrial

As imagens das peças são separadas por classe.
Exemplo:

train/ok/peca_001.jpg
train/defeito/peca_101.jpg

2️⃣ Treinamento (Transfer Learning)

Usamos ResNet18 pré-treinada no ImageNet, ajustando apenas a última camada para o número de classes industriais.

3️⃣ Predict + Grad-CAM

Após treinar, aplicamos Grad-CAM para gerar mapas de calor que mostram onde o modelo focou.

4️⃣ Visualização Final

O resultado é mostrado como:

Imagem original

Heatmap Grad-CAM

Overlay destacando defeitos reais



---

🔥 Exemplo de Output

(Adicione suas imagens reais aqui após rodar o notebook/script)

Peça original      |      Mapa Grad-CAM      |      Overlay (Pred: defeito)

O Grad-CAM destacará automaticamente regiões com:

Trincos

Arranhões

Deformações

Falha de acabamento

Buracos

Desalinhamentos


Isso torna o modelo muito útil em ambientes industriais.


---

🧠 Código Principal

O script principal (main.ipynb) inclui:

Carregamento de dataset

Treino + validação

Salvamento do melhor modelo

Execução do Grad-CAM em uma imagem


O Grad-CAM é implementado usando PyTorch hooks para capturar:

ativações da última camada convolucional

gradientes relativos à classe alvo


Isso segue a formulação do paper oficial Grad-CAM: Visual Explanations from Deep Networks via Gradient-based Localization (Selvaraju et al., 2017).


---

🎯 Objetivos do Projeto

Este repositório foi construído com os seguintes objetivos:

Demonstrar domínio de Visão Computacional aplicada a processos reais.

Mostrar capacidade de implementar e explicar modelos interpretáveis.

Criar um portfólio profissional para vagas em IA industrial, automação, ML Engineering e Computer Vision.



---

🧭 Como Executar

1. Treinar o modelo

python main.ipynb --train

2. Gerar Grad-CAM de uma peça

python main.ipynb --gradcam --image data/val/defeito/peca_001.jpg

Um arquivo PNG com o overlay será criado automaticamente.


---

🧪 Resultados Esperados

Acurácia média entre 85% e 98%, dependendo da qualidade do dataset.

Grad-CAM focando claramente em áreas com defeitos.

Melhor interpretabilidade do que modelos tradicionais de CNN.



---

📚 Referências

Grad-CAM: Visual Explanations from Deep Networks via Gradient-based Localization — Selvaraju et al. (2017)

Tutoriais oficiais de Transfer Learning do PyTorch

Implementações open-source de hooks para Grad-CAM

Documentação do torchvision (ResNet18)



---

Autor

Projeto desenvolvido para fins de estudo e demonstração profissional.
