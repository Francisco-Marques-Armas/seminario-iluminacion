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

1. Light: Esta es la clase base para todos los tipos de luces en Unity. Los parámetros de entrada varían según el tipo de luz (DirectionalLight, PointLight, SpotLight, AreaLight...). Estas luces simulan fuentes de luz en la escena, como el sol, lámparas, etc. Puedes ajustar la intensidad, el color y otros parámetros para definir cómo afectan la escena.
2. LightProbeGroup.ProbePositions: Esta función permite acceder a las posiciones de las sondas de luz en un LightProbeGroup. Las sondas de luz se utilizan para capturar información de iluminación indirecta en la escena y se utilizan en conjunción con el sistema de Iluminación Global para lograr una iluminación más realista.
3. RenderSettings.ambientLight: Controla el color y la intensidad de la luz ambiental en la escena. La luz ambiental es la luz que ilumina todos los objetos por igual y se utiliza para simular la luz que se dispersa en una escena desde múltiples fuentes.
4. Lighting.Bake: Este es un método utilizado para calcular y almacenar información de iluminación estática en la escena. Se utiliza en combinación con sistemas como el mapeo de luz global (Global Illumination) y el mapeo de oclusión ambiental (Ambient Occlusion) para mejorar la calidad de la iluminación en tiempo real.
5. LightProbes.GetInterpolatedLightProbe: Esta función se utiliza para obtener la información de iluminación indirecta (de sondas de luz) en una posición específica de la escena. Permite que los objetos reflejen la iluminación global y la iluminación indirecta de manera más precisa.
6. ReflectionProbe.RenderProbe: Las sondas de reflexión se utilizan para capturar la información de reflexión en la escena. Este método se utiliza para renderizar la sonda de reflexión y capturar cómo refleja la escena en tiempo real.
7. LightmapSettings.lightmaps: Esta propiedad te permite acceder a los mapas de luz precalculada que se utilizan para iluminar objetos en la escena. Los mapas de luz se generan durante el proceso de cocción de luz y se aplican a los objetos para lograr una iluminación más realista.

Estas son algunas de las funciones sobre la iluminación en Unity que hemos considerado entre las mas relevantes
