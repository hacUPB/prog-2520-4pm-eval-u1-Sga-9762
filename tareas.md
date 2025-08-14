## Tarea 1 (12/08/2025)
Realizar un algoritmo en el que se pregunte la fecha de nacimiento del usuario, preguntar la fecha actual, y calcular con los datos anteriores la edad de la persona.

## Pseudocódigo
```
Inicio
  Mostrar "Introduzca la fecha actual (DD/MM/YYYY)"
  Leer DAct, MAct, AAct
  Mostrar "Introduzca su fecha de nacimiento (DD/MM/YYYY)"
  Leer DNac, MNac, ANac
    Si DAct > 0 y DAct =< 31 y MAct > 0 y MAct =< 12 y AAct > 1900 y DNac > 0 y DNac =< 31 y MNac > 0 y MNac =< 12 y ANac > 1900 y ANac < AAct
        EAños = AAct - ANac
          Si MNac < MAct
              EMes = MAct - MNac
          Si no
              EAños - 1
              EMes = 12 - (MNac - MAct)
          Fin Si
        Leer DiasMes
          Si DiasMes > 0 y DiasMes =< 31
            EDias = DiasMes - DAct
          Fin Si
        Mostrar "Su edad actual es: ", EAños, " años, ", EMes, " meses, ", EDias, " días."
    Fin Si
Fin
```

## Tarea 2
 Realizar el ejercicio 4.8 del libro, teniendo en cuenta la siguiente información: 
 > Se tiene una tarjeta de $10.000.000. Calcular el valor de todas las cuotas sabiendo:
 > 1. Valor de la compra
 > 2. Tasa de interés del 2%
 > 3. Número de cuotas maximas: 36

### Pseudocódigo
```
Inicio
Leer N_artcs
Leer total_artcs
Leer cuotas
  Si cuotas <= 36 y total_artcs <= 10000000
      Si precio_artcs >= 200000
        pr_dcto = total_artcs*0.15
        costoidv_artcs = pr_dcto/N_artcs
        valor_cuota = pr_dcto / (1-(1/(1+0.2))^cuotas)/0.2) -- fórmula del sistema de amortización francés
      Si precio_artcs > 100000
        pr_dcto = total_artcs*0.12
        costoidv_artcs = pr_dcto/N_artcs
        valor_cuota = pr_dcto / (1-(1/(1+0.2))^cuotas)/0.2) -- fórmula del sistema de amortización francés
      Si no
        pr_dcto = total_artcs*0.1
        costoidv_artcs = pr_dcto/N_artcs
        valor_cuota = pr_dcto / (1-(1/(1+0.2))^cuotas)/0.2) -- fórmula del sistema de amortización francés
      Fin Si
  Fin Si
Mostrar pr_dcto
Mostrar costoidv_artcs
Mostrar valor_cuota
Fin
```

```
