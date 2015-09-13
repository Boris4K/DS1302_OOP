# DS1302_OOP
DS1302 library for arduino
example:

int CLK 5

int DATA 6

int RST 7

char buffer[80];
static int_time prev_time, curr_time;
ds1302_struct rtc(CLK, DATA, RST);

//to get the new time reading you must update
rtc._DS1302_update();
//this copies the result to a class
rtc._DS1302_get_time_and_date(curr_time);

rtc._DS1302_get_time(buffer);
printf("%s",buffer); // print the time
rtc._DS1302_get_date(buffer);
printf("%s",buffer); // print the date

//set the date
curr_time.Seconds = 33;
curr_time.Minutes = 12;
curr_time.Hours = 6;
curr_time.Date = 22;
curr_time.Month = 09;
curr_time.Year = 15;
rtc._DS1302_set_date_time(curr_time);
