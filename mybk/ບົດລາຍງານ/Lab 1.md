
# **Blink**

---

# I.ການເຮັດວຽກຂອງວົງຈອນ

- ເມື່ອກົດປຸ່ມ :
ຂໍ້ຄວາມ "Button HIGH" ຈະປາກົດຢູ່ໃນ Serial Monitor.
- ເມື່ອບໍ່ໄດ້ກົດປຸ່ມ :
ຂໍ້ຄວາມ "ປຸ່ມ LOW" ຈະປາກົດຢູ່ໃນ Serial Monitor.
1. ການດໍາເນີນງານຂອງວົງຈອນໂດຍລວມ
ວົງຈອນນີ້ເຮັດວຽກຄ້າຍຄືກັນກັບ "ເປີດ-ປິດສະວິດ" ໂດຍ:
ປຸ່ມກົດຄວບຄຸມສະຖານະຂອງ LED ແລະສະແດງມັນຢູ່ໃນ Serial Monitor.
ເມື່ອກົດປຸ່ມ, ວົງຈອນຈະເປີດໄຟ LED ແລະສະແດງຂໍ້ຄວາມ "ປຸ່ມ HIGH".
ເມື່ອປຸ່ມຖືກປ່ອຍອອກມາ, ວົງຈອນປິດ LED ແລະສະແດງຂໍ້ຄວາມ "Button LOW".

# 1.ການກຽມອຸປະກອນ

| ມີດັ່ງນີ້ :    |
| -------------- |
| Arduino Uno R3 |
| BreadBoard     |
| Red LED        |
| 220 Ω Resistor |
- **Arduino Uno R3**

![[images.png]]

- **BreadBoard**
![[BB.png]]
- **Red LED**
![[{E63445DA-A973-4DD2-AC85-FAE58B8E639A}.png]]
- **220 Ω Resistor**
![[{D3756261-BA8E-4417-90B5-EFBD65A21477}.png]]

# 2.ສ້າງແຜນວົງຈອນ

![[{B0818B6D-5C4F-4B9A-862C-FFD8A53BEA2E}.png]]

- **ມຸມມອງແບບ Schematic**
![[{D2114B18-87A2-447A-845D-90D7BA097E27}.png]]


| Arduino | 220 Ω Resister | LED           |
| ------- | -------------- | ------------- |
| PIN 13  | ຊ້າຍ / ຂວາ     | Anode ( + )   |
| GND     | None           | Cathode ( - ) |

# 3.Coding
```cpp
// C++ code
//
void setup() {
// put your setup code here, to run once:

  pinMode(LED_BUILTIN, OUTPUT); // PIN 13
  
}

void loop() {
// put your main code here, to run repeatedly:
	
  digitalWrite(LED_BUILTIN, HIGH);
  delay(1000); // Wait for 1000 millisecond(s) = 1 second
  
  digitalWrite(LED_BUILTIN, LOW);
  delay(1000); // Wait for 1000 millisecond(s) = 1 second
  
}
```
# **4.ການລັນໂປຣແກຣມ ແລະ ການເຮັດວຽກ**

**ທົດລອງສະແກນລິ້ງ QR Code:**
![[Untitled 1.png|218x218]]
# **5.ຜົນລັບຕໍ່ວົງຈອນຕົວຈິງ**

![[IMG20241105102836.jpg|365x274]]