# **Buzzer**

---
# I.ການເຮັດວຽກຂອງວົງຈອນ

Buzzer ແມ່ນອຸປະກອນທີ່ໃຊ້ເພື່ອຜະລິດສຽງ, ໂດຍສ່ວນໃຫຍ່ໃຊ້ໃນລະບົບເຕືອນ, ລະບົບຄວບຄຸມ, ຫຼືໃນອຸປະກອນທີ່ຕ້ອງການສຽງເພື່ອແຈ້ງເຕືອນ

- ເມື່ອກົດປຸ່ມ Buzzer ຈະເລີ່ມຫຼິ້ນເພງຈົນກວ່າເພງຈະຈົບ, ເມື່ອເພງຈົບ Buzzer ຈະຢຸດເຮັດວຽກ.
# 1.ການກຽມອຸປະກອນ

| ມີດັ່ງນີ້ :    |
| -------------- |
| Arduino Uno R3 |
| BreadBoard     |
| Switch         |
| 1 kΩ Resistor  |
| Buzzer         |
- **Arduino Uno R3**

![[images.png]]

- **BreadBoard**
![[BB.png]]
- **Switch**
![[{8C2FE903-4D65-4FE8-A423-1E410AF5E61A}.png]]
- **1 kΩ Resistor**
![[{FF8D9BBF-DFD5-4AC3-B279-1D2F01622593}.png]]
- Buzzer
![[{C96BA705-EE99-4A4D-8F88-B17F6CDDA691}-1.png]]
# 2.ສ້າງແຜນວົງຈອນ

![[{E64B8B16-7933-4033-9DC3-701EF5A95928}.png]]

- **ມຸມມອງແບບ Schematic**

![[{B21775F3-D14F-44D1-8D70-FED59B2852DB}.png]]

| Arduino | 1 k Ω Resister | Buzzer   | Button |
| ------- | -------------- | -------- | ------ |
| GND     | ຊ້າຍ / ຂວາ     | None     | 2a     |
| GND     | ຊ້າຍ / ຂວາ     | Negative | None   |
| Pin 12  | None           | None     | 2b     |
| Pin 8   | None           | Positive | None   |
| 5 v     | None           | None     | 1a     |
# 3.Coding
```cpp
// Define the notes and their frequencies
#define NOTE_B0  31
#define NOTE_C1  33
#define NOTE_CS1 35
#define NOTE_D1  37
#define NOTE_DS1 39
#define NOTE_E1  41
#define NOTE_F1  44
#define NOTE_FS1 46
#define NOTE_G1  49
#define NOTE_GS1 52
#define NOTE_A1  55
#define NOTE_AS1 58
#define NOTE_B1  62
#define NOTE_C2  65
#define NOTE_CS2 69
#define NOTE_D2  73
#define NOTE_DS2 78
#define NOTE_E2  82
#define NOTE_F2  87
#define NOTE_FS2 93
#define NOTE_G2  98
#define NOTE_GS2 104
#define NOTE_A2  110
#define NOTE_AS2 117
#define NOTE_B2  123
#define NOTE_C3  131
#define NOTE_CS3 139
#define NOTE_D3  147
#define NOTE_DS3 156
#define NOTE_E3  165
#define NOTE_F3  175
#define NOTE_FS3 185
#define NOTE_G3  196
#define NOTE_GS3 208
#define NOTE_A3  220
#define NOTE_AS3 233
#define NOTE_B3  247
#define NOTE_C4  262
#define NOTE_CS4 277
#define NOTE_D4  294
#define NOTE_DS4 311
#define NOTE_E4  330
#define NOTE_F4  349
#define NOTE_FS4 370
#define NOTE_G4  392
#define NOTE_GS4 415
#define NOTE_A4  440
#define NOTE_AS4 466
#define NOTE_B4  494
#define NOTE_C5  523
#define NOTE_CS5 554
#define NOTE_D5  587
#define NOTE_DS5 622
#define NOTE_E5  659
#define NOTE_F5  698
#define NOTE_FS5 740
#define NOTE_G5  784
#define NOTE_GS5 831
#define NOTE_A5  880
#define NOTE_AS5 932
#define NOTE_B5  988
#define NOTE_C6  1047
#define NOTE_CS6 1109
#define NOTE_D6  1175
#define NOTE_DS6 1245
#define NOTE_E6  1319
#define NOTE_F6  1397
#define NOTE_FS6 1480
#define NOTE_G6  1568
#define NOTE_GS6 1661
#define NOTE_A6  1760
#define NOTE_AS6 1865
#define NOTE_B6  1976
#define NOTE_C7  2093
#define NOTE_CS7 2217
#define NOTE_D7  2349
#define NOTE_DS7 2489
#define NOTE_E7  2637
#define NOTE_F7  2794
#define NOTE_FS7 2960
#define NOTE_G7  3136
#define NOTE_GS7 3322
#define NOTE_A7  3520
#define NOTE_AS7 3729
#define NOTE_B7  3951
#define NOTE_C8  4186
#define NOTE_CS8 4435
#define NOTE_D8  4699
#define NOTE_DS8 4978

// Define the pin for the buzzer
const int buzzer = 8;

// Melody for "Happy Birthday"
int melody[] = {
  NOTE_G4, NOTE_G4, NOTE_A4, NOTE_G4, NOTE_C5, NOTE_B4,
  NOTE_G4, NOTE_G4, NOTE_A4, NOTE_G4, NOTE_D5, NOTE_C5,
  NOTE_G4, NOTE_G4, NOTE_G5, NOTE_E5, NOTE_C5, NOTE_B4, NOTE_A4,
  NOTE_F5, NOTE_F5, NOTE_E5, NOTE_C5, NOTE_D5, NOTE_C5
};

// Note durations: 4 = quarter note, 8 = eighth note, etc.
int noteDurations[] = {
  4, 8, 4, 4, 4, 2,
  4, 8, 4, 4, 4, 2,
  4, 8, 4, 4, 4, 4, 2,
  4, 8, 4, 4, 4, 2
};

void setup() {
  // Nothing to do here
}

void loop() {
  // Play each note in the melody
  for (int i = 0; i < 25; i++) {
    int noteDuration = 1000 / noteDurations[i];
    tone(buzzer, melody[i], noteDuration);
    delay(noteDuration * 1.3); // Add delay between notes
  }

  // Add a pause after the song
  delay(2000);
}

```

# **4.ການລັນໂປຣແກຣມ ແລະ ການເຮັດວຽກ**
**ທົດລອງສະແກນລິ້ງ QR Code:**

![[Untitled 5.png|204x204]]
# **5.ຜົນລັບຕໍ່ວົງຈອນຕົວຈິງ

![[IMG20241126101500.jpg|471x353]]