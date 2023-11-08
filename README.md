# seminario-iluminacion

## Investiga sobre los modelo de iluminación que aplica Unity y resume las relaciones existentes con el modelo explicado en clase.

1. Iluminación directa e indirecta
La iluminación directa es la que incluye la luz que es emitida, rebota en una superficie una vez y luego es reflejado en un sensor directamente, como una cámara. La luz indirecta es toda la otra luz que llega al sensor, incluyendo aquellas que rebotan en superficies varias veces y la luz del cielo. Unity puede calcular la iluminación directa, indirecta, y tanto directa como indirecta, dependiendo de cómo se configure el proyecto.
2. Iluminación en tiempo real y baked lighting
La iluminación en tiempo real es el tipo de iluminación en el que Unity realiza los cálculos en tiempo de ejecución. Baked lighting es el proceso en el que se precalcula toda la ruta de la luz y se guardan los datos que luego se aplican en tiempo real. Se puede también realizar los dos tipos de iluminado a la vez, lo que se denomina "mixed lighting".
3. Global
La iluminación global es un grupo de técnicas que modelan tanto la luz directa como la indirecta para proveer resultados de iluminación realistas. Unity tiene dos sistemas de iluminación global que combinan tanto la luz directa como la indirecta: el sistema de iluminación global baked y el sistema de iluminación global en tiempo real.

En clase nos concentramos en el modelo de iluminación local, que sólo tiene en cuenta el efecto de la fuente de luz, al contrario que la iluminación global, en la que un objeto se ilumina por la fuente de luz y la que reflejan los otros objetos. Además, el modelo de unity no se basa en las ecuaciones de energía emitida y absorbida por los objetos, al contrario que el modelo de radiosidad.


## Indica las funciones de la API de Unity más importantes respecto a la iluminación.
