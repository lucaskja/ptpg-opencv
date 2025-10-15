# Análise de Imagens de Microplásticos com OpenCV

Um projeto Python para análise de imagens de microplásticos usando OpenCV e técnicas de equalização de histograma.

## Estrutura do Projeto

```
ptpg-opencv/
├── data/           # Coloque suas imagens de microplásticos aqui
├── notebooks/      # Notebooks Jupyter para análise
│   ├── histogram_equalization.ipynb    # Equalização de histograma interativa
│   └── interactive_adjustments.ipynb   # Ajustes de matiz, saturação e contraste
├── src/           # Código fonte Python
├── results/       # Imagens de saída e resultados da análise
├── venv/          # Ambiente virtual Python 3.13
└── requirements.txt
```

## Configuração

1. **Ative o ambiente virtual:**
   ```bash
   source venv/bin/activate
   ```

2. **Inicie o Jupyter Lab:**
   ```bash
   jupyter lab
   ```

3. **Adicione suas imagens:**
   - Coloque imagens de microplásticos na pasta `data/`
   - Formatos suportados: JPG, PNG, TIFF

## Funcionalidades

### Equalização de Histograma (`histogram_equalization.ipynb`)
- **CLAHE (Contrast Limited Adaptive Histogram Equalization)**: Melhora contraste preservando detalhes locais
- **Equalização Padrão**: Equalização global tradicional
- **Comparação Visual**: Original colorida, escala de cinza, equalizada e histogramas
- **Controles Interativos**: Ajuste de limite de corte e tamanho de bloco em tempo real

### Ajustes Interativos (`interactive_adjustments.ipynb`)
- **Matiz (Hue)**: Rotação da roda de cores (-180° a +180°)
- **Saturação**: Intensidade das cores (0x a 3x)
- **Contraste**: Diferença entre tons claros e escuros (0x a 3x)
- **Visualização em Tempo Real**: Comparação lado a lado original vs ajustada

## Funções OpenCV Utilizadas

### Carregamento e Conversão:
- `cv2.imread()`: Carrega imagens do disco
- `cv2.cvtColor()`: Converte entre espaços de cor (BGR↔RGB↔HSV↔GRAY)

### Equalização de Histograma:
- `cv2.equalizeHist()`: Equalização padrão global
- `cv2.createCLAHE()`: Cria objeto CLAHE com parâmetros
- `clahe.apply()`: Aplica CLAHE em imagem escala de cinza

### Manipulação de Cores:
- **Espaço HSV**: Separação de matiz, saturação e brilho
- **Operações matemáticas**: Módulo, multiplicação e clipping
- **Preservação de ranges**: Manutenção de valores válidos (0-255, 0-179°)

## Uso

1. **Equalização de Histograma:**
   - Abra `notebooks/histogram_equalization.ipynb`
   - Use os sliders para ajustar parâmetros CLAHE
   - Compare métodos padrão vs CLAHE
   - Analise histogramas antes e depois

2. **Ajustes de Cor:**
   - Abra `notebooks/interactive_adjustments.ipynb`
   - Ajuste matiz, saturação e contraste
   - Visualize mudanças em tempo real
   - Experimente diferentes combinações

## Dependências

- OpenCV 4.10.0.84 - Processamento de imagens
- NumPy 2.1.1 - Operações matemáticas
- Matplotlib 3.9.2 - Visualização
- Jupyter Lab - Ambiente interativo
- Pillow 10.4.0 - Manipulação adicional de imagens
- ipywidgets - Controles interativos

## Vantagens para Análise de Microplásticos

- **CLAHE**: Preserva detalhes finos das partículas
- **Controle de Ruído**: Reduz amplificação de ruído de fundo
- **Ajustes Precisos**: Controles interativos para otimização
- **Comparação Visual**: Análise antes/depois facilitada
- **Flexibilidade**: Suporte a múltiplos formatos de imagem
