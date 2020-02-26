Buenas tardes, disculpa la tardanza en enviar el código la verdad he estado algo ocupado con entregas.
Este projecto tal cual es el que todos encontramos para tomar de ejemplo la prueba, en vez de hacer modificaciones para enviarte algo funcional lo explicare

Empezamos por la naturaleza del proyecto se encuentra en rxjs-5.5.12 algo con lo que se toparon mis colegas es que no podian correrlo por el cambio que hubo en el core de ng6+ hay dos formas de solucionar esto, haciendo un downgrade de ng para que acepte la versión de rxjs, para esto yo recomiendo usar N o NVM para manejar las versiones que usaremos de node y poder trabajar en diversos ambientes, la otra actualizar rxjs a su version 6+ y dentro del modulo existe rxjs/compat que hace alución a compatible para evitar hacer la migración completa de la logica rxjs y sus observables.

Pasando a otro tema el servidor en este proyecto tiene pocos endpoints habría que editar server/index.js agregar los metodos de envio de chat recepción 1 a 1, 1 a muchos y crear en este el servicio de conversión de emoticones por expresión regular y un diccionario

el proyecto esta estrucutrado muy simple su front viene a ser client donde habría que crear los componentes dentro de src/app para el consumo de los servicios lo que haria seria estructurar la arquitectura del projecto creando un folder de services dentro del gua moveria el archivo de chat.services, igual otras arquitecturas manejan providers, el punto es buscar un mejor orden del proyecto, igual los componentes se estrucuturarian mejor en un views o pages y componentes modulares para tener page/principal.ts que invoque componentes components/text-area.ts, main-chat private-chata etc a manera de poder armar un chatroom y chats privados

en cuanto al empleo de docker, escribiria el dokerfile para que corar los comandos npm i, node index, npm build, node build/ habria que crear la imagen y realizar el deploy, un error comun es el docker login, para montarlo en la nube sudo r ~/.docker/config.json && docker login && docker-compose up seran buenos aliados para los ambientes locales/dev para puesta en la nube habra que explorar mas la arquitectura para asignar puertos y buscar que docker pueda hacer replicas y levantarse en caso de caer los servicios.

Quizá no sea un formato convencional entregar un codigo pero creeo es mejor mostrar la comprensión que solo enviar algo que encontre modificarlo y esperar puedan arrancar el proyecto, las bases es saber donde modificar el código, que versiones estas usando, y como se haran los releases para tener un buen manejo del proyecto.

Ismael Esquinca
adrakiel@gmail.com