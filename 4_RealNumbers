        import java.util.Scanner;

        public class PerfectNumber 
        {
            public static void main(String[] args)
            {
                int num = 0;
                int sum = 0;
                String factors;
                Scanner in = new Scanner(System.in);

                System.out.print("Enter the largest number to try to display: ");
                num = in.nextInt();
                while(num > 10000)
                {
                    System.out.print("Please enter a number in the range of 2-10,00: ");
                    num = in.nextInt();
                }

                for(int i =2; i < num; i++)
                {
                    for(int j= 1; j<i; j++)
                    {
                        if((i%j)==0)    
                        {
                            sum+=j;
                        }
                    }
                    if(sum == i)
                    {
                        System.out.println(i + " is a Perfect Number! ");
                        factors = isPerfect(i);
                        System.out.println("Factors: " + factors);
                    }
                }
            }

            public static String isPerfect(int number)
            {
                String factors = "";
                for(int i=1; i < number; i++)
                {
                    if((i%number)==0)
                    {
                      factors += Integer.toString(i);  
                    }
                }
                return factors;
            }

        }
