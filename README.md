# Biometric Based Electronic Voting Machine (Fingerprint-Based EVM)

## Project Overview
This project is an IoT-based Electronic Voting Machine (EVM) that uses fingerprint authentication to ensure that only registered voters can cast a vote. The system is built around an ESP32 microcontroller and integrates a fingerprint sensor, LCD display, push buttons, and a voice module to create a secure and user-friendly voting platform.

The primary objective is to eliminate unauthorized voting and prevent duplicate votes by validating each voter through biometric fingerprint verification.

---

## Features

- Biometric voter authentication using fingerprints
- One-person, one-vote mechanism
- Fingerprint enrollment and database management
- ESP32-based embedded implementation
- LCD display for user interaction
- Push-button candidate selection
- Voice feedback for user guidance
- Persistent vote storage using ESP32 Preferences library
- Low-cost and portable design
- Suitable for academic and demonstration purposes

---

## System Architecture

1. Voter places finger on the fingerprint sensor.
2. Fingerprint is matched against stored templates.
3. If authentication is successful:
   - System checks whether the voter has already voted.
   - If not, voting options are displayed.
4. Voter selects a candidate using push buttons.
5. Vote count is updated and stored.
6. User receives LCD and voice confirmation.
7. Duplicate voting is blocked.

---

## Hardware Components

| Component | Purpose |
|------------|----------|
| ESP32 Development Board | Main controller |
| Adafruit Fingerprint Sensor | Biometric authentication |
| 16x2 I2C LCD Display | User interface |
| Push Buttons | Candidate selection |
| Voice Module | Audio prompts |
| Power Supply | System power |
| Connecting Wires | Hardware interfacing |

---

## Software Requirements

- Arduino IDE
- ESP32 Board Package
- Adafruit Fingerprint Sensor Library
- LiquidCrystal_I2C Library
- Preferences Library (ESP32)

---

## Pin Configuration

### Voting Buttons

| Function | GPIO |
|----------|------|
| Candidate 1 | GPIO 25 |
| Candidate 2 | GPIO 32 |
| Candidate 3 | GPIO 33 |

### Fingerprint Sensor

| Fingerprint Module | ESP32 |
|-------------------|-------|
| TX | GPIO 16 |
| RX | GPIO 17 |

### Voice Module

| Voice Module | ESP32 |
|-------------|-------|
| RX | GPIO 27 |
| TX | GPIO 26 |

---

## Project Workflow

### Step 1 – Database Cleaning
The fingerprint sensor memory is cleared before registering new voters.

Functions used:
- verifyPassword()
- getTemplateCount()
- emptyDatabase()

### Step 2 – Fingerprint Enrollment
Each voter fingerprint is enrolled and assigned a unique ID.

Enrollment process:
1. Place finger
2. Capture first image
3. Remove finger
4. Capture second image
5. Generate fingerprint model
6. Store template

### Step 3 – Voting Operation
1. Authenticate voter
2. Verify voting eligibility
3. Display candidates
4. Record vote
5. Store vote count
6. Prevent duplicate voting

---

## Repository Structure

```text
Biometric-Based-EVM/
│
├── README.md
├── code/
│   └── IOT_Code_EVM.txt
│
├── docs/
│   └── FingerPrint Based EVM_Report.pdf
│
├── images/
│   ├── Circuit.jpeg
│   ├── EVM.jpeg
│   └── EVM Working.jpeg
│
└── video/
    └── EVM vdo.mp4
```

---

## Images

### Circuit Diagram
Add the image from:
`images/Circuit.jpeg`
![Circuit Diagram](images/Circuit.jpeg)

### Hardware Prototype
Add the image from:
`images/EVM.jpeg`
![Electronic Voting Machine](images/EVM.jpeg)


---

## Libraries Used

```cpp
#include <Adafruit_Fingerprint.h>
#include <LiquidCrystal_I2C.h>
#include <Preferences.h>
```

---

## Advantages

- Secure voter authentication
- Prevents multiple voting
- Low-cost implementation
- Easy deployment
- User-friendly interface
- Expandable for larger databases

---

## Limitations

- Limited fingerprint storage capacity
- Prototype-level implementation
- Not intended for official election use
- Requires prior fingerprint enrollment

---

## Future Enhancements

- Cloud-based vote monitoring
- IoT dashboard integration
- Face recognition support
- Aadhaar/National ID integration
- Remote vote analytics
- Blockchain-based vote security

---

## Demonstration

A demonstration video is available in:

```text
video/EVM vdo.mp4
```

---

## Author

**Roshan Robbin**  
M.Tech Embedded Systems  
National Institute of Electronics & Information Technology (NIELIT)

---

## License

This project is released for academic and educational purposes.
