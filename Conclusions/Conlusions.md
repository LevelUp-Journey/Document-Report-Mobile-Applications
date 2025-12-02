# Conclusiones:

​	A lo largo de los diferentes sprints de desarrollo de **LevelUp Journey**, se ha demostrado que la problemática identificada al inicio del proyecto —la desmotivación, desorganización y riesgo de deserción en los primeros ciclos universitarios— no solo es vigente, sino también crítica para la experiencia académica de los estudiantes. La construcción incremental de la solución, desde la definición de supuestos y problem statements hasta el despliegue en producción sobre Firebase para las aplicaciones en **Flutter** y **Android nativo**, confirma que existe una **necesidad clara y actual** de herramientas que acompañen este periodo de adaptación. Los hallazgos del proceso de diseño y validación evidencian que muchos estudiantes de primeros ciclos carecen de canales estructurados para organizar su vida académica, lo cual refuerza la pertinencia del proyecto.

​	En ese sentido, uno de los aportes más relevantes del producto es la incorporación de la **gamificación como estrategia pedagógica**. A través de dinámicas como puntos, logros, niveles e insignias, LevelUp Journey no se limita a ser un repositorio de anuncios, sino que se configura como un entorno que promueve la participación activa y el sentido de progreso. Durante los sprints de diseño de experiencia de usuario y definición funcional, se identificó que los estudiantes responden mejor a estímulos que combinan claridad informativa con elementos lúdicos que refuercen la motivación intrínseca y extrínseca. La plataforma, por tanto, se posiciona como una propuesta que integra componentes tecnológicos y pedagógicos, orientados a fortalecer la permanencia y la autonomía de los estudiantes.

​	El proceso de desarrollo guiado por **Lean UX** permitió que cada sprint tuviera un énfasis claro en la validación de supuestos más que en la producción de artefactos puramente documentales. En las primeras iteraciones, se formularon y priorizaron hypotheses sobre el comportamiento de los usuarios, el impacto esperado y las funcionalidades críticas. Posteriormente, se diseñaron prototipos y se construyeron versiones funcionales mínimas que hicieron posible obtener retroalimentación temprana. Este enfoque redujo el riesgo de desarrollar características poco relevantes y permitió que el esfuerzo técnico se concentrara en aquello que realmente agregaba valor: centralización de anuncios, notificaciones oportunas, segmentación de comunicados y registro de interacción. Como resultado, el producto que hoy se encuentra desplegado responde de manera más precisa a las necesidades reales de los estudiantes y docentes.

​	Desde la perspectiva técnica, los sprints dedicados a la implementación del backend, la integración con Firebase y el despliegue de las aplicaciones móviles consolidaron una solución **funcional, escalable y alineada con buenas prácticas de ingeniería de software**. La arquitectura planteada, basada en servicios especializados y aplicaciones cliente en Flutter y Android nativo, permite una fácil evolución futura, incorporación de nuevas funcionalidades y eventual integración con otros sistemas institucionales. El despliegue en Firebase no solo asegura una infraestructura adecuada para el piloto, sino que también facilita la gestión de autenticación, analíticas básicas y distribución de las aplicaciones. Con ello, puede afirmarse que la plataforma alcanzó un nivel de madurez suficiente para ser utilizada en contextos reales de prueba con estudiantes de primeros ciclos.

​	En el plano institucional, LevelUp Journey demuestra un **impacto potencial significativo y sostenible**. Al ofrecer un canal centralizado para la comunicación académica, la plataforma contribuye a mejorar la continuidad de los estudiantes, reducir la pérdida de información crítica y fortalecer la percepción de acompañamiento por parte de la universidad. Esto tiene efectos directos en indicadores como la retención en los primeros ciclos, la participación en actividades formativas y el aprovechamiento de oportunidades académicas. Asimismo, la herramienta facilita que docentes y coordinaciones gestionen mejor sus comunicaciones, disminuyendo la dependencia de canales informales y la carga asociada a aclaraciones y mensajes redundantes.

​	La **segmentación bien definida** —centrada en estudiantes de primero a tercer ciclo y profesores que dictan en dichas etapas— ha sido clave para asegurar que las funcionalidades diseñadas respondan a necesidades específicas. Los estudiantes encuentran en la plataforma un entorno donde la información está organizada, priorizada y enriquecida con elementos motivacionales, mientras que los docentes disponen de un canal formal que les permite difundir anuncios con mayor trazabilidad e impacto. Esta alineación entre segmento objetivo y propuesta de valor incrementa las probabilidades de adopción y uso sostenido.

​	Finalmente, los resultados de todos los sprints permiten concluir que LevelUp Journey posee **proyección de escalabilidad y expansión regional**. Si el piloto en la UPC demuestra mejoras en indicadores de organización, participación y permanencia, el modelo puede adaptarse a otras facultades y a instituciones de educación superior de la región que enfrentan problemáticas similares de deserción temprana. La solución no solo atiende un problema concreto, sino que propone un marco replicable donde la tecnología, la gamificación y el enfoque centrado en el usuario convergen para acompañar a los estudiantes en una etapa decisiva de su trayectoria académica.

## Conclusiones y recomendaciones.

​	A partir del desarrollo completo de **LevelUp Journey**, la validación de hipótesis mediante Lean UX y el despliegue operativo en Firebase para Flutter y Android nativo, se plantean las siguientes recomendaciones orientadas a la mejora continua, escalabilidad y sostenibilidad institucional del proyecto:

​	En primer lugar, se recomienda **continuar con el proceso de validación continua con usuarios reales**, especialmente estudiantes de primeros ciclos y docentes, a fin de medir el grado de utilidad, adopción y satisfacción con las funcionalidades implementadas. Si bien los prototipos y el MVP permitieron validar supuestos clave, es necesario ampliar el alcance de las pruebas con grupos más diversos, cursos de distintas facultades y escenarios académicos con mayor volumen de anuncios. Esta evaluación permitirá priorizar nuevas funcionalidades y corregir posibles fricciones en la experiencia de usuario.

​	En segundo lugar, resulta fundamental **fortalecer la capa de gamificación**, ya que representa uno de los pilares diferenciales del proyecto. Se recomienda enriquecer los sistemas de logros y niveles con dinámicas más profundas, tales como retos colaborativos, objetivos semanales o recompensas simbólicas que motiven la participación sostenida. Asimismo, se puede evaluar la incorporación de tableros de progreso, comparativas anónimas entre compañeros y badges de constancia, elementos que incrementan el engagement académico.

​	Una tercera recomendación consiste en **ampliar y optimizar la arquitectura técnica del backend**, considerando la integración con servicios institucionales. Es recomendable avanzar hacia una infraestructura modular más robusta, con microservicios desacoplados, APIs mejor documentadas y un sistema de logs y monitoreo que permita escalar sin comprometer el rendimiento. Además, implementar analíticas más avanzadas permitirá identificar patrones de interacción, tiempos de lectura de anuncios y métricas de retención, información clave para futuras decisiones estratégicas.

​	Asimismo, se sugiere desarrollar un **panel web administrativo para docentes, coordinadores y áreas académicas**, donde puedan gestionar comunicados, revisar estadísticas y programar avisos con mayor comodidad. Esta interfaz reforzará la adopción por parte del personal institucional y reducirá la dependencia de dispositivos móviles, facilitando una gestión más ordenada y profesional del flujo informativo.

​	Otra recomendación es **establecer alianzas con facultades específicas** para implementar pilotos escalonados. La expansión gradual permitirá asegurar que el producto se adapte a las características de cada programa académico, evitando un despliegue masivo prematuro sin antes considerar necesidades locales. A partir de estos pilotos, la universidad podría evaluar indicadores de impacto como participación en actividades, cumplimiento de entregas y reducción de consultas repetitivas.

​	Finalmente, para garantizar la sostenibilidad a largo plazo, se aconseja **estructurar un roadmap evolutivo** que contemple mejoras funcionales, nuevas integraciones y mantenimiento continuo. Este roadmap debe incluir hitos trimestrales, priorización basada en datos y mecanismos de retroalimentación permanente con usuarios. Asimismo, sería beneficioso evaluar la integración futura con herramientas institucionales como intranets, sistemas de matrícula o plataformas académicas internas, lo que permitiría consolidar a LevelUp Journey como un ecosistema de comunicación integral.

​	En síntesis, las recomendaciones buscan asegurar que LevelUp Journey evolucione desde un MVP funcional hacia una plataforma madura, escalable y alineada con las necesidades reales de estudiantes y docentes, manteniendo su enfoque en gamificación, centralización informativa y mejora continua basada en evidencia.

## Video App Validation



<img src="https://i.imgur.com/t99ZZF4.png" alt="UPC-LOGO"/>

Anexo: https://www.youtube.com/watch?v=Dt2aWnbycKQ



<img src="https://i.imgur.com/KRqzzw4.png" alt="UPC-LOGO"/>

Anexo: https://youtu.be/Dt2aWnbycKQ

## Video About the product

<img src="https://i.imgur.com/ldmtGYb.png" alt="UPC-LOGO"/>

https://youtu.be/-JoEPhY6FNc



## Video About the team

<img src="https://i.imgur.com/CgUZpoy.png" alt="UPC-LOGO"/>



https://youtu.be/QQoHhhnBDXo