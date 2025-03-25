# Prueba Técnica: Evaluación del Pensamiento Crítico

## Contexto de Negocio

El banco Davivienda está interesado en potenciar la automatización de tareas y procesos mediante el uso de herramientas de Inteligencia Artificial (IA). Para ello, busca capacitar a su personal en habilidades relacionadas con IA y modelos de lenguaje (LLMs), con el objetivo de resolver problemas complejos y reducir la procrastinación derivada de la falta de claridad en objetivos.

Se espera que, al abordar esta prueba, hagas uso de plataformas de IA como ChatGPT o Gemini para respaldar tu proceso de pensamiento y programación, incluso si no posees un conocimiento previo profundo de estas tecnologías. Precisamente, la intención es evaluar la forma en que aplicas estas herramientas para enfrentar un problema y cómo estructuras el flujo de trabajo.


## Contexto del Problema

En el mundo laboral, la procrastinación y los flujos de trabajo desordenados son un fenómeno común, particularmente entre estudiantes universitarios o personal que no ocupa cargos administrativos. Esto suele deberse a la falta de claridad en los objetivos de las tareas que se les asignan.

Supongamos que a un ingeniero de software (SWE) en una startup se le asigna la tarea de construir una página de inicio de sesión para una aplicación web. La situación se vuelve confusa y desalentadora cuando intenta comenzar a programar y surgen preguntas como: 

- "¿Debo construir primero el servidor de autenticación o crear la interfaz frontal?" 
- "¿Cuales son las tareas que tengo que hacer?"

Esas preguntas pueden derivar en cuestiones más pequeñas, volviendo la tarea confusa y fomentando la procrastinación. Este fenómeno es fácilmente replicable en distintas industrias.

Este proyecto busca ayudar en el análisis y la organización de las tareas que los usuarios necesitan completar. Se basa en la capacidad de los Modelos de Lenguaje (LLMs) para descomponer cualitativamente la información con este propósito. Asimismo, implicará un análisis de comportamiento que ajuste el estilo de trabajo según los patrones de cómo los usuarios abordan diferentes tareas, con el fin de generar una sugerencia de flujo de trabajo óptimo.

---

## Orientación para Abordar la Tarea

Ahora, piensa en cómo combinarías varios Modelos de Lenguaje (LLMs) o múltiples interacciones con un mismo LLM para enfrentar este tipo de problema:

- ¿De qué manera aprovecharías diversas respuestas o perspectivas que ofrezca el modelo?
- ¿Qué subtareas o aspectos del problema asignarías a diferentes consultas o instancias del LLM?
- ¿Cómo integrarías estas distintas respuestas para obtener un panorama claro y organizado que facilite el avance de la tarea?

### Ejemplo Gráfico (Usando Mermaid)

Para ilustrar de manera sencilla cómo funcionaría un LLM frente a una tarea puntual, podemos usar el ejemplo de "contar un chiste".

```mermaid
flowchart LR
    A((Entrada: Por favor, cuéntame un chiste.)) --> B[LLM procesa la solicitud]
    B --> C{Verificación interna}
    C -->|¿Es apropiado?| D[LLM genera el chiste]
    D --> E((Salida: Chiste generado))
```

[![](https://mermaid.ink/img/pako:eNo9kUtOwzAQhq9izaqV0ipp0jRkAaKPXSshkFhAWIzsSWqR2NXE4dX2QKw5ABK9GGla8Moz_zffWPIWpFUEKeSlfZVrZCeWt5kR7bnu9RbGMSpMxY1lkeOLZU_I5vBpHFYkGiPkWteOhv2-GAwuxfRxuVyJDVtJNYoSRW1LLbVr1NNJOe2w2faeWOdaotSHLyO0ccQG9ydmdmR2P9-LWmCr2mhU9mon5p27IEOMgsrz5rN33nkXvd4dlvr43lmXnnFl-33woGCtIHXckAcVcYXHErZHQwZuTRVlkLZXhfycQWb27cwGzYO11d8Y26ZYQ5pjWbdVs1HoaK6xYKz-u0xGEc9sYxykQRx0Eki38AZplAzD8SjywyDwx6MwvvDgvYUm8TAZRXGQjMIwafPx3oOPbq0_TAI_CSZt5MeRP44jD0hpZ3l1-jZpTa4L2P8CURuPuA?type=png)](https://mermaid.live/edit#pako:eNo9kUtOwzAQhq9izaqV0ipp0jRkAaKPXSshkFhAWIzsSWqR2NXE4dX2QKw5ABK9GGla8Moz_zffWPIWpFUEKeSlfZVrZCeWt5kR7bnu9RbGMSpMxY1lkeOLZU_I5vBpHFYkGiPkWteOhv2-GAwuxfRxuVyJDVtJNYoSRW1LLbVr1NNJOe2w2faeWOdaotSHLyO0ccQG9ydmdmR2P9-LWmCr2mhU9mon5p27IEOMgsrz5rN33nkXvd4dlvr43lmXnnFl-33woGCtIHXckAcVcYXHErZHQwZuTRVlkLZXhfycQWb27cwGzYO11d8Y26ZYQ5pjWbdVs1HoaK6xYKz-u0xGEc9sYxykQRx0Eki38AZplAzD8SjywyDwx6MwvvDgvYUm8TAZRXGQjMIwafPx3oOPbq0_TAI_CSZt5MeRP44jD0hpZ3l1-jZpTa4L2P8CURuPuA)

#### ¿Qué es LangChain?
LangChain es una biblioteca en Python que facilita la creación de flujos de trabajo (cadenas) para interactuar con modelos de lenguaje. Permite combinar diferentes componentes —como prompts, modelos y herramientas externas— con el fin de construir aplicaciones que aprovechen de manera óptima las capacidades de los LLM.

#### ¿Qué es un Prompt?
Un prompt es la instrucción o mensaje de texto que se envía al modelo de lenguaje. En pocas palabras, indica al LLM qué se le está pidiendo, brindándole el contexto y las guías necesarias para generar una respuesta coherente.

#### Ejemplo de uso con LangChain

Para poner este flujo en práctica, podrías usar la librería [LangChain](https://github.com/hwchase17/langchain) de la siguiente manera:

```python
from langchain.llms import OpenAI

# Inicializa el modelo (ej. GPT-3, GPT-4, etc.) con tu llave de API.
llm = OpenAI(api_key="TU_API_KEY")

# Define el prompt que representa la entrada "Por favor, cuéntame un chiste."
prompt = "Por favor, cuéntame un chiste."

# Envía la solicitud al LLM
response = llm(prompt)

# Imprime la respuesta generada
print(response)
```

En este pequeño ejemplo, el LLM sólo recibe la entrada ("Por favor, cuéntame un chiste") y genera una respuesta directa sin realizar un paso de verificación o filtrado. Por ello, no se alinea totalmente con el diagrama de verificación interna mostrado arriba, donde se ilustra un proceso más completo. 

Para emular una verificación interna (como se ve en el diagrama), se podrían añadir pasos adicionales en LangChain que analicen si la solicitud del usuario es adecuada o cumple con ciertas políticas, antes de generar la respuesta final. De esta forma, el flujo se parecería más al representado en el diagrama y se ajustaría mejor a un sistema de control y moderación de contenidos.

## Objetivo del Ejercicio

El objetivo de esta prueba técnica es que, con base en la situación descrita, diseñes de forma creativa una estrategia o flujo de trabajo que permita abordar y resolver el problema planteado. Deberás elaborar un diagrama (por ejemplo, usando Mermaid) o una secuencia de pasos para:

1. Descomponer el problema principal en tareas o sub-problemas más pequeños.
2. Determinar cómo podrían interactuar uno o varios LLMs para dar soporte en cada sub-problema.
3. Integrar las respuestas o soluciones generadas, a fin de diseñar un flujo de trabajo coherente y centrado en evitar la procrastinación.

Se evaluará tu capacidad para:

- Pensar críticamente y organizar información compleja.
- Fundamentar cómo y por qué emplearías LLMs o herramientas similares en distintas fases del proceso.
- Presentar tu propuesta de manera clara, ya sea en forma de diagrama Mermaid o a través de una lista de pasos organizados.

## Entregable

El entregable final deberá ser un _notebook_ en Python que implemente la estrategia diseñada. Para ello, se recomienda hacer uso de la documentación oficial de LangChain disponible en:

[https://python.langchain.com/docs/tutorials/llm_chain/](https://python.langchain.com/docs/tutorials/llm_chain/)

Dentro de este _notebook_, deberás:

- Explicar paso a paso la lógica detrás de tu propuesta.
- Integrar las subtareas y la secuencia de consultas a uno o varios LLMs.
- Mostrar cómo se aprovecharía LangChain para desarrollar el flujo de trabajo.

Así, demostrarás tu capacidad de combinar teoría y práctica para abordar problemas complejos haciendo uso de modelos de lenguaje.

