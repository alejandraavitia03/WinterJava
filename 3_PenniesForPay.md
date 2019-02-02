import java.util.Scanner;

public class PennieForPay 
{
    public static void main(String [] args)
    {
        //To take input
        Scanner in = new Scanner(System.in);
        
        //define needed variables
        int daysDoubled = 0;
        double total = 0;
        double penny = 0.01; 
        
        //Prompting the user
        System.out.println("For how many days will the pay double? ");
        daysDoubled = in.nextInt();
        
        //Validate using a while loop
        while(daysDoubled < 1)
        {
            System.out.print("Please enter a number equal to or greater than 1: ");
            daysDoubled = in.nextInt();
        }
        
        System.out.println("Day\t\tTotal Pay\n-----------------------------------------");
        // for loop for display and calculations 
        for(int i = 1; i <= daysDoubled; i++)
        {
            System.out.printf("%d\t\t%s\t\t%9.2f\n", i , "$", penny);
            total += penny;
            penny *= 2;
        }
        System.out.println("-----------------------------------------");
        System.out.printf("%s\t\t%s\t\t%9.2f\n", "Total: ","$",total);
    }
}
