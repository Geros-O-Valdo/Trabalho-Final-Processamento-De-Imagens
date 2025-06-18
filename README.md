# Trabalho-Final-Processamento-De-Imagens
# 📚 Extração Inteligente de Conteudos da Lousa

Este projeto tem como objetivo **automatizar a extração de imagens úteis da lousa durante uma aula presencial**, descartando automaticamente os momentos em que o professor está à frente do quadro. A ferramenta é pensada especialmente para cenários presenciais, onde alunos precisam de registros limpos do conteúdo sem gravar a aula inteira ou causar distrações com fotos manuais.

## 🎯 Motivação

Durante aulas presenciais, muito do conteúdo relevante fica no quadro-negro, mas:
- É apagado rapidamente após a explicação.
- Alunos não conseguem copiar tudo a tempo.
- Fotos manuais ficam borradas ou são proibidas.
- Gravações integrais são invasivas, pesadas e difíceis de consultar.

Com este sistema, o professor apenas se afasta do quadro, e o programa identifica automaticamente os momentos "limpos" para salvar as imagens relevantes.

---

## ⚙️ Como Funciona

O script analisa um vídeo (`video.mp4`) de uma aula e executa os seguintes passos:

1. **Detecção de presença humana** no quadro usando o modelo `YOLOv5`.
2. **Ignora frames** em que o professor ainda está na frente do quadro.
3. **Compara com o último frame salvo** para evitar salvar imagens quase idênticas.
4. **Salva somente quadros diferentes e limpos** em uma pasta de saída (`frames_sem_professors/`).

---

## 🧠 Tecnologias Utilizadas

- [Ultralytics YOLOv5](https://github.com/ultralytics/yolov5) – para detecção de pessoas
- [OpenCV](https://docs.opencv.org/) – manipulação e leitura de vídeo
- [scikit-image](https://scikit-image.org/docs/) – cálculo de similaridade estrutural (SSIM)
- [tqdm](https://tqdm.github.io/) – barra de progresso no terminal

---

## ▶️ Como Usar

1. **Instale os requisitos** (de preferência em um ambiente virtual):

```bash
pip install opencv-python-headless ultralytics scikit-image tqdm
