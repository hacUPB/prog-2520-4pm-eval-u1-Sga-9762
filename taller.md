# Taller 14/08/2025
## Ejercicios con condicionales
> 1. **Verificación de peso de despegue**

    En una pista de pruebas de aeronaves, el sistema debe verificar si el peso total de la aeronave, incluyendo combustible y carga, supera el límite máximo permitido para el despegue. Dependiendo del resultado, el sistema deberá indicar si la aeronave está lista para despegar o si debe reducir carga o combustible.

### Pseudocódigo:
```
Inicio
    Leer MTOW
    Leer FLWG
    Leer PAYLOAD
    TOW = FLWG + PAYLOAD
    Si TOW <= MTOW
        Mostrar "Peso total de despegue no supera el máximo establecido. Autorizado a despegar!"
    Si no
        Mostrar "Peso maximo de despegue SUPERADO. ¡Despegue no autorizado! Reduzca la carga y/o el combustible para poder despegar."
    Fin Si
Fin
```

### Tabla de variables:
|Entrada| Descripción  | Salida | Descripción | Intermedia | Descripción | Control | Descripción | 
|------|-----------| ---- | ---- | ---- | ---- | ---- | ----- |
| MTOW | Peso máximo de despegue | - | - | - | TOW | Operación suma entre FLWG y PAYLOAD |- |- |
| FLWG| Peso del combustible |  - | - | - | - | - |- |- |
|PAYLOAD| Peso de la carga | - | - | - | - | - |- |- |




> 2. **Control de temperatura del motor**
    
    Durante una inspección de rutina, se mide la temperatura de un motor de turbina. Si la temperatura es mayor a un valor crítico, se debe indicar "Peligro: sobrecalentamiento". Si está dentro del rango seguro, indicar "Operación normal". Si es demasiado baja, indicar "Motor frío – Calentar antes de operar".

### Pseudocódigo:
```
Inicio
    Leer MAXEGT
    Leer MINEGT
    Leer EGT
    Si EGT > MAXEGT
        Mostrar "Peligro: SOBRECALENTAMIENTO"
    Si EGT > MINEGT
        Mostrar "Operación normal"
    Si no
        Mostrar "Motor frío - Calentar antes de operar."
Fin
```

### Tabla de variables:

|Entrada| Descripción  | Salida | Descripción | Intermedia | Descripción | Control | Descripción | 
|------|-----------| ---- | ---- | ---- | ---- | ---- | ----- |
| MAXEGT | Límite maximo de temperatura | - | - | - | - | - |- |- |
| MINEGT| Límite mínimo de temperatura |  - | - | - | - | - |- |- |
|EGT | Temperatura de motor | - | - | - | - | - |- |- |

## Ejercicios con bucles:

> 1. **Registro de altitudes de vuelo**
    
    Un sistema debe registrar la altitud de vuelo cada 10 minutos durante una hora y mostrar todas las mediciones al final.

### Pseudocódigo:
```
Inicio
   i = 0 
    Mientras i <= 5
        Leer altitud
        Altitud[i] = altitud
        Mostrar Altitud[i]
        i = i + 1
    Fin Mientras
Fin
```

### Tabla de variables:

|Entrada| Descripción  | Salida | Descripción | Intermedia | Descripción | Control | Descripción |
|------|-----------| ---- | ---- | ---- | ---- | ---- | ----- |
| altitud | Altitud de vuelo | Altitud[i] | Altitud registrada en el intervalo | - | - | i | Contador de intervalo (10 minutos) | 



> 2. **Control de combustible en pruebas**
    
    Durante un ensayo en banco de un motor a reacción, se mide el nivel de combustible cada minuto y se detiene el registro cuando el combustible baja del 10%. Mostrar el tiempo total de operación antes de llegar a ese punto.

### Pseudocódigo:
```
Inicio
i = 0
FUEL = 100
    Mientras FUEL > 10 y FUEL <= 100
        Leer porcentaje
        FUEL = FUEL - porcentaje
        i = i + 1
    Fin Mientras
    t_ops = i
    Mostrar t_ops
Fin
```

### Tabla de variables:

|Entrada| Descripción  | Salida | Descripción | Intermedia | Descripción | Control | Descripción |
|------|-----------| ---- | ---- | ---- | ---- | ---- | ----- |
| - | -  | t_ops | Tiempo de operación (mostrado) | FUEL | Nivel de combustible | i | Tiempo de operación | 

## Ejercicios con bucle y condicionales

> 1. **Detección de turbulencia en trayecto**
    
    Un sensor mide la aceleración vertical de la aeronave en intervalos de un segundo durante un trayecto de 2 minutos. Si el valor medido supera un umbral, indicar que se ha detectado turbulencia en ese instante. Al final, mostrar cuántas turbulencias se detectaron.

### Pseudocódigo:
```
Inicio
i = 0
TBCT = 0
Leer max_turbulence
    Desde i = 0 hasta i = 119
        Leer VACCL
        i = i + 1
        Si VACC > max_turbulence
            Mostrar "Turbulencia detectada. Máximo umbral superado."
            TBCT = TBCT + 1
        Fin Si
    Fin Desde
Mostrar TBCT 
Fin
```

### Tabla de variables:

|Entrada| Descripción  | Salida | Descripción | Intermedia | Descripción | Control | Descripción |
|------|-----------| ---- | ---- | ---- | ---- | ---- | ----- |
| max_turbulence | Umbral establecido de turbulencia | TBCT | Conteo de detección de turbulencia | - | - | i | Control de intervalo (segundos) | 
| VACCL | Aceleración vertical |

> 2. **Control de temperatura en cabina**
    
    Un sistema mide cada 5 minutos la temperatura en cabina durante una hora. Si en algún momento se detecta una temperatura mayor a 27°C o menor a 18°C, debe indicar que se active el sistema de climatización.

### Pseudocódigo:
```
Inicio

    Desde i = 0 hasta i = 11
        i = i + 1
        Leer cab_temp
            Si cab_temp > 27 y cab_temp < 18
                Mostrar "Temperatura de cabina diferente al rango establecido. Activar el sistema de climatización inmediatamente."
            Fin Si
    Fin Desde
Fin
```
### Tabla de variables:

|Entrada| Descripción  | Salida | Descripción | Intermedia | Descripción | Control | Descripción |
|------|-----------| ---- | ---- | ---- | ---- | ---- | ----- |
| cab_temp | Temperatura en cabina | - | - | - | - | i | Control de intervalo (5 minutos) | 


> 3. **Simulación de conteo de pasajeros**
    
    Durante el abordaje, un sistema cuenta a los pasajeros que ingresan. Si el número total supera la capacidad máxima, el sistema debe detener el conteo y mostrar un mensaje de alerta.

### Pseudocódigo:
```
Inicio
i = 0
Leer max_pax
    Si i <= max_pax
        Mientras i < max_pax
            i = i + 1
            Mostrar i
        Fin mientras
    Si no
        Mostrar "Capacidad de pasajeros máxima alcanzada. Detener abordaje INMEDIATAMENTE."
    Fin Si
Fin
```
### Tabla de variables:
|Entrada| Descripción  | Salida | Descripción | Intermedia | Descripción | Control | Descripción |
|------|-----------| ---- | ---- | ---- | ---- | ---- | ----- |
| max_pax | Capacidad máxima de pasajeros | - | - | - | - | i | Control de intervalo (1 x pasajero) | 


## Ejercicios adicionales:

> 1. **Planificación de misión satelital**
    
    Desarrollar un algoritmo que reciba datos de consumo de energía por hora de un satélite durante un día completo. Si en cualquier hora el consumo excede un límite crítico, debe registrarse como una alerta. Al final, mostrar el consumo total y el número de alertas generadas.

### Pseudocódigo:
```
Inicio
Leer ConsumoLimite
ALRT = 0
ConsumoTotal = 0
    Desde i = 0 hasta i = 23
        Leer energycsp
        ConsumoEnergia[i] = energycsp
        ConsumoTotal = ConsumoTotal + ConsumoEnergia
        i = i + 1
        Si ConsumoEnergia > ConsumoLimite
            Mostrar "¡Alerta! Consumo límite superado."
            ALRT = ALRT + 1
        Fin Si
    Fin Desde
Mostrar ConsumoTotal
Mostrar ALRT
Fin
```
### Tabla de variables:

|Entrada| Descripción  | Salida | Descripción | Intermedia | Descripción | Control | Descripción |
|------|-----------| ---- | ---- | ---- | ---- | ---- | ----- |
| ConsumoLimite | Límite establecido de consumo de energía | ConsumoTotal | Consumo total de energía | - | - | i | Control de intervalo (1 hora) | 
| energycsp | Consumo de energía leído en el intervalo | ALRT | Registro de alertas de consumo | - | - | - | - | - |


> 2. **Simulación de carga y balanceo de aeronave**
    
    Una aeronave tiene varias bodegas de carga. El sistema debe permitir ingresar el peso cargado en cada bodega y verificar que:
    
    - El peso total no exceda el máximo permitido.
    - Ninguna bodega individual supere su límite.
        
        Mostrar mensajes de advertencia si alguna condición no se cumple.

### Pseudocódigo:
```
Inicio

Fin
```
### Tabla de variables:



