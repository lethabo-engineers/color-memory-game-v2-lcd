# Getting Started — v2 (LCD Upgrade)

## Build

### Final build
![Final build](../images/FINAL_BUILD_V2.jpg)

### Wiring overview
![Wiring overview](../images/WIRING_OVERVIEW_V2.jpg)

---

## Notes
This is **Version 2** of the Arduino Mega color memory game. The goal is to keep the v1 gameplay the same, but add an LCD so the game has a proper UI (score, round, prompts).

---

## Hardware Overview
**Main board:** Arduino Mega 2560  
**Outputs:** LEDs (pattern display) + 16x2 LCD  
**Inputs:** Push buttons

---

## Pin Map (v2)

### LEDs
- LED1 (Red)    → D2  
- LED2 (Green)  → D3  
- LED3 (Blue)   → D4  
- LED4 (Yellow) → D5  

### Buttons (`INPUT_PULLUP`)
- BTN1 → D6  
- BTN2 → D7  
- BTN3 → D8  
- BTN4 → D9  
> Pressed = LOW, Released = HIGH

### LCD 
- RS  → (pick a free pin)
- E   → (pick a free pin)
- D4–D7 → (pick 4 free pins)
- VSS → GND
- VDD → 5V
- VO  → middle pin of potentiometer (contrast)
- A/K → backlight power (if used)

---

## Wiring Guide

### LEDs
- Anode (long leg) → Arduino pin
- Cathode (short leg) → 220Ω resistor → GND

### Buttons (`INPUT_PULLUP`)
- One side → GND
- Other side → Arduino pin

### LCD
- Wire based on I2C or parallel option above

---

## LCD Display Plan (v2 UI)
Suggested screens:
- Startup: `Color Memory Game`
- Watch mode: `Watch the pattern`
- Your turn: `Your turn`
- Round/Score: `Round: X`
- Game over: `Game Over | Score: X`

---

## Upload & Test Checklist
- [ ] LEDs all work
- [ ] Buttons read correctly (INPUT_PULLUP)
- [ ] LCD powers on and shows text
- [ ] Pattern playback works
- [ ] Input checking works
- [ ] LCD updates correctly on round/game-over

---

## Troubleshooting

### LCD is on but shows blank blocks
- Contrast is wrong (adjust the potentiometer)  
- Wrong I2C address / wiring (if I2C)

### LCD doesn’t show at all
- Check VCC/GND
- Check SDA/SCL pins if I2C
- Confirm you’re not using pins already used by LEDs/buttons
