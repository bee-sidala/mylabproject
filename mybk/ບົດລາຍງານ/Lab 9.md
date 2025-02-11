
# **Seven Segment**

---

# I.ການເຮັດວຽກຂອງວົງຈອນ

7 Segment ເປັນຈໍສະແດງຜົນສະແດງຕົວເລກ - ຕົວອັກສອນ (ບາງອັນທີ່ເປັນໄປໄດ້) ທີ່ມີຫນ້າຈໍທີ່ເຮັດຈາກການຈັດລຽງຫລອດໄຟ LED ໃນທິດທາງຍາວເມື່ອຫລອດໄຟ LED ແຕ່ລະຄົນຖືກສະຫວ່າງໃນເວລາດຽວກັນ. ມັນຈະສາມາດສະແດງອອກເປັນຕົວເລກສີ່ຫຼ່ຽມ.

7 Segment : ໃຊ້ເປັນຈໍສະແດງຜົນ ເຈັດສ່ວນໃນຮູບແບບຂອງອຸປະກອນສະແດງຜົນອີ ເລັກໂຕຣນິກສາຫຼັບ
# 1.ການກຽມອຸປະກອນ

| ມີດັ່ງນີ້ :    |
| -------------- |
| Arduino Uno R3 |
| BreadBoard     |
| 7 Segment      |
| 1 kΩ Resistor  |
- **Arduino Uno R3**

![[images.png]]

- **BreadBoard**
![[BB.png]]
- **7 Segment**
![[{FAFF3C65-A48E-4DF1-A96C-4F0A0A73C411}.png]]
- **1 kΩ Resistor**
![[{D3756261-BA8E-4417-90B5-EFBD65A21477}.png]]

# 2.ສ້າງແຜນວົງຈອນ
![[image-5.png|536x542]]
- **ມຸມມອງແບບ Schematic**
![[image-6.png]]
### ຄໍາແນະນໍາ

| Arduino | 1 k Ω Resister | 7 - segments |
| ------- | -------------- | ------------ |
| Pin 9   | None           | A            |
| Pin 8   | None           | B            |
| Pin 7   | None           | C            |
| Pin 6   | None           | D            |
| Pin 5   | None           | E            |
| Pin 4   | None           | F            |
| Pin 3   | None           | G            |
| Pin 2   | None           | DP           |
| GND     | ຊ້າຍ / ຂວາ     | Common       |

# 3.Coding
```cpp
int segPins[] = {9, 8, 7, 6, 5, 4, 3, 2 };   // { a b c d e f g . }

byte segCode[11][8] = {
//  a  b  c  d  e  f  g  .
  { 1, 1, 1, 1, 1, 1, 0, 0},  // 0
  { 0, 1, 1, 0, 0, 0, 0, 0},  // 1
  { 1, 1, 0, 1, 1, 0, 1, 0},  // 2
  { 1, 1, 1, 1, 0, 0, 1, 0},  // 3
  { 0, 1, 1, 0, 0, 1, 1, 0},  // 4
  { 1, 0, 1, 1, 0, 1, 1, 0},  // 5
  { 1, 0, 1, 1, 1, 1, 1, 0},  // 6
  { 1, 1, 1, 0, 0, 0, 0, 0},  // 7
  { 1, 1, 1, 1, 1, 1, 1, 0},  // 8
  { 1, 1, 1, 1, 0, 1, 1, 0},  // 9
  { 0, 0, 0, 0, 0, 0, 0, 1}   // .
};

void displayDigit(int digit)
{
  for (int i = 0; i < 8; i++)
  {
    digitalWrite(segPins[i], segCode[digit][i]);
  }
}

void setup()
{
  for (int i = 0; i < 8; i++)
  {
    pinMode(segPins[i], OUTPUT);
  }
}

void loop()
{
  // Count from 0 to 9
  for (int n = 0; n < 10; n++)   
  {
    displayDigit(n);
    delay(1000);
  }

  // Count back from 9 to 0
  for (int n = 9; n >= 0; n--)   
  {
    displayDigit(n);
    delay(500);
  }
}

```

# **4.ການລັນໂປຣແກຣມ ແລະ ການເຮັດວຽກ**
**ທົດລອງສະແກນລິ້ງ QR Code:**

![[ssss.png|174x174]]
# **5.ຜົນລັບຕໍ່ວົງຈອນຕົວຈິງ
![[image-7.png]]