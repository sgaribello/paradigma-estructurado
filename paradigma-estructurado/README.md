# Paradigma Estructurado — Sistema de Control de Gastos Personales

Implementación del Sistema de Control de Gastos Personales bajo el **paradigma
estructurado** en Python, para la actividad de seguimiento de paradigmas de
programación con trabajo colaborativo en Git y GitHub.

**Integrante responsable:** Santiago
**Rama de trabajo:** `feature/paradigma-estructurado`
**Paradigma complementario del equipo:** Orientado a Objetos (Angélica Ruiz)

---

## Descripción del problema

Aplicación para la gestión de finanzas personales que administra los registros
financieros de un usuario. Todas las funcionalidades están implementadas con
control de flujo secuencial y modular, sin clases personalizadas ni librerías
de alto nivel.

### Funcionalidades implementadas

| # | Funcionalidad | Descripción |
|---|---|---|
| 1 | Registrar gasto | Captura concepto, monto y categoría |
| 2 | Mostrar listado de gastos | Presenta todos los registros de forma organizada |
| 3 | Calcular gasto total acumulado | Suma el valor de todos los egresos |
| 4 | Mostrar el gasto de mayor valor | Identifica el registro con el monto más alto |
| 5 | Mostrar gastos mayores a un monto | Filtra por umbral ingresado por el usuario |
| 6 | Buscar gasto por concepto | Búsqueda por subcadena en la descripción |

---

## Enfoque del paradigma

El paradigma estructurado organiza el programa como una secuencia de pasos
ejecutados en orden, descompuestos en funciones o procedimientos independientes.
Los datos se mantienen en estructuras nativas del lenguaje y la lógica se
controla mediante condicionales y ciclos explícitos.

## Elementos del paradigma aplicados

### Variables globales y locales
- `gastos`: variable global que contiene la colección de todos los registros.
- `total`, `resultados`, `encontrados`: variables locales dentro de cada función.

### Estructuras condicionales (if / else)
Se emplean para validar las entradas del usuario, determinar el gasto de mayor
valor, seleccionar la opción del menú y comprobar coincidencias en la búsqueda.

### Ciclos (while, for)
- `while`: validación de datos numéricos y bucle principal del menú.
- `for`: recorrido de la colección en listado, total, máximo, filtro y búsqueda.

### Funciones independientes con paso de parámetros
Cada funcionalidad está implementada en una función que recibe la lista de
gastos como parámetro, evitando el uso de clases:

| Función | Responsabilidad |
|---|---|
| `registrar_gasto(lista_gastos)` | Captura y agrega un nuevo gasto |
| `mostrar_gastos(lista_gastos)` | Presenta el listado completo |
| `calcular_total(lista_gastos)` | Suma los montos registrados |
| `mostrar_gasto_mayor(lista_gastos)` | Identifica el monto más alto |
| `filtrar_por_monto(lista_gastos)` | Filtra por umbral |
| `buscar_por_concepto(lista_gastos)` | Búsqueda por subcadena |

### Estructuras de datos nativas
La colección se almacena como una lista de diccionarios, donde cada gasto tiene
las claves `concepto`, `monto` y `categoria`. No se emplean clases
personalizadas ni librerías de alto nivel para el procesamiento.

### Menú secuencial interactivo en consola
La función `main()` controla el flujo con un ciclo `while` que despliega el
menú y despacha cada opción a su función correspondiente.

---

## Estructura

```text
estructurado/
├── README.md
└── gastos_estructurado.py
```

## Ejecución

Requiere **Python 3.8 o superior**. No usa dependencias externas.

```bash
python gastos_estructurado.py
```

---

## Ventajas y limitaciones del paradigma

**Ventajas**
- Código directo y fácil de seguir en programas pequeños.
- Bajo nivel de abstracción, sin estructuras adicionales.
- Rápido de implementar y de leer secuencialmente.

**Limitaciones**
- Los datos globales dificultan el control del estado en programas grandes.
- Poca reutilización y escalabilidad frente al paradigma orientado a objetos.
- El mantenimiento se vuelve complejo cuando crece el número de funciones.
