---
layout: page
title: FPGA-based remote-controlled car
description:
  We develope a remote-controlled car based on Xlinx EGO-1 FPGA board as a microcontroller.
  The car is equipped with L298N stepper motor drivers and 4 two-phase four-wire stepper motors.
  The FPGA board is utilized for bluetooth communication, instruction encoding and stepper motor control.
  User can send instructions with desired direction and speed via Bluetooth to control the car.
  The proposed design demonstrates the capabilities of FPGA-based systems for implementing complex control functions in robotic applications. <br>
  This is the project of a <b>3rd-year undergraduate course </b> at XJTU.
img: /assets/img/verilog_car.gif
importance: 9
category: coursework
---

This project aims to implement a remote-controlled car using the EGO1 FPGA (Field Programmable Gate Array) board from Xilinx. The project heavily utilizes digital electronic technology knowledge and hardware description language (HDL) development skills, combining combinatorial logic circuits, sequential logic circuits, serial communication, Bluetooth communication, and stepper motor control. The hardware setup includes the EGO1 board, L298N stepper motor driver, and 4 two-phase four-wire stepper motor.

The project is divided into three parts: Bluetooth communication, instruction encoding, and motor control.

- The Bluetooth communication is based on the integrated Bluetooth module (BLE-CC41-A) on the FPGA board. The control program of the Bluetooth module is responsible for controlling the Bluetooth status, transmitting and receiving Bluetooth signals, and performing UART serial communication between the Bluetooth module and the instruction encoding module.
- The instruction encoding module is entirely implemented by Verilog HDL within the FPGA board. By defining instruction encoding protocol, the instruction encoding module on FPGA board converts the hexadecimal data received by the Bluetooth module, including the motor's working mode, speed, and steering angle, into motor control commands. Since 4 wheels are encoded individually, the car is able to achieve steering by sending different commands to each wheel.
- The motor control module includes the L298N stepper motor driver and four stepper motors. The control commands are periodic pulse digital signals, which can be sent to stepper motor drivers. The motor driver L298N converts the pulse signals to power output which can be used to drive the stepper motor. Since we use an eight-step method to control steering angles, which can achieve a minimum steering angle of 0.9 degrees.

Our system also allows control of the car's movement direction and speed through ASCII character input from a mobile app.

To summerize, this project highlights the FPGA HDL development of Bluetooth communication, hardware decoding and encoding, and hardware control of stepper motors.

<video controls autoplay="true" width="640">
    <source src="/assets/img/verilog_car.mp4" type="video/mp4">
    Download the
    <a href="/assets/img/verilog_car.mp4">MP4</a>
    video.
</video>
