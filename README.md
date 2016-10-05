# RXJAVA
### Concepto previo
El flujo de trabajo con RxJava será normalmente el siguiente: creación de un Observable el cual emite los datos que queremos recibir, transformación de dichos datos y trabajo con ellos. Este Observable equivale al Subject que teníamos en el patrón Observer.

Los datos emitidos serán recibidos por dos tipos de entidades: Observers y Subscribers. Observer nos define la siguiente interfaz:

```java
public interface Observer<T> {
    void onCompleted();
    void onError(Throwable e);
    void onNext(T t);
}
```
Los métodos arriba definidos son básicos y hay que tener muy claro qué hace cada uno:
* [onCompleted()]: se notifica al observador que el observable al que está suscrito ha dejado de emitir
* [onError()]: se notifica que el observable ha tenido un error.
* [onNext()]: se le da al observador un nuevo ítem emitido por el observable.