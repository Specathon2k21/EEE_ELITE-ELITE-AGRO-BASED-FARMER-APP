# EEE-ELITE-AGRO-BASED-FARMER-APP
# eee-elite agro based farmers application

 
bool createfile()
{
 // create the .csv file in the sd card
 serial.println("creating file");
  
 serial.println("  ok - creating and opening file");
 file datafile = sd.open("datalog.csv", file_write);
  
 if(datafile)
 {
   serial.println("  ok - file created");
   serial.println("  ok - appending legend to file");
   serial.print("  ok - appending "); serial.println(legend);
   datafile.println(legend);
   datafile.close();
   serial.println("  success - data appended");
 }
 else
 {
   serial.println("  error - file not detected");
   serial.println("  ok - trying again in 5 seconds");
   serial.println("________________________________________");
   serial.println("");
   datafile.close();
   delay(5000);
   return false;
 }
 serial.println("________________________________________");
 serial.println("");
 return true;
}
  
void checkfile()
{
 serial.println("checking .csv");
 serial.println("________________________________________");
 serial.println("setting up file");
  
 serial.println("  ok - checking for file presence");
 if(sd.exists("datalog.csv")) // check if the .csv file already exists
 {
   // append to the existing file is it exists
   serial.println("  ok - file exists");
   serial.println("  ok - will append to existing file");
   serial.println("________________________________________");
   serial.println("");
 }
 else
 {
   // create a new file to append to
   serial.println("  ok - file not present");
   serial.println("  ok - creating file");
   serial.println("");
   while(!createfile()) {};
 }
}
bool createfile()
{
 // create the .csv file in the sd card
 serial.println("creating file");
  
 serial.println("  ok - creating and opening file");
 file datafile = sd.open("datalog.csv", file_write);
  
 if(datafile)
 {
   serial.println("  ok - file created");
   serial.println("  ok - appending legend to file");
   serial.print("  ok - appending "); serial.println(legend);
   datafile.println(legend);
   datafile.close();
   serial.println("  success - data appended");
 }
 else
 {
   serial.println("  error - file not detected");
   serial.println("  ok - trying again in 5 seconds");
   serial.println("________________________________________");
   serial.println("");
   datafile.close();
   delay(5000);
   return false;
 }
 serial.println("________________________________________");
 serial.println("");
 return true;
}
  
void checkfile()
{
 serial.println("checking .csv");
 serial.println("________________________________________");
 serial.println("setting up file");
  
 serial.println("  ok - checking for file presence");
 if(sd.exists("datalog.csv")) // check if the .csv file already exists
 {
   // append to the existing file is it exists
   serial.println("  ok - file exists");
   serial.println("  ok - will append to existing file");
   serial.println("________________________________________");
   serial.println("");
 }
 else
 {
   // create a new file to append to
   serial.println("  ok - file not present");
   serial.println("  ok - creating file");
   serial.println("");
   while(!createfile()) {};
 }
}
 bool createfile()
{
 // create the .csv file in the sd card
 serial.println("creating file");
  
 serial.println("  ok - creating and opening file");
 file datafile = sd.open("datalog.csv", file_write);
  
 if(datafile)
 {
   serial.println("  ok - file created");
   serial.println("  ok - appending legend to file");
   serial.print("  ok - appending "); serial.println(legend);
   datafile.println(legend);
   datafile.close();
   serial.println("  success - data appended");
 }
 else
 {
   serial.println("  error - file not detected");
   serial.println("  ok - trying again in 5 seconds");
   serial.println("________________________________________");
   serial.println("");
   datafile.close();
   delay(5000);
   return false;
 }
 serial.println("________________________________________");
 serial.println("");
 return true;
}
  
void checkfile()
{
 serial.println("checking .csv");
 serial.println("________________________________________");
 serial.println("setting up file");
  
 serial.println("  ok - checking for file presence");
 if(sd.exists("datalog.csv")) // check if the .csv file already exists
 {
   // append to the existing file is it exists
   serial.println("  ok - file exists");
   serial.println("  ok - will append to existing file");
   serial.println("________________________________________");
   serial.println("");
 }
 else
 {
   // create a new file to append to
   serial.println("  ok - file not present");
   serial.println("  ok - creating file");
   serial.println("");
   while(!createfile()) {};
 }
}
the checkfile() function checks if the.csv file that the device is supposed to append to exists. if the file exists, the function ends, otherwise it calls on createfile() which creates a new.csv file to append to.

collectdata

void collectdata()
{
 serial.println("gathering data");
 serial.println("________________________________________");
  
 serial.println("getting data from sensors");
 serial.println("  ok - contacting all sensors");
  
 // collecting data from all sensors
 soilsens.requesttemperatures();
 soiltemp = soilsens.gettempcbyindex(0);
 soilhumidity = analogread(a1);
 soilhumidity = map(soilhumidity, 1023, 0, 0, 100);
  
 atmotemp = gy21.readtemperature();
 atmohumidity = gy21.readhumidity();
 visiblelight = uv.readvisible();
 void collectdata()
{
 serial.println("gathering data");
 serial.println("________________________________________");
  
 serial.println("getting data from sensors");
 serial.println("  ok - contacting all sensors");
  
 // collecting data from all sensors
 soilsens.requesttemperatures();
 soiltemp = soilsens.gettempcbyindex(0);
 soilhumidity = analogread(a1);
 soilhumidity = map(soilhumidity, 1023, 0, 0, 100);
  
 atmotemp = gy21.readtemperature();
 atmohumidity = gy21.readhumidity();
 visiblelight = uv.readvisible();
 bool burndata(string data)
{
 serial.println("burning data");
 serial.println("________________________________________");
 serial.println("burning data to sd card");
 serial.println("  ok - opening file");
 file datafile = sd.open("datalog.csv", file_write);
 if(datafile)
 {
   serial.println("  ok - file is present");
   serial.print("  ok - appending "); serial.println(data);
   serial.println("  ok - burning data");
   datafile.println(data); // burn the data to the sd card
   datafile.close();
   serial.println("  success - data appended");
   serial.println("________________________________________");
   serial.println("");
 }
 else
 {
   serial.println("  error - file not present");
   serial.println("  ok - trying again in 5 second");
   serial.println("________________________________________");
   serial.println("");
   delay(5000);
 }
 serial.println("");
}
serial.println("  ok - getting responce");
 serial.println("");
 // read back from server
 while(1)
 {
   if(client.available()) 
   {
     char c = client.read();
     serial.print(c);
   }
   if(!client.connected()) 
   {
     break;
   }
 }
 serial.println("  success - data is parsed");
 serial.println("________________________________________");
 serial.println("");
}
