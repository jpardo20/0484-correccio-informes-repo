# Informe de correcció: GRUP 1

- Timestamp: `2025-11-11T08:51:51.780Z`
- Activitat: `validacio-mer-agencia`
- Compleció: **100.0%**
- Respostes correctes: **7/10**
- Escenaris amb discrepància: **3, 5, 6**


## Detall per escenari
### Escenari 1
- Resposta equip: **Sí** · Esperat: **Sí** ✅
- Text o imatge a 'On ...': Sí
  - **Text aportat:**

```
TOURS (1) ———< programa >——— VIATGES (N)
```

  - **Justificació:**
  > El modelo E/R contempla ya que un tour puede dar lugar a múltiples viajes (relación 1:N).
  > Por ejemplo, el tour "Italia Essencial" puede programar tres viajes (V1, V2, V3) en meses diferentes, todos ellos vinculados al mismo código Tour.

### Escenari 2
- Resposta equip: **Sí** · Esperat: **Sí** ✅
- Text o imatge a 'On ...': Sí
  - **Text aportat:**

```
representado en el tributo ordre entre viatges y punts_ruta
```

  - **Justificació:**
  > La relación inclou entre VIATGES y PUNTS_RUTA permite definir la secuencia de los puntos de la ruta ordre

### Escenari 3
- Resposta equip: **Sí** · Esperat: **No** ❌
- Text o imatge a 'On ...': Sí
  - **Text aportat:**

```
TOURS (1) ———< inclou >——— PUNTS_RUTA (N)
```

  - **Justificació:**
  > TOURS se relaciona con RUTAS mediante la relación "orden" (1:N).
  > RUTAS se relaciona con PUNTS_RUTA mediante "programaPuntos" (1:N).
  > Esto implica que:
  > Varios TOURS pueden compartir una misma RUTA.
  > Y una RUTA puede contener puntos como Roma, que aparecen en varios tours.
  > Por tanto, si Roma es un PUNT_RUTA dentro de una RUTA que es compartida por más de un TOUR, el modelo lo permite.

### Escenari 4
- Resposta equip: **Sí** · Esperat: **Sí** ✅
- Text o imatge a 'On ...': Sí
  - **Text aportat:**

```
CLIENT ———< fa >——— RESERVES

RESERVES ———< inclou >——— PARTICIPANTS
```

  - **Justificació:**
  > RESERVAS se relaciona con CLIENTE mediante la relación "corresponde", indicando quién hace la reserva.
  > RESERVAS se relaciona con PARTICIPANTES mediante la relación "fs", con cardinalidad 1:N.
  > Esto permite que:
  > Un cliente (Joan) haga una reserva.

### Escenari 5
- Resposta equip: **Sí** · Esperat: **No** ❌
- Text o imatge a 'On ...': Sí
  - **Text aportat:**

```
PUNTS_RUTA té l’atribut tipusPuntRuta, que pot indicar si el punt és de “visita”, “estada”
```

  - **Justificació:**
  > El diagrama muestra que:
  > PUNTS_RUTA se relaciona con ALLOTACIONES mediante la relación "admet", con cardinalidad (0,N).
  > Esto significa que: Un punto de ruta puede tener un alojamiento asociado

### Escenari 6
- Resposta equip: **Sí** · Esperat: **No** ❌
- Text o imatge a 'On ...': Sí
  - **Text aportat:**

```
RESERVES (N) ———< correspon >——— VIATGES (N)
```

  - **Justificació:**
  > El diagrama muestra que:
  > RESERVAS se relaciona con VIAJES mediante la relación "dataReserva", con cardinalidad (1,1).
  > Esto implica que:
  > Cada reserva está asociada a un único viaje.
  > No es posible, según el modelo actual, que una reserva cubra más de un viaje.

### Escenari 7
- Resposta equip: **Sí** · Esperat: **Sí** ✅
- Text o imatge a 'On ...': Sí
  - **Text aportat:**

```
PUNTS_RUTA (1) ———< admet >——— ALLOTJAMENTS (N)
```

  - **Justificació:**
  > El diagrama muestra una relación "admet" entre PUNTS_RUTA y ALOJAMIENTOS, con cardinalidad (0,N).
  > Esto significa que:
  > Un punto de ruta puede admitir varios alojamientos.
  > Por tanto, es totalmente viable que Hotel A y Hotel B estén disponibles para el mismo punto.
  > Además, dado que la relación es opcional, también se pueden tener puntos sin alojamiento .

### Escenari 8
- Resposta equip: **Sí** · Esperat: **Sí** ✅
- Text o imatge a 'On ...': Sí
  - **Text aportat:**

```
CLIENT ———< fa >——— RESERVES
un clinete por difetente reserva(1:N)
```

  - **Justificació:**
  > El diagrama muestra que:
  > CLIENT se relaciona con RESERVes mediante la relación "corresponde", con cardinalidad 1:N.
  > Esto significa que un mismo cliente puede realizar varias reservas.
  > Además:
  > Cada reserva se asocia a un único viaje (relación con VIAtGES).

### Escenari 9
- Resposta equip: **No** · Esperat: **No** ✅
- Text o imatge a 'On ...': Sí
  - **Text aportat:**

```
El modelo actual no
```

  - **Justificació:**
  > El modelo sólo indica qué hoteles son posibles en un punto de ruta, pero no asigna a participantes a alojamientos concretos.

### Escenari 10
- Resposta equip: **Sí** · Esperat: **Sí** ✅
- Text o imatge a 'On ...': Sí
  - **Text aportat:**

```
El modelo actual no tiene ninguna relación o entidad que permita especificar qué participante duerme en qué alojamiento concreto dentro de un punto de ruta y un viaje
```

  - **Justificació:**
  > El modelo E/R ya contempla los atributos necesarios dentro de RESERVES para representar el importe de la señal, la fecha y el estado de confirmación.
