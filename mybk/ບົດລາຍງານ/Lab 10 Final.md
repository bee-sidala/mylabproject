# Lab Project 2 Mid-Term Exam : Counter Number

---

# 0.ການເຮັດວຽກຂອງວົງຈອນ

ເພື່ອໃຊ້ນັບຈຳນວນຕ່າງໆໃນການເຮັດວຽກ ພຽງແຕ່ເຮົາກົດປຸ່ມລົງໄປ ເຄື່ອງນັບຂອງເຮົາບໍ່ແມ່ນ ແບບທົ່ວໄປ ນັບແບບເລກຄີ່ແລະຄູ່ໄດ້!
  ຮັດວຽກໂດຍຮັບ Input ປຸ່ມ 3 ປຸ່ມ (ເລກຄີ່, ເລກຄູ່, Reset) ແລະສະແດງຕົວເລກເທິງ LED 7-segment ໂດຍໃຊ້ ຟັງຊັນ nextOdd() ແລະ nextEven() ເພື່ອຄິດໄລ່ຕົວເລກຖັດໄປ ແລະ4ຟັງຊັນ displayNumber() ເພື່ອສະແດງຜົນເທິງ LED 7-segment
# 1.ການກຽມອຸປະກອນ

| ມີດັ່ງນີ້ :        |
| ------------------ |
| Arduino Uno R3     |
| BreadBoard         |
| 7 Segment X3       |
| 220 kΩ Resistor X7 |
| Switch X3          |
- **Arduino Uno R3**

![[images.png]]

- **BreadBoard**
![[BB.png]]

- **7 Segment**
![[{FAFF3C65-A48E-4DF1-A96C-4F0A0A73C411}.png]]
- **220 kΩ Resistor**
![[{D3756261-BA8E-4417-90B5-EFBD65A21477}.png]]
- **Switch**
![[{8C2FE903-4D65-4FE8-A423-1E410AF5E61A}.png]]
# 2.ສ້າງແຜນວົງຈອນ
![[{42D1D791-EA92-46F8-AFEA-9CF3802B5CFE}.png]]
- **ມຸມມອງແບບ Schematic**
![[{CF4238AF-B87B-41F5-9C20-642CC487DCC6}.png]]

| Component              | Arduino Pin | Details                                                          |
| ---------------------- | ----------- | ---------------------------------------------------------------- |
| 7-Segment Display      | D4          | Segment a                                                        |
|                        | D5          | Segment b                                                        |
|                        | D6          | Segment c                                                        |
|                        | D7          | Segment d                                                        |
|                        | D8          | Segment e                                                        |
|                        | D9          | Segment f                                                        |
|                        | D10         | Segment g                                                        |
|                        | GND         | Common Cathode                                                   |
| Push Button S1 (Odd)   | A1          | Connected with pull-up resistor (not shown in image but implied) |
| Push Button S2 (Even)  | A2          | Connected through 220 Ohm Resistor R5                            |
| Push Button S3 (Reset) | A3          | Connected with pull-up resistor (not shown in image but implied) |
| Resistor R5            | N/A         | 220 Ohm (connected to S2)                                        |
| Power                  | 5V          |                                                                  |
| Ground                 | GND         |                                                                  |
# 3.Coding
```cpp
#define a 10
#define b 12
#define c 2
#define d 4
#define e 6
#define f 8
#define g 7

#define buttonOdd 5 
#define buttonEven 9  
#define buttonReset 13

int currentNumber = 0;
int buttonStateOdd = 0, buttonStateEven = 0, buttonStateReset = 0;

void setup() {
  pinMode(a, OUTPUT);
  pinMode(b, OUTPUT);
  pinMode(c, OUTPUT);
  pinMode(d, OUTPUT);
  pinMode(e, OUTPUT);
  pinMode(f, OUTPUT);
  pinMode(g, OUTPUT);

  pinMode(buttonOdd, INPUT_PULLUP);
  pinMode(buttonEven, INPUT_PULLUP);
  pinMode(buttonReset, INPUT_PULLUP);
}

void loop() {

  buttonStateOdd = digitalRead(buttonOdd);
  buttonStateEven = digitalRead(buttonEven);
  buttonStateReset = digitalRead(buttonReset);

  if (buttonStateOdd == LOW) {
    currentNumber = nextOdd(currentNumber); 
    displayNumber(currentNumber);
    delay(300);
  }


  if (buttonStateEven == LOW) {
    currentNumber = nextEven(currentNumber);
    displayNumber(currentNumber);
    delay(300);
  }

  if (buttonStateReset == LOW) {
    currentNumber = 0; 
    displayNumber(currentNumber);
    delay(300);
  }
}

int nextOdd(int num) {
  num++;
  if (num % 2 == 0) num++;
  if (num > 9) num = 1;  
  return num;
}


int nextEven(int num) {
  num++;
  if (num % 2 != 0) num++; 
  if (num > 8) num = 0;    
  return num;
}

void displayNumber(int num) {
  switch (num) {
    case 0:
      digitalWrite(a, HIGH); digitalWrite(b, HIGH); digitalWrite(c, HIGH);
      digitalWrite(d, HIGH); digitalWrite(e, HIGH); digitalWrite(f, HIGH);
      digitalWrite(g, LOW);
      break;
    case 1:
      digitalWrite(a, LOW); digitalWrite(b, HIGH); digitalWrite(c, HIGH);
      digitalWrite(d, LOW); digitalWrite(e, LOW); digitalWrite(f, LOW);
      digitalWrite(g, LOW);
      break;
    case 2:
      digitalWrite(a, HIGH); digitalWrite(b, HIGH); digitalWrite(c, LOW);
      digitalWrite(d, HIGH); digitalWrite(e, HIGH); digitalWrite(f, LOW);
      digitalWrite(g, HIGH);
      break;
    case 3:
      digitalWrite(a, HIGH); digitalWrite(b, HIGH); digitalWrite(c, HIGH);
      digitalWrite(d, HIGH); digitalWrite(e, LOW); digitalWrite(f, LOW);
      digitalWrite(g, HIGH);
      break;
    case 4:
      digitalWrite(a, LOW); digitalWrite(b, HIGH); digitalWrite(c, HIGH);
      digitalWrite(d, LOW); digitalWrite(e, LOW); digitalWrite(f, HIGH);
      digitalWrite(g, HIGH);
      break;
    case 5:
      digitalWrite(a, HIGH); digitalWrite(b, LOW); digitalWrite(c, HIGH);
      digitalWrite(d, HIGH); digitalWrite(e, LOW); digitalWrite(f, HIGH);
      digitalWrite(g, HIGH);
      break;
    case 6:
      digitalWrite(a, HIGH); digitalWrite(b, LOW); digitalWrite(c, HIGH);
      digitalWrite(d, HIGH); digitalWrite(e, HIGH); digitalWrite(f, HIGH);
      digitalWrite(g, HIGH);
      break;
    case 7:
      digitalWrite(a, HIGH); digitalWrite(b, HIGH); digitalWrite(c, HIGH);
      digitalWrite(d, LOW); digitalWrite(e, LOW); digitalWrite(f, LOW);
      digitalWrite(g, LOW);
      break;
    case 8:
      digitalWrite(a, HIGH); digitalWrite(b, HIGH); digitalWrite(c, HIGH);
      digitalWrite(d, HIGH); digitalWrite(e, HIGH); digitalWrite(f, HIGH);
      digitalWrite(g, HIGH);
      break;
    case 9:
      digitalWrite(a, HIGH); digitalWrite(b, HIGH); digitalWrite(c, HIGH);
      digitalWrite(d, HIGH); digitalWrite(e, LOW); digitalWrite(f, HIGH);
      digitalWrite(g, HIGH);
      break;
  }
}

```

# **4.ການລັນໂປຣແກຣມ ແລະ ການເຮັດວຽກ**
**ທົດລອງສະແກນລິ້ງ QR Code:**

![[ssss_1_.png|214x214]]
# **5.ຜົນລັບຕໍ່ວົງຈອນຕົວຈິງ

![[IMG20250117105940.jpg]]