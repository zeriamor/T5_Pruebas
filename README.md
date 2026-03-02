# T5_Pruebas
### Ejercicio 1 - calcularPrecioFinal()

**Método:**
```java
public static int calcularPrecioFinal(int precioBase, int descuento) {
    return precioBase - (precioBase * descuento / 100);
}

ID	   Entrada(precioBase, descuento)	   Resultado esperado	    Oráculo
TC01	(100, 10)	                         90	                    Valor esperado: 100 - 10 = 90
TC02	(100, 15)	                         85	                    100 - (100*15/100=15) = 85
TC03	(200, 0)	                         200	                  precioBase - 0 = precioBase
TC04	(150, 100)	                       0	                    precioBase - precioBase = 0
TC05	(0, 50)	                           0	                    Cero con cualquier descuento da cero
TC06	(100, 120)	                       -20	                  El método permite precios negativos
TC07	(-50, 10)	                         -55	                  Opera correctamente con negativos
TC08	(100, -10)	                       110	                  Descuento negativo = incremento

### Ejercicio 2  

**¿Qué ocurre si descuento es negativo?**
El método interpreta un descuento negativo como un recargo. Por ejemplo, (100, -10) da 110, que es como aplicar un +10% al precio.

**¿Y si es mayor que 100?**
El método permite descuentos superiores al 100%, dando precios negativos. Por ejemplo, (100, 120) da -20.

**¿El método debería permitir esos valores?**
No, en un sistema real no tendría sentido un precio negativo ni un descuento negativo. Lo lógico sería validar las entradas y lanzar una excepción si son inválidas.

### Ejercicio 3 - Mejora del método

```java
public static int calcularPrecioFinal(int precioBase, int descuento) {
    if (precioBase < 0) {
        throw new IllegalArgumentException("El precio base no puede ser negativo");
    }
    if (descuento < 0 || descuento > 100) {
        throw new IllegalArgumentException("El descuento debe estar entre 0 y 100");
    }
    return precioBase - (precioBase * descuento / 100);
}
/*Así validamos que:
precioBase >= 0;
descuento esté entre 0 y 100;
si no, lanzar IllegalArgumentException
*/
