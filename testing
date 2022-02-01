
#include <string.h>

using namespace std;
//substring()

#define WHITESPACE 5

void setup() {
  // put your setup code here, to run once:
  Serial.begin(9600);
  String message="PK375T4C39 Confirmed. on 25/11/21 at 6:56 PM Ksh5,300.00 received from NDIRANGU MBURU 254723500586.  Account Number throttle repair New Utility balance is Ksh5,300.00";

  //Get index of date from Confirmed. on
  int startOfDate=message.indexOf(". on ")+WHITESPACE;
  int endOfDate=message.indexOf(" at");
  String DateUnparsed;

  //Validate index of Date
 if(endOfDate!=-1){
  DateUnparsed=message.substring(startOfDate,endOfDate); ///String with full date
 }else{
  Serial.println("We are currently unable to process your payment. Date Initialization Failed. Contact Admin");
   exit(-1);
  }


  //Convert string Date to character Array to enable conversion to int
  //remove non alphanumeric characters like commas and fullstops

  int endOfDay=DateUnparsed.indexOf('/');
  int  dayPaid=DateUnparsed.substring(0,endOfDay).toInt();
  bool validDay=false;
 ;
  //date validation

  if(dayPaid>0&&dayPaid<=31){
   validDay=true;
    }else{
      Serial.println("Invalid date!Please Contact Admin");

      }
      Serial.println(dayPaid);

      //GET MONTH PAID
    int lastForwardslash=DateUnparsed.lastIndexOf('/');
    int startOfMonth=DateUnparsed.indexOf('/')+1;
  int monthPaid=DateUnparsed.substring(startOfMonth,lastForwardslash).toInt();
   bool validMonth=false;

   //date validation

  if(monthPaid>0&&monthPaid<=12){
   validMonth=true;
    }else{
      Serial.println("Invalid date!Please Contact Admin");

      }
  Serial.println(monthPaid);


    //GET YEAR PAID

  int yearPaid=DateUnparsed.substring(lastForwardslash+1).toInt();
  Serial.println(yearPaid);


}

void loop() {
  // put your main code here, to run repeatedly:

}
