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
