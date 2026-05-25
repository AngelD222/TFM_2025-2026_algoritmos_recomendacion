# TFM_2025-2026_algoritmos_recomendacion
TFM realizado para el máster de IA de la Universidad de Murcia. PPR topológico, filtrado semántico, modelo híbrido y red neuronal

# Sistemas de recomendación en redes sociales sintéticas creadas con IA generativa

Código del Trabajo de Fin de Máster del Máster en Inteligencia Artificial
de la Universidad de Murcia (curso 2025-2026).

El trabajo diseña, implementa y evalúa cuatro algoritmos de recomendación
sobre la red social sintética generada por el simulador de Buitrago López
et al. (2025), cuyo tejido relacional se construye con el algoritmo de
homofilia de López, Pastor-Galindo y Ruipérez-Valiente (2026):

1. **Algoritmo 1 — topológico:** recomendación de cuentas mediante
   Personalized PageRank sobre un grafo dirigido ponderado por amistades e
   interacciones.
2. **Algoritmo 2 — semántico:** filtrado por contenido con embeddings
   `all-MiniLM-L6-v2` y similitud del coseno.
3. **Algoritmo 3 — híbrido:** combinación lineal de señal topológica,
   semántica y psicológica (OCEAN), con pesos calibrados por grid search.
   Incluye una extensión de cuatro dimensiones que añade los intereses
   declarados del usuario.
4. **Algoritmo 4 — neuronal:** perceptrón multicapa que fusiona las mismas
   señales de forma no lineal, entrenado con muestreo negativo.

Todos los modelos se evalúan bajo un protocolo común (partición temporal,
Recall@10, NDCG@10 y diversidad temática) y calibran sus parámetros sobre
un conjunto interno de validación, sin tocar el conjunto de prueba.

## Contenido

- `algoritmos_1_2_3.ipynb` — infraestructura común y Algoritmos 1, 2 y 3
  (incluida la extensión de intereses del Algoritmo 3).
- `red_neuronal.ipynb` — Algoritmo 4 (red neuronal).

## Datos

Los notebooks operan sobre cuatro ficheros CSV exportados por el simulador
(`users.csv`, `friendships.csv`, `interactions.csv`, `messages.csv`). Estos ficheros se encuentran en la carpeta del repositorio `archivos`

## Requisitos

Python 3 con `pandas`, `numpy`, `networkx`, `scikit-learn`,
`sentence-transformers`, `matplotlib`, `pytorch` y `tqdm`.

## Autor

Ángel Franco Rodríguez — TFM dirigido por Alejandro Buitrago López y
José Antonio Ruipérez Valiente.
