# Potentiometer

---

# I.ການເຮັດວຽກຂອງວົງຈອນ
Potentiometer ເປັນອຸປະກອນທີ່ໃຊ້ເພື່ອ:

1.ປັບຄ່າຄວາມຕ້ານທານ: ສາມາດໃຊ້ປັບຄ່າຄວາມຕ້ານທານໃນວົງຈອນໄຟຟ້າເພື່ອຄວບຄຸມຄ່າກະແສຫຼືແຮງດັນໃຫ້ໄດ້ຕາມທີ່ຕ້ອງການ

2.ໃຊ້ເປັນສວິດຄວບຄຸມລະດັບ
  
# 1.ການກຽມອຸປະກອນ

| ມີດັ່ງນີ້ :     |
| --------------- |
| Arduino Uno R3  |
| BreadBoard      |
| Potentiometer   |
| 220 kΩ Resistor |
| LED             |
- **Arduino Uno R3**

![[images.png]]

- **BreadBoard**
![[BB.png]]
- **LED**
![[{84D44AC0-D33D-449B-8363-0CB1C33C9EB3}.png]]
- **220 kΩ Resistor**
![[{D3756261-BA8E-4417-90B5-EFBD65A21477}.png]]
- Potentiometer
 ![[{9EDD4E9E-9B69-46D9-A10B-1705FA50B4F2}.png]]
# 2.ສ້າງແຜນວົງຈອນ

![[{ED37801A-BDA4-4C62-B43E-0BB3F39362EB}.png]]

- **ມຸມມອງແບບ Schematic**

![[image-3.png]]
### ຄໍາແນະນໍາ

| Arduino | 1 k Ω Resister | LED           | Potentiometer |
| ------- | -------------- | ------------- | ------------- |
| GND     | ຊ້າຍ / ຂວາ     | Cathode ( - ) | None          |
| Pin 12  | None           | Anode ( + )   | None          |
| GND     | None           | None          | T1            |
| A1      | None           | None          | Wiper         |
| 5 v     | None           | None          | T2            |

# 3.Coding
```cpp
int analogValue = 0;
int ledValue = 0;

void setup() {
  Serial.begin(9600);
  pinMode(11, OUTPUT);
  
}

void loop() {
  analogValue = analogRead(A0);
  Serial.println(analogValue);

  ledValue = map(analogValue, 0, 1023, 0, 255);
  Serial.println(ledValue);
  
  analogWrite(11, ledValue);
  delay(10);
  
}

```

# **4.ການລັນໂປຣແກຣມ ແລະ ການເຮັດວຽກ**
**ທົດລອງສະແກນລິ້ງ QR Code:**

![[Untitled 7.png|214x214]]
# **5.ຜົນລັບຕໍ່ວົງຈອນຕົວຈິງ

![[image-4.png|538x717]]