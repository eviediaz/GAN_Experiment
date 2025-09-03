# DCGAN en Fashion-MNIST  

Este proyecto implementa y compara tres configuraciones de **Deep Convolutional GANs (DCGANs)** entrenadas sobre el dataset **Fashion-MNIST**, con el objetivo de evaluar cómo las variaciones en el tamaño del espacio latente (*z_dim*) y el batch size influyen en la calidad de las imágenes generadas.  

## ✨ Características principales  
- Implementación de **3 configuraciones ligeras** de DCGAN (A, B y C).  
- Entrenamiento sobre Fashion-MNIST (imágenes en escala de grises de 10 categorías de ropa).  
- Evaluación mediante métricas específicas para GANs:  
  - **FID (Frechet Inception Distance)**  
  - **KID (Kernel Inception Distance)**  
  - **IS (Inception Score: mean ± std)**  
- Visualizaciones:  
  - Rejilla 8×8 de imágenes generadas (inicio, mitad y final del entrenamiento).  
  - Comparación “**Generada vs. Real más parecida**”.  
  - Gráficas de pérdidas (Generador y Discriminador).  
  - Barras comparativas de FID, KID e IS.  
  - Radar de métricas normalizadas.  

## ⚙️ Configuraciones probadas  

| Configuración | z_dim | Batch size | Épocas |  
|---------------|-------|------------|--------|  
| **A**         | 100   | 128        | 30     |  
| **B**         | 50    | 64         | 30     |  
| **C**         | 200   | 128        | 30     |  

## 📊 Resultados principales  

| Configuración | FID (eval) | KID (eval) | IS (eval)        | Obs. destacadas |  
|---------------|------------|------------|------------------|-----------------|  
| **A (z=100)** | 0.0276     | 0.0394     | 3.50 ± 0.30      | Valores intermedios, pérdida G con picos (~9). |  
| **B (z=50)**  | 0.0209     | **0.0276** | 3.47 ± 0.36      | Mejor KID, pero pérdida G inestable (pico ~19). |  
| **C (z=200)** | **0.0139** | 0.0304     | **3.54 ± 0.22**  | Más balanceada, mejor FID e IS, curvas más estables. |  

✅ La **Configuración C (z=200)** fue la más óptima y consistente.  
✅ La **Configuración B (z=50)** destacó en KID, pero mostró mayor inestabilidad.  

## 📂 Estructura del proyecto  
├── checkpoints/ # Modelos entrenados (.pth)
├── outputs/ # Imágenes generadas durante entrenamiento
├── results/ # Comparaciones y evaluaciones
├── DiazQuevedoEvieNataly_DL_Informe.pdf # Informe del proyecto
├── DiazQuevedoEvieNataly_DeepLearning_GAN.ipynb # Notebook con código
└── README.md # Este archivo


