# CPP-Program-to-count-the-number-of-days-in-a-given-month-of-a-year

Number of days in a given month of a given year in C++
 
Number of days in any month of a year can vary specifically in February as the cycle of leap year repeats in every 4 years when the year is leap February gives the count to 29 days but the when the year is not leap it gives count to 28 days and so no of days in a year varies from 365 to 366. 
Rather than February every month gives the count of 30 or 31 days in any case whether the year is a leap or not.

Number of days in a given month of a year in C++
Method Discussed :
Method 1: Using if-else ladder.
Method 2 : Using Switch Case.
Method 3 : Using Array
Method 1 :
Check if the given month is February. 
If True Check if the year is a year leap or not.
If year is a leap year Print 29 Days, Else Print 28 Days.
If Condition in Step 3 is False Check the month. 
Print the number of days assigned to specific Month.
Method 1 : Code in C++
Run
//Write a program to count the number of days in a given month of a year in C++
#include <bits/stdc++.h>
using namespace std;

int main()
{
    int month = 12, year=2012;
    
    if((month==2) && ((year%400==0) || ((year%100!=0)&&(year%4==0)))){
        cout<<"Number of days is 29";
    }
    else if(month==2){
        cout<<"Number of days is 28";
    }
    else if(month==1 || month==3 || month==5 || month==7 || month==8 || month==10 || month==12){
        cout<<"Number of days is 31";
    }
    else if(month==4 || month==6 || month==9 || month==11){
        cout<<"Number of days is 30";
    }
    else cout<<"Invalid month";
    
    return 0;
}
Output
Number of days is 31
Method 2 :
In this method instead of using if-else-if ladder we use switch case.

Method 2 : Code in C++
Run
//Write a program to count the number of days in a given month of a year in C++
#include <bits/stdc++.h>
using namespace std;

int main()
{
    int month = 12, year=2012;
    
    switch (month) {
    // Cases for 31 Days
    case 1:
    case 3:
    case 5:
    case 7:
    case 8:
    case 10:
    case 12:
        cout<<"Number of days is 31 Days.";
        break;
  
    // Cases for 30 Days
    case 4:
    case 6:
    case 9:
    case 11:
        cout<<"Number of days is 30 Days.";
        break;
  
    // Case for 28/29 Days
    case 2:
        if((year%400==0) || ((year%100!=0)&&(year%4==0)))
        cout<<"Number of days is 29";
        else cout<<"Number of days is 28";
        break;
  
    default:
        cout<<"Invalid Month.";
        break;
    }
    
    return 0;
}
Output
Number of days is 31
Method 3 :
In this method instead of using if-else-if ladder or switch case, we use array.

Method 3 : Code in C++
Run
//Write a program to count the number of days in a given month of a year in C++
#include<bits/stdc++.h>
using namespace std;

int main()
{
    
    int arr[12] = { 31, 28, 31, 30, 31, 30, 31, 31, 30, 31, 30, 31 };
    int month = 12, year=2012;
    
    //For checking leap year
    if(month==2 && ((year%400==0) || ((year%100!=0)&&(year%4==0))))
        cout<<"Number of days is "<< arr[month-1]+1;
    
    else cout<<"Number of days is"<<arr[month-1];
   
    
    return 0;
}
Output
Number of days is 31

