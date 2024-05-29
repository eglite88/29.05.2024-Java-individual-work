# 29.05.2024-Java-individual-work


/*
Develop a simple book management application with ArrayList.
User should be able to add a book to ArrayList.
User should be able to remove a book from ArrayList.
User should be able to delete a book from ArrayList.

Easy: Work with String in ArrayList. All the actions should be available for user.

Medium: Work with String User should be able to repeat all the actions infinitely.

Hard: Create a Book class and work with Book object to the ArrayList.
*/
import java.util.ArrayList;
import java.util.stream.Collectors;
import java.util.Scanner;


public class Main {
  public static void main(String[] args) {
    
    printWelcome();
    System.out.println(); 
    
    var books = new ArrayList<String>();
    var scanner = new Scanner(System.in);
    while (true) {
                System.out.println("Enter the name of the book you want to add or type exit to stop: ");
              var item = scanner.nextLine(); 
                if(item.equals("exit")){
                    break;
                }
                addItem(books, item);
            }
            printArrayList(books);

            System.out.println("If you want to remove book from AWESOME BOOKS, please write book name:");
            var itemToRemove = scanner.nextLine(); 
              books.removeIf(item -> item.equals(itemToRemove));

            printTakeOutItem(books, itemToRemove); 
            printArrayList(books);

  
        } //closing void main method

       public static void printWelcome() {
    System.out.print("Welcome to book application AWESOME BOOKS");  
  }
  
        public static void printArrayList(ArrayList<String> items) {
            System.out.println("You have added following books:");
            for (String item : items) {
                System.out.println(item);
            }
        }

        public static void addItem(ArrayList<String> books, String item) {
            books.add(item); 
            System.out.println(item + " has been added to AWESOME BOOKS "); 
        }

      public static void printTakeOutItem(ArrayList<String> books, String item) {
           books.remove(item);
           System.out.println(item + " has been removed from AWESOME BOOKS "); 
  }
  
    } //closing class main 
    
