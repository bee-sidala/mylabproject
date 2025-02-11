#  Relay

---

# I.ການເຮັດວຽກຂອງວົງຈອນ

Relay ແມ່ນອຸປະກອນທີ່ໃຊ້ໃນການຄວບຄຸມວົງຈອນຄວາມໄຟຟ້າຫຼືອຸປະກອນດ້ວຍສັນຍານຂາເຂົ້າທີ່ມີກຳລັງຕໍ່າ. Relay ມີຫນ້າທີ່ສຳຄັນໃນລະບົບໄຟຟ້າ ແລະໃນອຸປະກອນໄຟຟ້າ
ຈະຕ້ອງມີການຈ່າຍໄຟໃຫ້ໄດ້ຕາມກຳນົດ ເນື່ອງຈາກ Relay ມີການເຊັດຄ່າຢູ່ໃນຕົວຢູ່ໃນຕົວຢູ່ແລ້ວ.
# 1.ການກຽມອຸປະກອນ

| ມີດັ່ງນີ້ :    |
| -------------- |
| Arduino Uno R3 |
| BreadBoard     |
| LED            |
| 1 kΩ Resistor  |
| Relay          |
- **Arduino Uno R3**

![[images.png]]

- **BreadBoard**
![[BB.png]]
- **LED**
![[{AC395198-FBA4-4876-8BEC-6BA5E5692A45}.png]]!
- **1 kΩ Resistor**
![[{D3756261-BA8E-4417-90B5-EFBD65A21477}.png]]
- Relay 
![[{59A881EB-3AAD-4809-A661-9B9F94E0FE65}.png]]
# 2.ສ້າງແຜນວົງຈອນ

![[{3CF5E0CC-D851-4532-81D0-99F43DF21C06}.png|288x478]]
- **ມຸມມອງແບບ Schematic**
![[{92501B2D-5E37-4306-A40F-8897D3C20444}.png]]
### ຄໍາແນະນໍາ

| Arduino | 1 k Ω Resister | LED           | Relay |
| ------- | -------------- | ------------- | ----- |
| GND     | Left / Right   | Cathode ( - ) | T6    |
| GND     | Left / Right   | Cathode ( - ) | T7    |
| Pin 13  | None           | None          | T8    |
| GND     | None           | None          | T5    |
| 5 v     | None           | None          | T12   |

# 3.Coding
```cpp
NO CODING!
```

# **4.ການລັນໂປຣແກຣມ ແລະ ການເຮັດວຽກ**
**ທົດລອງສະແກນລິ້ງ QR Code:**

![[Untitled 8.png|220x220]]
# **5.ຜົນລັບຕໍ່ວົງຈອນຕົວຈິງ

![[{D9BE3753-81C6-4812-9119-2AED6388D7EF}.png]]