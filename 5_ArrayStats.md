          import java.util.Scanner;

          public class ArrayStatistics
          {
              public static void main(String[] args)
              {
                  Scanner in = new Scanner(System.in);
                  int size;
                  double min;
                  double max;
                  double avg;
                  double popStd;
                  double sampleStd;
                  System.out.print("How many number of the type double do you want to store in your array? ");
                  size = in.nextInt();

                  double[] myArray = new double[size];

                  //Populating the Array
                  for(int i= 0; i < size; i++)
                  {
                      System.out.printf("%s%d%s", "Enter a value #", (i+1), ": ");
                      myArray[i] = in.nextDouble();
                  }
                  //finding min and max and average
                  min = getMin(myArray);
                  max = getMax(myArray);
                  avg = getAvg(myArray);
                  popStd = getPSD(myArray, avg, size);
                  sampleStd = getSSD(myArray, avg, size);

                  //Display 
                  System.out.println("\nThe statistics for your user entered array are: ");
                  System.out.println("------------------------------------------------\n");
                  System.out.printf("%32s%10.3f%n","Minimum:", min);
                  System.out.printf("%32s%10.3f%n","Maximum:", max);
                  System.out.printf("%32s%10.3f%n","Average:", avg);
                  System.out.printf("%32s%10.3f%n","Standard deviation (population):", popStd);
                  System.out.printf("%32s%10.3f%n","Standard deviation (sample):", sampleStd);
              }
              //Method for finding the minimum
              public static double getMin(double[] array)
              {
                  double min = array[0];
                  for(int i = 1; i < array.length;i++)
                  {
                      if(array[i]< min)
                      {
                          min = array[i];
                      }
                  }
                  return min;         
              }
              //Method for find the maximum 
              public static double getMax(double[] array)
              {
                  double max = array[0];
                  for(int i = 1; i < array.length;i++)
                  {
                      if(array[i] > max)
                      {
                          max = array[i];
                      }
                  }
                  return max;         
              }
              //Method for finding the average
              public static double getAvg(double[] array)
              {
                  double sum = 0;
                  double avg = 0;
                  for(int i = 0; i < array.length; i++)
                  {
                      sum += array[i];
                  }
                  avg = sum / array.length;
                  return avg;
              }
              //Method for population standard deviation
              public static double getPSD(double[] array,double avg, int size)
              {
                  double[] diffArray = new double[size];
                  double[] squaredDiff = new double[size];
                  double sum = 0;
                  double popStd = 0;
                  //This is just for finding the diffrences
                  for(int i = 0; i < size; i++)
                  {
                      diffArray[i]= array[i] - avg;
                  }
                  //Square the differences
                  for(int i= 0; i < size; i++)
                  {
                      squaredDiff[i] = diffArray[i]  * diffArray[i];
                      sum += squaredDiff[i];
                  }
                  popStd = Math.sqrt(sum / size); 
                  return popStd;
              }
              //Now for sample standard
              public static double getSSD(double[] array,double avg, int size)
              {
                  double[] diffArray = new double[size];
                  double[] squaredDiff = new double[size];
                  double sum = 0;
                  double smpStd = 0;
                  //This is just for finding the diffrences
                  for(int i = 0; i < size; i++)
                  {
                      diffArray[i]= array[i] - avg;
                  }
                  //Square the differences
                  for(int i= 0; i < size; i++)
                  {
                      squaredDiff[i] = diffArray[i]  * diffArray[i];
                      sum += squaredDiff[i];
                  }
                  smpStd = Math.sqrt(sum / (size-1)); 
                  return smpStd;
              }

          }
