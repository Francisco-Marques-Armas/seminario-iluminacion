# seminario-iluminacion

## Investiga sobre los modelo de iluminación que aplica Unity y resume las relaciones existentes con el modelo explicado en clase.

1. Iluminación directa e indirecta
La iluminación directa es la que incluye la luz que es emitida, rebota en una superficie una vez y luego es reflejado en un sensor directamente, como una cámara. La luz indirecta es toda la otra luz que llega al sensor, incluyendo aquellas que rebotan en superficies varias veces y la luz del cielo. Unity puede calcular la iluminación directa, indirecta, y tanto directa como indirecta, dependiendo de cómo se configure el proyecto.
2. Iluminación en tiempo real y baked lighting
La iluminación en tiempo real es el tipo de iluminación en el que Unity realiza los cálculos en tiempo de ejecución. Baked lighting es el proceso en el que se precalcula toda la ruta de la luz y se guardan los datos que luego se aplican en tiempo real. Se puede también realizar los dos tipos de iluminado a la vez, lo que se denomina "mixed lighting".
3. Global
La iluminación global es un grupo de técnicas que modelan tanto la luz directa como la indirecta para proveer resultados de iluminación realistas. Unity tiene dos sistemas de iluminación global que combinan tanto la luz directa como la indirecta: el sistema de iluminación global baked y el sistema de iluminación global en tiempo real.

En clase nos concentramos en el modelo de iluminación local, que sólo tiene en cuenta el efecto de la fuente de luz, al contrario que la iluminación global, en la que un objeto se ilumina por la fuente de luz y la que reflejan los otros objetos. Además, el modelo de unity no se basa en las ecuaciones de energía emitida y absorbida por los objetos, al contrario que el modelo de radiosidad.

La iluminación ambiental representa la luz que está dispersa en el ambiente de tal manera que parece venir de todas direcciones. Es el nivel base de luz que asegura que ninguna parte de la escena esté completamente oscura.

Implementación: En Unity, la configuración de la luz ambiental se puede ajustar en la ventana de Iluminación bajo la pestaña de Ambiente. Puedes establecer el color y la intensidad de la luz ambiental, lo que afecta a toda la escena de manera global. Unity también soporta luz ambiental proveniente de skyboxes y gradientes de color ambiental personalizados.

La iluminación difusa simula la luz que viene de una fuente de luz e incide en un objeto, dispersándose en todas direcciones. Es la luz no brillante que es típica para superficies mate.

Implementación: Unity calcula la iluminación difusa usando el modelo de reflectancia Lambertiana, que asume que la luz se refleja igualmente en todas direcciones. Esto es parte de los cálculos del shader estándar y se aplica automáticamente a materiales con un color albedo no nulo.

La iluminación especular representa los reflejos brillantes y espejados que ocurren en superficies brillantes. Es lo que crea los reflejos y la sensación de brillo en los materiales.

Implementación: En el Shader Estándar, los reflejos especulares están controlados por las propiedades de suavidad y metalicidad del material. El shader utiliza el modelo Blinn-Phong o de Renderizado Basado en la Física (PBR) para calcular el término especular.

En Unity, los materiales son activos que definen la apariencia visual de las superficies. Son esencialmente una combinación de un shader (que dicta cómo el material interactúa con la luz y se renderiza en la pantalla) y un conjunto de propiedades (como colores, texturas y otros parámetros) que el shader utiliza.

Los materiales a menudo usan texturas, que son imágenes de mapa de bits que añaden detalle a la superficie. Las texturas pueden representar varios aspectos como color, mapeo normal (para detalle de superficie), metalicidad, rugosidad, oclusión ambiental y más.

## Indica las funciones de la API de Unity más importantes respecto a la iluminación.

1. Light: Esta es la clase base para todos los tipos de luces en Unity. Los parámetros de entrada varían según el tipo de luz (DirectionalLight, PointLight, SpotLight, AreaLight...). Estas luces simulan fuentes de luz en la escena, como el sol, lámparas, etc. Puedes ajustar la intensidad, el color y otros parámetros para definir cómo afectan la escena.
2. LightProbeGroup.ProbePositions: Esta función permite acceder a las posiciones de las sondas de luz en un LightProbeGroup. Las sondas de luz se utilizan para capturar información de iluminación indirecta en la escena y se utilizan en conjunción con el sistema de Iluminación Global para lograr una iluminación más realista.
3. RenderSettings.ambientLight: Controla el color y la intensidad de la luz ambiental en la escena. La luz ambiental es la luz que ilumina todos los objetos por igual y se utiliza para simular la luz que se dispersa en una escena desde múltiples fuentes.
4. LightProbes.GetInterpolatedLightProbe: Devuelve una sonda interpolada para la posición dada para las sondas de luz horneada (baked light) y en tiempo real combinadas.
5. ReflectionProbe.RenderProbe: devuelve unn número entero que representa un RenderID que se puede utilizar posteriormente para comprobar si la sonda ha terminado de renderizar mientras renderiza en modo de intervalo de tiempo.
6. LightmapSettings: Una escena puede tener varios mapas de luz almacenados y los componentes del Renderizador pueden usar esos mapas de luz. Esto hace posible utilizar el mismo material en varios objetos, mientras que cada objeto puede hacer referencia a un mapa de luz diferente o a una parte diferente del mismo mapa de luz.

Estas son algunas de las funciones sobre la iluminación en Unity que hemos considerado entre las mas relevantes
