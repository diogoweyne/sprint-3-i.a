# 🏍️ Projeto Pátio de Motos - Visão Computacional

## 📖 Descrição do Projeto
Este projeto tem como objetivo **monitorar motocicletas em tempo real** em um pátio, utilizando **Visão Computacional**.  
A solução integra **YOLOv8 (Ultralytics)** para detecção de objetos, **OpenCV** para processamento de vídeo e **Streamlit** para visualização dos dados em dashboard interativo.  

Os dados coletados (quantidade de motos, confiança das detecções e timestamp) são armazenados em um banco **SQLite**, permitindo análises quantitativas e qualitativas.

---

## 🛠️ Tecnologias Utilizadas
- **Python 3.10+**
- [Ultralytics YOLOv8](https://github.com/ultralytics/ultralytics)
- [OpenCV](https://opencv.org/)
- [Streamlit](https://streamlit.io/)
- [SQLite3](https://www.sqlite.org/index.html)
- Pandas & SQLAlchemy

---

## 🚀 Como Rodar o Projeto

### 1. Clonar o repositório
```bash
git clone https://github.com/seu-usuario/sp3-ia.git
cd sp3-ia
```

### 2. Criar ambiente virtual (recomendado)
```bash
python -m venv .venv
.\.venv\Scriptsctivate   # Windows
source .venv/bin/activate  # Linux/Mac
```

### 3. Instalar dependências
```bash
pip install -r requirements.txt
```

### 4. Baixar modelo YOLO pré-treinado
O YOLOv8n (nano) será baixado automaticamente na primeira execução:
```python
from ultralytics import YOLO
YOLO("yolov8n.pt")
```

### 5. Rodar detecção em tempo real
Usando webcam:
```bash
python src/main.py
```

Ou usando vídeo de teste:
```bash
python src/main.py data/video.mp4
```

> Aperte `q` para encerrar o vídeo.

### 6. Rodar o dashboard
```bash
streamlit run src/dashboard.py
```

O dashboard abrirá no navegador em [http://localhost:8501](http://localhost:8501).

---

## 📊 Funcionalidades e Métricas
- ✅ Detecção de **múltiplas motos** em tempo real.  
- ✅ Exibição de **bounding boxes** com confiança da predição.  
- ✅ Armazenamento em banco SQLite:
  - Timestamp de cada detecção.  
  - Quantidade de motos por frame.  
  - Confiança média das predições.  
- ✅ Dashboard interativo com:
  - Últimos registros salvos.  
  - Gráfico histórico de quantidade de motos detectadas.  

---

## 📂 Estrutura do Projeto
```
sp3-ia/
├── src/
│   ├── main.py           # Script principal
│   ├── moto_detector.py  # Classe YOLO para detecção
│   ├── persistencia.py   # Persistência no SQLite
│   ├── dashboard.py      # Dashboard Streamlit
├── database/             # Banco SQLite gerado automaticamente
├── data/                 # Vídeos de teste
├── requirements.txt      # Dependências
```



## 👨‍💻 Autores
- **Diogo Paquete Weyne** – RM558380
- **Gustavo Tonato Maia** – RM555393
- **João Victor de Souza** – RM555290  
