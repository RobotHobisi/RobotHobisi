# RobotHobisi
Arduino üzerinden ds18b20 devresini kurunuz.
Yada istediğiniz herhangi bir veri oluşturunuz. 
Torak , ısı , ışık , nem yada herhangi farklı bir sensörü de kullanabilirsiniz. 
Ardından kodu Arduino y a yükleyin.
Programı çalıştırın ve doğru bağlantı portunu  bağlantı hızını seçin. 
Start tuşuna bastığınız anda verileri kaydetmeye başlayacaktır. 
Verileri txt Dosyasına kaydetmek için bilgisayarın C sürücüsünde sql isminde bir dosya oluşturun.
Örnek Arduino Kodları aşağıdadır. 
Kodu Arduino  ya yükleyin. 
DallasTemperature kütüphanesi yüklü değilse kütüphaneyi indirip kurmanız gerekiyor.
Kütüphaneyi indirmek için : https://github.com/milesburton/Arduino-Temperature-Control-Library
linkine tıklayabiliriniz.
 #include <OneWire.h> 
#include <DallasTemperature.h>

#define ONE_WIRE_BUS 2 

OneWire oneWire(ONE_WIRE_BUS); 

DallasTemperature sensor(&oneWire);

void setup(void) 
{ 
 Serial.begin(9600); 
 sensor.begin(); 
} 
void loop(void) 
{ 
 sensor.requestTemperatures(); 
 Serial.println(sensor.getTempCByIndex(0));
  delay(100); 
} 
