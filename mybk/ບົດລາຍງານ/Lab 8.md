
# Servo

---

# I.ການເຮັດວຽກຂອງວົງຈອນ
Servo ແມ່ນອຸປະກອນທີ່ຜູ້ໃຊ້ສາມາດໃຊ້ເພື່ອຄວບຄຸມການເຮັດວຽກຂອງເຄື່ອງຈັກ. ຫຼືລະບົບການເຮັດວຽກຂອງລະບົບການເຮັດວຽກນັ້ນ ໃຫ້​ເປັນ​ດັ່ງ​ທີ່​ພວກ​ເຮົາ​ຕ້ອງ​ການ​ ໃຊ້ກັບລະບົບການເຮັດວຽກ
- ຄຸມທິດຂອງ  Servo motor ແລະ ບອກຄ່າເທິງ Serial Monitor.
  - Micro Servo motor : ເປັນມໍເຕີກະແສໄຟ ກົງທີ່ໃຊ້ໃນການຄວບຄຸມມູມ ຫຼື ຕາແໜ່ງເສັ້ນຊື່ທີ່ ມີຄວາມລະອຽດສູງ.
# 1.ການກຽມອຸປະກອນ

| ມີດັ່ງນີ້ :    |
| -------------- |
| Arduino Uno R3 |
| BreadBoard     |
| Potentiometer  |
| Servo Motor    |
- **Arduino Uno R3**

![[images.png]]

- **BreadBoard**
![[BB.png]]
- Servo Motor
![[{71065B7D-C8B8-45C7-B0FE-A05DF170962E}.png]]

- Potentiometer
 ![[{9EDD4E9E-9B69-46D9-A10B-1705FA50B4F2}.png]]
 
# 2.ສ້າງແຜນວົງຈອນ

![[{9B0D61F4-A0CE-403C-97C4-E105203EDE15}.png]]
- **ມຸມມອງແບບ Schematic**
![[{B393262A-572F-4BBC-B57B-D024CBE4C3C8}.png]]


### ຄໍາແນະນໍາ

| Arduino | 1 k Ω Resister | Servo  |
| ------- | -------------- | ------ |
| GND     | None           | Ground |
| 5v      | None           | Power  |
| Pin 9   | None           | Signal |

| Arduino | 1 k Ω Resister | Servo  | Potentiometer |
| ------- | -------------- | ------ | ------------- |
| GND     | None           | Ground | None          |
| 5v      | None           | Power  | None          |
| Pin 9   | None           | Signal | None          |
| GND     | None           | None   | Wiper         |
| A0      | None           | None   | T2            |
# 3.Coding
```cpp
#include <Servo.h>

Servo myservo;  // create servo object to control a servo

void setup() {
  Serial.begin(9600);
  myservo.attach(9);  // attaches the servo on pin 9 to the servo object
 
}

void loop() {
  for (int i = 0; i <= 180; i++){
    
    myservo.write(i);
   
    Serial.println(i);
    delay(15);
  }
  delay(500);
  for (int i = 180; i >= 0; i--){
    
    myservo.write(i);
    
    Serial.println(i);
    delay(15);
  }
  delay(500);
}

```

```cpp
#include <Servo.h>

Servo myservo;  // create servo object to control a servo

int potpin = A0;  // analog pin used to connect the potentiometer
int val;    // variable to read the value from the analog pin

void setup() {
  Serial.begin(9600);
  myservo.attach(9);  // attaches the servo on pin 9 to the servo object
 
}

void loop() {
  val = analogRead(potpin);           // reads the value of the potentiometer (value between 0 and 1023)
  Serial.print("pot = ");
  Serial.print(val);
  Serial.print(", servo = ");
  val = map(val, 0, 1023, 0, 180);     // scale it to use it with the servo (value between 0 and 180)
  
  Serial.println(val);
  myservo.write(val);                  // sets the servo position according to the scaled value
  delay(15);                           // waits for the servo to get there
}
```

# **4.ການລັນໂປຣແກຣມ ແລະ ການເຮັດວຽກ**
**ທົດລອງສະແກນລິ້ງ QR Code:**

![[Untitled 9.png|228x228]]
# **5.ຜົນລັບຕໍ່ວົງຈອນຕົວຈິງ

![[IMG20250107100225-1.jpg]]