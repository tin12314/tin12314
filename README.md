import java.util.Scanner;

public class Main {
public static void main(String[] args) {
Scanner scanner = new Scanner(System.in);
    System.out.println("Enter the type of pet: ");
    String animal = scanner.nextLine();
    
    System.out.println("Enter the name of the pet: ");
    String name = scanner.nextLine();
    
    System.out.println("Enter the age of the pet: ");
    int age = scanner.nextInt();
    
    Pet pet = new Pet(animal, name, age);
    pet.printInfo();
}
}

class Pet {
private String animal;
private String name;
private int age;

public Pet(String animal, String name, int age) {
    setAnimal(animal);
    setName(name);
    setAge(age);
}

public void setAnimal(String animal) {
    if(animal.equals("Cat") || animal.equals("Dog")) {
        this.animal = animal;
    }
    else {
        this.animal = "Unknown animal";
    }
}

public void setName(String name) {
    if(name == null || name.length() <= 2) {
        this.name = "ERROR";
    }
    else {
        this.name = name;
    }
}

public void setAge(int age) {
    if(age < 0 || age >= 100) {
        this.age = -1;
    }
    else {
        this.age = age;
    }
}

public void printInfo() {
    System.out.println("Pet Details:");
    System.out.println("   Name: " + name);
    System.out.println("   Age: " + age);
    System.out.println("   Animal: " + animal.charAt(0));
}
}
