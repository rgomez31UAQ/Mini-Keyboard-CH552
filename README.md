# idawgz32

### Un teclado mecánico, ¿en esta economía?

Un teclado de bolsillo experimental, ultraportátil y muy asequible, cuya fabricación cuesta menos de 5 dólares en materiales. El objetivo del proyecto es hacer un teclado que se puede dar como obsequios o regalos. Todo el PCBA puede ser producido por JLCPCB. Utiliza un CH552 como MCU, y ejecuta el firmware FAK.

![a photo of an idawgz32](https://raw.githubusercontent.com/ChrisChrisLoLo/idawgz32/main/images/PXL_20240225_225159875.jpg)

# Estado
Los PCBs v0.0 técnicamente funcionan, aunque los actuales interruptores smd utilizados tienen una alta tasa de fallos y se supone que son de mala calidad. Los PCBs v2.0 están en progreso y utilizarán el interruptor EVQP0N02B en su lugar, que se sabe que funcionan bien.

Recomiendo esperar a que salga la v2.0, aunque la v0.0 tiene algunas soluciones que se describen en la entrada de mi blog.

Hay que tener en cuenta que este diseño tiene tolerancias muy bajas para los interruptores de las teclas. Es probable que necesites una impresora 3D como una Bambu Lab A1/A1 mini/P1P/P1S y ajustar la resolución de la capa de corte a 0,08 mm. Impresoras como la Prusa i3/mini también pueden funcionar, pero no han sido probadas.

# Acerca de
Me emocioné con la nueva tendencia reciente de la construcción de teclados con el chip CH552, y quería ampliar mi [pusheenz40](https://github.com/ChrisChrisLoLo/pusheenz40) con el objetivo final de construir un teclado que cueste tan poco que pueda regalarlo en convenciones. El tamaño de la placa, el diseño y la selección de componentes (o la falta de ellos) están todos al servicio de conseguir el precio más bajo posible.

Puedes leer más sobre el experimento y el proceso de diseño en la entrada de mi blog aquí: https://chrischrislolo.github.io/orthoLabLogs/idawgs32-how-i-made-a-full-keyboard-for-dollar6.html

Los archivos de la carcasa incluyen archivos 3MF, archivos STEP que incluyen la carcasa superior, así como los botones.


![a idawgz32](https://raw.githubusercontent.com/ChrisChrisLoLo/idawgz32/main/images/PXL_20240225_201119535.jpg)


# Caso
Los archivos del caso se pueden encontrar en el directorio `case`.

Los casos impresos en 3D pueden y deben utilizar la resolución más fina posible en su impresora, y lo ideal sería utilizar una impresora de gama alta debido a sus bajas tolerancias. Los modelos han sido probados para trabajar con el laboratorio Bambu A1 y P1S en una altura de capa y la configuración de detalle de 0,08 mm (extra fino). Se recomienda utilizar una impresora de alta calidad y/o más reciente.

Lubricar los railes de la carcasa con algo como krytox 205g0 es altamente recomendable (y casi obligatorio para placas v0.0), especialmente cuando se usa una carcasa de aluminio CNC. 

## PCB
Puedes encontrar los archivos fuente de la PCB en la carpeta `pcb`. Los archivos BOM se pueden encontrar en esta carpeta.

pcb](https://raw.githubusercontent.com/ChrisChrisLoLo/idawgz32/main/images/PXL_20240225_224453990.jpg)

## Estructura del directorio
- `case`
    En esta carpeta se encuentran los archivos necesarios para imprimir una funda para el teclado
- `drafts`
    Almacena cualquier información ergogénica o intermedia utilizada en la fabricación de la funda
- `pcb`
    Proyecto Kicad relativo al proyecto. Contiene la lista de materiales, los archivos de colocación y los gerbers
   
## BOM
- 1 PCBA
  - El PCB incluirá todas las partes eléctricas necesarias, incluyendo los interruptores.
- 1 carcasa superior de aluminio CNC o carcasa superior 3DP
- 32 botones impresos en 3D
- 8 tornillos M1.6 de 3mm (de cabeza plana para un ajuste más al ras, aunque otros tipos de cabeza también deberían funcionar)
- 4-8 (idealmente 8) 1-2mm bumpons (algo como Sj5302 es un buen lugar para empezar)

## Montaje
Flasheo de la pcb con mi rama FAK (ver sección de abajo). Bootmagic está habilitado, así que usar la tecla superior izquierda para flashear de aquí en adelante es posible.

Coloca los botones impresos en 3D en la carcasa, y asegúrate de que no se pegan y pueden moverse libremente arriba y abajo. Si se atascan (por ejemplo, si hay que aplicar una fuerza considerable para que salgan), comprueba que estás imprimiendo con la configuración de detalle más fina. Todas las teclas deben estar alineadas con la carcasa. Una vez que los interruptores estén en su sitio, recubra la placa sobre la carcasa. Presione suavemente la pcb para asegurarse de que un botón no se presiona hacia abajo.

Opcionalmente envuelve la placa con una goma elástica para mantenerla en su sitio y dale la vuelta para validarlo todo. A continuación, presione suavemente cada botón para asegurarse de si se puede accionar. Si un botón está muy pegajoso, puede ser necesario volver a imprimirlo o lijarlo. Si hay una ligera fricción en el retorno de las teclas, ésta debería desaparecer lentamente a medida que el teclado se vaya asentando. Si hay un botón que no se acciona, es posible que esté desalineado. Dale la vuelta a la placa, retira la goma elástica y la pcb, y asegúrate de que la tecla problemática está a ras de la carcasa. Vuelva a colocar la placa y pruebe hasta que todas las teclas se accionen correctamente.

A continuación, gire el teclado una última vez para que la placa quede hacia arriba. Atornille los tornillos y pruebe una última vez.

Finalmente, coloque los topes de goma

## Firmware
La rama y el tenedor de FAK Firmware se puede encontrar aquí:
https://github.com/ChrisChrisLoLo/fak/tree/idawgz32
