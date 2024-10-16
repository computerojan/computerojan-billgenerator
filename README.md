                                                   BILL GENERATOR
THIS IS A C-PROGRAM FOR A  BILL GENERATOR FOR HOTEL BOOKING WHICH INCLUDES PARAMETERS LIKE AADHAR ID, MOBILE NUMBER, NUMBER OF GUESTS, NUMBER OF DAYS OF STAY AND THE TOTAL BILL WHICH INCLUDES 'GST TAX' AS WELL.

Assignment 3
Group Members :
Niraj Fegade : B24CE1055
Janhavi Patil : B24CE1056
Om Chandurkar : B24CE1057
Atharva Bhonde : B24CE1058
Topic : Hotel Bill Generate
System
Research: A hotel bill generator in C
programming is a software application
designed to automate the billing process
for hotel services. This program typically
includes functionalities to manage
customer data, room bookings, service
charges, and the generation of final bills

Analysis:
Data Structures:

 Hotel Information: This includes details
such as room types, rates, availability,
and additional services offered (e.g.,
meals, laundry).
 Customer Information: This typically
consists of customer names, contact
details, booking dates, and payment
records.
 Billing Information: This encompasses
the calculation of total costs based on
room rates and services availed.

Ideate:
 User Interaction: The program
should allow users to input their
choices through a console interface.
 Dynamic Pricing Calculation: It should
calculate prices based on user
selections (e.g., number of nights
stayed, additional services).

 Error Handling: The program should
handle invalid inputs gracefully,
prompting users to re-enter data when
necessary.
 Bill Generation: Finally, it should
generate a formatted bill that includes
all relevant details like
Customer name, room type, duration
of stay, service charges, and total
amount due.

Build :
#include &lt;stdio.h&gt;
#include &lt;string.h&gt;
// Function to check the length of a number
int intlen(long long number) {
    int len = 0;
    while (number != 0) {
        number /= 10;
        len++;
    }
    return len;
}
// Function to check the length of the Aadhar ID
int aadharlen(long long i) {
    int len = 0;
    while (i != 0) {
        i /= 10;
        len++;
    }
    return len;

}
int main() {
    int choice, d;
    long long number, aadhar;
    char name[100];
    int guests;
    float totalbill,bill;
    float prices[] = {0, 2000, 3500, 1500, 2500, 3000, 5500, 2500, 4000};
    printf(&quot;\n    WELCOME TO PARADISE HOTEL  \n&quot;
           &quot;\nWE PROVIDE THESE SERVICES \n&quot;
           &quot;\n1] SINGLE BED AC ROOMS - 2000RS PER DAY\n&quot;
           &quot;\n2] DOUBLE BED AC ROOMS - 3500RS PER DAY\n&quot;
           &quot;\n3] SINGLE BED NON AC ROOMS - 1500RS PER DAY\n&quot;
           &quot;\n4] DOUBLE BED NON AC ROOMS - 2500RS PER DAY\n&quot;
           &quot;\n5] SINGLE BED AC ROOMS WITH 3 TIME MEAL - 3000RS PER DAY\n&quot;
           &quot;\n6] DOUBLE BED AC ROOMS WITH 3 TIME MEAL - 5500RS PER DAY\n&quot;
           &quot;\n7] SINGLE BED NON AC ROOMS WITH 3 TIME MEAL - 2500RS PER DAY\n&quot;
           &quot;\n8] DOUBLE BED NON AC ROOMS WITH 3 TIME MEAL - 4000RS PER
DAY\n&quot;);
    // Corrected choice validation
    while (1) {
        printf(&quot;\nENTER YOUR CHOICE (1-8):  \n&quot;);
        scanf(&quot;%d&quot;, &amp;choice);
        if (choice &gt;= 1 &amp;&amp; choice &lt;= 8) {
            break;
        } else {
            printf(&quot;PROVIDE A VALID CHOICE\n&quot;);
        }
    }
   
    printf(&quot;\nENTER YOUR NAME:  \n&quot;);
    scanf(&quot;%s&quot;, name);
    // Loop to validate Aadhar ID
    while (1) {
        printf(&quot;\nENTER YOUR AADHAR ID (12 digits):  \n&quot;);
        scanf(&quot;%lld&quot;, &amp;aadhar);
       
        if (aadharlen(aadhar) == 12) {
            break;
        } else {
            printf(&quot;INVALID AADHAR ID. PLEASE ENTER A 12-DIGIT NUMBER\n&quot;);
        }
    }

    // Loop to validate mobile number
    while (1) {
        printf(&quot;\nENTER YOUR MOBILE NO (10 digits): \n&quot;);
        scanf(&quot;%lld&quot;, &amp;number);
       
        if (intlen(number) == 10) {
            break;
        } else {
            printf(&quot;INVALID MOBILE NUMBER. PLEASE ENTER EXACTLY 10 DIGITS\n&quot;);
        }
    }
     // Validate the number of guests
    while (1) {
        printf(&quot;\nENTER THE NUMBER OF GUESTS (1 or more):  \n&quot;);
        scanf(&quot;%d&quot;, &amp;guests);
        if (guests &gt; 0) {
            break;
        } else {
            printf(&quot;INVALID NUMBER OF GUESTS. PLEASE ENTER A POSITIVE
NUMBER\n&quot;);
        }
    }
   
    // Validate the number of days
    while (1) {
        printf(&quot;\nENTER THE NUMBER OF DAYS TO STAY (1 or more):  \n&quot;);
        scanf(&quot;%d&quot;, &amp;d);
        if (d &gt; 0) {
            break;
        } else {
            printf(&quot;INVALID NUMBER OF DAYS. PLEASE ENTER A POSITIVE
NUMBER\n&quot;);
        }
    }
    bill = prices[choice] * d;
    totalbill = bill + ( bill * 0.18);
  // Displaying the bill
   
 printf(&quot;\n✭✭✭✭✭✭✭✭✭✭✭✭✭✭✭ BILL SUMMARY
✭✭✭✭✭✭✭✭✭✭✭✭✭✭✭\n&quot;);
    printf(&quot;                    HOTEL RESERVATION                  \n&quot;);
    printf(&quot;=======================================================\n&quot;);
    printf(&quot;\nNAME             : %s\n&quot;, name);
    printf(&quot;AADHAR ID          : %lld\n&quot;, aadhar);
    printf(&quot;MOBILE NO          : %lld\n&quot;, number);

    printf(&quot;NUMBER OF GUESTS   : %d\n&quot;, guests);
    printf(&quot;NUMBER OF DAYS     : %d\n&quot;, d);
    printf(&quot;BILL               : %.2f RS\n&quot;,bill);
    printf(&quot;BILL WITH GST      : %.2f RS\n&quot;,totalbill);
    printf(&quot;CHECK IN TIME      : 10 AM\n&quot;);
    printf(&quot;CHECK OUT TIME     : 9 AM\n&quot;);
    printf(&quot;=======================================================\n&quot;);
    printf(&quot;              THANK YOU FOR CHOOSING US!             \n&quot;);
   
printf(&quot;✭✭✭✭✭✭✭✭✭✭✭✭✭✭✭✭✭✭✭✭✭✭✭✭✭✭✭✭✭✭✭✭✭✭✭✭✭✭
✭✭\n&quot;);
   
    return 0;
}

Test : It is successfully tested on VS Code
software and run Perfectly on it without any
error or mistake and generate a perfect bill .
Output: example
✭✭✭✭✭✭✭✭✭✭✭✭✭✭✭BILLSUMMARY✭✭✭✭✭✭✭✭✭✭✭✭✭✭✭
                    HOTEL RESERVATION                  
=======================================================
NAME             : ATHARVA_PATIL
AADHAR ID          : 567452338976
MOBILE NO          : 9873452622
NUMBER OF GUESTS   : 2
NUMBER OF DAYS     : 4
BILL               : 22000.00 RS
BILL WITH GST      : 25960.00 RS
CHECK IN TIME      : 10 AM
CHECK OUT TIME     : 9 AM
=======================================================
              THANK YOU FOR CHOOSING US!            
✭✭✭✭✭✭✭✭✭✭✭✭✭✭✭✭✭✭✭✭✭✭✭✭✭✭✭✭✭✭✭✭✭✭✭✭✭

Published On GitHub :
https://github.com/computerojan/computerojan-
billgenerator
