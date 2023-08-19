# Java-program-Counting-number-of-days-in-a-given-month-of-a-year-

Number of days in a given month of a given year in  Java
 
In this page we will discuss the program to find the number of days in a given month of a given year in java . Number of days in any month of a year can vary specifically in February as the cycle of leap year repeats in every 4 years when the year is leap February gives the count to 29 days but the when the year is not leap it gives count to 28 days and so no of days in a year varies from 365 to 366.

Number of days in a given month of a year in java
Method Discussed :
Method 1: Using if-else ladder.
Method 2 : Using Switch Case.
Method 3 : Using Array
Method 1 :
Check if the given month is February. 
If True Check if the year is a year leap or not.
If year is a leap year Print 29 Days, Else Print 28 Days.
Now, check if month is 1, 3, 5, 7, 8, 10, 12, then print 31 days.
Check if month is 4, 6, 9, 11 then print 30 days.
Otherwise, print Invalid Month.
Method 1 : Code in Java
Run
import java.io.*;
import java.util.*;

class Main{

    public static void main(String args[]){

        int month, year;
        month = 12;
        year = 2012;
        if((month==2) && ((year%4==0) || ((year%100==0)&&(year%400==0))))
            System.out.println("Number of days is 29");

        else if(month==2)
            System.out.println("Number of days is 28");

        else if(month==1 || month==3 || month==5 || month==7 || month==8 || month==10 || month==12)
            System.out.println("Number of days is 31");

        else
            System.out.println("Number of days is 30");


    }

}
Output
Number of days is 31
Method 2 :
In this method instead of using if-else-if ladder we use switch case.

Method 2 : Code in Java
Run
import java.io.*;
import java.util.*;

class Main{

    public static void main(String args[]){
        
        int month=12, year = 2012;
        switch (month) {
            // Cases for 31 Days
            case 1:
            case 3:
            case 5:
            case 7:
            case 8:
            case 10:
            case 12:
            System.out.println("Number of days is 31");
            break;
  
            // Cases for 30 Days
            case 4:
            case 6:
            case 9:
            case 11:
            System.out.println("Number of days is 30");
            break;
  
            // Case for 28/29 Days
            case 2:
                if((year%400==0) || ((year%100!=0)&&(year%4==0)))
                    System.out.println("Number of days is 29");
                else System.out.println("Number of days is 28");
            break;
  
            default:
            System.out.println("Invalid Month.");
            break;
        }
    
    }
}
Output
Number of days is 31
Related Pages
Lowest Common Multiple (LCM)

Greatest Common Divisor

Binary to Decimal to conversion

Octal to Decimal conversion

Hexadecimal to Decimal conversion

Method 3 :
In this method instead of using if-else-if ladder or switch case, we use array.

Method 3 : Code in Java
Run
import java.io.*;
import java.util.*;

class Main{

    public static void main(String args[]){
        
        int arr[] = { 31, 28, 31, 30, 31, 30, 31, 31, 30, 31, 30, 31 };
        int month = 12, year=2012;
    
        //For checking leap year
        if(month==2 && ((year%400==0) || ((year%100!=0)&&(year%4==0))))
            System.out.println("Number of days is "+ arr[month-1]+1);
    
        else System.out.println("Number of days is "+arr[month-1]);
            
    }
}
Output
Number of days is 31
