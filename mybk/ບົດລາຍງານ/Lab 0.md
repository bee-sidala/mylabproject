# **Getting to Experement Blink**

---

# I.
ຖ້າເບິ່ງທີ່ບອດ, ຈະສັງເກດເຫັນວ່າບໍ່ງ່າຍທີ່ຈະສຽບຈໍພາບສະແດງຜົນ ເຊິ່ງເຮັດ ໃຫ້ການຂຽນ Hello World ເປັນໂປຣແກຣມທໍາອິດທີ່ຍາກ, ຖ້າເວົ້າເຖິງການຂຽນເປັນໂປຣແກຣມທໍາອິດທີ່ເຮົາສາມາດຂຽນໄດ້ຂ້ອນຂ້າງງ່າຍ ແລະ ເປັນການທົດສອບການເຮັດວຽກຂອງມັນ.

• ສິ່ງທີ່ພວກເຮົາຕ້ອງການເຮັດແມ່ນ blink led.

# **ພິສູດສິ່ງທີ່ເຮັດໄດ້**

          1.Compile code ລວມໂຄດ

          2.Run on platform ການເຮັດວຽກຂອງຖານ

          3.Control pins ການຄວບຄຸມ

# **1.ການກຽມອຸປະກອນ

**ມີດັ່ງນີ້ :**

![[Untitled 2.png|220x220]]

| ລະຫັດ | ຈຳນວນ    | ຊື່ອຸປະກອນ     |
| ----- | -------- | -------------- |
| Name  | Quantity | Component      |
| U1    | 1        | Arduino Uno R3 |
| B1    | 1        | BreadBoard     |
| R1    | 1        | 220Ω Resistor  |
| D1    | 1        | LED            |

# **2.ສ້າງແຜນວົງຈອນ**
![[Experiment_Blink.png]]

**ມຸມມອງແບບ Schematic**
![[Screenshot_2024-05-02_at_15.32.15.png]]

# **3.Coding**

`blink.ino`
```cpp
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
![[Untitled 2.png|220x220]]
# **5.ຜົນລັບຕໍ່ວົງຈອນຕົວຈິງ**

![[image-2.png]]