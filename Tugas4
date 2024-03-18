#include <LiquidCrystal_I2C.h>
LiquidCrystal_I2C lcd(0x27, 16, 2);

#define pirPin 12 //deklarasi pin dari pir yang diberi nama variabel pirPin
int statusPir = LOW; //deklarasi kondisi dari sensor pir apakah high atau low
int gerakanPir; //deklarasi variabel untuk pembacaan pir sensor
int motioncount = 0;

void setup() {
  pinMode(pirPin, INPUT); //set pirPin menjadi pin input
  lcd.init();
  lcd.backlight();
  lcd.setCursor(2,0);
  lcd.print("TUGAS 4:");
  lcd.setCursor(3,1);
  lcd.print("Sensor PIR");
  Serial.begin(9600); //memulai komunikasi serialke serial monitor dengan baud rate 9600
  delay(4000);
}

void loop() {
  gerakanPir = digitalRead(pirPin);
  if(gerakanPir==HIGH){ //mengecek kondisi pir, jika mendeteksi gerakan maka skrip di bawah if akan dieksekusi secara berulang-ulang saat pir tetap mendeteksi gerakan
    delay(2000);
    motioncount++;
    updateLCD();

    Serial.print("Motion Detect = ");
    Serial.println(motioncount);

    lcd.backlight();  
    lcd.setCursor(0, 0);  
    lcd.print("Motion Detect !");
    delay(2000) ;
  }
  else{  
    Serial.println("NO motion detect");
    // lcd.setBacklight(LOW);
    lcd.clear();
  }
  delay(2000);
}

void updateLCD() {
  lcd.setCursor(0, 1);
  lcd.print("Count =  ");
  lcd.print(motioncount); // menampilkan Hitungan
}
