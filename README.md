# Shopping-bill
This code will generate the shopping bill of a customer with discounts,taxes levied,date and time of the purchase.
import java.util.*;
import java.time.format.DateTimeFormatter;
import java.time.LocalDateTime; 
class Shoppingbill{
public static void main(String[] args){
double total=0,Total;
String [] a=new String[100];
int [] b=new int[100];
int [] c=new int[100];
int [] d=new int[100];
double [] e=new double[100];
Scanner sc=new Scanner(System.in);
int n=sc.nextInt();
for(int i=0;i<n;i++)
{
  sc.nextLine();
    a[i]=sc.nextLine();//products
    b[i]=sc.nextInt(); //cost
    c[i]=sc.nextInt(); //quantity
    d[i]=sc.nextInt();//discounts for each product
    e[i]=b[i]*c[i]-((d[i]*b[i]*c[i])/100);//each product total after discount
}
System.out.print("Tirumala shop");//shopname
System.out.println("\njonnalagadda");//shop place
DateTimeFormatter dtf = DateTimeFormatter.ofPattern("yyyy/MM/dd HH:mm:ss");
   LocalDateTime now = LocalDateTime.now();
   System.out.println(dtf.format(now));
System.out.println("PRODUCT MRP QUANTITY DISCOUNT   TOTAL");
for(int i=0;i<n;i++)
{
  System.out.print(a[i]+"\t");
  System.out.print(b[i]+"\t");
  System.out.print(c[i]+"\t");
  System.out.print(d[i]+"\t");
  System.out.print(e[i]+"\t");
  System.out.println();
}
for(int i=0;i<n;i++)
{
  total=total+e[i];
}
System.out.println("enter the gst");
double gst=sc.nextDouble();
Total=total+((gst*total)/100);
System.out.println("The total bill to be paid is");
System.out.println(Total);
System.out.println("THANK YOU VISIT AGAIN");
}
}
