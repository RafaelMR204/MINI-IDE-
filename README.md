# Mini IDE Web - Analizador Léxico y Sintáctico

Este proyecto es un IDE web que implementa un analizador léxico, sintáctico y una máquina de Turing. Desarrollado como parte del curso de Compiladores.

## Autor
- **Nombre:** Rafael Monsivais Robles
- **Profesor:** ING Kevin David Molina Gomez

## Características

- 🔍 **Análisis Léxico**: Identifica y clasifica los tokens en el código fuente
- 🌳 **Análisis Sintáctico**: Analiza la estructura gramatical del código
- 🤖 **Máquina de Turing**: Implementación de un simulador de máquina de Turing
- 🎨 **Interfaz Moderna**: Diseño oscuro moderno con editor de código integrado
- 📝 **Editor de Código**: Editor con resaltado de sintaxis

## Requisitos

- Python 3.8 o superior
- Flask
- Navegador web moderno

## Instalación

1. Clonar el repositorio:
```bash
git clone [URL-del-repositorio]
cd [nombre-del-directorio]
```

2. Crear un entorno virtual (recomendado):
```bash
python -m venv venv
```

3. Activar el entorno virtual:
- Windows:
```bash
venv\Scripts\activate
```
- Linux/Mac:
```bash
source venv/bin/activate
```

4. Instalar las dependencias:
```bash
pip install -r requirements.txt
```

## Uso

1. Iniciar el servidor:
```bash
python app.py
```

2. Abrir el navegador y visitar:
```
http://localhost:5000
```

## Funcionalidades

### Análisis Léxico
- Identifica tokens en el código fuente
- Clasifica elementos como variables, operadores, números, etc.
- Muestra errores léxicos encontrados

### Análisis Sintáctico
- Verifica la estructura gramatical del código
- Genera un árbol sintáctico
- Identifica errores en la estructura del código

### Máquina de Turing
- Simula una máquina de Turing
- Procesa cadenas de entrada
- Determina si una cadena pertenece al lenguaje de "humanos" o "robots"

## Estructura del Proyecto

```
mini-ide-web/
├── app.py              # Aplicación principal Flask
├── lexer.py           # Implementación del analizador léxico
├── parser_custom.py   # Implementación del analizador sintáctico
├── turing_machine.py  # Implementación de la máquina de Turing
├── static/           
│   ├── style.css      # Estilos CSS
│   └── script.js      # JavaScript del cliente
├── templates/
│   └── index.html     # Plantilla principal
└── requirements.txt   # Dependencias del proyecto
```

## Tecnologías Utilizadas

- **Backend**: Python, Flask
- **Frontend**: HTML5, CSS3, JavaScript
- **Editor**: CodeMirror
- **Estilos**: Bootstrap 5
- **Iconos**: Bootstrap Icons

## Licencia

Este proyecto está bajo la Licencia MIT. Ver el archivo `LICENSE` para más detalles.

## Lenguaje Personalizado

### Tokens
- **NUMERO**: Números enteros o decimales (`\d+(\.\d+)?`)
- **IDENTIFICADOR**: Nombres de variables (`[a-zA-Z_][a-zA-Z0-9_]*`)
- **OPERADOR**: Operadores aritméticos y lógicos (`[\+\-\*/=<>!]=?|&&|\|\|`)
- **PARENTESIS**: Paréntesis (`[\(\)]`)
- **LLAVE**: Llaves (`[\{\}]`)
- **CORCHETE**: Corchetes (`[\[\]]`)
- **PUNTUACION**: Símbolos de puntuación (`[,;:]`)
- **CADENA**: Cadenas de texto (`"[^"]*"`)
- **COMENTARIO**: Comentarios de línea y bloque (`//.*|/\*[\s\S]*?\*/`)

### Gramática
```
programa    → declaracion*
declaracion → variable_decl | expresion
variable_decl → IDENTIFICADOR "=" expresion
expresion   → literal | IDENTIFICADOR | operacion
operacion   → expresion OPERADOR expresion
literal     → NUMERO | CADENA
```

### Ejemplos Válidos
```javascript
x = 42
nombre = "Juan"
resultado = 10 + 5 * 3
```

### Ejemplos Inválidos
```javascript
42x = 10  // Identificador inválido
= 5       // Falta identificador
x = "texto incompleto  // Cadena sin cerrar
```

## Máquina de Turing
La implementación incluye una Máquina de Turing que clasifica entre Humano y Robot:

### Descripción
- La máquina procesa cadenas compuestas únicamente por los símbolos 'a' y 'b'
- Convierte cada 'a' en 'X' y cada 'b' en 'Y'
- Clasifica la entrada basándose en el último símbolo de la cadena original

### Reglas de Clasificación
- Si termina en 'a': Clasifica como "Humano 🧍"
- Si termina en 'b': Clasifica como "Robot 🤖"
- Cualquier otro caso: "Desconocido ❓"

### Ejemplos Válidos
```
Entrada: "aaab"
Pasos:
1. Posición 0: 'a' → 'X'
2. Posición 1: 'a' → 'X'
3. Posición 2: 'a' → 'X'
4. Posición 3: 'b' → 'Y'
Cinta final: XXXY
Resultado: Robot 🤖

Entrada: "aaa"
Pasos:
1. Posición 0: 'a' → 'X'
2. Posición 1: 'a' → 'X'
3. Posición 2: 'a' → 'X'
Cinta final: XXX
Resultado: Humano 🧍
```

### Ejemplos Inválidos
```
Entrada: "abc"  // Contiene caracteres no válidos
Resultado: Desconocido ❓ (caracteres inválidos)

Entrada: ""     // Cadena vacía
Resultado: Desconocido ❓
```

## Características
- Editor de código con resaltado de sintaxis
- Detección de errores léxicos en tiempo real
- Visualización de tokens por línea
- Árbol sintáctico para código válido
- Simulador de Máquina de Turing integrado
- Interfaz moderna y responsive con Bootstrap
- Tema oscuro para el editor (Monokai)

## Capturas de pantalla
- Pantalla inicial 
![Image Alt](https://github.com/RafaelMR204/MINI-IDE-/blob/3c5da2ac365949300005d5f2a6c35d67a5e7c4ac/Captura%20de%20pantalla%202025-06-02%20095048.png) 
Análisis Lexico
![Image Alt](https://github.com/RafaelMR204/MINI-IDE-/blob/3c5da2ac365949300005d5f2a6c35d67a5e7c4ac/Captura%20de%20pantalla%202025-06-02%20095224.png) 
Análisis Sintactico 
![Image Alt](https://github.com/RafaelMR204/MINI-IDE-/blob/3c5da2ac365949300005d5f2a6c35d67a5e7c4ac/Captura%20de%20pantalla%202025-06-02%20095258.png)
Maquina de Turing
![Image Alt](https://github.com/RafaelMR204/MINI-IDE-/blob/3c5da2ac365949300005d5f2a6c35d67a5e7c4ac/Captura%20de%20pantalla%202025-06-02%20095315.png)
