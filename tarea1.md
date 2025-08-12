# Tarea (12/08/2025)
### Realizar un algoritmo en el que se pregunte la fecha de nacimiento del usuario, preguntar la fecha actual, y calcular con los datos anteriores la edad de la persona.

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
