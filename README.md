# Patrón de Diseño: Observer

## Descripción:

Observer es un patrón de diseño de comportamiento que permite definir un mecanismo de suscripción para notificar a varios objetos sobre cualquier evento que le suceda al objeto que están observando. El objeto que es observado es denominado sujeto, notificador o también publicador, mientras que los objetos interesados en conocer los cambios de estado en el notificador son llamados observadores o suscriptores. Durante esta explicación, los llamaremos notificadores y suscriptores respectivamente.

## Problemática que resuelve:

El patrón Observer la problemática que resuelve es el hecho de que los objetos que estan interesados en el cambio de estado de otro objeto no tengan que estar consultando constantemente si sucedió el cambio frente al cual ellos tienen que ejecutar determinado accionar.

## Solución que brinda:

El patrón Observer sugiere que se añada un mecanismo de suscripción a la clase notificadora para que los objetos individuales puedan suscribirse o cancelar su suscripción a un flujo de eventos que proviene de esa notificadora. El mecanismo consiste en tener en la clase notificadora un atributo que sea una lista de referencias a objetos suscriptores, y métodos que permitan añadir/quitarlos de la lista. Entonces, cuando le sucede un evento importante al notificador, recorre sus suscriptores y llama al método de notificación específico de sus objetos.

## Pasos para implementar el patrón Observer:

1. Dividir la logica de negocio en dos partes: la funcionalidad central, independiente del resto de código, que actuará como notificador; y el resto. que se convertirá en el grupo de clases suscriptoras.

2. Declarar la interfaz suscriptora, que contenga el método actualizar.

3. Declarar la interfaz notificadora com los métodos para añadir y eliminar de la lista a un objeto suscriptor.

4 .Decidir dónde colocar la lista de suscripción y la implementación de los métodos de suscripción. Normalmente, este código es colocado en una clase abstracta derivada directamente de la interfaz notificadora. Los notificadores concretos extienden esa clase, heredando el comportamiento de suscripción. Sin embargo, si se está aplicando el patrón a una jerarquía de clases existentes, se debería considerar utilizar la composición: colocar la lógica de la suscripción en un objeto separado y hacer que todos los notificadores reales la utilicen.

5. Crear clases notificadoras concretas. Cada vez que suceda algo importante dentro de una notificadora, deberá notificar a todos sus suscriptores.

6. Implementar los métodos de notificación de actualizaciones en clases suscriptoras concretas. La mayoría de las suscriptoras necesitarán cierta información de contexto sobre el evento, que puede pasarse como argumento del método de notificación.

7. El cliente debe crear todos los suscriptores necesarios y registrarlos con los notificadores adecuados.

# Diagrama UML:

## Ventajas:

* Permite introducir nuevas clases suscriptoras sin tener que cambiar el código de la clase notificadora. 
* Permite establecer relaciones entre objetos durante el tiempo de ejecución.

## Desventajas:
* Los suscriptores son notificados en un orden aleatorio.

## Ejemplos:

1. 

2. 

3. 
