package fal18;

public class SkiRental extends SportShopRental
{
    //Creating a private int name size & intialized to 175
    private int size = 175; 
    
    //Set and Gets
    public int getSize()
    {
        return this.size;
    }
    public void setSize(int size)
    {
        if(size < 50 || size > 200)
        {
            throw new IllegalArgumentException("Size out of range");
        }
        else
        {
            this.size = size; 
        }
    }
    //the toString
    @Override
    public String toString()
    {
        return String.format("Rental #%d%s%7.2f%s%b%s%4d%s", getRentalNumber(), ", Cost: $" 
            ,getRentalCost(), ", New: ", isNewModel(), ", Size: " 
                ,this.size , " cm");
    }
    
    @Override
    public double lateCharge()
    {
        return getRentalCost() * .10;
    }
    
    
}
-===============package fal18;

// 25 pts total (15 points for correct implementation (3 pts per section below), 10 points code passes all unit test).
// Refer to the UML class diagram for naming of all methods in this class: SnowMobileRentalUML.pdf

// 1. Create public class named SnowMobileRental that inherits SportShopRental
public class SnowMobileRental extends SportShopRental
{
    //declaring my varibale and initializing them 
    private int capacity =1;
    private String vin = "1A234567890123456789";
    
    //Get and Sets
    public int getCapacity()
    {
        return this.capacity;
    }
    public void setCapacity(int capacity)
    {
        if(capacity< 1 || capacity > 3)
        {
             throw new IllegalArgumentException("Capacity out of range");
        }
        else
        {
           this.capacity = capacity;
        }
        
    }
    public String getVin()
    {
        return this.vin;
    }
    public void setVin(String vin)
    {
        if (vin.length() > 20)
        {
            throw new IllegalArgumentException("Vin cannot be more than 20 characters");
        }
        else
        {
            this.vin = vin;
        }
    }
    
    //The toString
    @Override
    public String toString()
    {
        return String.format("Rental #%d%s%7.2f%s%b%s%1d%s%s", getRentalNumber(), ", Cost: $" 
            ,getRentalCost(), ", New: " + isNewModel(), ", Capacity: "
            ,this.capacity, " seat, Vin: ", this.vin);
    }
    //Implementing the abstract method
    @Override
    public double lateCharge()
    {
        return (20 + this.capacity * 5) * 100;
    }
    
}
==============
package fal18;

// 25 pts total (15 points for correct implementation (3 pts per section below), 10 points code passes all unit test).
// Refer to the UML class diagram for naming of all methods in this class: SnowboardRentalUML.pdf

public class SnowboardRental extends SportShopRental
{
    //Declaring my varibale and initaliazing them
    private int size = 140;
    private boolean freestyle = true;
    
    
    //Set/Get 
    public int getSize()
    {
        return this.size;
    }
    public void setSize(int size)
    {
        if(size < 50 || size > 180)
        {
            throw new IllegalArgumentException("Size out of range");
        }
        else
        {
            this.size = size;
        }
    }
    public boolean isFreestyle()
    {
        return this.freestyle;
    }
    public void setFreestyle(boolean freestyle)
    {
        this.freestyle = freestyle;
    }
    
    //To string
    public String isString()
    {
        return String.format("Rental #%d%s%7.2f%s%b%s%4d%s%b", getRentalNumber(), ", Cost: $" 
                , getRentalCost(), ", New: ", isNewModel(),", size: "
                ,this.size ,"cm, " ,this.freestyle);
    }
    //Implementing lateCharge
    @Override
    public double lateCharge()
    {
        return getRentalCost() * .20;
    }
}
======================
package fal18;

// 25 pts total (15 points for correct implementation (3 pts per section below), 10 points code passes all unit test).
// Refer to the UML class diagram for naming of all methods in this class: SportShopRentalUML.pdf

// 1. Create abstract class named SportShotRental.
abstract class SportShopRental
{
    //Creating my member variable and initializing them
    private boolean newModel = false; 
    private double rentalCost = 25.0;
    private long rentalNumber = 1;

    //Gets/Sets for private members.
    public boolean isNewModel()
    {
        return this.newModel;
    }
     public void setNewModel(boolean newModel)
    {
        this.newModel = newModel;
    }
    public double getRentalCost()
    {
        return this.rentalCost;
    }
     public void setRentalCost(double rentalCost) 
    {
        if(rentalCost <= 0) //Threw an IllegalArugmentExcetion for invalid data.
        {
            throw new IllegalArgumentException("RentalCost out of range");
        }
        else
        {
            this.rentalCost= rentalCost;
        }
    }
     public long getRentalNumber()
    {
        return this.rentalNumber;
    }
    public void setRentalNumber(long rentalNumber)//Threw an IllegalArugmentExcetion for invalid data.
    {
        if(rentalNumber < 1 || rentalNumber > 999999999999L)
        {
            throw new IllegalArgumentException("RentalNumber out of range");
        } 
        else 
        {
            this.rentalNumber= rentalNumber;
        }
    } 
     //Overrided methods that returns a formatted string
    @Override
    public String toString()
    {
        return String.format("Rental #%d%s%7.2f%s%b", this.rentalNumber,", Cost: $" 
                ,this.rentalCost ,", New: ",this.newModel);
    }
    
    //Abstract method lateCharge that will return the late chare as a double
    abstract public double lateCharge();
}


 

