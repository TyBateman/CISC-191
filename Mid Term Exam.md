Question 1:

```java
import java.util.Scanner;

class InventoryControl
{
    String itemName;
    String companyName;

    public InventoryControl(String name, String companyName)
    {
        this.itemName = itemName;
        this.companyName = companyName;
    }

    public void updateInventory()
    {
        Scanner scanner = new Scanner(System.in);
        System.out.print("Enter New Item: ");
        this.itemName = scanner.nextLine();
        System.out.print("Enter New Item Company Name: ");
        this.companyName = scanner.nextLine();
    }

    public void displayInventory()
    {
        System.out.println("Item Name: " + itemName);
        System.out.println("Company: " + companyName);
    }
}

import java.util.Scanner;

class Painkillers extends InventoryControl
{
    String expirationDate;
    String ageGroup;

    public Painkillers(String name, String companyName, String expiryDate, String ageGroup)
    {
        super(name, companyName);
        this.expirationDate = expirationDate;
        this.ageGroup = ageGroup;
    }
    
    @Override
        public void updateInventory()
        {
        super.updateInventory();
        Scanner scanner = new Scanner(System.in);
        System.out.print("Enter New Expiration Date: ");
        this.expirationDate = scanner.nextLine();
        System.out.print("Enter New Age Group: ");
        this.ageGroup = scanner.nextLine();
    }

    @Override
    public void displayInventory()
    {
        super.displayInventory();
        System.out.println("Expiry Date: " + expirationDate);
        System.out.println("Age Group: " + ageGroup);
    }
}

import java.util.Scanner;

class Bandages extends InventoryControl {
    String expirationDate;
    String ageGroup;
    String waterproof;

    public Bandages(String name, String companyName, String expiryDate, String ageGroup, String waterproof)
    {
        super(name, companyName);
        this.expirationDate = expirationDate;
        this.ageGroup = ageGroup;
        this.waterproof = waterproof;
    }

    @Override
    public void updateInventory()
    {
        super.updateInventory();
        Scanner scanner = new Scanner(System.in);
        System.out.print("Enter New Expiration Date: ");
        this.expirationDate = scanner.nextLine();
        System.out.print("Enter New Age Group: ");
        this.ageGroup = scanner.nextLine();
        System.out.print("Waterproof? (Y/N) ");
        this.waterproof = scanner.nextLine();
    }

    @Override
    public void displayInventory() 
    {
        super.displayInventory();
        System.out.println("Expiry Date: " + expirationDate);
        System.out.println("Age Group: " + ageGroup);
        if (waterproof == "Y")
        {
            System.out.println("Waterproof: Yes");
        }
        else
        {
            System.out.println("Waterproof: No");
        }
    }
}

import java.util.Scanner;

class Equipment extends InventoryControl
{
    double itemWeight;

    public Equipment(String name, String companyName, double itemWeight)
    {
        super(name, companyName);
        this.itemWeight = itemWeight;
    }
    
    @Override
        public void updateInventory()
    {
        super.updateInventory();
        Scanner scanner = new Scanner(System.in);
        System.out.print("Enter New Item Weight: ");
        this.itemWeight = scanner.nextDouble();
    }

    @Override
    public void displayInventory() {
        super.displayInventory();
        System.out.println("Item Weight: " + itemWeight + " lbs");
    }
}
```

Question 2:

Updated Equipment to Catch Negative Weight Error:

```java
class Equipment extends InventoryControl
{
    double itemWeight;

    public Equipment(String name, String companyName, double itemWeight)
    {
        super(name, companyName);
        this.itemWeight = itemWeight;
    }
    
    @Override
        public void updateInventory()
        {
        super.updateInventory();
        Scanner scanner = new Scanner(System.in);
        System.out.print("Enter New Item Weight: ");
        this.itemWeight = scanner.nextDouble();
        if (itemWeight < 0)
        {
            System.out.println("Error: Negative Weight");
            this.itemWeight = 0;
        }
    }

    @Override
    public void displayInventory() {
        super.displayInventory();
        System.out.println("Item Weight: " + itemWeight + " lbs");
    }
}
```
Question 3:

```java
class InvalidExpirationDateException extends Exception
{
    public InvalidExpirationDateException(String message) {
        super(message);
    }
}

import java.util.Scanner;

class Painkillers extends InventoryControl
{
    String expirationDate;
    String ageGroup;

    public Painkillers(String name, String companyName, String expiryDate, String ageGroup)
    {
        super(name, companyName);
        this.expirationDate = expirationDate;
        this.ageGroup = ageGroup;
    }
    
    @Override
        public void updateInventory()
        {
        super.updateInventory();
        Scanner scanner = new Scanner(System.in);
        System.out.print("Enter New Expiration Date: ");
        this.expirationDate = scanner.nextLine();
        System.out.print("Enter New Age Group: ");
        this.ageGroup = scanner.nextLine();
    }
    
    public void updateExpiryDate() {
        Scanner scanner = new Scanner(System.in);
        boolean valid = false;
        
        //i couldn't get what i was trying to do to work in time, sorry.
        //if (valid == true)
        //{
                //System.out.print("Enter new expiry date (YYYY-MM-DD): ");
                //String newExpirationDate = scanner.nextLine();
                //if (!newExpirationDate.matches("\\d{4}-\\d{2}-\\d{2}"))
                //{
                    //throw new InvalidExpirationDateException("Invalid date format. Use YYYY-MM-DD.");
               // }
               // this.expirationDate = newExpirationDate;
              //  valid = true;
           // catch (InvalidExpirationDateException e){
                
           // }
             //   System.out.println("Error: " + e.getMessage());
        //    }
        }


    @Override
    public void displayInventory()
    {
        super.displayInventory();
        System.out.println("Expiry Date: " + expirationDate);
        System.out.println("Age Group: " + ageGroup);
    }
}

```
