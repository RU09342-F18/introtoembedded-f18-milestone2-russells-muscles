# Milestone 2: Closed Loop Systems
## Summary
The code included in this repository was designed with the MSP430F5529 to find and display the temperature of a room in Celcius. A desired temperature can be entered determining the applied fan speed changing the temperature until the desired temperature is reached then the fan will keep the temperture up to a range of 3 degrees Celcius.

## General Functionality
The code works with different circuits measuring the temperature of the room and determining the fan speed using the microcontroller. A voltage divider is used with a thermistor to determine the temperature by measuring the voltage of the voltage divider with the analog digital converter in the MSP430F5529. The number of samples are determined by TimerA1. After the voltage is measured the resistance of the thermistor is calcualted and from this the temperature is calculated in Celcius this process in completed in the ADC interrupt activated by the TimerA1 interrupt also toggling a green LED. From this and the initial desired temperature the PWM duty cycle is determined making the fan change in speed in a few if statements. If the temperature goes too low the fan turns off and if the temperature approaches the desired the fan slows the change in temperature. If the temperature is too high the fan turns on high depending on the distance from the desired temperature then when two degrees above the desire temperature the fan slows to slow the temperature change. A new desired temperature can also be changed from the initial of 20 degrees Celcius using UART to the  UCA1RXD pin with an interrupt that detects the input of the pin.
 
## Inputs and Outputs of Microcontroller

### MSP430F5529
 INPUTS: P4.5-PM_UCA1RXD
 OUTPUTS: P4.7-Green LED, P4.4-PM_UCA1TXD, P2.0-Timer1 Hardware PWM
 Timer: TimerA1

## Authors

   Author: Kieran O'Connor and Shane Price  
   Last Editted: 11/30/2018
