                              import java.util.Scanner;
                              import java.text.NumberFormat;
                              import java.text.DecimalFormat;

                              public class TaxCalculator { 
                                  public static void main(String[] args){
                                      //define needed variables
                                      double total_collected, sales, county_salestx, state_salestx, total_salestx;
                                      double statetx = .0675;
                                      double countytx = .0310;
                                      int year;
                                      String month;

                                      //get input necessary
                                      Scanner in = new Scanner(System.in);
                                      System.out.print("Please enter the month: ");
                                      month = in.next();
                                      System.out.print("Enter total amount collected: ");
                                      total_collected = in.nextDouble();
                                      System.out.print("Enter the year: ");
                                      year = in.nextInt();

                                      //perform calculations
                                      sales = calculateSales(total_collected);
                                      county_salestx = sales*countytx;
                                      state_salestx = sales*statetx;
                                      total_salestx = state_salestx + county_salestx;

                                      //print out the answers
                                      NumberFormat nf = new DecimalFormat("#0.00");
                                      System.out.println("\nMonth: " + month + " " + year);
                                      System.out.println("----------------------------------");
                                      System.out.println("Total Collected:\t$ " + nf.format(total_collected));
                                      System.out.println("Sales:  \t\t$ " + nf.format(sales));
                                      System.out.println("County Sales Tax:\t$ " + nf.format(county_salestx));
                                      System.out.println("State Sales Tax:\t$ " + nf.format(state_salestx));
                                      System.out.println("Total Sales Tax:\t$ " + nf.format(total_salestx));
                                  }

                                  //calculate sales from total.
                                  //return as a double rounded to 2 decimal places
                                  public static double calculateSales(double total){
                                      double sales = 0.0;
                                      sales = total / 1.0985;
                                      sales = Math.round(sales*100.0) / 100.0;
                                      return sales;
                                  }
                              }
