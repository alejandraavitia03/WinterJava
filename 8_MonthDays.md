                public class MonthDay
                {
                    private int month;
                    private int year;
                    private int[] days = {31, 28, 31, 30, 31, 30, 31, 31, 30, 31, 30, 31};

                    public MonthDay(int mnth, int yr)
                    {
                  this.setMonth(mnth);
                  this.setYear(yr);      
                    }

                    public void setMonth(int mnth)
                    {
                        if(mnth < 1 || mnth > 12)
                        {
                            throw new IllegalArgumentException("Month out of range.");
                        }
                        else
                        {
                            this.month = mnth;
                        }
                    }

                    public void setYear(int year)
                    {
                        if(year < 0)
                        {
                            throw new IllegalArgumentException("Can't have negative year.");
                  }
                        else
                        {
                            this.year = year;
                        }
                    }

                    public int getNumberOfDays()
                    {
                        if((this.year % 100 == 0 && this.year%400 == 0 ) || (this.year % 100 != 0 && this.year % 4 == 0))
                        {
                            this.days[1] = 29;
                  }
                  return this.days[this.month-1];
                    }

                    public int getMonth()
                    {
                        return this.month;
                    }

                    public int getYear()
                    {
                  return this.year;
                    }
                }
                ============================================================================================================
                import java.util.Scanner;

                public class TestDriver 
                {
                    public static void main(String[] args)
                    {
                        int month, year;
                  Scanner in = new Scanner(System.in);
                  System.out.print("Please enter a month: ");
                  month = in.nextInt();
                  System.out.print("\nPlease enter a year: ");
                  year = in.nextInt();

                  try
                        {
                            MonthDay md = new MonthDay(month, year);
                            System.out.print("\n" + md.getMonth() + "/" + 
                     md.getYear() + " has: " + md.getNumberOfDays() +
                     " days.");
                        } 
                  catch(Exception e)
                        {
                            System.out.println(e);
                        }
                    }
                }
