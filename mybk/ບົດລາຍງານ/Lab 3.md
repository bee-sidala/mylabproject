
# RGB

---

# I.ການເຮັດວຽກຂອງວົງຈອນ
1. ຕົວຢ່າງຄໍາສັ່ງແລະຜົນໄດ້ຮັບ
ຄໍາສັ່ງເຮັດວຽກ
ເປີດໄຟ LED ທັງໝົດ
ປິດໄຟ LED ທັງໝົດ.
r ເປີດໄຟແດງ
g ເປີດໄຟສີຂຽວ
b ເປີດໄຟສີຟ້າ.
rg ເປີດໄຟສີແດງແລະສີຂຽວ
allColors ສະແດງລໍາດັບຂອງໄຟກະພິບທັງຫມົດ.
2. ການດໍາເນີນງານຂອງວົງຈອນໂດຍລວມ
ຜູ້ໃຊ້ສົ່ງຄໍາສັ່ງຜ່ານ Serial Monitor ເພື່ອຄວບຄຸມໄຟ LED.
Arduino ໄດ້ຮັບຄໍາສັ່ງແລະກວດເບິ່ງວ່າມັນແມ່ນຫຍັງ.
ຄວບຄຸມ pins 11, 10, ແລະ 9 ເພື່ອເປີດ / ປິດ LED ຕາມຄໍາສັ່ງ.
ຖ້າຄໍາສັ່ງບໍ່ຖືກຕ້ອງ ລະບົບຈະສະແດງຜົນກະພິບໂດຍອັດຕະໂນມັດ.
  
# 1.ການກຽມອຸປະກອນ

| ມີດັ່ງນີ້ :     |
| --------------- |
| Arduino Uno R3  |
| BreadBoard      |
| RGB LED         |
| 220 kΩ Resistor |
- **Arduino Uno R3**

![[images.png]]

- **BreadBoard**
![[BB.png]]
- **RGB LED**
![[{84D44AC0-D33D-449B-8363-0CB1C33C9EB3}.png]]
- **220 kΩ Resistor**
![[{D3756261-BA8E-4417-90B5-EFBD65A21477}.png]]

# 2.ສ້າງແຜນວົງຈອນ

![[{7FB9843E-CE95-4913-B759-6CB88BA6C041}.png]]

- **ມຸມມອງແບບ Schematic**

![[{E692C07C-E128-475E-9AD9-6D986D74A670}.png]]

### ຄໍາແນະນໍາ

| Arduino                      | 220 Ω Resister | RGB LED                            |
| ---------------------------- | -------------- | ---------------------------------- |
| GND                          | ຊ້າຍ / ຂວາ     | Cathode ( - )                      |
| Pin 11 / GND / Pin 10 /Pin 9 | ຊ້າຍ / ຂວາ     | Red / Cathode ( - ) / Blue / Green |
| GND                          | None           | Cathode ( - )                      |

# 3.Coding
```cpp
int ledPins[] = {11, 10, 9};
const int NUM_LEDS = sizeof(ledPins) / sizeof(ledPins[0]);

void setup() {
  Serial.begin(9600);
  for(int i = 0; i < NUM_LEDS; i++) {
    pinMode(ledPins[i], OUTPUT);
  }
}

void loop() {
  while (Serial.available() > 0) {
    String input = Serial.readStringUntil('\n'); // Read until newline
    
    // Turn off all LEDs first
    for(int i = 0; i < NUM_LEDS; i++) {
      digitalWrite(ledPins[i], LOW);
    }
    delay(10);
    
    if (input == "on" || input == "rgb" || input == "rbg" || input == "grb" || input == "gbr" || input == "brg" || input == "bgr" ) {
      // turn all LEDs on
      for(int i = 0; i < NUM_LEDS; i++) {
        digitalWrite(ledPins[i], HIGH);
      }
    }
    else if (input == "off") {
      // turn all LEDs off
      for(int i = 0; i < NUM_LEDS; i++) {
        digitalWrite(ledPins[i], LOW);
      }
    }
    else if (input == "r") {
      digitalWrite(ledPins[0], HIGH);
    }
    else if (input == "g") {
      digitalWrite(ledPins[1], HIGH);
    }
    else if (input == "b") {
      digitalWrite(ledPins[2], HIGH);
    }
    else if (input == "rg" || input == "gr") {
      digitalWrite(ledPins[0], HIGH);
      digitalWrite(ledPins[1], HIGH);
    }
    else if (input == "rb" || input == "br") {
      digitalWrite(ledPins[0], HIGH);
      digitalWrite(ledPins[2], HIGH);
    }
    else if (input == "gb" || input == "bg") {
      digitalWrite(ledPins[1], HIGH);
      digitalWrite(ledPins[2], HIGH);
    }
    else {
      allColors();
    }
  }
}

void allColors() {
  //WHITE
  for(int i = 0; i < NUM_LEDS; i++) {
    digitalWrite(ledPins[i], HIGH);
  }
  delay(100);
  for(int i = 0; i < NUM_LEDS; i++) {
    digitalWrite(ledPins[i], LOW);
  }
  delay(100);
  
  //RED, GREEN, BLUE
  for(int i = 0; i < NUM_LEDS; i++) {
    digitalWrite(ledPins[i], HIGH);
    delay(100);
    digitalWrite(ledPins[i], LOW);
    delay(100);
  }
  
  //RED + GREEN index 0 and index 1
  for(int i = 0; i < 2; i++) {
    digitalWrite(ledPins[i], HIGH);
  }
  delay(100);
  for(int i = 0; i < 2; i++) {
    digitalWrite(ledPins[i], LOW);
  }
  delay(100);
  
  //RED BLUE index 0 and index 2
  for(int i = 0; i < 3; i += 2) {
    digitalWrite(ledPins[i], HIGH);
  }
  delay(100);
  for(int i = 0; i < 3; i += 2) {
    digitalWrite(ledPins[i], LOW);
  }
  delay(100);
  
  // GREEN + BLUE index 1 and index 2  
  for(int i = 1; i < 3; i++) {
    digitalWrite(ledPins[i], HIGH);
  }
  delay(100);
  for(int i = 1; i < 3; i++) {
    digitalWrite(ledPins[i], LOW);
  }
  delay(100);
}
```

# **4.ການລັນໂປຣແກຣມ ແລະ ການເຮັດວຽກ**
**ທົດລອງສະແກນລິ້ງ QR Code:**

![[Untitled 4.png|222x222]]

# **5.ຜົນລັບຕໍ່ວົງຈອນຕົວຈິງ

![[IMG_20250128_102025_223 1.jpg]]