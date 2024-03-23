# EstacionaTec Multiagent System Parking Lot Simulation
## Demo Link
https://youtu.be/YKGM0njEuI8

## Introduction
Al ir a una plaza es común no encontrar un lugar de estacionamiento cercano al destino al que uno se
dirige. Esto lleva a utilizar más tiempo del necesario al tener que examinar todo el espacio hasta
encontrar un cajón. La situación a resolver es controlar la logística y administración de los cajones
dentro de un estacionamiento de una plaza con varios establecimientos como tiendas. La estrategia
planteada para dar solución es el hacer un sistema de estacionamiento inteligente, en el que los
vehículos puedan llegar a la entrada e indicarle a la o el administrador del estacionamiento a qué
establecimiento se dirigen.  

El estacionamiento de la plaza está dividido en cuatro secciones (A, B, C y
D), cada una se encuentra más cerca de algunos lugares que otros; por lo que, la o el administrador
le asignará un espacio en la sección con el cajón con la mejor prioridad (1 siendo la mejor prioridad y
32 siendo la peor prioridad) disponible. Las prioridades ya están establecidas y no cambian, estas
fueron definidas conforme a qué tan cercano es el establecimiento al cajón. Cuando un carro desee
ingresar a la plaza debe esperar a que la o el administrador le asigne el cajón que ocupará. Los carros
permanecerán un número aleatorio de steps en el cajón de estacionamiento entre 20 y 40 y, una vez
transcurridos, saldrán de este y de la plaza.  

Es decir, mediante la asignación de prioridades a los cajones del estacionamiento y el tener una o un
administrador, se puede eficientar el proceso de encontrar un espacio y dar mejores resultados a los
visitantes de la plaza al ubicarlos cerca del establecimiento que les interesa. 
## Roles
![image](https://github.com/Silvana-Ruiz/Multiagent_System_Parking_Lot/assets/67821436/0ebd60c2-d0f9-4116-a19a-0d114ce8d98a)
## Context and Problem
El buscar un lugar de estacionamiento en plazas o centros comerciales es una tarea tardada e
indeseada para las y los conductores ya que su objetivo es poder rápidamente encontrar el mejor
espacio disponible para así llegar a su destino final. De hecho, en su estudio Shoup [1] analizó el flujo
de los automóviles en varias ciudades del mundo como Detroit, Nueva York y Londres e indicó que la
búsqueda de un lugar para estacionarse puede contribuir hasta en 30% del tráfico. Por lo que, es
posible apreciar la severidad de esta situación para reducir la congestión vehicular y mejorar la
movilidad urbana.  
Otro asunto relevante es que, en ocasiones, el cajón encontrado puede estar ubicado lejos del
establecimiento al que se planea visitar. Por ello, el sistema de multiagentes propuesto tiene como entorno
una plaza con varios lugares como tiendas, junto a estas se encuentra un estacionamiento, el
cual en su entrada cuenta con una o un administrador responsable de indicarle a los carros que
planean ingresar a la plaza qué cajón deben ocupar considerando qué tan cercano es este al
establecimiento que desean visitar y si se encuentra disponible o no. Para ello, se propone asignarle
a cada cajón del estacionamiento una prioridad de acuerdo a los posibles destinos (establecimientos)
de modo que, mientras más pequeño sea el valor que se le asignó al cajón, tiene mayor prioridad
para tal establecimiento; por lo que, la o el administrador buscará en el estacionamiento qué cajón
tiene la mejor prioridad y verificará que se encuentre disponible, si no lo está, buscará la siguiente
mejor prioridad hasta encontrar un cajón libre.  

En [2], una propuesta similar es descrita donde se toman peticiones por parte de la o el conductor
sobre la distancia que desea caminar desde su cajón hasta su destino y un rango del costo que está
dispuesta o dispuesto a pagar. La aplicación móvil de Smart Parking propone un lugar de
estacionamiento al usuario, si este le parece adecuado podrá ser reservado. Además, se explica que,
los usuarios no suelen solicitar un cajón en específico, en vez, sino que trabajan mediante particiones
del área para así asignar cajones en esta si es que su destino está en tal distrito. Este enfoque es
similar al que se propone ya que, se busca proporcionar a las y los conductores un espacio de
estacionamiento lo más cercano considerando otras variables como disponibilidad. A diferencia de
lo propuesto, en el estudio también se considera el costo.  

Los resultados de esta investigación [2] muestran que bajo condiciones de tráfico, estacionamientos
amplios, flujo y saturación de vehículos, se optimiza la posición para los clientes y al mismo tiempo
se elimina el tiempo de búsqueda de estos espacios, es decir que en lugar de que el cliente deba
trasladarse a través del estacionamiento en búsqueda de un cajón libre, ya conoce previamente hacia
dónde debe dirigirse. En estadísticas, se logró reducir en 49% la utilización de calles dentro del
estacionamiento (flujo en estacionamiento optimizado), se elimina el tiempo de búsqueda en
estacionamiento, que termina reduciendo más del 30% el tiempo de estacionado por vehículo,
además de proveer el cajón más cercano para el momento en el que se estaciona el vehículo.
A partir de los parámetros, es decir el, tamaño del estacionamiento (capacidad) y cantidad de
vehículos (saturación o tráfico) podemos generar la simulación y analizar los resultados obtenidos
por nuestro programa asignando la ubicación más cercana para cada vehículo dependiendo de su
lugar objetivo.  
## SMART GOALS
Aspectos SMART: Específico Medible Alcanzable Realista Tiempo
1. Cajones libres  
Garantizar que el 100% de los cajones que se asignan del estacionamiento estén libres y no
ocupados al tener a una o un administrador que verificará el estado de los cajones con base
en su acceso a la disponibilidad de un cajón conociendo sus coordenadas para el 18 de
enero. 
2. Cajón más cercano 
Reducir en 20% el tiempo que tardan los carros en encontrar un cajón de estacionamiento
disponible al tener a una o un administrador que conocerá qué cajones están libres y se
encuentran más cercanos al destino del carro con el conocimiento y la utilización de las
prioridades de los cajones puesto que, cada cajón tiene una prioridad asignada dependiendo
del edificio, para el 20 de enero. 
4. Menor congestión vehicular 
Liberar las calles de congestión vehicular en un 15% al indicarle a los agentes carros en qué
cajón deben estacionarse para estar cerca de su destino, eliminando el tráfico causado por la
búsqueda de un cajón libre, al seguir las indicaciones de la o el administrador del
estacionamiento con un movimiento de los carros definido basado en rutas y sin desvíos o
acciones innecesarias para el 27 de enero.
![image](https://github.com/Silvana-Ruiz/Multiagent_System_Parking_Lot/assets/67821436/9c683a7b-71db-44ca-af4f-2389f705673a)

## Restrictions
Las restricciones de este proyecto son:  
● Los carros se mueven a una velocidad constante en cada step. Cabe destacar que, en las
curvas de la entrada y salida del estacionamiento donde se duplica la distancia, ahí se reduce
la velocidad a la mitad.  
● Los carros realizan el movimiento de girar al tomar una ruta y al ingresar y salir de un cajón. 
● No se tomará en cuenta el tráfico fuera del estacionamiento.  
● La plaza cuenta con 5 establecimientos objetivo (tiendas).  
● Una visita a un establecimiento siempre durará una cantidad de steps aleatoria entre 20 y 40. 
● Cada carro solo visita un estacionamiento en la plaza.  
● El estacionamiento no se puede llenar esto debido a la cantidad baja de waiting time o
cantidad de steps por la que los autos se mantendrán estacionados.  
● Una vez dadas las indicaciones por la o el administrador, el cajón asignado al carro es
considerado no disponible pese a que el carro aún esté en el trayecto para llegar a este. 
● El estacionamiento tiene 32 cajones.  
● El estacionamiento está dividido en 4 secciones (A, B, C y D) (solo para organizar el
estacionamiento), cada una con 8 cajones.  
● La plaza tiene una entrada con una caseta donde se encuentra la o el administrador. 
● La plaza tiene una salida.  
● La o el administrador asignará al carro un cajón con la mejor prioridad disponible en todo el
estacionamiento de acuerdo con el establecimiento objetivo del carro.  
● Las prioridades ya están establecidas y no cambian.  
● Cada cajón tiene una prioridad de acuerdo al establecimiento objetivo (Ej. el cajón en la
coordenada (1,4) tiene una prioridad 3 para el edificio de color azul mientras que, tiene una
de 26 para el verde).  
● No pueden encontrarse dos carros en una misma celda de la grid (cajón de estacionamiento
o calle).  
● El carro transita por el estacionamiento por las calles que lo dirijan al cajón asignado, sin
desvíos.  
● El carro solo tiene 4 direcciones a las que puede estar mirando: arriba, abajo, izquierda y
derecha.  
● Solo hay 5 colores de los que puede ser el carro, este corresponde al color del
establecimiento objetivo.  

## Requirements
### Functional Requirements
#### Multiagent System
1. El administrador determina el cajón de estacionamiento más cercano para los nuevos carros
dependiendo del establecimiento al que se dirigen.  
2. El administrador proporciona la ubicación del cajón de estacionamiento a los carros.  
3. Todos los carros se mueven en una celda ya sea en diagonal o adyacente por step.  
4. Los carros no pueden colisionar entre ellos y tampoco pueden estar en las mismas
coordenadas simultáneamente. En caso de estar adyacentes el auto de atrás debe esperar a
que el otro auto siga moviéndose.  
5. Los carros tienen tres estados: esperando, moviéndose y estacionados.  
6. Los autos permanecen “esperando” a que sean los primeros en la fila de la o el
administrador, para así cambiar su estado a “moviéndose” y para que la o el administrador
les asigne un cajón de estacionamiento cuando sea su turno.  
7. Cada cajón de estacionamiento está “disponible” si no hay un auto en él y “no disponible” si
se encuentra ocupado.  
8. El estacionamiento está divido en 4 “secciones”, A, B, C y D, que son un conjunto de cajones
de estacionamientos.  
9. Cada auto visita únicamente un establecimiento y, en consecuencia, solo puede tener un
cajón asignado al entrar al estacionamiento.  
10. Una vez que se haya estacionado el auto por el número de steps aleatorios entre 20 y 40,
saldrá del cajón y plaza.  
11. Una vez que se libere el cajón, su estado pasará a “disponible”.  
12. La o el administrador tiene prohibido asignar a un nuevo carro un cajón no disponible.  
13. El estacionamiento no se puede llenar esto debido a la cantidad baja de waiting time o
cantidad de steps por la que los autos se mantendrán estacionados.  
14. El programa genera las coordenadas de posición de los carros en todo el estacionamiento y
los almacena en un JSON para enviarlos como respuesta por la API.  
#### Graphics

1. El programa en Unity recupera los datos de las coordenadas y otros atributos de los carros de
la API por steps para establecer el movimiento de los carros.  
2. Los carros se mantienen en el suelo en todo momento, es decir que no muestran un
movimiento inusual o inesperado.  
3. Los autos no pueden colisionar entre ellos.  
4. Los carros se mueven a una velocidad constante en cada step. Cabe destacar que, en las
curvas de la entrada y salida del estacionamiento donde se duplica la distancia, ahí se reduce
la velocidad a la mitad.  
5. Los autos solo se pueden mover en el flujo establecido, es decir de derecha a izquierda
siguiendo la dirección de la entrada y salida.  
6. Existe un modelo para el administrador, auto, establecimiento y cajones de estacionamiento
además de los componentes del entorno (se añadirán objetos al entorno que no tendrán
funcionamiento pero ayudarán a mejorar la calidad de la simulación, es decir; arbustos,
postes, árboles, etc).  
7. Los autos son del mismo color que el color del establecimiento al que se dirigen.  
8. Los autos que aún no tienen asignado un cajón deben permanecer junto a la caseta de la o el
administrador hasta que este les asigne las coordenadas.  
9. Los autos son visibles una vez que se encuentran junto a la caseta del admin.  
10. Los autos no dejan de ser visibles cuando salen del estacionamiento.  
### Nonfunctional Requirements
#### Multiagent System
1. El programa funciona sin errores críticos, lo cuales detienen la ejecución.  
2. El programa funciona con distintas condiciones como número de carros con distintos
destinos entre sí (establecimientos a los que desean ir).  
3. Reducir el número de steps posible para que el carro llegue a su cajón y salga de la plaza (que
los autos no hagan movimientos innecesarios).  
4. Se utiliza un sistema de control de versiones como git para mantener backups del código.  
5. Se utiliza Jupyter Notebook para el desarrollo colaborativo del programa.  
6. Se utiliza Python 3 y la versión 1.1 del framework Mesa para el desarrollo del sistema.  
7. El programa se puede ejecutar en diferentes sistemas operativos como Windows, MacOs y
Linux.
#### Graphics
1. La simulación mantiene el mismo número de FPS (Fotogramas por segundo) durante toda la
ejecución.  
2. El programa no presenta errores de Timeout y mantiene una conexión constante con la API.  
3. Se mantiene la integridad de los datos desde que son obtenidos en Python con Mesa hasta
que son simulados en Unity.  
4. La simulación se ve natural y el movimiento es cercano a la realidad.  
5. No se observan errores de diseño en la escena como mal posicionamiento de los carros
dentro de los cajones o calles muy angostas.  
6. Se utiliza Unity 2021.3.8f1 en adelante pero se evita la 2021.3.13.  
7. Se utiliza la herramienta ProBuilder de unity para el modelado de algunos assets.
## Description of the Multiagent System
La solución multiagente consiste de dos agentes principales, el carro y la o el administrador del
estacionamiento. También se incluyeron agentes dummy como ParkingSpot para representar los
cajones, Street para las calles y BlockedCells para indicar espacios en los que no puede haber otros
agentes. Estos interactúan en una plaza, la o el administrador se encuentra en la entrada de esta en
una caseta y cuando un carro desea ingresar debe esperar a que la o el administrador le asigne un
cajón, el cual es seleccionado dependiendo del establecimiento que visitará.  

Por motivos de organización, el estacionamiento tiene 32 cajones y se encuentra dividido en cuatro
secciones (A, B, C y D) cada una con 8 cajones. Cada cajón por su establecimiento destino tiene una
prioridad asignada de 1 a 32, mientras más bajo sea el número, mayor prioridad tendrá; por ejemplo,
el cajón que se encuentra en la coordenada (1,4) tiene una prioridad 3 para el edificio de color azul
mientras que, tiene una de 26 para el verde. Por lo que, para cada carro que desee ingresar a la plaza
la o el administrador buscará en la matriz de prioridades correspondiente a su estacionamiento
destino el cajón con la mejor prioridad que se encuentre disponible. Esto significa que, tal vez los
cajones de la sección más cercana al establecimiento se encuentren ocupados; por lo tanto, se
buscará qué cajón tiene la siguiente mejor prioridad y se verificará que se encuentre disponible.
Veáse matrices de prioridad de acuerdo con el establecimiento objetivo.  

![image](https://github.com/Silvana-Ruiz/Multiagent_System_Parking_Lot/assets/67821436/1a44bb1e-397b-4201-8d9e-6191ebdf8f50)

Una vez que se le asigne un cajón al carro, este deberá navegar por las calles sin realizar
movimientos innecesarios hasta llegar a su cajón objetivo. Después, se mantendrá estacionado
por una cantidad aleatoria de steps entre 20 y 40 (el número bajo de steps en el que se
mantienen estacionados los autos ocasiona que no se llene el estacionamiento). Posteriormente,
se deberá de retirar de su cajón y del estacionamiento evitando colisiones en su
salida. Si hay un carro transitando en la calle cuando desea salir del cajón, el carro esperará a
que la celda de calle directamente adyacente y diagonal a la derecha estén vacías para dar el
giro. Mientras sale del cajón, los carros en la calle que se encuentren detrás deberán
detenerse para prevenir una colisión.  

Diseño de la plaza y estacionamiento:
![image](https://github.com/Silvana-Ruiz/Multiagent_System_Parking_Lot/assets/67821436/797faef2-9353-4a6f-9703-218676800e85)

Representación por cuadrícula para MESA del modelo anterior es el siguiente:
![image](https://github.com/Silvana-Ruiz/Multiagent_System_Parking_Lot/assets/67821436/447496fc-814f-43e0-863a-c5db8db4b695)

Clases utilizadas en Mesa:  
- ParkingSpot: Representa un cajón en el estacionamiento, puede estar libre o no.  
- Street: Este agente indica las celdas del grid por las que el agente carro puede transitar.  
- BlockedCell: Las celdas bloqueadas se utilizan para indicar las celdas donde no puede haber
otros agentes, se utiliza para propósitos de visualización.
- Car: El agente se mueve por el estacionamiento de la plaza para llegar al cajón de
estacionamiento más cercano al establecimiento que visita.  
- Admin: El agente de la o el Admin es responsable de asignarle el cajón de estacionamiento
más cercano a los carros.  
- Plaza: Esta es la clase del modelo del sistema de multiagentes, aquí se crean a los demás
agentes y se les asigna una coordenada en la grid.  

## Model of the Agents 
Los agentes en el sistema serán dos, los carros y la o el administrador. 
![image](https://github.com/Silvana-Ruiz/Multiagent_System_Parking_Lot/assets/67821436/4a572fd1-2bd4-462c-84f4-1beba8550b0c)
![image](https://github.com/Silvana-Ruiz/Multiagent_System_Parking_Lot/assets/67821436/164e5f35-62a2-4c97-9f52-2b21a7f06b9b)

*Agente Carro*  
Máquina de Estados   
![image](https://github.com/Silvana-Ruiz/Multiagent_System_Parking_Lot/assets/67821436/e797782b-e0c8-4dd9-9180-21f323facbbc)

Diagrama de Agente 
![image](https://github.com/Silvana-Ruiz/Multiagent_System_Parking_Lot/assets/67821436/6d81cc5e-a963-4622-8c83-311d5c3791ba)

*Agente Administrador o Administradora*  
Máquina de Estados   
![image](https://github.com/Silvana-Ruiz/Multiagent_System_Parking_Lot/assets/67821436/8d08555a-480f-4bdd-8a80-c76dcc3f9594)

Diagrama de Agente  
![image](https://github.com/Silvana-Ruiz/Multiagent_System_Parking_Lot/assets/67821436/3e4e6d5a-e20e-4d57-84b6-45a9b9687fea)

## Model of the Scenery
El ambiente que se modelará en la simulación es una plaza con establecimientos , los cuales son 5
tiendas, árboles, una caseta, un vecindario cercano, postes de luz y bancas. En esta plaza se cuenta
con una caseta donde se encuentra la o el administrador, este agente recibe a los carros en la
entrada de la plaza y les da indicaciones sobre qué cajón de una sección del estacionamiento deben
tomar para ubicarse más cerca del lugar al que desean visitar. Cabe destacar que, el estacionamiento
está organizado en secciones, las cuales se encuentran más cercanas a unas tiendas que a otras. Por
ello, la o el administrador tendrá que utilizar las matrices de prioridad de los establecimientos para
encontrar qué cajón tiene la mejor prioridad y se encuentra libre. Estas prioridades no cambian, ya
están definidas por cada establecimiento en la plaza, y van del 1 al 32 siendo 1 la mejor prioridad y
32 la peor; por ejemplo, el cajón en la coordenada (1,4) tiene una prioridad 3 para el edificio de color
azul mientras que, esta es de 26 para el verde.  

Después de ser asignados un cajón, los carros deberán dirigirse a este evitando colisiones en el
proceso; por ejemplo, si la siguiente celda de la calle en su recorrido se encuentra ocupada, el carro
se deberá detener. Una vez que llegue al cajón, deberá de permanecer en este una cantidad aleatoria
de steps entre 20 y 40, esta cantidad baja de steps es la razón por la que el estacionamiento no se
llena. Después, deberá salir de su cajón, si la calle (celda) directamente adyacente al cajón y la calle
en diagonal a la derecha (celda) de este están vacías podrá efectuar la salida (se considera la celda en
diagonal por el giro). En caso de que alguna de estas se encuentre ocupada, tendrá que esperar a
que se liberen. Posteriormente, el carro deberá dirigirse a la salida de la plaza.  

El tiempo en la simulación se maneja por pasos, steps. En cuanto a la modelación del espacio, se
plantea la utilización de una malla (matriz de espacios) para representar la plaza y dentro de sí el
estacionamiento, ya que esto es útil a la hora de tomar las cells como cajones y un grupo de estos
como las secciones. Los agentes carro solo se pueden ubicarse en una cell en cada step.  

Respecto a sus características, el ambiente es determinista debido a que tras realizar ciertas acciones
con los agentes se debe tener el mismo resultado. Lo anterior se puede ejemplificar con la dinámica
que existe entre la o el administrador y el carro, una vez que el primero le indique el cajón con mejor
prioridad libre, el carro se dirigirá a este. Por lo que, es posible determinar qué sucederá conociendo
los estados actuales de los agentes y las acciones que pueden tomar. Asimismo, el ambiente es
estático debido a que, en el entorno el estacionamiento no cambia, mantiene la misma cantidad de
cajones y secciones en cada step. A su vez, se cuenta con un entorno discreto ya que el tiempo es
manejado por medio de steps y cuenta con estados, percepciones y acciones finitas [3] para cada
uno de los agentes. Por último, es un sistema multiagente ya que se cuenta con dos agentes con
inteligencia, el de carro y el de la o el administrador. También se tienen otros agentes como los
ParkingSpot, Street y BlockedCells. En conjunto, conforman nuestro sistema e interactúan con el
entorno.  

## Interaction model
Para la comunicación de datos, se creará una API que transmita los datos generados por MESA hacia
la simulación en Unity utilizando HTTPServer en Python. Existirá un endpoint que regrese los datos
de los agentes carro para poder utilizar su respuesta dentro de la simulación de Unity. A continuación
se muestra el formato de JSON con los datos referentes a la simulación.  

Como se puede observar, el JSON contiene información del Step actual y un arreglo de objetos Car
que contienen la información del Agente Auto. Para cada auto de la simulación se mandan los
siguientes datos:  
● Unique_id: identificador único del carro 
● X: Posición en X del carro  
● Y: Posición en Y del carro  
● State: Estado del carro  
  ○ Waiting = 0  
  ○ Moving = 1  
  ○ Parked = 2  
● Color: Color del carro (de acuerdo al edificio al que se dirige)  
● Is_Active: Utilizado para saber si el carro ya es el primer 
carro en la fila y se encuentra junto a la o el administrador y por
ende, será visible en la simulación  
![image](https://github.com/Silvana-Ruiz/Multiagent_System_Parking_Lot/assets/67821436/c3e41503-1a55-4f58-9d5b-025187507285)

Estas variables son necesarias en Unity. El unique_id nos permite
identificar de manera sencilla a qué objeto le pertenecen tales
valores. La posición en X y Y nos permitirá posicionar los carros en
Unity. El color será el utilizado en la textura del carro. Por último, el
valor de Is_Active establece si el carro debería ser visible o no en la
simulación.  

# 3D Model
## Description of the Scenery to Model
![image](https://github.com/Silvana-Ruiz/Multiagent_System_Parking_Lot/assets/67821436/e8f63861-1703-4c5b-ab54-8429731a0f71)
![image](https://github.com/Silvana-Ruiz/Multiagent_System_Parking_Lot/assets/67821436/1df2f553-7102-4c0f-8823-34d4de92dffd)
![image](https://github.com/Silvana-Ruiz/Multiagent_System_Parking_Lot/assets/67821436/0feacf87-2992-40df-9f6f-874231ade23f)
![image](https://github.com/Silvana-Ruiz/Multiagent_System_Parking_Lot/assets/67821436/c23d92e6-338a-4ad7-a863-1bf7cb387e02)

La escena consiste en un estacionamiento principal dividido en 4 secciones (A, B, C y D) que
representan una zona de la plaza comercial. Cada rectángulo fuera del estacionamiento representa
uno de los establecimientos hacia los cuales los carros se pueden dirigir. Si un carro es rojo, entonces
su ubicación objetivo es el edificio rojo por lo que el administrador deberá asignarle el lugar de
estacionamiento más cercano al establecimiento rojo, el cual puede ser una tienda de ropa por
ejemplo. A su vez, dentro de las secciones existen líneas amarillas que delimitan los cajones de
estacionamiento. Solamente un carro puede ocupar la posición de un cajón de estacionamiento a la
vez.  

Además, en la escena existe un flujo de autos de izquierda a derecha sobre las calles (representado
con flechas blancas). Por lo que, los autos se encuentran en la entrada formados (en la simulación
solo podrá ser visible el primer carro debido a la alta cantidad de agentes carro que se manejan). En
la entrada junto con la caseta se contará con una pluma que se esté levantando y bajando cada vez
que la o el administrador en la caseta les asigna un cajón de estacionamiento e ingrese el carro.
Después, los carros deben transitar por la calle hacia la derecha hasta llegar al cajón asignado para
estacionarse. Una vez que se retiran del estacionamiento, se dirigen hacia la derecha para la salida.
Cabe destacar que, los autos no pueden entrar al estacionamiento si no tienen un cajón asignado.  

## Graphic Components Description
![image](https://github.com/Silvana-Ruiz/Multiagent_System_Parking_Lot/assets/67821436/d31797ae-591d-41f7-a0a5-3a864a816fdd)
![image](https://github.com/Silvana-Ruiz/Multiagent_System_Parking_Lot/assets/67821436/370fdd32-6326-46f9-87e5-f5c49116b122)

![image](https://github.com/Silvana-Ruiz/Multiagent_System_Parking_Lot/assets/67821436/ac874be1-2270-466e-8d40-b79c05a76a47)
![image](https://github.com/Silvana-Ruiz/Multiagent_System_Parking_Lot/assets/67821436/4e51bf3a-bd8d-4499-93f8-145230613c04)

![image](https://github.com/Silvana-Ruiz/Multiagent_System_Parking_Lot/assets/67821436/9bc8ec5d-6375-415a-85e1-6c1f8378e568)
![image](https://github.com/Silvana-Ruiz/Multiagent_System_Parking_Lot/assets/67821436/30597b77-ede5-4d0a-97ca-1cb1e21c7d3c)

![image](https://github.com/Silvana-Ruiz/Multiagent_System_Parking_Lot/assets/67821436/cea25f34-56fe-4645-9acf-a05295e11d4c)

![image](https://github.com/Silvana-Ruiz/Multiagent_System_Parking_Lot/assets/67821436/b26d9742-4de8-4ff3-94c0-1ed462a2ab8f)

![image](https://github.com/Silvana-Ruiz/Multiagent_System_Parking_Lot/assets/67821436/a8967853-6fc6-4e96-a451-b172d4cd675b)
![image](https://github.com/Silvana-Ruiz/Multiagent_System_Parking_Lot/assets/67821436/f3cb7fbf-0cde-4c55-89a0-9b19e95e9585)

![image](https://github.com/Silvana-Ruiz/Multiagent_System_Parking_Lot/assets/67821436/6ea1bf17-cebc-4f52-8833-549a9378c4b6)

![image](https://github.com/Silvana-Ruiz/Multiagent_System_Parking_Lot/assets/67821436/3008890f-956c-4b48-9081-13700970199d)

![image](https://github.com/Silvana-Ruiz/Multiagent_System_Parking_Lot/assets/67821436/545214fb-122f-4536-b9c3-e0ffd0d86d54)

![image](https://github.com/Silvana-Ruiz/Multiagent_System_Parking_Lot/assets/67821436/809c83c7-3058-4c36-a3a6-7ca863bfae63)

![image](https://github.com/Silvana-Ruiz/Multiagent_System_Parking_Lot/assets/67821436/d80546a2-d7f3-4c12-ae11-a2c677e198f0)

![image](https://github.com/Silvana-Ruiz/Multiagent_System_Parking_Lot/assets/67821436/eff7796d-606f-425a-97a3-d451e468d5a0)

## Prefabs Description
![image](https://github.com/Silvana-Ruiz/Multiagent_System_Parking_Lot/assets/67821436/2520b48b-5329-4df4-987a-4fcd12d660e3)
![image](https://github.com/Silvana-Ruiz/Multiagent_System_Parking_Lot/assets/67821436/3c320d55-113e-4bb9-b33b-1db3533c7618)

![image](https://github.com/Silvana-Ruiz/Multiagent_System_Parking_Lot/assets/67821436/87ea14a9-cd2e-463c-9a28-8d5083b6e365)

![image](https://github.com/Silvana-Ruiz/Multiagent_System_Parking_Lot/assets/67821436/c0193f93-3b5a-4a06-897f-63f2069cfe5f)

## Scripts Description
### Script de Mesa
El script de MESA (Google Colab) se encuentra en el siguiente vínculo:  
https://colab.research.google.com/drive/1o7WUEl6wssKFM_9yS3NqWhCsmLQOAkck?usp=sharing

En el Script de MESA se muestran primeramente las coordenadas de cada una de los agentes y
agentes dummy que van a ser utilizados, es decir las calles y cajones de estacionamiento, al igual que
también se crean las matrices de prioridad que sirven para encontrar el cajón disponible más
cercano al establecimiento destino.  
Algunas funciones y clases importantes en el Script son las siguientes:  
![image](https://github.com/Silvana-Ruiz/Multiagent_System_Parking_Lot/assets/67821436/9d019ec5-0b45-47fc-ac7e-b5568ea8c2db)
![image](https://github.com/Silvana-Ruiz/Multiagent_System_Parking_Lot/assets/67821436/fd46235e-fd93-45be-a6e1-2ce3396addf1)

### Unity Scripts
![image](https://github.com/Silvana-Ruiz/Multiagent_System_Parking_Lot/assets/67821436/67b30b84-d3a3-4e1f-b426-be0efdb5f9a0)
![image](https://github.com/Silvana-Ruiz/Multiagent_System_Parking_Lot/assets/67821436/632e9bc7-59e4-47d1-b737-15f4ad165961)

![image](https://github.com/Silvana-Ruiz/Multiagent_System_Parking_Lot/assets/67821436/a9c88dba-792b-4d96-a7a0-935ce7b1cae1)

![image](https://github.com/Silvana-Ruiz/Multiagent_System_Parking_Lot/assets/67821436/bff887a1-250a-43fe-b515-2ca20a5ef952)

![image](https://github.com/Silvana-Ruiz/Multiagent_System_Parking_Lot/assets/67821436/831ba61a-4e59-45af-8d54-b879bfb9369e)

![image](https://github.com/Silvana-Ruiz/Multiagent_System_Parking_Lot/assets/67821436/22459904-7f1b-4a28-8821-bc84b5c78fa6)

## Project Management Backlog
Product y sprint backlog:  
https://trello.com/invite/b/L4ms4Nnv/ATTIbde7387fa2dcde7f36788a5c08ac3303AC12403C/sprint-e
stacionatec  

(El link solicita la creación de una cuenta o hacer inicio de sesión, el modo de vista requiere de
suscripción).  
Entrega 1  
![image](https://github.com/Silvana-Ruiz/Multiagent_System_Parking_Lot/assets/67821436/fdcc4808-13a8-42d4-ab6e-8cfa0d42ab61)

Entrega 2  
![image](https://github.com/Silvana-Ruiz/Multiagent_System_Parking_Lot/assets/67821436/48f13b53-02ba-493b-9b7e-ce9e084b5f84)
![image](https://github.com/Silvana-Ruiz/Multiagent_System_Parking_Lot/assets/67821436/4c8532b4-4240-48a4-bc9e-a9dafde146a4)

Entrega 3  
![image](https://github.com/Silvana-Ruiz/Multiagent_System_Parking_Lot/assets/67821436/ee2f93c8-3456-45c3-9729-506a6452eaf3)

Entrega Final  
![image](https://github.com/Silvana-Ruiz/Multiagent_System_Parking_Lot/assets/67821436/932494df-480f-4016-8067-9db347dff730)

## Communication Tools
Se utiliza zoom para realizar reuniones cada dos días para así mantener una comunicación efectiva
entre las y los miembros del equipo.  
![image](https://github.com/Silvana-Ruiz/Multiagent_System_Parking_Lot/assets/67821436/4834c81d-ba8b-4b35-873d-1f5fa69702fc)

## Conclusion  
Durante el bloque hemos podido aprender de los sistemas multiagentes desde sus casos de uso
hasta sus características. De esta manera, hemos podido comenzar a adentrarnos a su programación 
mediante el uso del framework Mesa en Python. Esto nos permitió desarrollar un proyecto del
sistemas multiagentes en su totalidad aplicando la teoría estudiada en clases en un escenario de la
vida real como un estacionamiento de una plaza. De igual manera, en el módulo de gráficas,
creamos modelos en Unity utilizando la herramienta ProBuilder. Además, realizamos Prefabs y les
añadimos scripts con código en C# para añadir movimiento o instanciar objetos. Esto nos ha dado un
mayor entendimiento sobre cómo relacionar ambos módulos para aplicarlos en nuestro reto de la
simulación de un estacionamiento.

## References
[1] D. C. Shoup, “Cruising for parking,” Transport Policy, vol. 13, no. 6, pp. 479–486, Feb. 2006.
[2] Y. Geng and C. G. Cassandras, “A new ‘smart parking’ system infrastructure and
Implementation,” Procedia - Social and Behavioral Sciences, vol. 54, pp. 1278–1287, Oct. 2012.
[3] S. J. Russell and P. Norvig, “ Chapter 2. Intelligent Agents,” in Artificial Intelligence: A modern
approach, Third., Upper Saddle River, New Jersey: Prentice-Hall, 2010, p. 44.
[4] Code Monkey, “Splines are awesome!!!,” YouTube, 11-Dec-2020. [Online]. Available:
https://www.youtube.com/watch?v=7j_BNf9s0jM. [Accessed: 28-Jan-2023].






