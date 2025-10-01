# 🚀 Projeto Pátio de Motos - Visão Computacional

Este projeto faz parte da Sprint 3 do Challenge e tem como objetivo **detectar motocicletas em um pátio** utilizando técnicas de **Visão Computacional**.  
A solução foi implementada com o modelo **YOLOv8 (Ultralytics)**, capaz de identificar motos em **tempo real via webcam** ou a partir de **imagens/vídeos de teste**.

---

## 📌 Estrutura do Projeto

```
projeto-patio-motos/
│── data/               # pasta para armazenar vídeos ou imagens de teste
│── models/             # pasta para salvar modelo YOLO treinado ou pré-treinado
│── src/
│   ├── main.py         # script principal (roda detecção em vídeo ou webcam)
│   ├── detector.py     # classe para carregar e rodar o modelo YOLO
│   └── utils.py        # funções auxiliares (FPS, métricas, etc.)
│── requirements.txt    # dependências do projeto
│── README.md           # documentação
```

---

## ⚙️ Tecnologias Utilizadas

- [Python 3.9+](https://www.python.org/)  
- [Ultralytics YOLOv8](https://github.com/ultralytics/ultralytics) → modelo pré-treinado em COCO  
- [OpenCV](https://opencv.org/) → captura e exibição de imagens/vídeos  
- [Matplotlib](https://matplotlib.org/) → visualização (opcional para gráficos de métricas)  

---

## 🚀 Como Executar

### 1️⃣ Clonar o Repositório
```bash
git clone https://github.com/SEU_USUARIO/projeto-patio-motos.git
cd projeto-patio-motos
```

### 2️⃣ Criar Ambiente Virtual (recomendado)
```bash
python -m venv .venv
.venv\Scripts\activate   # Windows
```

### 3️⃣ Instalar Dependências
```bash
pip install -r requirements.txt
```

### 4️⃣ Baixar Modelo YOLOv8 (Nano - Leve)
```bash
python -c "from ultralytics import YOLO; YOLO('yolov8n.pt')"
```

### 5️⃣ Executar a Detecção
- Usando **webcam**:
```bash
python src/main.py
```

- Usando **vídeo**:
No `main.py`, troque:
```python
cap = cv2.VideoCapture(0)
```
por:
```python
cap = cv2.VideoCapture("data/motos.mp4")
```

- Usando **imagem estática** (teste):
```python
python src/test_image.py
```

---

## 📊 Resultados Parciais

- **Detecção em tempo real:** o modelo YOLOv8n conseguiu identificar motocicletas com boa precisão.  
- **FPS médio:** ~10-15 fps em CPU (varia conforme o hardware).  
- **Métricas qualitativas:** caixas delimitadoras são desenhadas em torno das motos com a **confiança da predição**.  
- **Escalabilidade:** pode ser expandido para contagem de veículos, integração com banco de dados ou monitoramento em tempo real de pátios.  

Exemplo de saída (ilustrativo):  

![Exemplo de detecção](https://github.com/ultralytics/assets/raw/main/im/detect.jpg)

---

## 🔗 Repositório no GitHub

👉 [Clique aqui para acessar o repositório](https://github.com/SEU_USUARIO/projeto-patio-motos)

---

## ✨ Próximos Passos

- Adicionar **armazenamento de logs** das detecções (JSON/CSV/BD).  
- Criar **dashboard** com histórico de entradas e saídas.  
- Implementar **alertas automáticos** para irregularidades (ex: moto fora da vaga).  



## 👨‍💻 Autores
- **Diogo Paquete Weyne** – RM558380
- **Gustavo Tonato Maia** – RM555393
- **João Victor de Souza** – RM555290  
