
Appweb Angular 6, Java 1.8, Srping Boot

OS iOS , Android
Postgres
Back end API


Posible migracion de OnPremise a Cloud Publico sin datos criticos

Fase: aplicaciones en mantenimiento correctivo
Versiones tardan meses

Scrum como framework agil

Preferencia con Opensource


1) Realiza un pequeño diagrama de componentes de alto nivel que refleje la solución propuesta y que
dé cobertura global al conjunto de aplicaciones.


![Diagrama](https://raw.githubusercontent.com/siamaksade/openshift-cd-demo/ocp-4.3/images/pipeline.svg?sanitize=true)


2) Enumera y describe brevemente qué herramientas propondrías en esta solución para poder realizar
estos despliegues ágiles.

- Github: Control de versions y repositorio de codigo
- SonarCube: Analisis de la calidad del codigo
- Nexus: Repository de artefactos o binarios
- Openshift: Platforma de despligues y orquestacion de contenedores
- Quay.io: Control de versiones de contenedores
- Jenkins (Build Image): Pipeline para realizar un CICD continuada : 
    - Construir la imagen
    - test de integracion,
    - test de aceptacion
    - test rendimiento
    - subir artefactos ..

3) Propón alguna mejora a nivel metodológico para poder implantar en la organización.

TDD y BDD

Hay dos metodologias para los desarrolladores que mejorar la eficiencia y a calidad del codigo.

1.- Test Driven Development
2.- Business Driven Development

Las dos siguen un ciclo continuo de desarrollo 

La primera se basa en realizar test funcionales o de integracion como punto de partida. Despues el desarrollador  crea el codigo que hace pasar estos test. Finalmente revisa el codigo quitando las partes que no son necesarias.

![tdd](https://i2.wp.com/www.funkysi1701.com/wp-content/uploads/2017/03/tdd_flow.gif?resize=287%2C300&ssl=1)

Las ventajas ademas de la productividad es evitar que se produzcan errores en otras etapas mas avanzadas como la implentacion en produccion etc.

El segundo metodo mejora la comunicacion entre los desarrolladores y los desarralladores de negocio evitando crearun producto que no cumpla con las expectativas del mercado.

Esta metodologia utiliza un lenguaje llano y simple para poder entenderse las dos partes, create simple frases que definen como va a ser el projecto y lo que tienen que cumplir.

Muchas empresas utilizan los tests como fase ultima para la verificacion de sus productos, esta nueva metodologia se focaliza mas en entender el problema planteado y despues desarrollar el producto. Es una manera de crear restriciones (constrains) que despues el futuro producto tienen que pasar.

Las dos metodologias implantan processos automaticos de testeo para la verficacion del producto.

4) Describe el tipo de perfiles que Ibermática debería proporcionar (no hay volumetrías) para ofrecer el
servicio.



- Analista de Coste de la nube
- Arquitectos de la nube  ( conomiento en AWS,...)
- Experto en Automatizacion (scripts, python, ansible, cheff)
- Director de projecto
- Test Quality 
- Ingeniero Consultor Devops

Analista de Coste de la nube es justificable por que es uno de los quebraderos de cabeza al realizar operaciones en la nube.


5) Enumera y describe brevemente las fa
fases que debería tener este servicio, teniendo en cuenta que
hay ya otros proveedores que finalizarán servicio en la empresa cliente con la entrada en vigor de
esta nueva RFP.

1. Evangelizacion de la nueva forma de trabajar

Se presenta a los desarrolladores el nuevo paradigma/entorno de desarrollo de applicaciones

2. Creacion de Equipos agiles - 5-10% de la plantilla

Se crean equipos agiles con el 5 al 10% de la plantilla de desarrolladores.

3. Creacion del entorno de trabajo . Fase 1 MVP

Se crea grupos, usuarios, roles y politicas de identificacion
Se crea un cluster en la nube y con Openshift , este entorno de trabajo ahora con muchas opciones manuales como la identificacion en el entorno, despues se automatizaran.

4. Creacion de la actual version de la app y separacion en microservicios

Los desarrolladores empiezan a trabajar con la nueva dinamica para ir conociendo los nuevos mecanismos.
Lo mas importante empiezan a entender con la TDD pueden alcanzar sus objetivos con menos estres y mas confianza


5. MVP de la applicacion  y automatizacion del nuevo entorno CICD

A medida que los desarrolladores realizan entregas y correcciones periodicas ( cada dia varias veces) de la applicacion, el equipo de Ibermatica automatiza las authorizaciones, creacion de nuevos usuarios, creaciones de projects, etc asi como las pipeline de continua integracion y continuo despligue.

6. Escalar la solucion al resto de equipos

esta ultima fase es integrar al resto de personal de forma gradual, divido por equipos , cada equipo lidera una parte de la applicacion que estan desarrollando. 



6) Para la última de las fases propuestas en el punto anterior, pinta un pequeño cro
cronograma que refleje
las subtareas a realizar, y una aproximación del tiempo que pueden llevar cada una de ellas.

El tiempo va en funcion de la adaptacion a la tecnologia de los desarrolladores , asi como el numero de personas que integran en Ibermatica.

6 meses de la 1-5
6 meses en la ultima fase


7) Describe al menos 3 SLA que propondrías al cliente que pudieran penalizar al proveedor.

1.- Seguridad y privacidad de los datos
Todos los datos son encriptados y guardados en un servidor HA, los passwords, secrets, claves de cifrado, etc.
son automaticamente gestionados y solo administradores de la parte del cliente podran ceder autorizaciones.

2.- Rendimiento ( maximo tiempo de respuesta 1h )
En caso de necesidad de respuesta urgente el tiempo maximod de accion es de una hora


3.- Disponibilidad del servicio CICD ( 99% 24h,7 dias semana )
esta clausula garantiza tener un sistema de desarrollo y produccion efectivo la mayor parte del tiempo con muy pocas incidencias.

4.- Expectativas de recuperacion ante desastre ( 3 horas )
En caso el cluster se venga abajo, Ibermatica se compromete en restablecer el sistema en menos de 3 horas.

La seguridad y la rapidez del servicio son muy bien valorados por el cliente.


8) Enumera 3 formaciones que se pueden impartir al cliente par que adquiera el conocimiento de la
solución propuesta, indicando número de jornadas y asistentes aproximado.

Las formaciones pueden realizarse de forma online ya que el aprendizaje es diferente  y a diferentes tiempo para diferentes personas.

Se pueden realizar presentaciones de las herramientas a modo introductorio y crearles un entorno de test para que los desarrolladores no tengan ese miedo de utilizar una herramienta nueva.

- Admin de Usuarios y seguridad en la nube
- Creacion y administracion de projectos en Github y metodologia de trabajo
  - Name conventions
  - Open API 3.0 standard
- Kibana una solucion para la monitorizacion de logs
  - Crear hans-on para monitorizar errores de la applicacion en los tres entronos de trabjao (dev, stage, prod) 

Como modelo de negocio para Ibermatica mas que ensenyar las herramientas en si , seria ensenyarles y guiarles como deberian trabajar con las heramientas. Por ejemplo incidir mas en las mejores practicas y metodologias de trabajos que mejoran el producto al final de su ciclo de vida.

9) Este apartado es independiente de los anteriores. Supón que el conjunto de perfiles y herramientas
propuestos con sus costes asociados, da un importe de 3 millones de euros. Sabemos que el cliente
no va a pagar por este servicio más de 2 millones. Describe brevemente qué opciones se te ocurren
para conseguir adaptar el importe inicial al que quiere el cliente.

Opciones:

- Usar parte de su plantilla para ayudar a Ibermatica a realizar la implementacion.
  con lo que Ibermatica puede reducir el servicio.
- Realizar un contrato de mantenimiento de larga duraccion una vez haya cumplido el servicio.
  Con ello Ibermatica puede fidelizar el cliente y acceder a otro tipo de necesidades, que seguro las tendra.

