
# **Switch**

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
| Switch         |
| 10 kΩ Resistor |
- **Arduino Uno R3**

![[images.png]]

- **BreadBoard**
![[BB.png]]
- **Switch**
![[{8C2FE903-4D65-4FE8-A423-1E410AF5E61A}.png]]
- **10 kΩ Resistor**
![[{FF8D9BBF-DFD5-4AC3-B279-1D2F01622593}.png]]

# 2.ສ້າງແຜນວົງຈອນ

![[{BB55DEF0-2684-4B17-B5EE-66EFC2F4E288}.png]]

- **ມຸມມອງແບບ Schematic**
![[image.png|448x407]]

| Arduino    | 10 k Ω Resister | Button  |
| ---------- | --------------- | ------- |
| Pin 2 / 5v | None            | 1a / 2a |
| GND        | ຊ້າຍ / ຂວາ      | None    |
| GND        | ຊ້າຍ / ຂວາ      | 1b      |

# 3.Coding
```cpp
int buttonState = 0;

void setup()
{
  pinMode(2, INPUT);
  pinMode(LED_BUILTIN, OUTPUT);
  Serial.begin(9600);
}

void loop()
{
  // read the state of the pushbutton value
  buttonState = digitalRead(2);
  // check if pushbutton is pressed.  if it is, the
  // buttonState is HIGH
  if (buttonState == HIGH) {
    // turn LED on
    Serial.println("Button HIGH"); 
    digitalWrite(LED_BUILTIN, HIGH);
  } else {
    // turn LED off
    Serial.println("Button LOW"); 
    digitalWrite(LED_BUILTIN, LOW);
  }
  delay(10); // Delay a little bit to improve simulation performance
}
```

# **4.ການລັນໂປຣແກຣມ ແລະ ການເຮັດວຽກ**
**ທົດລອງສະແກນລິ້ງ QR Code:**

![[Untitled 3.png|223x223]]

# **5.ຜົນລັບຕໍ່ວົງຈອນຕົວຈິງ**

![[image-1.png|452x339]]
