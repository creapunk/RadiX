# RadiX Drive Specification

## ⚡ Electrical characteristics

* Input Powering requirements:
	- V<sub>SYSTEM</sub> system supply: 5V<sub>DC</sub> ± 0.2V<sub>DC</sub>
	- V<sub>MOTOR</sub> motor supply: 2-75V<sub>DC</sub> with absolute maximum 90V<sub>DC</sub>
* **Maximum current requirements:** 6A<sub>RMS</sub> 
* Onboard voltage sources (taken from V<sub>SYSTEM</sub> ):
	- 3.3V Buck DC-DC for system supply
	- 12V Boost DC-DC for mosfets supply
	- 3.3V LDO for analog domain

------

## 🔄 Motor Driving Control Capabilities

- **Supported load types:** 
	- Brushed DC motor: 2x 8A<sub>RMS</sub> or 1x 16A<sub>RMS</sub>
	- Stepper motor: 1x Unipolar or Bipolar 8A<sub>RMS</sub>
	- BLDC or PMSM: 1x 8A<sub>RMS</sub>
	- Solenoid: 4x 8A<sub>RMS</sub> or 2x 16A<sub>RMS</sub> or 1x 32A<sub>RMS</sub>
	- Transformers: 2x 8A<sub>RMS</sub> or 1x 16A<sub>RMS</sub>
- **Maximum output current I<sub>RMS</sub>:** **8A<sub>RMS</sub>** per channel with **12A<sub>PEAK</sub>**
- **Maximum output power P<sub>MAX</sub>:** 450W<sub>RMS</sub>@75V with 600W<sub>PEAK</sub>@75V 
- Maximum rated power P<sub>RATED</sub>: **P<sub>RATED</sub> ≤ 6 x V<sub>MOTOR</sub>** and **P<sub>RATED</sub> ≤ 4 x I<sub>RMS</sub>**
- **Energy saving features:** Passive Braking, Freewheeling and automatic power down
- **Working PWM frequency F<sub>PWM</sub>:** up to **83kHz** (11bit resolution) with up to 99.5% duty cycle
- **Maximum phase channel resistance:** 30mΩ
- **Supported position sensors:**
	- 2x ABZ encoder
	- SPI/SSI encoder
	- 2x UART/USART encoder
	- I2C encoder
	- Hall sensor (3 inputs)
- **Diagnostic functions:** overheat detection, short-circuit detection, overcurrent detection for each channel, under-voltage detection, over-voltage detection, open-load detection

------

## 🖥️ MCU Performance and External interfaces

**MCU:** High-performance Arm Cortex-M4 MCU **STM32G431CB** running at **170MHz** with:

- **128KB Flash** memory and **32KB SRAM** memory and **1Kb OTP**
- Math accelerator with trigonometric functions calculations support;
- True random number generator
- Internal HSI and RTC with external oscillator option

**Interfaces:**

- **USB2.0** for PC communication
- **CAN-Bus** with CAN-FD 5MBit/s support for high-speed or long-range wired connection with daisy chain connection option

- **SWD** programming interface with reset feature 
- 11x fast multifunctional bidirectional 5V tolerant I/O with hardware support of:
	- 2x **USART**, 2x UART, 3x UART Single wire
	- 2x **I2C**
	- 1x **SPI or SSI**
	- 2x ABZ
	- Custom functionality

**I/O protection features**:

- ESD protection (persistent against electrostatic discharge)
- Overcurrent protection

**User interaction:**

- **RGB LED** for indication of working mode or current status

------

## 📏 Mechanical data

- **Size dimensions:**
	- PCB outline: 58x37.5x4mm
	- **Driver housing:** 64x49x10mm
- **Weight:**
	- **10g** board only
	- **60g** with aluminum housing

------

## 🔥 Operating conditions

- **Working temperature range:** **-25 to +80** degrees Celcius
- **Environment humidity range:** 0 to 90%
- **Environmental safety:** potential **Lead-Free** and **RoHS** compliance
- **Maximum heat dissipation**: 15W from motor control circuit and 0.5W from other system
