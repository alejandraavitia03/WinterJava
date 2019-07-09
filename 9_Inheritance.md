        public class TestCuboid 
        {
            public static void main(String[] args) 
            {
              Cuboid myCuboid = new Cuboid();
              System.out.println("Hi! Im an object created by Alejandra."
                      + "I am a cuboid and I inherited traits from a rectangle!");
              System.out.println("My color is: " + myCuboid.getColor());
              System.out.println("My length is: " + myCuboid.getLength());
              System.out.println("My width is: " + myCuboid.getWidth());
              System.out.println("My depth is: " + myCuboid.getDepth());
              System.out.println("I have an Area of: " + myCuboid.getArea());
              System.out.printf("I have a Volume of: %.1f\n" , myCuboid.getVolume());

              System.out.println("\nNow meet my friend the book!\n");

              Cuboid book = new Cuboid(55.6, 27.5, 54.8, "Brown");
              System.out.println("Hi! Im an object created by Alejandra."
                      + "I am a book(shape of a cuboid) and I inherited traits from a rectangle!");
              System.out.println("My color is: " + book.getColor());
              System.out.println("My length is: " + book.getLength());
              System.out.println("My width is: " + book.getWidth());
              System.out.println("My depth is: " + book.getDepth());
              System.out.println("I have an Area of: " + book.getArea());
              System.out.printf("I have a Volume of:%.1f\n" , book.getVolume());
            }  
        }
        =================================================================================
        public class Rectangle //My Super Class
        {
            private double length;
            private double width;
            private String color;
             //Constructors
            public Rectangle()
            {
                this.length = 4.0;
                this.width = 3.0;
                this.color = "Unicorn Tears";
            }
            public Rectangle(double length, double width, String color)
            {
                this.length = length;
                this.width = width;
                this.color = color; 
            }
            //SET/GET
            public void setLength(double length)
            {
                this.length = length;
            }
            public void setWidth(double width)
            {
                this.width = width;
            }
            public void setColor(String color)
            {
                this.color = color;
            }
            public double getLength()
            {
                return this.length;
            }
            public double getWidth()
            {
                return this.width;
            }
            public String getColor()
            {
                return this.color;
            }
            //Lets do area
            public double getArea()
            {
                double area;
                area = length * width;
                return area;
            }
        }
        =========================================================
        public class Cuboid extends Rectangle //My subclass
        {
            private double depth;

            public Cuboid()
            {
                super();
                this.depth = 15.7;
            }
            public Cuboid(double depth) 
            {
              super(); 
              this.depth = depth;
           }
            public Cuboid(double depth, double length,double width, String color)
            {
                super(length,width, color);
                this.depth = depth;
            }
            //SET/GET for subclass
            public double getDepth()
            {
                return this.depth;
            }
            public void setDepth(double depth)
            {
                this.depth = depth;
            }
            //Lets do volume
            public double getVolume()
            {
                double volume;
                volume = getArea() * depth;
                return volume;         
            }
        }

