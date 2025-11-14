# Introdução (1 minuto):
Apresentação sobre outros exemplos relacionados a Threads. <br>
## Diferença entre Thread e runnable:
Ambas têm a mesma função, que é permitir executar várias tarefas de forma concorrente, mas Thread é uma superclasse e Runnable é uma interface. <br>
Isso significa que uma classe que herdar de Thread não pode herdar de nenhuma classe, já uma classe pode herdar de uma super classe qualquer e implementar Runnable. <br>
Além disso, um objeto Runnable pode ser usado por várias threads. <br>
# Execução (3 minutos):
## Exemplo simples com Thread:
```java
public class ThreadExample extends Thread {
   public void run() {
      System.out.println("Thread is running");
   }

   public static void main(String args[]) {
      ThreadExample t1 = new ThreadExample();
      t1.start();
   }
}
```
## Exemplo simples run Runnable:
```java
public class RunnableExample implements Runnable {
   public void run() {
      System.out.println("Thread is running for Runnable Implementation");
   }

   public static void main(String args[]) {
      RunnableExample runnable = new RunnableExample();
      Thread t1 = new Thread(runnable);
      Thread t2 = new Thread(runnable);
      t1.start();
      t2.start();
   }
}
```
## Exemplo com classe que herda de outra e implementa Runnable:
```java
class Animal {

    protected String name;

    public Animal(String name) {
        this.name = name;
    }

    public void makeSound() {
        System.out.println("Generic animal noises.");
    }
}

class Cat extends Animal implements Runnable {

    public Cat(String name) {
        super(name);
    }

    @Override
    public void makeSound() {
        System.out.println(name + " says meow.");
    }

    @Override
    public void run() {
        System.out.println(name + " is running.");
        this.makeSound();
    }
}

public class Main {

    public static void main(String[] args) {
        Cat myCat = new Cat("Garfield");
        Thread catAction = new Thread(myCat);
        Thread catAction2 = new Thread(myCat);
        catAction.start();
        catAction2.start();
        new Thread(myCat).start();
        new Thread(myCat).start();
        new Thread(myCat).start();
        new Thread(myCat).start();
        new Thread(myCat).start();
        new Thread(myCat).start();
    }
}

```
# Vídeo (30 segundos):
<video width="320" height="240" controls>
  <source src="video.mp4" type="video/mp4">
</video>

# Fontes:
1. <https://liascript.github.io/course/?https://raw.githubusercontent.com/AndreaInfUFSM/elc117-2025b/main/classes/28/README.md#1>
2. <https://www.w3schools.com/java/java_threads.asp>
3. <https://medium.com/javarevisited/java-threads-and-its-methods-c3cb20dde51c>
4. <https://stackoverflow.com/questions/2865315/threads-in-java>
5. <https://www.reddit.com/r/learnjava/comments/jhakoz/what_is_java_threads/>
6. <https://www.geeksforgeeks.org/java/java-threads/>
7. <https://docs.oracle.com/javase/8/docs/api/java/lang/Thread.html>
8. <https://www.tutorialspoint.com/difference-between-thread-and-runnable-in-java>
9. <https://www.geeksforgeeks.org/java/implement-runnable-vs-extend-thread-in-java/>
