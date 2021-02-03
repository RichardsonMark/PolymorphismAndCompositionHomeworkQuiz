# Polymorphism & Composition Homework - Quiz

# Polymorphism

1. What does the ___word___ 'polymorphism' mean?
-   The word polymorphism means: Many forms.

2. What does it mean when we apply polymorphism to OO design? Give a simple Java example.
- Polymorphism applied to OO design means treating a class as if it is more than one type or class at the same time. For instance, you could have a 'Desktop' and a 'Printer' both are a desktop and a printer on their own, but can also 'connect things', as shown here where both can now 'connect' to a network:

```java

public interface IConnect {
  public String connect(String data);
}


public class Desktop implements IConnect {
    public String connect(String data) {
      return "connecting to network: " + data;
    }


  public class Printer implements IConnect{
      public String connect(String data) {
        return "connecting to " + data + " network";
      }
  }

```

3. What can we use to implement polymorphism in Java?
- You can use interfaces and abstract classes.

4. How many 'forms' can an object take when using polymorphism?
- As many as is needed.

5. Give an example of when you could use polymorphism.
- Expanding the example above in question 2, if you wanted to add those devices to an ArrayList of devices connected to the network, you can add those different types to the collecton using polymorphism.

```java

  private ArrayList<IConnect> devices;

    public Network(String name){
        this.devices = new ArrayList<IConnect>();
        this.name = name;
    }

```


# Composition

6. What do we mean by 'composition' in reference to object-oriented programming?
- Composition is when objects are used/put together to make up another object to get the functionality needed.

7. When would you use composition? Provide a simple example in Java.
- When you want to have an object which is made up of other objects/'has' other objects in it. Below is an example of an Electric car from our lab today:

```java

public class Electric extends Car {

    private int batteryCapacity;

    public Electric(ArrayList<IPower> fuel, int price, String colour, String model) {
        super(fuel, price, colour, model);
    }


public abstract class Car {

    private ArrayList<IPower> fuel;
    private int price;
    private String colour;
    private String model;

    public Car(ArrayList<IPower> fuel, int price, String colour, String model) {
        this.fuel = fuel;
        this.price = price;
        this.colour = colour;
        this.model = model;
    }


Electricity electric = new Electricity();
ArrayList<IPower> fuel = new ArrayList<>();
fuel.add(electric);

electricCar = new Electric(fuel, 15000, "Blue", "Zappy900");

```

8. What is/are the advantage(s) of using composition?
- Dependency Inversion. Pieces can be changed or even fully replaced without having to worry about any inheritance.

9. When an object is destroyed, what happens to all the objects it is composed of?
- They too get destroyed.
