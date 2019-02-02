                        import java.util.Scanner;
                        public class MinAndMax
                        {
                            public static void main(String[] args)
                            {
                                //declaring needed variables
                                int min = Integer.MAX_VALUE;
                                int max = Integer.MIN_VALUE;
                                int one, two, three, four;
                                Scanner in = new Scanner(System.in);

                                //prompt for input and keep track of min and max values
                                System.out.print("Enter the first value: ");
                                one = in.nextInt();
                                min = one < min ? one : min;
                                max = one > max ? one : max;

                                System.out.print("Enter the second value: ");
                                two = in.nextInt();
                                min = two < min ? two : min;
                                max = two > max ? two : max;

                                System.out.print("Enter the third value: ");
                                three = in.nextInt();
                                min = three < min ? three : min;
                                max = three > max ? three : max;  

                                System.out.print("Enter the fourth value: ");
                                four = in.nextInt();
                                min = four < min ? four : min;
                                max = four > max ? four : max;

                                //display variables to user
                                System.out.printf("The values entered: %d, %d, %d, %d. "
                                        + "have a minimum value of %d and a maximum of %d. ",
                                        one, two, three, four, min, max);
                            }
                        }
