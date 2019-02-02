                  public enum TrafficSignal 
                  {
                      RED(60), YELLOW(15), GREEN(45), WALK(20), DONT_WALK(15);

                      private int num;

                      private TrafficSignal(int num)
                      {
                          this.num = num;
                      }

                      public String toString()
                      {
                          return "" + num;
                      }
                  }
                  =============================================================
                  public class TestTrafficSignal 
                  {
                      public static void main(String[] args)
                      {
                          for(TrafficSignal time: TrafficSignal.values())
                          {
                              System.out.print(time.name()+ ": "+ time + " seconds!\n");

                          }
                      }
                  }
