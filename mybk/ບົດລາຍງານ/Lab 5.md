# Project 1 : Traffic Light

---

# 0.ການເຮັດວຽກຂອງວົງຈອນ

ສາທິດວິທີການໃຊ້ໄຟສັນຍານໃນລະບົບວົງຈອນ ນັ້ນເອງ
ກົດປຸ່ມ Switch ເພື່ອປ່ຽນໄຟສັນຍານຈາລາຈອນ
ເຊັ່ນ : ແດງ ເຫຼືອງ ຂຽວ
  
# 1.ການກຽມອຸປະກອນ

| ມີດັ່ງນີ້ :        |
| ------------------ |
| Arduino Uno R3     |
| BreadBoard         |
| LED X3             |
| 220 kΩ Resistor X3 |
- **Arduino Uno R3**

![[images.png]]

- **BreadBoard**
![[BB.png]]
- **LED**
![[{E63445DA-A973-4DD2-AC85-FAE58B8E639A}.png]]
- **220 kΩ Resistor**
![[{D3756261-BA8E-4417-90B5-EFBD65A21477}.png]]

# 2.ສ້າງແຜນວົງຈອນ

![[{859D5B92-DC51-4D5E-8E8C-30C91282B48D}.png]]

- **ມຸມມອງແບບ Schematic**
![[{68D3FBBE-B475-4E58-B22E-E734B609401B}.png]]

| Component      | Arduino Pin | Details                                                 |
| -------------- | ----------- | ------------------------------------------------------- |
| LED (RED)      | D3          | Connected with 220 Ohm Resistor R1                      |
| Resistor R1    | N/A         | 220 Ohm (connected to LED RED and D3)                   |
| Push Button S1 | D1          | Connected with pull-up resistor (not shown but implied) |
| LED (YELLOW)   | D2          | Connected with 220 Ohm Resistor R2                      |
| Resistor R2    | N/A         | 220 Ohm (connected to LED YELLOW and D2)                |
| LED (GREEN)    | D1          | Connected with 220 Ohm Resistor R3                      |
| Resistor R3    | N/A         | 220 Ohm (connected to LED GREEN and D1)                 |
| Ground         | GND         | Connected to all grounds                                |
# 3.Coding
```cpp
// C++ code

void setup()
{
  pinMode(0, INPUT);
  pinMode(4, OUTPUT);
  pinMode(3, OUTPUT);
  pinMode(2, OUTPUT);
}

void loop()
{
  if (digitalRead(0) == 0) {
    digitalWrite(4, LOW);
    digitalWrite(3, LOW);
    digitalWrite(2, HIGH);
    delay(2000); // Wait for 2000 millisecond(s)
    digitalWrite(4, LOW);
    digitalWrite(3, HIGH);
    digitalWrite(2, LOW);
    delay(2000); // Wait for 2000 millisecond(s)
  }
  digitalWrite(4, HIGH);
  digitalWrite(3, LOW);
  digitalWrite(2, LOW);
}
```

# **4.ການລັນໂປຣແກຣມ ແລະ ການເຮັດວຽກ**
**ທົດລອງສະແກນລິ້ງ QR Code:**

![[Untitled 6.png|244x244]]

# **5.ຜົນລັບຕໍ່ວົງຈອນຕົວຈິງ

**ບໍ່ໄດ້ຕໍ່ໄວ້ T ^ T ຂໍເປັນພາບຈຳລອງແທນ**

![[{42CF8B6B-157A-489C-8030-67B28C794E20}.png|544x413]]