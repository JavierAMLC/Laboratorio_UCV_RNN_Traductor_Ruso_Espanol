# Laboratorio_UCV_RNN_Traductor_Ruso_Espanol

### Preguntas de Análisis Resueltas

1. **¿Qué es una secuencia en el contexto de redes neuronales recurrentes?**
   - Es una sucesión ordenada de datos vinculados temporal o lógicamente entre sí, donde el orden de los elementos determina el significado del conjunto. En texto, las palabras y letras forman secuencias lineales de longitud variable.

2. **¿Qué diferencia existe entre una RNN simple y una LSTM?**
   - Una RNN tradicional sufre del problema del desvanecimiento del gradiente (*vanishing gradient*), impidiéndole recordar dependencias a largo plazo. Una LSTM soluciona esto introduciendo celdas de memoria gobernadas por compuertas (*gates*) de entrada, salida y olvido, permitiendo modular el flujo de información a largo plazo.

3. **¿Qué función cumple el encoder?**
   - El codificador lee la secuencia de entrada en el idioma original (ruso) y comprime secuencialmente toda su semántica en un vector de características de tamaño fijo conocido como *vector de contexto*.

4. **¿Qué función cumple el decoder?**
   - El decodificador extrae el vector de contexto generado por el encoder y, usando sus propios estados ocultos autoregresivos, reconstruye la frase en el idioma de destino (español) palabra por palabra.

5. **¿Por qué se usan los tokens `<start>` y `<end>`?**
   - El token `<start>` actúa como el disparador inicial para que el decodificador comience a predecir la primera palabra semántica. El token `<end>` sirve como criterio de parada para terminar el bucle predictivo dinámico.

6. **¿Por qué el modelo funciona mejor con frases que ya vio durante el entrenamiento?**
   - Debido al tamaño extremadamente reducido del dataset, el modelo tiende al sobreajuste (*overfitting*), memorizando las asignaciones textuales en lugar de generalizar las estructuras gramaticales abstractas subyacentes.

7. **¿Qué dificultades presenta traducir del ruso al español?**
   - El ruso posee características morfológicas complejas como las declinaciones por casos gramaticales (seis casos), un alfabeto cirílico diferente y un orden de palabras extremadamente flexible, lo que dificulta el mapeo directo uno a uno con el español.

8. **¿Por qué este enfoque fue importante antes de la aparición de Transformers?**
   - Rompió el paradigma de las traducciones basadas puramente en reglas estadísticas ríguidas, permitiendo modelar frases enteras como entidades de longitud variable y continuas de manera matemática.

9. **¿Por qué este modelo no puede competir con Google Translate o DeepL?**
   - Google Translate y DeepL operan sobre arquitecturas avanzadas basadas en *Transformers* (Mecanismos de Atención masiva) entrenados con miles de millones de parámetros y gigabytes de datos lingüísticos reales.

10. **¿Qué necesitaría mejorar para acercarse a un traductor real?**
    - Incrementar masivamente el corpus de entrenamiento a millones de pares lingüísticos, implementar mecanismos de atención (*Attention Mechanisms*) para evitar la pérdida de información en secuencias largas, y migrar hacia arquitecturas de tipo *Transformer*.
