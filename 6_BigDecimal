                import java.math.BigDecimal;
                public class Account 
                {  
                   private String name; // instance variable 
                   private BigDecimal balance; // instance variable and change double to BigDecimal

                   // Account constructor that receives two parameters  
                   public Account(String name, double balance) 
                   {
                      this.name = name; // assign name to instance variable name

                      // validate that the balance is greater than 0.0; if it's not,
                      // instance variable balance keeps its default initial value of 0.0
                      if (new BigDecimal(balance).compareTo(new BigDecimal(0)) != 0)// if the balance is valid
                      {
                         this.balance = new BigDecimal(balance); // assign it to instance variable bigdecimal balance
                      }
                   }

                   // method that deposits (adds) only a valid amount to the balance
                   public void deposit(double depositAmount) 
                   {      
                      if (depositAmount > 0.0) // if the depositAmount is valid
                      {
                        balance = balance.add(new BigDecimal(depositAmount)); // add it to the balance 
                      }
                   }

                   // method returns the account balance
                   public BigDecimal getBalance()
                   {
                      return balance; 
                   } 

                   // method that sets the name
                   public void setName(String name)
                   {
                      this.name = name; 
                   } 

                   // method that returns the name
                   public String getName()
                   {
                      return name; 
                   } 
                } // end class Account 
                =========================================================
                import java.util.Scanner;

                public class TestAccount 
                {
                    public static void main(String[] args)
                    {
                        Scanner in = new Scanner(System.in);
                        Account acnt1 = new Account("Alejandra Avitia", 80.50);
                        Account acnt2 = new Account("Alberto Avitia", -11.56);
                        double depositAmnt = 0;
                        //Display
                        System.out.printf("%s%s%.2f\n", acnt1.getName(), " balance: $", acnt1.getBalance());
                        System.out.printf("%s%s%.2f\n", acnt2.getName(), " balance: $", acnt2.getBalance());

                        System.out.print("Enter the deposit for the first account: $");
                        depositAmnt = in.nextDouble();
                        System.out.printf("\n%n%s%.2f%s%n%n", "Depositing ", depositAmnt, " to the first account's balance!");
                        //Adding it
                        acnt1.deposit(depositAmnt);

                        //Display updated account for #1
                        System.out.printf("%s%s%.2f\n", acnt1.getName(), " balance: $", acnt1.getBalance());
                        System.out.printf("%s%s%.2f\n", acnt2.getName(), " balance: $", acnt2.getBalance());

                        System.out.print("Enter the deposit for the second account: $");
                        depositAmnt = in.nextDouble();
                        System.out.printf("\n%n%s%.2f%s%n%n", "Depositing ", depositAmnt, " to the second account's balance!");
                        //Adding it
                        acnt2.deposit(depositAmnt);

                        //Display updated account for #2
                        System.out.printf("%s%s%.2f\n", acnt1.getName(), " balance: $", acnt1.getBalance());
                        System.out.printf("%s%s%.2f\n", acnt2.getName(), " balance: $", acnt2.getBalance());
                    }
                }
