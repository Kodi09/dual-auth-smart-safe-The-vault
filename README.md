# Secure Vault with Dual Authentication (RFID + Face Recognition)
A hardware-based secure vault system that combines RFID authentication
and facial recognition to control a servo-driven locking mechanism.

<img width="436" height="245" alt="1" src="https://github.com/user-attachments/assets/c9e8038f-4e87-4e81-b30c-7d54c3190204" /> &nbsp;&nbsp; <img width="380" height="245" alt="2" src="https://github.com/user-attachments/assets/7f7b8e0e-4ae4-41d6-a71b-ab79cdf87333" />

## Overview
This group project demonstrates a secure physical vault system using a dual-layer authentication pipeline. Access is granted only when both RFID credentials and facial identity verification succeed. The system integrates embedded electronics, computer vision, and mechanical actuation using an Arduino–Raspberry Pi architecture.  
The vault enclosure and component housing were custom designed and 3D printed to securely mount the electronics and locking mechanism.  
Access the demo here: https://drive.google.com/file/d/1lSihVzP1OhVPipp5lbZ8LVXCogkNITz8/view?usp=share_link

## System Architecture
The system is split into two main processing units:
- **Arduino Uno** handles RFID validation, servo control, and buzzer feedback
- **Raspberry Pi 4** performs facial recognition using a camera module

Both systems communicate over serial to coordinate authentication and actuation. 

## Authentication Workflow
1. User taps an RFID card on the reader and the UID is validated against stored credentials.
2. Upon successful RFID validation, the 7'display prompts the user and shows a live camera preview to assist with face alignment.
3. The Raspberry Pi captures the user’s face and performs facial recognition by comparing the image against pre-trained facial data.
4. If both RFID and facial authentication succeed, a command is sent to the Arduino to rotate the servo and unlock the vault for a fixed duration before returning to the locked position.
5. Visual messages on the screen and audible buzzer alerts indicate access granted or denied at each stage.
6. All authentication attempts are logged with timestamps, including RFID UID, facial recognition outcome, and final access status.

## Circuit Diagram
The following diagram shows the wiring between the Arduino,Raspberry Pi, RFID reader, servo motor, and buzzer.
<img width="389" height="433" alt="Screenshot 2026-01-20 at 5 15 12 PM" src="https://github.com/user-attachments/assets/86dd3ac3-2698-4e79-87c3-c87e42bd1fcb" />

This design demonstrates a complete end-to-end embedded system that integrates sensing, perception, decision-making, and physical actuation.



