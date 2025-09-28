# Documentación del código los lenguaje principales

La documentación del código de estos lenguajes se realiza principalmente mediante **comentarios** en el código fuente, siguiendo **convenciones específicas** para que las herramientas de documentación puedan generar referencias automáticamente. 

---

## Python: Docstrings

En Python, el método principal para documentar código son las **docstrings** (cadenas de documentación).

* **¿Qué son?**
  Cadenas literales encerradas en **triple comillas** (`"""` o `'''`) que aparecen como la primera instrucción dentro de un módulo, clase, función o método.

* **Propósito:**
  Describen lo que hace el código y cómo usarlo: argumentos, lo que devuelve, y excepciones que pueda lanzar.

* **Acceso:**
  Están disponibles en tiempo de ejecución mediante el atributo especial `__doc__` y son utilizadas por herramientas como **Sphinx** o **pdoc**.

* **Formatos Comunes:**

  * **reStructuredText (reST):** Nativo de Sphinx.
  * **NumPy Style:** Claro y conciso, usado en ciencia de datos.
  * **Google Style:** Secciones bien definidas para parámetros, retornos, etc.

**Ejemplo (Google Style):**

```python
def calcular_area_circulo(radio):
    """
    Calcula el área de un círculo.

    Args:
        radio (float): El radio del círculo.

    Returns:
        float: El área calculada.
        
    Raises:
        TypeError: Si el 'radio' no es numérico.
    """
    if not isinstance(radio, (int, float)):
        raise TypeError("El radio debe ser un número.")
    return 3.14159 * (radio ** 2)
```

---

## JavaScript: JSDoc

En JavaScript, la convención más popular para documentar es **JSDoc**.

* **¿Qué es?**
  Un sistema de marcado basado en **comentarios multilínea** (`/** ... */`) que utiliza **etiquetas especiales** (`@param`, `@returns`, `@type`, etc.).

* **Propósito:**
  Documentar funciones, clases, tipos de datos, parámetros y valores de retorno. Mejora la autocompletación en IDEs y permite generar documentación con herramientas como **JSDoc**.

* **Ubicación:**
  Se coloca inmediatamente antes del código que describe (función, clase, método, etc.).

**Ejemplo:**

```javascript
/**
 * Suma dos números.
 * @param {number} num1 El primer número a sumar.
 * @param {number} num2 El segundo número a sumar.
 * @returns {number} La suma de los dos números.
 */
function sumar(num1, num2) {
    return num1 + num2;
}
```

---

## PHP: PHPDoc

En PHP se utiliza **PHPDoc**, muy parecido a JSDoc y Javadoc (Java).

* **¿Qué es?**
  Un estándar de documentación que emplea **comentarios multilínea especiales** (`/** ... */`) con **etiquetas** (`@param`, `@return`, `@var`, `@throws`, etc.).

* **Propósito:**
  Documentar clases, métodos, propiedades y variables. Es útil para **type hinting** en PHP moderno y para generar documentación con **phpDocumentor**.

* **Ubicación:**
  Se coloca inmediatamente antes del elemento que se documenta.

**Ejemplo:**

```php
<?php

/**
 * Clase para manejar operaciones matemáticas básicas.
 */
class Calculadora {
    
    /**
     * Resta un número de otro.
     *
     * @param float $minuendo El número del que se resta.
     * @param float $sustraendo El número a restar.
     * @return float El resultado de la resta.
     * @throws \InvalidArgumentException Si algún argumento no es numérico.
     */
    public function restar(float $minuendo, float $sustraendo): float {
        return $minuendo - $sustraendo;
    }
}

?>
```

