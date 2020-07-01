**<span>**Outline**</span>**

*   **<span>**Use cases.**</span>**
*   **<span>**Target to start with.**</span>**
*   **<span>**A quick comparison of TIC2000 and STM32H7 (Dual-core MCUs)**</span>**

**<span>**Use Cases:**</span>**

**<span>UC1</span>** **<span>: Battery Management Systems</span>**

Customer: Eberspaecher

PP1: Use of lookup tables for their algorithms.

<span style="color: rgb(51,51,51);">PP2: No simulation capabilities yet in their ecosystem. They want to put more emphasis on doing simulation before coding.</span>

They've designed battery management systems for ~20 years. They used to be Venture, they were acquired by Eberspaecher 4 years ago. Common industries they sell their systems to are portable medical devices, defense (radios), industrial (forklifts), and green renewable energy storage. <span style="color: rgb(51,51,51);">A combination of trying to take on more complex designs (large format systems) and a new hire (recent grad) MATLAB/Simulink champion led to an interest in our tools. They want to create models for state of charge and other functions that are easier to work within an environment like Simulink instead of writing hand-code (C). Reusability came up often during the meetings.</span>

*   Currently, they don't look at dynamic responses. Typically they look at behavior over seconds and minutes. 
*   They work with a variety of chemistries.
*   Their current SOC (State of Charge)algorithms are based on look-up tables (OCV (Open circuit voltage) and temperature)
*   They want to put more emphasis on doing simulation before coding, they recognize the benefits of spending more time upfront on model development.
*   <span style="color: rgb(51,51,51);">Sending resources for code generation optimization, ISO 26262, Stateflow/cell balancing example, and overview of CAN message capabilities.</span>
*   <span style="color: rgb(51,51,51);">Ideally, they want to have small pieces of their models/systems that are standard across all the work they do, and then layer the customization needed for a particular customer or project on top of those standard pieces.</span>

<span style="color: rgb(51,51,51);">They work with a variety of targets. For microcontrollers, typical ones are the STM32 family, Pic 24, TI dual-core processors.</span>

**<span>UC2: </span>** **<span>SoCB for hardware architecture and quick prototyping.*</span>**

**<span>Customer: </span>** **<span>Sony LSI Design Inc.</span>** <span> </span>

<span>PP1: They would like to use multiple AXI4 slaves to one master.</span>

<span>PP2: No support for MicroBlaze, other CPUs like ARM Cortex M0 and RISC-V.</span>

<span>SONY LSI is making ASICs for Signal processing, communication, and image processing.  They are existing users of HDL Coder but only recently. Developer Suzuki-san seems to be trying to incorporate the MW tools within the company. </span>

<span>Note: They have evaluated the SoCB product in the past.</span>

**<span>UC3</span>** **<span>: </span>** **<span>Support </span>** **<span>for </span>** **<span>ADSP-CM419</span>**

**<span>Customer</span>** **<span>: Generic</span>**

<span>Currently,</span> <span> the analog devices processor,</span> <span> ADSP-CM419F (</span> <span>Mixed-Signal Dual-Core Control Processor with ARM Cortex-M4/M0 and 16-bit ADCs</span> <span>) is not supported to be used with MATLAB or Simulink.</span> <span> The customer wants this support to be implemented.</span> <span> </span>

Customers workflow<span>: </span> <span>The model has a three-phase PWM rectifier and the customer would like to generate a gate signal using this processor and also some code that need</span> <span>s to be run on this processor.</span>

**Other Use Cases:**

**<span>UC4: Motor control application</span>**

**<span>Customer: Generic</span>** <span> </span>

<span>The customer wants to use the </span> <span>STM32 motor-control pack using the FOC algorithm for three-phase, low voltage, and low-current motor. He decided to work on the </span> <span>P-NUCLEO-IHM03 with STM32 NUCLEO-G431RB + Microcontroller STSPIN830 and Motor Driver Port. The above-mentioned combo from ST gives quick prototyping capability which in turn reduces cost and time to market.</span> <span> </span>

<span> </span>

**UC5: Low-Cost Prototyping solutions **

**<span>Customer: </span>** **<span>Neptronic</span>** <span> </span>

<span>PP1: No Support for <span style="color: rgb(51,51,51);">Target STM32 F0.</span></span>

<span><span style="color: rgb(51,51,51);">PP2: Currently they deploy handwritten code and they want to integrate that code with the model-based design.</span></span>

<span>Neptronic is a manufacturer of actuator products based out of </span> <span>Montreal. They are interested in low-cost prototyping platforms such as  Arduino and Cortex M0 boards which can provide the embedded code generation workflow for their products like piezo actuators and DC motor controllers.</span> <span> **T<span style="color: rgb(51,51,51);">hey do not use our tools right now.</span>**</span>

**<span>UC6: Algorithm generation using MATLAB </span>** <span> </span>

**<span>Customer: </span>** **<span>BAE Systems Inc.</span>** <span> </span>

<span>PP1: <span style="color: rgb(51,51,51);">Do not trust that MATLAB Coder gives the exact C code that would be trustable on board the system.</span></span>

<span>BAE Systems Inc is an Aerospace company based out of the UK. They are interested in exploring the algorithm development capabilities of MATLAB. Their embedded system is based on ARM Cortex M.</span> <span> </span>

**<span>UC7: Optimized code generation from MBD</span>** **<span>.</span>** <span> </span>

**<span>Customer: </span>** **<span>John Deere GmbH & Co. KG ETIC</span>**

<span>John Deere is an American corporation that manufactures agricultural, construction, and forestry machinery, diesel engines. They are interested in model-based design and optimized automatic code generation to meet the project deadline and time to market their products. Currently, they are using the EC workflow for their Cortex M targets. </span> <span>Code is integrated into Keil and compiled for an ARM Cortex M-3 and debugging is done in the Keil environment.</span> <span> </span>

<span> </span>

**<span>UC8: Code generation for the medical control </span>** **<span>system.</span>** <span> </span>

**<span>Customer: </span>** **<span>W.O.M. WORLD OF MEDICINE GmbH</span>** <span> </span>

<span>PP1: <span style="color: rgb(51,51,51);">Time to find errors, debugging.</span></span>

<span><span style="color: rgb(51,51,51);">PP2: Want to reduce testing effort.</span></span>

<span>WOM is a pioneer and world leader in the field of Minimally Invasive Medicine. As a medical device company with an international focus. They are interested in </span> <span>PIL and </span> <span>simulation for identifying new test cases. Currently, they are using o</span> <span>ne platform for all products; currently Arm Cortex M4 (single-precision, floating-point).</span> <span> </span>

Workflow: 

1.  One platform for all products; currently Arm Cortex M4 (single-precision, floating-point).
2.  SW is directly tested @ physical prototype.

**<span>UC9: Signal Processing using Simulink</span>** <span> </span>

**<span>Customer: </span>** **<span>Bürkert Werke GmbH</span>** <span> </span>

<span>This group is developing fluid flow rate sensors that are part of a flow rate controller. The sensor concept is based on the measurement of temperatures of the fluid. Therefore the fluid</span> <span> is heated up to a defined temperature at the inlet of the sensor and the temperature at the outlet is measured. Thus the flow rate can be calculated which is proportional to the outlet temperature and the thermal losses. Their interest is a</span> <span>utomatic C-Code Generation for STM 32 / GNU environment, mainly floating point, no real need for fixed point.</span> <span> </span>

<span> </span>

**<span>UC10: Automatic code generation for wearables. </span>** <span> </span>

**<span>Customer: </span>** **<span>Sony Digital Network Applications Inc.</span>** <span> </span>

<span>PP1: <span style="color: rgb(51,51,51);">The C codes generated from MATLAB Coder are high power consumption.</span></span>

<span>The SONY </span> <span>Digital Network Applications Inc. </span> <span>wants to use MATLAB Coder to generate C codes for their new wearable device implementation based on the MATLAB programs from their research department. Their interest is in </span> <span>Auto-generate embedded C codes from the research department's MATLAB programs that will save time and cost. T</span> <span>he processor is ARM Cortex-M4 + ARM CMSIS libraries that can be used in the MATLAB Coder generated C codes.</span>

**Target to start with**

1.  F767ZI (Arun and Vikky had done some work on motor control example for SoCB). We can start from this board as we have some prior experience with this one.
2.  Start with STM32H745 and make ST at par with TI support, and scale the supported block by making use of the EC blocks.
3.  Add support for only Cortex M which will be vendor-agnostic
    1.  TMS320F2838x contains one ARM core as well 

**Quick Comparision between TMS320F2838x and STM32H745**

<table class="wrapped"><colgroup><col> <col> <col></colgroup> 

<tbody>

<tr>

<td>

<span> </span>

</td>

<td>

**TMS320F2838x**

</td>

<td>

**STM32H745**

</td>

</tr>

<tr>

<td colspan="1">Core</td>

<td colspan="1">

Dual-core C28x architecture 

1.  Two TMS320C28x 32-bit CPUs + Arm Cortex M4 Based Connectivity Manager
2.  200 MHz
3.  DP-FPU
4.  Trigonometric Math Unit (TMU)
5.  CRC engine and instructions (VCRC)
6.  Fast Integer Division (FINTDIV)

</td>

<td colspan="1">

Dual-core Arm architecture

1.  32-bit Arm® Cortex®-M7 + 32-bit Arm® 32-bit Cortex®-M4
2.  480 MHz
3.  DP-FPU
4.  ART Accelerator™
5.  DSP instructions in the ISA

</td>

</tr>

<tr>

<td colspan="1">Second Core</td>

<td colspan="1">

Arm® Cortex® M4 processor

1.  125 MHz
2.  Flash: 512 KB
3.  RAM: 96 KB

</td>

<td colspan="1">

Arm® Cortex® M4 processor

1.  240 MHz
2.  Flash: Up to 2 MB (Shared between CM7 and CM4)
3.  RAM: 1 MB of RAM (Shared between CM7 and CM4)
4.  Uses a memory controller.

</td>

</tr>

<tr>

<td>

<span>Connectivity</span> <span> </span>

</td>

<td>

1.  <span>I2C</span> <span> </span>
2.  <span>SPI</span> <span> </span>
3.  <span>UART</span> <span> </span>
4.  <span>McBSP (</span> <span>Multichannel Buffered Serial Port </span> <span>)</span> <span> </span>
5.  <span>CAN </span> <span> </span>
6.  <span>LIN </span> <span> </span>
7.  <span>USB</span> <span> </span>
8.  <span>FSI</span> <span> </span>
9.  <span>Ethernet</span>
10.  <span>CAN FD</span>
11.  <span>EtherCAT</span>

</td>

<td>

1.  <span>I2C</span> <span> </span>
2.  <span>SPI</span> <span> </span>
3.  <span>USARTs</span> <span> </span>
4.  <span>LPUART</span> <span> </span>
5.  <span>I2S,SAIs (serial audio interface) SPDIFRX,</span> <span> </span>
6.  <span>SWPMI single-wire protocol master interface</span> <span> </span>
7.  <span>SD/SDIO/MMC,</span> <span> </span>
8.  <span>CAN FD,</span> <span> </span>
9.  <span>USB OTG,</span> <span> </span>
10.  <span>Ethernet MAC, </span> <span> </span>
11.  <span>HDMI-CEC </span> <span> </span>
12.  <span>Camera interface</span>

</td>

</tr>

<tr>

<td>

<span>Sensing</span> <span> </span>

</td>

<td>

1.  <span>ADC : 12-16-bit (up to 12.5 MSPS)</span> <span> </span>
2.  <span>Sigma-delta filter modules.</span>
3.  <span>PGAs for easy signal conditioning</span> <span> </span>

<span> </span>

</td>

<td>

1.  <span>ADC: 16-bit (up to 36 channels, up to 3.6 MSPS)</span> <span> </span>
2.  <span>Digital filters for sigma-delta modulator (DFSDM) </span>
3.  <span>Internal temperature sensor </span> <span> </span>
4.  <span>12-bit D/A converters (1 MHz)</span> <span> </span>
5.  <span>Ultra-low-power comparators </span> <span> </span>
6.  <span>Operational amplifiers (7.3 MHz bandwidth) </span> <span> </span>

</td>

</tr>

<tr>

<td>

<span>Actuation</span> <span> </span>

</td>

<td>

1.  <span>HRPWM </span> <span> </span>
2.  <span>Advanced </span> <span>time synchronization between PWMs</span> <span> </span>
3.  <span>Advanced inter-PWM and ADC synchronization</span> <span> </span>
4.  <span>Variety of timer count modes</span> <span> </span>
5.  <span>Customizable triggering</span> <span> </span>
6.  <span>External DACs for reference bias waveform generation</span> <span> </span>
7.  <span>Advanced protection</span> <span> </span>
8.  <span>Directly trip PWMs without CPU i</span> <span>ntervention, nor clocking</span> <span> </span>
9.  <span>Supports PWM s</span> <span>hutdown or cycle-by-cycle PWM modification</span> <span> </span>
10.  <span>Peak current-mode control support</span> <span> </span>

</td>

<td>

1.  <span>High-resolution timer (2.1 ns max resolution) </span> <span> </span>
2.  <span> 32-bit timers with up to 4 IC/OC/PWM or pulse counter and quadrature (incremental) encoder input (up to 240 MHz)</span> <span> </span>
3.  <span>16-bit advanced motor control timers (up to 240 MHz) </span> <span> </span>
4.  <span>10× 16-bit general-purpose timers (up to 240 MHz) • 5× 16-bit low-power timers (up to 240 MHz) </span> <span> </span>
5.  <span>watchdogs (independent and window)</span> <span> </span>
6.  <span>SysTick timer</span> <span> </span>
7.  <span>RTC with sub-second accuracy and hardware calendar</span> <span> </span>

</td>

</tr>

<tr>

<td>

<span>Exclusive feature</span>

</td>

<td>

<span>C</span> <span>onfigurable Logic Block (CLB)</span> <span> </span>

</td>

<td>

<span>3DES, AES 256, GCM, CCM SHA-1, SHA-256, MD5, HMAC Crypto/Hash processor Security services SFI and SB-SFU</span> <span> </span>

</td>

</tr>

<tr>

<td>

<span>Performance </span> <span> </span>

</td>

<td>

<span>100-925 DMIPS </span> <span> </span>

</td>

<td>

<span>1327 DMIPS/ 3224 CoreMark</span> <span> </span>

</td>

</tr>

<tr>

<td>

<span>Summary </span> <span> </span>

</td>

<td>

1.  <span>C2000 series MCUs are field-proven and very much suited for Sensing and control applications.</span> <span> </span>
2.  <span>Very focused on control applications and offers very powerful sensing and control peripherals.</span>

</td>

<td>

1.  <span>STM32H7 series MCUs are new to the market and it covers a wide range of applications such as multimedia, HMI and industrial control. </span> <span> </span>
2.  <span>It also supports the advanced security features which are becoming important as there are many advancements in the connected products.</span> <span> </span>

<span> </span>

</td>

</tr>

</tbody>

</table>

**Gecks:**

<span>ARM Cortex M</span> <span> </span>

1.  <span>P-NUCLEO-IHM03 with STM32 NUCLEO-G431RB + Microcontroller STSPIN830 and Motor Driver Port  </span> [<span>http://komodo.mathworks.com/main/gecko/view?Record=2221557</span>](http://komodo.mathworks.com/main/gecko/view?Record=2221557) <span> </span>
2.  <span>Support ADSP-CM419F processor with Simulink  </span> [<span>http://komodo.mathworks.com/main/gecko/view?Record=1486580</span>](http://komodo.mathworks.com/main/gecko/view?Record=1486580) <span> </span>
3.  <span>Can MATLAB Generate Fixed Point for ARM (A and M series)?  Lots of interest in fixed-point design.  Curious how to configure for specific processors.</span> [<span>https://inside-labs.mathworks.com/salesservice/ers/ersEvent/27678</span>](https://inside-labs.mathworks.com/salesservice/ers/ersEvent/27678) <span> </span>
4.  <span>The processor is ARM Cortex-M4\. And ARM CMSIS libraries can be used in the MATLAB Coder generated C codes. </span> [<span>https://inside-labs.mathworks.com/salesservice/ers/ersEvent/13173</span>](https://inside-labs.mathworks.com/salesservice/ers/ersEvent/13173) <span> </span>
5.  <span>Automatic C-Code Generation for STM 32 / GNU environment, mainly floating point, no real need for fixed point. The code for the operation panel is written manually and integrated with auto code. They have embedded coder experience, but this has not yet been unused for this sensor </span> [<span>https://inside-labs.mathworks.com/salesservice/ers/ersEvent/12260</span>](https://inside-labs.mathworks.com/salesservice/ers/ersEvent/12260/)
6.  <span>W.O.M. WORLD OF MEDICINE GmbH, </span> <span>One platform for all products; currently Arm Cortex M4 (single-precision, floating-point) </span> [<span>https://inside-labs.mathworks.com/salesservice/ers/ersEvent/11018</span>](https://inside-labs.mathworks.com/salesservice/ers/ersEvent/11018) <span> </span>
7.  <span>Existing EC customer, Code is integrated into Keil and compiled for an ARM Cortex M-3 </span> [<span>https://inside-labs.mathworks.com/salesservice/ers/ersEvent/9734</span>](https://inside-labs.mathworks.com/salesservice/ers/ersEvent/9734) <span> </span>
8.  <span>Support for Micro Blaze, other CPUs like ARM Cortex M0 </span> [<span>https://inside-labs.mathworks.com/salesservice/ers/ersEvent/32802</span>](https://inside-labs.mathworks.com/salesservice/ers/ersEvent/32802) <span> </span>
9.  <span>Embedded System is some type of ARM Cortex </span> [<span>https://inside-labs.mathworks.com/salesservice/ers/ersEvent/32890</span>](https://inside-labs.mathworks.com/salesservice/ers/ersEvent/32890) <span> </span>
10.  <span>Target STM32 F0 </span> [<span>https://inside-labs.mathworks.com/salesservice/ers/ersEvent/32597</span>](https://inside-labs.mathworks.com/salesservice/ers/ersEvent/32597) <span> </span>
11.  [<span>http://komodo.mathworks.com/main/gecko/view?Record=1749414</span>](http://komodo.mathworks.com/main/gecko/view?Record=1749414)
12.  <span>[https://inside-labs.mathworks.com/salesservice/ers/ersEvent/29935](https://inside-labs.mathworks.com/salesservice/ers/ersEvent/29935)</span>
13.  <span>run C code on different processors, and find out the effect of changing cache size, vary parameters, and perform tradeoffs to see what would give her the most benefit. </span> [<span>https://inside-labs.mathworks.com/salesservice/ers/ersEvent/34401</span>](https://inside-labs.mathworks.com/salesservice/ers/ersEvent/34401)

**Misc**

*   [<span>Getting started with STM32 Motor control SDK5.0</span>](https://www.youtube.com/watch?v=h3ZuM2Z0UGs) <span> </span>
*   [<span>Plug&Play Design - Very Precise Field Oriented 3-Phase Motor Control (STSPIN32F0 eval board)</span>](https://www.youtube.com/watch?v=efq2wUOcg2A) <span> </span>
*   <span>[http://www.brianchavens.com/2018/09/20/motor-control-microcontroller-performance-comparison](http://www.brianchavens.com/2018/09/20/motor-control-microcontroller-performance-comparison/)</span>
*   RISC-V 

    1.  [<span>https://inside-labs.mathworks.com/salesservice/ers/ersEvent/34401</span>](https://inside-labs.mathworks.com/salesservice/ers/ersEvent/34401) <span> </span>
    2.  [<span>https://inside-labs.mathworks.com/salesservice/ers/ersEvent/34233</span>](https://inside-labs.mathworks.com/salesservice/ers/ersEvent/34233) <span> </span>
    3.  [<span>https://inside-labs.mathworks.com/salesservice/ers/ersEvent/32802</span>](https://inside-labs.mathworks.com/salesservice/ers/ersEvent/32802) <span> </span>
    4.  [<span>https://inside-labs.mathworks.com/salesservice/ers/ersEvent/32802</span>](https://inside-labs.mathworks.com/salesservice/ers/ersEvent/32802) <span> </span>
