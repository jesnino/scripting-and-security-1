# Crear un hilo heredando de la clase Thread
## Java, Processes, Threads 
### URL: https://www.jesusninoc.com/2012/08/30/crear-un-hilo-heredando-de-la-clase-thread/
```Java
import java.util.concurrent.TimeUnit;

public class HelloThread extends Thread {
    public void run() {
    	System.out.println("Ejecutando hilo");
        System.out.println(Thread.currentThread().getName());
    }
    public static void main(String args[]) {
    	System.out.println(Thread.currentThread().getName());
    	int i=0;
    	while(i<100)
    	{
        (new HelloThread()).start();
        try {
			TimeUnit.SECONDS.sleep(10);
		} catch (InterruptedException e) {
			e.printStackTrace();
		}
        i++;
    	}
    }
}

```
